
# linear algebra
## scalar
a single numerical value
## vector
a set of numerical values
## matrix
a set of sets of numerical values
## tensor
a tensor is a structure containing n dimensions of data - a matrix, for example, is a 2 dimensional tensor. A sca

# neural networks
Neuron computes weighted sum of inputs:

$Y=activationfunction(\sum(weight*input) + bias)$

## activation function
activation function is typically RELU in modern applications - the identity function above 0 and 0 for x<0



## patterns/features/weights
activations of the neurons in a given layer

## input layer 
beginning of a neural network that brings initial data into the system

## bias
constant which is added to the product of features and weights

## hidden layer
### units/neurons
## output layer

## supervised learning

## self supervised learning

## reinforcement learning
agents interact with environments through actions, recieving rewards and observations in return

## transfer learning
using a model that has already learned foundational patterns

## seq2seq
learning algorithm which translates from one sequence to another

## classification 
predicting whether something is one thing or another

## epoch
one complete pass of the training dataset

# computer vision
## object detection

# word2vec
# gym and universe
# nlp 
# bert
# cnns
# transformers
# cuda
# w&b

# tensorflow
# pandas
# sqlalchemy
# spark
# sql
# pytorch


## tensors
import torch
```python
# 1. Tensors are multidimensional arrays with support for autograd
x = torch.Tensor([1, 2, 3])

# 2. Tensors have a shape and a data type
x.shape # (3,)
x.dtype # torch.float32

# 3. Tensors can be reshaped
x = x.reshape(3, 1)
x.shape # (3, 1)

# 4. Tensors can be filled with zeros or ones
x = torch.zeros((3, 1))
x = torch.ones((3, 1))

# 5. Tensors can be initialized with random values
x = torch.randn((3, 1))

# 6. Tensors can be sliced
x = torch.Tensor([[1, 2, 3], [4, 5, 6], [7, 8, 9]])
x[:2] # first two rows
x[:, 1] # second column

# 7. Tensors can be concatenated
x1 = torch.Tensor([[1, 2, 3], [4, 5, 6]])
x2 = torch.Tensor([[7, 8, 9], [10, 11, 12]])
x = torch.cat([x1, x2], dim=0) # concatenate on the 0th dimension (rows)

# 8. Tensors support element-wise operations
x = torch.Tensor([1, 2, 3])
y = torch.Tensor([4, 5, 6])
x + y # [5, 7, 9]

# 9. Tensors can be used for matrix multiplication
x = torch.Tensor([[1, 2], [3, 4]])
y = torch.Tensor([[5, 6], [7, 8]])
x @ y # [[19, 22], [43, 50]]

# 10. Tensors can be used for automatic differentiation
x = torch.tensor(2.0, requires_grad=True)
y = x**2
y.backward()
x.grad # 4.0
```
## operations
```python
import torch

x_add = x + x
x_sub = x - x
x_mult = x * x
x_div = x / x

# Matrix multiplication
x_mat_mult = torch.matmul(x, x)

# Transpose a tensor
x_t = x.t()

# Compute the inverse of a tensor
x_inv = torch.inverse(x)

# Compute the determinant of a tensor
x_det = torch.det(x)

# Compute the trace of a tensor
x_trace = torch.trace(x)

# Create a diagonal tensor
diag = torch.diag(x)

# Compute the outer product of two tensors
outer_prod = torch.ger(x, x)

# Compute the eigenvalues and eigenvectors of a tensor
eigvals, eigvecs = torch.eig(x, eigenvectors=True)

# Compute the singular values and singular vectors of a matrix
svals, svecs = torch.svd(x)

# Compute the Cholesky decomposition of a matrix
cholesky = torch.cholesky(x)

# Compute the QR decomposition of a matrix
q, r = torch.qr(x)

# Compute the LU decomposition of a matrix  
p, l, u = torch.lu(x)


```




Creating Models: Building neural networks and creating models.

Training Models: Writing code to train models and update parameters.
Saving and Loading Models: Saving and loading models for later use.
Debugging Models: Utilizing the debugging tools for troubleshooting issues.
Transfer Learning: Applying pre-trained models to new data.
Optimizing Models: Using optimization techniques to improve model performance.
Deploying Models: Deploying models to production environments.
Using Data Loaders: Working with data loaders to feed data into models.



# scikit-learn
# data analysis
# data model