---
title: Machine Learning for anomaly detection
tags: google talks
---

At Google IO this year, I had many activities, one of which was to teach a workshop in anomaly detection. It uses a novel approach -- by training an encoder-decoder architecture with electrocardiogram (EKG) values and exploring the reconstruction error.

The logic was that when an autoencoder model gets trained on only good EKG values, then the reconstruction error for good ones will be small. Thus, an abnormal EKG would have a high reconstruction error, and if this is above a certain threshold, we know that it's an anomaly.

Watch the entire workshop here:
<div>{%- include extensions/youtube.html id='2K3ScZp1dXQ' -%}</div>