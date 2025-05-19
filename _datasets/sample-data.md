---
layout: dataset
title: Sample Dataset
author: IHDN Team
date: 2024-03-20
category: Data
tags: [R, dataset, sample, tutorial]
---

# Sample Dataset

This is a sample dataset for practicing R programming and data analysis.

## Dataset Description

The dataset contains simulated data for a hypothetical study on plant growth under different conditions.

## Loading the Data

```r
# Create sample data
set.seed(123)
plant_data <- data.frame(
  plant_id = 1:100,
  species = sample(c("A", "B", "C"), 100, replace = TRUE),
  height = rnorm(100, mean = 50, sd = 10),
  weight = rnorm(100, mean = 20, sd = 5),
  sunlight = runif(100, 2, 8),
  water = runif(100, 100, 500)
)

# Save the data
write.csv(plant_data, "plant_data.csv", row.names = FALSE)
```

## Data Structure

```r
# View the structure of the data
str(plant_data)

# Get summary statistics
summary(plant_data)
```

## Basic Analysis

```r
# Calculate mean height by species
aggregate(height ~ species, data = plant_data, FUN = mean)

# Create a scatter plot
plot(plant_data$sunlight, plant_data$height,
     main = "Plant Height vs Sunlight",
     xlab = "Sunlight (hours)",
     ylab = "Height (cm)",
     col = as.factor(plant_data$species))
```

## Data Dictionary

| Variable | Description | Type |
|----------|-------------|------|
| plant_id | Unique identifier for each plant | Integer |
| species | Plant species (A, B, or C) | Factor |
| height | Plant height in centimeters | Numeric |
| weight | Plant weight in grams | Numeric |
| sunlight | Daily sunlight exposure in hours | Numeric |
| water | Weekly water intake in milliliters | Numeric |

## Download

You can download the dataset in the following formats:
- [CSV Format](plant_data.csv)
- [RDS Format](plant_data.rds)

## Usage Example

```r
# Load the data
plant_data <- read.csv("plant_data.csv")

# Create a boxplot of height by species
boxplot(height ~ species, data = plant_data,
        main = "Plant Height by Species",
        xlab = "Species",
        ylab = "Height (cm)",
        col = c("lightblue", "lightgreen", "lightpink"))
```

## Related Tutorials

- [Introduction to R](r-introduction.md)
- [Data Visualization in R](r-data-visualization.md) 