# Assignment-5.3
1. If Z is norm (mean = 0, sd = 1)
Find P(Z > 2.64)
Answer -
pnorm(2.64, lower.tail = FALSE)
[1] 0.004145301

Find P(|Z| > 1.39)
Answer -
2 * pnorm(-1.39)
[1] 0.1645289


2. Suppose p = the proportion of students who are admitted to the graduate school of the University of
California at Berkeley, and suppose that a public relation officer boasts that UCB has historically had a
40% acceptance rate for its graduate school. Consider the data stored in the table UCBAdmissions from
1973. Assuming these observations constituted a simple random sample, are they consistent with the
officerâ..s claim, or do they provide evidence that the acceptance rate was significantly less than 40%?
Use an Î± = 0.01 significance level.
Answer –
Our null hypothesis in this problem is H0 : p = 0.4 and the alternative hypothesis is H1 : p < 0.4. We reject the null hypothesis if ˆp is too small, that is, if
 pˆ − 0.4 √ 0.4(1 − 0.4)/n < −zα,
 where α = 0.01 and −z0.01 is 
> -qnorm(0.99)
[1] -2.326348
> A<-as.data.frame(UCBAdmissions)
> head(A)
     Admit Gender Dept Freq
1 Admitted   Male    A  512
2 Rejected   Male    A  313
3 Admitted Female    A   89
4 Rejected Female    A   19
5 Admitted   Male    B  353
6 Rejected   Male    B  207
>xtabs(Freq ~ Admit, data = A)
Admit
Admitted Rejected 
    1755     2771 
> phat <- 1755/(1755 + 2771)
> (phat - 0.4)/sqrt(0.4 * 0.6/(1755 + 2771))
[1] -1.680919

Our test statistic is not less than −2.32, so it does not fall into the critical region. Therefore, we fail to reject the null hypothesis that the true proportion of students admitted to graduate school is less than 40% and say that the observed data are consistent with the officer’s claim at the α = 0.01 significance level.
