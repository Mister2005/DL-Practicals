# Implementation Plan: DL Practical Exam Notebooks

This plan details the variations to be added to each of the 8 experiments to meet your teacher's exam requirements. The goal is to keep the code extremely clean and simple so that it resembles code written by a college student in a practical exam.

## Open Questions
> [!IMPORTANT]
> **Exp 1 (Perceptron) - "Static Sum":** A single-layer perceptron cannot logically solve the XOR problem, which is required for the "Sum" bit in binary addition. Does "static sum" refer to implementing the Carry bit (which is an AND gate), or should I use a multi-layer perceptron (MLP) for the sum, or simply provide the XOR training data and show that a single perceptron fails to converge? I will implement AND, OR, NAND, and NOR as requested. For "static sum", I'll provide an MLP OR just a simple sum function unless you clarify.
> 
> **Exp 8 (Diffusion Model):** Implementing a full Diffusion model from scratch is highly complex for an exam. Is it acceptable to implement a very simplified version demonstrating the "forward process" (adding random noise to an image over steps) and a basic "reverse process" (a simple Autoencoder or CNN predicting the noise)?

## Proposed Changes

### Exp 1: Perceptron
**Goal:** Implement logic gates AND, OR, NAND, NOR, and static sum.
- **Modifications:**
  - Create a single versatile Perceptron class/function.
  - Hardcode training data and targets for AND, OR, NAND, and NOR.
  - Train and evaluate the perceptron on all 4 gates sequentially in the notebook.
  - Add a section for "static sum" to demonstrate learning a simple addition operator.

### Exp 2: Backpropagation
**Goal:** Variations with random weights, Xavier initialization, and MLPClassifier.
- **Modifications:**
  - **Variation 1:** Custom backpropagation implementation initializing weights randomly (e.g., `np.random.randn`).
  - **Variation 2:** The same custom backpropagation but with Xavier/Glorot initialization (`np.random.randn * sqrt(1/n)`).
  - **Variation 3:** Use `sklearn.neural_network.MLPClassifier` to solve the same problem using library functions.

### Exp 3: Convolutional Neural Network (CNN)
**Goal:** Apply CNN on loading one image, on a given matrix, and on a given dataset.
- **Modifications:**
  - **Variation 1 (One Image):** Load a single image (e.g., using OpenCV or PIL) and pass it through a manual or Keras convolution layer to show feature extraction.
  - **Variation 2 (Given Matrix):** Define a hardcoded 2D NumPy array and apply a hardcoded filter/kernel manually (using `scipy.signal.convolve2d` or nested loops).
  - **Variation 3 (Given Dataset):** Build a simple Keras `Sequential` CNN and train it on the MNIST dataset.

### Exp 4: Recurrent Neural Network (RNN)
**Goal:** RNN sentiment analysis on a given/own dataset.
- **Modifications:**
  - Discard the current shape-based CNN code in Exp-4.
  - Implement a straightforward Keras `SimpleRNN` or `LSTM` model.
  - Use the built-in Keras IMDB movie review sentiment dataset.
  - Keep preprocessing (padding sequences) and model architecture minimal.

### Exp 5: Self-Organizing Map (SOFM/SOM)
**Goal:** SOFM on a given problem.
- **Modifications:**
  - Refine the current custom SOM implementation.
  - Apply it to a simple given problem like clustering RGB colors or a small 2D coordinate dataset to visually show the grid adapting to the data.

### Exp 6: PCA and Autoencoder
**Goal:** PCA and autoencoder on a given dataset.
- **Modifications:**
  - Use the Iris dataset or MNIST.
  - Implement `sklearn.decomposition.PCA` to reduce dimensionality and reconstruct.
  - Implement a basic Keras Autoencoder (Encoder + Decoder Dense layers) and compare reconstruction/MSE.

### Exp 7: Variational Autoencoder (VAE)
**Goal:** VAE on a given dataset.
- **Modifications:**
  - Use PyTorch or Keras to build a simple VAE (Encoder with mean/log-variance outputs, reparameterization trick, Decoder).
  - Train on MNIST to reconstruct digits and generate new ones.

### Exp 8: GAN and Diffusion
**Goal:** GAN and diffusion model by adding random noise.
- **Modifications:**
  - **Variation 1 (GAN):** Keep the simplified PyTorch GAN implementation on MNIST.
  - **Variation 2 (Diffusion):** Implement a simple script demonstrating the forward diffusion process (adding Gaussian noise to an MNIST image over $T$ timesteps) and a basic UNet/Autoencoder attempting to denoise a noisy image.

## Verification Plan
- **Execution**: I will execute the updated Python code for all 8 experiments to ensure they run without syntax errors and produce the expected outputs (e.g., convergence for gates, shape matching for CNNs, falling loss for Autoencoders).
- **Format**: Ensure no markdown or comments are injected into the final notebooks and that standard Python variables and library functions are utilized elegantly.
