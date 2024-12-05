
<!-- README.md is generated from README.Rmd. Please edit that file -->

# plmphd

<!-- badges: start -->
<!-- badges: end -->

The goal of `plmphd` is to provide a set of functions for a new method
called **“People-Like-Me”** (**PLM**) that can be used to predict the
longitudinal trajectories for the new target individual. The package is
designed to be user-friendly and easy to use. The package is still under
development, but it is already functional and can be used to analyze
data. The difference between the `plmphd` package and other linear mixed
model based methods is that the `plmphd` is designed based on curve
matching and to predict a new out-of-sample target. As we know, the
prediction of the longitudinal trajectory is a challenging task,
particularly when the target individual is not in the training dataset.
The `plmphd` package is designed to address this challenge by using the
curve matching method, to find the matches who are most similar to the
unknown target individual as a donor cohort, then to predict the
longitudinal trajectory for the new target individual only based on the
information from the donor cohort.

An alternative prediction based on linear mixed model is discussed by
Dr. Dimitris Rizopoulos with [dynamic
predictions](https://stats.stackexchange.com/questions/367521/how-does-a-fitted-linear-mixed-effects-model-predict-longitudinal-output-for-a-n).
Here we summarize the key points for the linear mixed model based
prediction: For example, ${\hat{y}}_{oj}$ denotes the observed outcome
data for the new patient $j$, then you can first obtain an estimate, say
$\hat{b}_j^$ of his/her random effects from the posterior
distribution $b_j \mid \hat{y}\_{oj}, \theta$, where $\theta$ denotes
the model parameters. For example, $\hat{b}\_j^*\$ is the mean of this
posterior distribution. Given this estimate of his/her random effects,
you calculate predictions using $x\_j(t)\beta + z_j(t)\hat{b}\_j^*$,
where $x_j(t)$ and $z_j(t)$ denote the design matrices for the fixed and
random effects at the (future) time points of interest, and $\beta$
denotes the fixed effects. Standard errors for these predictions can be
obtained using a Monte Carlo scheme. For models fitted by `lme()` you
can obtain these predictions using function `IndvPred_lme()` from
package
[JMbayes](https://cran.r-project.org/web/packages/JMbayes/index.html);
also you can obtain the same type of individualized predictions using
the `predict()` method for models fitted by the `mixed_model()` function
of the [GLMMadaptive](https://drizopoulos.github.io/GLMMadaptive/)
package.

For the function `people-like-thee()` in `plmphd` package, it is
designed to predict the longitudinal trajectories with dynamic
prediction function adapted from Dr. Dimitris Rizopoulos function for
`lme4::lmer()` (which can only `nlme::lme()` fuction). The function is
designed to be user-friendly and easy to use.

The `plmphd` package is still under development, but it is already
functional and can be used to analyze data. Here we provide the basic
exmaples and simulated dataset in the `plmphd` package.

## Installation

You can install the development version of `plmphd` from
[GitHub](https://github.com/) with:

``` r
# install.packages("devtools")
devtools::install_github("Goodgolden/plmphd")
```

## Example

This is a basic example which shows you how to solve a common problem:

What is special about using `README.Rmd` instead of just `README.md`?
You can include R chunks like so:

You’ll still need to render `README.Rmd` regularly, to keep `README.md`
up-to-date. `devtools::build_readme()` is handy for this.

You can also embed plots, for example:

In that case, don’t forget to commit and push the resulting figure
files, so they display on GitHub and CRAN.
