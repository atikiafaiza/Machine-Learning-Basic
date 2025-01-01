# Machine-Learning-Basic

## Evaluating a model
Model evaluation in machine learning is the process of assessing how well a trained model performs on <b>unseen</b> data. It involves using metrics and techniques to measure the model's accuracy, precision, or other relevant indicators depending on the task. The goal is to ensure the model generalizes effectively. Proper evaluation helps identify overfitting, underfitting, and areas for improvement, ensuring the model's reliability and effectiveness in real-world applications.

#### Training and Test Set
As mentioned earlier, evaluating a model requires unforeseen data to assess its performance effectively. However, collecting such data can often be costly and time-consuming.

A conventional and practical approach is to divide the existing dataset into two subsets: the training set and the test set.

<div style="text-align: center;">
<img src="./images/train test set.jpg" alt="train test set" width="600">
  <h6> Figure 1: Example of training and test set (a screenshot taken from the Coursera Advanced Machine Learning course)</h6>
</div>

The model is trained using the training set, where parameters (e.g., weights 𝑤 and biases b) are optimized by minimizing a cost function.

The test set, which remains unseen during training, is then used to evaluate the model's performance by computing test errors.

## Model Selection
The test set helps us determine the optimal model by evaluating and comparing the performance of multiple models, allowing us to select the one that performs best on unseen data.


Let’s say there are 10 models like the following:

𝑓<sub>𝑤,𝑏</sub>(𝑥) = 𝑤<sub>1</sub>𝑥 + 𝑏

f<sub>𝑤,𝑏</sub>(𝑥) = w<sub>1</sub>x + w<sub>2</sub>x<sup>2</sup> + b

f<sub>𝑤,𝑏</sub>(𝑥) = w<sub>1</sub>x + w<sub>2</sub>x<sup>2</sup> + w<sub>3</sub>x<sup>3</sup> + b

....

f<sub>𝑤,𝑏</sub>(𝑥) = w<sub>1</sub>x + w<sub>2</sub>x<sup>2</sup> + ... + w<sub>10</sub>x<sup>10</sup> + b

Suppose we trained each of these models on the training set and tested them on the test set. After evaluation, we found that Model 5 had the least error on the test set. Based on this, we can choose Model 5 as the optimal model.

The process involves the following flow:

1. All models minimize the cost function (e.g., 𝐽(𝑤,𝑏)) on the training set by fitting parameters 𝑤 and 𝑏.
2. By testing on the test set, we evaluate each model's performance and select the one with the lowest error.

The issue with this approach is that while we aim to find the best model for **unseen data**, the test set eventually becomes a **seen dataset** during the model selection process. By choosing the model with the lowest error on the test set, we are effectively treating the test set as part of the training process. This means that the models are being indirectly trained on the test set, much like how they were trained and fitted to the training set.

To summarize, this approach results in **fitting the test set**, which compromises its purpose as a purely unseen dataset. Consequently, the selected model may not generalize well to entirely new, unseen data. This highlights the need for an additional dataset (e.g., a validation set) or alternative evaluation techniques to mitigate this issue.
