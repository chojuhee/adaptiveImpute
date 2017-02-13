# adaptiveImpute

This repository includes R functions and the corresponding manuals to implement the Adaptive-Impute algorithm proposed in the paper
"Intelligent Initialization and Adaptive Thresholding for Iterative Matrix Completion; Some Statistical and Algorithmic Theory for 
Adaptive-Impute". Below, we provide descriptions for the files in this repository.


Adi_Rfunction (original) : the original R codes implementing Adaptive-Impute
Adi_manual (original)    : manuals for "Adi_Rfunction (original)". It includes usage, arguments, values, and examples for the R function, 
                            adaptiveImpute, from the file "Adi_Rfunction (original)".

Adi(without truncation)_Rfunction : a faster version of the original Adaptive-Impute. It can be used when the data entries are not bounded
                                      and so do not need to be truncated.
Adi(without truncation)_manual    : manuals for "Adi(without truncation)_Rfunction". It includes usage, arguments, values, and examples for 
                                      the R function, fastAdi, from the file "Adi(without truncation)_Rfunction".
                            
