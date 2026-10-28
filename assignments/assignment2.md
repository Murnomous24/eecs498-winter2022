# Assignment 2

In this assignment, you will implement various image classification models, based on the SVM / Softmax / Two-layer Neural Network. The goals of this assignment are as follows:

- Implement and apply a Multiclass Support Vector Machine (SVM) classifier
- Implement and apply a Softmax classifier
- Implement and apply a Two-layer Neural Network classifier
- Understand the differences and tradeoffs between these classifiers
- Understand how a Two-layer Neural Network can approximate an arbitrary function
- Practice implementing vectorized gradient code by checking against naive implementations, and using numeric gradient checking

This assignment is due on **Friday, January 28th at 11:59pm EDT**.

## Q1: Linear Classifiers (57 points)

The notebook **linear\_classifier.ipynb** will walk you through implmenting SVM and Softmax classifier. You are required to write code on **linear\_classifier.py**.

## Q2: Two-layer Neural Network (38 points)

The notebook **two\_layer\_net.ipynb** will walk you through implementing a two-layer neural network-based classifier. Your implementation will go to **two\_layer\_net.py**.

## Q3: MNIST Challenge (5 points)

The notebook **challenge\_problem.ipynb** will walk you through the challenge problem where you will manually set the weights of a Two-layer Neural Network classifier and evaluate on MNIST hand drawn digits.

## Steps

### 1. Use the local starter code

The local starter code is in `A2/`. Set up the `eecs498` environment using the [README](<../README.md#local-assignment-environment>).

- [Original starter code (reference)](https://web.archive.org/web/20260616092844id_/https://web.eecs.umich.edu/~justincj/teaching/eecs498/WI2022/assignments/A2.zip)

### 2. Open the local notebooks

Open the `*.ipynb` files in `A2/` with Jupyter or VS Code and select the
**Python (eecs498)** kernel. Run the local GPU and path setup cells first.
The notebooks locate `A2/` automatically, use the local NVIDIA GPU,
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

Once you have completed a notebook, download the completed `uniqueid_umid_A2.zip` file, which is generated from your last cell of the `challenge_problem.ipynb` file. Before executing the last cell in `challenge_problem`, please manually save your results so that the zip file includes all updates.

**Make sure your downloaded zip file includes your most up-to-date edits**; the zip file should include *linear\_classifier.ipynb*, *two\_layer\_net.ipynb*,*challenge\_problem.ipynb*, *linear\_classifier.py*, *two\_layer\_net.py*, *svm\_best\_model.pt*, *softmax\_best\_model.pt*, *nn\_best\_model.pt*, *hand\_drawn\_weights.jpeg* for this assignment.

### 6. Submit your python and ipython notebook files to Autograder

When you are done, [please upload your work to Autograder (UMich enrolled students only)](https://autograder.io/). Your `*.ipynb` files *SHOULD include* all the outputs. Please check your outputs up to date before submitting yours to Autograder.
