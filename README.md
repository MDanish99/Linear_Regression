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


### Assumptions for Linear Regression are as follows:

#### Linearity:
This assumption means that the model should be in a correct functional form, it should be noted that it does not implies that equation should be in linear form. For example:

<a href="https://www.codecogs.com/eqnedit.php?latex=\dpi{150}&space;y&space;=&space;a&space;&plus;b(x)&space;&plus;c(x^2)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\dpi{150}&space;y&space;=&space;a&space;&plus;b(x)&space;&plus;c(x^2)" title="y = a +b(x) +c(x^2)" /></a>

The above equation (with y as dependent variable and x as explanatory variable) is quadratic but it's in linear form and hence can be used as a linear regression model. It can be re-written in this form which may help to understand it better:

<a href="https://www.codecogs.com/eqnedit.php?latex=\dpi{150}&space;y&space;=&space;a&space;&plus;&space;b(\Theta{}')&space;&plus;&space;c(\Theta&space;{}'')" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\dpi{150}&space;y&space;=&space;a&space;&plus;&space;b(\Theta{}')&space;&plus;&space;c(\Theta&space;{}'')" title="y = a + b(\Theta{}') + c(\Theta {}'')" /></a>

where 

<a href="https://www.codecogs.com/eqnedit.php?latex=\dpi{150}&space;\Theta&space;{}'=&space;x\:\:&space;\:&space;\:&space;\:&space;\:&space;\:&space;\Theta&space;{}''=&space;x^{2}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\dpi{150}&space;\Theta&space;{}'=&space;x\:\:&space;\:&space;\:&space;\:&space;\:&space;\:&space;\Theta&space;{}''=&space;x^{2}" title="\Theta {}'= x\:\: \: \: \: \: \: \Theta {}''= x^{2}" /></a>

How to check: Plot the residuals against the explanatory variable, they should be evenly spread across 0, hence implying linearity.



#### No Hetroskedasticity (constant error variance):
It simply means that variance among the errors should be constant and should not deviate with respect to changes in value of explanatory variables.

Goldfeld-Quandt test or Breusch-Pagan test can be carried out to test this assumption.

#### Independent Error Terms (no auto-correlation):
Let's say we have a regression model where time is one of the explanatory variables. Hence, each value of this variables relates to the previous variables, hence auto-correlation problem can exist here.

Durbin-Watson or Breusch-Godfrey test can be carried out to test this assumption.

#### Normality of Errors:
It means that erros should make a bell-shaped distribution or errors should follow an approximately normal distribution

Histogram or QQ-Plot can be made to test this assumption.

#### No multicollinearity:
Multicollinearity exists when the explanatory variables are themselves related. It can be of two types:

Structural multicollinearity: Can be caused creating new predictor variables such as using X and X^2 both in the regression models, clearly there is some correlation between X and X^2.

Data multicollinearity: This type of multicollinearity is present in the data itself rather than being an artifact of the model.

Checking Correlation between Variables or VIF (Variance Inflation Factor) can help with testing this assumption.

#### Exogeneity:
It means that that a particular variable is independent and hence not affected by other variables in the system.

Let's say we create the model:

<a href="https://www.codecogs.com/eqnedit.php?latex=y&space;=&space;\alpha&space;&plus;&space;\beta&space;x&space;&plus;&space;\epsilon&space;\:&space;\:&space;\:&space;\:&space;\:&space;\:&space;\:&space;\:&space;\:&space;\:&space;\:&space;\:&space;where&space;\:&space;\:&space;\:&space;\:&space;\epsilon&space;=&space;Error\:&space;Terms" target="_blank"><img src="https://latex.codecogs.com/gif.latex?y&space;=&space;\alpha&space;&plus;&space;\beta&space;x&space;&plus;&space;\epsilon&space;\:&space;\:&space;\:&space;\:&space;\:&space;\:&space;\:&space;\:&space;\:&space;\:&space;\:&space;\:&space;where&space;\:&space;\:&space;\:&space;\:&space;\epsilon&space;=&space;Error\:&space;Terms" title="y = \alpha + \beta x + \epsilon \: \: \: \: \: \: \: \: \: \: \: \: where \: \: \: \: \epsilon = Error\: Terms" /></a>

In the above model, 𝑦 is wages and 𝑥 is a metric that is an indicator for a college degree. Let's suppose there is some other ability and we are not aware of it. We will be using the above model while the true model would be one mentioned below.

The true model is:
<a href="https://www.codecogs.com/eqnedit.php?latex=y&space;=&space;\alpha&space;&plus;&space;\beta&space;x&space;&plus;&space;\gamma&space;z&space;&plus;&space;\epsilon" target="_blank"><img src="https://latex.codecogs.com/gif.latex?y&space;=&space;\alpha&space;&plus;&space;\beta&space;x&space;&plus;&space;\gamma&space;z&space;&plus;&space;\epsilon" title="y = \alpha + \beta x + \gamma z + \epsilon" /></a>

𝑧 is some metric which measures the ability. If wages are a function of both education and ability, and college graduates are expected to have higher ability because college tends to attract and admit higher ability students, then if one were to run a simple regression of wages on education, the strict exogeneity assumption would be violated. In that case, we cannot use the model to infer causation.






