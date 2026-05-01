#  Machine Learning Module – Landmine Detection Robot

This module handles the intelligent detection of potential landmines using image-based classification and sensor-assisted validation.

---

##  Objective

To classify terrain objects as:

* **Mine**  (potential threat)
* **Normal**  (safe surface)

The ML model is designed to run on edge devices like ESP32-CAM for real-time detection.

---

##  Approach

We use a **multi-stage detection system**:

1. Sensors (metal detector, ultrasonic, IR) identify suspicious conditions
2. Camera captures image using ESP32-CAM
3. ML model classifies the object
4. Final decision triggers alert system

---

##  Dataset

The dataset consists of labeled images in two categories:

* **Mine Class**:

  * Metallic objects (buried or partially visible)
  * Suspicious shapes under soil or surface

* **Normal Class**:

  * Plain ground
  * Rocks, sand, or safe terrain

### 📸 Data Collection Strategy

* Captured using ESP32-CAM / smartphone
* Multiple lighting conditions
* Different angles and distances
* Real-world terrain simulation

###  Dataset Size (Target)

* 100–200 images per class
* Total: ~300–500 images

---

##  Model Development

The model is built using Edge Impulse Studio.

###  Pipeline:

* Input: Image (96x96 or 160x160 resolution)
* Processing: Image preprocessing
* Learning: Classification (Neural Network)

###  Training:

* Epochs: 20–50
* Optimization: Accuracy vs latency balance

---

##  Model Deployment

* Platform: ESP32-CAM
* Export Format: Arduino Library (ZIP)
* Inference: Real-time edge classification

> The trained model can be found in `model.zip` (if available).

---

##  Inference Workflow

1. Capture image from camera
2. Convert image to input signal
3. Run classification model
4. Analyze output probabilities
5. Trigger alert if "mine" probability exceeds threshold

---

##  Current Status

* Dataset collection: In progress
* Model training: Pending
* Deployment: Planned

---

##  Future Improvements

* Increase dataset size for better accuracy
* Use sensor fusion with ML predictions
* Optimize model for faster inference
* Integrate GPS for location tagging
* Enable real-time remote monitoring

---

##  Limitations

* ESP32-CAM has limited processing power
* Accuracy depends heavily on dataset quality
* Environmental conditions may affect detection

---

##  Author

Vishesh Bhardwaj
