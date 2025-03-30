# AJL-Project
Information about our approach to the Break Through Tech AJL Kaggle team project. 

## Team Members
- [Ashley Lopez](https://github.com/ashleylopezm)
- [Gloria P](https://github.com/gloriapul)
- [Glenvelis Perez](https://github.com/gperez42)
- [Claire Lee](https://github.com/claireslee)

## Project Highlights
This Kaggle project is hosted by [Break Through Tech](https://www.breakthroughtech.org/) and the [Algorithmic Justice League (AJL)](https://www.ajl.org/about). The goal of the project was to create a model that could classify 21 different skin conditions across diverse skin tones! Techniques used in Break Through Tech resources related to image processing and transfer learning were part of the core of our work. Throughout this project, our team learned more about algorithm fairness and the pros and cons of building a model from scratch compared to using a pre-trained model. 

## Setup & Execution
All project code is found in this repository, specifically in our [AJLteam3.ipynb file](https://github.com/gloriapul/AJL-Project/blob/main/AJLTeam3.ipynb). All data used can be found on the AJL [Kaggle competition site](https://www.kaggle.com/competitions/bttai-ajl-2025/data). Colab and Google Drive were used to create the code and access the data. 

## Project Overview 
Break Through Tech, a year long program designed to mentor and help undergraduate students learn about machine learning and gain career readiness skills, teamed up with AJL for this Kaggle competition. AJL is an organization that aims to combines art and research to highlight the social implications and harms of artificial intelligence. It is crucial that when working with artificial intelligence, more work must continue to be done to combat potential errors and negative effects. 

With this in mind, the objective of this project was to navigate one of the areas in which artificial intelligence can be faulty, specifically by creating a fair model that can work on a diverse range of skin tones and skin conditions. Work like this is significant for navigating diagnostic errors, delayed treatments, and health disparities for underserved communities in the dermatology field. 

## Data Exploration 
All data was provided by Kaggle. The dataset is a subset of the FitzPatrick17k dataset, a labeled collection of about 17,000 images depicting a variety of serious (e.g., melanoma) and cosmetic (e.g., acne) dermatological conditions with a range of skin tones scored on the FitzPatrick skin tone scale (FST). More information can be found in this [video](https://www.youtube.com/watch?v=bizJpy5VQmQ) regarding the dataset. About 4500 images are in this set, representing 21 skin conditions out of the 100+ in the full FitzPatrick set.

For our approach, a multi-class classification approach was used. Since there are 21 possible skin conditions, it was important to have multiple classes rather than just simple classification. A small convolutional neural network (CNN) model with residual connections, separable convolutions, and batch normalization was built to examine the data. Our model was trained using 12 epochs. This very first model was not high in accuracy which is why, in future iterations, a pre-trained model would instead be used to improve accuracy. Creating our plan for this initial model was helpful though with understanding the data we needed and our exploration of it. We explored the images through techniques such as data augmentation and creating a chart showing the data's distribution. Having our initial model was also helpful for running predictions on one image at a time.  

As part of this process, 2 figures are shown below.

The most important step when starting out was being able to understand the data and its distribution. So, this first visual displays the spread of the data and the 21 diseases we were working with.
![Second Visual](https://github.com/gloriapul/AJL-Project/blob/main/value_counts.png)

The second visualization reveals all of the layers in our CNN model, and the settings we applied for each one. As seen, more work can continue to be done to adjust the settings if our regular CNN model were to be used. 

![Second Visual](https://github.com/gloriapul/AJL-Project/blob/main/layers.png)

## Model Development
We used a custom CNN model built using TensorFlow and Keras for the WiDS 2025 Brain Activity/ADHD classification challenge. The architecture drew inspiration from Xception-style networks, incorporating:
* SeparableConv2D layers to reduce parameters and computational cost
* BatchNormalization, Dropout, and GlobalAveragePooling for regularization and generalization
* Residual connections for deeper, stable learning

It was also important to feature engineer and tune our hyperparameters. Data preprocessing included normalization (Rescaling) and resizing images to 180x180. We also used data augmentation strategies such as horizontal flipping and rotation to help prevent overfitting. Our hyperparameters were also manually tuned, with a batch size: 32 (optimized for Colab's memory), epochs: 12, and learning rate: 3e^-4 (using the Adam optimizer). A ModelCheckpoint callback also saved model weights per epoch. For training setup, the dataset was split using image_dataset_from_directory with a 80/20 train-validation split. Evaluation metric during training was binary accuracy, and Binary Crossentropy was used as the loss function (with logits).

## Results & Key Findings
Regarding our overall performance, our initial custom CNN model achieved limited accuracy on validation data, which we expected given its lightweight architecture and limited training epochs. It was valuable as a baseline to explore the dataset and begin testing predictions. The model training was done over 12 epochs, and we applied data augmentation (ex: flipping, rotation) to improve generalization. 

For fairness across skin tones,fFairness was a core motivation, as the project centered around equitable dermatological diagnosis across Fitzpatrick skin tones. However, explicit subgroup performance metrics (ex: per-tone accuracy, confusion matrices by tone) were not implemented in this initial version. 

## Impact Narrative
This project was created because fairness in skin condition classification **matter**. Skin condition detection AI models have historically shown bias against darker skin tones, leading to misdiagnoses, delayed treatment, and widening health disparities. Our work contributes to addressing these gaps by building and evaluating models using a diverse dataset (Fitzpatrick17k), helping ensure that dermatological tools serve all skin tones equitably.

Our project could support early detection of dermatological issues across all skin tones, awareness in the ML community of the risks of biased training data, or even development of more inclusive medical AI tools. Our initial model is a first step. With future improvements like pre-trained architectures and fairness audits, this work could help pave the way for clinically relevant and ethically responsible diagnostic AI in dermatology.

## Next Steps & Future Improvements
Our initial model was a relatively simple convolutional neural network (CNN) trained from scratch. While it helped us understand the dataset and build a foundation, it has a few key limitations:
* **Limited accuracy** due to model complexity, data size, and short training duration (12 epochs).
* **Resource constraints** (RAM, training time) prevented us from experimenting with larger architectures or more extensive hyperparameter tuning.

Next time, we would explore supplementing the dataset with additional diverse dermatology datasets that include metadata for skin tone, age, or lighting conditions.

Ultimately, we aim to create a model that not only performs well but also treats all skin tones equitably, helping close diagnostic gaps in dermatological care.
