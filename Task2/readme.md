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

