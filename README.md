# Diffusion Model

As part of the IS 693R course at BYU, this last project before the final aimed to teach about diffusion models, what their purpose is, how they differ from transformers, and how to build them.

## Diffusion from Scratch

For this part of the project, [this Hugging Face tutorial](https://huggingface.co/learn/diffusion-course/en/unit1/3) was used, and for topical knowledge, [this Medium article](https://medium.com/@roelljr/the-ultimate-guide-rnns-vs-transformers-vs-diffusion-models-5e841a8184f3) was quite insightful.

In the Hugging Face tutorial, we use a diffusion model called a [U-Net](https://medium.com/analytics-vidhya/what-is-unet-157314c87634), which is a popular choice for segmentation tasks. It has a **constricting path**, an **expanding path**, and **skip connections** to process the data and make sure the output is the same size as the input. [Here](https://www.youtube.com/watch?v=wnuWqG18FVU) is a helpful short video to explain, and below is a diagram of the model.

![An overview of the U-Net model architecture.](https://lmb.informatik.uni-freiburg.de/people/ronneber/u-net/u-net-architecture.png "U-Net Architecture")

After creating our own U-Net model from scratch in the first part of the tutorial, we move on to using Hugging Face's models to go a bit more in depth, specifically using `UNet2DModel`, which is based off of the [DDPM](https://arxiv.org/abs/2206.00364) paper.

## Stable Diffusion

Everything above was explored in `main.ipynb`, but below and in the `stable_diffusion.ipynb` we will explore Hugging Face's [Introduction to Stable Diffusion](https://huggingface.co/learn/diffusion-course/en/unit3/2). In this walkthrough, we use a diffusion model with a VAE (variational autoencoder), which encdes its input into a compressed representation and then decode this 'latent' representation back into something close to the original input. Below is a diagram:

![The VAE diffusion model](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRjo-w9nNguJOka5NWinqBTKZc0mkX6Yu1PzwdN_6BkWES-nfhF)

As seen in the `stable_diffusion.ipynb` file, the model we are using also has a tokenizer and text encoder, a UNet, and a scheduler. While not all of these require diagrams, here is the UNet diagram:

![The UNet model](https://encrypted-tbn1.gstatic.com/images?q=tbn:ANd9GcTtNZY-6Zvm7EPxw2V-FqUMP30HodgRbDITqqLY4OiuSb4xnEaN)

Using these components, we are able to make an image diffusion model for text-to-image generation. There are more parts to the walkthrough, including image-to-image models, inpainting, and depth-to-image, but the current implementation is sufficient for the scope of this project.