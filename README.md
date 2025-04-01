# Diffusion Model

As part of the IS 693R course at BYU, this last project before the final aimed to teach about diffusion models, what their purpose is, how they differ from transformers, and how to build them. For this project and to that end, [this Hugging Face tutorial](https://huggingface.co/learn/diffusion-course/en/unit1/3) was used, and for topical knowledge, [this Medium article](https://medium.com/@roelljr/the-ultimate-guide-rnns-vs-transformers-vs-diffusion-models-5e841a8184f3) was quite insightful.

In the Hugging Face tutorial, we use a diffusion model called a [U-Net](https://medium.com/analytics-vidhya/what-is-unet-157314c87634), which is a popular choice for segmentation tasks. It has a **constricting path**, an **expanding path**, and **skip connections** to process the data and make sure the output is the same size as the input. [Here](https://www.youtube.com/watch?v=wnuWqG18FVU) is a helpful short video to explain, and below is a diagram of the model.

![An overview of the U-Net model architecture.](https://lmb.informatik.uni-freiburg.de/people/ronneber/u-net/u-net-architecture.png "U-Net Architecture")

After creating our own U-Net model from scratch in the first part of the tutorial, we move on to using Hugging Face's models to go a bit more in depth, specifically using `UNet2DModel`, which is based off of the [DDPM](https://arxiv.org/abs/2206.00364) paper.
