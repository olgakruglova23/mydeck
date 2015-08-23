---
title       : IMDB film analysis
subtitle    : Presentation for Developing Data Products course
author      : Olga Kruglova 
job         : no 
framework   : revealjs        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : default      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
--- bg:blue

## IMDB films by year and rating

Project for Developing Data Products course.

--- 

## 58788 films have been released in 1893-2005.

- Films are labeled by genre and rated by users.
- Rating represents weighted average of votes.

How to navigate in such a wealth of information? Not to worry!
IMDB films will help you!

--- 

## Application features.


- Displays the list of films of chosen genre in chosen year and/or rating ranges.
- Shows the chart of a genre representation over year and/or rating ranges.
- Displays top 10 voted films in chosen genre, year and/or rating range. 

--- 


## Chart example


```r
library(ggplot2)
count <- sapply(movies[, c(18:24)], function(x) {length(which(x == "1"))})
countY <- data.frame(count)
countY$genre <- rownames(countY)
p <- ggplot(countY, aes(x = genre, y = count)) + geom_bar(stat = "identity")
p <- p + ggtitle("Genres on IMDB by year and rating")
p + theme(text = element_text(size = 18), plot.title = element_text(size=18, face = "bold"), 
                               axis.title=element_text(size=16,face="bold"), axis.text.x=element_text(angle=90))
```

<img src="assets/fig/unnamed-chunk-1-1.png" title="plot of chunk unnamed-chunk-1" alt="plot of chunk unnamed-chunk-1" width="700px" height="400px" />


---

## Would you like to know how it works?

- The source code can be found on [Github](http://bit.ly/1KEx70y).
- Application demonstration is on [shinyapps.io](http://bit.ly/1MGJs8L).
- [Developing Data Products course](https://www.coursera.org/course/devdataprod) will teach how to create applications using [Shiny](http://shiny.rstudio.com/) and [Slidify](http://slidify.org/)..... and [Google](www.google.com) is always your friend too!!


