# PyTorch Practice

A collection of hands-on PyTorch notebooks for learning how neural networks work, from raw tensor math to `torch.nn`-based architectures.

## 📁 Repository Structure

```
pytorch_practice/
├── neural network from scratch/
│   └── scratch.ipynb        # Logistic regression built with raw PyTorch tensors (manual gradients)
├── ANN/
│   ├── ann.ipynb             # Artificial Neural Network built with torch.nn
│   └── fmnist_small.csv      # Small Fashion-MNIST dataset used for training
└── README.md
```

## 📓 Notebooks

### 1. `neural network from scratch/scratch.ipynb`
Builds a simple binary classifier **without** `torch.nn`, to understand what's happening under the hood:
- Loads the **Breast Cancer Wisconsin (Diagnostic)** dataset directly from a CSV URL
- Preprocesses data with `StandardScaler` and `LabelEncoder`
- Implements a custom `SimpleNN` class with manually initialized weights/bias
- Computes a **sigmoid** forward pass and a hand-written **binary cross-entropy** loss
- Performs manual gradient descent (`loss.backward()` + manual parameter updates) — no optimizer object
- Evaluates classification accuracy on the test set

### 2. `ANN/ann.ipynb`
Builds a proper Artificial Neural Network using PyTorch's high-level API:
- Loads a small **Fashion-MNIST** subset (`fmnist_small.csv`) and visualizes sample images
- Wraps the data in a custom `Dataset` / `DataLoader` pipeline
- Defines a `MyNN` model with `nn.Sequential` (Linear → BatchNorm1d → ReLU → Dropout, stacked twice, ending in a 10-class output layer)
- Trains with `CrossEntropyLoss` and `SGD` (with weight decay)
- Evaluates using accuracy, a confusion matrix, and a classification report
- Plots the training loss curve over epochs

## 🛠️ Requirements

- Python 3.8+
- [PyTorch](https://pytorch.org/get-started/locally/)
- pandas
- numpy
- scikit-learn
- matplotlib
- jupyter

## ⚙️ Installation

```bash
git clone https://github.com/Kabeer07-dev/pytorch_practice.git
cd pytorch_practice
pip install torch pandas numpy scikit-learn matplotlib jupyter
```

## 🚀 Usage

Launch Jupyter and open either notebook:

```bash
jupyter notebook
```

Then run:
- `neural network from scratch/scratch.ipynb` to see how a network works at the tensor/gradient level
- `ANN/ann.ipynb` to see a full training pipeline built with PyTorch's `nn` module

## 🎯 Purpose

This repo is a personal learning space for practicing PyTorch fundamentals — going from manual tensor operations and gradients to using PyTorch's built-in layers, optimizers, and evaluation tools.

## 📄 License

No license specified yet. Add one (e.g. [MIT](https://choosealicense.com/licenses/mit/)) if you'd like others to reuse this code.