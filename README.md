# EECS498: Deep Learning for Computer Vision (Winter 2022)

## Repository Structure

```text
.
├── assignments/          # Local assignments
│   ├── A1/ … A6/         # Notebooks, Python code, and sample inputs
│   └── assignment*.md    # Assignment instructions
├── assignments_colab/    # Original Colab assignments and instructions
├── mini-project/         # Mini-project instructions
├── environment.yml       # Conda environment
└── requirements.txt      # Pinned Python dependencies
```

## Local Assignments

The 15 notebooks in `assignments/` run in local Jupyter or VS Code instead of
Colab/Google Drive. They add automatic path setup, CUDA checks, and local storage
for data and outputs. A4 reuses downloaded VOC data and its mAP evaluation checkout;
A6 includes data-loader compatibility fixes. The original version is preserved in
`assignments_colab/`.

## Local Assignment Environment

Run from the repository root with Conda and an NVIDIA GPU available:

```bash
conda env create --file environment.yml
conda activate eecs498
python -m ipykernel install --sys-prefix --name eecs498 --display-name "Python (eecs498)"
jupyter lab
```

Select **Python (eecs498)** and run the notebook's setup cells first. Initial
dataset and pretrained weight downloads require internet access.

## Assignment Progress

- [ ] [A1](<assignments/assignment1.md>): PyTorch basics and kNN
- [ ] [A2](<assignments/assignment2.md>): Linear classifiers and two-layer networks
- [ ] [A3](<assignments/assignment3.md>): Fully connected and convolutional networks
- [ ] [A4](<assignments/assignment4.md>): Object detection
- [ ] [A5](<assignments/assignment5.md>): RNNs, image captioning, and Transformers
- [ ] [A6](<assignments/assignment6.md>): VAEs, GANs, network visualization, and style transfer

## Acknowledgments

- Course materials: Justin Johnson, University of Michigan, [EECS498/598 Winter 2022](https://web.archive.org/web/20260616092844/https://web.eecs.umich.edu/~justincj/teaching/eecs498/WI2022/schedule.html).
- A1 starter code: [nizne9/EECS498-WI22](https://github.com/nizne9/EECS498-WI22/tree/a4712f9738dbdd8272042588c9b15f8a03b3ef82/A1).

## AI Usage

GPT 6.1 Sol converted the assignment and mini-project instructions from HTML to
Markdown. Codex preserved the Colab originals, adapted notebooks for local GPU
execution, and edited the documentation.
