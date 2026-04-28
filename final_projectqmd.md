# TV Series Final Project


## Quarto

Quarto enables you to weave together content and executable code into a
finished document. To learn more about Quarto see <https://quarto.org>.

## Running Code

When you click the **Render** button a document will be generated that
includes both content and the output of embedded code. You can embed
code like this:![](images/clipboard-40922044.png)

``` r
library(readr)
library(dplyr)
library(janitor)
library(forcats)
library(tidyverse)
library(stringr)
library(ggplot2)
tvseries<- read_csv("data/Animated_Tv_Series.csv")
```

``` r
tvclean <- tvseries |>
  clean_names() |>
  select(id, title, episodes, year, original_channel, technique, im_db, google_users) |>
  drop_na() |>
  separate(year, into = c("start_year", "end_year"), sep = "-") |>
  mutate(across(c(start_year, end_year), as.numeric))
```

``` r
tvclean |>
  group_by(original_channel, start_year) |>
  summarize(total_episodes = sum(episodes, na.rm = TRUE), .groups = "drop") |>
  filter(
    original_channel %in% c("Cartoon Network", "Nickelodeon", "Disney Channel", "Netflix", "Adult Swim", "Fox")) |>
  ggplot(aes(x = start_year, y = total_episodes, fill = original_channel)) +
  geom_col(position = "dodge") +
  scale_fill_viridis_d(option ="mako")
  #scale_fill_manual(values = c("#823749", "#983998", "#109", "#324556", "#676", "#217"))
```

### **Data Description**

1.  The data source I will be using is from Kaggle. It is a fun TV
    series data set with a lot of my favorite shows from my childhoods.
    I wanted to choose a fun data set for my project.

2.  My data contains TV shows, their channels, IMDb ratings, google
    users, episodes, years the shows were on air for, and techniques of
    how the shows were shot. I will be focusing on a few variables, the
    titles of shows, the year of which they were on air for, the IMDb
    ratings, maybe the episodes, and the techniques.

3.  What is the most popular TV channel in each year? I will answer this
    by summing up the amount of shows releases within that year for that
    particular channel.

- What is the highest rated TV show in each year? based on IMDb
- Which TV channel produces the most CGI based series? alternative
  question: How has the use of CGI in TV series changed over time?
  another alternative, what are the most common techniques used to
  create a TV show? sum up the each technique used by each show.

### **Data Visualization**

1.  I think I will be doing time series data, so I might do a simple bar
    plot and line plot.

2.  I would highlight the most popular TV channel throughout the year by
    adding text to that case on the graph. I will highlight the highest
    rated TV show by ordering the bars from largest to smallest.

3.  I would need sum up the number of TV channels and connect the shows
    to their release year to find out the total shows within that year
    apart of the specific channel.

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
