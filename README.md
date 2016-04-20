# Differential-Privacy-for-Smooth-Queries
After running the code on a dataset, you will get a synthetic data set which will preserve differential privacy. The URL of the paper is:http://papers.nips.cc/paper/5011-efficient-algorithm-for-privately-releasing-smooth-queries.pdf 
You can run DP_init generate the type of each attribute (i.e. binary or continuous). 
The command is DP_init [data file] [output of type] (see init.bat)
Before this program, the data should be scaled to [-1,1]. 
Those attributes with values of -1 or 1 are considered "binary" while others are considered "continuous"
You can modify the result if the automatic detect is not correct. (see type.txt)

For those with type "binary", the attributes in synthetic data base contains only two numbers, -1 or 1.
For those with type "other", the attributes in synthetic data base are between -1 and 1.

The you can run DP_LP to generate synthetic data base. 
The command is DP_LP [config file name] (see train.bat)

The config file should contain some parameters of this program (see config.txt). "config.txt" is our default parameters.


The program will generate the synthetic data base in the file given in config file.

Format of input database : each line contain one tip of information separated by comma.(see WDBC_Scaled.csv)


The meaning of each parameter:
R_size 64: the number of basis functions 
C_size 10000: the number of points uniformly sampled from the ellipsoid obtained by PSI
N 100 : the number of discretized points in each dimension  
eps 0.5: Privacy parameters 
m 10000: the size of synthetic database
para_t 3: the upper bound of the degree of basis functions  
sigma 4: the variance of the Gaussian kernel function
n_sample_D 1000: the number of test points
n_sample_Q 10000: the number of test queries, the worst-case error is over these 10000 queries
csv_filename WDBC_scaled.csv: the scaled database(input)
output_filename output.txt: the output synthetic database(output) 
type_filename type.txt: the file indicating the type of each attribute
k 10:the number of the top eigenvectors and eigenvalues
n_PSI 5: the number of iterations
eps_PSI 1: privacy parameter for the Private PCA
delta_PSI 0.00001: privacy parameter for the Private PCA
ellipsR 3: the ratio of the square root of the eigenvalues to the radius of the ellipsoid in each eigenvetor  
pMean_eps 1: privacy parameter for obtaining the private mean of database
isPm1Shrinked 1: restrict the sampling points in [-1,1]^d
