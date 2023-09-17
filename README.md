# Speech Recognition Probability Enhancement Project

## Introduction

This repository contains the research and findings of a project aimed at enhancing the accuracy of a speech recognition network's predicted probabilities. The network exhibited interesting behavior where it was uncertain about its predictions despite achieving high accuracy. In this project, which was conducted during my internship at the University of Leuven, we address this issue by utilizing a Multi-Layer Perceptron (MLP) model to analyze prediction patterns and improve the evaluation of probabilities per character.


## Table of Contents

- [Data Description](#data-description)
- [Problem Statement](#problem-statement)
- [Objectives](#objectives)
- [Results](#results)
-  [Discussions and Conclusions](#Discussions-and-Conclusions)

## Data Description

The dataset used in this project consists of a sample of standard Dutch spoken in Flanders and the Netherlands, known as CGN, comprising approximately one million words. Various dimensions underlying the variation in language use were considered, leading to the identification of several components[1]. Refer to Table 1.1 for a breakdown of these components.

## Problem Statement

Each character in a sentence is associated with a probability value stored within an array of 37 elements. The network selects the character with the highest probability as its prediction. However, a comparison between the accuracy of the first-best character in a given interval and the probability assigned to that character revealed interesting insights. As illustrated in Figure 1.2, there is a sharp tail between 0.1% to 5% probability values. Surprisingly, the actual probability is often greater than 50% for predicted probabilities as low as 5% and below. This indicates that the network is uncertain about its character choices despite achieving high accuracy with these low probabilities.

## Objectives

The primary objectives of this project are as follows:

1. **Identify the Origin of the Probability Tail**
   - Investigate whether the difference in the distribution of each of the 37 characters in the dataset contributes to the issue.
   - Examine whether the presence of different components in the data is a factor.
   - Analyze if variations in data distribution between different intervals play a role.

2. **Enhance the Network's Results**
   - Develop a hypothesis: Utilizing an MLP, we can map actual probabilities to predicted probabilities to enhance the network's confidence scores.

3. **Determine the Optimal Mapping**
   - Experiment with different mappings and devise a method to measure their effectiveness.


## Results

This project aims to address the issue of uncertainty in a speech recognition network's predictions by mapping actual probabilities to predicted probabilities using an MLP. Detailed results, findings, and insights will be documented in the project notebooks and can be found in the `results` section of our report.


# Discussions and Conclusions

In conclusion, the best result we got was after training an MLP with KLD loss function on the first half of the data. Its results can be found in section 2.5.3.
