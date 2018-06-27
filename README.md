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
MHCA$Time.Started = as.Date(MHCA$Time.Started)
MHCA = subset(MHCA, Time.Started >  )
dim(MHCA)
```


