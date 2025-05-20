# 🧠 SynAdult: : Multimodal Synthetic Adult Dataset Generation

**SynAdult** is an open-source project that leverages state-of-the-art diffusion models to generate high-quality adult facial data from text prompts. It is a synthetic data generation framework focused on photorealistic adult face synthesis across age groups and ethnicities using fine-tuned Stable Diffusion XL (SDXL) models. This repository supports downstream applications like expression classification, face recognition, and animation synthesis via a multimodal pipeline. It also integrates the **LivePortrait** retargeting pipeline to animate static images with realistic facial expressions and head pose dynamics.

---

## 🚀 Features

- ✨ **High-Fidelity Adult Face Synthesis** using SDXL + DreamBooth.
- 🏷️ Covers multiple **age groups**, **genders**, and **ethnicities** (Asian, African, White).
- 🎭 Integrated **video retargeting pipeline** using [LivePortrait](https://liveportrait.github.io/) for facial expression & head pose animation.
- 📊 Compatible with downstream tasks like face classification and expression recognition.
- 🎥 Generation of neuromorphic event streams (V2E simulator).
- 📡 Outputs include **RGB**, **video**, **event**, and **3D morph** modalities.

---

## 🧩 Pipeline Components

### 1. SDXL DreamBooth Fine-Tuning
We fine-tune SDXL using DreamBooth to learn subject-identity tokens for specific adult appearances.

```bash
python generate.py \
    --model_path=outputs/your_subject_model \
    --prompt="Senior white adult male person with full face in frame and beard, Frontal Pose, Unique face with distinct facial features" \
    --num_inference_steps=50 \
    --guidance_scale=7.5
```

### 2. LivePortrait for Video Retargeting
We adapt the [LivePortrait](https://liveportrait.github.io/) pipeline for facial motion synthesis, enabling:
- Retargeted lip-sync and head motion.
- Video rendering of static SD-generated images.

### 3. Optional: V2E (Video-to-Event) Conversion
Generate event-based neuromorphic streams to simulate privacy-preserving modalities for surveillance, driving, or health applications.

---

## 📁 Folder Structure

```
.
├── sdxl_models/              # Fine-tuned DreamBooth checkpoints
├── scripts/                  # Generation and animation scripts
├── LivePortrait/             # Integrated video retargeting code
├── events/                   # Optional neuromorphic outputs
├── samples/                  # Example outputs (GIFs, videos, meshes)
└── README.md
```

---

## 📜 License & Dataset Access

This project follows an **open-source license** and includes privacy-conscious, non-identifiable synthetic data. For academic and research use only. If you'd like access to the full dataset, please fill out our [dataset access form](#).

---

## 📣 Citation

If you use this work, please cite:

```bibtex
@misc{adultdiff2025,
  title={AdultDiffusion: Multimodal Synthetic Adult Face Dataset using Diffusion and Retargeting},
  author={Your Name et al.},
  year={2025},
  howpublished={\url{https://github.com/your-repo/adultdiffusion}},
}
```

