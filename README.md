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
library(data.table)
setwd("C:/Users/Matthew.Hanauer/Desktop")
MHCA = read.csv("20180628090247-SurveyExport.csv", header = TRUE)
head(MHCA)
MHCA = separate(data = MHCA, col = Date.Submitted, c("Date", "Extra"), sep = " ")
head(MHCA)
MHCA$Date = as.Date(MHCA$Date, format = "%m/%d/%Y")
MHCA = subset(MHCA, Date > "2015-11-11")
MHCA = data.frame(MHCA)
```
At some point you need to figure out how to generate the file names automatically, skipping that step for now
So I want to place data into the a new dataset, but just the data not the variable name. 

First just copy over the correct data from Site#

Ok Just change the columns names on the MHCA (actual data set with data) and then subset those variables into a new dataframe.

1. Site#(. in R) = Set ID 
2. Site = Site ID
```{r}

setnames(MHCA, old = c("Site.", "Unit.", "Service.Type", "Client.Type", "X1a", "Helpfulness.of.staff.Interaction", "Courtesy.shown.to.you.by.staff.Interaction", "Concern.of.staff.Interaction", "Attention.to.privacy.Interaction", "Degree.of.confidentiality.Interaction", "Professionalism.of.staff.Interaction", "Opportunity.to.participate.in.decisions.about.your.treatment.Clinical.Program","Extent.to.which.your.individual.needs.were.addressed.Clinical.Program", "Organization.of.weekday.program.schedule.Clinical.Program", "Organization.of.weekend.holiday.program.schedule.Clinical.Program", "Appropriate.therapies.and.interventions.offered.Clinical.Program", "Ability.of.staff.to.talk.with.you.Clinical.Program", "Availability.of.staff.to.talk.with.you.Clinical.Program", "Ease.of.completing.paperwork.Clinical.Program", "Convenience.of.location.of.facility.Access", "Signs.and.directions.to.treatment.areas.Access", "Ability.to.reach.desired.department.or.person.by.phone.Access", "Hours.appointments.are.available.Access", "Length.of.time.between.making.appointment.and.seeing.the.psychiatrist.Access", "Length.of.time.between.making.appointment.and.seeing.the.therapist.counselor.Access", "Time.spent.in.waiting.area.for.your.scheduled.appointment.Access", "Safety.of.the.environment.Environment", "Comfortable.feeling.Environment", "Noise.level.Environment", "Attractiveness.of.the.facility.Environment", "Cleanliness.of.the.facility.Environment", "Provision.of.necessary.convenience.items.Environment", "Desirability.of.food.Environment", "Availability.of.refreshments.or.snacks.Environment", "Arrangements.for.you.to.pay.bill.without.unnecessary.hardship.Finance.Business.Office", "Reasonableness.of.fees.Finance.Business.Office", "Degree.to.which.treatment.helped.you.deal.with.your.problem.complaint.Outcome.and.Reputation", "Willingness.to.return.for.treatment.Outcome.and.Reputation", "Reputation.of.our.organization.Outcome.and.Reputation", "Overall.quality.of.care.and.services.Outcome.and.Reputation", "P1", "P2", "P3", "P4", "P5", "P6", "P7", "P8", "P10", "Other..specify..P10", "Other..specify..P11", "Other..specify..P12", "P13", "P11", "P12", "Comments.", "Date"), new = c("SITE ID", "UNIT ID", "CUSTOMER TYPE", "SURVEY METHOD", "Q1a", "Q2a", "Q2b", "Q2c", "Q2d", "Q2e", "Q2f", "Q3a", "Q3b", "Q3c", "Q3d", "Q3e", "Q3f", "Q3g", "Q3h", "Q4a", "Q4b", "Q4c", "Q4d", "Q4e", "Q4f", "Q4g", "Q5a", "Q5b", "Q5c", "Q5d", "Q5e", "Q5f", "Q5g", "Q5h", "Q6a", "Q6b", "Q7a", "Q7b", "Q7c", "Q7d", "QP1", "QP2", "QP3", "QP4", "QP5", "QP6", "QP7", "QP8", "P10", "P10a", "P11a", "P12a", "P13", "P11", "P12", "COMMENTS", "P9"))
```
Now I need to subset the data for only the columns that I need, which are the ones listed above, then you need to create a unique csv file each each site.
```{r}
MHCA = MHCA[c("SITE ID", "UNIT ID", "CUSTOMER TYPE", "SURVEY METHOD", "Q1a", "Q2a", "Q2b", "Q2c", "Q2d", "Q2e", "Q2f", "Q3a", "Q3b", "Q3c", "Q3d", "Q3e", "Q3f", "Q3g", "Q3h", "Q4a", "Q4b", "Q4c", "Q4d", "Q4e", "Q4f", "Q4g", "Q5a", "Q5b", "Q5c", "Q5d", "Q5e", "Q5f", "Q5g", "Q5h", "Q6a", "Q6b", "Q7a", "Q7b", "Q7c", "Q7d", "QP1", "QP2", "QP3", "QP4", "QP5", "QP6", "QP7", "QP8", "P10", "P10a", "P11a", "P12a", "P13", "P11", "P12", "COMMENTS", "P9")]
head(MHCA)
```
Now create a new dataset for each unit
```{r}

```


