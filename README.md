# QA_squad_test
Squad Dataset:
SQuAD 2.0, which is a reading comprehension dataset
consisting of questions posed by crowdworkers on a set of Wikipedia articles. Furthermore, the
answer to every question is a segment of text from the corresponding reading passage or the question
is unanswerable. For the scope of our project, we use the official SQuAD 2.0 train and dev sets. 

Leverage the two datasets in the following way:
• train (129,941 examples): All taken from the official SQuAD 2.0 training set.
• dev (6,078 examples): Half of the official dev set, randomly selected.
• test (5,921 examples): The rest of the official dev set, plus hand-labeled examples.

Evaluation Method
To evaluate our models we use the standard SQuAD performance metrics: Exact Match (EM) score
and F1 score. For our project, we focus on the EM and F1 scores with respect to the dev set.

• Exact Match: A binary measure of whether the system output matches the ground truth
answer exactly.
• F1: Harmonic mean of precision and recall, where precision = (true positives) / (true
positives + false positives) and recall = true positives / (false negatives + true positives).

F1 score = (2×prediction×recall) / (precision + recall). (Note: In SQuAD, precision
measures to what extent the predicted span is contained in the ground truth span, and recall
measures to what extent the ground truth span is contained in the predicted span



