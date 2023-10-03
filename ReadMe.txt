************** Hands detection and Segmentation with Yolov5 and Segemnt anything Model (SAM) **********************

1: Firstly, we divide the originally given dataset into train and test split. The training set has 132 images while the remaining 18 are in the test set.
2: We annotate the images using labeling software and create Yolo format ground truths for training purposes.
3: The train folder has subdirectories images and labels, and the same test folder has images and labels. Images folders consist of images while labels have annotations (ground truths).
4: I trained the Yolov5 network with the given dataset and got 94.5% mean Average precision. We got trained weights that are present in a folder named "hand_dataset1\Hands_train\yolov5\runs\train\exp453\weights\hand_best.pt".
5. I have written code for yolov5 inference so that we can extract the exact Hand bounding box.
6: That bounding box is then passed to the Segment Anything model (SAM) that generates the segmentation masks around this Bounding box.
7: Finally we save masks as an image that are hands masks.

*********** How to train yolov5 **************
* Install Yolov5 from ultralytics:
!git clone https://github.com/ultralytics/yolov5  # clone
%cd yolov5
%pip install -qr requirements.txt comet_ml  # install

* Generate a custom.yaml file that is present in folder.
* !python train.py --img 640 --batch 16 --epoch 100 --data custom.yaml --weights yolov5m.pt --cache 

