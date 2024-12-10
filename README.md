# Exercise 3 - OCR

## Description

1. install and establish python environment including the required packages
2. use the provided python script handwritten-ocr-cnn.py to run all subsequent experiments
3. study the programm code
4. optimize network topology and training the generalisation capabilities and accuracy number of convolutional layers, neurons/planes of the feature and the training to maximize the generalisation by means of dropout layers, learning rate schedules
5. for each of the above means applied: analyse the loss function over both training and validation data and justify their application
6. optimize the training process by continuing from one task to the next by using the best method respectively its parameter
7. after optimizing the training process and the performance of the models by means of the above tasks analyse confusion matrix and accuracy report
8. write a report on the experimental results and findings for each of below tasks


## Virtual Environment 

### Setup 

1. Create a new virtual environment using `venv`:

    ```bash
    python -m venv .venv
    ```
2. Activate the virtual environment:

    - **Windows**:
        ```bash
        .venv\bin\Activate.ps1
        # or .venv\Scripts\activate if not using PowerShell
        ```
    - **Linux/macOS**:
        ```bash
        source .venv/bin/activate
        ```
3. Install the required packages:

    ```bash
    pip install -r requirements.txt
    ```
