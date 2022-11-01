---
layout: post
title: Understanding Precision and Recall
abstract: So you've built a machine learning model, trained it on a data and tested on another data... now what?... It is always a good practice to evaluate the quality of one’s work.
---

<center><img src="{{ site.url }}{{ site.baseurl }}/blog-post/img/Blog-P&R/1.jpg" style="width:80%"></center>


<br>*Evaluation is creation: hear it, you creators! Evaluating is itself the most valuable treasure of all that we value. It is only through evaluation that value exists: and without evaluation the nut of existence would be hollow. Hear it, you creators!*
*~Friedrich Nietzsche* <br>Most machine learning (ML) problems can be fit into two groups: **Classification** and **Regression** In this post we will learn about evaluation of classification machine learning models, which are algorithms that predict the class for a given input. The main metrics used to assess the performance of classification models are **Accuracy**, **Precision** and **Recall**. We will talk about them in detail.
<br>
<center><img src="{{ site.url }}{{ site.baseurl }}/blog-post/img/Blog-P&R/2.jpg" style="width:80%"></center>
<br>
# Accuracy
**Accuracy** is one of the metrics used for evaluating classification models. Accuracy can be defined as the number of correct predictions divided by total number of predictions. Accuracy alone doesn't tell the full story when you're working with a class-imbalanced data set where there is a significant disparity between the number of positive and negative labels. So, we need a more general metric to evaluate our Machine learning models.
<br>
# Confusion Matrix

A **confusion matrix** is an Ν×Ν table that aggregates a classification model's correct and incorrect guesses. One axis of a confusion matrix is the label that the model predicted, and the other axis is the ground truth. Ν represents the number of classes. For example, Ν=2 is used for a binary classification model. Let’s consider the following confusion matrix for a three-class (multi-class) classification model that categorizes three different iris types (Virginica, Versicolor, and Setosa). 


<center><img src="{{ site.url }}{{ site.baseurl }}/blog-post/img/Blog-P&R/3.jpg" style="width:80%"></center>
<br>

{:class="table table-bordered"}
|                               |**Setosa (predicted)**|**Versicolor (predicted)**|**Virginica (predicted)**|
|------------------------------ |--------------------- | ------------------------ | ----------------------- |
|   **Setosa (ground truth)**   |88                    |                        12|0                        |
| **Versicolor (ground truth)** |                     6|                       141|7                        |
|  **Virginica (ground truth)** |2                     |27                        |                      109|

<br>
When the ground truth was Virginica, the confusion matrix shows that the model was far more likely to mistakenly predict Versicolor over Setosa.


<center><img src="{{ site.url }}{{ site.baseurl }}/blog-post/img/Blog-P&R/4.jpg" style="width:80%"></center>
Some terms that are often used with 2X2 Confusion matrices are: A **true positive (TP)** is an outcome where the model *correctly* predicts the *positive* class. A **false positive (FP)** is an outcome where the model *incorrectly* predicts the *positive* class. A **true negative (TN)** is an outcome where the model *correctly* predicts the *negative* class. A **false negative (FN) is** an outcome where the model incorrectly predicts the negative class.


<center><img src="{{ site.url }}{{ site.baseurl }}/blog-post/img/Blog-P&R/5.jpg" style="width:80%"></center>

# Precision
**Precision** is a metric that answers the question - What proportion of **predicted Positives** is truly Positive?  It is defined for different classes the output is classified to. Precision is calculated as the number of correct positive predictions (TP) divided by the total number of positive predictions (TP + FP). By using the definition we can find precision for particular class belonging to set of N classes. In the iris types example above 

Precision_Setosa=88/88+6+2  

Therefore, 88/96 predictions of class Setosa were actually Setosa.

# Recall
**Recall** answers the question - What proportion of **actual Positives** is correctly classified? It is defined for different classes the output is classified to. recall is calculated as the ratio between the number of Positive samples correctly classified as Positive to the total number of Positive samples.
By using the definition we can find precision for particular class belonging to set of Ν classes. In the iris types example above: 

Recall_Versicolor=141/88+141+109  

Therefore, 141/338 correct predictions belonged to the Versicolor class.

# Accuracy vs Precision and Recall 
<center><img src="{{ site.url }}{{ site.baseurl }}/blog-post/img/Blog-P&R/6.jpg" style="width:80%"></center>

