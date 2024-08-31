# U-Net-Based-OBIA-
## Urban Functional Zones in Würzburg

### Project Overview
This project focuses on the semantic segmentation of urban areas using high-resolution aerial raster images and urban atlas mask data for the city of Würzburg. The aerial images, sourced from Bayern Atlas, offer a detailed 0.4 cm resolution, providing a rich dataset for analysis. The urban atlas masks serve as ground truth, categorizing the city into different zones including continuous urban fabric, discontinuous urban fabric, commercial and industrial areas, transport zones, urban green spaces, and non-urban areas. The primary objective is to classify these zones accurately using deep learning models.

### Data and Methodology
The project leverages two main datasets: high-resolution aerial images and urban atlas masks. Prior to training, the datasets were preprocessed by resizing and extracting image patches. A colormap was applied to the grayscale masks to visualize different urban zones, and the masks were converted to a categorical format suitable for model training. The data was split into 80% training and 20% testing sets.

Two U-Net models were implemented: a custom model and a ResNet34-based model, both following an encoder-decoder architecture with skip connections. The models were trained using the Adam optimizer and categorical cross-entropy loss, with IoU and F1 score metrics for evaluation. Early stopping was employed to mitigate overfitting, with the best model weights restored based on validation loss. 
Note: Third column (prediction on test image) of the image is the result of CustomUnet and fourth column is the result of Unet-Resnet34
![alt text](https://github.com/gokceyagmurbudak/U-Net-Based-OBIA-/blob/main/img/result1.png)

### Results and Challenges
The models demonstrated promising segmentation performance, effectively identifying various urban land use classes. However, several challenges were encountered, including compatibility issues between mask data and image objects, insufficient data volume, and suboptimal performance in non-urban areas. The IoU metric did not exceed 0.5, and overfitting was a notable issue. These challenges highlight areas for future improvement, such as refining the dataset and exploring alternative segmentation approaches.
