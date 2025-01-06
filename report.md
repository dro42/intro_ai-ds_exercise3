# Report

## Task 1

### Role of Convolution and Pooling Layers
- **Convolution Layers**: Extract local patterns from the input images by applying filters, enabling the network to learn spatial hierarchies of features.
- **Pooling Layers**: Reduce the spatial dimensions of feature maps, improving computational efficiency and reducing overfitting while retaining essential information.

### Experimental Setup
- **Enhancements**: A third pair of convolution and pooling layers was added to enhance feature extraction.
- **Feature Maps**: The number of planes/feature maps was varied across four configurations: **10**, **16**, **25**, and **50**.
- **Evaluation Metrics**: Accuracy, Precision, Recall, F1-Score

---

### Results Summary

#### Feature Maps: 10
- **Accuracy**: 96.09%
- **Macro Precision/Recall/F1-Score**: 96.10%
- **Observations**:
  - Achieved reasonable accuracy but showed underfitting on some classes (e.g., `8` and `7`).
  - Limited feature maps constrained the model's ability to capture complex patterns.

---

#### Feature Maps: 16
- **Accuracy**: 96.44%
- **Macro Precision/Recall/F1-Score**: 96.45%
- **Observations**:
  - Improved performance compared to 10 feature maps.
  - Validation loss was stable, and the model exhibited better generalization.

---

#### Feature Maps: 25
- **Accuracy**: 93.14%
- **Macro Precision/Recall/F1-Score**: 93.06%
- **Observations**:
  - Accuracy and precision dropped, indicating overfitting despite the increased feature maps.
  - Some classes (e.g., `8` and `9`) performed significantly worse.

---

#### Feature Maps: 50
- **Accuracy**: 93.62%
- **Macro Precision/Recall/F1-Score**: 93.57%
- **Observations**:
  - Model struggled with overfitting despite a larger capacity.
  - Loss curves exhibited higher fluctuations, impacting generalization on the test set.

---

### General Observations
- **Optimal Feature Maps**: 16 feature maps struck a good balance between model capacity and generalization.
- **Impact of Increased Feature Maps**: Beyond 16, adding more feature maps led to diminishing returns and overfitting.
- **Topology Efficiency**: The additional convolution and pooling layer improved feature extraction but required careful tuning of feature maps to prevent overfitting.


## Task 2: Learning Rate

### Role of Learning Rate in Optimization
The learning rate is a crucial hyperparameter in optimization algorithms that controls the step size at which the model updates its weights. A well-tuned learning rate ensures smooth convergence, while values that are too high or too low may lead to instability or slow training.

### Experimental Setup
- **Optimizer**: Stochastic Gradient Descent (SGD)
- **Learning Rates Tested**: 0.001, 0.003, 0.005, and 0.01
- **Evaluation Metrics**: Accuracy, Precision, Recall, F1-Score

### Results Summary

#### Learning Rate: 0.001
- **Accuracy**: 98.57%
- **Macro Precision/Recall/F1-Score**: 98.57%
- **Observations**:
  - Achieved the best balance between training and validation performance.
  - Loss function exhibited stable convergence.

---

#### Learning Rate: 0.003
- **Accuracy**: 98.58%
- **Macro Precision/Recall/F1-Score**: 98.57%
- **Observations**:
  - Slightly higher accuracy than 0.001, but the validation loss was marginally less stable.
  - Effective for consistent gradient updates.

---

#### Learning Rate: 0.005
- **Accuracy**: 98.45%
- **Macro Precision/Recall/F1-Score**: 98.44%
- **Observations**:
  - Minor instability in validation loss curves, indicating a trade-off between convergence speed and stability.
  - Performance was strong but slightly lower than smaller learning rates.

---

#### Learning Rate: 0.01
- **Accuracy**: 98.24%
- **Macro Precision/Recall/F1-Score**: 98.23%
- **Observations**:
  - The highest learning rate showed signs of reduced generalization, with increased fluctuations in the loss function.
  - Certain classes (e.g., `5`, `9`) exhibited reduced precision due to the larger step size.

---

### General Observations
- **Optimal Learning Rate**: 0.003 provided the best accuracy with relatively stable convergence.
- **Impact of Larger Learning Rates**: Higher rates led to slight overfitting and instability in validation loss.
- **Convergence Behavior**: Smaller learning rates (0.001–0.003) offered smoother convergence and better overall performance.


## Task 3: Learning Rate Schedules

### Learning Rate as an Optimization Parameter
- Learning rate determines the step size for updating weights during optimization.
- Learning rate schedules adapt the learning rate over time to improve convergence and generalization.

### Learning Rate Schedules Used
An **Exponential Decay** schedule was applied:
- `initial_learning_rate`: Varied between **0.001**, **0.003**, **0.005**, and **0.01**.
- `decay_rate`: 0.9 over `n_epochs`.

### Results Summary

#### Learning Rate: 0.01
- **Accuracy**: 98.57%
- **Observations**: Stable convergence with high precision and recall across all classes.

#### Learning Rate: 0.001
- **Accuracy**: 97.70%
- **Observations**: Smooth loss convergence, but slower learning compared to higher rates.

#### Learning Rate: 0.003
- **Accuracy**: 98.32%
- **Observations**: Balanced learning and generalization with slightly faster convergence.

#### Learning Rate: 0.005
- **Accuracy**: 98.20%
- **Observations**: Minor instability in loss convergence but comparable performance to lower rates.

