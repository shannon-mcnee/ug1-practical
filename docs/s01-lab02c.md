# Lab 2 in class activity

Part of becoming a psychologist is asking questions and gathering data to enable you to answer these questions effectively. It is very important that we understand all aspects of the research process such as experimental design, ethics, data management and visualisation. 

In this class, you will be learning how to develop reproducible scripts. This means scripts that completely and transparently perform some analysis from start to finish in a way that yields the same result for different people using the same software on different computers. And transparency is a key value of science, as embodied in the “trust but verify” motto. When you do things reproducibly, others can understand and check your work. This benefits science, but there is a selfish reason, too: the most important person who will benefit from a reproducible script is your future self. When you return to an analysis after two weeks of vacation, you will thank your earlier self for doing things in a transparent, reproducible way, as you can easily pick up right where you left off. This is relevant within the context of open science which is a big debate in the scientific community at the moment. Some classic psychological experiments have been found to not be replicable. See the links below for some discussion on this topic:

[Study delivers bleak verdict on validity of psychology experiment results](https://www.theguardian.com/science/2015/aug/27/study-delivers-bleak-verdict-on-validity-of-psychology-experiment-results)

[Low replicability in psychological science](http://www.apa.org/science/about/psa/2015/09/low-replicability.aspx)

As part of your skill development, it is very important that you work with data so you can become confident and competent in your management and analysis of data. In the labs, we will work with real data that we will find from databases. When we are working with data we will use software called RStudio ![](r_studio.png). Information about this software can be found here [RStudio](https://www.rstudio.com/). R Studio is available on the computers in the lab but is free to download onto your own devices. Guidance on how to do this can be found [RStudio download](https://www.rstudio.com/products/rstudio/download/#download). More information on why we are working with RStudio is here and the link to the prep video on RStudio you are to watch for this lab can be found here. 

**Getting our data ready to work with**

Today in the lab we will be working on loading libraries (opening the apps) required to work with our data and then loading our data into RStudio beofre getting it organised into a sensible format that relates to our research question.  

OK, so what is our first step? Yup, thats right, we need to tell RStudio what packages we want to use and where to find all the files we need before we pull them in ready for work. 

**Task 1 - loading in the package**

```r
library(tidyverse)
```

**Task 2 - read in data**

```r
dat <- read_csv ('ahi-cesd.csv')
pinfo <- read_csv('participant-info.csv')
```

**Task 3 - join the files together**

```r
all_dat <- inner_join(dat, pinfo, by='id', 'intervention')
```

**Task 4 - pull out variables of interest**

```r
summarydata <- select(all_dat, ahiTotal, cesdTotal, sex, age, educ, income, occasion, elapsed.days)
```

Well done! You have started on your journey to become a confident and competent member of the open scientific community! To show us how competent you are you should now complete the assessment for this lab which follows the same instructions as this in-class activity but asks you to work with different variables. Always us the lab prep materials as well as what you do in class to help you complete the class assessments! Success through repetition! Upload you homework assessment which can be found here by 12pm 1 week from your lab. The assessmrn submission page can be found here. 
