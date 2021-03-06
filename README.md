# PLNet: Network inference for poisson log-normal model based on Dtrace method

> PLNet is a package for calculating the precision matrix of poission log-normal model using moment method and dtrace loss. We first calculate the covariance matrix by moment method and then calculate the precision matrix by dtrace loss using R package EQUAL.

## Installation
**PLNet** is available on [Github](https://github.com/XiDsLab/PLNet).

### R Package installation
- Before installing **PLNet** package, please install **cescwang85-EQUAL-da9cbbb.tar.gz** on [Github](https://github.com/XiDsLab/PLNet).
- For the development version, use the github install
```{r package github, eval = FALSE}
remotes::install_github("https://github.com/XiDsLab/PLNet")
```

## Usage and main functions
The package comes with a simulation data and a single-cell RNA sequence data about Interferon β-Stimulated PBMCs to present the functionality of main function.

### PLNet
```{r load PLNet, eval = FALSE}
library(PLNet)

## simulation data for testing
data("obs_mat")
PLNet_res_sim<-PLNet::PLNet(obs_mat = PLNet::obs_mat,
Sd_est = "GMPR",lambda_vec = NULL , n_lambda = 50 , lambda_valuemax0 = 10,penalize.diagonal = TRUE)

## real data analysis
data("realdatamatrix")
PLNet_res_real<-PLNet::PLNet(obs_mat = PLNet::realdatamatrix,
Sd_est = "GMPR",lambda_vec = NULL , n_lambda = 50 , lambda_valuemax0 = 10,penalize.diagonal = TRUE)
```

### data_generator
```{r, warning = FALSE}
library(MASS)
data_generator_res<-PLNet::data_generator(n = 100, p = 50, densy_degree = 0.05,
sd_ls = 0.1, mean_ls = log(10),value_nondiagonal = 0.3)
```


## Reference

Please cite our work using the following references:
