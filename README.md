---
title: "MHCA"
output: html_document
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
```
Load data and start filtering for time 

Test subset between month May and July
```{r}
setwd("C:/Users/Matthew.Hanauer/Desktop")
MHCA = read.csv("20180627152112-SurveyExport.csv", header = TRUE)
head(MHCA)
MHCA = separate(data = MHCA, col = Date.Submitted, c("Date", "Extra"), sep = " ")
MHCA$Date = as.Date(MHCA$Date, format = "%m/%d/%Y")
MHCA = subset(MHCA, Date > "2017-05-11")

```


