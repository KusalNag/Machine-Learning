This repository has Projects related to machine learning and reinforcement learning
K-Means Clustering from Scratch:
The goal of this project is to build a unsupervised model to classify images into their respective classes, using the cifar10 dataset. In the first part of the assignment, I have built a K means clustering model from scratch.
**2 Data**
I have imported the cifar10 dataset from ‘keras.datasets’. It has images from 10 different classes:
1. Airplane
2. Automobile 3. Bird
4. Cat
5. Deer
6. Dog
7. Frog
8. Horse 9.Ship
10. Truck
I have used only the test data from this data set which has 10,000 32x32 color images.

**3 Python Editor**
I have used Jupiter Notebook IDE in Anaconda Navigator
**4 Part 1: Implement K-Means Clustering** 

**4.1 K-Means implementation**
• Step1-Converted the color images into greyscale images.
• Step2-Chose 10 random points from the data as centroids.
• Step3-Calculated labels for all the points using Euclidian
distance from the points to each centroid and set the label to closest centroid.
𝑍 = min⁡(Σ(√(𝑥1 − 𝑥2)2)
• Step4-Using the labels calculated the mean of that cluster and updated the centroids with their means.
• Step5-Calculated the labels with the new clusters
• Step6- iterate through step 4 and 5 until labels in n-1th iteration and nth iteration are equal.
Label frequency after convergence are :
[ 0, 702]
[ 1, 984]
[ 2, 987]
[ 3, 1135]
[ 4, 721]
[ 5, 950]
[ 6, 1626]
[ 7, 1061]
[ 8, 814]
[ 9, 1020]
**4.2 Calculating Silhouette Score and Dunn’s Index**
Silhouette score:
Silhouette score is used to identify how far or close each cluster is to each other. The range of Silhouette score is [-1,1]. A score of -1
means that the clusters are merging into each other an a score of 1 denotes they are distinct from each other.
Therefore a silhouette score of -1 indicates bad clustering and a score of 1 indicates the clusters are well formed.
**Dunn’s Index:**
The Dunn Index is the ratio of the smallest distance between observations not in the same cluster to the largest intra-cluster distance. The Dunn Index has a value between [0,infinity] , and should be maximized.
**5 Part-2:Auto-Encoders and Kmeans**
For the second part of the assignment I have designed an autoencoder in order to retrieve the sparse representation of the input images( encoder part) and then retrieve almost similar image from that sparse representation (decoder or reconstruction part).
Some applications of autoencoders are:
• Imagecompression(lossy) • Dimensionality reduction • Featureextractionetc.
The main idea of autoencoders is that the whole image can be reduced to a minimal form which can almost all the significant features of an image and these features are of the highest significance.
It is a lossy compression and decompression meaning that the image obtained after decoding the compressed image is not the replica of the original image rather varies slightly.
**5.1 Auto-Encoders implementation**
Encoder:
• I have created a feedforward neural network which takes cifar10 images as input
• It flattens the image from 32*32*3 to 3072 neurons in input layer
• It is then connected to a 120 neuron dense layer which holds the compressed images.
• The encoder model is created with these input and outputs.
Decoder:
• The input from the encoder(compresseddata)is taken as input to the Decoder part.
• It is then connected to another dense layer which has 3074 neurons( flattened image pixel).
• It is then resized to the color image 3D structure 32*32*3 which is the output of the Decoder.
Autoencoder:
• Theinputlayeroftheencoderandtheoutputlayerofthe
decoder are the starting and ending points of the autoencoder.
 
• I have taken adamax as the optimizer and meansquared error as loss function.
• The input and the expected output are same for autoencoders as we want to reconstruct the same image again.
I have compressed the original image size of 3074 to 120 which is around 3% of the original size and reconstructed the images from that 3%.
Hence there will be some missing/blurred features in the reconstructed images.

