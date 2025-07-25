# Cat and Dog Image Classifier

This project is a solution to the **freeCodeCamp (FCC) Cat and Dog Image Classification Challenge**. The goal was to build a Convolutional Neural Network (CNN) using TensorFlow and Keras to classify images of cats and dogs with **at least 63% accuracy**.

---

## Challenge Description

The challenge was part of the **Machine Learning with TensorFlow** certification on [freeCodeCamp](https://www.freecodecamp.org/). It required:
- Building an image classifier using TensorFlow 2.x
- Working in Google Colaboratory
- Achieving a minimum test set accuracy of **63%** (bonus for >70%)

Dataset was provided as a ZIP file containing:
- `train/` (with subfolders `cats/` and `dogs/`)
- `validation/` (with subfolders `cats/` and `dogs/`)
- `test/` (with 50 unlabeled images)

---

## How I Solved It

### 1. **Data Preparation**
- Downloaded and unzipped the dataset in Google Colab.
- Used `ImageDataGenerator` to:
  - Normalize image pixel values (`rescale=1./255`)
  - Apply data augmentation (rotation, zoom, flip, shift, etc.) to prevent overfitting.
- Organized the test folder by moving all test images into a subfolder (`unknown/`) to be compatible with `flow_from_directory()`.

### 2. **Model Architecture**
- Built a CNN using Keras `Sequential` model:
  - Stacked 3 Conv2D + MaxPooling2D layers
  - Flattened output, added a Dense layer with ReLU activation
  - Used Dropout to reduce overfitting
  - Output layer with sigmoid activation for binary classification
- Compiled the model with:
  - **Loss**: `binary_crossentropy`
  - **Optimizer**: `adam`
  - **Metric**: `accuracy`

### 3. **Model Training**
- Trained for **15 epochs** using:
  - 2000 training images
  - 1000 validation images
  - Batch size: 20
- Monitored training and validation accuracy/loss

### 4. **Prediction and Evaluation**
- Predicted probabilities for the 50 test images.
- Compared rounded predictions to ground truth labels.
- Achieved accuracy above **63%**, passing the FCC challenge.

---

## Results

- Final model accuracy on the test set: **✔ Passed Challenge**
- Model generalized well without overfitting due to augmentation

---

## 🛠 Technologies Used

- Python
- TensorFlow 2.x
- Keras (High-level API in TensorFlow)
- Google Colaboratory (for execution)
- Matplotlib (for visualization)

---

## How to Run

1. Open the notebook in [Google Colab](https://colab.research.google.com/)
2. Follow the step-by-step code cells to:
   - Download and preprocess the data
   - Define and train the model
   - Predict and visualize results
   - Evaluate performance

---

## Sample Output

Visual predictions for test images include:
- Probability labels: e.g. "95.20% dog" or "82.75% cat"
- Performance plots for training vs. validation accuracy/loss

---

## Credits

This project was completed as part of the [freeCodeCamp TensorFlow Certification](https://www.freecodecamp.org/learn/machine-learning-with-python/).  
Special thanks to FCC for providing structured learning challenges to apply real-world machine learning concepts.

---

## Contact

Feel free to reach out if you have questions or suggestions:

**Krishna Moghe**  
Email: krishnamoghe74@gmail.com  
GitHub: [@KrishnaMoghe](https://github.com/KrishnaMoghe)

