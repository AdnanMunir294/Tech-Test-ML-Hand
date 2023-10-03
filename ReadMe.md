************** Hands detection and Segmentation with Yolov5 and Segemnt anything Model (SAM) **********************

*  Firstly, we divide the originally given dataset into train and test split. The training set has 132 images while the remaining 18 are in the test set.
* We annotate the images using labeling software and create Yolo format ground truths for training purposes.
*  The train folder has subdirectories images and labels, and the same test folder has images and labels. Images folders consist of images while labels have annotations (ground truths).
*  We trained the Yolov5 network with the given dataset and got 94.5% mean Average precision.
*  I have written code for yolov5 inference so that we can extract the exact Hand bounding box.
*  That bounding box is then passed to the Segment Anything model (SAM) that generates the segmentation masks around this Bounding box.
*   Finally we save masks as an image that are hands masks.

*********** How to train yolov5 **************
* Install Yolov5 from ultralytics:
!git clone https://github.com/ultralytics/yolov5  # clone
%cd yolov5
%pip install -qr requirements.txt comet_ml  # install

* Generate a custom.yaml file that is present in folder.
* Train dataset can be accessed through this link of drive " https://drive.google.com/file/d/1TUCbT4zrIIFmpl0UjFd250ol-PHt7w0x/view?usp=sharing "
* Test dataset can be accessed thourgh this drive link " https://drive.google.com/file/d/1gwd3SylaMq4YAHYdWIUD7ea3HRSPRK5D/view?usp=sharing"
* !python train.py --img 640 --batch 16 --epoch 100 --data custom.yaml --weights yolov5m.pt --cache 
* Trained weights can be accessed through this link "https://drive.google.com/file/d/1BBkHM0uXnUqwMXUl3hKQ0wgHkPkKGRXm/view?usp=sharing".



