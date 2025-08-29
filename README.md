# U-Net for Pet Image Segmentation

This repository contains a complete implementation of the U-Net architecture for a semantic segmentation task. The project was developed to segment images of cats and dogs from the **Oxford-IIIT Pet Dataset**, assigning a class label (pet, background, or outline) to each individual pixel.

The entire pipeline, from data preprocessing to model training and visualization, is implemented in a Jupyter Notebook using TensorFlow and Keras.

---

### Results & Visualizations

The trained model is capable of producing highly accurate segmentation masks that closely match the ground truth. Below is a sample prediction from the test set, illustrating the model's performance.

---

### Model Architecture: U-Net

This project utilizes the **U-Net architecture**, which is specifically designed for biomedical image segmentation but has proven to be highly effective for general semantic segmentation tasks. The model consists of two main parts:

1.  **The Contracting Path (Encoder):**
    * A series of convolutional and max-pooling layers that act as a feature extractor. It captures the context of the image, progressively down-sampling the input to learn "what" is in the image.

2.  **The Expansive Path (Decoder):**
    * A series of up-sampling (transposed convolution) and convolutional layers. It works to reconstruct a full-resolution segmentation map from the learned features.

The key feature of U-Net is the use of **skip connections**, which concatenate the feature maps from the encoder path with the corresponding layers in the decoder path. This allows the model to combine high-level contextual information with low-level, fine-grained features, enabling precise localization of the segmentation boundaries.

---

### Dataset

The model was trained on the **Oxford-IIIT Pet Dataset**, which includes:
* 37 categories of cats and dogs.
* ~200 images for each category.
* Detailed pixel-level trimap segmentation masks, which classify each pixel into one of three classes:
    1.  The pet.
    2.  The background.
    3.  A boundary outline.

---
