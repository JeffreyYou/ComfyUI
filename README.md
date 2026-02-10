# ConfyUI Workflow Setup

## ConfyUI

### 1. Git Upstream
```
git remote add upstream git@github.com:Comfy-Org/ComfyUI.git
git remote -v
git show remote
```

### 2. Pytorch (NVIDIA)
Install stable pytorch:
```
pip install torch torchvision torchaudio --extra-index-url https://download.pytorch.org/whl/cu130
```

Install pytorch nightly instead
```
pip install --pre torch torchvision torchaudio --index-url https://download.pytorch.org/whl/nightly/cu130
```

Uninstall pytorch
```
pip uninstall torch
```

### 3. Dependency Setup

```
pip install -r requirements.txt
```

## ConfyUI-Manager
**ComfyUI-Manager** is an extension that allows you to easily install, update, and manage custom nodes for ComfyUI.

Install the manager dependencies:
```
pip install -r manager_requirements.txt
```

Enable the manager with the --enable-manager flag when running ComfyUI:
```
python main.py --enable-manager
```

## Run ConfyUI
```
python main.py
```