# Dimension Reduction

[Dimension Reduction wiki](https://www.wikiwand.com/en/Dimensionality_reduction)

[SOM](https://www.wikiwand.com/en/Self-organizing_map)

### Low-dimension Embedding

For high-dimensional data (e.g., with number of dimensions more than 10) dimension reduction is usually performed prior to applying the k-NN algorithm in order to avoid the effects of `the curse of dimensionality`. 

The curse of dimensionality in the k-NN context basically means that `Euclidean distance` is unhelpful in high dimensions because all vectors are almost equidistant to the search query vector (imagine multiple points lying more or less on a circle with the query point at the center; the distance from the query to all data points in the search space is almost the same).

Feature extraction and dimension reduction can be combined in one step using `principal component analysis (PCA)`, `linear discriminant analysis (LDA)`, or `canonical correlation analysis (CCA)`, or `non-negative matrix factorization (NMF)`  techniques as a pre-processing step, followed by `clustering` by `k-NN` on feature vectors in reduced-dimension space. In machine learning this process is also called `low-dimensional embedding`.

---

# Classification

### Classification

分类就是学习如何根据过去的例子做出预测。

`Classification` is the problem of **identifying to which of a set of categories (sub-populations) a new observation belongs, on the basis of a training set of data containing observations (or instances) whose category membership is known**.   

An example would be assigning a given email into "spam" or "non-spam" classes or assigning a diagnosis to a given patient as described by observed characteristics of the patient (gender, blood pressure, presence or absence of certain symptoms, etc.). Classification is an example of **pattern recognition**. 

An algorithm that **implements classification**, especially in a concrete implementation, is known as a `classifier`.

[from wikipedia]

### K-NN Classifier

In **pattern recognition**, the `k-nearest neighbors algorithm (k-NN)` is a non-parametric method used for classification and regression. 

In both cases, **the input consists of the k closest training examples in the feature space**. In k-NN classification, **the output is a class membership**. 

An object is classified by a majority vote of its neighbors, with the object being assigned to the class most common among its k nearest neighbors (k is a positive integer, typically small). If k = 1, then the object is simply assigned to the class of that single nearest neighbor.

k-NN is a type of `instance-based learning`, or `lazy learning`, where the function is only approximated locally and all computation is **deferred** until classification.

A peculiarity of the k-NN algorithm is that it is sensitive to the local structure of the data.

In the classification phase, k is a user-defined constant, and an unlabeled vector (a query or test point) is classified by assigning the label which is most frequent among the k training samples nearest to that query point.

### Parameter selection - K

The best choice of `k` depends upon the data; generally, larger values of k reduces effect of the noise on the classification,[5] but make boundaries between classes less distinct. A good k can be selected by various heuristic techniques (see hyperparameter optimization). The special case where the class is predicted to be the class of the closest training sample (i.e. when k = 1) is called the nearest neighbor algorithm.


### Data Reduction

Data reduction is one of the most important problems for work with huge data sets. Usually, only some of the data points are needed for accurate classification. Those data are called the prototypes and can be found as follows:

Select the class-outliers, that is, training data that are classified incorrectly by k-NN (for a given k)
Separate the rest of the data into two sets: (i) the prototypes that are used for the classification decisions and (ii) the absorbed points that can be correctly classified by k-NN using prototypes. The absorbed points can then be removed from the training set.


---


# Clustering

### Vecter Quantifization

codebooks vector  
the closest neibourhood   
[k-means clustering](https://www.wikiwand.com/en/K-means_clustering) 

### On-line Algorithm

In computer science, an `online algorithm` is one that can **process its input piece-by-piece in a serial fashion**, i.e., in the order that the input is fed to the algorithm, **without having the entire input available from the start**.

In contrast, an **offline algorithm** is **given the whole problem data from the beginning and is required to output an answer which solves the problem at hand**. In operations research, the area in which online algorithms are developed is called `online optimization`.

As an example, consider the sorting algorithms selection sort and insertion sort: selection sort repeatedly selects the minimum element from the unsorted remainder and places it at the front, which requires access to the entire input; it is thus an offline algorithm. On the other hand, insertion sort considers one input element per iteration and produces a partial solution without considering future elements. Thus insertion sort is an online algorithm.

Note that insertion sort produces the optimum result, i.e., a correctly sorted list. For many problems, online algorithms cannot match the performance of offline algorithms. **If the ratio between the performance of an online algorithm and an optimal offline algorithm is bounded**, the online algorithm is called `competitive algorithm`. [from wikipedia]

### K-means Algorithm

![codebook](https://coolshell.cn/wp-content/uploads/2012/06/K-Means.jpg)
从上图中，我们可以看到，A, B, C, D, E 是五个在图中点。而灰色的点是我们的种子点，也就是我们用来找点群的点。有两个种子点，所以K=2。

K-Means的算法如下：

- 随机在图中取K（这里K=2）个种子点。  
- 然后对图中的所有点求到这K个种子点的距离，假如点Pi离种子点Si最近，那么Pi属于Si点群。（上图中，我们可以看到A,B属于上面的种子点，C,D,E属于下面中部的种子点）  
- 接下来，我们要移动种子点到属于他的“点群”的中心。（见图上的第三步）  
- 然后重复第2）和第3）步，直到，种子点没有移动（我们可以看到图中的第四步上面的种子点聚合了A,B,C，下面的种子点聚合了D，E）。  

求点群中心的算法:

1）Minkowski Distance 公式 —— λ 可以随意取值，可以是负数，也可以是正数，或是无穷大。  
2）Euclidean Distance 公式 —— 也就是第一个公式 λ=2 的情况  
3）CityBlock Distance 公式 —— 也就是第一个公式 λ=1 的情况  