Precision and Recall are useful in cases where classes are not evenly distributed. A common example is developing a classification algorithm that predicts whether or not someone has the disease. If only a small percentage of the population (let's say 1%) has this disease, we could build a classifier that predicts if a person has or does not have the disease, we would have built a model which is 99% accurate and 0% useful.
However, if we measured the recall of this useless predictor, it would be clear that there was something wrong with our model. In this example, *recall ensures that we're not overlooking the people who have the disease, while precision ensures that we're not misclassifying too many people of having the disease when they do not in reality.*
# F-score
You wouldn't want a model that incorrectly predicts a person has cancer (the person would end up in a painful and expensive treatment process for a disease they didn't have) but you also don't want to incorrectly predict a person does not have cancer when in fact they do. Thus, it's important to evaluate both the precision and recall of a model.Ultimately, it's nice to have one number to evaluate a machine learning model just as you get a single grade on a test in school. Thus, it makes sense to combine the precision and recall metrics; the common approach for combining these metrics is known as the **f-score**.
Fβ=1+β2\*precision\*recallβ2\*precision+recall
where β is a factor which determines how much important recall is with respect to precision. Putting β as 1 gives us the harmonic mean of precision and recall. The highest possible value of an F-score is 1.0, indicating perfect precision and recall, and the lowest possible value is 0, if either the precision or the recall is zero. Since, Precision and recall are defined class-wise, F-score is also defined **class-wise**.


# The choice of an evaluation metric

Recall is the ability of a model to fit all the relevant cases within a dataset. Precision is the ability of a classification model to identify only the relevant data points. A system with high Precision might leave out some actual positives, but what it intends to return is high accuracy in the particular class. On the other hand, a system with high Recall might give you numerous misclassifications of other classes, but it almost always will correctly classify the particular class from the dataset. Here, “particular class” means the class with respect to which precision and recall are being calculated. Which one to choose is a tough decision and entirely depends on the problem you are using machine learning for. Generally speaking, *optimizing Precision typically reduces Recall and vice versa*. Therefore, many applications consider a metric derived from both Precision and Recall (called the F-score) to measure the performance of a machine learning situation. Here are a few examples where optimizing one of the metric seems quite appropriate than another:

## Example 1

Say you are building a course recommender system. The idea is to recommend courses to students based on their profiles.A student’s time is crucial; thus, you don’t want to waste their valuable time recommending courses that they may not like or are irrelevant to them. In this case Precision is what you should prefer optimizing for. It is okay not to recommend good courses. However, what your system recommends should be very high quality as students should not spend time watching courses that are irrelevant to them.

## Example 2

Assume that you want to shortlist candidates for a job opening and see if they should be selected for an interview. As your organization is looking for talented candidates, you don’t want to miss out on a candidate that can be a potential hire. Having inexperienced or irrelevant candidates won’t hurt as long as you catch all the relevant and talented ones.
Therefore, Recall is the metric you should optimize for. If you instead optimize for Precision, there is a possibility of excluding talented candidates, which is not desired.

## Example 3

Say you are a thief and you have broken into a house. You aim to rob money, jewellery, and everything else you think is “valuable". Taking some invaluable items certainly would not hurt you, what would matter is how many of the valuable items are you able to steal.Therefore, in this case recall is what you should optimize for. Had you gone with precision in this case you would have missed some valuable items and it would definitely have not been a good steal.

Alternative Solution :

Assuming the thief could steal only a limited amount of valuable items, stealing non-valuable objects would take up space. Therefore, optimizing precision would be beneficial for the thief. So, in this case we need to focus on both precision and recall, as a result Fb-score comes into play. We can determine the importance of recall against precision by varying beta. Thus, in this example we see that the choosing precision or recall and giving importance to one of them totally depends on the problem of our model.

## Example 4:

We all have played Among Us, haven’t we? If not, the aim is to identify the imposters within a group of players. What we want in this case is to catch the imposters, we may afford to lose some of our valuable crewmates in this process as long as the imposter is caught. However, we would not like to lost too many of our teammates too as it would grant a victory to the imposter. Thus, we should again go with recall in this case. You definitely want to catch the imposter.

