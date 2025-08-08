## About this project/journal/Github:

This GitHub is a source code for the creation or development of a CNN model that classifies multi-class eye diseases using fundus images as the imaging technique. There are a total of 4 classes in this classification model, namely Cataract, Diabetic Retinopathy, Glaucoma, and Normal. In this proposed research/project (TA_CNN_modelConvNeXtTiny.ipynb, TA_CNN_modelEfficientNetV2B3.ipynb, TA_CNN_modelEfficientNetV2S.ipynb), hyperparameter tuning was performed using the Keras Tuner with the Bayesian Optimization algorithm, Transfer Learning, and Fine-tuning. This research was conducted using the Google Colab Pro platform with a T4 GPU runtime type and high memory (High-RAM), which was used to support the model training process that requires significant computational resources.  

The following is a detailed explanation of the files on GitHub:
1. Q2_Diabetic_Retinopathy.ipynb file is the retraining code for the model from the research by Yasashvini et al., 2022, titled “Diabetic Retinopathy Classification Using CNN and Hybrid Deep Convolutional Neural Networks.”
2. The Q3_A_deep_neural_network.ipynb file contains the retraining code for the model from Thanki's 2023 study titled “A deep neural network and machine learning approach for retinal fundus image classification.”
3. The S3_Glaucoma.ipynb file is the retraining code for the model from the research by Fuadah et al., 2022, titled “GLAUCOMA CLASSIFICATION BASED ON FUNDUS IMAGES PROCESSING WITH CONVOLUTIONAL NEURAL NETWORK.”
4. The TA_CNN_modelConvNeXtTiny.ipynb file is the training code proposed in my research with ConvNeXtTiny as the base model architecture.
5. TA_CNN_modelEfficientNetV2B3.ipynb file is the training code proposed in my research with EfficientNetV2B3 as the base model architecture.
6. TA_CNN_modelEfficientNetV2S.ipynb file is the training code proposed in my research with EfficientNetV2S as the base model architecture.

### Important Points to Note

However, there are several points that need to be noted and emphasized when retraining the three journals, due to the lack of reproducibility in the previous research journals. For Thanki's (2023) journal, several points need to be noted, namely:

1. In this study, CNN was used for feature extraction, and the results were used for classification with machine learning algorithms. The pre-trained CNN model used is SqueezeNet. However, it is not specified whether it is SqueezeNet 1.0 or SqueezeNet 1.1. Therefore, in this retraining, the latest version, SqueezeNet 1.1, is used because the study was conducted in 2022, and at that time, SqueezeNet 1.1 was more widely used as it was the latest and improved version compared to its predecessors.
2. Neither the pre-trained SqueezeNet 1.0 nor SqueezeNet 1.1 models are available in the Tensorflow Keras Application. Therefore, in the retraining of the research, ONNX Runtime was used with the pre-trained SqueezeNet 1.1 model, which was exported from Pytorch to be used in Tensorflow, followed by feature extraction. The results of the feature extraction were used for classification with machine learning algorithms.

Meanwhile, for the journal by Fuadah et al. (2022), several things need to be noted, namely:

1. Since the activation function between convolutional layers is not explicitly mentioned in the study, the ReLU activation function was used in this replication, as is common practice in CNNs for image data.
2. The research journal states that three convolutional layers with output channels of 16, 32, and 64 and a filter size of 5x5 were used in each layer. However, the abstract and model architecture diagram indicate that the study used three convolutional layers with output channels of 8, 16, and 32 and a filter size of 5x5 in each layer. Therefore, in retraining the research model, three convolutional layers with output channels of 8, 16, and 32 and a filter size of 5x5 in each layer were used.
3. The journal states that a filter value of 5x5 should be used for the Pooling layer, but this value is invalid and causes problems when executed, so a filter value of 2x2 was used, which is a commonly used value in CNN model creation.

Finally, for the journal by Yasashvini et al. (2022), there are several things to note, namely:

1. The study conducted three proposed methods, and the journal states that the Hybrid CNN model combined with DenseNet121 using Transfer Learning achieved better model evaluation results than the other two proposed methods. Therefore, in this comparison, retraining was performed using the Hybrid CNN architecture combined with DenseNet121.
2. Not all preprocessing techniques were implemented during retraining, such as Wiener filter, image smoothing, blending, and masking, due to limitations in direct support from the TensorFlow API without using external libraries like Albumentations or OpenCV. However, data augmentation was still performed, such as random flipping with horizontal and vertical values, and preprocessing using preprocess_input().
3. Since the batch size was not specified in the original study, a batch size of 32 was used, which is a common and stable configuration for training CNN models such as DenseNet121.

## Dataset Information:

The dataset used to create the model during this study was obtained from Kaggle under the title “eye_diseases_classification,” which was uploaded by Guna Venkat Doddi in 2022. The dataset contains a total of 4,217 fundus eye images, categorized into 4 classes: Cataract (1,038 images), Diabetic Retinopathy (1,098), Glaucoma (1,007), and Normal (1,074).

**Dataset Link:** *https://www.kaggle.com/datasets/gunavenkatdoddi/eye-diseases-classification*

## Website Demo Model:

After the CNN model training and development process was completed, the best results from each model architecture (ConvNeXtTiny, EfficientNetV2B3, and EfficientNetV2S) that had been evaluated were then implemented into a web-based application using the Streamlit library. The deployment process was carried out through the Streamlit Community Cloud platform, which allows the application to be run and accessed online. 

**Here is the link to the model demo website:** *https://ta-demo-model-rizkiikhwan.streamlit.app/*

## References:
1. Fuadah, Y. N., Saidah, S., Sy, N. K., Magdalena, R., & Da’wan Ubaidullah, I. (2022). GLAUCOMA CLASSIFICATION BASED ON FUNDUS IMAGES PROCESSING WITH CONVOLUTIONAL NEURAL NETWORK. Jurnal Teknik Informatika (JUTIF), 3(3). https://doi.org/10.20884/1.jutif.2022.3.3.276
2. Thanki, R. (2023). A deep neural network and machine learning approach for retinal fundus image classification. Healthcare Analytics, 3. https://doi.org/10.1016/j.health.2023.100140
3. Yasashvini, R., Raja Sarobin M, V., Panjanathan, R., Graceline Jasmine, S., & Jani Anbarasi, L. (2022). Diabetic Retinopathy Classification Using CNN and Hybrid Deep Convolutional Neural Networks. Symmetry, 14(9). https://doi.org/10.3390/sym14091932
