# AWS SAGEMAKER CIFAR

## DATASET USED

CIFAR-10

Link: <https://www.cs.toronto.edu/~kriz/cifar.html>

---

## TRAINING With Local Instance

![local-instance](https://user-images.githubusercontent.com/15984084/151658259-940c126b-baa8-445d-b970-0ad8709ded93.png)

---

## TRAINING Without Spot Instance

![without-spot-instance](https://user-images.githubusercontent.com/15984084/151658267-67eb2214-06ae-4765-83b3-b6d92e80667e.png)

- Training seconds: 600
- Billable seconds: 600

---

## TRAINING With Spot Instance

- Training seconds: 338
- Billable seconds: 107
- Managed Spot Training savings: 68.3%

![with-spot-instance](https://user-images.githubusercontent.com/15984084/151658274-68b2c116-b69c-4bbc-9e2a-21fc23521864.png)

---

## EVALUATION OUTPUT

![evaluation](https://user-images.githubusercontent.com/15984084/151658285-0ca42a5a-b610-4716-9e7a-a1fb9da8fdaf.png)

---

## REFERENCES

1. GitHub Repository: <https://github.com/aws/amazon-sagemaker-examples/tree/master/sagemaker-python-sdk/pytorch_cnn_cifar10>
2. Notebook Link: <https://github.com/aws/amazon-sagemaker-examples/blob/master/sagemaker-python-sdk/pytorch_cnn_cifar10/pytorch_local_mode_cifar10.ipynb>

---
