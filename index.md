---
title: "Developing Data Products"
author: "Karthikeyan Ramakrishnan"
highlighter: highlight.js
output: html_document
job: DA
knit: slidify::knit2slides
mode: selfcontained
hitheme: tomorrow
subtitle: Diamond Price Prediction
framework: io2012
widgets: []
---

## Overveiw 

1. This app shall be used for prediction of diamond
2. In General diamond price shall be measured by Carat size
3. As a first step we will build our linear model using dataset DIAMOND


--- .class #id 

## Model Preparation
First load our dataset diamond from UsingR package 

```r
library(UsingR);require(UsingR);data(diamond)
```
Creating our linear model using lm function

```r
fit<-lm(price~carat,data=diamond)
coef(fit)
```

```
## (Intercept)       carat 
##   -259.6259   3721.0249
```
From the co efficient we estimate that 3721.0 dollar increase in price for every carat increase in mass of diamond


--- 

## Prediction

New data shall be loaded in variable name called new


```r
new<-3.75
predict(fit,newdata=data.frame(carat=new))
```

```
##        1 
## 13694.22
```

We predict that for 3.75 mass of diamond price for the same shall be 13694.22 dollar.

--- 

## Plot

Plotting the fitted regression line & data


```r
plot(diamond$carat,diamond$price,xlab="size in carat",ylab="price in $",col="red")
lines(diamond$carat,fit$fitted,col="blue")
```

![plot of chunk unnamed-chunk-4](assets/fig/unnamed-chunk-4-1.png) 







