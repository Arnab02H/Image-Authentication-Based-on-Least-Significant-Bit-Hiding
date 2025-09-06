# 📸 Image Authentication using 2-Bit LSB Method

## 📌 Project Overview
This project presents an approach for **Image Authentication** based on the **2-Bit Method** using **Arnold’s Cat Map**. The primary objective is to embed a watermark in images securely, ensuring their authenticity and integrity, which is especially useful for medical images. 🏥🔒

## 👨‍💻 Authors
- **Arnab Bera** 

## 🏫 Institution
**Chennai Mathematical Institute, Chennai**

## 🚀 Features
- ✅ **Watermark Embedding & Extraction:** Secure image authentication through reversible data hiding.
- 🎨 **LSB Hiding Technique:** Ensures imperceptible watermarking without significant image degradation.
- 🌀 **Arnold’s Cat Map:** Used for scrambling the watermark for enhanced security.
- 📊 **Performance Metrics:** Evaluates Peak Signal-to-Noise Ratio (PSNR), Structural Similarity Index (SSIM), and Normalized Cross Correlation (NCC).
- 🛡️ **Attack Resistance:** Resilient to image processing attacks like **histogram equalization, median filtering, Gaussian noise, salt & pepper noise, cropping, JPEG compression**, etc.

## 🛠️ Methodology
### 1️⃣ **Embedding Process**
1. 🖼️ Convert the image using **Haar Wavelet Transform**.
2. 🔍 Divide the image into LL, HL, LH, and HH sub-bands.
3. 🔄 Apply **Arnold's Cat Map** to scramble the watermark image.
4. 🔑 Encode the watermark using **SHA-256 hashing**.
5. 📥 Embed the scrambled watermark into the **HH sub-band** and the SHA-256 hash into **LL sub-band** using **Histogram Shifting**.
6. 🔄 Perform **Inverse Haar Transform** to reconstruct the stego image.

### 2️⃣ **Extraction Process**
1. 🔄 Apply **Haar Transform** on the stego image to extract LL and HH components.
2. 🖼️ Retrieve the watermark from **HH sub-band** and extract the **SHA-256 hash** from **LL sub-band**.
3. 🔄 Reverse **Arnold’s Cat Map** to recover the original watermark.
4. ✅ Verify watermark integrity using **SHA-256 validation**.

## 📊 Experimental Results
- 📂 **Dataset Used:** USC SIPI Image Dataset
- 📈 **Average PSNR:** 60.866 dB
- 🔢 **NCC after Salt & Pepper Noise (0.001 density):** 0.89
- 🛡️ **Performance:** Image authentication works well under normal conditions but is affected by aggressive attacks.

## 📦 Dependencies
Ensure the following Python libraries are installed:
```sh
pip install numpy opencv-python scipy
```

## ▶️ Usage
1. **Run the attack script:**
   Open the desired attack notebook (e.g., `Attack/Median Blur_3/Average Filtering.ipynb`) and run all cells to apply the attack on the images.

2. **Run the extraction script:**
   Open the `Without Attack/code no attacks.ipynb` notebook and run all cells to extract the watermark from the attacked images.

## 🏁 Conclusion
This project successfully implements a **robust image authentication technique** using **Histogram Shifting and Arnold’s Cat Map**. The method is effective for **secure watermark embedding**, but its resilience against aggressive attacks can be improved.

---