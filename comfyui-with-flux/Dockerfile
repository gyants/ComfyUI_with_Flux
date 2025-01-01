FROM valyriantech/comfyui-without-flux:latest

# Due to the fact that the models are in a gated repository, we need to download them separately BEFORE building this image and store them locally in a folder called flux
# https://huggingface.co/black-forest-labs/FLUX.1-dev/blob/main/ae.sft
COPY flux/ae.sft /ComfyUI/models/vae/
# https://huggingface.co/black-forest-labs/FLUX.1-dev/blob/main/flux1-dev.sft
COPY flux/flux1-dev.sft /ComfyUI/models/diffusion_models/

# Download and move clip_l.safetensors
RUN wget -O /ComfyUI/models/clip/clip_l.safetensors "https://huggingface.co/comfyanonymous/flux_text_encoders/resolve/main/clip_l.safetensors?download=true" --progress=bar:force:noscroll

# Download and move t5xxl_fp8_e4m3fn.safetensors
RUN wget -O /ComfyUI/models/clip/t5xxl_fp8_e4m3fn.safetensors "https://huggingface.co/comfyanonymous/flux_text_encoders/resolve/main/t5xxl_fp8_e4m3fn.safetensors?download=true" --progress=bar:force:noscroll

# Download LoRas
RUN wget -O /ComfyUI/models/loras/xmooning.safetensors "https://huggingface.co/Zerioud/xpunc/resolve/main/fixed_xmooning-flux-2.0.safetensors?download=true" --progress=bar:force:noscroll
RUN wget -O /ComfyUI/models/loras/manhole.safetensors "https://huggingface.co/Zerioud/xpunc/resolve/main/manhole-1.0-0000318.safetensors?download=true" --progress=bar:force:noscroll
RUN wget -O /ComfyUI/models/loras/sniffies.safetensors "https://huggingface.co/Zerioud/xpunc/resolve/main/sniffies-1.0-000285.safetensors?download=true" --progress=bar:force:noscroll
RUN wget -O /ComfyUI/models/loras/uncut.safetensors "https://huggingface.co/Zerioud/xpunc/resolve/main/xpenis-uncut-flux-11-000098.safetensors?download=true" --progress=bar:force:noscroll


CMD [ "/start.sh" ]
