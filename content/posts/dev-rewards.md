---
title: dev-rewards
date: 2024-03-12T12:19:03+08:00
draft: False
featuredImage: https://images.unsplash.com/photo-1709761402478-52114c2df7b4?ixid=M3w0NjAwMjJ8MHwxfHJhbmRvbXx8fHx8fHx8fDE3MTAyMTcwNDV8&ixlib=rb-4.0.3
featuredImagePreview: https://images.unsplash.com/photo-1709761402478-52114c2df7b4?ixid=M3w0NjAwMjJ8MHwxfHJhbmRvbXx8fHx8fHx8fDE3MTAyMTcwNDV8&ixlib=rb-4.0.3
---

# [fluencelabs/dev-rewards](https://github.com/fluencelabs/dev-rewards)

# Fluence Developer Rewards

# Generate proof (docker)

1. Build docker image

   > `docker build -t dev-reward-script .`

2. If your ssh keys are in ~/.ssh, run the script:

   > `docker run -it --rm --network none -v ~/.ssh:/root/.ssh:ro dev-reward-script`

   If your ssh keys are in other directories, replace
   {dir_path_for_your_ssh_keys} with your directory path:

   > `docker run -it --rm --network none -v /{dir_path_for_your_ssh_keys}:/root/.ssh:ro dev-reward-script`

# Generate proof (local sh script)

1. Install dependencies

   > `./install.sh`

2. Run the script

   > `./proof-sh/proof.sh`

# Generate proof (local python script)

1. Install python

   > https://www.python.org/downloads/

2. Install dependencies

   > `./install.sh`

   > `python3 -m venv claim-venv`

   > `source claim-venv/bin/activate`

   > `pip3 install -r python/requirements.txt`

3. Run the script

   > `python3 python/proof.py`