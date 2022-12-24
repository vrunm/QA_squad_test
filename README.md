# QA_squad_test
Squad Dataset:
SQuAD 2.0, which is a reading comprehension dataset
consisting of questions posed by crowdworkers on a set of Wikipedia articles. Furthermore, the
answer to every question is a segment of text from the corresponding reading passage or the question
is unanswerable. 

The dataset contains the columns
Id: a string feature.

Title: a string feature.

Context: a string feature.

Question: a string feature.

Answers: a dictionary feature containing:

Leverage the two datasets in the following way:
• train (129,941 examples): All taken from the official SQuAD 2.0 training set.
• dev (6,078 examples): Half of the official dev set, randomly selected.
• test (5,921 examples): The rest of the official dev set, plus hand-labeled examples.

> Fine Tuning of the model has been done using the research paper: "[Question and Answering on SQuAD 2.0: BERT Is All
You Need](https://web.stanford.edu/class/archive/cs/cs224n/cs224n.1194/reports/default/15812785.pdf))".

| Model | Epochs | EM | F1 Score(Weighted) |
| ----- | ------ | -------- | ------------------ |
|BERT | 6 | 70 | 76|
|DistilBERT | 6 | 86% |0.86|
|Roberta  | 6 | 76% |0.74|

**Evaluation Method**
To evaluate our models we use the standard SQuAD performance metrics: Exact Match (EM) score
and F1 score. For our project, we focus on the EM and F1 scores with respect to the dev set.

• **Exact Match**: A binary measure of whether the system output matches the ground truth
answer exactly.

• **F1**: Harmonic mean of precision and recall, where precision = (true positives) / (true
positives + false positives) and recall = true positives / (false negatives + true positives).

    
Considering the FinBERT model a detailed analysis of the optimizers used for training has been done.
The table lists out the different optimizers and thier parameters used in training.

The following research paper has been used for fine tuning the optimizers:[On Empirical Comparisons of Optimizers for Deep Learning](https://arxiv.org/pdf/1910.05446.pdf)

Optimizer | Learning Rate | $\gamma$| Momentum $\eta$ | Alpha $\alpha$ | Beta1 $\beta_1$ | Beta2 $\beta_2$
| --- | --- | --- | --- | --- | --- | --- |
AdamW | 5e-5 |    |     |     | 10e-3 |10e-4|
RMSprop | 0.01 | 0.01 | 0.99|     | 10e-3  | 10e-5|
Adagrad | 5e-5 |
SGD(Momentum)| 5e-5 | 0.001|
SGD   | 0.01 | 


    
**Comparing the Training loss of all optimizers**
<br>
<img src = "train_loss_all_optim.png">


**Comparing the Validation loss of all optimizers**
<br>
<img src = "val_loss_all_optim.png">

The rate of convergence of the Adam optimizer is the fastest.

We can conclude the order of convergence of the optimizers:
AdamW > RMSprop > Adagrad > SGD (Momentum) > SGD
