# Screening-of-Common-Retinal-Diseases-with-Deep-Learning

Maryam Ghaffari






# Introduction





# Problem Statement and Mission






#  Evaluation Metrics
The model will be a multi classifier, meaning that there are four potential classes (CNV, DME, DRUSEN, and NORMAL) that can be placed. While all three conditions can affect the health of the retina, CNV and DME are generally considered more serious and require more aggressive treatment, as they can cause rapid and severe vision loss if left untreated. If the model incorrectly predicts a normal or drusen states, it means some patients at higher risk of vision loss would be untreated. Therefore, for the purposes of this work, a low false-negative rate has more value than a low false-positive rate. When a low false-negative rate has more value than a low false-positive rate, the metric evaluation of sensitivity or recall is more important than specificity or precision. Sensitivity or recall measures the proportion of actual positives that are correctly identified as such by a classification model, while specificity or precision measures the proportion of actual negatives that are correctly identified as such. A low false-negative rate means that the model is correctly identifying most of the positive cases, which is particularly important in situations where missing a positive case can have serious consequences. In contrast, a low false-positive rate is more important when the cost of false positives is high, such as in medical testing where false positives can lead to unnecessary treatments and anxiety for patients. The Recall are defined as:

$$\text{Recall}$$ | $$\frac{\text{Number of True Positives}}{\text{Number of Actual Total Positives}}$$

The model will achieve:

$$ \text{Recall} => 0.9 $$ 

# Methodology
Methodology in a data science project refers to the structured approach or process used to carry out the project from start to finish.The general research strategy in this project is to use the OSEMN pipline on the availabe dataset to structure their workflow and make it more organized and efficient The OSEMiN pipeline consists of the following five steps: Obtain, Scrub, Explore, Model, and iNterpret.
