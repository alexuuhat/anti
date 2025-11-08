# 🤖 AI-Powered Anti-Malware System
> Hybrid Machine-Learning + Behavioural Defence Engine for Malware Detection & System Sanitisation

---
## 📌 Overview

This project presents an **AI-augmented Anti-Malware framework** designed for advanced malware detection and system sanitisation.  
It combines **static ML analysis, behavioural threat intelligence, and system cleaning capabilities** — fully offline.

### Capabilities
- Hybrid **XGBoost + Transformer** detection engine  
- Malware artefact cleanup & temp system sanitisation  
- Offline executable inference (no cloud)  
- Manual OS verification support via `mrt.exe`

> Built for research labs, malware analysis learning, and cyber-defence experiments.

---

## 🚀 Features

| Capability | Description |
|---|---|
AI Malware Detection | Static + Behaviour ML ensemble  
System Cleanup | Clears malware artefacts & junk  
Admin-Level Execution | Deep cleanup requires elevated privileges  
Offline Mode | No network required  
Manual Verification | Supports Windows MRT security validation  

---

## 🧠 System Components

| File | Purpose |
|---|---|
`Alex_tmpC.exe` | System junk + malware trace cleaner  
`Antimalware.exe` | AI-powered malware scanner  

> **Run both as Administrator** for full cleaning capability.

---

## 🧩 Architecture

### Detection Pipeline

```mermaid
flowchart TD  
A[Input File] --> B[Static Feature Extractor]  
A --> C[Behaviour Data Collector]  
B --> D[XGBoost Static Classifier]  
C --> E[Transformer Behaviour Model]  
D --> F[Ensemble Fusion Layer]  
E --> F  
F --> G[Malware Verdict + Confidence Score]
````

---

## 📚 Dataset & Lab Environment

| Source  | Notes                                         |
| ------- | --------------------------------------------- |
| Malware | Public datasets, malware feeds, isolated labs |
| Benign  | Signed system binaries & trusted software     |

> All datasets handled in **air-gapped sandboxes**.

### Labels

* malicious
* benign
* *optional:* malware family & behavioural tag classes

### Features Used

| Type      | Examples                                          |
| --------- | ------------------------------------------------- |
| Static    | PE metadata, imports, entropy, byte histograms    |
| Behaviour | API calls, registry edits, FS ops, network traces |
| Heuristic | Path intelligence, execution context patterning   |

### Dataset Split

| Stage                | %   |
| -------------------- | --- |
| Train                | 70% |
| Validation           | 15% |
| Test (chronological) | 15% |

---

## 🧠 Model Training

### Models

| Model              | Role                            |
| ------------------ | ------------------------------- |
| XGBoost            | Structured static code features |
| Transformer / LSTM | Behavioural event sequences     |
| Hybrid Fusion      | Combines both inference outputs |

### Hyperparameters

```yaml
Transformer:
  dim: 128
  layers: 6
  heads: 8
  dropout: 0.1

XGBoost:
  n_estimators: 1000
  max_depth: 8
  learning_rate: 0.05
```

### Evaluation Metrics

* ROC-AUC
* Precision @ Low-FPR
* Recall / F1
* Drift monitoring optional

---

## ⚙️ Usage Guide

### Execution Order

```
1️⃣ Run Alex_tmpC.exe (Administrator) — junk + artefact cleanup
2️⃣ Run Antimalware.exe (Administrator) — AI malware scan
3️⃣ Optional: Validate with MRT → Win + R → mrt
```

### CLI Options

```
Antimalware.exe --scan <path>
Antimalware.exe --full
Antimalware.exe --log <file>

Alex_tmpC.exe --clean-temp --clean-cache
```

> **No internet required** — fully offline engine.

---

## 📂 Project Layout

```
/project
 ┣ /models
 ┣ /src
 ┣ /docs
 ┣ requirements.txt
 ┗ README.md
```

---

## 📘 Model Card

| Category       | Info                                            |
| -------------- | ----------------------------------------------- |
| Task           | AI malware classification & system sanitisation |
| Environment    | Offline Windows lab VM                          |
| Threat Surface | Executable malware + behaviour logs             |
| Limitation     | Kernel / firmware rootkits out-of-scope         |
| Privacy        | 100% local inference                            |

---

## 🛡 Threat Model Coverage

| Threat                    | Support       |
| ------------------------- | ------------- |
| Standard Windows malware  | ✅             |
| Behaviour-based malware   | ✅             |
| Script droppers & loaders | ✅ heuristic   |
| Kernel-level malware      | ⚠ partial     |
| Firmware malware          | ❌ not covered |

---

## ✅ Operational Safety

* Run in **VM / sandbox only**
* Snapshot OS before live malware testing
* Log outputs for incident study
* **Never** release trained models with malware samples

---

## ⚠ Disclaimer

This project is **strictly for educational + research use**.
Author holds **no responsibility** for misuse or harm.

---

## 📜 License

**MIT License** — free to modify, study, and extend in research environments.

---

## 🤝 Contribution

* PRs welcome
* Ideas & research collabs appreciated
* Ethical security researchers only

---
