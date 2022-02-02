# TSAI Assignment

## Session 13 - AWS Sagemaker

ASSIGNMENT

1. Go through this notebook (Links to an external site.), change the dataset (to anything other than "Amazon Reviews Polarity Dataset").
   - <https://github.com/aws-samples/finetune-deploy-bert-with-amazon-sagemaker-for-hugging-face/blob/main/finetune-distilbert.ipynb>
2. Record the whole step using any video capturing software (like OBS).
3. Upload the video on youtube (you can make it unlisted, but allow for embedding)
4. Share the link to your YouTube video, and the GitHub link where I can see the code you used for training (move the notebook with logs from Amazon to Github)

---

## YOUTUBE LINK

<https://youtu.be/M1mfEy8NfDU>

<img width="300" src="https://user-images.githubusercontent.com/15984084/152216041-d0c242a0-e7ca-4164-9434-00c420fc6e5f.jpeg">

---

## What is AWS Sagemaker?

- Amazon SageMaker is a fully-managed service that enables data scientists and developers to quickly and easily build, train, and deploy machine learning models at any scale.
- Amazon SageMaker includes modules that can be used together or independently to build, train, and deploy your machine learning models.

Build

- Amazon SageMaker makes it easy to build ML models and get them ready for training by providing everything you need to quickly connect to your training data, and to select and optimize the best algorithm and framework for your application.

Train

- You can begin training your model with a single click in the Amazon SageMaker console. Amazon SageMaker manages all of the underlying infrastructure for you and can easily scale to train models at petabyte scale.

Deploy

- Once your model is trained and tuned, Amazon SageMaker makes it easy to deploy in production so you can start running generating predictions on new data (a process called inference).

Amazon SageMaker takes away the heavy lifting of machine learning, so you can build, train, and deploy machine learning models quickly and easily.

---

## DISTRIBUTED

To scale and accelerate our training we will use Amazon SageMaker, which provides two strategies for distributed training, data parallelism and model parallelism.

- Data parallelism splits a training set across several GPUs
- Model parallelism splits a model across several GPUs.
- We are going to use SageMaker Data Parallelism, which has been built into the Trainer API. To be able use data-parallelism we only have to define the distribution parameter in our HuggingFace estimator.

---

## DATASET USED

amazon_reviews_multi

- It is an Amazon product reviews dataset for multilingual text classification.
- The dataset contains reviews in English, Japanese, German, French, Chinese and Spanish, collected between November 1, 2015 and November 1, 2019. Each record in the dataset contains the review text, the review title, the star rating, an anonymized reviewer ID, an anonymized product ID and the coarse-grained product category (e.g. ‘books’, ‘appliances’, etc.)
- Dataset Link: <https://huggingface.co/datasets/amazon_reviews_multi>
- Data Fields
  - review_id: A string identifier of the review.
  - product_id: A string identifier of the product being reviewed.
  - reviewer_id: A string identifier of the reviewer.
  - stars: An int between 1-5 indicating the number of stars.
  - review_body: The text body of the review.
  - review_title: The text title of the review.
  - language: The string identifier of the review language.
  - product_category: String representation of the product's category.
- DATA SAMPLE

      {
         "review_id": "de_0784695",
         "product_id": "product_de_0572654",
         "reviewer_id": "reviewer_de_0645436",
         "stars": "1",
         "review_body": "Leider, leider nach einmal waschen ausgeblichen . Es sieht super h\u00fcbsch aus , nur leider stinkt es ganz schrecklich und ein Waschgang in der Maschine ist notwendig ! Nach einem mal waschen sah es aus als w\u00e4re es 10 Jahre alt und hatte 1000 e von Waschg\u00e4ngen hinter sich :( echt schade !",
         "review_title": "Leider nicht zu empfehlen",
         "language": "de",
         "product_category": "home"
      }

