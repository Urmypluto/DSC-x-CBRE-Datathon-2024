# DSC-x-CBRE-Datathon-2024
Github for DSC x CBRE Datathon 2024 @ NYU
Created by: Yui Cao, Tony Yu, Tiffany He, Cindy Gao

## Motivation
Within rapid development of E-Commerce during pandemic, timely construction of industrial warehouses is essential. 
A precise model for estimating construction time ensures efficient planning and resource allocation, vital for meeting the demands of rapidly growing online retail. 
With accurate projections, businesses can strategize their supply chain management effectively, optimizing delivery schedules and customer satisfaction. 
Additionally, timely completion of warehouses facilitates economic growth by attracting investments and fostering job creation in the region.

## Approach

For this challenge, we have developed 2 Convolutional Neural Networks (CNN) to classify and predict the construction status for buildings in indicated coordinates and addresses:

**1. Pretrained VGG16 model**
We used a pretrained VGG16 model from pytorch and finetuned the fully connected layers to generalize for our challenge specifically - classification of construction status between 1-5. VGG16 model has been proven to be one of the most efficient model for general image classification with its depth and computational efficiency.

**2. Pretrained and modified ResNet50 model with dropout layers**
For such a small dataset (with 222 images), overfitting becomes a problem. We modified a pretrained ResNet50 model and added a dropout layer to the fully connected layer in order to reduce overfitting and increase generalizability. 
For this model, we applied 5-fold cross validation method as well as data augmentation and normalization to solve the problem of small training and validation data size, with a scheduled learning rate between [0.001, 0.0005, 0.0001]. We trained 50 epochs for each learning rate across 5 folds. Then we picked the best performing fold and learning rate, which turned out to be 4th fold and learning rate = 0.001, and trained for another 100 epochs as our final model.


## Results


## Classification


## Construction completion date estimation
