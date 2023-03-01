# Screening-of-Common-Retinal-Diseases-with-Deep-Learning

Maryam Ghaffari






# Introduction
Optical coherence tomography (OCT) imaging is now a standard of care for guiding the diagnosis and treatment of some of the leading causes of blindness worldwide: age-related macular degeneration (AMD) and diabetic macular edema (DME). Deep learning algorithms can automatically screen OCT images to detect abnormalities and flag them for further examination by a trained ophthalmologist. The use of deep learning in OCT image classification for detecting retina diseases has evolved rapidly over the past decade, with increasingly accurate algorithms being developed and tested in clinical settings.

# Problem Statement and Mission
Accurate detection between OCT images of **retinal diseases** can significantly benefit patients by enabling early detection, personalized treatment, improved monitoring, and reduced healthcare costs. It can also help ophthalmologists make more informed decisions regarding patient care, leading to better patient outcomes. Choroidal Neovascularization (CNV), Diabetic Macular Edema (DME), and Drusen, are more common conditions that can affect the health of the retina, but they differ in severity and treatment options.While all three conditions can affect the health of the retina, CNV and DME are generally considered more serious and require more aggressive treatment, as they can cause rapid and severe vision loss if left untreated. Drusen, while generally harmless, can increase the risk of developing age-related macular degeneration, which can cause vision loss over time. Implementing clinical decision support algorithms for medical images faces challenges in terms of accuracy and interpretability. This project attempted to develop a diagnostic tool based on a deep learning framework for screening patients for commonly treatable and blinding retinal diseases. 
This project attempted to develop an effective learning algorithm to process medical images and diagnose the major pathologies in each image accurately. By applying this approach to a dataset of OCT images, I tried to enhance accuracy in classifying CNV and DME.

There are two main **objectives** the proposal, which are as follows:

- Generate a **Convolutional Neural Network (CNN)** which distinguish between different condition in OCT images with a high accuracy.
- Reveal potential indicators in the OCT images in different diagnosis by **highlighting regions recognized by the CNN**. 





#  Evaluation Metrics
The model will be a **multi-classification**, meaning that there are four potential classes (CNV, DME, DRUSEN, and NORMAL) that can be placed. While all three conditions can affect the health of the retina, CNV and DME are generally considered more serious and require more aggressive treatment, as they can cause rapid and severe vision loss if left untreated. If the model incorrectly predicts a normal or drusen states, it means some patients at higher risk of vision loss would be untreated. Therefore, for the purposes of this work, a **low false-negative** rate has more value than a low false-positive rate. When a low false-negative rate has more value than a low false-positive rate, the metric evaluation of **sensitivity or recall** is more important than specificity or precision. Sensitivity or recall measures the proportion of actual positives that are correctly identified as such by a classification model, while specificity or precision measures the proportion of actual negatives that are correctly identified as such. A low false-negative rate means that the model is correctly **identifying most of the positive cases**, which is particularly important in situations where missing a positive case can have serious consequences. In contrast, a low false-positive rate is more important when the cost of false positives is high, such as in medical testing where false positives can lead to unnecessary treatments and anxiety for patients. The Recall are defined as:

$$ \text{Recall} = \frac{\text{Number of True Positives}}{\text{Number of Actual Total Positives}} $$ 

The model will achieve:

$$ \text{Recall} => 0.9 $$ 

# Methodology
Methodology in a data science project refers to the structured approach or process used to carry out the project from start to finish.The general research strategy in this project is to use the OSEMN pipline on the availabe dataset to structure their workflow and make it more organized and efficient The OSEMiN pipeline consists of the following five steps: **Obtain, Scrub, Explore, Model, and iNterpret**.

## Obtain
The data that will be used for the model has been graciously prepared by University of California San Diego, Guangzhou Women and Children's Medical Center This dataset contains thousands of validated OCT and Chest X-Ray images described and analyzed in "Identifying Medical Diagnoses and Treatable Diseases by Image-Based Deep Learning". The images are split into a training set and a testing set of independent patients. Images are labeled as (disease)-(randomized patient ID)-(image number by this patient) and split into 4 directories: **CNV, DME, DRUSEN, and NORMAL**. I will use the processed CT images hosted by Casper for the neural networks. In order to access these data I download it directly to the local hardware, and create a path to the images.


## Scrub and Explore
The data itself was biased with 98.9% of the images being of normal and , and so the normal dataset was shortened to the 8000 random selection of each group. 

![image](https://user-images.githubusercontent.com/101681195/222004361-80531e34-8710-45b7-87cd-c5bcb78ff68f.png)




## Model














 ## Repository Structure
```

├── Code : final_student.ipynb includ modeling
├── Data : Data used for modeling, includes train and test image files
├── Images : Images used in Phase 4 Project Presentation.pdf and README
├── Phase 4 Project Presentation.pdf : Presentation for stakeholders
└── README.md : Project information and repository structure
