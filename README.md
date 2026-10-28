# Gemma 3.5 (4B) — Portable AI Medical Assistant

<p align="center">
  <img src="https://img.shields.io/badge/Fine--Tuned%20With-QLoRA-blueviolet?style=for-the-badge&logo=nvidia" alt="QLoRA">
  <img src="https://img.shields.io/badge/Architecture-Gemma%203.5%204B-blue?style=for-the-badge&logo=google" alt="Gemma">
  <img src="https://img.shields.io/badge/Quantization-GGUF%20%7C%20Q4__K__M-success?style=for-the-badge" alt="GGUF">
  <img src="https://img.shields.io/badge/Platforms-iOS%20%7C%20Android%20%7C%20Linux%20%7C%20macOS-orange?style=for-the-badge&logo=apple" alt="Platforms">
</p>

---

## 📌 Overview

**Gemma 3.5 (4B Medical Edition)** is a specialized, fine-tuned variant built on top of **Google's Gemma 3.5 (4B)** architecture. Optimized locally using 4-bit QLoRA on NVIDIA hardware, merged, and converted to high-efficiency GGUF format, it is engineered to run as a fast, fully offline, privacy-focused medical assistant on mobile devices (**iOS & Android**) and local edge environments.

---

## 📱 Hardware & System Requirements

To ensure smooth local execution without memory issues or system throttling (e.g. iOS Jetsam limits), your target device must meet the following criteria:

* **RAM Requirement:** **8 GB RAM or higher** (12 GB+ RAM recommended for optimal multitasking).
* **iOS Devices:** **iPhone 16 series or newer** (iPhone 15 Pro, iPhone 16/16 Pro, iPhone 17 Pro Max, etc.).
* **Android Devices:** Modern Android devices with **8 GB+ RAM** running GGUF-compatible runners (e.g., PocketPal AI, ML Studio).
* **Storage Space:** ~2.5 GB of free storage for the GGUF model file.

---

## ⚡ Key Features

* **100% Offline & Private:** Operates entirely locally with zero cloud dependencies or data leakage risks.
* **Cross-Platform:** Runs seamlessly on both **iOS** and **Android** mobile systems.
* **Optimized Gemma 3.5 Quantization:** Converted to `Q4_K_M` GGUF for the best balance between speed, RAM consumption, and intelligence.
* **Mobile Ready:** Designed to strictly respect mobile OS memory limits with an optimal context size of 512–1024 tokens.
* **Domain Alignment:** Fine-tuned specifically on medical domain datasets, clinical rationale, and interactive consultation workflows.

---

## 🛠️ Pipeline & Tech Stack

The model was trained, merged, and packaged using an end-to-end local machine learning workflow:

```text
[Raw Gemma 3.5 4B]
       │
       ├──> 🧬 4-bit QLoRA Training (bitsandbytes / PyTorch / CUDA on RTX 3060 12GB)
       │
       ├──> 🔀 Adapter Merging (fp16 merged model weights -> custom/)
       │
       └──> ⚡ llama.cpp Conversion & Quantization (GGUF Q4_K_M format)
               │
               └──> 📱 Mobile Deployment (PocketPal AI on iOS & Android via Releases)
