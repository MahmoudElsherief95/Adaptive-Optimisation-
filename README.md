# Adaptive-Optimisation

In this assignment, the goal is to get familiar with some of the most common (adaptive) **optimisation algorithms**. Essentially, the most common optimisation algorithms are nothing more than variants of gradient descent. Although it is often claimed that stochastic gradient descent outperforms any adaptive learning method when carefully configured, it is often more convenient to use a method that requires less tuning.

### Exercise 1: Stochasticity 

Rather than using plain gradient descent algorithm, a stochastic variant is used to train neural networks. This variant is known as *Stochastic Gradient Descent*, or *SGD* for short. Although this naming scheme seems to suggest that stochasticity is part of the algorithm, it is actually introduced by how we use the data to compute gradients.

Instead of computing the gradients over the entire dataset in one go, the samples in the dataset are split up in more manageable pieces called *mini-batches*. This can speed up the computations significantly and avoids memory problems with very large datasets. Another benefit from mini-batches is that they introduce variation, or *stochasticity*, in the gradient computations. After all, the gradient for each mini-batch will be different to the gradient for other mini-batches or for all samples. This stochasticity can be useful to escape local minima in the optimisation process. To amplify this stochasticity, it is also common to shuffle the samples in the dataset so that mini-batches consist of different samples.

------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
### Exercise 2: Gradient Descent with Momentum 

Another way to keep gradient descent from getting stuck in local minima is to use momentum. Momentum accumulates the gradient directions over different batches and accelerates/decelarates the descent when all gradients point in the same/different direction(s). This also means that the update does not directly use the magnitude of the gradient, but instead focuses on the direction. 

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
### Exercise 3: The Adamax Optimiser

Momentum already provides a way to reduce the importance of the gradient magnitude. 
With adaptive learning rate methods, an attempt is made to ignore most of the magnitude information and the size of the update is mainly controlled by controlling the learning rate. 
One of the most popular first order adaptive methods in practice, is the Adam optimiser.
However, Adam also has a sibling called *Adamax* that typically performs on a similar level.

To understand Adamax, we have to look at the variance as a rescaled $L_2$ norm.
Instead of dividing by the $L_2$ norm, as it is done in Adam, Adamax divides by the $L_\inf$ norm.
This gives rise to the following updates for first and second moment estimates:

<img width="1178" alt="image" src="https://github.com/user-attachments/assets/8a31c84f-d907-47c5-a992-6a158bf55fcd">

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
### Exercise 4: Evaluation and Update 

When using the optimisers to fit a neural network to a given set of data, we can effectively minimise the empirical error. However, we are actually interested in minimising the risk. Therefore, it is also useful to evaluate the network regularly on unseen data.

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
### Exercise 5: Training Logistic Regression

To test your framework, it is best to start with a simple problem.
Therefore, we jump back to assignment one, where we learned that logistic regression is actually a single-layer network.
If your optimiser works correctly, the loss should go down when a sufficiently small learning rate was chosen.

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
### Exercise 6: Training a Multi-layer Network (3 Points)

It would have been silly to do all of this work to train logistic regression.
Something you probably already would have been able to do before the start of this course.
The real goal is to train *deep* networks with multiple layers.
You probably can't wait to build a convolutional network with your framework!

<img width="1505" alt="image" src="https://github.com/user-attachments/assets/27d9abd2-8aa3-4ac2-8660-dbc0d5173776">
