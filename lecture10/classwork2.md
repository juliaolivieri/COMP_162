# Lecture 10

## Classwork 2 questions (work through as many as you have time for)
1. Create a plot of `windspeed` by `season`. Try using `geom_freqpoly()`, `geom_density()`, and `geom_histogram()`. Which visualization do you prefer?
2. Create a plot of `humidity` by `month`. Try using `geom_freqpoly()`, `geom_density()`, and `geom_histogram()`. Which visualization do you prefer?
3. Try filtering these plots to just `fall` and `spring`.
4. Create a box plot of `windspeed` by `season`. Choose a variable to set `fill` to.
5. Try adding points to the plot above with `geom_jitter()`. Do you prefer the plot with or without these points?
6. Create a box plot of `humidity` by `month`. Choose a variable to set `fill` to.
7. Create a `geom_line()` plot of `temperature_F` vs `date_noyear`. Add smoothing with `geom_smooth()`. Were there big temperature differences between the two years?
8. Create a bar plot showing the frequency of each kind of species in the Star Wars data. Drop rows for which `homeworld` is NA. Only include species that appear more than once in the data. Sort the bars by frequency.
9. Try using these techniques to visualize relationships in either dataset.

## Vignette 4

![](https://github.com/juliaolivieri/COMP_162/blob/7f245a8eb4587db5c4e43a9707ba4692989cc715/lecture10/plots/vignette4.png)


New techniques:
* Learn how to filter by multiple values at once using the "or" operator `|`.
* Learn `geom_freqpoly()` for creating a "frequency polygon" plot (whereas a histogram shows frequency with bars, this shows frequency with lines)
* Learn `geom_density()` for creating a smoothed density estimate (a smoothed version of a frequency polygon)

Example commands with new techniques:
```
bike_sharing %>%
  filter(season == "summer" | season == "winter") %>%
  ggplot(aes(temperature_F,color=season)) +
  geom_freqpoly() 
  
bike_sharing %>%
  filter(season == "summer" | season == "winter") %>%
  ggplot(aes(temperature_F,color=season)) +
  geom_density()
```

All code from lecture:
```
bike_sharing %>%
  ggplot(aes(temperature_F)) +
  geom_histogram(fill="dodgerblue")

bike_sharing %>%
  ggplot(aes(temperature_F,fill=season)) +
  geom_histogram()

bike_sharing %>%
  ggplot(aes(temperature_F,fill=season)) +
  geom_histogram() +
  facet_wrap(~season)

bike_sharing %>%
  ggplot(aes(temperature_F,fill=season)) +
  geom_histogram() +
  geom_freqpoly() +
  facet_wrap(~season)

bike_sharing %>%
  ggplot(aes(temperature_F,color=season)) +
  geom_freqpoly() 

bike_sharing %>%
  filter(season == "summer" | season == "winter") %>%
  ggplot(aes(temperature_F,fill=season)) +
  geom_histogram() +
  facet_wrap(~season)

bike_sharing %>%
  filter(season == "summer" | season == "winter") %>%
  ggplot(aes(temperature_F,color=season)) +
  geom_freqpoly() 

bike_sharing %>%
  filter(season == "summer" | season == "winter") %>%
  ggplot(aes(temperature_F,color=season)) +
  geom_density()

bike_sharing %>%
  ggplot(aes(temperature_F,color=season)) +
  geom_density()

bike_sharing %>%
  ggplot(aes(temperature_F,color=season)) +
  geom_density() + 
  labs(title="Temperature by season", x="temperature (F)")
ggsave("temp_by_season.png")
```

## Vignette 5

![](https://github.com/juliaolivieri/COMP_162/blob/7f245a8eb4587db5c4e43a9707ba4692989cc715/lecture10/plots/vignette5.png)

New techniques:
* Learn how to create box plots with `geom_boxplot()`
* Learn how to add "jitter" to points with `geom_jitter()`
* Learn how to create grouped box plots by setting `fill` equal to a categorical variable

Example command with new techniques:
```
bike_sharing %>%
  ggplot(aes(season,humidity)) +
  geom_jitter(color="dodgerblue")
  
bike_sharing %>%
  ggplot(aes(season,humidity,fill=weather)) +
  geom_boxplot()
```

All code from lecture:
```
bike_sharing %>%
  ggplot(aes(season,humidity)) +
  geom_point(color="dodgerblue")

bike_sharing %>%
  ggplot(aes(season,humidity)) +
  geom_jitter(color="dodgerblue")

bike_sharing %>%
  ggplot(aes(season,humidity)) +
  geom_boxplot()

bike_sharing %>%
  ggplot(aes(season,humidity)) +
  geom_boxplot() +
  geom_jitter()

bike_sharing %>%
  ggplot(aes(season,humidity,fill=weather)) +
  geom_boxplot()


bike_sharing %>%
  ggplot(aes(season,humidity,fill=weather)) +
  geom_boxplot() +
  labs(title="Changes in humidity by season and weather")
ggsave("humidty_weather.png")
```

## Vignette 6

![](https://github.com/juliaolivieri/COMP_162/blob/7f245a8eb4587db5c4e43a9707ba4692989cc715/lecture10/plots/vignette6.png)

New techniques:
* Use `geom_line()` to connect points 
* Use `group` to add multiple lines to a `geom_line()` plot
* Use `geom_smooth()` to add a trend line to data

Example command with new techniques:
```
bike_sharing %>%
  ggplot(
    aes(date_noyear,count, color = year, group = year)) + 
  geom_line() +
  geom_smooth()
```

All code from lecture:
```
bike_sharing %>%
  ggplot(
       aes(date_noyear,count)) + 
  geom_point()

bike_sharing %>%
ggplot(
       aes(date_noyear,count, color = year)) + 
  geom_point()

bike_sharing %>%
  ggplot(
    aes(date_noyear,count, color = year)) + 
  geom_line()

bike_sharing %>%
  ggplot(
    aes(date_noyear,count, color = year, group = year)) + 
  geom_line()

bike_sharing %>%
  ggplot(
    aes(date_noyear,count, color = year, group = year)) + 
  geom_line() + 
  geom_point()

bike_sharing %>%
  ggplot(
    aes(date_noyear,count, color = year, group = year)) + 
  geom_line() +
  geom_smooth()

bike_sharing %>%
  ggplot(
    aes(date_noyear,count, color = year, group = year)) + 
  geom_line() +
  geom_smooth() +
  labs(title="number of riders by date",x="date")
ggsave("riders_by_date.png")
```

## Vignette 7

![](https://github.com/juliaolivieri/COMP_162/blob/7f245a8eb4587db5c4e43a9707ba4692989cc715/lecture10/plots/vignette7.png)

New techniques:
* Use `group_by()` and `summarize()` to pipe data into `ggplot()`
* Create a bar plot based on two variables by setting `stat = "identity"`
* Using `reorder` to change the order of bars in a bar plot
* Using `drop_na()` to filter NA values from a data frame
* Use `filter()` to only include bars with a certain count threshold

Example command with new techniques:
```
starwars %>%
  group_by(homeworld) %>%
  summarize(count = n()) %>%
  filter(count > 1) %>%
  drop_na() %>%
  ggplot(aes(reorder(homeworld,count),count)) +
  geom_bar(fill = "dodgerblue",stat="identity")
```

All code from lecture:
```
starwars %>%
  ggplot(aes(homeworld)) +
  geom_bar(fill = "dodgerblue")

starwars %>%
  group_by(homeworld) %>%
  summarize(count = n()) %>%
  ggplot(aes(homeworld,count)) +
  geom_bar(fill = "dodgerblue",stat="identity")

starwars %>%
  group_by(homeworld) %>%
  summarize(count = n()) %>%
  filter(count > 1) %>%
  ggplot(aes(homeworld,count)) +
  geom_bar(fill = "dodgerblue",stat="identity")

starwars %>%
  group_by(homeworld) %>%
  summarize(count = n()) %>%
  filter(count > 1) %>%
  ggplot(aes(reorder(homeworld,count),count)) +
  geom_bar(fill = "dodgerblue",stat="identity")

starwars %>%
  group_by(homeworld) %>%
  summarize(count = n()) %>%
  filter(count > 1) %>%
  drop_na() %>%
  ggplot(aes(reorder(homeworld,count),count)) +
  geom_bar(fill = "dodgerblue",stat="identity")

starwars %>%
  group_by(homeworld) %>%
  summarize(count = n()) %>%
  filter(count > 1) %>%
  drop_na() %>%
  ggplot(aes(reorder(homeworld,count),count)) +
  geom_bar(fill = "dodgerblue",stat="identity") +
  labs(title = "Frequency of each homeworld in Star Wars", x = "homeworld")
ggsave("homeworld_freq.png")
```
