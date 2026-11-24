# YOLOv7 on Windows CPU

## Installation

Use Python 3.12 and create a virtual environment:

```bash
py -3.12 -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip setuptools wheel
python -m pip install torch torchvision --index-url https://download.pytorch.org/whl/cpu
python -m pip install -r requirements.txt
```

The requirements use NumPy 1.26.4 or newer. Install the CPU-only PyTorch wheels before the project requirements.

## Usage

```bash
python detect.py --weights yolov7.pt --source inference/images/bus.jpg --device cpu
```

Download the official [`yolov7.pt` weights](https://github.com/WongKinYiu/yolov7/releases/download/v0.1/yolov7.pt) into the project root before running inference. The official checkpoint is not included; `traced_model.pt` is included as a generated trace of those weights, but this command still requires `yolov7.pt`. Results are saved under `runs/detect/`.