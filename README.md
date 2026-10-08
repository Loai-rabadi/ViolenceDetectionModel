# Violence Detection with YOLOv8

A notebook-based project that evaluates a YOLOv8 model for detecting violence and non-violence. The repository includes the main evaluation notebook, validation visualizations, and the model weights.

## Repository contents

- `ViolenceDetectionModel.ipynb` — main evaluation notebook
- `yolo_small_weights.pt` — trained YOLOv8 model weights (~22 MB)
- `runs/detect/val/` — validation plots and sample predictions
- `requirements.txt` — Python dependencies
- `Fight-Violence-detection-yolov8/README.md` — upstream model/dataset notes

## Setup

Use Python 3.9 or newer, then install dependencies:

```bash
python -m pip install -r requirements.txt
```

Open `ViolenceDetectionModel.ipynb` in Jupyter or Google Colab. Place `yolo_small_weights.pt` in the notebook's working directory, or update the model path in the notebook.

## Roboflow dataset access

The notebook downloads the validation dataset from Roboflow. Create an API key in your Roboflow account and set it as an environment variable; do not paste API keys into notebooks or commit them to GitHub.

Linux/macOS:

```bash
export ROBOFLOW_API_KEY="your-key"
```

Windows PowerShell:

```powershell
$env:ROBOFLOW_API_KEY="your-key"
```

Restart the notebook kernel after setting the variable, then run the cells in order. Dataset access may require permission from the Roboflow workspace owner.

## Reported evaluation

The notebook records these results for the evaluated model and validation split:

| Metric | Overall | Violence | Non-violence |
|---|---:|---:|---:|
| Precision | 0.847 | 0.972 | 0.721 |
| Recall | 0.714 | 0.582 | 0.847 |
| mAP@0.5 | 0.807 | 0.783 | 0.830 |
| mAP@0.5:0.95 | 0.537 | 0.550 | 0.523 |

These are results on the notebook's validation data, not a guarantee of real-world performance. In particular, the violence class has lower recall, so some violent events may be missed. This model should not be treated as a substitute for human review or emergency response.

## Model and dataset attribution

The project notebook references the Roboflow project `east-west-uniersy/violance-nonviolance` and the upstream repository [Musawer1214/Fight-Violence-detection-yolov8](https://github.com/Musawer1214/Fight-Violence-detection-yolov8). Review their licenses and dataset terms before redistributing the weights or dataset.

The notebook also links to the model project on [Hugging Face](https://huggingface.co/Musawer14/fight_detection_yolov8).
