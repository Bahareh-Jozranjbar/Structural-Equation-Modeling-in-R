# Structural Equation Modeling in R

This repository demonstrates how to perform Structural Equation Modeling (SEM) using the [`lavaan`](https://lavaan.ugent.be/) package in R. The model is based on a sample dataset provided by UCLA and examines the relationships between latent constructs such as *personality* and *academic performance*.

## Overview

This project walks through a simple SEM workflow:

1. Loading and inspecting a dataset
2. Defining a measurement and structural model
3. Fitting the model using `lavaan`
4. Evaluating model fit
5. Visualizing the SEM diagram

## Dataset

The dataset comes from UCLA Statistical Consulting Group and contains the following observed variables:

- **Personality indicators**: `motiv`, `harm`, `stabi`
- **Academic indicators**: `verbal`, `read`, `arith`, `spell`
- **Predictor variables**: `ses` (socioeconomic status), `ppsych` (parental psychology)

The file is read directly from this source:
```r
data_url <- "https://stats.idre.ucla.edu/wp-content/uploads/2021/02/worland5.csv"
```
## Model Specification
- Two latent variables are defined:

personality measured by motiv, harm, stabi

academic measured by verbal, read, arith, spell

- Structural regressions are set as:

personality ~ ses + ppsych

academic ~ ses + ppsych + personality

ppsych ~ personality

- Additionally, some correlated residuals are included based on model modification indices.

Key R Packages
lavaan - for specifying and fitting SEM models

semPlot - for creating visual diagrams of SEM models

## How to Run
Open the .Rmd or .R file

## Install required packages:

```r
install.packages(c("lavaan", "semPlot"))
Knit or run all cells to generate summary output and SEM plot
```
## Outputs
Model fit indices (e.g., CFI, RMSEA, SRMR)

Standardized parameter estimates

SEM path diagram
