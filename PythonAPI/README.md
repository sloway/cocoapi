I am working here to trying a evaluation for Mediapipe pose model with COCO Dataset Keypoint


Before getting started, download Dataset  
You can see dataset [here](https://cocodataset.org/#download)  
I am gonna use 2017 Validation images and annotations

For images, unzip [file](http://images.cocodataset.org/zips/val2017.zip) and put them like {root}/images/val2017/*.jpg  
For annotations, unzip [file](http://images.cocodataset.org/annotations/annotations_trainval2017.zip) and put them like {root}/annotations/*.json

The first task is picking images to keypoint test.
This time, I just use images like this  
- Image has a single person
- The person has keypoints more than 13
And output is gonna be csv or json file having image data to be used as input of Mediapipe pose detection.

The second task is pose detection by Mediapipe 
Because mediapipe pose solution returns more keypoints than Coco dataset with another format, I need some converting.  
Output will be used as input of estimating AP metric by pycocotools,  
Format should be like [this](https://cocodataset.org/#format-results)

The final task is estimating AP metric.
If output from 2nd task is generated properly,  
At this stage, all I need to do is just running evaluation function of pycocotools

Let's get started




