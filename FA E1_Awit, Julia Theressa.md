---
title: "FA E1"
author: "Julia Theressa Awit"
course: "APM1110 Probability"
output: pdf_document
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
```

## Problem 13
A malicious spyware can infect a computer system through the Internet or through email. The spyware comes through the Internet 70% of the time and 30% of the time, it gets in through email. If it enters via the Internet, the anti-virus detector will detect it with probability 0.6, and via email, it is detected with probability 0.8.

### (a) Probability that this spyware infects the system
### (b) Probability that the detected spyware came through the Internet

```{r}
p_internet <- 0.7
p_email <- 0.3
detect_internet <- 0.6
detect_email <- 0.8

p_not_detected_internet <- 1 - detect_internet
p_not_detected_email <- 1 - detect_email

p_infect <- (p_internet * p_not_detected_internet) + (p_email * p_not_detected_email)

p_detected <- (p_internet * detect_internet) + (p_email * detect_email)

p_internet_given_detected <- (p_internet * detect_internet) / p_detected

p_infect
p_internet_given_detected
```

## Problem 14
Of the emails you receive, 20% are spam on average. Your spam filter is able to detect 90% of them but also misclassifies as spam 15% of the genuine emails.

### (a) Probability that an email marked as spam is actually spam
### (b) Probability that an email not marked as spam is actually legitimate

```{r}
p_spam <- 0.2
p_legit <- 0.8
detect_spam <- 0.9
misclassify_legit <- 0.15

p_marked_spam <- (p_spam * detect_spam) + (p_legit * misclassify_legit)
p_spam_given_marked_spam <- (p_spam * detect_spam) / p_marked_spam

p_not_marked_spam <- (p_spam * (1 - detect_spam)) + (p_legit * (1 - misclassify_legit))
p_legit_given_not_marked_spam <- (p_legit * (1 - misclassify_legit)) / p_not_marked_spam

p_spam_given_marked_spam
p_legit_given_not_marked_spam
```



