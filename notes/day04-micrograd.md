Gradient Descent

Gradient descent is the process of improving a neural network by updating its parameters in the direction that reduces the loss.

After a forward pass, the loss measures how wrong the model's predictions are.

Backpropagation computes the gradient of the loss with respect to every parameter.

Each parameter is then updated using:

new_parameter = old_parameter - learning_rate × gradient

The gradient tells us how changing a parameter affects the loss.

If the gradient is positive:

decrease the parameter

If the gradient is negative:

increase the parameter

Repeating this process causes the network to gradually reduce its loss and improve its predictions.

Training Loop
Forward pass
Compute loss
Backpropagation
Calculate gradients
Update parameters
Repeat

This loop is the foundation of neural network training.