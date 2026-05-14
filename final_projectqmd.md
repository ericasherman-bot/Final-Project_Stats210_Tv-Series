# TV Series Final Project


### **Data Description**

1.  The data source is from Kaggle. It is a fun TV series data set with
    a lot of my favorite shows from my childhood. I wanted to choose a
    fun data set for my project.

2.  My data contains TV shows, their channels, IMDb ratings, google
    users, episodes, years the shows were on air for, and techniques of
    how the shows were shot. I will be focusing on a few variable; the
    titles of shows, the year of which they were on air for, tv channels
    and IMDb ratings.

3.  Research Questions:

- How do distributions of the IMDb ratings for TV shows based on their
  start year across the time period 1999-2019 vary?
- What are the top rated TV shows based on IMDb between Adult swim,
  Cartoon Network, Disney Channel, Nickelodeon?
- What is the highest rated TV show in between Adult swim, Cartoon
  Network, Disney Channel, Nickelodeon? based on IMDb

I selected the years 1999–2019 to examine a 20-year period while
excluding years affected by the COVID-19 pandemic, since the pandemic
may have influenced television production and audience ratings.
Including all years in the data set resulted in an overcrowded
visualization, so the ridge-plot visualization was limited to this time
range to improve readability. Similarly, for the bar chart
visualization, only the top 40 shows were included because plotting a
larger number of shows made the graph appear overly crowded and
difficult to interpret.

### **Data Cleaning**

I first started by cleaning the names and then selecting the variables I
was going to use for my visualizations, imdb, tv channel, title, and
year. I then dropped any na values from the data. The year column had
the start and end year of each show, so I had to create a two new
columns, one with only the start year and the other with the end year.
Some of the TV shows had the start and end date embedded into the title
so I asked chat GPT how to use string r text to extract the numbers and
characters out of the titles. Lastly, I saved the cleaned data set as an
object then a csv file and placed into a data folder. I did additional
data cleaning that were specific to each visualization. For the first
visualization: “Distribution of IMDb Ratings by Show Start Year
(1999–2019),” I filtered the cleaned data set to include only television
shows with start years between 1999 and 2019. For the second
visualization: “IMDb Rating for Top 40 Shows in the Selected TV
Channels,” I filtered the data set to include four TV Channels: Adult
Swim, Cartoon Network, Disney Channel, and Nickelodeon. I chose these
channels they ones I watched growing up and provided an interesting
basis for comparison. I then arranged in descending order by IMDb
rating, and only the top 40 shows were included to maintain readability
and reduce overcrowding. For the third visualization: “Distribution of
IMDb Ratings for Selected TV Channels,” I again filtered the data set to
include the same four TV Channels and arranged in descending order by TV
channel.

### **Data Visualization**

1.  For my first visualization I created a ridgeline plot with density.
    Each ridgeline represents the start year of all the shows that were
    released in that year, and the x axis is mapped to IMDb rating. It
    shows a summary of all the shows for each year. So “Regular Show”,
    for instance, was released in 2010, so regular show will only be
    plotted in that year.

![](images/imdb_ridge_plot.png)

2.  For the second visualization I created a barplot in descending order
    to show the top rated show (based on IMDb) within the four selected
    TV channels, Adult Swim, Cartoon Network, Disney Channel,
    Nickelodeon specific channel. The TV show with the highest IMDb
    rating is “Avatar: The Last Airbender” Produced by Nickelodeon.

![](images/imdb_bar_plot.png)

3.  Lastly, I wanted to look at the distributions of IMDb ratings of TV
    shows within the four TV channels selected and if one on average had
    a higher IMDb rating than the other three. So I created a raincloud
    plot. All four distributions have roughly the same mean and median.
    The distribution of TV channel Nickelodeon has more spread than the
    other three channels.

![](images/imdb_cloud_plot.png)
