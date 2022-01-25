# TSAI Assignment

## SESSION 11 - TASK3 - BART for Paraphrasing with Simple Transformers

ASSIGNMENT

1. Reproduce the training explained in this blog. You can decide to pick fewer datasets.
   - <https://towardsdatascience.com/bart-for-paraphrasing-with-simple-transformers-7c9ea3dfdd8c>
2. Show output on 5 samples.

---

## OUTPUT ON 5 SAMPLES

![OUTPUT](assets/output1.png)
![OUTPUT](assets/output2.png)

---

## TRAINING LOGS

![logs](assets/training_logs.png)

---

## BART Sequence-to-Sequence

The encoder uses a denoising objective similar to BERT while the decoder attempts to reproduce the original sequence (autoencoder), token by token, using the previous (uncorrupted) tokens and the output from the encoder.

![BART](assets/BART.png)

---

## DATASETS USED

- PAWS: Paraphrase Adversaries from Word Scrambling <https://github.com/google-research-datasets/paws#paws-wiki>
- First Quora Dataset Release: Question Pairs <https://quoradata.quora.com/First-Quora-Dataset-Release-Question-Pairs>
- Microsoft Research Paraphrase Corpus
  <https://msropendata.com/datasets/e235323f-f23c-4246-b2e6-27d7a654d6cc>
  - NOT USED

## REFERENCES

1. BART for Paraphrasing with Simple Transformers: <https://towardsdatascience.com/bart-for-paraphrasing-with-simple-transformers-7c9ea3dfdd8c>
2. BART: Denoising Sequence-to-Sequence Pre-training for Natural Language Generation, Translation, and Comprehension <https://arxiv.org/pdf/1910.13461.pdf>

---
