# Capstone
# Benchmarking Facial Beauty Predictors
By Aditya Patel and Chris Westendorf

## <a href="https://github.com/adityahpatel/milestone2_dating_and_beauty/blob/main/25-cwestend-adityahp%20Benchmarking%20Facial%20Beauty%20Predictors.pdf">Read the PDF report here</a>

We set out to explore and benchmark the visual recognition problem of Facial Beauty Prediction (FBP), assessing facial attractiveness that is consistent with human perception. Such a FPB model can be used by online dating companies as a dating profile recommender.

To tackle this problem, various computational models with different FBP paradigms were explored. We considered this problem a semantic topology problem so we focused our efforts on comparing the feature generation and modeling process of machine learning pipelines with various convolutional neural network (CNN) approaches. Specifically, we analogously engineered our machine learning pipelines to perform feature engineering similar to that of a CNN— extracting structure and topics from the topology of a headshot image. This allowed us to interpret the impact and efficiency of CNN layers as they relate to convolutions, pooling, weighting, and decision functions. And our goal was to build a model that beat the Root Mean Squared Error achieved by state-of-the-art CNNs such as AlexNet, ResNet-18 and ResNeXt-50 on the held-out test set.

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
