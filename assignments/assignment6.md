# Assignment 6

In this assignment you will implement two different kinds of generative models:
**Variational Autoencoders (VAEs)** and **Generative Adversarial Networks (GANs)**.

The goals of this assignment are:

- Understand and implement a variational autoencoder and a conditional variational autoencoderand apply them to the MNIST dataset
- Understand and implement a generative adversarial network and apply it to the MNIST dataset
- Use image gradients to synthesize saliency maps, adversarial examples, and perform class visualizations
- Combine content and style losses to perform artistic style transfer

This assignment is due on **Tuesday, April 26th** at 11:59pm EDT.

## Q1: Variational Autoencoder

The notebook **variational\_autoencoders.ipynb** will walk you through the implementation of a VAE on the MNIST dataset.
This will allow you to generate new data, and to interpolate in the latent space.

## Q2: Generative Adversarial Networks

The notebook **generative\_adversarial\_networks.ipynb** will walk you through the implementation of fully-connected and convolutional generative adversarial networks on the MNIST dataset.

## Q3: Network Visualization

The notebook **network\_visualization.ipynb** will walk you through the use of image gradients for generating saliency maps, adversarial examples, and class visualizations.

## Q4: Style Transfer

In the notebook **style\_transfer.ipynb**, you will learn how to create images with the artistic style of one image and the content of another image.

## Steps

### 1. Download the zipped assignment file

- [Click here to download the starter code](https://web.archive.org/web/20260616092844id_/https://web.eecs.umich.edu/~justincj/teaching/eecs498/WI2022/assignments/A6.zip)

### 2. Unzip all and open the Colab file from the Drive

Once you unzip the downloaded content, please upload the folder to your Google Drive.
Then, open each `*.ipynb` notebook file with Google Colab by right-clicking the \*.ipynb file.
We recommend editing your `*.py` file on Google Colab, set the ipython notebook and the code side by side.
For more information on using Colab, please see our [Colab tutorial](https://web.eecs.umich.edu/~justincj/teaching/eecs498/WI2022/colab.html).

### 3. Work on the assignment

Work through the notebook, executing cells and writing code in `*.py,` as indicated.
You can save your work, both `*.ipynb` and `*.py,` in Google Drive (click “File” -> “Save”) and resume later if you don’t want to complete it all at once.

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
please submit the `*.py`, `*.ipynb` and other required files to Autograder for grading your implementations in the middle or after implementing everything. You can partially grade some of the files in the middle, but please make sure that this also reduces the daily submission quota. Please check our [Autograder tutorial](https://web.eecs.umich.edu/~justincj/teaching/eecs498/WI2022/autograder.html) for details.

### 5. Download .zip file

Once you have completed a notebook, download the completed `uniqueid_umid_A6.zip` file, which is generated from your last cell of the `generative_adversarial_networks.ipynb` notebook. Before executing the last cell in this notebook, please manually **run all the cells of notebook and save your results** so that the zip file includes all updates.

**Make sure your downloaded zip file includes your most up-to-date edits**; the zip file should include:

- *vae.py*
- *variational\_autoencoders.ipynb*
- *gan.py*
- *generative\_adversarial\_networks.ipynb*
- *network\_visualization.py*
- *network\_visualization.ipynb*
- *style\_transfer.py*
- *style\_transfer.ipynb*

### 6. Submit your python and ipython notebook files to Autograder

When you are done, [please upload your work to Autograder (UMich enrolled students only)](https://autograder.io/). Your `*.ipynb` files *SHOULD include* all the outputs. Please check your outputs up to date before submitting yours to Autograder.
