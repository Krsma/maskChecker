# Mask Checker
Mask checker is a neural network model based on the [YoloV3](https://pjreddie.com/darknet/yolo/) deep learning framework which is designed to find and classify people present in the image input which are with or without a protective mask covering of their face.

The network is being trained on organic public images of crowds of people. Using real images of people wearing different types of face covering enables this network to detect people wearing a vast types of masks, from the more advanced respirators and N95/PP3 masks, the general surgical masks, and the various homemade cloth variations of face coverings. 
The model is also being developed in a way to enable to detect the chin, neck, or mouth and other "bad" mask wearing styles.   

The goal of this project is to develop a full system which can help in combating the current COVID19 pandemic, but that can also be used in the future.


**Future goals**
- [ ] Expanded data set 
- [ ] YoloV3 tiny version 
- [ ] DLL/SO export 
- [ ] A portable Raspberry Pi solution
# Installation

**Darknet installation**

Follow the installation process from either the [original](https://github.com/pjreddie/darknet) or the better [Alexei fork](https://github.com/AlexeyAB/darknet) of the Darknet project. Check if Darknet is running normally. 

**Cloning the repository**
1. Clone this repo to a folder
2. Copy the cfg/yolov3_custom_train.cfg to the cfg folder of your Darknet installation
3. Copy the files from data to the data folder of your Darknet installation
4. Download the weights from [here](https://drive.google.com/drive/folders/1qVsUzrx1T2f0cth9M_QwxUDZSpIXcr9C?usp=sharing) and copy it to the Darknet installation folder
5. Download the data set from [here](https://drive.google.com/drive/folders/1WvIBpYkgWm5DdJAByXT4FQuxLf1fKLQq?usp=sharing) and unzip it in the Darknet installation folder


# Usage

**To train from scratch**

`sudo ./darknet detector train data/yolo.data cfg/yolov3_custom_train.cfg cfg/darknet53.conv.74`

If training from scratch you will require the  additional darknet53.conv.74 file.

**To continue training from the weights**

`./darknet detector train data/yolo.data cfg/yolov3_custom_train.cfg maskStandard.weights`

**To detect on an image**

`./darknet detector test data/yolo.data cfg/yolov3_custom_train.cfg backup/yolov3_custom_train.weights [IMAGE_PATH]`

For a more advanced tutorial refer to [the original Darknet repo](https://pjreddie.com/darknet/yolo/).