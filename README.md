📘 HOW TO USE (Must Read)

This system predicts drought severity using satellite imagery from Sentinel-2 and Landsat 8. Follow these steps carefully to run the pipeline:

### 🔹 1. Upload Dataset

Start by uploading the required satellite bands to your Colab or working directory:

* `B03.jp2` – Green band (Sentinel-2)
* `B04.jp2` – Red band (Sentinel-2)
* `B08.jp2` – Near Infrared band (Sentinel-2)
* `B10.TIF` – Thermal Infrared band (Landsat 8 Band 10)
* `MTL.txt` – Metadata file from Landsat (for LST calibration)

These files are mandatory for feature extraction and drought classification.

🔹 2. Run Feature Extraction Code

Execute the code block to calculate:

* NDVI (Vegetation health)
* NDWI (Water content)
* LST (Land Surface Temperature)
* GLCM contrast and Wavelet energy

The output will include vegetation maps, a color-coded drought risk map, and feature scores.

🔹 3. Optional: Deep Learning Prediction

If you're using the deep learning model:

* Upload or generate the `.h5` model file (e.g., `cv_drought_vit.h5`)
* Upload 6 `.npy` NDVI stacks (e.g., `ndvi_Jan.npy`, `ndvi_Feb.npy`, etc.)
* Upload a `true_labels.npy` file if you want to evaluate accuracy

The model will output:

* Pixel-wise class predictions (Normal, Moderate, Severe)
* Accuracy, Precision, F1 Score, and a confusion matrix

### 📌 Notes

* All `.jp2`, `.TIF`, and `.npy` files must be uploaded before running
* Colab may require re-uploading files after each restart
* You may edit the NDVI threshold logic or model structure as needed
