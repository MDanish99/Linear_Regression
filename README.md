# Linear_Regression

Regression is all about exploring a relationship between two or more variables, and identifying how strong the relationship is. Linear Regression, as the name tells is to make a linear model, modelling the relationship. Output or the dependent variable is supposed to be a scalar value, whereas the independent or explanatory variables can be scalar or categorical.

Linear Regression with one independent variable is often known as 'Simple Linear Regression' whereas the case where independent variables are more than one is known as 'Multilinear / Multiple Linear Regression'.

It's important to understand the assumptions of Linear Regression. This tutorial will help us to understand the assumptions and we will try to build a linear regression model with a dataset taken from kaggle and then we will try to validate the assumptions.

### Dataset:

#### Columns:

age: age of primary beneficiary

sex: insurance contractor gender, female, male

bmi: Body mass index, providing an understanding of body, weights that are relatively high or low relative to height,
objective index of body weight (kg / m ^ 2) using the ratio of height to weight, ideally 18.5 to 24.9

children: Number of children covered by health insurance / Number of dependents

smoker: Smoking

region: the beneficiary's residential area in the US, northeast, southeast, southwest, northwest.

charges: Individual medical costs billed by health insurance

#### Aim: Predict medical charges (can be also be treated as insurance costs)

Link to the dataset: https://www.kaggle.com/mirichoi0218/insurance


Assumptions for Linear Regression are as follows:

1) Linearity: This assumption means that the model should be in a correct functional form, it should be noted that it does not implies that equation should be in linear form. For example:
2) 
<a href="https://www.codecogs.com/eqnedit.php?latex=y&space;=&space;a&space;&plus;&space;b(x)&space;&plus;&space;c(x^2)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?y&space;=&space;a&space;&plus;&space;b(x)&space;&plus;&space;c(x^2)" title="y = a + b(x) + c(x^2)" /></a>

The above equation (with y as dependent variable and x as explanatory variable) is quadratic but it's in linear form and hence can be used as a linear regression model. It can be re-written in this form which may help to understand it better:

<a href="https://www.codecogs.com/eqnedit.php?latex=\dpi{150}&space;y&space;=&space;a&space;&plus;&space;b(\Theta{}')&space;&plus;&space;c(\Theta&space;{}'')" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\dpi{150}&space;y&space;=&space;a&space;&plus;&space;b(\Theta{}')&space;&plus;&space;c(\Theta&space;{}'')" title="y = a + b(\Theta{}') + c(\Theta {}'')" /></a>

where 

<a href="https://www.codecogs.com/eqnedit.php?latex=\dpi{150}&space;\Theta&space;{}'=&space;x\:\:&space;\:&space;\:&space;\:&space;\:&space;\:&space;\Theta&space;{}''=&space;x^{2}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\dpi{150}&space;\Theta&space;{}'=&space;x\:\:&space;\:&space;\:&space;\:&space;\:&space;\:&space;\Theta&space;{}''=&space;x^{2}" title="\Theta {}'= x\:\: \: \: \: \: \: \Theta {}''= x^{2}" /></a>


