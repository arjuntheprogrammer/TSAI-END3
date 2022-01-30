# AWS SAGEMAKER CIFAR

## Finetuning Hugging Face DistilBERT with Amazon Reviews Polarity dataset

Use the Hugging Faces transformers and datasets library with Amazon SageMaker to fine-tune a pre-trained transformer on binary text classification.

Use the pre-trained DistilBERT model with the Amazon Reviews Polarity dataset. We will then deploy the resulting model for inference using SageMaker Endpoint.

---

## DATASET USED

Amazon Polarity

The Amazon Reviews Polarity dataset consists of reviews from Amazon. The data span a period of 18 years, including ~35 million reviews up to March 2013.

Reviews include product and user information, ratings, and a plaintext review. It's avalaible under the amazon_polarity dataset on Hugging Face.

Link: <https://github.com/dsk78/Text-Classification---Amazon-Reviews-Polarity>

---

## Training Logs

![image](https://user-images.githubusercontent.com/15984084/151690743-4805b0c1-d797-4a50-be80-aa74593fa899.png)

---

## AWS Training Job Spot Instance

- Name: finetune-distilbert-base-cased-2022-01-30-06-28-08
- Training time (seconds): 505
- Billable time (seconds): 151
- Managed spot training savings: 70%
- Instance Type: ml.p3.2xlarge
- Instance count: 1

TRAINING JOB

![image](https://user-images.githubusercontent.com/15984084/151690679-5af62543-9d05-43f8-a0ab-81db55c7577c.png)

AWS Train and Test Configuration

![image](https://user-images.githubusercontent.com/15984084/151690933-633d6e60-74ac-458f-88fd-d543ad0baee0.png)

---

## Metrics

![image](https://user-images.githubusercontent.com/15984084/151690731-d5b28b29-b5d2-499b-b539-6fef40d9a6b2.png)

---

## Evaluation

![image](https://user-images.githubusercontent.com/15984084/151690755-9ea8233b-0c06-4856-baca-9c5eb6a668b8.png)

---

## AWS Endpoint

![image](https://user-images.githubusercontent.com/15984084/151690694-da38f2a0-094d-432c-b3ec-47b0b6c51964.png)

---

## REFERENCES

1. GitHub Repository: <https://github.com/aws-samples/finetune-deploy-bert-with-amazon-sagemaker-for-hugging-face>
2. Notebook Link: <https://github.com/aws-samples/finetune-deploy-bert-with-amazon-sagemaker-for-hugging-face/blob/main/finetune-distilbert.ipynb>

---
