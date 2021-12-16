---
layout: default
---

## Some interesting personality quote 

### Introduction

Language is the main mode of communication through which a person expresses their thoughts and feelings. We tend to form an opinion of a person after just a few interactions with them either through spoken or written conversation. This then raises an interesting question: Do language use truly reflect personality types? While the idea that language and personality are related is not new [1], systematic examination of how word use relates to individual differences in personality traits have only been studied by researchers in the recent past [2][3]. Inspired by these studies, in this article, we aim to explore and analyze this relationship using Quotebank, an open corpus of 178 million quotations attributed to the speakers who uttered them, extracted from 162 million English news articles published between 2008 and 2020. [4]

#### From Text to Personality Score
Before delving into various analysis on personalities, we would like to give you a background on the core ideas and methods enabling our study. We are given a corpus of text for each speaker and somehow, we would like to transform this text to a number so that we can quantify the personality of a speaker and do all kinds of comparisons. How do you go from a piece of text to a personality measure you ask? Good question! We asked the same question and luckily, we were not the first people to have thought about it! There have been several studies on this topic in the past that have shown significant correlations between different word categories (e.g. pronouns, positive/negative words etc.) and personality types. Most of these studies focus on finding the relationship between personality types and so-called LIWC word categories[5] using supervised learning methods. After an extensive examination of these psycho-linguistic study papers, we decided to use the correlation results found between the Big Five personality types[6] and LIWC word categories, from a large-scale study of personality and word use among bloggers[7]. More concretely, given a sample corpus of text for a sample of speakers, we first run this text through the LIWC software[8] (seriously, we bought it!) to produce a matrix of frequency numbers (let's call it L) where rows correspond to a speaker and columns are the different word categories. On the other hand, we have a matrix of correlations (let's call it C) between the very same word categories and all the Big Five personality types and subtypes (extracted from [7]). We then simply multiply these matrices (we also first normalize L across word categories) to produce our personality scores (let's call it P). Mathematically speaking, P = LC where the rows of P correspond to different speakers and columns are the different facets of Big Five personality traits (e.g. depression, trust, dutifulness etc.) Voila! We started with a piece of text and ended up with a bunch of numbers presumably corresponding to personalities of people. In the rest of the article, we will try to analyze these numbers for people across professions, idealogies, countries, genders etc. to see whether these correlations hold and reveal the real world of personalities.


### Some funny title for politicians analysis

Let's compare some politicians!
<iframe height="700" width="1000" frameborder="no" src="https://yirencao.shinyapps.io/polis/"> </iframe>

#### Validation for Politician Analysis

<img src="images/hillary_trump.png" alt="drawing" width="5000"/>

The score of the 1000 people's control group is used to generate the boxplots above, the actual data points are also plotted in black. While the counterparts for Donald Trump and Hillary Clinton are plotted in red and blue respectively.

According to the [paper `Perceived personality and campaign style of Hillary Clinton and Donald Trump`](https://www.sciencedirect.com/science/article/pii/S0191886917305688?casa_token=1aBX0HMkSQ0AAAAA:I4CHEpEfM9LRiQCrsLw1lk61IUt0MJu2RvD8L7t_PV_xBHisPnM8Z78xrEyfTpqa1Xo7ollgvM7L) where the big five personality score of Trump and Clinton are evaluated by domain experts as below. 
Clinton scores low on neuroticism, average on agreeableness, extraversion, openness, and high on conscientiousness.
Trump scores very low on agreeableness, conscientiousness and emotional stability, average on openness, and very high on extraversion.
Our results agree to the research in agreeableness and conscientiousness but contradicts in extraversion, neuroticism and openness. 
However, the personality rating is to some extent subjective. Even for the experts in this specific case, Trump supporters and Clinton supporters will rate significantly differently, as depicted in [a later finding](https://www.sciencedirect.com/science/article/pii/S0191886918300850).

#### Can we cluster similar politicians together?
To cluster the politicians in terms of their personality, we first perform PCA to reduce the dimension of our dataset since we have 35 variables for personality traits. Then based on PC1 and PC2, the major two dimensions that explain most of the variations, we produce k-means clustering. We choose k = 2 as the optimal one by looking at the total WSS and silhouette plots.

<iframe height="750" width="100%" frameborder="no" src="html/pca_politician_k_2.html"></iframe>
Moreover, we also would like to have a more detailed clustering for politicians, we find k = 4 also give a reasonably good result on silhouette and WSS plots.

<iframe height="750" width="100%" frameborder="no" src="html/pca_politician_k_4.html"></iframe>

### Some funny title for gender analysis

### Some funny title for country analysis

<select class="personality-selector"></select>
<iframe class="personality-frame" height="500" width="100%" frameborder="no" src="html/world-speakers.html"> </iframe>

### Some funny title for suicide analysis

### Some funny title for entrepreneur/artist analysis


### Conclusion

### Team, Links to repo

### References
[1] Sanford, 1942
[2] Fast and Funder, 2008
[3] Mehl et al., 2006
[4] Quotebank
[5] LIWC Category
[6] https://en.wikipedia.org/wiki/Big_Five_personality_traits
[7] Personality in 100000 paper
[8] LIWC software