# Capstone
# AI Ball Bounce Detector
By Aditya Patel and Sharadwata Ganguli

## <a href="https://github.com/adityahpatel/milestone2_dating_and_beauty/blob/main/25-cwestend-adityahp%20Benchmarking%20Facial%20Beauty%20Predictors.pdf">Read the PDF report here</a>

We set out to explore and benchmark the visual recognition problem of Facial Beauty Prediction (FBP), assessing facial attractiveness that is consistent with human perception. Such a FPB model can be used by online dating companies as a dating profile recommender.

The notebooks need to be run in sequence (only after the folder structure is created as per details present in the folder_structure.txt file and the environment is built as per the requirements.txt file):
•	Module1
o	Module1_Step1_Downloading_from_youtube.ipynb
	Download tennis match videos (4 professional and 4 amateur short tennis matches under a variety of conditions like different court surface, different camera angle and different lighting)
o	Module1_Step2_Image_for_Annotation.ipynb 
	Extract all frames from these videos
•	Manual step:
o	We will next use the labelimg tool to create the tennis ball bounding box coordinate text files per image file. We will select 126 images per video for a total of 1008 images across 8 tennis videos. We will need to ensure a ratio of 1:2 for images where the tennis ball is in the front end of the court to images where the tennis ball is in the far end of the court. This will ensure sufficient sample of small tennis ball images at far end of the court for the Object Detection Model to learn from. We will also create smaller sets of 504 and 256 images by reducing the number of images proportionately to evaluate if smaller image sets perform as well as larger image set while detection objects.
•	Module 2: Object Detection
o	Module2_Step1a_Annotated_Images_proam_256_original+labeled_aug.ipynb, Module2_Step1b_Annotated_Images_proam_504_original+labeled_aug.ipynb, Module2_Step1c_Annotated_Images_proam_1008_original+labeled_aug.ipynb
	Augment the images sets of 256, 504 and 1008 original images to 887, 1764 and 3525 original + augmented images respectively
o	Module2_Step2b_Custom_training_YOLOv4-tiny_proam_256_labeledaug3x.ipynb,
Module2_Step2d_Custom_training_YOLOv4-tiny_proam_504_labeledaug3x.ipynb,
Module2_Step2e_Custom_training_YOLOv4-tiny_proam_1008_labeledaug3x.ipynb,
Module2_Step2g_Custom_training_YOLOv4-tiny_proam_1008_labeledaug3x_1664res.ipynb
	Train YOLOv4-tiny object detection model on all 3 original +augmented images set.
	Increase network resolution from 416 to 1664 to be able to detect tennis ball at far end of the court as well as achieve performance of 93.9% on mAP@0.50. This is the 3,525 image set model trained on 1664 resolution and is the selected object detection model.
•	Modeule3: Bounce Detection
o	Module3_Step1_Video_Frame_Object_Detection.ipynb
	For a standard professional tennis match video execute Module 1 (Frame Extraction from video) and Object Detection to provide a set of text files containing the coordinates of the detected tennis ball across extracted frames.
![image](https://user-images.githubusercontent.com/32350477/164947612-884cce7f-347d-418b-b962-a7b8c064ddb3.png)




Dataset: <a href="https://github.com/HCIILAB/SCUT-FBP5500-Database-Release">SCUT-FBP5500: A Diverse Benchmark Dataset for Multi-Paradigm Facial Beauty Prediction</a>


## Notebooks: Machine Learning Pipeline

* <a href="https://github.com/adityahpatel/milestone2_dating_and_beauty/blob/main/00_EDA%2BFeature_Engineering_ML_pipeline.ipynb">00_EDA+Feature_Engineering_ML_pipeline</a>
* <a href="https://github.com/adityahpatel/milestone2_dating_and_beauty/blob/main/01_Unsupervised_PCA_ML_pipeline.ipynb">01_Unsupervised_PCA_ML_pipeline</a>
* <a href="https://github.com/adityahpatel/milestone2_dating_and_beauty/blob/main/02_Unsupervised_BOVF_ML_pipeline.ipynb">02_Unsupervised_BOVF_ML_pipeline</a>
* <a href="https://github.com/adityahpatel/milestone2_dating_and_beauty/blob/main/03_Supervised_Classification_ML_pipeline.ipynb">03_Supervised_Classification_ML_pipeline</a>
* <a href="https://github.com/adityahpatel/milestone2_dating_and_beauty/blob/main/04_Failure_Analysis_BOVW_clustering.ipynb">04_Failure_Analysis_BOVW_clustering</a>

## Notebooks: Convolutional Neural Network
* <a href="https://github.com/adityahpatel/milestone2_dating_and_beauty/blob/main/CNN/cnn_v3.ipynb">CNN_v3</a>
* <a href="https://github.com/adityahpatel/milestone2_dating_and_beauty/blob/main/CNN/cnn4_colab.ipynb">CNN4_colab</a>
* <a href="https://github.com/adityahpatel/milestone2_dating_and_beauty/blob/main/CNN/VGGFeatureExtractor.ipynb">VGGFeatureExtractor</a>
