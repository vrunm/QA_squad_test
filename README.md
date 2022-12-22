# QA_squad_test
Squad Dataset:
SQuAD 2.0, which is a reading comprehension dataset
consisting of questions posed by crowdworkers on a set of Wikipedia articles. Furthermore, the
answer to every question is a segment of text from the corresponding reading passage or the question
is unanswerable. 

The dataset contains the columns
id: a string feature.
title: a string feature.
context: a string feature.
question: a string feature.
answers: a dictionary feature containing:

Leverage the two datasets in the following way:
• train (129,941 examples): All taken from the official SQuAD 2.0 training set.
• dev (6,078 examples): Half of the official dev set, randomly selected.
• test (5,921 examples): The rest of the official dev set, plus hand-labeled examples.

> Fine Tuning of the model has been done using the research paper: "[Question and Answering on SQuAD 2.0: BERT Is All
You Need](https://web.stanford.edu/class/archive/cs/cs224n/cs224n.1194/reports/default/15812785.pdf))".


**Evaluation Method**
To evaluate our models we use the standard SQuAD performance metrics: Exact Match (EM) score
and F1 score. For our project, we focus on the EM and F1 scores with respect to the dev set.

• **Exact Match**: A binary measure of whether the system output matches the ground truth
answer exactly.

• **F1**: Harmonic mean of precision and recall, where precision = (true positives) / (true
positives + false positives) and recall = true positives / (false negatives + true positives).


