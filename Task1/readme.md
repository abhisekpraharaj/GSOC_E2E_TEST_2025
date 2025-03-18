# Dataset Description
### 32x32 matrices with two channels: hit energy and time for two types of
### particles, electrons and photons, hitting the detector.

# Models
  - Model1(Custom RESNET)
  - Model2(Pretrained RESNET)

# Results

## Model 1
This is the custom ResNet model which we trained over the electron and photon dataset, and we achieved an AUC of around **0.79**.
![loss acc_cresnet](https://github.com/user-attachments/assets/dda0293d-5601-4a79-aebf-fc50130e2764)

![ROC_AUC_CRESNET](https://github.com/user-attachments/assets/da4a3167-ac00-481d-9381-f0a0596d3046)


## Model 2
This is the pre-trained ResNet model which we have fine-tuned on the electron-photon dataset for classification, and we achieved an AUC of around **0.78**.

![loss_accuracy_Pretrained_resnet](https://github.com/user-attachments/assets/749132de-6140-4282-b801-1ca9d922cf75)

![ROC_pretrained_resnet](https://github.com/user-attachments/assets/d862dd01-427c-40da-ac38-a41b3fe4b26e)

