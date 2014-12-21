---
title       : Developing Data Products Project
subtitle    : Registered Deaths from Toronto Open Data
author      : Ryan Seeto
job         : 
framework   : html5slides       # {io2012, html5slides, shower, dzslides, ...}
highlighter : prettify  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : standalone # {standalone, draft}
knit        : slidify::knit2slides

---

## Introduction
This Slidify presentation is created for the November 2014 offering of Coursera's "Developing Data Products."  The purpose of this project is to investigate if there was a difference in the location of deaths of all the deaths registered by the City of Toronto.

---

## Methodology
Data was collected from the [Toronto Open Data](http://www1.toronto.ca/wps/portal/contentonly?vgnextoid=7c4da9552dbfe310VgnVCM10000071d60f89RCRD&vgnextchannel=1a66e03bb8d1e310VgnVCM10000071d60f89RCRD) project.   

The civic centre where the death was registered was not relevant, therefore, the dataset was reshapped to include just the location of death ("Outside City Limits" vs. "Toronto") and the time period.

---

## Results

```r
deathdata <- read.csv("deathdata.csv", sep = "\t")
t.test(deathdata$Outside_City_Limits, deathdata$Toronto)
```

```
## 
## 	Welch Two Sample t-test
## 
## data:  deathdata$Outside_City_Limits and deathdata$Toronto
## t = -31.2612, df = 56.266, p-value < 2.2e-16
## alternative hypothesis: true difference in means is not equal to 0
## 95 percent confidence interval:
##  -960.9268 -845.2009
## sample estimates:
## mean of x mean of y 
##  275.8085 1178.8723
```

A t-test revealed that there are significantly more deaths occuring in Toronto than outside the city limits.

---

## Discussion

The difference in death location may be attributed to the fact that there is a larger population in metropolitan Toronto than outside the city limits.  Further research is warrented before drawing any conclusions.

---

## Closing Remarks

Happy Holidays!


