🧠 Image Classifier with TensorFlow & Keras
This project builds and trains a convolutional neural network (CNN) using TensorFlow/Keras to classify images into categories. The dataset was processed on Kaggle, with a workflow that includes data cleaning, model training, and evaluation.

🗃️ Dataset
The dataset was uploaded manually in Kaggle and stored in a read-only directory.
It was filtered to remove corrupt or unsupported image formats (.jpeg, .jpg, .png) and copied to a writable working directory (/kaggle/working/data_dir).

🧪 Model Architecture
A simple CNN built using Keras' Sequential API:

    model=Sequential([
        Input(shape=(256, 256, 3)),
        Conv2D(16, (3, 3), strides=1, activation='relu'),
        MaxPooling2D(),
        Conv2D(32, (3, 3), strides=1, activation='relu'),
        MaxPooling2D(),
        Conv2D(16, (3, 3), strides=1, activation='relu'),
        MaxPooling2D(),
        Flatten(),
        Dense(256, activation='relu'),
        Dense(1, activation='sigmoid')  # Binary classification])

 Training
Images are resized to (256, 256) and normalized (x/255).
Data is loaded using tf.keras.utils.image_dataset_from_directory().
Batch size: 32
Loss: binary_crossentropy
Optimizer: adam

📈 Evaluation
Model accuracy and loss are tracked during training.
Visualizations (loss/accuracy curves) are included in the notebook.

📌 Notes
This project runs entirely in Kaggle Notebooks.
Make sure to install necessary packages using !pip install in the first cell (e.g., for opencv-python or Pillow).
File uploads for testing must be done via the “Files” tab in the left sidebar of the Kaggle editor.
