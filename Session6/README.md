# TSAI Assignment

## SESSION 6 - RNN/LSTM With Attention Mechanism

ASSIGNMENT

1. Train model we wrote in the class on the following two datasets taken from this link <https://kili-technology.com/blog/chatbot-training-datasets/>
   1. <http://www.cs.cmu.edu/~ark/QA-data/>
   2. <https://quoradata.quora.com/First-Quora-Dataset-Release-Question-Pairs>
2. Once done, please upload the file to GitHub and proceed to share the things asked below:
   1. Share the link to your GitHub repo (100 pts for code quality/file structure/model accuracy) (100 pts)
   2. Share the link to your readme file (100 points for proper readme file)
   3. Copy-paste the code related to your dataset preparation for both datasets. (100 pts)
3. If your model trains and gets to respectable accuracy (200 pts).

Please remember that the objective of this assignment is to learn how to write code step by steps, so I should be seeing your exploration steps.

---

## QUESTION-ANSWER DATASET

Manually-generated factoid question/answer pairs with difficulty ratings from Wikipedia articles. Dataset includes articles, questions, and answers.

- There are three directories, one for each year of students: S08, S09, and S10.
- The file "question_answer_pairs.txt" contains the questions and answers.
- The first line of the file contains column names for the tab-separated data fields in the file.
- ArticleTitle | Question | Answer | DifficultyFromQuestioner | DifficultyFromAnswerer | ArticleFile

**Data Fields:**

- Field 1 is the name of the Wikipedia article from which questions and answers initially came.
- Field 2 is the question.
- Field 3 is the answer.
- Field 4 is the prescribed difficulty rating for the question as given to the question-writer.
- Field 6 is the relative path to the prefix of the article files. html files (.htm) and cleaned text (.txt) files are provided.

**Data Samples:**

- Abraham_Lincoln Who suggested Lincoln grow a beard? Grace Bedell. hard medium data/set3/a4
- Abraham_Lincoln When did the Gettysburg address argue that America was born? 1776 hard hard data/set3/a4
- Abraham_Lincoln When did the Gettysburg address argue that America was born? 1776. hard hard data/set3/a4

---

## FIRST QUORA DATASET

- Dataset consists of over 400,000 lines of potential question duplicate pairs.
- Each line contains IDs for each question in the pair, the full text for each question, and a binary value that indicates whether the line truly contains a duplicate pair.

**Data Fields:**

- id - the id of a training set question pair
- qid1, qid2 - unique ids of each question (only available in train.csv)
- question1, question2 - the full text of each question
- is_duplicate - the target variable, set to 1 if question1 and question2 have essentially the same meaning, and 0 otherwise.

**Data Samples:**

![image](https://qph.fs.quoracdn.net/main-qimg-ea50c7a005eb7750af0b53b07c8caa60)

---

## Seq2Seq Model

![image](https://pytorch.org/tutorials/_images/seq2seq.png)

![IMG_1196](https://user-images.githubusercontent.com/15984084/143487788-dfff34b1-660c-4048-bfad-3c67b6fa67f2.jpg)

![IMG_1197](https://user-images.githubusercontent.com/15984084/143487799-0841c351-094d-498c-a5c8-fc40fb67fe27.JPG)

Encoder:

![image](https://pytorch.org/tutorials/_images/encoder-network.png)

Decoder:

![image](https://pytorch.org/tutorials/_images/decoder-network.png)

Attention Decoder:

![image](https://pytorch.org/tutorials/_images/attention-decoder-network.png)

---

## REFERENCES

1. NLP FROM SCRATCH: TRANSLATION WITH A SEQUENCE TO SEQUENCE NETWORK AND ATTENTION: <https://pytorch.org/tutorials/intermediate/seq2seq_translation_tutorial.html>
2. <https://colab.research.google.com/drive/1yyON_VSYneppLPlPVhUMtGcDYMqEKVba?usp=sharing>
3. Sequence to Sequence Learning with Neural Networks: <https://arxiv.org/abs/1409.3215>
4. Learning Phrase Representations using RNN Encoder-Decoder for Statistical Machine Translation: <https://arxiv.org/abs/1406.1078>
5. Sequence to Sequence Learning with Neural Networks: <https://arxiv.org/abs/1409.3215>
6. Neural Machine Translation by Jointly Learning to Align and Translate: <https://arxiv.org/abs/1409.0473>
7. A Neural Conversational Model: <https://arxiv.org/abs/1506.05869>

---
