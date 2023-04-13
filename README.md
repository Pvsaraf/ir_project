# Evidence Retrieval for Fact Verification - CS60092 - Group 14

## There are three modules in this IR System:
* Document Retrieval
* Sentence Retrieval
* Fact Verification

### How to use the Fact Verification module?
This module deals with the classification of every claim-evidences pair into either SUPPORTS, REFUTES, or NOT ENOUGH INFO. For this, we use some pretrained model. In our case, we use the "roberta-large-mnli" model from Hugging Face model hub. 

Link to RoBERTa model: https://huggingface.co/roberta-large-mnli.

We used Facebook BART model as well, for comparison.

Link to Facebook BART model: https://huggingface.co/facebook/bart-large-mnli.

### Using fine-tuned pretrained model for testing?
Run the "fact_verification.ipynb" jupyter notebook. This requires the pretrained model fine-tuned for the FEVER task. You can either generate the fine-tuned model using "fine_tuning_rte.ipynb" (discussed later), or you can use our generated fine-tuned model.

Link to the fine-tuned pretrained model: https://drive.google.com/drive/folders/1ShykW5wmMt2bWRx9AjdO36KUJBie4vkX?usp=share_link.

Further, it will require development dataset which can be generated using "build_csv.ipynb" notebook, or you can use the "output.csv" file directly.

Link to output.csv: https://drive.google.com/file/d/1fm6SDn0TQckZqLFs7ctNODOZNPLC1W_z/view?usp=sharing.

### How to fine-tune the model?
This section has two parts:
* Data generation for fine-tuning
* Fine-tuning the  model

**Data generation for fine-tuning:**
For this part, run the "build_csv.ipynb" jupyter notebook. In order to do this, you need two files in place, "fever.db" and "train.jsonl".

Link to fever.db: https://drive.google.com/file/d/1qoEqOdqcPHOrX1JGKxdxyBomUjxvh8fw/view?usp=sharing.

Link to train.jsonl: https://drive.google.com/file/d/1awN6S3ejR-Jkn81Qg1K8j__cvOF3nfuw/view?usp=sharing.

This will generate a file "output.csv" which will be used for fine-tuning the model.

**Data generation for fine-tuning:**
For this part, run the "fine_tuning_rte.ipynb" jupyter notebook. In order to do this, we need the fine-tuning dataset. You can either generate your own dataset using "build_csv.ipynb", or you can use our generated "output.csv" to replicate the results which we got.

Link to output.csv: https://drive.google.com/file/d/1fm6SDn0TQckZqLFs7ctNODOZNPLC1W_z/view?usp=sharing.

This code will produce the pretrained model with the name "fine-tuned-roberta-large-mnli", which can be used for testing using "fact_verification.ipynb".

---

Slides:
https://docs.google.com/presentation/d/1skxHsoJ_qZ5_EJStu0oVrV6pQ1yVYjRK/edit#slide=id.g21cf28aefd8_2_12
