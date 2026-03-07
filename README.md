This script is a data preprocessing component of a research project on GPS spoofing detection in UAV systems.
It loads UAV flight logs, injects simulated spoofing attacks into GPS coordinates, and extracts motion-based features used later for machine learning models.

The output of this script is a feature dataset (X) and corresponding labels (y) that can be used for training or evaluating spoofing detection algorithms.

The script processes UAV flight logs stored in CSV format. Example directory structure:

Phantom4_001_csv/
    flight_1/FLY001.csv
    flight_2/FLY002.csv

The script automatically searches for:

**/FLY*.csv

To evaluate spoofing detection methods, the script injects synthetic GPS spoofing attacks into a portion of each flight.


Notes
The script can be run in Google Colab or locally with access to the flight log dataset.
This script focuses only on data preparation and spoofing simulation.
Model training and evaluation are implemented in separate components of the project.

