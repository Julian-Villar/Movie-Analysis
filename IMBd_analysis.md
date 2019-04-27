IMDB Analysis
================
Julian Villar
30 April 2019

# Are movies getting better?

## Introduction

Do you miss the good old days? Nostalgia really has a way of messing
with our perception of whether things are improving. Clearly in
technological terms we are better off, but what about culturally? To
question whether art is getting better or worse is completely
subjective, but what if we could ask everyone what they think on pieces
of art throughout time and rate it, that way we could quantify whether
there is improvement or not. Thanks to the Internet Movie Database
(IMDb) we can.

Using Data acquired on the 16th July 2018 publically available from
IMDb, we will report our findings. \#\# Tools used

``` r
library(tidyverse)
library(ggrepel) 
library(gghighlight)
library(ggridges)
library(tidytext)
library(readr)
library(scales)
library(knitr)
```

## Ratings

Perhaps before we search through trends throughout time, it is better to
establish a baseline. The average movie rating fits this purpose and
naturally falls a good entry point to this report.

We introduce our first dataset, df\_ratings. That is the ratings data
frame. This is our simplest dataset and provides us the Movie ID that’ll
act as a Foreign key between our various datasets, the average rating
for a movie (averageRating) and the number of votes for each movie
(numVotes).

We provide the first few entries to show this dataset clearly.

    ## # A tibble: 6 x 3
    ##   tconst    averageRating numVotes
    ##   <chr>             <dbl>    <dbl>
    ## 1 tt0000001           5.8     1491
    ## 2 tt0000002           6.3      181
    ## 3 tt0000003           6.6     1127
    ## 4 tt0000004           6.4      110
    ## 5 tt0000005           6.2     1829
    ## 6 tt0000006           5.5       96

We begin by plotting the average rating of all movies.
![](movie_analysis4Github_files/figure-gfm/unnamed-chunk-3-1.png)<!-- -->
![](imdb-1.png)

## Expanding our dataset

Now this extensive dataset is added, we’ll combine them

Now with our new extensive data frame we move to perform the real
analysis.

Making a subset was the first challenge, this is as follos

``` r
df_ratingsHORROR = subset(df_ratings, grepl("Horror", genres))
```

As previously done for Horror we will now recreate for Comedy

``` r
df_ratingsCOMEDY = subset(df_ratings, grepl("Comedy", genres))
```

might be error here pls no
