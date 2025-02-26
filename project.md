# Super Image Resolution Generator using GAN - Generative Adversarial Network
### ~ Pratham Vyas
### 1. General Idea : 
This file serves as the main documentation for the repository. It provides an introduction to **ESRGAN (Enhanced Super-Resolution Generative Adversarial Networks)**, highlights recent updates, and offers links to related resources such as **BasicSR** and **Real-ESRGAN**. The README also includes guidance on how to use the provided models and scripts for image super-resolution tasks.

## 2. Transfer_RRDB_models : 
This script is used for converting or transferring pre-trained RRDB models from other frameworks or formats into the format compatible with this ESRGAN implementation. This is particularly useful if you have models trained elsewhere that you wish to use within this codebase.

## 3. RRDBNet_architecture :
This script defines the architecture of the RRDBNet (Residual-in-Residual Dense Block Network), which is the **generator network** used in ***ESRGAN***. The key components include:

1. **Residual-in-Residual Dense Blocks (RRDB)**: These are the building blocks of the network, combining multiple dense layers with residual connections to effectively capture complex features.

2. Network Structure: The RRDB blocks are stacked sequentially, **followed by upsampling layers** to increase the image resolution. 

3. The final layer *outputs* the ***high-resolution image***.
![](figures\architecture.jpg)
![](figures\RRDB.png)

## 4. Net_interpreter: 
This script provides functionality for **interpolating between two trained ESRGAN models**. Model interpolation can be useful to balance between different training objectives, such as **perceptual quality** and **fidelity**. The main aspects include:

1. **Loading Models**: The script loads two pre-trained models specified by the user.

2. **Interpolation Process**: It computes a weighted average of the parameters of the two models based on a given **interpolation factor**.

3. **Saving Interpolated Model**: The resulting interpolated model is saved for later use in **super-resolution tasks**.

## 5. Test : 
This script is designed for testing the ESRGAN model on low-resolution images to produce super-resolved outputs. The primary functions include:

1. **Loading the Model**: It loads a pre-trained ESRGAN model.

2. **Processing Images**: The script reads low-resolution images, processes them through the model, and generates high-resolution outputs.

3. **Saving Results**: The super-resolved images are saved to a specified directory for evaluation.


![](figures\qualitative_cmp_03.jpg)
![](figures\abalation_study.png)