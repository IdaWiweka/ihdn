---
layout: tutorial
title: Data Visualization in R
author: IHDN Team
date: 2024-03-20
category: R
tags: [R, visualization, ggplot2, plots]
---

# Data Visualization in R

This tutorial covers the basics of data visualization in R using both base R and the popular ggplot2 package.

## Base R Plotting

R comes with powerful built-in plotting capabilities:

```r
# Create sample data
x <- 1:10
y <- x^2

# Basic scatter plot
plot(x, y, 
     main = "Simple Scatter Plot",
     xlab = "X values",
     ylab = "Y values",
     col = "blue",
     pch = 19)
```

## Using ggplot2

ggplot2 is a more modern and flexible plotting system:

```r
# Install and load ggplot2
if (!require(ggplot2)) install.packages("ggplot2")
library(ggplot2)

# Create a sample dataset
data <- data.frame(
  x = 1:10,
  y = (1:10)^2,
  group = rep(c("A", "B"), each = 5)
)

# Create a ggplot
ggplot(data, aes(x = x, y = y, color = group)) +
  geom_point() +
  geom_line() +
  theme_minimal() +
  labs(
    title = "Sample Plot with ggplot2",
    x = "X values",
    y = "Y values"
  )
```

## Common Plot Types

### Bar Plots

```r
# Create sample data
categories <- c("A", "B", "C", "D")
values <- c(10, 20, 15, 25)

# Base R bar plot
barplot(values, 
        names.arg = categories,
        col = "steelblue",
        main = "Simple Bar Plot")

# ggplot2 bar plot
ggplot(data.frame(categories, values), 
       aes(x = categories, y = values)) +
  geom_bar(stat = "identity", fill = "steelblue") +
  theme_minimal()
```

### Box Plots

```r
# Create sample data
set.seed(123)
data <- data.frame(
  group = rep(c("A", "B", "C"), each = 30),
  value = rnorm(90)
)

# Base R box plot
boxplot(value ~ group, data = data,
        main = "Box Plot by Group",
        col = c("lightblue", "lightgreen", "lightpink"))

# ggplot2 box plot
ggplot(data, aes(x = group, y = value, fill = group)) +
  geom_boxplot() +
  theme_minimal()
```

## Customizing Plots

### Adding Themes

```r
# Install and load additional themes
if (!require(ggthemes)) install.packages("ggthemes")
library(ggthemes)

# Create a plot with different themes
p <- ggplot(data, aes(x = x, y = y)) +
  geom_point() +
  labs(title = "Themed Plot")

# Try different themes
p + theme_economist()  # Economist theme
p + theme_wsj()       # Wall Street Journal theme
p + theme_tufte()     # Tufte theme
```

## Saving Plots

```r
# Save as PNG
png("my_plot.png", width = 800, height = 600)
plot(x, y)
dev.off()

# Save ggplot
ggsave("my_ggplot.png", 
       plot = p,
       width = 8,
       height = 6,
       dpi = 300)
```

## Next Steps

In the next tutorial, we'll cover:
- Interactive visualizations with plotly
- Creating dashboards with shiny
- Advanced ggplot2 techniques
- Custom themes and styles 