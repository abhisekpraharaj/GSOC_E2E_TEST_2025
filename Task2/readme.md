## Dataset Description

### . The dataset is stored in Parquet format.
### . It consists of six separate datasets, each containing approximately 150,000 rows.
### . Each dataset has five columns:
   - **X_jet**: Nested structure containing 8-channel arrays, each with a shape of (125, 125).
   - **mass**: Scalar value representing the mass.
   - **pt**: Scalar value representing the transverse momentum.
   - **ieta**: Integer value representing the pseudorapidity index.
   - **iphi**: Integer value representing the azimuthal angle index.

### Data Format

Each row in the dataset corresponds to a single jet event, where:
### . `X_jet` represents a **multi-channel image-like** structure.
### . `mass`, `pt`, `ieta`, and `iphi` provide **additional scalar attributes** related to the jet event.

# Methods for Training Models

## 1. Chunked Data from Multiple Datasets with Custom CNN Regression
- This method loads data in chunks from four different datasets.
- A Custom CNN regression model is used.
- The model takes **X_jet** (all 8 channels) and **pt** as inputs for training.

### Process:
1. Load chunks from 4 different datasets.
2. Train the Custom CNN Regression model using the loaded data.

---

## 2. Full Data from One Dataset with Custom CNN (3 Channels)
- This method loads the entire dataset from a single file.
- A Custom CNN regression model is used.
- The model takes only **3 selected channels** from **X_jet** as input for training.

### Process:
1. Load the full dataset from one file.
2. Train the Custom CNN Regression model using the 3 selected channels.

---

## 3. Full Data from One Dataset with VGG16 (3 Channels)
- This method loads the entire dataset from a single file.
- The **VGG16** model is used.
- The model takes only **3 selected channels** from **X_jet** as input for training.

### Process:
1. Load the full dataset from one file.
2. Train the VGG16 model using the 3 selected channels.

