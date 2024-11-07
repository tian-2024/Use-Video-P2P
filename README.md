# Guide of Video-P2P

video p2p: https://github.com/dvlab-research/Video-P2P

> The video p2p project uses old version of diffusers (0.11.1, latest version is 0.31.0).
> 
> It's hard to change the version because its dependencies on tuna-a-video library, which is use old version and build a UNet3D model from local file, which is not easy to change.
> 
> So I just  use the version of original code.

# step 1: Use New requirements.txt

The new requirements.txt will help avoid many troubles.

```
torch==1.13.1
torchvision==0.14.1
diffusers[torch]==0.11.1
xformers==0.0.16
huggingface-hub==0.25.2
transformers>=4.25.1
bitsandbytes==0.35.4
decord==0.6.0
numpy==1.26.4
accelerate
tensorboard
modelcards
omegaconf
einops
imageio
ftfy
opencv-python
ipywidgets
triton
```

# step2: download model

go to the directory.

```
huggingface-cli download --resume-download stable-diffusion-v1-5/stable-diffusion-v1-5 --local-dir ./stable-diffusion-v1-5 --local-dir-use-symlinks False
```


## step3: specify the gpu

```
import os
os.environ['CUDA_VISIBLE_DEVICES'] = str(7)
```

Then the tuning will cost about 5 minutes, which is same as the original paper.