The amazon_reviews_multi has 5 classes (stars) to match those into a sentiment-analysis task we will map those star ratings to the following classes labels:

- (1-2): Negative
- (3): Neutral
- (4-5): Positive

---

## MODEL USED

DistilBERT base multilingual model (cased)

- The model is trained on the concatenation of Wikipedia in 104 different languages listed here. The model has 6 layers, 768 dimension and 12 heads, totalizing 134M parameters (compared to 177M parameters for mBERT-base).
- On average DistilmBERT is twice as fast as mBERT-base.
- Model Link: <https://huggingface.co/distilbert-base-multilingual-cased>

---

## LABELS DISTRIBUTION IN TRAIN DATASET

![image](https://user-images.githubusercontent.com/15984084/152216608-5716de12-f745-49c7-b1eb-0a9e8872d9be.png)

---

## AWS SAGEMAKER NOTEBOOK INSTANCE

<img width="1676" alt="Session13-TSAI" src="https://user-images.githubusercontent.com/15984084/152186414-3e851d22-3d2e-45e9-bfca-4dd39444ccb6.png">

---

## AWS SAGEMAKER TRAINING JOB

- Name: finetune-distilbert-base-multilingual-cased-2022-02-02-14-58-39
- Training time (seconds): 17 minute(s) and 33 seconds
- Billable time (seconds): 5 minute(s) and 16 second(s)
- Managed spot training savings: 70%
- Instance Type: ml.p3.16xlarge
- Instance count: 1

<img width="1664" alt="finetune-distilbert-base-multilingual-cased-2022-02-02-" src="https://user-images.githubusercontent.com/15984084/152186427-8d483c25-716c-4279-898f-d8d566a080e0.png">

<img width="1565" alt="Pasted Graphic 2" src="https://user-images.githubusercontent.com/15984084/152186440-ba97bc70-3c64-483b-9892-b4179b9a43aa.png">

<img width="1616" alt="Pasted Graphic 3" src="https://user-images.githubusercontent.com/15984084/152186451-f6ab1296-d4bd-40c9-801f-76f01976ed91.png">

---

## TRAINING LOGS

<img width="1429" alt="Pasted Graphic 4" src="https://user-images.githubusercontent.com/15984084/152186474-31dbca5d-a15d-4024-8b38-037f3c37316f.png">

---

---

## EVALUATION RESULTS

- epoch = 3.0
- eval_accuracy = 0.7614
- eval_f1 = 0.7614
- eval_loss = 0.5882487297058105
- eval_runtime = 1.5266
- eval_samples_per_second = 3275.246
- eval_steps_per_second = 26.202

---

## PREDICTION OUTPUT

<img width="1421" alt="Pasted Graphic 5" src="https://user-images.githubusercontent.com/15984084/152186490-4c0881e5-d80a-4612-8e01-fdb04a10e63f.png">

---

## HUGGING FACE UPLOADED MODEL

HUGGING FACE HUB MODEL: <https://huggingface.co/arjuntheprogrammer/distilbert-base-multilingual-cased-sentiment-2>

---

## REFERENCES

1. Hugging Face on Amazon SageMaker: <https://huggingface.co/docs/sagemaker/main>
2. Deploy models to Amazon SageMaker: <https://huggingface.co/docs/sagemaker/inference>
3. Run training on Amazon SageMaker: <https://huggingface.co/docs/sagemaker/train>
4. Distributed training on multilingual BERT with Hugging Face Transformers & Amazon SageMaker: <https://www.philschmid.de/pytorch-distributed-training-transformers>
5. Available SageMaker Studio Instance Types: <https://docs.aws.amazon.com/sagemaker/latest/dg/notebooks-available-instance-types.html>
6. Example Notebook: <https://github.com/aws-samples/finetune-deploy-bert-with-amazon-sagemaker-for-hugging-face/blob/main/finetune-distilbert.ipynb>
7. Transformers: <https://github.com/huggingface/transformers>

---
