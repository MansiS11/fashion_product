# 🛍️ Fashion Product Images Classifier

This project aims to build a **multi-output deep learning model** that classifies fashion product images into multiple categories such as **gender**, **master category**, **sub-category**, **article type**, **base color**, and **season**.

The model is trained using the **Fashion Product Images Dataset** and leverages **EfficientNetB0** as the backbone for feature extraction.

---

## 📁 Dataset

- **Source**: [Fashion Product Images Dataset on Kaggle](https://www.kaggle.com/datasets/paramaggarwal/fashion-product-images-dataset)
- **Total Images**: 44,000+
- **Metadata**: Provided in a CSV file with the following columns:
  - `gender`
  - `masterCategory`
  - `subCategory`
  - `articleType`
  - `baseColour`
  - `season`

---

## 📌 Project Workflow

### 1. 🧪 Exploratory Data Analysis (EDA)
- Visualize distribution of categories
- Identify and handle missing values
- Detect and address class imbalance

### 2. 🧹 Data Preprocessing
- Encode categorical labels using LabelEncoder and OneHotEncoder
- Resize and normalize image data
- Train-validation split

### 3. 🧠 Model Architecture
- **Base Model**: `EfficientNetB0` (pre-trained on ImageNet)
- **Output Heads**: Six dense layers for each of the following:
  - Gender
  - Master Category
  - Subcategory
  - Article Type
  - Base Colour
  - Season
- **Loss Function**: Categorical crossentropy (one per output)
- **Optimizer**: Adam
- **Metrics**: Accuracy per category

### 4. 🏋️ Model Training
- Train on a GPU environment
- Use of callbacks like EarlyStopping and ModelCheckpoint

### 5. 📈 Evaluation
- Accuracy metrics per label
- Visual predictions with actual vs predicted categories

---

## 🖥️ Technologies Used

- Python 3.x
- TensorFlow / Keras
- NumPy, Pandas
- Seaborn, Matplotlib
- Scikit-learn
- EfficientNet (from `keras.applications`)

---

## 📊 Sample Prediction

| Image | Gender | Master Category | Subcategory | Article Type | Base Colour | Season |
|-------|--------|------------------|-------------|---------------|--------------|--------|
| ![example](images/sample.jpg) | Women | Apparel | Topwear | T-Shirt | Blue | Summer |

> *Note: Replace `images/sample.jpg` with your actual image path.*

---

## 🔍 Results

- The model performs well on high-level categories like `gender` and `masterCategory`.
- Some confusion occurs in visually similar fine-grained classes like `articleType` and `subCategory`.
- Overall, the architecture demonstrates strong multi-task learning capabilities.

---

## 🚀 Future Improvements

- Apply advanced data augmentation (e.g., `tf.image` pipelines)
- Use attention mechanisms like CBAM or SE blocks
- Hyperparameter tuning and learning rate scheduling
- Grad-CAM or SHAP-based explainability
- Deployment as a Flask/FastAPI API or Streamlit Web App

---

## 📁 Project Structure

