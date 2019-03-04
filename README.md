# Style transfer using perceptual losses

## Introduction
This project contains a notebook which explores Johnson et. al's (2016) [Perceptual Losses for Real-Time Style Transfer and Super Resolution](https://arxiv.org/abs/1603.08155) paper. Since it promises similar results as in Gatys et. al's (2015) [A Neural Algorithm of Artistic Style](https://arxiv.org/abs/1508.06576) paper in less time, I want to try it out for myself.

A closer look into this project can be found in my [blog post](http://francislata.blot.im/epoch-2-perceptual-losses).

## How to run
The Jupyter notebook called `perceptual_losses.ipynb` can be opened. Note that the following frameworks must exist in your PIP or Anaconda environment:
- PyTorch
- NumPy
- Python Imaging Library
- tqdm

## Dataset
In this project, I used [COCO dataset's 2014 training images (83K/13GB)](http://cocodataset.org). Download this dataset and update `DATASET_PATH` to the location of the dataset.

## How to train the model
After downloading the dataset, run the notebook from top to bottom. Training the dataset after two epochs takes around four hours.

## How to style any image
Find any input image and update `TEST_IMAGE_PATH` to the image's location. Note that there is already a pre-trained model. Running the following line of code:

```python
load_model_checkpoint(image_transformation_network, optimizer, "style-transfer-alpha1e5-beta1e10-epoch-2")
```

will load the pre-trained model and invoke the subsequent lines to style the input image.
