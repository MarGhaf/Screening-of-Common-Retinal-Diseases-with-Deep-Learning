# Screening-of-Common-Retinal-Diseases-with-Deep-Learning

Maryam Ghaffari






# Introduction
Farabi hospital is a comprehensive center of excellence in **ophthalmology**. It is one of the most prestigious hospitals in Iran and serves a large population. It is assumed more than 500 patients visit Farabi Hospital daily. **Optical coherence tomography (OCT)** imaging is now a standard of care for guiding the diagnosis and treatment of some of the leading causes of blindness worldwide: age-related macular degeneration (AMD) and diabetic macular edema (DME). OCT was routinely done for most patients. The hospital as a stakeholder interested in implementing the diagnostic tool as part of their standard screening and treatment protocols. By using the tool to **screen patients for retinal diseases**, they could identify cases earlier and provide more effective treatment options, improving patient outcomes and reducing healthcare costs in the long run. **Deep learning algorithms** can automatically screen OCT images to detect abnormalities and flag them for further examination by a trained ophthalmologist. The use of deep learning in OCT image classification for detecting retina diseases has evolved rapidly over the past decade, with increasingly accurate algorithms being developed and tested in clinical settings.

# Problem Statement and Mission
Accurate detection between OCT images of **retinal diseases** can significantly benefit patients by enabling **early detection, personalized treatment, improved monitoring, and reduced healthcare costs**. It can also help ophthalmologists make more informed decisions regarding patient care, leading to better patient outcomes. Choroidal Neovascularization (CNV), Diabetic Macular Edema (DME), and Drusen are more common conditions that can affect the health of the retina, but they differ in severity and treatment options. While all three conditions can affect the health of the retina, **CNV and DME** are generally considered more serious and require more aggressive treatment, as they can cause rapid and severe vision loss if left untreated. Drusen, while generally harmless, can increase the risk of developing age-related macular degeneration, which can cause vision loss over time. Implementing clinical decision support algorithms for medical images faces challenges in terms of accuracy and interpretability. This project attempted to develop a diagnostic tool based on a deep learning framework for screening patients for commonly treatable and blinding retinal diseases. 
This project attempted to develop an effective learning algorithm to process medical images and diagnose the major pathologies in each image accurately. By applying this approach to a dataset of OCT images, I tried to enhance accuracy in classifying CNV and DME.

This proposal has two **primary objectives**:

- Generate a **Convolutional Neural Network (CNN)** which distinguish between the different condition in OCT images with high accuracy.
- Reveal potential indicators in the OCT images in different diagnoses by **highlighting regions recognized by the CNN**. 



#  Evaluation Metrics
The model will be a **multi-classification**, meaning that there are four potential classes (CNV, DME, DRUSEN, and NORMAL) that can be placed. While all three conditions can affect the health of the retina, CNV and DME are generally considered more serious and require more aggressive treatment, as they can cause rapid and severe vision loss if left untreated. If the model incorrectly predicts normal or drusen states, it means some patients at higher risk of vision loss would be untreated. Therefore, for the purposes of this work, a **low false-negative** rate has more value than a low false-positive rate. When a low false-negative rate has more value than a low false-positive rate, the metric evaluation of **sensitivity or recall** is more important than specificity or precision. Sensitivity or recall measures the proportion of actual positives that are correctly identified as such by a classification model, while specificity or precision measures the proportion of actual negatives that are correctly identified as such. A low false-negative rate means that the model is **identifying most of the positive cases** correctly, which is particularly important in situations where missing a positive case can have serious consequences. In contrast, a low false-positive rate is more important when the cost of false positives is high, such as in medical testing where false positives can lead to unnecessary treatments and anxiety for patients. The Recall is defined as:

$$ \text{Recall} = \frac{\text{Number of True Positives}}{\text{Number of Actual Total Positives}} $$ 

The model will achieve:

$$ \text{Recall} => 0.9 $$ 

# Methodology
Methodology in a data science project refers to the structured approach or process used to carry out the project from start to finish.The general research strategy in this project is to use the OSEMiN pipline on the availabe dataset to structure their workflow and make it more organized and efficient The OSEMiN pipeline consists of the following five steps: **Obtain, Scrub, Explore, Model, and iNterpret**.

