# AJL-Project
Information about our approach to the Break Through Tech AJL Kaggle team project. 

## Team Members
- [Gloria P](https://github.com/gloriapul)

## Project Highlights
This Kaggle project is hosted by [Break Through Tech](https://www.breakthroughtech.org/) and the [Algorithmic Justice League (AJL)](https://www.ajl.org/about). The goal of the project was to create a model that could classify 21 different skin conditions across diverse skin tones! Techniques used in Break Through Tech resources related to image processing and transfer learning were part of the core of our work. Throughout this project, our team learned more about algorithm fairness and the pros and cons of building a model from scratch compared to using a pre-trained model. 

## Setup & Execution
All project code is found in this repository, attach link. All data used can be found on the AJL [Kaggle competition site](https://www.kaggle.com/competitions/bttai-ajl-2025/data). Colab and Google Drive were used to create the code and access the data. 

## Project Overview 
Break Through Tech, a year long program designed to mentor and help undergraduate students learn about machine learning and gain career readiness skills, teamed up with AJL for this Kaggle competition. AJL is an organization that aims to combines art and research to highlight the social implications and harms of artificial intelligence. It is crucial that when working with artificial intelligence, more work must continue to be done to combat potential errors and negative effects. With this in mind, the objective of this project was to navigate one of the areas in which artificial intelligence can be faulty, specifically by creating a fair model that can work on a diverse range of skin tones and skin conditions. Work like this is significant for navigating diagnostic errors, delayed treatments, and health disparities for underserved communities in the dermatology field. 

## Data Exploration 
All data was provided by Kaggle. The dataset is a subset of the FitzPatrick17k dataset, a labeled collection of about 17,000 images depicting a variety of serious (e.g., melanoma) and cosmetic (e.g., acne) dermatological conditions with a range of skin tones scored on the FitzPatrick skin tone scale (FST). More information can be found in this [video](https://www.youtube.com/watch?v=bizJpy5VQmQ) regarding the dataset. About 4500 images are in this set, representing 21 skin conditions out of the 100+ in the full FitzPatrick set.

For the data exploration, a multi-class classification approach was used. Since there are 21 possible skin conditions, it was important to have multiple classes rather than just simple classification. As an initial approach, a small convolutional neural network (CNN) model with residual connections, separable convolutions, and batch normalization was built to examine the data. Our model was trained using 12 epochs. In future iterations, a pre-trained model would instead be used to improve accuracy. 

As part of our data exploration, 2 figures are shown below.

The first visualization reveals all of the layers in our CNN model, and the settings we applied for each one. As seen, more work can continue to be done to adjust the settings if our regular CNN model were to be used. 

![First Visual](https://github.com/gloriapul/AJL-Project/blob/main/layers.png)

The second visualization reveals all of the layers in our CNN model, and the settings we applied for each one. As seen, more work can continue to be done to adjust the settings if our regular CNN model were to be used. 

## Model Development
## Results & Key Findings
## Impact Narrative
## Next Steps & Future Improvements
