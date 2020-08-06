# Drug_discovery_project_documentation

## How to get ready?  
### Get ready for GNN  
[GNN Tutorials summary](https://medium.com/@jim.morris.shen/graph-neural-networks-5df67d78f262?source=friends_link&sk=7158f6cc1ba9931a5e2b4d1f81447ed0)

### Get ready to use DGL and Pytorch  
Please read the official document of DGL and Pytorch. 
For advanced knowledge about how to use Pytorch, please read this article.
[How to understand Pytorch Source Code?](https://medium.com/@jim.morris.shen/how-to-understand-pytorch-source-code-1fdbdbbf007e)

### Get ready for the Autoencoder  
[AE, VAE, and VGAE](https://medium.com/@jim.morris.shen/ae-vae-and-vgae-79802b6fe0af?source=friends_link&sk=20eb11c53ea7efc3b71e91e85f3cc219)

## Papers we used for this project  
This project is mainly based on three papers:
- [Variational Graph Auto-Encoders](https://arxiv.org/abs/1611.07308)
- [GIN](https://arxiv.org/abs/1810.00826)

## Network structure  
We have TWO PARTS:
1. Unsupervised machine learning part.
2. Supervised machine learning part. '
For the first part, we have two branches, one is used to predict the adjanct matrix as the VGAE paper. One is used to predict the Fingerprint.
So, in total, we have three branches as shown in the [network architecture](./network_structure.png).


## Branch 3: Graph classification tutorial  
The graph calssification is based on the GIN. tutorial can be found from [Tutorial of Graph Classification by DGL](https://medium.com/@jim.morris.shen/tutorial-of-graph-classification-by-dgl-75baa9478c16?source=friends_link&sk=44b0c49061390ab9ae946f1b8b9a0f6e)

## Branch 1 and 2 
Branch 1 and 2 is essential a GAE. It is using the GAE model introducted in the VGAE paper. At the same time, the encoder network is replaced to the network of GIN.
Detail of the network structure can be found from [Here](https://docs.google.com/presentation/d/1QVJ7PIigq2_PYAqfscvivH7Qml0zFtXLm0Vl30Kcg78/edit?usp=sharing)

## Code for the whole system  
Code of the whole system can be get from the github. It is a private repo, please sending email to jim.morris.shen@gmail.com to ask for accessing.
https://github.com/liketheflower/graph_classification_jak
