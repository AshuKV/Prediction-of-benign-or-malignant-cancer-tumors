# Prediction-of-benign-or-malignant-cancer-tumors
Prediction of benign or malignant cancer tumors Using ML

## Explaination of eigen-vectors and eigen-values and their importance:
In PCA - the eigen-vectors determine the principal direction of the variance and the eigen-values are the magnitude of the variance - they are used to explain the variance in the data along the new principal component.


## The classification methods being used and reason for choosing this method:
I started with logistic regression because it is a simple and easily interepreted linear model used for classification. The results of logistic regression were so good that I did not really need to further explore any other methods. Since, the problem statement is related to the medical domain - the cost of false negatives could be human lives. So, in order to further reduce the amount of false negatives I tried XGBoost because it is a very fast and powerful tree based model. It did not however provide much improvement in performance so I chose to stick with my tuned logistic regression model as the final model due to its interpretability and simplicity.

## Confusion matrix and explaination of how it can help us to check reliability of result:
It helps us check reliability in this case as we are not optimizing for accuracy but for the model have high precision and recall or as low false negatives as possible.

## The learning curve and explaination of how it can help us in determining whether the model is being over-fit or under-fit:
The learning curves shown above inform us that the model is not over fitting (test and train accuracies are similar) and it is not underfitting (all metrics are all very high)

## Adding “regularization parameter” to the model, and how it helps to improve the model performance:
I consider adding regularization to prevent the model from overfitting or becoming too complex. It improves the performance by simplifying the model which will allow it to generalize better on out of sample detection.

## Explaination of how reinforcement-learning can be utilized in fraud detection models:
RL systems have an agent that works in an environment and performs some actions. In this case specifically the agent will act like a fraudster and perform an action (making a transaction) in the environment (banking system + fraud detection system). We can have the action result in a reward which is the transaction is accepted or rejected. In this way the agent will keep getting better at committing fraud and we can use this information to inform other models as to the optimal policy a fraudster would undergo to trick our fraud detection system.

## When to use logistic sigmoid, tanh, and Fourier as basis function:
Sigmoid is normally used as last layer for binary classification problems as it outputs a value constrained between 0 and 1. Hence it is used when we want to output a probability. It is also used sometimes in LSTMs however tanh is preferred in this case as it output ranges from (-1, +1) which allows for increases and decreases in the state which sigmoid would not allow for (0,1 constraint). Tanh is also said to be good at preventing the vanishing gradient problem which is found commonly in RNN/LSTM networks. Fourier transforms are usually used in image transformation domain. I see some research describing it being used in time series data as well as some kinds of convolution networks. However, it is doubtful to me as to where a fourier basis function would be used over sigmoid or tanh.
