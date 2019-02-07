### Purpose
This repository is about implementation and improvement of the paper **[A link prediction approach for item recommendation with complex numbers](https://www.sciencedirect.com/science/article/abs/pii/S0950705115000568)**.

### Abstract
In the paper, recommendation problem is converted into a link prediction problem. They proposed a novel way for describing the relations "similar vs dissimilar and like vs. dislike" using complex numbers. This technique is called as **CORLP (Complex Representation-based Link Prediction)** and it is the technique which uses complex numbers to represent the like and dislike relations between users and items.

After describing the relations, they created **adjacency matrix A** in Figure 1. Then, they took the nth power (3,5,7,9) of A. Powered matrix contains the estimations. N (10, 20 ... 100) item which is not rated before the users is recommended to each user. Finally, they calculated the hits rate and coverage. 

<p align="center">
  <img src="./images/adjacency_matrix_A.png">
  <br>
  Figure 1. Adjacency Matrix A
</p>

As written in the paper, A<sub>uu</sub> and A<sub>ii</sub> matrices are intentionally left zero. A<sub>ui</sub> represents ratings to like(j) or dislike(-j), depending on the rating is less than the threshold. A<sub>iu</sub> is equal to the transpose of A<sub>ui</sub> multiplied by -1.

For further improvement of the paper, A<sub>uu</sub> and A<sub>ii</sub> matrices will be taken account of by finding **Latent Factors (pu and qi)** of A<sub>ui</sub>. Then, A<sub>uu</sub> and A<sub>ii</sub> is created by applying cosine similarity to pu and qi respectively. After re-creating the matrix A, nth power of A are taken, hits rate and coverage are calculated.

### About Dataset ( [MovieLens 100k](http://files.grouplens.org/datasets/movielens/ml-100k-README.txt) | [Download](http://files.grouplens.org/datasets/movielens/ml-100k.zip) )

 MovieLens 100k dataset was collected during the seven-month period from September 19th, 1997 through April 22nd, 1998 by the GroupLens Research Project at the University of Minnesota. The dataset consists of 100,000 ratings from 943 users on 1682 movies. Those ratings are scaled 1-5. Furthermore, each user has rated at least 20 movies in the dataset.<br>
 
**u.data**, is full dataset randomly ordered and tab separated list of user id, item id, rating and timestamp, is considered. Also, A<sub>ui</sub> is created using u.data. 

### Terminology

**Latent Factor** is technique for matrix factorization. It is good for answer the "How to estimate missing rating?" question. With this technique, original matrix is divided by two matrices called **p<sub>u<sub>** and **q<sub>i<sub>**. Original matrix dimension is reduced and optimization, SGD (Stochastic Gradient Descent) process, can be done on it. So that, sparsity problem on the dataset is prevented.
  
**Hits rate** corresponds to ability to recommend relevant items to user.<br>
**Coverage**  corresponds to the percentage of items the system can recommend.

<p align="center">
  <img src="./images/formulas_hitsrate_coverage.png">
  <br>
  Figure 2. Hits Rate and Formula
</p>

### Requirements

The implementation of CORLP method and further improvement of it are developed using Python programming language on Google Colab. 

<p align="center">
  <img src="./images/table_of_libraries.png">
  <br>
  Table 1. Libraries used in Python
</p>

### Methodology 
| ![CORLP](./images/method_paper.png) | ![CORLP with Latent Factor](./images/method_latent.png)
|:---:|:---:|
| CORLP | CORLP with Latent Factor | 

### (File Not Added Yet.) Comparison of Two Method 
Three different tests are conducted.<br>
**Test 1**: Adjacency Matrix is powered by 3, 5, 7, 9. <br>
**Test 2**: Threshold value for converting complex number were changed to 3, 4, 5. In this case, only A<sup>3</sup> is considered.<br>
**Test 3**: Effect of different threshold value for cosine similarity was tested. Threshold is changed 0 to 0.5.<br>

Please, check **results.pdf** file for the test results.
 
### Developers  :computer:
- _Şafak Akıncı (@safak17)_<br />
  _https://github.com/safak17_
- _Ahmet Gökçe Bozan (@gkca)_<br />
  _https://www.github.com/gkca_
