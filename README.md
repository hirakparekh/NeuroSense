<div align="center">

# 🧠 NeuroSense — Multimodal Parkinson's Detection

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=20&pause=1000&color=A855F7&center=true&vCenter=true&width=720&lines=Handwriting+%2B+MRI+%2B+voice+%E2%86%92+a+single+risk+score.;Classical+ML+%2B+deep+learning%2C+fused.;A+non-invasive+screening+proof-of-concept." alt="Typing SVG" />

<p>
  <img src="https://img.shields.io/badge/Python-3.9+-3776AB?logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/Flask-000000?logo=flask&logoColor=white" />
  <img src="https://img.shields.io/badge/OpenCV-5C3EE8?logo=opencv&logoColor=white" />
  <img src="https://img.shields.io/badge/scikit--learn-F7931E?logo=scikit-learn&logoColor=white" />
  <img src="https://img.shields.io/badge/scikit--image-013243" />
  <img src="https://img.shields.io/badge/librosa-FF8C00" />
</p>

<em>A machine-learning screening app that analyzes handwriting patterns, MRI brain scans, and voice recordings to estimate the likelihood of Parkinson's disease — combining classical ML and deep learning into one probabilistic risk score.</em>

</div>

---

## 📌 Overview

Parkinson's disease affects motor control, neurological structure, and speech. Relying on a single
diagnostic signal can be unreliable, so NeuroSense integrates **three complementary modalities** and
fuses their outputs into a final risk assessment:

* ✍️ **Handwriting** (spiral & wave drawings)
* 🧠 **MRI brain scans**
* 🎙️ **Voice recordings**

> ⚠️ **Disclaimer:** This is **not a diagnostic tool.** It is designed to assist clinicians and
> researchers by providing early risk indicators, not to replace professional diagnosis.

<table>
  <tr>
    <td align="center"><img src="handwriting/spiral.png" width="180"/><br/><sub>Spiral drawing</sub></td>
    <td align="center"><img src="handwriting/wave.png" width="180"/><br/><sub>Wave drawing</sub></td>
    <td align="center"><img src="mri/sample.png" width="180"/><br/><sub>MRI scan</sub></td>
  </tr>
</table>

## 🧩 System architecture

| Modality | Input | Processing | Model | Output |
|---|---|---|---|---|
| ✍️ **Handwriting** | Spiral & wave drawings | Grayscale, resize, Otsu thresholding, HOG features | SVM | Probability |
| 🧠 **MRI** | Brain scans | Feature extraction / learning | ML/DL model | Probability |
| 🎙️ **Voice** | Short recordings | Audio signal feature extraction (librosa) | ML classifier | Probability |
| 🔗 **Fusion** | All three | Decision fusion | — | **Aggregated risk score** |

Each modality is analyzed independently with a domain-appropriate model, and the results are
combined into a single probabilistic output.

## 🛠️ Technologies

![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-000000?logo=flask&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?logo=opencv&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?logo=scikit-learn&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?logo=numpy&logoColor=white)
![librosa](https://img.shields.io/badge/librosa-FF8C00)

## 🚀 Getting started

```bash
# 1. Install dependencies
pip install -r requirements.txt

# 2. Run the Flask app
python app.py
```

Then open the local URL Flask prints and upload a sample for each modality.

> **Note:** the trained models in `models/` are tracked with Git LFS — make sure
> [`git lfs`](https://git-lfs.com) is installed before cloning so the `.pkl` files download in full.

## 🗂️ Project layout

```
app.py            Flask web app
templates/        web UI
handwriting/      spiral & wave analysis (HOG + SVM) + notebooks
mri/              MRI scan analysis + notebooks
sound/            voice analysis
models/           trained models + scalers + encoders (Git LFS)
requirements.txt
```

---

<div align="center">
<sub>Built by <a href="https://github.com/hirakparekh">@hirakparekh</a> · A non-invasive screening proof-of-concept · Not for clinical diagnosis</sub>
</div>
