
# Binary and Multiclass Image Classification

This project involves building binary and multiclass image classification models using traditional machine learning algorithms. The dataset used contains images of characters and digits (`m`, `n`, `s`, `5`) that are first preprocessed and then used to train and evaluate different classifiers.

## Project Structure

### 1. Data Preprocessing
- **Grayscale Conversion:** All images are converted to grayscale for simplicity.
- **Resizing:** Each image is resized to 28x28 pixels, reducing the dimensionality and making it more manageable for the models.
- **Flattening:** The 28x28 images are flattened into 1D arrays of 784 elements, which serve as the input features for the models.
- **Target Labels:** Separate target labels are created for each classification task:
  - Binary Classification between `m` and `n`
  - Binary Classification between `m` and `s`
  - Multiclass Classification between `m`, `n`, `s`, and `5`
- **Combining Data:** The images and their corresponding labels are combined into a single DataFrame for easier manipulation.

### 2. Binary Classification Models
Two binary classification models are built and evaluated:
- **`m` or `n`:** Logistic Regression is used to classify images as either `m` or `n`.
- **`m` or `s`:** Logistic Regression is used to classify images as either `m` or `s`.

### 3. Multiclass Classification Model
A multiclass classifier is built to distinguish between `m`, `n`, `s`, and `5`. The model is trained using an SGD (Stochastic Gradient Descent) classifier.

### 4. Model Evaluation
- **Confusion Matrix:** Used to visualize the performance of the classifier by showing the true positives, true negatives, false positives, and false negatives.
- **Accuracy Score:** The accuracy score is calculated for both the training and test sets to evaluate model performance.
- **Precision, Recall, F1 Score:** These metrics are calculated to evaluate the model's performance, especially for imbalanced classes.
- **ROC Curve Analysis:** ROC curves are plotted to analyze the performance of the binary classifiers.

### 5. Data Sampling Techniques
- **Random Sampling:** Data is split into training and test sets randomly.
- **K-Fold Cross Validation:** K-Fold cross-validation is used to assess the model's performance more robustly.
- **Stratified K-Fold Cross Validation:** This method ensures that each fold has a representative distribution of the target variable, especially useful for imbalanced datasets.

### 6. Improved Classification with RGB Images
An additional step was taken to explore the performance of models when using RGB images instead of grayscale images. RGB images have more information, but the increased dimensionality can also lead to more complex models.

## Results
- **Binary Classifiers:**
  - The binary classifiers performed well on training data but showed signs of overfitting on test data, particularly due to the imbalance in the classes.
- **Multiclass Classifier:**
  - The multiclass classifier struggled with underfitting, as evidenced by high bias and variance, suggesting a need for more training data or more complex models.
- **Improved Classification:**
  - Using RGB images improved the training accuracy significantly, but the test accuracy showed only negligible improvement. This indicates that simply increasing the input data complexity without improving model architecture or image processing techniques may not lead to better results.

## Future Work
- **Data Augmentation:** Techniques like image rotation, flipping, and noise addition could help in generating more training data and improving model robustness.
- **Use of Deep Learning Models:** Implementing convolutional neural networks (CNNs) could significantly improve the classification performance by better handling image data.
- **Advanced Image Processing:** Applying techniques like binarization or morphological operations could enhance the feature extraction process.

