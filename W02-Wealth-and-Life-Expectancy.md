---
title: "Wealth and Life Expectancy"
author: "Kylie Furner"
date: "October 28, 2022"
output:
  html_document:  
    keep_md: true
    toc: true
    toc_float: true
    code_folding: hide
    fig_height: 6
    fig_width: 12
    fig_align: 'center'
---






```r
# Use this R-Chunk to import all your datasets!

library(gapminder)
gap <- gapminder
library(dplyr)
library(ggplot2)
```

## Background

Hans Rosling is one of the most popular data scientists on the web. His original TED talk, The best stats you’ve ever seen set a new bar for data visualization. We are going to create some graphics using his formatted data as our weekly case study.

## Data Wrangling


```r
# Use this R-Chunk to clean & wrangle your data!
filteredCountries <- gap %>%
filter(country != "Kuwait")
```

## Data Visualization


```r
# Use this R-Chunk to plot & visualize your data!
ggplot(data = filteredCountries, mapping = aes(x = lifeExp, y = gdpPercap, color = continent, size = pop/100000)) + geom_point() + facet_wrap(~year, ncol = 12) + labs(size = "Population", y = "GDP Per Capita", x = "Life Expectancy", color = "Continent") + scale_y_continuous(trans = "sqrt")
```

![](W02-Wealth-and-Life-Expectancy_files/figure-html/plot_data-1.png)<!-- -->

## Conclusions

In this assignment I learned how to filter data by filtering out the country Kuwait from the data set. I also learned how to use colors and scale to further sort the data. 

