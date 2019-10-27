# Feature Extraction

## SIFT
![sift](/Assets/sift.jpg)
![sift comparison](/Assets/sift_compare.jpg)

## Saliency Detection
> Saliency detection is the process of automatically detecting the most “salient” regions of an image. It takes out the important features that are noticeable at once when a human looks at it.
> We used a Fine grained Saliency detection - This algorithm was initially used for detecting humans in images and video streams but can also be generalized to other forms of saliency as well.

![salience](/Assets/salience.jpg)
![salience threshold](/Assets/sal_threshold.jpg)

## Smoothing images
> We used Low-pass filters to smooth out the images and blur the uninteresting parts in the images such as the audience, the arena and the score display. We also applied multiple levels of blurs to get the most interesting features in the image.

## Image Occlusion
> To prevent blurring out the important features, we had certain restrictions on the amount of blur that we can apply. So, in order to eliminate the most obvious noises, we occluded 20% of the data that surrounded the baskball ground.

## Histogram equalization
> A histogram is a very important tool in Image processing. It is a graphical representation of the distribution of data. An image histogram gives a graphical representation of the distribution of pixel intensities in a digital image.
> The histogram equalization process is an image processing method to adjust the contrast of an image by modifying the image’s histogram. This is a good feature to use after eliminating the noise because the lightness of the basketball ground is almost the same everywhere in the region.
![all features](/Assets/final.jpg)