## Obtain
The data that will be used for the model has been graciously prepared by the University of California San Diego, Guangzhou Women and Children's Medical Center This dataset contains thousands of validated OCT and Chest X-Ray images described and analyzed in "Identifying Medical Diagnoses and Treatable Diseases by Image-Based Deep Learning". The images are split into a training set and a testing set of independent patients. Images are labeled as (disease)-(randomized patient ID)-(image number by this patient) and split into 4 directories: **CNV, DME, DRUSEN, and NORMAL**. I will use the processed CT images hosted by Casper for the neural networks. In order to access these data I download it directly to the local hardware and create a path to the images.


## Scrub and Explore
The data itself was biased with 98.9% of the images being of normal and , and so the normal dataset was shortened to the 8000 random selection of each group. 

![image](https://user-images.githubusercontent.com/101681195/222004361-80531e34-8710-45b7-87cd-c5bcb78ff68f.png)


## Model
After modeling with basline CNN the model showed high biased and it needed to be regulrized. The most promising model was the model that includes 4 blocks of convolutional layers, each followed by a max pooling layer to downsample the feature maps. The model then flattens the output of the last max pooling layer and passes it through two fully connected layers, each consisting of 512 neurons, with ReLU activation functions and a 0.3 dropout rate to reduce overfitting. Finally, the model outputs a probability distribution over the 4 classes using a dense layer with a sigmoid activation function. The the Netron visualization of the CNN model was illustrated in below image. 


![image](https://user-images.githubusercontent.com/101681195/224182839-ceb3f0b6-4b3b-4407-a26b-7b3561b70885.png)


## Performance
Through the confusion matrix results on the test dataset, it was reveled that the model showed a low false-negative rate in the **CNV and DME**. It menas the model is **identifying most of the positive cases** correctly, which is particularly important in situations where missing a positive case can have serious consequences. In This situation the metric evaluation of **sensitivity or recall** is more important than specificity or precision. This model could fulfill the objective of this prosoal which was **recall > 0.9**. 

![image](https://user-images.githubusercontent.com/101681195/224195011-98ffba25-dd68-4c03-9aae-fb7a2ace687f.png)


## Feature Visulization
Visualizing feature maps in a CNN can help us understand how the network is processing the input image at different layers. Feature maps are the output of a convolutional layer and they represent the activation of certain filters in response to the input image. By visualizing the feature maps, we can see what the network is focusing on in the image, and how the feature representation changes as we move deeper into the network. By Comparing the features maps in 4 groups we can gain insights into what the model has learned. For example, we can see the model is detecting edges, shapes and how it combines these features to make predictions.

![image](https://user-images.githubusercontent.com/101681195/224390795-749ed7b3-df2f-41f9-a15c-e724371cce0c.png)


# Conclusion
In conclusion, this project aimed to develop a deep learning-based diagnostic tool using a convolutional neural network to accurately classify optical coherence tomography (OCT) images of retinal diseases. The use of deep learning algorithms in medical image classification has evolved rapidly over the past decade, and this project demonstrates that the application of such algorithms can significantly benefit patients by enabling early detection, personalized treatment, improved monitoring, and reduced healthcare costs.

The developed CNN model was trained and tested on a dataset of OCT images to distinguish between four potential classes (CNV, DME, DRUSEN, and NORMAL) with a high accuracy rate of 0.89. However, the main focus of the project was to achieve a high recall rate for the more serious conditions, CNV and DME, with a goal of above 0.9. The model achieved a recall of 0.94 and 0.96 for CNV and DME, respectively, indicating a low false-negative rate and a high level of sensitivity in identifying positive cases.

Therefore, the results of this project suggest that implementing deep learning-based diagnostic tools for screening and diagnosis of retinal diseases can significantly improve patient outcomes and reduce healthcare costs by enabling early detection and personalized treatment. However, further research is needed to address challenges in accuracy and interpretability of such algorithms and to ensure their ethical use in clinical settings.

 ## Repository Structure
```

├── Code : final_student.ipynb includ modeling
├── Data : Data used for modeling, includes train and test image files
├── Images : Images used in Phase 4 Project Presentation.pdf and README
├── Phase 4 Project Presentation.pdf : Presentation for stakeholders
└── README.md : Project information and repository structure
