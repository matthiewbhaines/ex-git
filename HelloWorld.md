---
title: "Hello World"
author: "Matthiew Haines"
date: "2025-01-07"
output: 
  html_document:
    keep_md: true
---


``` r
head(cars)
```

```
##   speed dist
## 1     4    2
## 2     4   10
## 3     7    4
## 4     7   22
## 5     8   16
## 6     9   10
```


``` r
aov1 <- aov(dist ~ speed, data = cars)
summary(aov1)
```

```
##             Df Sum Sq Mean Sq F value   Pr(>F)    
## speed        1  21185   21185   89.57 1.49e-12 ***
## Residuals   48  11354     237                     
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
```


``` r
agricolae::LSD.test(aov1, "speed")$groups
```

```
##        dist groups
## 24 93.75000      a
## 25 85.00000     ab
## 22 66.00000    abc
## 18 64.50000     bc
## 23 54.00000    bcd
## 14 50.50000    bcd
## 20 50.40000     cd
## 19 50.00000     cd
## 17 40.66667    cde
## 16 36.00000   cdef
## 13 35.00000   cdef
## 15 33.33333   cdef
## 10 26.00000    def
## 11 22.50000    def
## 12 21.50000    def
## 8  16.00000    def
## 7  13.00000     ef
## 9  10.00000     ef
## 4   6.00000      f
```


``` r
library(ggplot2)
ggplot(data = cars, aes(x = speed, y = dist)) +
  geom_point()
```

![](HelloWorld_files/figure-html/unnamed-chunk-4-1.png)<!-- -->

