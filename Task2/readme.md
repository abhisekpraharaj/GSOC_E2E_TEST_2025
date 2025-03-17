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
- The model takes **X_jet** (2 channels) and **pt** as inputs for training.

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
___________________________________________________________

## Model Comparison Table

| Method                                    | Inputs                      | Epochs | MAE (Prediction) | Training Time |
|-------------------------------------------|-----------------------------|--------|------------------|---------------|
| Chunked Data from Multiple Datasets with Custom CNN Regression | **X_jet (2 selected channels), pt** | 40   | 92 (unscaled_predictions) | 32 mins |
| Full Data from One Dataset with Custom CNN (3 Channels) | **X_jet (3 selected channels)** | 5 | 0.6647 (scaled_predictions) | 11.24 hrs |
| Full Data from One Dataset with VGG16 (3 Channels) | **X_jet (3 selected channels)** | 5 | 0.5914 (scaled_predictions) | 11.22 hrs |

## Results  

### 1. Chunked Data from Multiple Datasets with Custom CNN Regression  
#### Loss Curve 
![Loss](https://github.com/user-attachments/assets/7080a22b-bfd9-4355-b66d-a7eb54879837)

#### Actual vs Predicted  
![actual_vs_prediction](https://github.com/user-attachments/assets/54354fb5-ce01-4108-9831-6f002599d5c5)


#### Error  
 ![error_metrics](https://github.com/user-attachments/assets/12f74fcd-fd0e-4d48-bd59-ae48b32f7218)


---

### 2. Full Data from One Dataset with Custom CNN (3 Channels)  
#### Loss Curve   
![Loss_CNN](https://github.com/user-attachments/assets/39c2b4ae-9858-4767-b7b6-3bbdf64c3f83)


#### Error in prediction
![Error_metrics](https://github.com/user-attachments/assets/82b7a6f7-9bd3-412e-b053-2ec163eabbc9)

---

### 3. Full Data from One Dataset with VGG16 (3 Channels)  
#### Loss Curve  

![vgg16_loss](https://github.com/user-attachments/assets/f98cc8e5-03d6-4fd0-8559-915538fadab9)

#### Error in Prediction  

![vgg16_error](https://github.com/user-attachments/assets/cf160f0f-9d44-4451-a393-fbcd1fd48dbe)



## Suggestions and Future Improvements  

### 1. Efficient Data Loading for GPU Utilization  
I need assistance in implementing a **robust data reading and loading mechanism** to efficiently utilize GPU resources. Faster and optimized data loading will significantly reduce training time while allowing the model to train on the **entire dataset**, leading to better accuracy.  

From the current results, we observe that training on a **single dataset** achieves a **low MAE** and **minimal prediction errors**. Thus, if we can efficiently feed data from **all datasets** into the model, it will improve regression accuracy further.  

### 2. Physics-Informed Neural Networks (PINNs) with **pt** as a Feature  
Incorporating **pt** as a feature presents an opportunity to leverage **Physics-Informed Neural Networks (PINNs)**. If we can derive a function representing the physical relationship involving **pt**, we could integrate it into the model's training process as a **physics-based loss function**.  

This physics-informed loss could significantly enhance the model’s learning and predictive capabilities. While I haven't fully explored this approach yet, with proper guidance, I aim to **extend the project** in this direction to improve performance and interpretability.  



