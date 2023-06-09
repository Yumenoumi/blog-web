---
title: gpt4all
date: 2023-04-02T12:16:20+08:00
draft: False
featuredImage: https://wallpaperhub.app/api/v1/get/11957/0/1080p
featuredImagePreview: https://wallpaperhub.app/api/v1/get/11957/0/1080p
---

# [nomic-ai/gpt4all](https://github.com/nomic-ai/gpt4all)

# gpt4all



# Setup

Clone the repo

`git clone --recurse-submodules git@github.com:nomic-ai/gpt4all.git`

Setup the environment

```
python -m pip install -r requirements.txt

cd transformers
pip install -e . 

cd ../peft
pip install -e .
```


## Generate

`python generate.py --config configs/generate/generate.yaml --prompt "Write a script to reverse a string in Python`


## Train

`accelerate launch --dynamo_backend=inductor --num_processes=8 --num_machines=1 --machine_rank=0 --deepspeed_multinode_launcher standard --mixed_precision=bf16  --use_deepspeed --deepspeed_config_file=configs/deepspeed/ds_config.json train.py --config configs/train/finetune-7b.yaml`
