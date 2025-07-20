# Real-Time Eye State Detection with Pygame and TensorFlow Lite

This project implements a real-time eye state detection system (e.g., Open vs. Closed) using a webcam feed, TensorFlow Lite for inference, and Pygame for display. It can be used for applications like drowsiness detection or attention monitoring.

## 🚀 Features

- Real-time video capture with Pygame
- Eye state classification (Open/Closed) using a TensorFlow Lite model
- CPU acceleration with XNNPACK delegate
- Lightweight and cross-platform
- Terminal-based output with predictions
- Visual feedback via Pygame window

## 💾 Demo

```
Left Eye Prediction: 0.2231 → Open  
Right Eye Prediction: 0.2327 → Open  
...
```

## 🧠 Model

The app uses a TensorFlow Lite model trained to classify eye states. The model should:
- Accept an eye crop as input (normalized and resized)
- Output a probability score (e.g., > 0.5 means "Open")

## 📦 Requirements

- Python 3.10+
- TensorFlow Lite Runtime
- Pygame
- OpenCV (for camera and preprocessing)
- NumPy

Install dependencies:

```bash
pip install pygame opencv-python numpy tflite-runtime
```

> Note: On macOS with Apple Silicon (M1/M2/M3), some dependencies may need special installation steps. Use `miniforge` or `conda` if needed.


```

## ▶️ Usage

```bash
python main.py
```

Instructions will appear in the terminal. Press `q` to quit.

## ⚠️ Known Warnings

You may see some non-critical log messages:

- `Feedback manager requires a model with a single signature inference.`  
  → Safe to ignore unless using feedback tensors.

- `Using NORM_RECT without IMAGE_DIMENSIONS...`  
  → Consider using square ROI or supplying image dimensions.

## 🛠️ Customization

- Adjust the eye state threshold if predictions are consistently off:
  ```python
  state = "Open" if prediction > 0.2 else "Closed"
  ```

- Modify the Pygame window to display text, overlays, or alert sounds.

## 🧪 TODO

- Add audio alert on eye closure
- Save logs or trigger events based on drowsiness
- Optimize performance for mobile or edge devices

## 📜 License

MIT License. Feel free to modify or use in your own projects.

---

### 🙌 Acknowledgments

- [TensorFlow Lite](https://www.tensorflow.org/lite)
- [Pygame](https://www.pygame.org/)
- [OpenCV](https://opencv.org/)
