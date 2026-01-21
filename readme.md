# Grayscale to Colored Image Converter 🎨

This project converts **grayscale images into realistic color images** using a **deep learning–based image colorization model**.  
It uses a **pretrained CNN (Caffe model)** integrated via **OpenCV’s DNN module**.

The model predicts the **`ab` color channels** in the LAB color space from a single **L (lightness) channel**, effectively hallucinating plausible colors.

---

## 📌 How It Works (Conceptual Overview)

1. The input image is converted from **BGR → LAB color space**
2. The **L channel (lightness)** is extracted
3. A pretrained CNN predicts the **`ab` chrominance channels**
4. The predicted `ab` channels are merged with the original `L`
5. The image is converted back to **BGR**, producing a colorized result

This approach is based on research by **Zhang et al. (2016)** on automatic image colorization.

---

## 🧠 Model Details

- **Architecture**: CNN trained on ImageNet
- **Framework**: Caffe
- **Color Clusters**: 313 `ab` color centroids
- **Inference Engine**: OpenCV DNN

---

## 📂 Project Structure
GrayTocolored/
│
├── Model/
│ ├── colorization_deploy_v2.prototxt
│ ├── colorization_release_v2.caffemodel
│ └── pts_in_hull.npy
│
├── images/
│ └── img1.jpg
│
├── GrayscaleTocolored.py
└── README.md
