--- 
title: "ug1-practical"
author: "psyTeachR"
date: "2019-05-14"
site: bookdown::bookdown_site
documentclass: book
bibliography: [book.bib, packages.bib]
biblio-style: apalike
link-citations: yes
description: "ug1-practical-materials"
---

# Overview {-}

Placeholder



<!--chapter:end:index.Rmd-->


# Lab 1 

Placeholder


## Pre-class activity
## In-class activities
### Activity 1: Replication task  
### Activity 2: Getting to know the data
## Additional resources around open science and replicability

<!--chapter:end:01-lab01.Rmd-->


# Lab 2

<div class="info">
<p>This is the first lab that the students are introduced to R. The important point here is that R is introduced as a tool which will support their open science practices such as replicability and follows on from discussion in lab 1 about working with data effectively. We presented the large messy data set in lab 1 highlighting the nature of work that students need to start thinking about before introducing R as the solution in lab 2.</p>
</div>

## Pre-class activity

### Data Management
* Watch video on intro to R
* Remember these key points as you work through the data activities on this course
 + R is a tool that enables you to become confident and competent working with data
 + This is essential as a psychologist as you need to know the data findings are based on are reliable and valid. Imagine delivering a treatment that was based on research where the analyst was not confident or competent?

See this tweet from Dr Dale Barr on how applicable these skills will be for you in your future careers...

<img src="images/Dale_tweet.png" width="500px" />

These are skills that you will use beyond our undergraduate course and that are desireable to employers. Just ask our previous students....

<img src="images/Steph_tweet.PNG" width="500px" />


Think of a skill you nailed the first time you did it. Not so easy? You will learn to work with data by repeating the essential basic skills over and over. It's new and will take time. Give yourself credit for trying and don't stress if it doesn't work right away. Use the resources we give, that are being talked about online among the open science community and ask questions in class and on the forums. We are here to help!
 
### The first thing we need to do is set the working directory. 
What this means is that we tell R where the files we need are. Think of it just like when you have different subjects, and you have seperate folders for each topic e.g. biology, history and so on. When working on R, it's useful to have the data sets and files in one folder. 
To set working directory press session -> set working directory -> choose directory and then select the folder where the data sets we are working on are saved, and save this file in the same folder as well. In other words- make sure your data sets and scripts are all in the same folder. Follow the pre-lab video to help you with this too. In the labs, we recommend that you create a folder for Psychology labs with sub-folders within for each lab in your M: drive. This is your personal area on the University network that is safe and secure so much better than flashdrives and desktops. 


### Important info on our homework worksheets
So we can see your progress in data management skills we are using a worksheet format **for the homework only** called R Markdown (abbreviated as .Rmd) which is a great way to create dynamic documents with embedded chunks of code. These documents are self-contained and fully reproducible which makes it very easy to share. This is an important part of your open science training as one of the reasons we are using R is that it enables us to share open and reproducible information. The reason we are using these worksheets in this format is so that you are given a task and then can fill in the required code. 

For more information about R Markdown feel free to have a look at their main webpage sometime http://rmarkdown.rstudio.com. The key advantage of R Markdown is that it allows you to write code into a document, along with regular text, and then *'knit'* it using the package `knitr` to create your document as either a webpage (HTML), a PDF, or Word document (.docx). **Before submitting your homework file check that it knits OK to html then submit the .Rmd file, not the knitted html version** 

You won't be creating webpages or other document types (unless you want to!) just yet but we want to tell you a little more about the format of these worksheets so you know how and why we are using them. It enables you to enter code after class for assessment. We can then use a program to mark these and return feedback to you. This is right in line with our ethos of open and reproducible science enabling us to show you a skill, let you try it and then enable you to show us how good you are at it!

**There are just a couple of important rules we need you to follow to make sure this all runs smoothly.**

1. These worksheets need to you fill in your answers and not change any other information. For example, if we ask you to replace NULL with your answer only write in the code you are giving as your answer and nothing else. To illustrate -

##### Task 1 read in your data

```r
data <- NULL
```
The task above is to read in the data file we are using for this task - the correct answer is ```data <- read_csv(data.csv)```. You would replace the NULL with:

##### Solution to Task 1

```r
data <- read_csv("data.csv")
```
This means we can look for your code and if it is in the format we expect to see it we can give you the marks! If you decide to get all creative on us then we can't give you the marks as 'my_lab_Nov_2018.csv' isn't the filename we have given to you to use. So don't change the file, variable or data frame names as we need these to be consistent. 

