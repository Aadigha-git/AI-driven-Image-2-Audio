# Stegano-AI-2-Audio


This project proposes a novel methodology for AI-enhanced image-to-audio encryption, combining steganography and encryption techniques. The foundational framework comprises two subsystems: image-in-image steganography and image-to-audio encryption and decryption. This code is an implementation of the paper:
> A. Chennupati, B. Prahas, B. A. Ghali and T. V. Nidhin Prabhakar, "AI-Driven Image-to-Audio Encryption with Data Hiding," 2024 15th International Conference on Computing Communication and Networking Technologies (ICCCNT), Kamand, India, 2024, pp. 1-6, doi: 10.1109/ICCCNT61001.2024.10725794.

## Foundational Framework

The proposed methodology begins with steganography, concealing the input image (secret image) within another image (cover image) to create a steganographic image. This process aims to make the steganographic image indistinguishable from the original cover image. Subsequently, the steganographic image undergoes an image-to-audio encryption process, where it is converted into an audio file for secure transmission. 

## Subsystems Overview

![image](https://github.com/user-attachments/assets/02314b12-8027-4730-99aa-6d7cf3135593)


### 1. Image-in-Image Steganography

![image](https://github.com/user-attachments/assets/9480c0cb-3331-43ec-9b6a-173c62533c34)


The first subsystem consists of two networks: Hide-Net and Reveal-Net. 
- **Hide-Net:** An Unet-based Generator, utilized for concealing information within images through steganography. It employs a U-shaped convolutional neural network architecture with skip connections to preserve high-resolution details during up-sampling.
- **Reveal-Net:** Designed for image generation or reconstruction, transforming an input tensor into an output tensor representing the revealed image. It comprises convolutional layers, batch normalization, and ReLU activation functions.

These networks are trained and validated using 1800 training images and 400 validation images from the Linnaeus 5 image dataset. Training is conducted for 100 epochs, aiming to minimize the h-loss and r-loss values (hide and reveal losses).

### 2. Image-to-Audio Encryption and Decryption

The second subsystem handles the encryption and decryption of images to audio and vice versa.
- **Encryption:** Begins with converting the input image into a bmp file, which is then converted into bytes format, normalized, and scaled. The normalized and scaled image bytes are used to generate an audio file (WAV format).
- **Decryption:** Involves loading the encrypted audio file, converting audio samples to 16-bit samples and byte values, and using these byte values to reconstruct the image using the PIL library. The decrypted image is then saved as a .png file.

## Results and Analysis

The proposed system demonstrates effective concealment and retrieval of information through steganography and image-to-audio encryption processes. The steganographic images and reconstructed images show minimal differences compared to the original images. The evaluation of the encryption and decryption processes reveals robustness, establishing reliability and security in the proposed image-to-audio framework.

## Conclusion

By leveraging cutting-edge techniques in steganography, image-to-audio encryption, and decryption, the proposed framework offers versatile applications in communication, artistic expression, and data protection. The successful fusion of multiple models within a single forum ensures multimedia privacy and security are easily achievable. 
