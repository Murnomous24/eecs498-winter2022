# Mini-Project

- [General Instructions](#general-instructions)
  - [Proposing your own project](#proposing-your-own-project)
- [Image Classification](#image-classification)
  - [Deliverables](#deliverables)
- [Single-Image Super-Resolution](#single-image-super-resolution)
  - [Deliverables](#deliverables-1)
- [Novel View Synthesis with NeRF](#novel-view-synthesis-with-nerf)
  - [Deliverables](#deliverables-2)

## General Instructions

The goal of the mini-project is for you to implement an entire deep learning pipeline yourself: data loading, model design, training, evaluation, and analysis.

Rather than writing a paper about your work, you will turn in a Colab / Jupyter notebook that interleaves written explanations of your project with runnable source code and results, similar in structure to the homework assignments. Also as with homework assignments, you must run all cells in your notebook to receive credit – we will not rerun your notebook.

We expect that the written text and figures in your notebook will be similar in length to a 3-4 page paper, but there are no strict requirements on length.

You should structure your code similar to the homework assignments, where the vast majority of your implementation is in .py files and the notebook only contains minimal driver code that calls into functions implemented in .py files.

Your notebook should include the following sections:

- **Introduction**: Describe the problem you are trying to solve, why it is important or useful, and summarize any important pieces of prior work that you are building upon.
- **Dataset**: Describe the dataset or datasets you are working with. Show examples from the datasets. If you collected or constructed your own dataset, explain the process you used to collect the images and labels, and why you made the choices you did in the data collection process.
- **Method**: Describe the method you are using; this may also contain parts of the implementation of your model, loss function, or other components along with sanity checks to ensure that those components are correctly implemented, similar to the homework.
- **Experiments**: Describe the experiments you did, and key results that we requested for each project. This may interleave explanations of the experiments you run, code for running those experiments, and figures you generate as a result of those experiments.
- **Conclusion / Future work**: What did you learn in doing this project? What are the shortcomings or failure cases of your work? If you had more time or resources, how would you continue or expand upon the work you have already done?

You should turn in a .zip file containing both your final notebook, along with all code you implemented. Your zip file should not include your training dataset; that would make the file too big!

### Open Source Code

While there are many open source implementations for the problems described below, you should not use them for your implementation. You may refer to existing open-source implementations if you are confused about a specific detail, but you should neither import from nor copy code directly from existing implementations. Your implementation should only use standard libraries for scientific computing in python (numpy, scipy, matplotlib), pytorch, torchvision, and libraries specifically mentioned in the descriptions for each project. If you have questions about whether you should or should not use an existing library, please ask about it on Piazza.

### Proposing your own project

We have prepared descriptions of several suggested projects for you. These are meant to be general guidelines; you don’t have to implement every single idea that we mention in these descriptions.

If you would like to pursue a project of your own design, you should submit to us a written project proposal of roughly 1-2 pages that answers the following questions:

- What goal or task are you trying to accomplish?
- What are they key pieces of prior work that you will be following? This could be one or several papers that you plan to reimplement or build upon.
- What data will you use for training and evaluation? If you are collecting your own dataset, where will it come from? Be concrete and specific.
- What computational resources will you use? Will you use Colab, or do you have additional computational resources available to you?
- How will you evaluate your results? What datasets or evaluation metrics will you use? How will you know if your model is working?
- What are the key deliverables you plan to achieve? This should be a specific result, metric, or plot that you see as the primary outcome of your project. You will be evaluated on whether or not you actually achieve this goal.

If you are proposing your own project, you should submit a project proposal by **Friday April 1, 2022**.
Please make a private post on Piazza with the `project-proposal` tag to submit your proposal.
Project proposals will not be graded, but we need to approve your proposed project to ensure that it will be feasible.

## Image Classification

In this course we have talked about a wide variety of tasks, models, and techniques. While it is exciting to learn about the latest models and ideas from cutting-edge academic research, these ideas are not very representative of the way that computer vision is often applied in practice. Academic research tends to focus on novel technical approaches, and typically shows results on standard benchmark datasets in order to provide fair comparisons with prior work.

Real-world deployments of computer vision often change both of these assumptions: they tend to use simple “tried-and-true” ideas rather than complex state-of-the-art models; and they tend to use custom datasets catering to the problem at hand. In many real-world applications of computer vision, the task of building and curating datasets for training and evaluation takes much more time and effort than actually building the models.

Of all the ideas we have discussed in the class, the most practically useful is image classification by transfer learning from a pretrained model. If you end up applying computer vision in your work in the future, this is likely to be the technique you will use. In this project you will build an image classification system as you might if faced with this problem in practice. You will collect your own image classification dataset, divide it into splits (train / val / test), and train classification models by transfer learning from networks pretrained on ImageNet. You will explore several options and hyperparameters, and analyze the performance of your trained networks.

### Papers to read

These are two of the earliest papers on transfer learning from deep convolutional networks, and should give some useful background on the problem:

- Donahue et al, “DeCAF: A Deep Convolutional Activation Feature for Generic Visual Recognition”, ICML 2014. [arXiv link](../papers/1310.1531_DeCAF.pdf)
- Razavian et al, “CNN Features off-the-shelf: an Astounding Baseline for Recognition”, CVPR Workshops 2014. [arXiv link](../papers/1403.6382_CNN_Features_Off_The_Shelf.pdf)

When analyzing a trained classification model, an attribution method attempts to determine which portion of an input image was responsible for a model’s decision. A few papers in this area to read are:

- Simonyan et al, “Deep Inside Convolutional Networks: Visualising Image Classification Models and Saliency Maps”, ICLR Workshop 2014. [arXiv link](../papers/1312.6034_Deep_Inside_Convolutional_Networks.pdf)
- Selvaraju et al, “Grad-CAM: Visual Explanations from Deep Networks via Gradient-based Localization”, IJCV 2019. [arXiv link](../papers/1610.02391_Grad_CAM.pdf)
- Fong et al, “Understanding Deep Networks via Extremal Perturbations and Smooth Masks”, ICCV 2019. [arXiv link](../papers/1910.08485_Extremal_Perturbations.pdf)

### Build an Image Classification Dataset

Your first task in this project is to collect your own image classification dataset for a classification task of your choice.

You should first define a set of two or more categories into which you want to classify images. These can be coarse categories (e.g. dog/cat/fish, hotdog/not-hotdog) or fine-grained categories (e.g. Ragdoll cat/British Shorthair cat). You should get creative in the categories that you choose! You should decide whether your categories are mutually exclusive (an image will have exactly one correct label) or non-exclusive (an image may have zero or more correct category labels). Mutually-exclusive categories are simpler to handle and analyze, so we suggest that you try to come up with a set of mutually exclusive categories.

Once you decide on a set of categories, you need to build a dataset by collecting images and labeling them. Larger datasets are likely to yield better results, but your dataset should have at least 100 images per category. You should get creative in the source of your images: you can take photos yourself, find images from the internet, or think of some other image source. However your images should not come from an existing computer vision dataset; we want you to go through the process of building your own dataset.

After you collect and label your dataset, you should split it into train / val / test splits. A good rule of thumb for splitting datasets is allocating 70% of your data to train, 10% to val, and 20% to test.

We expect that the process of building and labeling the dataset will be a large fraction of the work for this project.

Your notebook should include a section that describes your classification task and your dataset. You should explain what classification task you are trying to solve, why it could be useful, and what the categories are. You should describe your process for collecting images and labeling them, and discuss any challenges you faced in constructing your dataset. Finally, you should show examples from your dataset to give a sense for the types of images it contains.

Train an image classifier
Once you have collected a dataset, it is time to train several models on this dataset. Rather than implementing standard convolutional network architectures yourself, you should use torchvision which provides [a wide variety of commonly used models](https://pytorch.org/vision/stable/models.html#classification). You are encouraged to compare multiple architectures, but as a first step we recommend using ResNet18, ResNet50, or a small RegNet model (e.g. RegNetY-400MF).

You can consider three different ways of training a classifier:

- **Train from scratch**: Randomly initialize the model and train from scratch on your training set.
- **Feature extraction**: Initialize the model using weights pretrained on ImageNet; extract features from the model and train a linear model on top of extracted features. This can be implemented in several ways: you can use PyTorch to add a new layer onto the model, freeze all but the last layer, and train in PyTorch; you could also extract features from the model and save them in some format, then train a linear classifier with another package such as scikit-learn.
- **Fine-Tuning**: Initialize the model using weights pretrained on ImageNet; fine-tune the entire model on your training set. This should perform at least as well as feature extraction.

You may need to experiment with different optimizers, learning rates, L2 regularization strengths, and data augmentation strategies. You should train at least 6 different models, and report their accuracy on both the train and val sets.

You should show training curves for your models. You should plot the training loss per iteration, as well as the accuracy of the model on the train and val sets every epoch (pass through the training data).

You can try using test-time augmentation or model ensembling to improve upon the classification performance of your individual models.

Your notebook should explain the models you chose, explain any experiments you performed, and show the results described above.

### Analyze your models

After you have trained your models, you should analyze them to try and gain insight into how well they are working and where they make mistakes. You should analyze at least two different models: your best-performing model and at least one other of your choice.

You should show the following:

- **Qualitative examples** of images that were both correctly classified and incorrectly classified. You can show both images hand-picked by you to showcase interesting features of your model, and randomly-chosen images to give a better sense of the average performance of your model.
- **Confusion matrices**: A 2D matrix of predicted category vs ground-truth category, where each entry shows the fraction of val-set images falling into this situation; this demonstrates the kinds of mistakes that your model makes.
- **Attribution methods**: Use one or more attribution methods to give examples of what portions of images are used by the model for classification decisions.

Your notebook should include sections that describe and show each of the above methods of analysis, as well as any other type of analysis you perform.

### Run on the test set

After all your analysis, you should run your best-performing model on the test set. If your model performs very differently on the val and test sets then you should attempt to explain why that might be the case.

### Deliverables

To summarize, in this project we expect you to:

- Create your own image classification dataset with at least 100 images per category. In your notebook, discuss the classification problem you chose to solve, and how you went about collecting the dataset. Show example images from the dataset.
- Train at least 6 different image classification models on your dataset; in your notebook, show training curves for each model (training loss, train and val accuracy during training). You should also include a table that summarizes the final train and val accuracies of all your models. You can be creative in exactly what models you choose to train; but you must include at least one transfer learning result (feature extraction or finetuning from a model pretrained on ImageNet) and at least one result where you train the same CNN architecture from scratch on your dataset.
- In your notebook, analyze at least two of your trained models by showing qualitative examples, confusion matrices, and results from at least one attribution method on several images.

## Single-Image Super-Resolution

In the task of single-image super-resolution, a network receives as input a low-resolution image and it produces as output a higher-resolution version of the image. This is in general an underspecified problem – there are many possible high-resolution images that could correspond to the same low-resolution image. However, by training on datasets of corresponding high- and low-resolution images, a neural network can learn priors about the visual world that let it predict a plausible high-resolution output for any low-resolution input.

Similar to semantic segmentation, we can use a fully convolutional network to build a model for single-image super-resolution. The input to the model is a low-resolution image of shape 3 x H x W; the image goes through a series of convolution layers and upsampling layers (nearest-neighbor or bilinear upsampling, or transpose convolution) and eventually outputs a high-resolution output of shape 3 x fH x fW where f is the super-resolution factor; typically we have f=2, f=3, or f=4. During training the network output is compared with the true ground-truth output using an L2, L1, or some other loss function.

Your goal in this project is to implement and train a convolutional network for single-image super-resolution. You should train models for at least two super-resolution factors (f=2 and one other of your choice).

### Papers to read

- **SRCNN**: Dong et al, “Image super-resolution using deep convolutional networks”, TPAMI 2015. [arXiv link](../papers/1501.00092_SRCNN.pdf)
- **FSRCNN**: Dong et al, “Accelerating the super-resolution convolutional neural network”, ECCV 2016. [arXiv link](../papers/1608.00367_FSRCNN.pdf)
- **SRGAN**: Ledig et al, “Photo-Realistic Single Image Super-Resolution using a Generative Adversarial Network”, CVPR 2017. [arXiv link](../papers/1609.04802_SRGAN.pdf)

### Data

You can train your model on any image dataset that you choose; the ImageNet or COCO datasets are popular choices. Super-resolution generally does not need very large datasets for training; for example FSRCNN trains on a dataset of 100 images called General100 (available here http://mmlab.ie.cuhk.edu.hk/projects/FSRCNN.html); you might find this dataset useful for your own implementation as well. See Section 4.1 of the FSRCNN paper for more details on how to prepare your training dataset.

You should evaluate your model on the Set5 and Set14 datasets. During evaluation, the precise way that you prepare the low-resolution and high-resolution images is important; for this reason you should use the versions of the Set5 and Set14 dataset from [this GitHub repository by Jia-Bin Huang](https://github.com/jbhuang0604/SelfExSR/tree/master/data). Note that there are different versions of the datasets for each super-resolution factor.

### Model

You should implement a model similar to SRCNN or FSRCNN; follow the details in the papers as closely as you can.

As an optional extension, you may also consider using a generative adversarial network for super-resolution as described in the SRGAN paper. Training the model adversarially against a learned discriminator can produce images of higher perceptual quality, but with slightly lower PSNR or SSIM compared with a model trained using L2 or L1 losses alone.

Your notebook should include a section that describes your model architecture, training losses, and any other important implementation details of your model. You should experiment with different optimizers, training losses, model architectures, or other variations you can think of. You should show results for at least two different model variants for each super-resolution factor you consider.

### Evaluation

You should evaluate your model both on unseen images from your training dataset, and also on the Set5 and Set14 datasets. You may optionally choose to report additional results on the BSD100 or Urban100 datasets.

You should evaluate your models using peak signal-to-noise ratio (PSNR) and structural similarity (SSIM). You can use the [implementations of these metrics from scikit-image](https://scikit-image.org/docs/stable/api/skimage.metrics.html).

You should compare your model against bilinear and bicubic upsampling; you can use [scikit-image for this](https://scikit-image.org/docs/dev/api/skimage.transform.html#skimage.transform.resize). Your best model should outperform both of these simple baselines for all super-resolution factors you consider.

Concretely, for super-resolution factor 2 you should achieve PSNR of at least 34 on Set5; for super-resolution factor 3 you should achieve PSNR of at least 31 on Set5; and for super-resolution factor 4 you should achieve PSNR of at least 29 on Set5.

### Color Channels

One important detail of super-resolution methods is the color channel that the model uses for training and evaluation. So far in this course all images have been represented using the standard RGB color space; however there are other color spaces that are commonly used to represent images. One important color space is YCbCr. In this color space, Y is a grayscale color channel (luma) and Cb and Cr are two channels giving the color of the image (chroma). You can convert between RGB and YCbCr [using functions from scikit-image](https://scikit-image.org/docs/dev/api/skimage.color.html#skimage.color.rgb2ycbcr).

For single-image super-resolution, a common setup is to transform the image from RGB to YCbCr color space; the neural network receives the low-resolution Y channel and predicts a high-resolution Y channel, while the Cb and Cr channels are upsampled using bicubic interpolation. The training loss compares the predicted and ground-truth Y channels, and during evaluation we compute PSNR and SSIM between the predicted and ground-truth Y channels. You should follow this convention in your implementation.
It is also possible to train super-resolution models using color inputs and outputs; see Section 4.5 of the SRCNN paper for more details. You may optionally perform additional experiments on additional color channels.

### Deliverables

To summarize, in this project we expect you to:

- Implement models for single-image super-resolution.
  You should train models for at least two different super-resolution factors (2x, 3x, or 4x). For each model you should show training curves (loss on the train set, and PSNR on a held-out val set over the course of training). For each model you should report performance on the Set5 and Set14 datasets using PSNR and SSIM.
- You should compare against bilinear and bicubic upsampling, and your model should outperform these baselines.
- For super-resolution factors 2x / 3x / 4x, you should achieve PSNR on Set5 of at least 34 / 31 / 29.
- You should show qualitative results: show the low-resolution image, ground-truth high-resolution image, and predicted high-resolution image from each method you consider (your models and bilinear / bicubic) for several examples from a held-out val set, as well as for each image in Set5.

## Novel View Synthesis with NeRF

In the task of novel view synthesis, your training set consists of a set of images of a scene where you know the camera parameters (intrinsic and extrinsic) for each image. Your goal is to build a model that can synthesize images showing the scene from new viewpoints unseen in the training set.

Over the past two years, Neural Radiance Fields (NeRFs) have emerged as a simple and powerful model for this problem. NeRFs rely on the idea of volume rendering: to determine the color of a pixel, we shoot a ray originating from the camera center through the pixel and into the scene; for a set of points along the ray, we compute both the color and opacity of the 3D scene. Integrating the influence of these points gives the color of the pixel. The original NeRF paper [Mildenhall et al, ECCV 2020] proposed to train a fully-connected neural network that inputs (x, y, z) and a viewing direction, and outputs the RGB color and opacity of the 3D scene at that point. This network is trained to reproduce the pixel values of the training images; during inference, the network can be used to synthesize the color of pixels in novel views unseen during training.

The goal of this project is to implement a NeRF model and reproduce some of the main results from the original NeRF paper. You may optionally also incorporate ideas from some followup papers.

Note that this project is likely to involve a more complex implementation than the other two suggested projects. It is also intended to be somewhat open-ended; while the goal is to re-implement NeRF, you can be creative in exactly what results you show, and how you deviate from the original NeRF paper.

### Papers to read

- Mildenhall et al, “NeRF: Representing Scenes as Neural Radiance Fields for View Synthesis”, ECCV 2020. [arXiv link](../papers/2003.08934_NeRF.pdf)
- Barron et al, “Mip-NeRF: A Multiscale Representation for Anti-Aliasing Neural Radiance Fields”, ICCV 2021. [arXiv link](../papers/2103.13415_Mip_NeRF.pdf)

### Model

You should re-implement the model from the original NeRF paper. Their model takes roughly 1-2 days to converge on a single V100 GPU, so an exact re-implementation is likely not feasible given the computational resources available to you on Colab. You might consider the following simplifications or modifications to the original NeRF model that could allow for faster training at the expense of worse results:

- **Smaller MLP**: The paper uses an 8-layer MLP with 256 hidden units per layer (See Appendix A). Using a shallower or narrower model may allow for faster convergence.
- **No hierarchical sampling**: As discussed in Section 5.2, NeRF trains separate coarse and fine models. They first sample points uniformly along rays using stratified sampling and evaluate the coarse model at these points; the predicted densities are then used to sample a second set of points in regions of high density to be evaluated by the fine model. To simplify and speed up your implementation, you might use only a coarse model.
- **Fewer samples per ray**: NeRF trains using 64 coarse samples and 128 fine samples for each ray; using fewer samples per ray during training may allow for faster training.
- **Shorter training schedule**: NeRF trains with a batch size of 4096 rays and trains for 100k to 300k iterations; you may be able to achieve reasonable results while training with a smaller batch size or for fewer iterations.
- **Lower resolution images**: NeRF uses fairly high-resolution images for training: 800x800 images for synthetic scenes, and 1008x756 images for real scenes. Rather than using these images at their original resolution, downsampling images during training (by a factor of 2x, 4x, or 8x) will likely allow for faster convergence.

If you are feeling ambitious, you might also incorporate ideas from Mip-NeRF into your model, or try some novel ideas of your own design. Whatever variants of models you experiment with, describe them in your notebook. You can compare runtime and convergence speed (plot test-set PSNR vs training epoch) for different model variants you implement.

### Evaluation

You should show results on at least two different scenes using the datasets from the NeRF paper, [available here](https://www.matthewtancik.com/nerf). You should evaluate your results using PSNR and SSIM on test-set images. You likely won’t be able to match the performance reported in the NeRF paper, but you should compare with them nevertheless as an upper-bound on your performance.

### Deliverables

To summarize, in this method we expect you to:

- Re-implement the method from the NeRF paper. Rather than exactly re-implementing their method, you should use some of the suggested modifications (or others of your own design) above to try and reduce the training time. You should fully describe any changes you make to the basic NeRF algorithm.
- You should show results on at least two scenes used in the NeRF paper. For each scene, you should show training curves from your model (training losses and PSNR on at least one image from a held-out val set). You should also show qualitative results from each method: show several examples of a ground-truth image and your predicted image, both from training set views and novel test-set views.
- Show at least one video result, where you generate images along a continuously moving camera path, similar to the examples [on the NeRF project page](https://www.matthewtancik.com/nerf).
