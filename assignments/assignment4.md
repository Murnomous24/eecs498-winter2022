# Assignment 4

In this assignment, you will implement two different object detection systems. The goals of this assignment are:

- Learn about a typical object detection pipeline: understand the training data format, modeling, and evaluation.
- Understand how to build two prominent detector designs: one-stage anchor-free detectors, and two-stage anchor-based detectors.

This assignment is due on **Tuesday, March 29th** at 11:59pm ET.

## Q1: One-Stage Detector

The notebook **one\_stage\_detector.ipynb** will walk you through the implementation of **FCOS: Fully-Convolutional One-Stage Object Detector** [(Tian et al, CVPR 2019)](../papers/1904.01355_FCOS_paper.pdf).
You will train and evaluate your detector on the [PASCAL VOC 2007](http://host.robots.ox.ac.uk/pascal/VOC/voc2007/index.html) object detection dataset.

## Q2: Two-Stage Detector

The notebook **two\_stage\_detector.ipynb** will walk you through the implementation of a two-stage object detector *similar* to Faster R-CNN [(Ren et al, NeurIPS 2015)](../papers/1506.01497_Faster_R-CNN_paper.pdf).
This will combine a fully-convolutional Region Proposal Network (RPN) and a second-stage recognition network.

## Steps

### 1. Use the local starter code

The local starter code is in `A4/`. Set up the `eecs498` environment using the [README](../README.md#local-assignment-environment).

- [Original starter code (reference)](https://web.archive.org/web/20260616092844id_/https://web.eecs.umich.edu/~justincj/teaching/eecs498/WI2022/assignments/A4.zip)

### 2. Open the local notebooks

Open the `*.ipynb` files in `A4/` with Jupyter or VS Code and select the
**Python (eecs498)** kernel. Run the local GPU and path setup cells first.
The notebooks locate `A4/` automatically, use the local NVIDIA GPU,
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
- **IMPORTANT: Run all cells, and do not clear out the outputs, before submitting.**
  You will only get credit for code that has been run.

### 4. Evaluate your implementation on Autograder

Once you want to evaluate your implementation,
please submit the `*.py`, `*.ipynb` and other required files to Autograder for grading your implementations in the middle or after implementing everything. You can partially grade some of the files in the middle, but please make sure that this also reduces the daily submission quota. Please check our [Autograder tutorial](https://web.eecs.umich.edu/~justincj/teaching/eecs498/WI2022/autograder.html) for details.

### 5. Download .zip file

Once you have completed a notebook, download the completed `uniqueid_umid_A4.zip` file, which is generated from your last cell of the `two_stage_detector.ipynb` file. Before executing the last cell in `two_stage_detector.ipynb`, please manually **run all the cells of notebook and save your results** so that the zip file includes all updates.

**Make sure your downloaded zip file includes your most up-to-date edits**; the zip file should include:

- *common.py*
- *one\_stage\_detector.py*
- *two\_stage\_detector.py*
- *one\_stage\_detector.ipynb*
- *two\_stage\_detector.ipynb*
- *fcos\_detector.pt*
- *rcnn\_detector.pt*

### 6. Submit your python and ipython notebook files to Autograder

When you are done, [please upload your work to Autograder (UMich enrolled students only)](https://autograder.io/). Your `*.ipynb` files *SHOULD include* all the outputs. Please check your outputs up to date before submitting yours to Autograder.
