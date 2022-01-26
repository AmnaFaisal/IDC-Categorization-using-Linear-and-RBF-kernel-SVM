# IDC-Categorization-using-Linear-and-RBF-kernel-SVM

A machine learning model that will be able to analyze and accurately identify IDC (Invasive Ductal Carcinoma) 
as a step-in categorizing breast cancer subtype. This will enable clinical trials for breast cancer 
identification and subtype categorization to run more smoothly and effectively, simultaneously 
reducing time overhead and error involved. In order to accomplish this task, we will be utilizing 
dataset called Breast Cancer (Wisconsin) Diagnosis dataset that consists of a set of 30 features 
describing the characteristics of the cell nuclei present in the digitized image of a of a fine needle 
aspirate (FNA) of a breast mass. As it is evidently understood, breast tissues consist of multitudes of 
cells, only a few of which are cancerous depending on the stage at which cancer is being diagnosed. 
The mean, standard error (SE) and “worst” or largest (mean of the three largest values) of these 
features were computed for each image, resulting in 30 features. We analyzed the features to 
understand the predictive value for diagnosis. We then created models using two different algorithms 
and used the models to predict the diagnosis.

DATASET AND FEATURES
The dataset that we used was Wisconsin Breast Cancer Database(WBCD). This dataset has been 
widely used in research experiments. Features are computed from a digitized image of fine needle 
aspirate (FNA) of a breast mass. They describe characteristics of cell nuclei present in the image. The 
dataset was uploaded to google colab in the form of a csv file were following ten values features were 
included:
• radius (mean of distances from center to points on the perimeter)
• texture (standard deviation of gray-scale values)
• perimeter
• area
• smoothness (local variation in radius lengths)
• compactness (perimeter^2 / area - 1.0)
• concavity (severity of concave portions of the contour)
• concave points (number of concave portions of the contour)
• symmetry
• fractal dimension (“coastline approximation” - 1)
The mean, standard error (SE) and “worst” or largest (mean of the three largest values) of these 
features were computed for each image, resulting in 30 features.
In order to do classification on a clean dataset, the outliers from the given dataset were removed by 
using IQR(Inter-quartile Range).
After the outliers were identified and removed, the remaining/updated dataset was normalized in 
order to apply PCA(Principal Component Analysis) to learn variance ratio from the data.

SVM:
Support Vector Machine is a supervised learning algorithm that basically divides out target 
classes/labels in an n-dimensional space. It works by creating a decision boundary keeping support 
vectors in mind. SVM tries to maximize the distance of the decision boundary from these support 
vectors. The given dataset was trained and tested using two variations of SVM kernels, namely, ‘linear’ 
and ‘rbf’.
Linear Kernel SVM:
Linear kernel is usually used in case of datasets such that it is linearly separable (can be separated by 
a single line). We are classifying the dataset into just two labels/diagnoses, ‘Malignant(M)’ and 
‘Benign(B)’, thus the use of linear SVC makes sense. Linear kernel functions are also faster than other 
non-linear functions.
Linear Kernel Formula is:
𝐹(𝑥, 𝑥𝑗) = 𝑠𝑢𝑚(𝑥. 𝑥𝑗)
Where, x and xj represent the data we are trying to classify.
PAGE 3
RBF Kernel SVM:
RBF or Radial Basis Function is the go-to kernel for non-linear datasets. Here we use this kernel to see 
if classification of data is better with a linear decision boundary or a non-linear one. 
The formula for RBF is:
𝐾(𝑋1,𝑋2) = exp (
||𝑋1 − 𝑋2||
2
2𝜎
2
)
where,
1. ‘σ’ is the variance 
2. ||X₁ - X₂|| is the Euclidean (L₂-norm) Distance between two points X₁ and X₂.
For the purpose of this project, both of these kernels have been used. They are both trained and tested 
separately and the results for their accuracy are compared to decide which one bodes well for 
classification of dataset into benign and malignant cells.
