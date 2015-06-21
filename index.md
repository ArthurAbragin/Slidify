---
title       : Overfitting
subtitle    : 
author      : Arthur Abragin
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

Overfitting
========================================================



Why is not the most complicated regression model the best?
Let's create the sample of random data (y=x+sin(x)+random noise),choose the type of the model and try to predict several values which was excluded from the train set.
We will see that standart error of the predicted values increases as long as the model becomes more complicated. 

--- .class #id 


R code
========================================================


```r
sample_size<-100
x<-(1:sample_size)*10/sample_size
y<-x+sin(x)+rnorm(sample_size,0,0.3)
```


```r
dat1<-cbind(y,x)
```


```r
modelfit1<-lm(y~x,data=as.data.frame(dat1_train))
```


```r
err1<-sqrt(sum(((dat1_test[,2]-pred1$fit)^2))/10)
```


--- .class #id 

Results
========================================================
Here we can see the difference between standart error of the linear model and(err1) the 10th degree polynomial(err4).

```r
err1
```

```
## [1] 0.2491158
```

```r
err4
```

```
## [1] 0.6995547
```

--- .class #id 

Links
========================================================
GitHub repository
https://github.com/ArthurAbragin/DataProduct

Shiny application
https://arturabragin.shinyapps.io/DataProduct

--- .class #id 
