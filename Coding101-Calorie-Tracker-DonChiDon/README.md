# DonChiDon Calorie Tracker

A Python desktop application for tracking **daily calorie intake, exercise, and personalized calorie goals**, with built-in food matching and exercise recommendation features.

## Overview

Tracking calories and exercise manually can be time-consuming, especially when users need to repeatedly calculate calorie intake, energy expenditure, and daily goals.

**DonChiDon** is a desktop calorie-tracking application designed to simplify this process. Users can enter personal information, record meals and exercise, review daily calorie summaries, and receive exercise recommendations based on the gap between their current calorie balance and target intake.

The application was built with a graphical interface to make calorie tracking more accessible and intuitive for everyday users.

## Features

### Personalized Calorie Analysis

Users enter basic information such as height, weight, age, gender, activity level, and weight-management goals.

The application calculates:

- BMI and weight category
- Basal Metabolic Rate (BMR)
- Estimated daily calorie requirement
- Personalized target calorie intake

### Food Tracking

Users can record meals by entering a food name and meal category.

If calorie information is not entered manually, the application searches an internal food dataset and:

- returns an exact match when available
- searches for partially matching food names
- calculates similarity to select the closest available item

Users can also enter calorie values manually when more accurate information is available.

### Exercise Tracking

Users can record:

- Exercise type
- Duration
- Exercise intensity

Exercise data are matched against an exercise database to estimate calories burned.

### Exercise Recommendation

Based on the difference between calorie intake, calories burned, and the user's target, the application recommends up to **three exercise options**.

For supported exercises, users can also open related YouTube videos directly from the application.

### Data Management

The application supports:

- Automatic saving of user records
- Daily food and exercise summaries
- Viewing remaining calories relative to the target
- Deleting individual records
- Clearing all records
- Input validation and error messages

## Implementation

The application was developed primarily in **Python**.

Key implementation components include:

- **Tkinter** for the graphical user interface
- **PrettyTable** for displaying food and exercise records
- **Pandas** for reading structured food and exercise datasets
- File I/O for saving and restoring user information
- String-matching logic for identifying similar food items
- Recommendation logic for suggesting exercises
- `webbrowser` integration for opening exercise videos

## Repository Structure

```text
Coding101-Calorie-Tracker-DonChiDon/
├── DonChiDon-Calorie-Tracker-Coding101-Slides.pdf   # Project presentation and implementation details
└── README.md
```

## Tech Stack

`Python` · `Tkinter` · `Pandas` · `PrettyTable` · `PIL` · `File I/O` · `GUI Development`

## Project Context

**Coding101 Programming Competition / Project**  
Team Project · Python Application · GUI Development · Health & Lifestyle
