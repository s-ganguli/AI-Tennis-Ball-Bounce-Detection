# Capstone
# AI Ball Bounce Detector
By Aditya Patel and Sharadwata Ganguli

## <a href="https://docs.google.com/document/u/1/d/e/2PACX-1vRt3rCBcBjw2aYzvao5-FeXAx1ldeilFjNOLuC6dY-Qf1SoPQN6-euh-VaNs7SKJ8AYtAEyZuuMRKjc/pub"> Project report here</a>

## <a href="https://www.youtube.com/watch?v=0V2HgS6pJJI"> Project Video here</a>

The notebooks need to be run in sequence (only after the folder structure is created as per details present in the folder_structure.txt file and the environment is built as per the requirements.txt file):


### Module 1: Data Collection
* <a href="https://github.com/adityahpatel/Capstone/blob/main/Module1_Step1_Downloading_from_youtube.ipynb![image](https://user-images.githubusercontent.com/32350477/164957806-2d39befe-7aeb-455a-987d-0cb50a87fd8e.png)
">Module1_Step1_Downloading_from_youtube.ipynb</a> <br>
  Download tennis match videos (4 professional and 4 amateur short tennis matches under a variety of conditions like different court surface, different camera angle and different lighting)
* <a href="https://github.com/adityahpatel/Capstone/blob/main/Module1_Step2_Image_for_Annotation.ipynb![image](https://user-images.githubusercontent.com/32350477/164957864-21e682c7-8a8f-41aa-a065-16725597df09.png)
">Module1_Step2_Image_for_Annotation.ipynb</a> <br>
Extract all frames from these videos <br>

### Manual step
* We will next use the *labelimg* tool to create the tennis ball bounding box coordinate text files per image file. We will select 126 images per video for a total of 1008 images across 8 tennis videos. We will need to ensure a ratio of 1:2 for images where the tennis ball is in the front end of the court to images where the tennis ball is in the far end of the court. This will ensure sufficient sample of small tennis ball images at far end of the court for the Object Detection Model to learn from. We will also create smaller sets of 504 and 256 images by reducing the number of images proportionately to evaluate if smaller image sets perform as well as larger image set while detection objects.

### Module 2: Object (tennis ball) Detection
* <a href="https://github.com/adityahpatel/Capstone/blob/main/Module2_Step1a_Annotated_Images_proam_256_original%2Blabeled_aug.ipynb![
">Module2_Step1a_Annotated_Images_proam_256_original+labeled_aug.ipynb</a> <br>
<a href="https://github.com/adityahpatel/Capstone/blob/main/Module2_Step1b_Annotated_Images_proam_504_original%2Blabeled_aug.ipynb![image](https://user-images.githubusercontent.com/32350477/164958306-ae91f521-9930-48c7-a63b-9855da5944ad.png)
">Module2_Step1b_Annotated_Images_proam_504_original+labeled_aug.ipynb </a> <br>
<a href="https://github.com/adityahpatel/Capstone/blob/main/Module2_Step1c_Annotated_Images_proam_1008_original%2Blabeled_aug.ipynb![image](https://user-images.githubusercontent.com/32350477/164958464-6ef7e136-7580-4d13-8a72-49c721ee22f4.png)
">Module2_Step1c_Annotated_Images_proam_1008_original+labeled_aug.ipynb</a> 
    * Augment the images sets of 256, 504 and 1008 original images to 887, 1764 and 3525 original + augmented images respectively
* <a href="https://github.com/adityahpatel/Capstone/blob/main/Module2_Step2b_Custom_training_YOLOv4-tiny_proam_256_labeledaug3x.ipynb![image](https://user-images.githubusercontent.com/32350477/164958561-30fbe48f-931c-4226-8822-d4e45e189536.png)
">Module2_Step2b_Custom_training_YOLOv4-tiny_proam_256_labeledaug3x.ipynb</a> <br>
<a href="https://github.com/adityahpatel/Capstone/blob/main/Module2_Step2d_Custom_training_YOLOv4-tiny_proam_504_labeledaug3x.ipynb">Module2_Step2d_Custom_training_YOLOv4-tiny_proam_504_labeledaug3x.ipynb</a><br>
<a href="https://github.com/adityahpatel/Capstone/blob/main/Module2_Step2e_Custom_training_YOLOv4-tiny_proam_1008_labeledaug3x.ipynb">Module2_Step2e_Custom_training_YOLOv4-tiny_proam_1008_labeledaug3x.ipynb</a><br>
<a href="https://github.com/adityahpatel/Capstone/blob/main/Module2_Step2g_Custom_training_YOLOv4-tiny_proam_1008_labeledaug3x_1664res.ipynb">Module2_Step2g_Custom_training_YOLOv4-tiny_proam_1008_labeledaug3x_1664res.ipynb</a><br>



    * Train YOLOv4-tiny object detection model on all 3 original +augmented images set.
    * Increase network resolution from 416 to 1664 to be able to detect tennis ball at far end of the court as well as achieve performance of 93.9% on mAP@0.50. This is the 3,525 image set model trained on 1664 resolution and is the selected object detection model.

### Module3: Bounce Detection
* <a href="https://github.com/adityahpatel/Capstone/blob/main/Module3_Step1_Video_Frame_Object_Detection.ipynb">Module3_Step1_Video_Frame_Object_Detection.ipynb</a><br>
    * For a standard professional tennis match video execute Module 1 (Frame Extraction from video) and Object Detection to provide a set of text files containing the coordinates of the detected tennis ball across extracted frames.
* <a href="https://github.com/adityahpatel/Capstone/blob/main/Module3_Step2_Bounce_detector_preprocessing.ipynb">Module3_Step2_Bounce_detector_preprocessing.ipynb</a><br>
    * Extracts the ball coordinates from each of the thousands of text files corresponding to individual image and pushes them to a new csv file called model2_inputdata.csv
* <a href="https://github.com/adityahpatel/Capstone/blob/main/Module3_Step3_Bounce_detector_final.ipynb">Module3_Step3_Bounce_detector_final.ipynb</a><br>
    * Takes as input the model2_inputdata.csv created in the previous step and performs bounce detection. i.e. given a window of 10 frames, predicts whether a ball bounce occured in that window or not!
