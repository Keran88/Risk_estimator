
This repository contains a **data preprocessing module** used in research on **GPS spoofing detection in Unmanned Aerial Vehicles (UAVs)**.

The script loads UAV flight logs, injects simulated GPS spoofing into the telemetry data, and prepares the processed data for downstream analysis and machine learning experiments.

This code is **not a complete detection system**, but rather a **data preparation component** used within a larger research framework.



# Overview

UAV navigation systems rely heavily on **Global Navigation Satellite Systems (GNSS)** such as GPS. These signals are vulnerable to **spoofing attacks**, where a malicious transmitter sends fake navigation signals that mislead the UAV about its true position.

To study and evaluate spoofing detection methods, this script performs the following tasks:

1. Load UAV flight logs from CSV files
2. Identify relevant telemetry columns (GPS, velocity, timestamps)
3. Clean and preprocess the data
4. Inject simulated GPS spoofing attacks
5. Generate labeled datasets indicating spoofed segments (Optional for testing)

The processed data can then be used for:

* anomaly detection models
* sensor consistency analysis
* machine learning experiments
* cybersecurity research on UAV navigation systems

---
# Configuration Parameters

Several parameters control how the script processes data.

| Parameter          | Description                              |
| ------------------ | ---------------------------------------- |
| `N_FLIGHTS`        | Number of flight logs to process         |
| `MIN_LEN`          | Minimum length required for a flight log |
| `SPOOF_START_FRAC` | Fraction of flight where spoofing begins |
| `SPOOF_END_FRAC`   | Fraction of flight where spoofing ends   |
| `SPOOF_DRIFT`      | Magnitude of injected GPS drift          |
| `SPEED_BIAS`       | Speed scaling applied during spoofing    |


---

# Dependencies

The script uses the following Python libraries:

```
numpy
pandas
scikit-learn
scipy
matplotlib
tensorflow
```

---

# Running the Script

The script is designed to run in **Google Colab** with access to flight logs stored in Google Drive.


Limitations include:

* Only GPS coordinates are manipulated
* Other sensors are assumed to remain unaffected
* Environmental effects such as multipath interference are not modeled

---

# Research Context

This code is part of ongoing research focused on:

* UAV cybersecurity
* GNSS spoofing detection
* sensor consistency analysis
* machine learning based anomaly detection

The preprocessing pipeline prepares telemetry data for experiments evaluating detection algorithms.

---

# License

This repository is intended for research and academic use only.
