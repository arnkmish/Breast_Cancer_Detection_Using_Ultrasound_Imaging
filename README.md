# Breast Cancer Detection Using Ultrasound Imaging
This repository contains iPython notebook files that address the problem of breast cancer detection on ultrasound images. 

The problem of breast cancer detection is approached from several different ways- 

1. Benign vs. Malignant BUS Tumor classification (With and Without G.T Tumor mask)
2. Semantic Segmentation of Breast Tumor in BUS images
3. Multitask learning based segmentation and classification of BUS tumors. 

The code and the results present in this repository can serve as a baseline for innovative research works in this area.

For the purpose of experimentation, the publicly available BUSI dataset has been utilized, which can be access at: https://scholar.cu.edu.eg/?q=afahmy/pages/dataset

## Classification Results Without Tumor Mask Information

|Model      |Accuracy|Sensitivity|Specificity|Precision|Recall|F1 Score|AUC   |
|-----------|--------|-----------|-----------|---------|------|--------|------|
|ResNet50   |0.7594  |0.8352     |0.5952     |0.8172   |0.8352|0.826   |0.85  |
|InceptionV3|0.8270  |0.9120     |0.6428     |0.8469   |0.9120|0.8783  |0.8492|
|DenseNet121|0.7518  |0.7692     |0.7142     |0.8536   |0.7692|0.8092  |0.8330|
|Ensemble   |0.8496  |0.9120     |0.7142     |0.8736   |0.9120|0.8924  |0.8785|
