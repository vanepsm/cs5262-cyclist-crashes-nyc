# Investigating Cyclist Accidents in New York City: A Summary
**Aaron Vaneps: CS5262**

## Project Overview: Emphasizing the Binary Metric of Cyclist Injuries vs Fatalities
This machine learning project aims to analyze factors contributing to cyclist accidents in New York City, with a focus on distinguishing between incidents resulting in injuries and those resulting in fatalities. The increasing use of bicycles and e-bikes in urban environments underscores the importance of this study. Using data from the New York City vehicle collisions dataset, the project seeks to uncover patterns and correlations that can inform and improve safety measures for cyclists. The primary goal is to train data models that can predict the likelihood of injury versus fatality in cyclist-related accidents, providing valuable insights for cyclists, motorists, and policymakers.

## Explanation of Metrics: Cyclists Killed vs Injured
### Binary Classification
The core of our analysis revolves around binary classification, distinguishing between two crucial outcomes in cyclist accidents: fatalities (killed) and non-fatal injuries (injured). This classification helps in understanding the severity of accidents and the factors leading to more severe outcomes.

#### Key Metrics
- **Injury Rate:** The proportion of accidents where cyclists are injured but not killed.
- **Fatality Rate:** The proportion of accidents resulting in cyclist fatalities.
- **Accuracy:** The overall correctness of the model in predicting injury vs fatality.
- **Precision and Recall:** Precision measures the accuracy of predictions in identifying fatalities, while recall assesses how well the model identifies all actual fatalities.

#### Data
We utilize data from the New York City vehicle collisions dataset, focusing on cyclist accidents.

Dataset Source: [NYC Vehicle Collisions Dataset](https://catalog.data.gov/dataset/motor-vehicle-collisions-crashes)

Processed Subset: [Cyclist Accidents Subset](https://drive.google.com/file/d/1CFaRXe3Y6PWHpYOoGD7qih6-1oWzUi0e/view)


## Confusion Matrix: Interpreting Positive and Negative Results
A confusion matrix will be used to evaluate the performance of our model in predicting injuries versus fatalities.

- **Positive Result (Injured):** A true positive indicates the model correctly predicts a cyclist injury. A false positive means the model incorrectly predicts an injury when the cyclist was actually killed.
- **Negative Result (Killed):** A true negative refers to the model correctly predicting a fatality. A false negative occurs when the model predicts an injury, but the cyclist was killed.

| Confusion Matrix   | Predicted: Injured (Positive) | Predicted: Killed (Negative) |
|--------------------|-------------------------------|------------------------------|
| **Actual: Injured**| True Positive (TP)            | False Negative (FN)          |
| **Actual: Killed** | False Positive (FP)           | True Negative (TN)           |

- **Interpretation:**
  - **True Positives (TP):** Accidents correctly identified as resulting in cyclist injuries.
  - **True Negatives (TN):** Accidents correctly identified as resulting in cyclist fatalities.
  - **False Positives (FP):** Accidents incorrectly labeled as injuries instead of fatalities.
  - **False Negatives (FN):** Accidents incorrectly labeled as fatalities instead of injuries.

#### Economic Costs Associated with Injury and Death

This cost breakdown is meant for policymakers in city and state governments in alignment with a goal of reducing the overall cost on society of injuries and deaths in motor vehicle on cyclist accidents.

The average cost of motor-vehicle injuries and fatalities varies based on the severity of the injury and whether the outcome is fatal or non-fatal. According to the [National Safety Council](https://injuryfacts.nsc.org/all-injuries/costs/guide-to-calculating-costs/data-details/), the average economic cost by injury severity or crash in 2021 was as follows:

| Type                | Cost       |
|---------------------|------------|
| Death:              | $1,778,000 |
| Disabling Injury:   |   $155,000 |
| Evident Injury:     |    $40,000 |
| Possible Injury:    |    $24,000 |
| No Injury Observed: |     $6,700 |

*Since our data doesn't differntiate between disabling and non-disabling injuries, we will use the mean of all possible injuries.*

| Confusion Matrix   | Predicted: Injured (Positive)    | Predicted: Killed (Negative)    |
|--------------------|----------------------------------|---------------------------------|
| **Actual: Injured**| True Positive (TP) -     $73,000 | False Negative (FN) -   $83,000 |
| **Actual: Killed** | False Positive (FP) - $1,800,000 | True Negative (TN) - $1,778,000 |

- **Interpretation**
  - **True Positives (TP):** The cost to society of an accurately predicted injury is the average cost of an injury.
  - **True Negatives (TN):** The cost to society of an accurately predicted fatality is the average cost of that fatality.
  - **False Positives (FP):** The cost to society of a predicted injury that was actually a fatality is the cost of a fatality plus extra for the inaccuracy of the model. Perhaps of a failed intervention that cost money to implement, but didn't ultimately work.
  - **False Negatives (FN):** The cost to society of a predicted fatality that was actually an injury is the cost of an injury plus extra for the inaccuracy of the model. Perhaps of an intervention that was not needed.

This matrix will aid in understanding the model's effectiveness in differentiating between injuries and fatalities in cyclist accidents.