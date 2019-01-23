### Purpose
This repository is about implementation and improvement of the paper **A link prediction approach for item recommendation with complex numbers**

#### Here is BibTeX of the paper 
`
@article{xie2015link,
  title={A link prediction approach for item recommendation with complex number},
  author={Xie, Feng and Chen, Zhen and Shang, Jiaxing and Feng, Xiaoping and Li, Jun},
  journal={Knowledge-Based Systems},
  volume={81},
  pages={148--158},
  year={2015},
  publisher={Elsevier}
}
`
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

### About Dataset ( [MovieLens 100k](http://files.grouplens.org/datasets/movielens/ml-100k-README.txt) )

 MovieLens 100k dataset was collected during the seven-month period from September 19th, 1997 through April 22nd, 1998 by the GroupLens Research Project at the University of Minnesota. The dataset consists of 100,000 ratings from 943 users on 1682 movies. Those ratings are scaled 1-5. Furthermore, each user has rated at least 20 movies in the dataset.<br>
 
**u.data**, is full dataset randomly ordered and tab separated list of user id, item id, rating and timestamp, is considered.  

 [Download MovieLens 100k](http://files.grouplens.org/datasets/movielens/ml-100k.zip)


### Method

The implementation of CORLP method and further improvement of it are developed using Python programming language on Google Colab. 

<p align="center">
  <img src="./images/table_of_libraries.png">
  <br>
  Table 1. Libraries used in Python
</p>


