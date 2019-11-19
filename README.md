# Person Retrieval in Surveillance Video using Height, Color and Gender

This code contains a Tensorflow implementation for our paper - [Person Retrieval in Surveillance Video using Height, Color and Gender](https://arxiv.org/abs/1810.05080). If you find this code useful in your research, please consider citing: 
```@inproceedings{galiyawala2018person,
  title={Person retrieval in surveillance video using height, color and gender},
  author={Galiyawala, Hiren and Shah, Kenil and Gajjar, Vandit and Raval, Mehul S},
  booktitle={2018 15th IEEE International Conference on Advanced Video and Signal Based Surveillance (AVSS)},
  pages={1--6},
  year={2018},
  organization={IEEE}
}
```
This code was initially tested on an Ubuntu 16.04 system using Tensorflow 1.12. 

![Alt Text](https://github.com/Vanditg/Description_Based_Person_Identification/blob/master/readme_images/Person_Retrieval.jpeg)

**The paper proposes a deep learning-based linear filtering approach for person retrieval using height, cloth color, and gender.**

## Installation

1) Clone this repository.
```
git clone https://github.com/Vanditg/Description_Based_Person_Identification.git
```

2) In the repository, execute `pip install -r requirements.txt` to install all the necessary libraries.
	
3) Three deep learning models are used inorder to filter out the desired person.
	1) *Mask_RCNN:- Used to determine the coordinates of the person and fetch the pixelwise segmentation*
	2) *gender_model:- Used to determine gender of the person*
	3) *color_model:- Used to determine torso color of the person*

4) Download the pretrained weights.
	1) Mask_RCNN [pretrained weights](https://drive.google.com/open?id=1g8hvgQ199VmevOuoTJtaR9yo0CPheqxt) and save it in root directory
	2) gender_model [pretrained weights](https://drive.google.com/open?id=1ZB67dCOY_mSGBFtDL6EteKb_uOTodN9J) and save it in /modalities/gender/ 
	3) color_model [pretrained weight](https://drive.google.com/open?id=13EpN25wSwI5gcoEs8wgJ8OmFx4Y6-YfW) and save it in /modalities/torso_color/ 

### Usage
To use the GUI version
```
python app.py
```

![Alt Text](https://github.com/Vanditg/Description_Based_Person_Identification/blob/master/readme_images/queries_screen.png)

**Browse the video from your local disk and enter the soft-biometric features required to locate the desired person.**

### Important Instructions

1) Currently, Height channel is not used as a filter due to it's dependance on camera parameters.

2) Output frames with bounding box of the desired person are stored in /output/. folder.

## Example Output Frames

![Alt Text](https://github.com/Vanditg/Description_Based_Person_Identification/blob/master/readme_images/output.gif)

**Retrieving a person using torso color blue and gender female.**