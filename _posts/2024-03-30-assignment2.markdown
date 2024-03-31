---
layout: post
title:  "Assignment2"
date:   2024-03-30 11:50:00 +0100
categories: jekyll update
---
# A Short Data Story

## 1. Introduction
### 1.1 Dataset intro

The dataset is a collection of incident reports from a police department database, detailing a wide array of incidents ranging from robbery to vehicle theft, arson, and assault. Each record includes unique identifiers, a general category and detailed description of the incident, the day of the week, date and time it occurred, the police district it took place in, and its resolution status. Additionally, the dataset encompasses a variety of location information, with specific emphasis on administrative and geographical divisions, categorizations of areas based on different criteria such as vulnerability, and details regarding specific zones and neighborhoods. This makes it a comprehensive source for analyzing crime patterns, police response, and public safety issues. 

### 1.2 Website intro

This web-page is designed as a vital resource for the residents of San Francisco, aiming to shed light on emerging crime trends within the city. Its primary objective is to equip citizens with current and comprehensive information on the types of crimes that are witnessing an uptick, enabling them to stay informed and vigilant.

To achieve this, the page will feature different graphs and visual representations, offering an at-a-glance overview of the crime categories that are currently exhibiting the most alarming trends. These visual aids are not only intended to present a broad snapshot of the city's crime landscape but also to pinpoint which specific types of criminal activities are becoming more prevalent.

In a further effort to empower residents with detailed knowledge that could affect their safety, the webpage will delve into crime data spanning from 2015 to 2017, presenting it in a manner that is both accessible and easy to understand. This detailed visualization aims to provide citizens with the insights necessary to assess their personal risk based on their specific location within San Francisco.

By navigating through this data, individuals can gain a clearer understanding of how crime rates vary across different neighborhoods and over time, potentially influencing their daily decisions and lifestyle choices. The ultimate goal of this webpage is to foster a well-informed community, where every resident has the tools and information needed to contribute to their own safety and the safety of their neighbors.

## Visualizations
### 2.1 Time Series Plot

![test](https://github.com/banishee/banishee.github.io/raw/main/public/time_series_plot.png)

**Note:** 

The graphs presented serve as a visual examination of five distinct crime categories within San Francisco, with a focus on identifying trends in the frequency of these crimes from 2003 to 2017. The categories showcased are Larceny/Theft, Stolen Property, Trespass, Vandalism, and Weapon Laws.

A notable feature of these graphs is the use of color to emphasize the years that experienced the highest occurrence of crimes in each category—marked in red for immediate visibility. This color differentiation allows viewers to quickly discern patterns and potentially concerning increases in criminal activity over the last fifteen years.

For Larceny/Theft, the graph exhibits a fluctuating trend but shows a significant rise towards the latter years. Stolen Property, Trespass, and Vandalism categories also reflect a rising trend, with recent years standing out, indicating a growing concern. The graph for Weapon Laws shows less variability over the years, but an uptick is still visible in the latter period.

The intention behind marking the three most prevalent years in red is to draw attention to the most critical periods, thus encouraging residents, policymakers, and law enforcement to delve deeper into the underlying causes. It also aids in focusing preventive measures and resources on those years that could be the harbinger of a continuing or emerging trend. This visual approach to presenting crime data is an essential tool in community awareness efforts and strategic planning for public safety.

### 2.2 Map Plot
<embed 
        type="text/html" 
        src="/public/map_SF.html"
        width="1500"
        height="500"
        >

**Note:**

The plot visualizes a heat map of larceny/theft incidents across San Francisco, highlighting crime hotspots over a three-year period. The intensity of the colors ranges from blue to red, where warmer colors indicate higher frequencies of reported incidents. Areas with the most concentrated crime rates are encircled in red, allowing for quick identification of regions with the highest levels of larceny/theft. This map provides a clear, at-a-glance view of the spatial distribution of this particular crime category within the city's boundaries.