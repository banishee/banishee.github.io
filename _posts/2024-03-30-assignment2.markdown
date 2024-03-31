---
layout: post
title:  "Assignment2"
date:   2024-03-30 11:50:00 +0100
categories: jekyll update
---
# A Short Data Story

## Introduction
**The story should have a brief introduction to the dataset so new readers from outside the class can understand what's going on.**

### Dataset intro

The dataset is a collection of incident reports from a police department database, detailing a wide array of incidents ranging from robbery to vehicle theft, arson, and assault. Each record includes unique identifiers, a general category and detailed description of the incident, the day of the week, date and time it occurred, the police district it took place in, and its resolution status. Additionally, the dataset encompasses a variety of location information, with specific emphasis on administrative and geographical divisions, categorizations of areas based on different criteria such as vulnerability, and details regarding specific zones and neighborhoods. This makes it a comprehensive source for analyzing crime patterns, police response, and public safety issues. 

### Website intro

This web-page is designed as a vital resource for the residents of San Francisco, aiming to shed light on emerging crime trends within the city. Its primary objective is to equip citizens with current and comprehensive information on the types of crimes that are witnessing an uptick, enabling them to stay informed and vigilant.

To achieve this, the page will feature different graphs and visual representations, offering an at-a-glance overview of the crime categories that are currently exhibiting the most alarming trends. These visual aids are not only intended to present a broad snapshot of the city's crime landscape but also to pinpoint which specific types of criminal activities are becoming more prevalent.

In a further effort to empower residents with detailed knowledge that could affect their safety, the webpage will delve into crime data spanning from 2015 to 2017, presenting it in a manner that is both accessible and easy to understand. This detailed visualization aims to provide citizens with the insights necessary to assess their personal risk based on their specific location within San Francisco.

By navigating through this data, individuals can gain a clearer understanding of how crime rates vary across different neighborhoods and over time, potentially influencing their daily decisions and lifestyle choices. The ultimate goal of this webpage is to foster a well-informed community, where every resident has the tools and information needed to contribute to their own safety and the safety of their neighbors.

## Data Prepration
```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt

import folium
from folium.plugins import HeatMap

from bokeh.io import output_notebook
from bokeh.plotting import figure, show
from bokeh.models import FactorRange, ColumnDataSource
from bokeh.palettes import Category20
```

```python
df=pd.read_csv("Police_Department_Incident_Reports__Historical_2003_to_May_2018_20240214.csv")
df['Datetime']=pd.to_datetime(df.Date+' '+df.Time,format='%m/%d/%Y %H:%M')
df=df[df.Datetime.dt.year!=2018]
```

## Time Series Plot
**One time-series / bar chart (it's OK to use the "fancy" plot-typs like calendar plots or polar bar-charts from Week 2, Part 4).**
```python
focus_crimes_st = sorted(set(['LARCENY/THEFT','STOLEN PROPERTY','TRESPASS','VANDALISM','WEAPON LAWS']))
```
```python
crime_cat_year=[]
for crime in focus_crimes_st:
    crime_cat_year.append(np.unique(df[df.Category==crime]['Datetime'].dt.year,return_counts=True))
```
```python
plt.figure(figsize=(15,8))

for i in range(len(focus_crimes_st)):
    highest_values=np.partition(crime_cat_year[i][1],-3)[-3:]
    
    mask_highest = np.isin(crime_cat_year[i][1], highest_values)
    colors = ['red' if m else 'green' for m in mask_highest]

    plt.subplot(3,2,i+1)
    plt.bar(crime_cat_year[i][0],crime_cat_year[i][1],alpha=0.5,color=colors)
    plt.title(focus_crimes_st[i],fontsize=10,fontdict={'family':'serif'})
    plt.ylabel('Occurences',fontdict={'family':'serif'})


    plt.yticks(fontname='serif')
    if (i == 3)|(i==4):
        plt.xlabel('Year',fontdict={'family':'serif'})
        plt.xticks(fontname='serif',ticks=crime_cat_year[i][0])
    else:
        plt.xlabel('')
        plt.xticks(ticks=[])

plt.suptitle('Number Of Crimes Per Year',fontdict={'family':'serif'})
plt.tight_layout()
plt.show()
```

![test](https://github.com/banishee/banishee.github.io/raw/main/public/time_series_plot.png)