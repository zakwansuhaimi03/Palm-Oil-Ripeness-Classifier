# Palm Oil Fruit Ripeness Classification

![Python](https://img.shields.io/badge/Python-3.9%2B-3776AB?style=flat-square&logo=python&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-Keras-FF6F00?style=flat-square&logo=tensorflow&logoColor=white)
![VGG16](https://img.shields.io/badge/VGG16-Transfer%20Learning-1565C0?style=flat-square)
![Streamlit](https://img.shields.io/badge/Streamlit-App%20Demo-FF4B4B?style=flat-square&logo=streamlit&logoColor=white)

Deep learning system that classifies palm oil fruit ripeness from **drone imagery** into three
classes — **Unripe 🟢, Ripe 🟠, Overripe 🔴** — to support systematic, data-driven harvesting.

> Final Year Project 2024/2025 · Presented at **UM UG IFEST 2025**,
> Universiti Malaya — *Kategori Sains & Teknologi*

---

## 📌 Overview

Manual inspection of palm oil fruit bunches is labour-intensive and inconsistent. This project
applies **transfer learning with VGG16** to drone-captured imagery, providing an automated
ripeness assessment that can feed into a systematic harvesting workflow.

| Model | Role | Result |
|---|---|---|
| **VGG16** | Ripeness classification | **>90% validation accuracy** — strong on ripe-fruit detection |
| **YOLOv8** | Fruit localisation (detection) | Locates fruit in-frame; complements the classifier |

## ✨ Features

- 🖼️ Upload a drone image → instant ripeness prediction with confidence scores
- 🌴 Three ripeness classes: **Unripe / Ripe / Overripe**
- 📊 Interactive results with probability bars (Streamlit UI)
- 🔁 Trained with **colour-preserving data augmentation** (critical for ripeness cues)

## 🛠️ Tech Stack

- **TensorFlow / Keras** — VGG16 transfer learning, fine-tuned for ripeness
- **Streamlit** — web demo application
- **NumPy**, Keras image preprocessing
- Training conducted in **Google Colab**

## 📂 Project Structure

```
PalmRipenessAppLatest2/
├── app.py                   # Streamlit demo app
├── palm_ripeness_model.h5   # Fine-tuned VGG16 model weights
└── README.md
```

## 🚀 Getting Started

### Installation

```bash
git clone https://github.com/YOUR-USERNAME/palm-oil-ripeness-classifier.git
cd palm-oil-ripeness-classifier

pip install streamlit tensorflow numpy
```

### Run the demo

```bash
streamlit run app.py
```

The app opens in your browser — upload a palm oil image and it predicts the ripeness class.

> ⚠️ **Note on the model file:** `palm_ripeness_model.h5` is ~250 MB, which exceeds GitHub's
> 100 MB file limit. Use [Git LFS](https://git-lfs.com) or host the weights on Google Drive
> and update `MODEL_PATH` in `app.py` accordingly.

## 📊 Results & Discussion

- **VGG16 achieved over 90% validation accuracy**, performing strongly on ripe-fruit detection.
- The model frequently **confused ripe vs. overripe** classes — likely due to colour similarity
  and inconsistent lighting in drone images.
- **Class imbalance** (fewer overripe samples) affected learning of overripe features.
- **YOLOv8** localised fruit effectively but struggled with similar-looking classes.
- Consistent labelling and class-folder naming significantly influenced accuracy.

## 🔮 Future Improvements

- Colour-space enhancement (e.g. HSV/Lab) to separate ripe vs. overripe
- More balanced training data, especially overripe samples
- Combine the classifier with the YOLOv8 detector for end-to-end harvesting support

## 👤 Author

**Muhammad Zakwan bin Mohd Suhaimi** (U2101804)
B.Sc. Computer Science (Artificial Intelligence) · Universiti Malaya

Department of Artificial Intelligence, Faculty of Computer Science and Information Technology

---

*Presented at UM UG IFEST 2025 — Category: Science & Technology*
