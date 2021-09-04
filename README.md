# MoA-Kaggle-Competition-615-of-4373
Mechanisms of Action (MoA) Prediction (Kaggle Competition)

What is the Mechanism of Action (MoA) of a drug? And why is it important?

In the past, scientists derived drugs from natural products or were inspired by traditional remedies. Very common drugs, such as paracetamol, known in the US as acetaminophen, were put into clinical use decades before the biological mechanisms driving their pharmacological activities were understood. Today, with the advent of more powerful technologies, drug discovery has changed from the serendipitous approaches of the past to a more targeted model based on an understanding of the underlying biological mechanism of a disease. In this new framework, scientists seek to identify a protein target associated with a disease and develop a molecule that can modulate that protein target. As a shorthand to describe the biological activity of a given molecule, scientists assign a label referred to as mechanism-of-action or MoA for short.

How do we determine the MoAs of a new drug?

One approach is to treat a sample of human cells with the drug and then analyze the cellular responses with algorithms that search for similarity to known patterns in large genomic databases, such as libraries of gene expression or cell viability patterns of drugs with known MoAs.

In this competition, you will have access to a unique dataset that combines gene expression and cell viability data. The data is based on a new technology that measures simultaneously (within the same samples) human cells’ responses to drugs in a pool of 100 different cell types (thus solving the problem of identifying ex-ante, which cell types are better suited for a given drug). In addition, you will have access to MoA annotations for more than 5,000 drugs in this dataset.

#Conclusions:
My soution to this competition was based on a blend of two models, one based on a simpe artifical neurral netowrk framework an the other is based on a deep tabular data learning architecture (TabNet). This solution got me 615 place out of 4373 competitors.

1) Simple ANN
  a) Transformation of features using QuantileTransformer (RankGauss)
  b) PCA transformation on geens and cells columns.
  c) Feature Selection using Variance Encoding
  d) Split train/test/validation dataset using "MultilabelStratifiedKFold"
  c) Fit a simple ANN arhitecure with only one hidden layer and liniar activation function. Also label smoothing was used in training.

2) What is TabNet ?
TabNet is a Deep Neural Network for tabular data and was designed to learn in a similar way than decision tree based models, in order to have their benefits : interpretability and sparse feature selection. TabNet uses sequential attention to choose which features to reason from at each decision step, enabling interpretability and better learning (as the learning capacity is used for the most salient/important features). The feature selection is instancewise, so it can be different for each input.



