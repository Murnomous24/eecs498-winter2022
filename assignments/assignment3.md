# Assignment 3

In this assignment, you will implement Fully-Connected Neural Networks and Convolutional Neural Networks for image classification models. The goals of this assignment are as follows:

- Understand Neural Networks and how they are arranged in layered architectures
- Understand and be able to implement modular backpropagation
- Implement various update rules used to optimize Neural Networks
- Implement Batch Normalization for training deep networks
- Implement Dropout to regularize networks
- Understand the architecture of Convolutional Neural Networks and get practice with training these models on data

This assignment is due on **Friday, February 11 at 11:59pm ET**.

## Q1: Fully-Connected Neural Network (40 points)

The notebook **fully\_connected\_networks.ipynb** will walk you through implementing Fully-Connected Neural Networks.

## Q2: Convolutional Neural Network (60 points)

The notebook **convolutional\_networks.ipynb** will walk you through implementing Convolutional Neural Networks.

## Steps

### 1. Use the local starter code

The local starter code is in `A3/`. Set up the `eecs498` environment using the [README](../README.md#local-assignment-environment).

- [Original starter code (reference)](https://web.archive.org/web/20260616092844id_/https://web.eecs.umich.edu/~justincj/teaching/eecs498/WI2022/assignments/A3.zip)

### 2. Open the local notebooks

Open the `*.ipynb` files in `A3/` with Jupyter or VS Code and select the
**Python (eecs498)** kernel. Run the local GPU and path setup cells first.
The notebooks locate `A3/` automatically, use the local NVIDIA GPU,
and keep downloaded data and generated results in that assignment directory.

### 3. Work on the assignment

Work through the notebook, executing cells and writing code in `*.py,` as indicated.
Save both the local `*.ipynb` and `*.py` files to keep your progress.

While working on the assignment, keep the following in mind:

- The notebook and the python file have clearly marked blocks where you are expected to write code.
  **Do not write or modify any code outside of these blocks**.
- **Do not add or delete cells from the notebook**. You may add new cells to
  perform scratch computations, but you should delete them before submitting
  your work.
- **Run all cells, and do not clear out the outputs, before submitting.**
  You will only get credit for code that has been run.

### 4. Evaluate your implementation on Autograder

Once you want to evaluate your implementation,
please submit the `*.py` and `*.ipynb` files to Autograder for grading your implementations in the middle or after implementing everything. You can partially grade some of the files in the middle, but please make sure that this also reduces the daily submission quota. Please check our [Autograder tutorial](https://web.eecs.umich.edu/~justincj/teaching/eecs498/WI2022/autograder.html) for details.

### 5. Download .zip file

Once you have completed a notebook, download the completed `uniqueid_umid_A3.zip` file, which is generated from your last cell of the `convolutional_networks.ipynb` file. Before executing the last cell in `convolutional_networks.ipynb`, please manually save your results so that the zip file includes all updates.

**Make sure your downloaded zip file includes your most up-to-date edits**; the zip file should include *fully\_connected\_networks.ipynb*, *convolutional\_networks.ipynb*, *fully\_connected\_networks.py*, *convolutional\_networks.py* , *best\_overfit\_five\_layer\_net.pth*, *best\_two\_layer\_net.pth*, *one\_minute\_deepconvnet.pth*, *overfit\_deepconvnet.pth* for this assignment.

### 6. Submit your python and ipython notebook files to Autograder

When you are done, [please upload your work to Autograder (UMich enrolled students only)](https://autograder.io/). Your `*.ipynb` files *SHOULD include* all the outputs. Please check your outputs up to date before submitting yours to Autograder.
