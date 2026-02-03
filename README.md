# Advanced Mathematics Assigment 1:Learning Probability Density Functions using Roll-Number-Parameterized Non-Linear Model

# Objective:
The objective of this assignment is to learn the parameters of a probability density function using a roll-number-parameterized non-linear transformation applied to real-world air quality data.
The NO₂ (Nitrogen Dioxide) concentration values from the India Air Quality Dataset are used as the input feature. Each value is transformed using a roll-number-dependent non-linear function((z = Tr(x) = x + ar*sin(br*x)), and a parametric probability density function is learned for the transformed variable.


# Dataset: 
The dataset used is the India Air Quality Dataset from kaggle, and NO₂ concentration is considered as the input feature.

# Steps Applied:
1.Preprocessing - Missing values in the NO₂ column are removed and Data is treated as a one-dimensional continuous variable.
2.Roll Number Parameterized Transformation - Let x denote the original NO₂ concentration values. Each value is transformed using the following non-linear function: ar=0.05*(r mod 7) br=0.3*(r mod 5 + 1) r is university roll number. This transformation introduces a controlled non-linearity into the data while keeping the original scale intact.
3.Probability Density Function Model- The transformed variable z is modeled using the following PDF: p(z)=c*e^(-lambda(z-mu)^2) mu is mean of the distribution , lambda controls the spread, c is the normalisation constant.
4.Parameter Estimation Method:Method Used: Method of Moments
The parameters are estimated using the Method of Moments, assuming the density is properly normalized.
Mean:μ=E[z]
Variance:Var(z)=1/2λ​⇒λ=1/2Var(z)
c=sqrt(λ/pi)​

# Results:
Learned Parameters:
λ=0.001460436525489001
mu=25.809622897811263
c=0.021560876239314918
