# Quantum Machine Learning Experiments

> **Phase 2 repair branch:** The branch declares `qiskit-algorithms`, `pylatexenc` and `ipython` without guessing versions. Set `QKT_SOURCE_DIR` to the parent of the original `qkt` package and `QKT_DATASET_PATH` to the original `dataset_graph7.csv`. Missing scientific artifacts remain blocking; no alternative feature map, dataset, checkpoint, or compatibility claims have been introduced. Full runtime validation is pending; the following historical audit describes the original baseline.

## Overview and problem statement

Explore simulated quantum kernels and variational circuits for classification, comparing selected quantum approaches with classical SVM baselines. Intended for experimentation, not evidence of quantum advantage.

## Technology stack and prerequisites

Python 3 and a notebook runtime are required (exact version unspecified). [requirements.txt](requirements.txt) declares matplotlib, numpy, pandas, qiskit, qiskit-machine-learning, scikit-learn, seaborn; all versions are unpinned. Additional notebook dependencies not listed directly: qiskit-algorithms, pylatexenc. Two notebooks specify `qiskit>=1.0` in installation cells; this is a lower bound, not a tested compatible version matrix. Local Jupyter must be installed separately. No exact dependency lock is available.

## Project structure

- [qiskit-quantum-kernel-training.ipynb](notebooks/qiskit-quantum-kernel-training.ipynb) — experiment source.
- [quantum-convolutional-neural-networks.ipynb](notebooks/quantum-convolutional-neural-networks.ipynb) — experiment source.
- [quantum-kernel-optimization.ipynb](notebooks/quantum-kernel-optimization.ipynb) — experiment source.
- [quantum-neural-network-architecture.ipynb](notebooks/quantum-neural-network-architecture.ipynb) — experiment source.
- [requirements.txt](requirements.txt) — dependencies.
- [LICENSE](LICENSE) — repository license, separate from dataset rights.

## Dataset and preprocessing

The kernel optimization and QNN notebooks generate synthetic classification data; QCNN generates synthetic images. The kernel-training notebook references `../../data/dataset_graph7.csv` and imports `qkt.feature_maps` and `qkt.utils`, which are not included. External data provenance and licensing are not confirmed.

## Models and workflow

Kernel training uses TrainableFidelityQuantumKernel, SPSA, QuantumKernelTrainer and QSVC; optimization compares fidelity-kernel SVC against RBF and polynomial SVC with scaling/PCA. QCNN uses eight qubits, ZFeatureMap and convolution/pooling circuit layers with EstimatorQNN and COBYLA (200 iterations). QNN uses ZZFeatureMap, RealAmplitudes, StatevectorEstimator and COBYLA (120 iterations).

## Installation and execution

```bash
git clone https://github.com/Rmadanmohamed/quantum-machine-learning-experiments.git
cd quantum-machine-learning-experiments
python -m venv .venv
```

Activate with `source .venv/bin/activate` (Linux/macOS) or `.venv\Scripts\Activate.ps1` (Windows PowerShell).

```bash
python -m pip install -r requirements.txt
python -m pip install jupyter qiskit-algorithms pylatexenc
jupyter notebook notebooks/quantum-kernel-optimization.ipynb
```

Alternatively, use Google Colab or Kaggle where applicable. For local execution, adjust environment-specific file paths in a local working copy. Install optional notebook-specific packages only for experiments that use them. Exact compatible versions and end-to-end execution have not been verified.

## Environment variables

No application environment-variable configuration was identified in the reviewed notebook sections. Dataset paths and model settings are configured in cells. If downloading data from a restricted source, use that provider's authorized access method rather than embedding credentials.

## Usage, evaluation and limitations

Run the self-contained synthetic experiments separately. The kernel training workflow is blocked until the external `qkt` module and referenced CSV are supplied. Accuracy, balanced accuracy, confusion matrices and timing are computed in the notebooks; no saved numeric outputs were found. Statevector simulation can grow exponentially with qubit count; no physical quantum hardware is required by the shown statevector examples. Do not interpret synthetic accuracy as a real-world quantum speedup.

## Testing and validation

No automated test suite is included. Execute the relevant notebook with its required data and inspect generated results. Training and tests were not executed during this documentation audit.

## Screenshots and demo

No standalone screenshots or verified live demo were found. Generate charts and circuit/model visualizations by executing relevant notebooks.

## Author

**Ramadan Mohamed Hassan** — AI Engineer | AI Researcher | AI Automation | LLM & RAG Systems | Machine Learning

[Portfolio](https://ramadan-ai-portfolio.vercel.app/) · [LinkedIn](https://www.linkedin.com/in/ramadan-mohamed-89085a366/) · [GitHub](https://github.com/Rmadanmohamed) · [Email](mailto:ramadanmohameddd3@gmail.com)
