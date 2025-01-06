# Report

## Task 1

## Task 2

## Task 3

## Task 4: Optimizers

### 1. Momentum Term in SGD
- **Function**:
  - Momentum helps accelerate convergence by dampening oscillations in directions orthogonal to the gradient's path.
  - It adds a fraction of the previous update to the current update, allowing the algorithm to build up speed in areas with consistent gradients and reduce fluctuations.

### 2. Enhanced SGD with Momentum
The Stochastic Gradient Descent algorithm was enhanced with a momentum term set to **0.9**, as defined in the exercise notes.

### 3. Model Name Update
The model's name was updated dynamically to reflect the learning rate and optimizer configuration. 
This ensures proper identification of output files for loss functions, accuracy, and classification reports.

## 4. Learning Rate Variation
Four learning rates were evaluated: **0.001**, **0.003**, **0.005**, and **0.01**.


## Task 5: Dropout Layer (Regularization)

### Impact of Dropout Rates
Dropout is a regularization technique used to prevent overfitting in neural networks. 
It works by randomly setting a fraction of the layer’s units to zero during training. 
This task investigates the effect of different dropout rates on model accuracy, precision, recall, 
and F1-score, using the MNIST dataset for handwritten digit recognition.

### Results Summary

#### Dropout Rate: 0.2
- **Accuracy**: 98.17%
- **Macro Precision/Recall/F1-Score**: 98.17%
- **Observations**:
    - This dropout rate achieves the best overall accuracy and F1-score, indicating good generalization with minimal overfitting.
    - Validation performance is stable, and the highest precision and recall are observed for most digits.

#### Dropout Rate: 0.3
- **Accuracy**: 98.01%
- **Macro Precision/Recall/F1-Score**: 98.00%
- **Observations**:
    - Performance remains strong but slightly lower than with a dropout rate of 0.2.
    - Slight overfitting reduction is noted compared to the smaller dropout rate.

#### Dropout Rate: 0.4
- **Accuracy**: 96.64%
- **Macro Precision/Recall/F1-Score**: 96.62%
- **Observations**:
    - The model shows signs of underfitting at this higher dropout rate.
    - Validation accuracy drops notably, and F1-scores for some classes (e.g., 2, 3, and 9) decrease due to a lack of sufficient model capacity.