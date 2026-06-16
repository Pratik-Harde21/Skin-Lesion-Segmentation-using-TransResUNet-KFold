TransResUNet-KFold: Skin Lesion Segmentation Using Transformer-Residual U-Net

This project implements TransResUNet-KFold, a hybrid deep learning model for dermoscopic skin lesion segmentation. The model combines Transformer-based global context, Residual learning, and the classical U-Net decoder. The training uses 5-Fold Cross Validation on the PH2 Resized2 dataset to reduce data imbalance and improve robustness. The system outputs binary segmentation masks and evaluates performance using Accuracy, IoU, and Dice Score.

------------------------------------------------------------
FEATURES
------------------------------------------------------------
- Transformer-enhanced encoder for long-range feature extraction
- Residual blocks for stable deep learning
- U-Net decoder for accurate lesion boundary reconstruction
- Custom rotation and flipping image augmentation
- 5-Fold Cross Validation to reduce data bias
- Computes Accuracy, IoU, and Dice Score
- Produces binary segmentation masks
- Fully runnable on Google Colab or Kaggle

------------------------------------------------------------
DATASET
------------------------------------------------------------
Dataset Used: PH2 Resized2
Contains 200 dermoscopic images with expert-annotated binary masks.
Download link: https://www.kaggle.com/datasets/hashbanger/ph2-resized2

Required folder structure:

dataset/
   images/
   masks/

------------------------------------------------------------
HOW TO RUN THE PROJECT
------------------------------------------------------------

1. Clone the repository:
git clone https://github.com/your-username/TransResUNet-KFold.git
cd TransResUNet-KFold

2. Install dependencies:
pip install tensorflow numpy matplotlib scikit-image opencv-python

3. Prepare the dataset:
Place the PH2 images and masks inside:
dataset/images/
dataset/masks/

4. Run the notebook:
Open:
xskin-lesion-segmentation-using-transresunet-kfold.ipynb
Run in Google Colab, Kaggle, or Jupyter Notebook.

5. Configure dataset paths:
IMAGE_PATH = "/content/dataset/images/"
MASK_PATH  = "/content/dataset/masks/"

6. Preprocessing & Augmentation:
The notebook performs:
- Image resizing
- Pixel normalization
- Binary mask conversion
- Custom rotation + horizontal flip augmentation

Example augmentation function:
img_augmentation() generates rotated and flipped images and masks.

7. Train the model:
Run the training cells. The notebook automatically performs 5-Fold Cross Validation.

8. Evaluate the model:
The notebook prints:
Accuracy, IoU, Dice Score

Expected example results:
Accuracy: 95.72%
IoU: 87.42%
Dice Score: 94.16%

9. View segmentation results:
Predicted masks are saved in:
results/predicted_mask_x.png

10. Save the model:
model.save("TransResUNet_KFold.h5")

------------------------------------------------------------
MODEL ARCHITECTURE
------------------------------------------------------------
The TransResUNet-KFold architecture includes:
- Transformer encoder for global feature modeling
- Residual blocks for deep feature stability
- U-Net decoder for boundary refinement
- Skip connections between encoder and decoder
- Dice-based loss for segmentation learning
- Binary mask output layer

------------------------------------------------------------
METRICS USED
------------------------------------------------------------
Accuracy – Measures overall pixel correctness
IoU – Intersection over Union between prediction & mask
Dice Score – Measures segmentation overlap quality

------------------------------------------------------------
REPOSITORY STRUCTURE
------------------------------------------------------------
TransResUNet-KFold/
   dataset/
   results/
   models/
   utils/
   xskin-lesion-segmentation-using-transresunet-kfold.ipynb
   README.txt

------------------------------------------------------------
AUTHORS
------------------------------------------------------------
Pratik Harde (NITK Surathkal)
Prashant Gangarde (NITK Surathkal)


------------------------------------------------------------
FUTURE WORK
------------------------------------------------------------
- Multi-class lesion segmentation
- Lightweight Transformers for mobile/real-time deployment
- Multi-center clinical dataset validation



