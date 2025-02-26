+++
disableToc = false
title = "Easy Setup - Stable Diffusion"
weight = 2
+++

To set up a Stable Diffusion model is super easy.
In your models folder make a file called ``photoai.yaml``, then edit that file with the following. (You can change ``Linaqruf/animagine-xl`` with what ever ``sd-lx`` model you would like.
```yaml
name: animagine-xl
parameters:
  model: Linaqruf/animagine-xl
backend: diffusers

# Force CPU usage - set to true for GPU
f16: false
diffusers:
  pipeline_type: StableDiffusionXLPipeline
  cuda: false # Enable for GPU usage (CUDA)
  scheduler_type: dpm_2_a
```

Then to download and setup the model, Just send in a normal ``OpenAI`` request! LocalAI will do the rest!
```bash
curl http://localhost:8080/v1/images/generations -H "Content-Type: application/json" -d '{
  "prompt": "Two Boxes, 1blue, 1red",
  "size": "256x256"
}'
```