### General Observations
- **Optimal Schedule**: A learning rate of **0.003** with exponential decay provided the best balance between accuracy and stable convergence.
- Larger learning rates (e.g., **0.01**) achieved faster convergence but required careful regularization to avoid oscillations.


## Task 4: Optimizers

### Momentum Term in SGD
- **Function**:
  - Momentum helps accelerate convergence by dampening oscillations in directions orthogonal to the gradient's path.
  - It adds a fraction of the previous update to the current update, allowing the algorithm to build up speed in areas with consistent gradients and reduce fluctuations.

### Enhanced SGD with Momentum
The Stochastic Gradient Descent algorithm was enhanced with a momentum term set to **0.9**, as defined in the exercise notes.

### Learning Rate Variation
Four learning rates were evaluated: **0.001**, **0.003**, **0.005**, and **0.01**.

### Results Summary

#### Learning Rate: 0.001
- **Accuracy**: 98.20%
- **Macro Precision/Recall/F1-Score**: 98.19%
- **Observations**:
  - Achieved the best balance between training and validation accuracy.
  - Loss function showed smooth convergence without significant fluctuations.

---

#### Learning Rate: 0.003
- **Accuracy**: 98.14%
- **Macro Precision/Recall/F1-Score**: 98.13%
- **Observations**:
  - Slightly lower accuracy compared to 0.001.
  - Validation loss is consistent but slightly higher, indicating reduced generalization compared to the smallest learning rate.

---

#### Learning Rate: 0.005
- **Accuracy**: 96.71%
- **Macro Precision/Recall/F1-Score**: 96.71%
- **Observations**:
  - Model begins to show signs of underfitting for certain classes (e.g., `2` and `8`).
  - Loss curves exhibit minor instability due to the larger learning rate.

---

#### Learning Rate: 0.01
- **Accuracy**: 97.71%
- **Macro Precision/Recall/F1-Score**: 97.69%
- **Observations**:
  - Performance is slightly worse than 0.001, with some overfitting observed in the validation loss.
  - Certain digits (e.g., `3`, `5`, `9`) experience reduced precision due to oscillations caused by the higher learning rate.

---

### Loss Function Analysis
- For **0.001** and **0.003**, the loss functions for training and validation data converged smoothly, demonstrating stable learning and better generalization.
- For **0.005** and **0.01**, the loss functions showed higher fluctuations, indicating instability and suboptimal convergence.

---

### General Observations
- **Optimal Learning Rate**: 0.001. It provided the best trade-off between training and validation performance with stable convergence.
- **Momentum Effect**: Using momentum significantly improved convergence speed and stability, especially for smaller learning rates.
- **Impact of Larger Learning Rates**: As the learning rate increased, the model struggled to generalize and showed signs of instability, particularly with 0.01.


## Task 5: Dropout Layer (Regularization)

### Impact of Dropout Rates
Dropout is a regularization technique used to prevent overfitting in neural networks.
It works by randomly setting a fraction of the layer’s units to zero during training.
This task investigates the effect of different dropout rates on model accuracy, precision, recall,
and F1-score, using the MNIST dataset for handwritten digit recognition.

### Dropout Variation
Four dropout values were evaluated: **0.2**, **0.3**, **0.4**, and **0.5**.

### Results Summary

#### Dropout Rate: 0.2
- **Accuracy**: 98.17%
- **Macro Precision/Recall/F1-Score**: 98.17%
- **Observations**:
  - This dropout rate achieves the best overall accuracy and F1-score, indicating good generalization with minimal overfitting.
  - Validation performance is stable, and the highest precision and recall are observed for most digits.
  - Loss curves indicate a balanced model capacity with no overfitting or underfitting.

#### Dropout Rate: 0.3
- **Accuracy**: 98.01%
- **Macro Precision/Recall/F1-Score**: 98.00%
- **Observations**:
  - Performance remains strong but slightly lower than with a dropout rate of 0.2.
  - Slight overfitting reduction is noted compared to the smaller dropout rate.
  - Loss curves suggest a trade-off between generalization and model capacity.

#### Dropout Rate: 0.4
- **Accuracy**: 96.64%
- **Macro Precision/Recall/F1-Score**: 96.62%
- **Observations**:
  - The model shows signs of underfitting at this higher dropout rate.
  - Validation accuracy drops notably, and F1-scores for some classes (e.g., 2, 3, and 9) decrease due to a lack of sufficient model capacity.
  - Loss curves show a slower convergence and higher validation loss compared to lower dropout rates.

#### Dropout Rate: 0.5
- **Accuracy**: 95.27%
- **Macro Precision/Recall/F1-Score**: 95.23%
- **Observations**:
  - The highest dropout rate leads to significant underfitting, as the model struggles to learn meaningful features.
  - Precision and recall scores drop for most classes, with class-specific performance variations becoming prominent.
  - Loss curves show inconsistent convergence, indicating insufficient model capacity to fit the training data adequately.

### General Observations
- A **dropout rate of 0.2** provides the best balance between generalization and accuracy.
- As the dropout rate increases, the model transitions from minimal overfitting to underfitting, reducing its ability to generalize effectively.
- **Recommendation**: Use a dropout rate between **0.2 and 0.3** for optimal performance with this architecture and dataset.

## Best model configuration
- Feature Maps: 16
- Learning Rate: 0.003
- Learning Rate Sch