2. We will look for your answers within the boxes which start and end with ``` and have {r task name} in them e.g. 

<div class='verbatim'><code>&#96;&#96;&#96;{r tidyverse, messages=FALSE}</code>

```r
library(tidyverse)
```

<code>&#96;&#96;&#96;</code></div>

These are called code chunks and are the part of the worksheet that we can read and pick out your answers. If you change these in any way we can't read your answer and therefore give you grades. You can see in the example above that the code chunk, grey zone, starts and ends with these back ticks (usually found on top left corner of the keyboard). This code chunk has the ticks and text which makes it the part of the worksheet that will contain code. The {r tidyverse} part tells us which task it is (loading in tidyverse) and therefore what we should be looking for and what we can give marks for - loading in the package called tidyverse in the example above. If this changes then it won't be read properly so will impact on your grade.

### Take home message
The easiest way to use our worksheets is to think of them as fill-in-the-blanks and keep file names and names used in the worksheet the same. If you are unsure about anything then use the forums on Moodle and Slack to ask any questions and come along to the practice sessions. We have also made a short video about R Markdown and why we use it for our lab work which you can find in the prep section of lab 2 on Moodle. There is an R Markdown cheatsheet which will support you playing around with R Markdown which you can find here https://www.rstudio.com/wp-content/uploads/2015/02/rmarkdown-cheatsheet.pdf.


## In-class activity

Part of becoming a psychologist is asking questions and gathering data to enable you to answer these questions effectively. It is very important that we understand all aspects of the research process such as experimental design, ethics, data management and visualisation. 

In this class, you will be learning how to develop reproducible scripts. This means scripts that completely and transparently perform some analysis from start to finish in a way that yields the same result for different people using the same software on different computers. And transparency is a key value of science, as embodied in the “trust but verify” motto. When you do things reproducibly, others can understand and check your work. This benefits science, but there is a selfish reason, too: the most important person who will benefit from a reproducible script is your future self. When you return to an analysis after two weeks of vacation, you will thank your earlier self for doing things in a transparent, reproducible way, as you can easily pick up right where you left off. This is relevant within the context of open science which is a big debate in the scientific community at the moment. Some classic psychological experiments have been found to not be replicable. See the links below for some discussion on this topic:

[Study delivers bleak verdict on validity of psychology experiment results](https://www.theguardian.com/science/2015/aug/27/study-delivers-bleak-verdict-on-validity-of-psychology-experiment-results)

[Low replicability in psychological science](http://www.apa.org/science/about/psa/2015/09/low-replicability.aspx)

As part of your skill development, it is very important that you work with data so you can become confident and competent in your management and analysis of data. In the labs, we will work with real data that has been shared by other researchers. When we are working with data we will use software called RStudio <img src="images/RStudio.png" style="width:30px;"> which is the user interface for R that we are going to use. Information about this software can be found here [RStudio](https://www.rstudio.com/). R Studio is available on the computers in the lab but is free to download onto your own devices. Guidance on how to do this can be found [RStudio download](https://www.rstudio.com/products/rstudio/download/#download). Remember to watch the prep video on RStudio for a tour around the interface with Heather. 

**Getting our data ready to work with**

Today in the lab we will be working on loading libraries (opening the apps in the prep video) required to work with our data and then loading our data into R before getting it organised into a sensible format that relates to our research question.  

OK, so what is our first step? Yup, thats right, we need to tell R what packages we want to use and where to find all the files we need before we pull them in ready for work. 

**Task 1 - loading in the package**

```r
library(tidyverse)
```

**Task 2 - read in data**

```r
dat <- read_csv ('files/ahi-cesd.csv')
pinfo <- read_csv('files/participant-info.csv')
```

**Task 3 - join the files together**

```r
all_dat <- inner_join(dat, pinfo, by='id', 'intervention')
```

**Task 4 - pull out variables of interest**

```r
summarydata <- select(all_dat, ahiTotal, cesdTotal, sex, age, educ, income, occasion, elapsed.days)
```

Well done! You have started on your journey to become a confident and competent member of the open scientific community! To show us how competent you are you should now complete the assessment for this lab which follows the same instructions as this in-class activity but asks you to work with different variables. Always us the lab prep materials as well as what you do in class to help you complete the class assessments! Success through practice! 

<!--chapter:end:02-lab02.Rmd-->


# Lab 3

Placeholder


## Pre-class activity
## In-class activity

<!--chapter:end:03-lab03.Rmd-->


# Lab 4 

Placeholder


## Pre-class activity
## In-class activity
### Getting our data ready to work with
### We are now at the point where we can create a plot showing us some data. Why should we do this? This is an interesting thread from our colleagues Dr Guillaume Rousselet and Prof Lisa DeBruine on the reasons why we should use plots and the benefits of using ggplot, the package we will use today in RStudio, to create our plot: https://twitter.com/robustgar/status/1025342313004974080

<!--chapter:end:04-lab04.Rmd-->


# Lab 5

Placeholder


## Pre-class activity
### Wrangling Data
### The Autism Quotient (AQ)
### Thinking through the problem
## In class activity 
### Making the computer do the dirty work

<!--chapter:end:05-lab05.Rmd-->


# Lab 6

Placeholder


## Inclass activity 
### Task 1 - loading in the package 
### Task 2 - read in data
### Task 3 - getting our data into the correct format for analysis 
### Task 4 - Question format
### Task 5 - Scores
### Task 6 - Calculate AQ scores
### Task 7 - Calculate AQ scores cont'd
### Task 8 - Calculate AQ scores efficiently
### Task 9 - Using ggplot2, make a distribution of the overall AQ scores by producing a histogram from aq_scores.

<!--chapter:end:06-lab06.Rmd-->


# Lab 7

Placeholder


## Pre-class activity
### Probability and Probability Distributions
### Types of data
### Simple probability calculations
### Joint probability
### Prep exercise: Estimate the probability of getting X heads over four independent flips.
### Monte Carlo simulation
### Theoretical probability distributions
## Inclass activity
### Monte Carlo simulations
### The Binomial Distribution - Creating a Discrete Distribution

<!--chapter:end:07-lab07.Rmd-->


# Lab 8

Placeholder


## Pre-class activity
### Discrete or Continuous Datasets
#### <span style="color:DARKGREEN"> Quickfire Questions</span>
### Normal distribution
## Inclass activity
### Normal Distribution Probability
### Working with the Normal Distribution
### `pnorm()` - the probability or distribution function
### `qnorm()` - the quartile function

<!--chapter:end:08-lab08.Rmd-->


# (APPENDIX) Appendices {-} 

<!--chapter:end:appendix-0.Rmd-->

