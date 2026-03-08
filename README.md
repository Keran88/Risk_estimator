# UAV GPS Spoofing Simulation

This repository provides a **GPS spoofing simulation module for UAV flight logs**.
The script loads UAV telemetry data and injects simulated GPS spoofing into the recorded trajectory in order to study the effects of spoofing attacks.

The code focuses **only on spoofing simulation** and does not include the full data processing or feature extraction pipeline used in the associated research.

This repository is intended to illustrate **how spoofing scenarios are generated from real UAV flight logs** for experimentation and evaluation.

The output can be used to analyze how spoofing alters UAV trajectories or to generate datasets for further research.

---

# Spoofing Model

Spoofing is simulated by introducing **gradual drift in GPS coordinates** during a selected portion of the flight.

The spoofing interval is defined by two parameters:

* `SPOOF_START_FRAC`
* `SPOOF_END_FRAC`

These parameters represent the fraction of the flight where spoofing begins and ends.

During this interval:

1. Random drift is gradually added to the latitude and longitude values.
2. GPS displacement is modified to simulate abnormal motion.

This creates a **spoofed trajectory that slowly deviates from the original path**, mimicking realistic spoofing scenarios where the UAV is gradually pulled away from its true location.

---

# Configuration Parameters

The spoofing simulation can be controlled using the following parameters.

| Parameter          | Description                              |
| ------------------ | ---------------------------------------- |
| `N_FLIGHTS`        | Number of flight logs to process         |
| `MIN_LEN`          | Minimum length required for a flight log |
| `SPOOF_START_FRAC` | Fraction of flight where spoofing begins |
| `SPOOF_END_FRAC`   | Fraction of flight where spoofing ends   |
| `SPOOF_DRIFT`      | Magnitude of injected GPS drift          |
| `SPEED_BIAS`       | Speed scaling applied during spoofing    |

Adjusting these parameters allows researchers to simulate different spoofing conditions.

---

# Input Data

The script expects **UAV flight logs stored in CSV format**.

Example directory structure:

```
Phantom4_001_csv/
    flight1/FLY001.csv
    flight2/FLY002.csv
```

The script automatically searches for files using:

```
**/FLY*.csv
```

This allows flight logs to be located within nested folders.

---

# Dependencies

The script uses the following Python libraries:

```
numpy
pandas
scipy
scikit-learn
matplotlib
tensorflow
```

---

# Running the Script

The code is designed to run in **Google Colab** with flight logs stored in **Google Drive**.

Typical workflow:

1. Upload UAV flight logs to Google Drive
2. Mount Google Drive in the Colab environment
3. Set the dataset path in the script
4. Run the spoofing simulation

Example dataset path:

```
/content/drive/MyDrive/Phantom4_001_csv
```

---

# Limitations

The spoofing simulation implemented in this repository is simplified and intended for experimental analysis.

Limitations include:

* Only GPS coordinates are manipulated
* Other sensors are assumed to remain unaffected
* Environmental effects such as multipath interference are not simulated

Future work may incorporate more advanced spoofing scenarios and multi-sensor manipulation models.

---

# Research Context

This code is part of ongoing research related to:

* UAV cybersecurity
* GNSS spoofing analysis
* navigation system robustness
* sensor anomaly detection

The repository provides a **basic spoofing simulation tool** for generating controlled attack scenarios using real UAV telemetry data.

---

# License

This repository is intended for **research and academic use only**.
