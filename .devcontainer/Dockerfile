FROM nvidia/cuda:12.1.1-cudnn8-devel-ubuntu22.04

# System deps
RUN apt-get update && apt-get install -y \
    python3-pip \
    python3-dev \
    git \
    curl \
    wget \
    ca-certificates \
    && rm -rf /var/lib/apt/lists/*

# Alias python -> python3
RUN ln -s /usr/bin/python3 /usr/bin/python

# Upgrade pip and install PyTorch (CUDA version will match base image)
RUN pip install --upgrade pip && \
    pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu121

# Create a workspace directory
WORKDIR /workspace