# Precision vs Recall
To fully evaluate the effectiveness of a model, we must examine both precision and recall. However, we had earlier mentioned in this post that optimizing one typically reduces another. But why is that? It cannot be simply deduced from their mathematical definitions. We will take help of an example that can help us visualize this relation:

Look at the following figure, which shows 30 predictions made by an email classification model. Those to the right of the classification threshold are classified as "spam", while those to the left are classified as "not spam."

<center><img src="{{ site.url }}{{ site.baseurl }}/blog-post/img/Blog-P&R/7.jpg" style="width:80%"></center>

**Figure 1. Classifying email messages as spam or not spam.**

Let's calculate precision and recall based on the results shown in Figure 1:

{:class="table table-bordered"}
|-----------------------+-----------------------|
|True Positives (TP): 8 |False Positives (FP): 2|
| --------------------- + --------------------- |
|False Negatives (FN): 3|True Negatives (TN): 17|
|-----------------------+-----------------------|

Precision measures the percentage of emails flagged as spam that were correctly classified—that is, the percentage of dots to the right of the threshold line that are green in Figure 1:

Precision=TP/TP+FP=0.8

Recall measures the percentage of actual spam emails that were correctly classified—that is, the percentage of green dots that are to the right of the threshold line in Figure 1:

Recall=TP/TP+FN=0.73

Figure 2 illustrates the effect of increasing the classification threshold.

<center><img src="{{ site.url }}{{ site.baseurl }}/blog-post/img/Blog-P&R/8.jpg" style="width:80%"></center>


**Figure 2 Increasing classification threshold.**

The number of false positives decreases, but false negatives increase. As a result, **precision increases, while recall decreases**:

{:class="table table-bordered"}
|True Positives (TP): 7|False Positives (FP): 1|
| :- | :- |
|False Negatives (FN): 4|True Negatives (TN): 18|

Precision=TP/TP+FP=0.88

Precision=TP/TP+FN=0.64

Conversely, Figure 3 illustrates the effect of decreasing the classification threshold (from its original position in Figure 1).

<center><img src="{{ site.url }}{{ site.baseurl }}/blog-post/img/Blog-P&R/9.jpg" style="width:80%"></center>

**Figure 3. Decreasing classification threshold.**

False positives increase, and false negatives decrease. As a result, this time, **precision decreases and recall increases**:

{:class="table table-bordered"}
|True Positives (TP): 9|False Positives (FP): 3|
| :- | :- |
|False Negatives (FN): 2|True Negatives (TN): 16|

Precision=TP/TP+FP=0.75

Recall=TP/TP+FN=0.92


Thus we cannot rely on wither of the two, namely precision and recall, and we often need to look and create a balance between the two of them. Various metrics have been developed that rely on both precision and recall. We will now talk about one such metric- F-score.
# Conclusion

We tend to use accuracy because everyone has an idea of what it means rather than because it is the best tool for the task! Although better-suited metrics such as recall and precision may seem foreign, we already have an intuitive sense of why they work better for some problems such as imbalanced classification tasks. Statistics provides us with the formal definitions and the equations to calculate these measures. [Data science](https://www.datacamp.com/community/podcast/data-science-astronomy) is about knowing the right tools to use for a job and often we need to go beyond accuracy when developing classification models. Knowing about recall, precision and F-score allows us to assess classification models and should make us think skeptically about anyone touting only the accuracy of a model, especially for imbalanced problems.

As we have seen, accuracy does not provide a useful assessment on critical problems, but now we know how to employ smarter metrics.










# References : 

<https://www.jeremyjordan.me/evaluating-a-machine-learning-model/>

<https://developers.google.com/machine-learning/crash-course/classification/precision-and-recall>

<https://towardsdatascience.com/the-mindset-technique-to-understand-precision-and-recall-like-never-before-1a4b80ac551b>

<https://towardsdatascience.com/multi-class-metrics-made-simple-part-ii-the-f1-score-ebe8b2c2ca1>

<https://miro.medium.com/max/900/0*Uw37vrrKzeEWahdB>

<https://www.mage.ai/blog/definitive-guide-to-accuracy-precision-recall-for-product-developers>

<https://en.wikipedia.org/wiki/F-score>

<https://builtin.com/data-science/precision-and-recall>










