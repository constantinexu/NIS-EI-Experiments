# NIS-EI-Experiments

# NIS Experiments: Effective Information (EI) Analysis in Artificial Neural Networks

This repository implements the **Neural Information Squeezer (NIS)** framework to analyze **Effective Information (EI)** in artificial neural networks (ANNs) for two tasks: **IRIS Classification** and **MNIST Classification**. The experiments demonstrate how EI evolves across different layers of the network during training, providing insights into the information processing capabilities of ANNs.

## Repository Structure

- **`NIS-IRIS.ipynb`**: Jupyter Notebook for the IRIS classification task using a 4-layer neural network (4→5→5→3).
- **`NIS-MNIST.ipynb`**: Jupyter Notebook for the MNIST classification task using a 5-layer neural network (25→6→6→6→5).
- **`README.md`**: This file, providing an overview of the repository.

## Tasks and Network Architectures

### IRIS Classification
- **Dataset**: IRIS dataset (4 features, 3 classes).
- **Network Architecture**: 4 layers (4→5→5→3).
- **Objective**: Analyze EI dynamics across layers during training.

### MNIST Classification
- **Dataset**: MNIST dataset (25 features after dimensionality reduction, 5 classes).
- **Network Architecture**: 5 layers (25→6→6→6→5).
- **Objective**: Study EI evolution in a deeper network.

## Methodology: EI Calculation in Artificial Neural Networks

The experiments use the **Neural Information Squeezer (NIS)** framework to compute **Effective Information (EI)** for each layer of the network. Unlike traditional mutual information methods, which require discretization of input and output spaces and are computationally expensive in high-dimensional settings, the NIS framework provides an efficient and scalable approach for EI calculation in ANNs. Key steps include:

1. **Input Space Sampling**: Uniform sampling from the input space.
2. **Jacobian Matrix Calculation**: Measuring the sensitivity of outputs to inputs using the Jacobian matrix.
3. **Noise Estimation**: Estimating noise in the output space using Gaussian or Laplacian models.
4. **EI Computation**: Combining input entropy, output dimensionality, noise, and sensitivity to compute EI.
5. **Layer-wise Analysis**: Tracking EI changes across layers during training.

### Advantages Over Traditional Mutual Information Methods
- **Efficiency**: The NIS framework avoids the need for discretization, making it computationally efficient in high-dimensional spaces.
- **Scalability**: It scales well with the complexity of the network and the dimensionality of the data.
- **Interpretability**: The decomposition of EI into input entropy, noise, and sensitivity provides clear insights into the information processing capabilities of the network.
- **Robustness**: The method is robust to low-probability regions in the input space, which are often poorly estimated by traditional methods.

## Results

The results are visualized in the notebooks, showing how EI evolves with training epochs for each layer. Key observations include:
- **MNIST Task**: EI values stabilize over time, with significant changes in hidden layers.
- **IRIS Task**: EI values converge quickly, reflecting the simplicity of the dataset.

## Usage

1. Clone the repository:
   ```bash
   git clone https://github.com/constantinexu/NIS-EI-Experiments.git
   cd NIS-EI-Experiments
   ```
2. Open the notebooks in Jupyter:
   ```bash
   jupyter notebook
   ```
3. Run the cells in `NIS-IRIS.ipynb` and `NIS-MNIST.ipynb` to reproduce the experiments.

## Dependencies

- Python 3.x
- PyTorch
- NumPy
- Matplotlib
- Scikit-learn

Install dependencies using:
```bash
pip install torch numpy matplotlib scikit-learn
```

## References

- **Core Reference**: Jiang Zhang, Kai Liu. Neural Information Squeezer for Causal Emergence. In *Entropy*, volume 25, pages 1–26, 2023.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
