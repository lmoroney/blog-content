---
title: My Sound to Emoji ML App for WWDC21Challenges
layout: article
tags: ai coding personal 
---
Open sourcing my Sound->Emoji demo app. I created this as part of the app challenges at WWDC21!

First of all, you need to be an Apple Developer to do this, because it requires the Xcode 13 beta, and iOS 15 in order to work. It does work really well in the emulator!

As a starting point, I used the code that's available from [Apple Developers](https://developer.apple.com/documentation/soundanalysis/classifying_live_audio_input_with_a_built-in_sound_classifier)

This works really well as a starter -- giving you an app with two views. The first allows you to pick which sounds you want to classify for. The second then has meters indicating the intensity of the chosen sound. 

So, for example, if I'm breathing -- the second view will show something like this:

![Breathing View](/assets/breathing.png)

The following code within ContentView helps you pick which view to render. If you are in setup mode, it will use the SetupMonitoredSoundsView, otherwise it will be the DetectSoundsView:

``` swift
	var body: some View {
        ZStack {
            if showSetup {
                SetupMonitoredSoundsView(
                  querySoundOptions: { return try AppConfiguration.listAllValidSoundIdentifiers() },
                  selectedSounds: $appConfig.monitoredSounds,
                  doneAction: {
                    showSetup = false
                    appState.restartDetection(config: appConfig)
                  })
            } else {
                DetectSoundsView(state: appState,
                                 config: $appConfig,
                                 configureAction: { showSetup = true })
            }
        }
    }
```

 For my emoji viewer, I just edited the original DetectSoundsView to make it much simpler. One suprising thing is that the view redraws *on every inference* which seems excessive, but I didn't change that (for now), which is why the emoji viewing video might look a little flickery.

 I edited DetectSoundsView just to draw a label with the emoji, instead of all the meters from the original with this code:

``` swift
 static func generateDetectionsGrid(_ detections: [(SoundIdentifier, DetectionState)], dictionary: Dictionary<String,String>) -> some View {
        return ScrollView {
            ForEach(detections, id: \.0.labelName) {
                if($0.1.currentConfidence>0.3){
                    Label(dictionary[$0.0.labelName]!, systemImage: "").font(.system(size:120))
                }
            }
        }
    } 
```

This uses a dictionary to convert the label of the detected sound to an emoji. This is just a simple Dictionary<String, String> object that I create by manually assigning a label to an emoji. My code is [here](https://github.com/lmoroney/funcode/blob/master/ios15/classifysound/ClassifySound/Support/EmojiDictionaryHelper.swift)

...and if you want a video of the app in action, you can see it on [my twitter](https://github.com/lmoroney/funcode/blob/master/ios15/classifysound/ClassifySound/Support/EmojiDictionaryHelper.swift)

The full code for the app, borrowing heavily from the apple ample is [here](https://github.com/lmoroney/funcode/tree/master/ios15/classifysound). 






