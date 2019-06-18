---
title:  "Week2+3"
date:   2019-06-04 
categories: post
---

## Deliverable:
1. Extracting continuous ticker from videos
2. OCR for ticker 

## Ticker Extracion
As EAST detects continuous regions of text, the previous version of the textdetction algorithm extracted a set of disjoint words
[Example1](/assets/mydoc.pdf)
[Example2](/assets/mydoc.pdf)
The textdetection system had to be modified to combine the continuous words and extract it as a whole. 
To optimize the code and reduce redundant detections I am skipping frames. For the current implementation I am using a skip value of about 100 frames. This value depends on the speed of the ticker and may vary from channel to channel.
[Example2](/assets/mydoc.pdf)
## OCR improvements

All preprocessing done using Python's OpenCV package
### Version1
The first version of OCR that I implemented using tesseract4.0 recognized English characters with a reasonable accuracy. However,the OCR results for Hindi text either produced an unacceptable number of errors in the detected text or completely failed to recognize any text.
[Example2](/assets/mydoc.pdf)

Here is an example of an image for which OCR produced a blank output

###Version2
I discussed the problem with my mentors, Prof Gowri and Abhinav, who suggested that I try applying some image processing techniques such as binartization,threshholding, and thinning as the images were of low resolution.
Binarization and thresholing produced slightly better results, but some of the snapshots were still producing a blank result. 

I tried solving this problem by colour inverting the images that returned blank outputs after OCR and obtained better results

###Final Version
The final touch that I added was noise removal 

Stay tuned for more updates