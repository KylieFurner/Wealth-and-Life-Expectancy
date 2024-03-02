---
title: "Wealth and Life Expectancy"
author: "Kylie Furner"
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
# This R-chunk imports all the datasets

library(gapminder)
gap <- gapminder
library(dplyr)
library(ggplot2)
```

## Background

Hans Rosling is one of the most popular data scientists on the web. His original TED talk, The best stats you’ve ever seen set a new bar for data visualization. I am going to create some graphics using his formatted data.

## Data Wrangling


```r
# This R-Chunk cleans & wrangles the data
filteredCountries <- gap %>%
filter(country != "Kuwait")
```

## Data Visualization


```r
# This R-Chunk plots & visualizes the data
ggplot(data = filteredCountries, mapping = aes(x = lifeExp, y = gdpPercap, color = continent, size = pop/100000)) + geom_point() + facet_wrap(~year, ncol = 12) + labs(size = "Population", y = "GDP Per Capita", x = "Life Expectancy", color = "Continent") + scale_y_continuous(trans = "sqrt")
```

![](W02-Wealth-and-Life-Expectancy_files/figure-html/plot_data-1.png)<!-- -->

## Conclusions

In this assignment I learned how to filter data by filtering out the country Kuwait from the data set. I also learned how to use colors and scale to further sort the data. 

