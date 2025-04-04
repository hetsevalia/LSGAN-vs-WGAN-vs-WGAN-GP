# LSGAN-vs-WGAN-vs-WGAN-GP
GAN Comparison for LSGAN vs WGAN vs WGAN-GP
# Comparing LSGAN, WGAN, and WGAN-GP for Pneumonia Detection  

This project evaluates and compares the performance of **Least Squares GAN (LSGAN), Wasserstein GAN (WGAN), and Wasserstein GAN with Gradient Penalty (WGAN-GP)** on **PneumoniaMNIST**, a dataset from **MedMNIST**. The objective is to assess the quality of synthetic pneumonia X-ray images using standard evaluation metrics, **Inception Score (IS)** and **Fréchet Inception Distance (FID)**.  

## Project Overview  
Generative Adversarial Networks (GANs) are widely used for medical image synthesis, augmentation, and enhancement. This study compares three popular GAN architectures:  

1. **LSGAN** – Uses least squares loss instead of binary cross-entropy, leading to smoother gradient updates.  
2. **WGAN** – Introduces Wasserstein distance for improved training stability, replacing the traditional JS-divergence.  
3. **WGAN-GP** – Enhances WGAN by adding a **gradient penalty** to enforce Lipschitz continuity, improving image generation quality.  

## Dataset: PneumoniaMNIST (MedMNIST)  

- **Dataset Source**: PneumoniaMNIST is part of the MedMNIST dataset, specifically designed for lightweight benchmarking of medical image analysis.  
- **Data Description**:  
  - Images: **28×28 grayscale chest X-rays**.  
  - Labels: **Binary classification (pneumonia vs. normal)**.  
  - Total Images: **5,856 training, 1,496 validation, 1,498 test images**.  

###  Citation  
If using this dataset, please cite:  
> Jiancheng Yang, Rui Shi, Donglai Wei, Zequan Liu, Lin Zhao, Bilian Ke, Hanspeter Pfister, Bingbing Ni. Yang, Jiancheng, et al. *"MedMNIST v2 - A large-scale lightweight benchmark for 2D and 3D biomedical image classification."* Scientific Data, 2023.  

> Jiancheng Yang, Rui Shi, Bingbing Ni. *"MedMNIST Classification Decathlon: A Lightweight AutoML Benchmark for Medical Image Analysis".* IEEE 18th International Symposium on Biomedical Imaging (ISBI), 2021.  

## Methodology  

1. **Dataset** – PneumoniaMNIST from MedMNIST.  
2. **Architecture** – Identical generator and discriminator architectures across all models.  
3. **Training Setup**  
   - Models trained for **50 epochs**.  
   - Adam optimizer used with different hyperparameters for each model.  
   - Training performed on **Google Colab with GPU acceleration**.  
4. **Evaluation**  
   - **Inception Score (IS)** for image quality and diversity.  
   - **Fréchet Inception Distance (FID)** for similarity with real images.  

## Results (Epoch 50/50)  

| Model   | Inception Score (↑)  | FID Score (↓)  |  
|---------|----------------|------------|  
| **LSGAN**   | 1.6420  | 26.5000  |  
| **WGAN**    | 1.9418  | 26.5000  |  
| **WGAN-GP** | 1.4848  | 26.5000  |  

- **Inception Score (IS):** Higher values indicate better diversity and image quality.  
- **FID Score:** Lower values indicate generated images are closer to real images.  

### **Observations:**  
- **WGAN achieved the highest IS**, indicating better image diversity and quality.  
- **LSGAN performed moderately well**, while WGAN outperformed it.  
- **WGAN-GP had the lowest IS**, but the difference isn’t drastic.  
- **All models had the same FID score**, suggesting similar similarity to real images.    

## How to Run  

### **Clone the Repository**  
```bash
git clone https://github.com/hetsevalia/LSGAN-vs-WGAN-vs-WGAN-GP.git
cd LSGAN-vs-WGAN-vs-WGAN-GP

```
Install Dependencies

```
pip install torch torchvision numpy matplotlib tensorboard medmnist

```

TensorBoard Results
![WhatsApp Image 2025-04-04 at 18 42 40_a11309e7](https://github.com/user-attachments/assets/e8cab40c-f4a2-4aa1-85f6-0437857dc195)
![WhatsApp Image 2025-04-04 at 18 47 55_28fc2833](https://github.com/user-attachments/assets/7f87e0e1-c805-4f38-878b-57bce8908361)
![WhatsApp Image 2025-04-04 at 18 48 54_3db4ef24](https://github.com/user-attachments/assets/b9b01933-821d-4922-b2ba-284c175bbc14)
![WhatsApp Image 2025-04-04 at 18 49 24_34ce62a4](https://github.com/user-attachments/assets/ab8adaca-de31-4b05-ae9d-d87f1aeac6bd)
![WhatsApp Image 2025-04-04 at 18 49 54_1ce59c53](https://github.com/user-attachments/assets/17d59931-5128-4a59-9a27-ad2bf364ec48)
![WhatsApp Image 2025-04-04 at 18 50 24_62c4fd4d](https://github.com/user-attachments/assets/be30c7e5-df75-44af-a850-ec5778d02915)
![WhatsApp Image 2025-04-04 at 18 50 37_c85cb154](https://github.com/user-attachments/assets/4abadc3c-4520-4d5d-bc83-f83e96a099bd)

## **Future Improvements**

Train on a higher resolution version of the dataset.

Experiment with different learning rates and optimizers.









