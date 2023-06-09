---
title: ProFusion
date: 2023-05-27T12:16:12+08:00
draft: False
featuredImage: https://wallpaperhub.app/api/v1/get/12189/0/1080p
featuredImagePreview: https://wallpaperhub.app/api/v1/get/12189/0/1080p
---

# [drboog/ProFusion](https://github.com/drboog/ProFusion)

# ProFusion
<br>
<div style="text-align: center;"> <img src="./imgs/examples.png" alt="examples" width="90%"> </div>
<br>

Code for [Enhancing Detail Preservation for Customized Text-to-Image Generation: A Regularization-Free Approach](https://arxiv.org/abs/2305.13579).

ProFusion is a framework for customizing pre-trained large-scale text-to-image generation models, which is [Stable Diffusion 2](https://github.com/Stability-AI/stablediffusion) in our examples.
<br>

<div style="text-align: center;"> <img src="./imgs/framework.jpg" alt="framework" width="90%"> </div>
<br>

With ProFusion, you can generate infinite number of creative images for a novel/unique concept, with single testing image, on single GPU (~20GB are needed when fine-tune with batch size 1).

<div style="text-align: center;"> <img src="./imgs/daniel.jpg" alt="framework" width="80%"> </div>
<br>

## Example


- Install dependencies (we revised original [diffusers](https://github.com/huggingface/diffusers));

        cd ./diffusers
        pip install -e .
        cd ..
        pip install accelerate==0.16.0 torchvision transformers>=4.25.1 datasets ftfy tensorboard Jinja2 regex tqdm joblib 

- Initialize [Accelerate](https://github.com/huggingface/accelerate/);

        accelerate config

- Download a model [pre-trained on FFHQ](https://drive.google.com/file/d/1n6jZXpb2nE_ptftKjSr7JZ22TsCbZHCh/view?usp=share_link);

- Customize model with a testing image, example is shown in the notebook [test.ipynb](./test.ipynb);

## Train Your Own Encoder

If you want to train a PromptNet encoder for other domains, or on your own dataset.

- First, prepare an image-only dataset; 
    - In our example, we use [FFHQ](https://github.com/NVlabs/ffhq-dataset). Our pre-processed FFHQ can be found at [google drive link](https://drive.google.com/file/d/1cObckM1omlMgG5x1z9sMGqbrgCKNkPhu/view?usp=share_link).


- Then, run
    
        accelerate launch --mixed_precision="fp16" train.py\
              --pretrained_model_name_or_path="stabilityai/stable-diffusion-2-base" \
              --train_data_dir=./images_512 \
              --max_train_steps=80000 \
              --learning_rate=2e-05 \
              --output_dir="./promptnet" \
              --train_batch_size=8 \
              --promptnet_l2_reg=0.000 \
              --gradient_checkpointing


## Citation

    @misc{zhou2023enhancing,
      title={Enhancing Detail Preservation for Customized Text-to-Image Generation: A Regularization-Free Approach}, 
      author={Yufan Zhou and Ruiyi Zhang and Tong Sun and Jinhui Xu},
      year={2023},
      eprint={2305.13579},
      archivePrefix={arXiv},
      primaryClass={cs.CV}
    }
