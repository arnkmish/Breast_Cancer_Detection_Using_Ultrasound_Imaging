# Breast Cancer Detection Using Ultrasound Imaging
This repository contains iPython notebook files that address the problem of breast cancer detection on ultrasound images. 

The problem of breast cancer detection is approached from several different ways- 

1. Benign vs. Malignant BUS Tumor classification (With and Without G.T Tumor mask)
2. Semantic Segmentation of Breast Tumor in BUS images
3. Automatic tumor mask enhanced  classification of BUS images.

The code and the results present in this repository can serve as a baseline for innovative research works in this area.

For the purpose of experimentation, the publicly available BUSI dataset has been utilized, which can be access at: https://scholar.cu.edu.eg/?q=afahmy/pages/dataset

## Classification Results Without Tumor Mask Information

|Model      |Accuracy  |Sensitivity|Specificity|Precision |Recall    |F1 Score  |AUC       |
|-----------|----------|-----------|-----------|----------|----------|----------|----------|
|ResNet50   |0.7594    |0.8352     |0.5952     |0.8172    |0.8352    |0.826     |0.85      |
|InceptionV3|0.8270    |**0.9120** |0.6428     |0.8469    |**0.9120**|0.8783    |0.8492    |
|DenseNet121|0.7518    |0.7692     |**0.7142** |0.8536    |0.7692    |0.8092    |0.8330    |
|Ensemble   |**0.8496**|**0.9120** |**0.7142** |**0.8736**|**0.9120**|**0.8924**|**0.8785**|


## Classification Results With Tumor Mask Alpha-Blended With Input

|Model      |Accuracy  |Sensitivity|Specificity|Precision |Recall    |F1 Score  |AUC       |
|-----------|----------|-----------|-----------|----------|----------|----------|----------|
|ResNet50   |0.9022    |0.8791     |**0.9523** |**0.9756**|0.8791    |0.9248    |**0.9850**|
|InceptionV3|0.9323    |**0.9560** |0.8809     |0.9456    |**0.9560**|0.9508    |0.9612    |
|DenseNet121|0.9323    |0.9340     |0.9285     |0.9659    |0.9340    |0.9497    |0.9774    |
|Ensemble   |**0.9473**|**0.9560** |0.9285     |0.9666    |**0.9560**|**0.9613**|0.9837    |

## Semantic Segmentation Results Using UNet based Model

A UNet based semantic segmentation of BUS tumors have shown decent results with **~70% average Dice Score** on BUSI and UDIAT combined test set. The next task to explore is to see whether UNet based predictions blended with the original BUS images can actually help with the Benign vs. Malignant tumor classification or not. Because if it does improve the classification performance compared to the results obtained without using G.T masks, and is near to the performance obtained with G.T. masks, then it would mean that completely automated and effective predictive modeling can be performed for the end goal of efficient breast cancer prediction.

## UNet Predicted Mask Enhanced BUS Tumor Classification Results

|Model      |Accuracy  |Sensitivity|Specificity|Precision |Recall    |F1 Score  |AUC       |
|-----------|----------|-----------|-----------|----------|----------|----------|----------|
|ResNet50   |0.6240    |0.7252     |0.4047     |0.7252    |0.7252    |0.7252    |0.6182    |
|InceptionV3|0.6691    |0.5714     |**0.8809** |**0.9122**|0.5714    |0.7027    |**0.8413**|
|DenseNet121|0.7819    |0.9230     |0.4761     |0.7924    |0.9230    |0.8527    |0.7732    |
|Ensemble   |**0.8045**|**0.9340** |0.5238     |0.8095    |**0.9340**|**0.8673**|0.8354    |

From the UNet Mask Enhanced BUS Tumor Image Classification results we can observe that predicted mask based enhancement doesn't help with improving the classification performance. This is primarily due to the fact that the error from the segmentation phase propagates to the classification phase and the model performance decreases.
