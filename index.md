---
title       : Diamond Pricing App
subtitle    : Never Get Ripped Off Again
author      : 
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : zenburn      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Why Use This App?

1.  The average retail diamond seller markups the price by 100%
2.  Markups as high as 1000% are not unheard of
3.  With 4 available characteristics of a diamond this app can give you a fair asking price

--- .class #id 

## How it Works

Data from 308 diamond sales have been analyzed

A multivariate linear regression model on the data yields an R Squared of .95 suggesting 95% of price variability can be explained by the model


```r
modelFit <- train(price ~ .,data=Diamond,method="glm")
modelFit$results
```

```
##   parameter RMSE Rsquared RMSESD RsquaredSD
## 1      none  757   0.9532  120.4    0.01057
```

---

## Your Prediction

Your prediction is based on the previous model.  The following is the exact formula.  Not surprisingly as the size of your diamond increases the price goes up.  This is by far the largest factor.  As more color is added to the diamond the price decreases.  As the purity of the diamond decreases so does the price.

```
##                  Estimate Std. Error  t value   Pr(>|t|)
## (Intercept)        169.18      255.0   0.6634  5.076e-01
## carat            12766.40      190.0  67.1829 7.622e-181
## colourE          -1439.09      208.0  -6.9193  2.828e-11
## colourF          -1841.69      195.2  -9.4334  1.234e-18
## colourG          -2176.67      200.4 -10.8620  2.420e-23
## colourH          -2747.15      202.9 -13.5385  8.256e-33
## colourI          -3313.10      212.7 -15.5753  2.482e-40
## clarityVS1       -1474.57      159.7  -9.2348  5.243e-18
## clarityVS2       -1792.01      171.2 -10.4682  5.145e-22
## clarityVVS1       -689.29      159.9  -4.3101  2.227e-05
## clarityVVS2      -1191.16      148.8  -8.0074  2.726e-14
## certificationHRD    15.23      107.2   0.1420  8.872e-01
## certificationIGI   141.26      128.3   1.1014  2.716e-01
```

---

## Final Caveat 

The model is dependent on Carat size, Color, and Clarity.  Three of the 4 Cs in diamond grading.  These characteristics, particularly color and clarity are determined by a third party certification process.  It is important that a reputable organization has made the certification or else the color and clarity could be overstated.
