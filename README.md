# KalmanNet: Data-Driven Kalman Filtering

## Project Overview

This project implements a KalmanNet-inspired recurrent filtering approach based on the research paper *KalmanNet: Data-Driven Kalman Filtering*.

The project uses the EuRoC MAV MH_01_easy dataset to estimate UAV position and velocity and compares a traditional Kalman Filter with a GRU-based KalmanNet implementation.

## Dataset

- **Dataset:** EuRoC MAV – MH_01_easy
- **Sensors extracted:** IMU and Leica position measurements
- **Position sampling:** Resampled to 20 Hz
- **Training/testing split:** 80% / 20%

## Technologies Used

- Python
- PyTorch
- NumPy
- Pandas
- Matplotlib
- ROS Bags
- Scikit-learn

## Implementation

1. Extracted sensor measurements from the EuRoC ROS bag.
2. Processed timestamps and resampled position measurements.
3. Estimated UAV velocity from position measurements.
4. Developed a six-dimensional state-space model.
5. Implemented a traditional Kalman Filter.
6. Developed a GRU-based KalmanNet-inspired gain estimator.
7. Trained and evaluated both approaches.

## Experimental Results

| Metric | Traditional KF | KalmanNet |
|---|---:|---:|
| Position RMSE | 0.04587 m | 0.06415 m |
| Velocity RMSE | 0.14451 m/s | 0.18195 m/s |

The traditional Kalman Filter achieved lower RMSE in this experiment.

## Important Experimental Note

The experiment uses real EuRoC UAV trajectory data with simulated Gaussian noise added to position observations. Velocity reference values are estimated from smoothed position measurements.

This is a compact KalmanNet-inspired implementation, not a complete reproduction of the original paper or a direct IMU–Leica sensor-fusion system.

## How to Run

1. Open the `.ipynb` notebook in Kaggle.
2. Add the EuRoC MH_01_easy ROS bag dataset as a notebook input.
3. Enable Internet in Kaggle to install the `rosbags` dependency.
4. Run the notebook cells sequentially.

## References

1. Revach et al., *KalmanNet: Data-Driven Kalman Filtering*, ICASSP 2021.
2. EuRoC MAV Dataset, ETH Zurich.
3. Original implementation: https://github.com/KalmanNet/KalmanNet_TSP
