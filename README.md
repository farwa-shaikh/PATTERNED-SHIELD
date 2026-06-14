# 🛡️ Patterned Shield — Deepfake Image Protection Tool

> A browser-based tool that applies visual disruption techniques to protect your photos from deepfake AI systems — no server, no upload, 100% private.

---

## 🔍 What is This?

Deepfake AI works by detecting **facial landmarks** (eyes, nose, mouth) in your photo and using them to map a fake face over yours. This tool fights back by making your image mathematically confusing to those AI systems — while still looking normal to human eyes.

This project is part of my ongoing research into **accessible, low-barrier deepfake protection** for everyday users.

---

## 🧠 Research Background

Most deepfake protection research is highly technical and not accessible to general users. My goal is to bridge that gap — taking concepts from computer vision adversarial research and turning them into something anyone can use, right in their browser.

The tool implements three disruption techniques inspired by physical and digital adversarial methods:

### 1. 🔲 Patterned Shield — Moiré Mesh Overlay
- Overlays a dual-grid interference pattern on the image
- Creates **mathematical noise** that confuses the AI's feature extractor
- The AI sees a broken grid; humans see you normally
- Based on the principle that CNNs are sensitive to high-frequency texture noise

### 2. 💡 Asymmetric Lighting — Depth Map Disruption
- Simulates dual-color cyberpunk lighting (pink + cyan) from opposing angles
- Adds a projected light grid overlay
- Breaks the AI's ability to estimate **3D facial geometry**
- Deepfakes rely on consistent lighting to blend a fake face — impossible lighting = glitchy deepfake

### 3. 💎 Tactile Glitch — Reflective Hotspot Simulation
- Simulates IR-reflective jewelry placed at key facial zones: nose bridge, cheekbones, jaw
- Creates **blown-out hotspots** and pixel disruption rings
- AI can't tell where your skin ends and the object begins
- Based on physical anti-facial-recognition accessory research

---

## ✨ Features

| Feature | Detail |
|---|---|
| 🖼️ Upload any image | PNG, JPG, WEBP supported |
| 🎛️ 3 protection techniques | Switch between them live |
| 📊 Intensity slider | Control the strength of each effect |
| 📈 AI Confusion Score | Visual meter estimating landmark, depth, and skin disruption |
| ⬇️ Download | Save the protected image as PNG |
| 🔒 100% client-side | No server, no API, no data leaves your device |

---

## 🚀 How to Use

### Option 1 — Open directly in browser
```bash
# Just open the HTML file
open deepfake-shield.html
```
No installation needed. Works in any modern browser (Chrome, Firefox, Edge, Safari).

### Option 2 — Clone and run locally
```bash
git clone https://github.com/YOUR_USERNAME/patterned-shield.git
cd patterned-shield
open deepfake-shield.html
```

---

## 🗂️ Project Structure

```
patterned-shield/
│
├── deepfake-shield.html     # Complete self-contained tool (HTML + CSS + JS)
├── README.md                # This file
└── assets/
    └── screenshot.png       # Tool preview (add your own)
```

> The entire tool is a **single HTML file** — no dependencies, no build step, no npm install.

---

## 🖼️ Screenshots

| Original | Protected (Moiré) | Protected (Lighting) |
|---|---|---|
| *(upload your own screenshot)* | *(upload your own screenshot)* | *(upload your own screenshot)* |

---

## 📐 How the Effects Work (Technical)

```
Input Image
    │
    ▼
Canvas API draws original image
    │
    ├──► Technique 1: Dual-grid Moiré
    │       ├── Horizontal lines (cyan, spacing = f(intensity))
    │       ├── Rotated grid at 0.15 rad (pink)
    │       └── Random noise dots
    │
    ├──► Technique 2: Asymmetric Lighting
    │       ├── Radial gradient (pink, top-left)
    │       ├── Radial gradient (cyan, bottom-right)
    │       └── Projected amber grid
    │
    └──► Technique 3: Tactile Glitch
            ├── Hotspots at: nose bridge, L/R cheek, L/R jaw
            ├── Radial bloom (white → green)
            └── Pixel disruption ring + scanline artifacts
    │
    ▼
Protected Image → Download as PNG
```

---

## ⚠️ Limitations & Honest Notes

- This tool applies **visual-layer disruption** — it is not a cryptographic or mathematically proven adversarial attack
- Effectiveness against real-world deepfake models varies and has not been formally evaluated
- This is **research-stage work** — not a production security solution
- Advanced deepfake systems may still process disrupted images with some accuracy
- Think of this as a **first line of defense** and awareness tool, not a guarantee

---

## 🔬 Research Directions (Future Work)

- [ ] Implement pixel-space adversarial perturbations (FGSM, PGD) in-browser using TensorFlow.js
- [ ] Add frequency-domain disruption (DCT coefficient manipulation)
- [ ] Test against open-source deepfake models (DeepFaceLab, SimSwap)
- [ ] Measure PSNR/SSIM to quantify visual quality vs. protection trade-off
- [ ] Add face-detection overlay to target disruption precisely on facial regions
- [ ] Publish formal evaluation results

---

## 🤝 Collaboration

I am actively looking to collaborate with researchers and professors in:

- Computer Vision
- AI Security & Adversarial ML
- Media Forensics
- Digital Privacy

If you are working in any of these areas and would like to collaborate, please feel free to reach out via [LinkedIn](https://linkedin.com/in/YOUR_PROFILE) or open an Issue on this repo.

---

## 👩‍💻 About the Author

**Farwa** — AI Engineer & Research Assistant  
B.E. Electronic Engineering, Mehran University of Engineering & Technology (MUET)  
Based in Karachi, Pakistan

Interests: Graph Neural Networks · Computer Vision · AI Security · IoT Systems

---

## 📄 License

```
MIT License

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software to use, copy, modify, merge, publish, distribute, and/or
sell copies of the software, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND.
```

---

## ⭐ If this project helped you or interested you, please give it a star!

*Research is better when shared. Feel free to fork, build on it, and credit back.*
