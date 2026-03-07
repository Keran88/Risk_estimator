# UAV GPS Spoofing Simulation and Data Preparation

This repository contains a **data preprocessing module** used in research on **GPS spoofing detection in Unmanned Aerial Vehicles (UAVs)**.

The script loads UAV flight logs, injects simulated GPS spoofing into the telemetry data, and prepares the processed data for downstream analysis and machine learning experiments.

This code is **not a complete detection system**, but rather a **data preparation component** used within a larger research framework.

The **feature extraction implementation used in the experiments is intentionally not included** in this public repository.
The released code focuses on the **spoofing simulation and data processing pipeline** used to generate datasets for experimentation.

---

# Overview
To study and evaluate spoofing detection techniques, this script performs the following tasks:

1. Load UAV flight logs from CSV files
2. Identify relevant telemetry columns (GPS coordinates, velocity, timestamps)
3. Clean and preprocess the telemetry data
4. Inject simulated GPS spoofing attacks into the trajectory
5. Generate labeled datasets indicating spoofed segments *(optional, used for evaluation)*

The processed data can then be used for:

* anomaly detection models
* sensor consistency analysis
* machine learning experiments
* cybersecurity research on UAV navigation systems

---

# Configuration Parameters

Several parameters control how the script processes the dataset and injects spoofing.

| Parameter          | Description                              |
| ------------------ | ---------------------------------------- |
| `N_FLIGHTS`        | Number of flight logs to process         |
| `MIN_LEN`          | Minimum length required for a flight log |
| `SPOOF_START_FRAC` | Fraction of flight where spoofing begins |
| `SPOOF_END_FRAC`   | Fraction of flight where spoofing ends   |
| `SPOOF_DRIFT`      | Magnitude of injected GPS drift          |
| `SPEED_BIAS`       | Speed scaling applied during spoofing    |

These parameters allow researchers to simulate different spoofing scenarios and evaluate detection algorithms under controlled conditions.

---

# Dependencies

The script relies on the following Python libraries:

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

The script is designed to run in **Google Colab**, with UAV flight logs stored in **Google Drive**.

Typical workflow:

1. Upload the UAV flight log dataset to Google Drive
2. Mount Google Drive in the Colab environment
3. Set the dataset directory path
4. Run the preprocessing script

The script will automatically search for flight logs matching:

```
**/FLY*.csv
```

and process the selected files.

---

# Limitations

The spoofing model implemented in this repository is simplified and intended for experimental research purposes.

Current limitations include:

* Only GPS coordinates are manipulated
* Other onboard sensors are assumed to remain unaffected
* Environmental effects such as multipath interference are not modeled

Future work may incorporate more realistic spoofing scenarios and additional sensor models.

---

# Research Context

This code is part of ongoing research in the areas of:

* UAV cybersecurity
* GNSS spoofing detection
* sensor consistency analysis
* machine learning for anomaly detection

The preprocessing pipeline prepares telemetry data for experiments designed to evaluate spoofing detection methods.

---

# License

This repository is intended for **research and academic use only**.
