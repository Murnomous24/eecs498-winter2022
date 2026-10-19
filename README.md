# EECS498: Deep Learning for Computer Vision (Winter 2022)

## Repository Structure

| Path | Contents |
| --- | --- |
| `assignments/A1/`–`assignments/A6/` | Local GPU notebooks, starter code, and required sample inputs. |
| `assignments/assignment*.md` | Assignment instructions. |
| `assignments_colab/` | Unmodified backup of the original Colab assignments and instructions. |
| `mini-project/project.md` | Mini-project instructions. |
| `schedule.md` | Course schedule and reading materials. |
| `slides/`, `papers/` | Local reference PDFs, excluded from Git. |

## Local Assignment Environment

```bash
conda env create --file environment.yml
conda activate eecs498
python -m ipykernel install --sys-prefix --name eecs498 --display-name "Python (eecs498)"
python -m pip check
```

## Local Assignment Notebooks

Open the notebooks in `assignments/A1/`–`assignments/A6/` with Jupyter or VS Code
and select **Python (eecs498)**. Start Jupyter from the repository root or one
of its subdirectories. Run the setup cells first: they check the local NVIDIA
GPU, locate the assignment directory, and set its working directory and import
path. CUDA is required; choose a physical GPU with `CUDA_VISIBLE_DEVICES` before
starting Jupyter or its kernel if needed.
CPU examples and CPU/GPU comparison exercises keep their original device choices.

Datasets, checkpoints, generated figures, and submission archives stay in the
corresponding local assignment directory. Dataset and pretrained weight downloads
still require internet access on first use. A4 reuses its local `mAP/` checkout
and downloaded VOC data; its data loaders use up to four workers by default.
The original Colab notebooks and instructions are preserved in `assignments_colab/`.

## Assignment Progress

| Assignment | Topics | Status |
| --- | --- | --- |
| [A1](assignments/assignment1.md) | PyTorch basics and kNN | Not started |
| [A2](assignments/assignment2.md) | Linear classifiers and two-layer networks | Not started |
| [A3](assignments/assignment3.md) | Fully connected and convolutional networks | Not started |
| [A4](assignments/assignment4.md) | Object detection | Not started |
| [A5](assignments/assignment5.md) | RNNs, image captioning, and Transformers | Not started |
| [A6](assignments/assignment6.md) | VAEs, GANs, network visualization, and style transfer | Not started |

## Acknowledgments

- Course materials are from the University of Michigan's [EECS498/598: Deep Learning for Computer Vision, Winter 2022](https://web.archive.org/web/20260616092844/https://web.eecs.umich.edu/~justincj/teaching/eecs498/WI2022/schedule.html), taught by Justin Johnson.
- The A1 starter code was borrowed from [nizne9/EECS498-WI22](https://github.com/nizne9/EECS498-WI22/tree/a4712f9738dbdd8272042588c9b15f8a03b3ef82/A1).

## AI Usage

The assignment instructions, mini-project description, and course schedule were converted from HTML to Markdown using GPT 6.1 Sol. Formatting and links were adjusted while preserving the original content.

Codex copied the original `assignments/` tree to `assignments_colab/`, then adapted
the 15 notebooks in `assignments/` for local GPU execution. Changes cover kernel
selection, CUDA checks, local paths, reusable A4 dataset/evaluation setup,
A6 data-loader compatibility, and local running instructions. Exercise
implementation blocks remain unchanged.
