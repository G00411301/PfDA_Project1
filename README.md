# PfDA_Project1 #
Programming for Data Analytics - Project 1 repository

This repository contains the data (csv file) and jupyter notebook relating to my Programming for Data Analytics (PfDA) project 1.

## Problem Statement ##

For this project you must create a data set by simulating a real-world phenomenon of
your choosing. You may pick any phenomenon you wish – you might pick one that is
of interest to you in your personal or professional life. Then, rather than collect data
related to the phenomenon, you should model and synthesise such data using Python.
We suggest you use the numpy.random package for this purpose.
Specifically, in this project you should:
 - Choose a real-world phenomenon that can be measured and for which you could
collect at least one-hundred data points across at least four different variables.
 - Investigate the types of variables involved, their likely distributions, and their
relationships with each other.
 - Synthesise/simulate a data set as closely matching their properties as possible.
 - Detail your research and implement the simulation in a Jupyter notebook – the
data set itself can simply be displayed in an output cell within the notebook.
Note that this project is about simulation – you must synthesise a data set. Some
students may already have some real-world data sets in their own files. It is okay to
base your synthesised data set on these should you wish (please reference it if you do),
but the main task in this project is to create a synthesised data set. The next section
gives an example project idea.

## Contents of this Repository ##

This repository contains all of the files pertaining to the PfDA project including
 - Data Folder - Containing a csv of data sourced from kaggle relating to performance of tweets in terms of social engagement
 - This Readme file - Containing general information about the project
 - A jupyter notebook containing the project work and steps.

## Accessing the Repository ##

The repository has been set up with public access to allow users to easily download the repository.
The repository can be accessed at the following link: https://github.com/G00411301/PfDA_Project1

## How to view the project ##

The project is presented in a jupyter notebook using Python 3. During the development of the project I updated the Anaconda package on my local machine which required some amendment to the code. The final version of the project does operate with the most recent version of the ANaconda package with some future warnings with deprecated features which will be removed in future versions. 

## Project Approach ##

The approach adopted for the project was to identify and source a dataset appropriate for the analysis, for this I selected a Kaggle dataset detailing tweet engagement rates. A description of the dataset included on kaggle details the dataset:

*The dataset consists of 21677 tweets posted from 25th March 2019 to 31st January 2022 by 23 Destination marketing organizations (DMO). The tweets were collected to study the social media content strategy of DMOs. Specifically, the research attempted to study how the linguistic features in social media content strategies of DMOs change during the pre-Covid, lockdown, and post-lockdown phases and their impact on social media user engagement. Accordingly, the data constitutes key variables like confidence and positive engagement expressed in a tweet, the amount of cognitive content embedded in a tweet, the media type, the number of hashtags, mentions, and word count of a tweet. The number of likes and retweets associated with each tweet is also captured. The dataset also captures each tweet's date and time stamp to classify it into three phases: pre-COVID, during lockdown, and post-COVID. The timelines are chosen per the Government of India's declaration of the lockdown.*

### Project Structure ###

The Jupyter notebook is structured as follows:

#### Prepare Real Data Set for Analysis ####

The first step in the project was to analyse the real world data in order to understand its characteristics and disctribution. I began by importing the data from the CSV file stored in the Data directory.

Next I made any transformations I deemed necessary such as converting the string day values to integers and assigning a number to each day (0-6) represented Monday to Sunday.

The number of characters in tweet lenght was counted and stored as a varaible using the function len().

A numerical value was added to represent the media type that was associated with each tweet (this value was dropped from the analysis)

#### Real Data Analysis ####

Next we began analysing the real data. I began with a Seaborn pairplot to visualise each of the variables with referece to one another.

This was followed by a Histogram of each of the most important variables associated with the phenomenon of tweet likes.

The Histograms initially indicated that there were a number of out liers in the like count variable that must be cleaned up later.

Out of interest, I then calculated the mean and standard deviation of each variable by state (not fully relevant to the project as geographical distribution was not a key variable in this analysis but interesting to observe and could potentially indicate location popularity whihc could have an impact on like count - again, not explored in this project)

#### Variable Relationship ####

Next I generated summary tables showing the covariance and correlation between the data sets. The data was suprisingly poorly correlated. Next I generated sub plots of each of the variables, which again confirmed there was no signifincat linear relationship between teh variables.

#### Simulated Data ####

Next I began simulating data. I began by further analysing the data variable independntly, the Like count variable had a signifncant number of outliers as visualised by the histogram and box plot charts. In order to remove outliers, I used the Z scoer method and trimmed the vaues outside 3 standard deviations from the mean from the data set. Th resulting histogram appeared the match an expinential distrobution. I then used numpy.random.expontential to synthesize the data.

Clout and tweet length were both very difficult the fit to a distribution, as such I relied on np.random.choice, and fed the relevant variable into the dataset and generated 1000 values for each variable. This was confirmed to be appropriate as the mean of the origirnal and simulated data are comparable.

Day of the week followed a uniform distribution so np.random.uniform was used to simulate data. 


### References ###

Mendley Data Set: https://data.mendeley.com/datasets/bfk3hvdcnt/1

Kaggle data set source: https://www.kaggle.com/datasets/jocelyndumlao/dmo-social-media-engagement-dataset

Determining factors that drive twitter engagement rates: https://journals.scholarpublishing.org/index.php/ABR/article/download/2700/1677#:~:text=These%20variables%20includes%20the%20day,the%20tweet%20among%20other%20variables.

Investigating Outliers: https://www.youtube.com/watch?v=Cw2IvmWRcXs

Statistics by Jom: https://statisticsbyjim.com/probability/exponential-distribution/

Identifying data distributions: https://medium.com/the-researchers-guide/finding-the-best-distribution-that-fits-your-data-using-pythons-fitter-library-319a5a0972e9