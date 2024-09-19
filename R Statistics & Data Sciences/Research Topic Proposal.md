**Project Title and Research Questions**

1. What is the title of your proposed research project?  
   

Valence in Music

2. State the two research questions that you are going to attempt to answer with your analysis.  
   

*RQ1* – Does a happy mood correlate with a higher valence?

*RQ2* – Does a slower tempo correlate with a lower valence?

**Literature Review and Stakeholders**

3. Briefly describe your motivation for choosing this research topic. Will your study confirm, refute, replicate, or extend a previous study(ies)?  
   

I chose this topic because I love music and the behavioral aspects of neuroscience, so I thought it would be a great way to do research over something I enjoy. As I was searching for articles related to my topic, I found an assessment on the happiness of the world with Spotify data that used valence as a measurement of musical mood1. I thought it would be interesting to confirm and replicate other studies done to explore what different aspects of music influences valence in order to create a certain mood/atmosphere for a song2.

1Mcconnell, W. (2021, February 27). *How happy is the world? just ask Spotify.* Medium. Retrieved June 9, 2022, from [https://towardsdatascience.com/tracking-global-mood-with-spotify-847011228085](https://towardsdatascience.com/tracking-global-mood-with-spotify-847011228085)   
2Veas, C. (2020, September 13). *Predicting the music mood of a song with deep learning.* Medium. Retrieved June 10, 2022, from [https://towardsdatascience.com/predicting-the-music-mood-of-a-song-with-deep-learning-c3ac2b45229e](https://towardsdatascience.com/predicting-the-music-mood-of-a-song-with-deep-learning-c3ac2b45229e) 

4. Who are the stakeholders for your study?  
   

Some stakeholders are musicians, producers, and sound engineers who want to create a certain mood in their work. Other possible stakeholders could be music streaming companies and music distributors who want to gauge how a certain mood of music could influence who listens to what and when they listen; knowing this would also help with marketing (choosing how a song should be sold or who it should be sold to).

**Sampling and Data Collection Plan**

5. What is your population of interest (the population you will be making an inference about)?

My population of interest is songs (virtual music compositions) that can be found/accessed on the streaming site Spotify. 

6. Who or what will be the individual sampling units for your study?

A single song will be an individual sampling unit and it will be observed for its valence, mood, and tempo in each row, respectively. Each song will be selected from playlists already created and promoted on Spotify based on/corresponding to each categorical mood (i.e. ‘happy playlists’, ‘sad songs’, etc).

7. Cite the specific source(s) of your data and, if drawing from multiple sources, briefly describe the process you will use to combine your variables into a single dataset.  
   

[https://github.com/cristobalvch/Spotify-Machine-Learning/blob/master/data/data\_moods.csv](https://github.com/cristobalvch/Spotify-Machine-Learning/blob/master/data/data_moods.csv)  
I will only be using this dataset (but removing multiple columns and rows from the original) to create my own dataset. The database includes multiple aspects of each song (such as loudness, tempo, and time signature) and a wide range of music was chosen from Spotify playlists of multiple genres on the Spotify platform.

[https://www.frontiersin.org/articles/10.3389/fpsyg.2013.00417/full](https://www.frontiersin.org/articles/10.3389/fpsyg.2013.00417/full)  
I will be using this research article to define what I mean when representing valence in my dataset. This article describes how valence was measured/recorded in prior experiments done to study music mood.

8. Will your dataset be able to be considered a random sample from your population of interest?

No, my data will not be a random sample from my population as the selection of songs will be chosen from available Spotify playlists with English titles (and song names) only (which means artists who do not release their music for virtual streaming on the Spotify platform in English will not be considered in this experiment). This is a limitation as Spotify hosts music of many languages and stylistic musical choices can differ across many languages/cultures. This means that there could be certain aspects to songs and their style that influence valence and utilize mood and tempo differently that my data will not cover.

**Proposed Measures**

9. What will be your response variable?

Valence will represent my numeric response variable. It is considered numeric because it is a quantitative measure with a magnitude. It will run from a scale of 0.0 to 1.0 and represent a more negative sound as the valence value gets closer to 0.0, and a more positive sound as the valence value gets closer to 1.0.

10. What will be your first explanatory variable? How do you think it is related to your response variable? Describe the relationship you expect to find and why you think this relationship exists.

Mood will be my categorical explanatory variable. It will categorize my song samples as either having a happy or sad mood. I hypothesize that mood has a strong positive correlation with valence. As previous studies claim that a higher valence represents more of a positive sound, I believe that a song with a happy mood would have a more positive sound, and a song with a sad mood would have a less positive sound.

11. What will be your second explanatory variable? How do you think it is related to your response variable? Describe the relationship you expect to find and why you think this relationship exists.  
    

Tempo will be my numeric explanatory variable. It will list the tempo of each song with a standardized unit of beats in a song per minute (bpm). The values will range from 70.0 to 200.0 bpm. Since tempo influences the pace of a song, I think it may influence how positive or negative sounding a song is. I hypothesize that a higher valence value has a slightly positive correlation to a song’s bpm.

**Ethical Consequences**

12. What consequence might the results of your study have on your population of interest? How might your findings be used by the study’s stakeholders?

Though I believe the behavior is no new phenomenon, if enough people begin to find more interest in the valence of a song, songs may become specifically engineered to have a specific valence value and some moods/styles of music may stop being produced for digital consumption as it falls out of favor/popularity of stakeholders. Stakeholders may use this information to choose how to make and/or market certain songs. They may also use this information to influence music trends by pushing certain songs/sounds onto consumers.

