# DigitRecognition
Classifier trained on the MNIST dataset of handwritten digits. [0 through 9] 
We compare the accuracy of a Logistic Regression Classifier to a Support Vector Machine using 
sklearns LogisticRegression and SVC classes. Hyperparameter tuning of the parameter C which determines 
the (inverse) size of Regularisation (penalty for model complexity), is done in several rounds of five fold cross validation on the training set, using grid-search to find the best parameter setting for each Model. We stop tuning once the efficacy change is less than 0.1%. We train on a random subset of 5000 samples. 

# Statistical Test
5x2 CV 
McNemar

We are comparing classifiers (not learning algorithms that produce classifiers) within a single domain. 
We perform a total of three statistical tests: The 5x2CV and the McNemar test (Dietterich), as well as a 10x10CV test Remco Bouckaert and Eibe Frank (2004) for reproducibility.

# References and related publications

Great General Resource: https://machinelearningmastery.com/statistical-significance-tests-for-comparing-machine-learning-algorithms/

Related Publications: 

https://link.springer.com/article/10.1007/s00586-022-07188-w
https://direct.mit.edu/neco/article-abstract/10/7/1895/6224/Approximate-Statistical-Tests-for-Comparing?redirectedFrom=fulltext

“Approximate Statistical Tests for Comparing Supervised Classification Learning Algorithms” by Thomas Dietterich. 
https://ieeexplore.ieee.org/document/6790639
Review of 5 statistical tests to compare whether one learning tasks outperforms another. 
Common used tests. 
1) A test for the difference of two proportions (high type 1 error (marks difference if there is none)) 
2)  paired-differences t-test (high type 1 error) (dont use)
3) The cross-validated t test (10 fold), very powerful (able to detect differences), high type 1 error. (good in situations where type 2 error is more important)
4) McNemar's test (medium power, low type 1 error) - good for limited data or expensive training (i.e large DNNs)
5) 5x2CV test (powerful and low type 1 error). - good for efficient classification algorithms


Claude Nadeau and Yoshua Bengio 2003 “Inference for the Generalization Error“. 

Remco Bouckaert and Eibe Frank (2004) “Evaluating the Replicability of Significance Tests for Comparing Learning Algorithms”
Reccomend: 100 runs of random resampling or 10×10-fold cross-validation - to long for our purposes.

