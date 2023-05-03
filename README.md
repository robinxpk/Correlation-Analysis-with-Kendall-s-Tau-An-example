# Correlation analysis with Kendall's tau: An example

## Motivation

During the research for a statistics lecture, I came a across the thread [Pearson's or Spearman's correlation with non-normal data](https://stats.stackexchange.com/questions/3730/pearsons-or-spearmans-correlation-with-non-normal-data). Multiple comments address Kendall's Tau ($\tau$), which is a nonparametric measure of rank correlation with supposedly desireable properties.
Since I never heard of this measure before, I decided to play around with a simple data set and use Kendall's tau as a measure of association:

<img src="Scatter_Plot_Life_Span_vs_Sleep.png" alt= “Scatter-Plot:Life-Span-vs-Sleep” width="55%" height="300">

But before examining this data set further, I'll introduce the basics of Kendall's tau.

## Kendall's tau basics

Tau is a nonparametric measure of association introduced by Maurice G. Kendall in *Rank correlation methods* (You can read this book 
<a href="https://archive.org/details/rankcorrelationm0000kend/mode/2up" target="_blank" rel="noreferrer noopener">here</a> for free. It is easy to read).
It is based on variables of ordinal scale and as a nonparametric measure, **inferences** require - in contrast to Pearson’s coefficien - no assumption regarding the bivariate distribution. Also, Kendall's tau is more intuitive and easier to interpret than Spearman's rho. More on that later.

$\tau$ assesses the association between two ordinal variables by distinguishing between concordant and discordant pairs. A pair is a set of two observations and each observation consists of values for both variable. Because of the ordinal scale that value is a rank. Now we compare the rank of one variable in one observation with the rank of the same variable in the other observation. The rank is either higher or lower. If this is done for both variables, we can determine whether both variables move in the same direction. That is, whether both ranks drop or increase from one observation to the other or whether one rank increases while the other decreases. The former is considered to be a concordant pair, denoted with $P$, and the latter to be a discordant pair, denoted with $Q$. An important property of these pairs is their constant value. A concordant pair is still concordant after interchanging the order in which the observations are considered in.
The difference between all concordant and discordant pairs is denoted by $S = P−Q$. 

For a sample of size $n$, any specific observation can be paired with one of $(n−1)$ other observations. Resulting
in a total of $n(n − 1)$ possible pairs. Due to the mentioned constant value of a pair, only half of the possible
permutations are unique pairs. The caveat to obtain a meaningful value for $\tau$ is to only consider these unique
pairs. Hence, only half of the $n(n−1)$ possible combinations are relevant.
From now on we differentiate between the population value, denoted with $\tau$, and an estimator based on a
sample, denoted by $t$.
The basic formula to calculate Kendall’s coefficient is provided by:
$$t_\alpha = \frac{S}{\frac{1}{2}n(n-1)}$$
