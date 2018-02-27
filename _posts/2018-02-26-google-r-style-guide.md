---
title: 'Google R Style Guide'
date: 2018-02-26
permalink: /posts/2018/02/google-r-style-guide/
tags:
  - tutorial
  - code style
  - google
---

This post introduces R style guide from [google community](https://google.github.io/styleguide/Rguide.xml). It is very useful for beginners to learn how to code in an appropriate way that can share with other scholars. The basic goal of this post is to introduce the commonly used coding styles.

R Style Rules
=======
* File Names: end in .R
* Identifiers: variable.name (or variableName), FunctionName, kConstantName
* Line Length: maximum 80 characters
* Indentation: two spaces, no tabs
* Spacing
* Curly Braces: first on same line, last on own line
* else: Surround else with braces
* Assignment: use <-, not =
* Semicolons: don't use them
* General Layout and Ordering
* Commenting Guidelines: all comments begin with # followed by a space; inline comments need two spaces before the #

Example Funcion
======
CalculateSampleCovariance <- function(x, y, verbose = TRUE) {
  # Computes the sample covariance between two vectors.
  #
  # Args:
  #   x: One of two vectors whose sample covariance is to be calculated.
  #   y: The other vector. x and y must have the same length, greater than one,
  #      with no missing values.
  #   verbose: If TRUE, prints sample covariance; if not, not. Default is TRUE.
  #
  # Returns:
  #   The sample covariance between x and y.
  n <- length(x)
  # Error handling
  if (n <= 1 || n != length(y)) {
    stop("Arguments x and y have different lengths: ",
         length(x), " and ", length(y), ".")
  }
  if (TRUE %in% is.na(x) || TRUE %in% is.na(y)) {
    stop(" Arguments x and y must not have missing values.")
  }
  covariance <- var(x, y)
  if (verbose)
    cat("Covariance = ", round(covariance, 4), ".\n", sep = "")
  return(covariance)
}