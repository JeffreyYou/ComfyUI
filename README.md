# ConfyUI Workflow Setup

## Table of Contents
- [ConfyUI](#confyui)
  - [1. Virtual Env](#1-virtual-env)
  - [2. Pytorch (NVIDIA)](#2-pytorch-nvidia)
  - [3. Dependency Setup](#3-dependency-setup)
  - [4. Git Upstream (Optional)](#4-git-upstream-optional)
- [ConfyUI-Manager](#confyui-manager)
- [Run ConfyUI](#run-confyui)

## ConfyUI
### 1. Virtual Env
Setup virtual env using uv
```
uv venv --python 3.12
```
Verify venv is installed and activated
```
.\.venv\Scripts\Activate.ps1
python -c "import sys; print(sys.executable)"
# ...\ComfyUI\.venv\Scripts\python.exe
```
Upgrade pip
```
python -m pip install --upgrade pip
```

### 2. Pytorch (NVIDIA)
Install stable pytorch:
```
pip install torch torchvision torchaudio --extra-index-url https://download.pytorch.org/whl/cu130
```

Install pytorch nightly instead (recommended)
```
pip install --pre torch torchvision torchaudio --index-url https://download.pytorch.org/whl/nightly/cu130
```

Check pytorch version
```
pip show torch
# Name: torch
# Version: 2.11.0.dev20260209+cu130
# Summary: Tensors and Dynamic neural networks in Python with strong GPU acceleration
# Home-page: https://pytorch.org
# Author:
# Author-email: PyTorch Team <packages@pytorch.org>
# License: BSD-3-Clause
# Location: C:\Users\Jeffrey\AppData\Local\Programs\Python\Python313\Lib\site-packages
# Requires: filelock, fsspec, jinja2, networkx, setuptools, sympy, typing-extensions
# Required-by: torchvision
```

Uninstall pytorch
```
python -m pip uninstall torch
```

### 3. Dependency Setup

```
python -m pip install -r requirements.txt
```

### 4. Git Upstream (Optional)
```
git remote add upstream git@github.com:Comfy-Org/ComfyUI.git
git remote -v
git show remote
```

## ConfyUI-Manager
**ComfyUI-Manager** is an extension that allows you to easily install, update, and manage custom nodes for ComfyUI.

Install the manager dependencies:
```
python -m pip install -r manager_requirements.txt
```

Enable the manager with the --enable-manager flag when running ComfyUI:
```
python main.py --enable-manager
```

## Run ConfyUI
```
python main.py
```