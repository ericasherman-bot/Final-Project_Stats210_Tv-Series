# TV Series Final Project


## Quarto

Quarto enables you to weave together content and executable code into a
finished document. To learn more about Quarto see <https://quarto.org>.

## Running Code

When you click the **Render** button a document will be generated that
includes both content and the output of embedded code. You can embed
code like this:![](images/clipboard-40922044.png)

### **Data Description**

1.  The data source is from Kaggle. It is a fun TV series data set with
    a lot of my favorite shows from my childhood. I wanted to choose a
    fun data set for my project.

2.  My data contains TV shows, their channels, IMDb ratings, google
    users, episodes, years the shows were on air for, and techniques of
    how the shows were shot. I will be focusing on a few variables, the
    titles of shows, the year of which they were on air for, the IMDb
    ratings, maybe the episodes, and the techniques.

3.  How do the distributions of IMDb ratings vary across years from 1999
    to 2019? I choose these years because I wanted the cutoff to be
    before covid, since I though covid my influence the data and decided
    to do a 20 year period. I could not plot all years because the graph
    was too crowded.

- How do distributions of the IMDb ratings for TV shows based on their
  start year across the time period 1999-2019 vary?
- What are the top rated TV shows based on IMDb between Adult swim,
  Cartoon Network, Disney Channel, Nickelodeon? (I only chose the top 40
  because trying to graph more than 40 made the plot look overcrowded)
- What is the highest rated TV show in between Adult swim, Cartoon
  Network, Disney Channel, Nickelodeon? based on IMDb

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
    The distribution of Nickelodeon has more spread than the other three
    channels.

![](images/imdb_cloud_plot.png)

### **Data Cleaning**

The answer to at least three of these questions should be “YES” for the
data to meet the necessary standards to demonstrate your cleaning. Your
data source should not be an already perfectly prepared data set.

1.  Do you need to reformat any variables into different types
    (e.g. factors, time, dates, strings)? Or remove information from
    variable values? yes. I need to remove information in the year
    column. The year column has the shows start and end date and I just
    want the start date.
2.  Do you need to deal with any missing data, especially missing data
    coded other than NA?

- no

3.  Do you need to filter your data? How?

- Yes, I would use the filter function to filter out any na’s in the
  data. And I will use filter to first find the na’s in the variables I
  want to use, if any.

4.  Do you need to create any new variables? What variables? How?

- I might need to create new variables with mutate. I can create a new
  variable that only has the start year for each episode and keep the
  old variable with the total time the show was on air for.

5.  Do you need to add new data (join) to your data? What data? How?

- no

6.  Do you need pivot your data in any way? Why? How?

- no

7.  Do you need to summarize any of the variables? Which ones? How?

- yes, I would need to summarize the top ratings of the TV shows,
  summarize the total number of shows produced by a channel for each
  year. I will also use summarize to the total number of shows that use
  CGI.

8.  What other aspects of your data need to be “fixed” in order to make
    your data visualizations?

- I might get ride of the percents on the google user cases, if I end up
  using it.

Most will answer yes to the following for making your programming more
efficient using `select()`, but you should have **three other yeses
above**.

9.  Are there any variables you can exclude from your data?

- I can exclude the American company name, note and id.
