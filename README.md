# adaptiveImpute

This repository contains 

1) R codes for Figures 1-4 and Tables 1-4 which appear in Section 5 in the paper "Intelligent Initialization and Adaptive Thresholding for Iterative Matrix Completion; Some Statistical and Algorithmic Theory for Adaptive-Impute", and

2) an R package 'AdaptImpute' which implement the Adaptive-Impute algorithm proposed in the paper above. To install this R package, 

    - first, download 'AdaptImpute_0.1.0.tar.gz' file
    - second, run the following R codes to install the package from 'AdaptImpute_0.1.0.tar.gz' file,
          install.packages("...(dir).../AdaptImpute_0.1.0.tar.gz",repos=NULL)
      where ...(dir)... should be the directory which contains 'AdaptImpute_0.1.0.tar.gz' file.
    - third, run the following R codes to load and attach 'AdaptImpute' package,
          library(AdaptImpute)
    - the main function for matrix completion is called 'adaptImpute'. Here is an example: 
    
          n = 500
          d = 100
          r = 5
          
          ## create an underlying low-rank matrix, M0
          A = matrix(runif(n*r,-5,5),n,r)
          B = matrix(runif(d*r,-5,5),d,r)
          M0 = A %*% t(B)
          
          ## add noises to M0
          ## create a fully observed noisy low-rank matrix, Mf
          err = matrix(rnorm(n*d),n,d)
          Mf = M0+err
          
          ## observe only 10% of the entries of Mf
          ## unobserved entries are marked as zeros
          p = 0.1
          y = matrix(rbinom(n*d,1,p),n,d)
          dat = Mf*y
          
          ## matrix completion via Adaptive-Impute
          out = adaptImpute(M.p=dat,r=r)

    - For more details about the function 'adaptImptue', run the following R codes
          ?adaptImpute
      or
          help(adaptImpute)
