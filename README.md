# Sentimental-Analysis-Wrapper-and-Filter-Based-Project
1.1 Introduction
Sentimental analysis is the process of extracting conclusions from the opinions of the people on a particular topic. People around the world are connected to each other through an enormous network of social networking sites such as Facebook, Instagram, twitter and some more.
Twitter with a wide range of users (more than 300 million users) and huge data is used by most of the researchers to get informative data to process the public opinion and collect the required feedback. Users communicate through their tweets having abbreviations, slangs, sarcasm, emoticons and much more.

Machine Learning (ML) methods such as Random Forest and XG-Boost are generally the most used ML models for classification and regression.
Here, we have performed sentimental analysis on a dataset acquired from Kaggle which contains tweets expressing the depression level of the people (0 for low and 1 for high) with the help of some wrapper and filter-based bio-inspired algorithms viz. Particle Swarm Optimization (PSO) [1], Grey Wolf Optimization (GWO) [2] .
These models were used to analyze the public opinions by comparing their accuracy to each other along with scatter plot.
 

1.2 Problem Statement
The problem statement for the present work can be stated as follows:
Social media is the hub of public opinion where millions of opinions are shared every few minutes. As more and more people are expressing their thoughts on social media which can be both neutral and polarizing. The problem is to plot public sentiments on the relative topic and monitor it.

Objective of the project is to extract tweets from twitter and extract sentiments out of them and develop a sentimental analysis system using Bio inspired Algorithms using PSO and GWO and various other algorithms to optimise the parameters of various machine learning classifier. The system will analyze text and data and classify it a positive, negative or neutral based on its sentiment.



Methodology
2.1 Natural Language Processing (NLP)
Term Frequency-Inverse Document Frequency (TF-IDF) was used for converting raw data to numerical form so that the machine learning model can understand it.

2.2 Unsupervised Learning 
Principal Component Analysis (PCA) was used to reduce the dimensions to two so that the scatter plotted could be plotted easily.

2.3 Swarm Intelligence
Particle Swarm optimization (PSO) [1] is an optimization technique inspired by the flocking of birds, which searches for optimal feature weights for random forest, XG-boost and hence, resulting in the best accuracy.

Grey Wolf Optimization (GWO) [2] is an optimization technique inspired by the pack of gray wolves and is used for feature selection for machine learning model(here, random forest, XG-boost).

2.4 Models Used
Random Forest [4] is a learning technique that combines multiple decision trees to improve prediction accuracy and reduce overfitting. Each tree is built on a random sample of the data, and at each split, only a random subset of features is considered. The final prediction is made by averaging the outputs of all the trees for regression.

Extreme Gradient Boosting (XG-Boost) [3] is a machine learning algorithm that builds trees sequentially, with each new tree correcting the errors of the previous ones. It uses gradient boosting to optimize predictions and includes features like regularization and parallel processing, making it faster and more accurate compared to many other algorithms. 




Project Work Carried Out
3.1 Language Used
We used Python for the analysis of the dataset.

3.2 Dataset
We acquired a dataset (sentiment_tweets) from Kaggle which was based on twitter tweets and were labelled as per on depression (1 for high and 0 for low). The dataset had more than 10,000 tweets labelled as “message to examine” which were classified into two categories (depression or no depression). 

3.3 Feature Extraction Technique
We used TF-IDF as a vectorizer technique. We imported ‘Tfidfvectorizer’ from ‘sklearn.model_selection’ that converts raw data into numerical features.

3.4 Model 
We used Random Forest [4] and XG-Boost [3] model of machine learning. We imported ‘Random Forest and XG-Boost’ model from the ‘sklearn.ensemble’ and ‘xgboost’. We performed classification on the pre-processed and vectorized data. It is within the objective function of PSO [1] and GWO [2].

3.5 Algorithms
3.5.1 PSO
It is inspired by flocking nature of birds. The birds always fly together following some kind of pattern and abiding by some rules to look for food. The continuously adjust their speed and positions in order to achieve their goal of finding food. The bird closest to food is followed by the other birds. Similarly, the particles here act as the birds and the particle’s  fitness value is calculated by a fitness function and velocity. It has two variables: pBest for personal best and gBest for global variable that indicates the particle closest to food.
The particle’s velocity is calculated as:
v(t+1) = vt+w1*rand * (pBest-p)+w2*rand* (gBest-p)  	(1)
here,
●	vt+1 is the particle’s velocity at time t+1
●	vt is particle’s velocity at time t
●	w1 is weight of local information
●	w2 is weight of global information
●	p is particle’s position
●	rand is some random value
●	pBest is personal best
●	gBest is global best
The particle’s position is calculated as:
xt+1=xt+vt+1	(2)
here,
●	xt+1 is particle’s position at t+1
●	xt is particle’s position at time t


3.5.2 GWO
This algorithm is based on the leadership hierarchy of grey wolves and their hunting habits. Four distinct grey wolves alpha, beta, delta and omega (in hierarchical order) are employed to implement their hierarchy. There are three main steps in this algorithm, of which one is hierarchy management, followed by encircling prey and finally hunting.
Grey wolves surround the prey and mathematically it is represented as:
A = 2*α*r1 - a	(3)
C = 2*r2 	(4)
Xt+1 = Xt - A*D	(5)
here,
●	A and C are coefficient vectors.
●	a linearly decreases from 2 to 0 over the iterations.
●	r1 and r2 are random numbers between 0 and 1.
●	D is the distance between the prey and the wolf.
●	Xt is the current position of the wolf.
●	Xt+1 is the updated position of the wolf.
The hunting process involves the alpha, beta, and delta wolves guiding the omega wolves towards the prey. The omega wolves change their position as per the position of alpha, beta and delta.
Dα = |C*Xα - X(t)| 	(6)
Dβ = |C*Xβ - X(t)| 							(7)
Dδ = |C*Xδ - X(t)| 							(8)
X1 = Xα - A*Dα 							(9)
X2 = Xβ - A*Dβ 							(10)
X3 = Xδ - A*Dδ 							(11)
X(t+1) = (X1 + X2 + X3) / 3						(12)
Xα, Xβ and Xδ are the positions of the alpha, beta, and delta wolves, respectively.
Dα, Dβ and Dδ are the distances between prey and alpha,beta and delta respectively.

Results and Discussion
The results are :
4.1 Output of the PSO AND GWO
The output of the PSO and GWO using random forest and XG-Boost [3] is coming 99% approx. and their scatter graph has been plotted based on the logistic regression accuracy based on the dataset of sentiment tweeter consisting of depression data set.

Table 4.1. Result Table: 
          FILTER BASED	   RANDOM FOREST    	XG-BOOST
  PSO	          0.79	            0.996	         0.995
  GWO	          0.54	            0.996	         0.995

In Table 4.1. The accuracies of PSO and GWO for filter based and wrapper based using ML models of random forest and XG-Boost has been depicted.

Conclusion and Future Work
Analysis of Twitter sentiment falls under the category of mining of text and opinion. We processed the dataset using two different algorithms (PSO, GWO) and then acquired the accuracy. The integration of Particle Swarm Optimization (PSO) and Grey Wolf Optimization (GWO) with filter-based feature selection methods, followed by classification using XG -Boost and Random Forest, demonstrates an effective approach for high-dimensional data processing. PSO and GWO efficiently optimize feature subsets, leading to reduced dimensionality and improved model accuracy. XG-Boost excels in handling complex datasets with high predictive accuracy, while Random Forest ensures robust and interpretable results. 

On comparing the accuracies with each other we found out that PSO had the higher accuracy than GWO. Results presented in the report indicate the performance of PSO and GWO with the help of Random Forest and XG-Boost which are the models of machine learning. Future Work for it focuses on combining PSO and GWO into the hybrid optimization strategies for better feature selection and enhancing computational efficiency for large-scale data sets, integrating feature selection with deep learning classifiers to explore for further improvements.

