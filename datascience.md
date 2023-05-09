
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

# gym and universe
# nlp 

## t sne

supervised dimensionality reduction algorithm that is used to go from a high dimensional space to two or three dimensions so that we can visualize the data
sne uses a gaussian and t sne uses a student t distribution
meaning the t sne is more robust to outliers
the decay for t sne is 1 - 1/(1 + d*2) where d is the distance between two points 

loss is minimized using gradient descent

early exaggeration is used to make the attraction between points more pronounced at first before repulsion takes over

a good heuristic is to multiply attractive forces by 12 for 250 iterations [1](https://distill.pub/2016/misread-tsne/)


perplexity is a measure of how many neighbors each point has

the general heuristic is to use perplexity 30 and then knn 3 times the perplexity - only calculating the 90 nearest neighbors reduces complexity from O(n^2) to 90

you can also use approximate nearest neighbors to reduce complexity

barnes hut is an algorithm that uses a quadtree coming from physics simulations of multiple bodies

uniform affinity kernel means that the probability of a point being a neighbor is the same for all points

a gaussian distribution is equivalent to a t distribution with infinite degrees of freedom - cauchy distribution is equivalent to a t distribution with 1 degree of freedom

you can vary the distribution to change the tails and group things better or worse




## word2vec
s
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

a pytorch dataset is an object that has two methods __len__ and __getitem__

getitem allows you to index into the dataset like a list `dataset[i]`

len allows you to get the length of the dataset like you would with a list `len(dataset)`




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


## mongo

wiredtiger is the default storage engine for MongoDB 3.2 and later. It is a high-performance storage engine that is designed to handle large amounts of data and provide fast read and write operations. It is also the default storage engine for MongoDB 4.0 and later.

The WiredTiger storage engine uses a set of files to store data. These files are located in the data directory of the MongoDB database. The data directory is specified by the dbpath option in the mongod.conf file. The default location of the data directory is /data/db on Linux and macOS, and C:\data\db on Windows.

The following files are created in the data directory when the MongoDB database is started:

1. mongod.lock - A lock file used by the mongo daemon to ensure only one instance is running.

2. WiredTiger.wt - This is a file that contains the data stored in the MongoDB database.

3. local.0 - This is a file that contains local database information, such as server configuration and authentication settings.

4. storage.bson - This is an index file used by MongoDB for faster retrieval of data.

5. journal - This is a log file that contains a record of all changes made to the database.'

6. WiredTiger.lock - This is a lock file used by the WiredTiger storage engine to ensure only one instance is running.

7. WiredTiger.turtle - This is a file that contains information about the WiredTiger storage engine.

8. WiredTiger.wt - This is a file that contains the data stored in the MongoDB database.

9. WiredTigerLAS.wt - This is a file that contains the data stored in the MongoDB database.


## transformers

Sure, I can provide a toy example of the data fed into a Transformer, explain each step in detail, and give an example of the output.

Suppose we have a simple sequence-to-sequence translation task where we want to translate a sentence from English to French. The input sentence is "I am happy today", and the output sentence should be "Je suis heureux aujourd'hui".

Here's how the data would be preprocessed and fed into the Transformer:

Tokenization: The input sentence is first split into individual tokens or words using a tokenizer. For example, the input sentence would be tokenized into ["I", "am", "happy", "today"].

Embedding: Each token is then converted into a vector representation using an embedding matrix. For example, the token "I" might be represented as the vector [0.5, 0.3, -0.2], "am" might be represented as [0.2, 0.1, 0.4], and so on.

Positional encoding: Since the Transformer model does not inherently capture the order of the tokens, a positional encoding is added to the embedding vectors to indicate their position in the sequence. For example, the embedding vector for "I" might be modified to [0.5, 0.3, -0.2, 0.1, 0.2, -0.1], where the last three values represent the position of the token in the sequence.

Self-attention: The embedded and encoded input sequence is then passed through the self-attention mechanism of the Transformer. The self-attention mechanism calculates the attention weights between all the input tokens, based on their relationships to each other. This attention mechanism allows the model to selectively focus on certain parts of the input sequence and assign higher weights to more relevant tokens.

Multi-head attention: In the multi-head attention step, the self-attention mechanism is repeated multiple times with different sets of learnable parameters, allowing the model to capture different types of relationships between the input tokens.

Feedforward layers: The output from the multi-head attention layer is then passed through a series of feedforward layers, which transform the input vectors using non-linear activations.

Decoding: The output from the feedforward layers is then passed through a decoder, which predicts the output sequence in the target language. This process is similar to the encoding steps described above, but with different learnable parameters and an output vocabulary.

For this toy example, let's assume the Transformer has been trained and outputs the following French translation: "Je suis heureux aujourd'hui". The output sentence would be tokenized into ["Je", "suis", "heureux", "aujourd'hui"], embedded, encoded, and passed through the decoder to generate the final output sequence. The output sequence would then be converted back into text, resulting in the translated sentence "I am happy today".
