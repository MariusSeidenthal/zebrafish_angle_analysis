# Zebrafish Angle Analysis
Analysis of zebrafish bending angle during free swimming. Based on WormRuler (https://github.com/dvettkoe/wormruler).
## Overview 
This is an open-source python based video analysis tool to analyze the bending angle of _Danio Rerio_, developed by Marius Seidenthal as part of his PhD thesis in the Gottschalk Lab, Goethe University Frankfurt, Germany.

## Getting started

### Installation

Download the [latest release](https://github.com/MariusSeidenthal/zebrafish_angle_analysis/releases/tag/v0.0.4), unzip the folder and start the _"zebrafish_analysis_v*.exe"_.

### Guide

This tool offers an user-friendly graphical user interface (GUI) that offers a step-by-step guidance for the analysis of single freely swimming fish videos.

![](https://i.imgur.com/c6gy8ov.png)
![](https://i.imgur.com/QzI89dQ.png)

Each step can be started separately or start all at once (it is recommended to review results after each step).

#### 1. Select videos to be analyzed
Select the main directory in which your videos are stored.

(Only supports the following file types: **.avi/.AVI** or **.mov/.MOV**)
   
It is currently only able to analyze a single fish per video.

Users can now start each step one by one or start all step at once by clicking "Start all".

#### 2. Background correction
Enter Gamma values depending on the brightness of the video. The gamma value should be between 0.7 to 1.3.

The resolution can be adjusted to speed up the process. It is generally recommended to use 1200 x 800 pixel.

After starting, the program will ask to select a ROI. This can be used to avoid rims and unwanted artifacts in your videos. The rectangular ROI should be drawn to cover the whole arena.

We recommend to start background correction for one video and adjust the gamma values accordingly. The preview buttons may be used to test whether the gamma values are appropriate.

The plate preview should be used to see whether the entered Gamma value is sufficient to correctly detect the arena in which the animal is allowed to move. This is crucial to avoid artifacts.

Background corrected videos should look like above: only the white fish should be visible on black background.

#### 3. Skeletonize
Adjust the framerate to match the framerate of your videos.

Check the box to override already analyzed videos. This option can be useful, if the gamma value was not adjusted correctly and analysis has to be repeated.

We recommend using 1 angle which is calculated from 3 skeleton points (from the swimm bladder to the tail tip). 

The program automatically detects the the head of the animal and will set the three points for angle calculation as shown above. 

#### 4. Normalize Data

Can be used to further clean up the data. Otherwise, use the data in the raw_angle.txt file for analysis.

Measured skeleton length (in pixel) is normalized and values above or below the given values are discarded. This may help to avoid artifacts detected during skeletonization.



#### 5. Analyze Data
Normalized data will be summarized for each analyzed condition and exported into an XLSX format for further analysis.

Normalized values for each analyzed worm as well as mean, standard error of the mean and n numbers will be given.

When more than 50 % of the datapoints of an animal are omitted, it will be ignored in the statistical analysis and listed separately.
