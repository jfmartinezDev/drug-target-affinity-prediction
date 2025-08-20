# Drug–Target Affinity Prediction

A reproducible proof-of-concept pipeline for predicting **drug–target binding affinity (DTA)** using public biomedical data. This project combines **graph neural networks (GNNs)** for molecular graphs with **transformer-based protein embeddings** (ESM2-small as placeholder) and exposes a **FastAPI** service for inference. It is designed for clarity, reproducibility, and lightweight execution in CPU environments (e.g., Google Colab or local Docker).

---

## 📌 Objectives
- Curate a small public subset (placeholder included) to enable rapid prototyping.
- Build a CPU-friendly baseline with GCN/GIN for molecular graphs.
- Fuse molecular embeddings with protein embeddings for affinity regression.
- Implement slots for interpretability (e.g., GNNExplainer, Integrated Gradients).
- Deploy the trained model as a REST API with FastAPI and Docker.

---

## 📂 Repository Structure
```
drug-target-affinity-prediction/
├── data/                # Raw, interim, processed datasets
├── notebooks/           # Prototyping in Jupyter/Colab
├── src/dta/             # Source code (data prep, models, training, explainability)
├── api/                 # FastAPI service
├── tests/               # Unit tests
├── scripts/             # Helper scripts (download, preprocess, train, run API)
├── configs/             # Config files (training hyperparameters, etc.)
├── artifacts/           # Trained models and outputs (ignored in git)
├── Dockerfile           # Container setup
├── docker-compose.yml   # Optional multi-container setup
├── Makefile             # Task automation
├── pyproject.toml       # Optional build/packaging config
├── requirements.txt     # Project dependencies
├── requirements.lock.txt# Locked dependency versions
└── README.md            # Documentation

```

---

## 🚀 Quickstart

### 1. Clone and setup environment
```bash
git clone https://github.com/<your-username>/drug-target-affinity-prediction.git
cd drug-target-affinity-prediction
make setup
```

### 2. Run training (toy dataset included as placeholder)
```bash
make train
```

### 3. Launch API locally
```bash
make api
# Visit http://localhost:8000/docs
```

### 4. Build and run with Docker
```bash
make docker-build
make docker-run
```

---

## 🧪 Testing
Run basic unit tests:
```bash
make test
```

---

## ⚠️ Notes
- This POC favors **portability and simplicity** over full-scale performance.  
- Replace the synthetic dataset with a curated subset of **BindingDB** or other biomedical datasets for realistic experiments.  
- Interpretability methods and uncertainty estimation are left as future work but have placeholders in the codebase.  

---

## 📑 Requirements
- Python 3.10+
- PyTorch (CPU)
- PyTorch Geometric
- RDKit
- FastAPI + Uvicorn
- Scikit-learn, Pandas, NumPy
- pytest, ruff

All dependencies are listed in `requirements.txt`.  

---

## 📌 Future Work
- Implement interpretability with **GNNExplainer** and **Captum Integrated Gradients**.
- Add **scaffold split** and **cold-protein split** evaluations.
- Integrate **conformal prediction** for uncertainty estimation.
- Deploy on cloud services (Azure/GCP/AWS) with containerized API.

---

## 📜 License
[MIT](LICENSE)