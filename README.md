# EEG Epilepsy Detection using CNN on Bonn Dataset

Deep learning CNN model for binary classification of epileptic seizure detection using EEG signals from the Bonn University dataset.

**Dataset:**
- Bonn University EEG Dataset
- http://www.meb.uni-bonn.de/epileptologie/science/physik/eegdata.html

- **Set A & B**: Healthy volunteers (eyes open/closed)
- **Set C & D**: Interictal (between seizures)
- **Set E**: Ictal (during seizure activity)

Each signal contains **4097 samples** at 173.61 Hz sampling rate.

**Task:**

- Binary classification: **Healthy (Set A) vs (Set E)**
- Binary classification: **Healthy (Set ABCD) vs (Set E)**

**Results:**

- **Model Parameters**: 99,713
- **Architecture**: 4 Conv1D layers + Global Average Pooling
- **Test Accuracy**: 100%
- Training Loss 0.0287
- Validation Loss	0.0917

**Model Architecture (BonnCNN):**

- Input: (1, 4097)
↓
- Conv1D(16, k=3) + BN + ReLU + MaxPool(2)
↓
- Conv1D(32, k=5) + BN + ReLU + MaxPool(2)
↓
- Conv1D(64, k=7) + BN + ReLU + MaxPool(2)
↓
- Conv1D(128, k=9) + BN + ReLU + MaxPool(2)
↓
- Global Average Pooling
↓
- Dense(64) + Dropout(0.5)
↓
- Dense(1) + Sigmoid

**Author:**
- Hesam Moradkhani, IUST University, Tehran, Iran
