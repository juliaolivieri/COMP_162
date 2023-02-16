# Lecture 10

## Vignette 1 

![](https://github.com/juliaolivieri/COMP_162/blob/7f245a8eb4587db5c4e43a9707ba4692989cc715/lecture10/plots/vignette1.png)

New techniques:
* Pipe a data frame into `ggplot` using `%>%`
* Add a new column with `mutate()` and pipe the result into a plot
* Add title, x, and y labels with `labs()`

Example command with new techniques:
```
bike_sharing %>%
  mutate(frac_casual = casual/count) %>%
  ggplot(aes(temperature_F,count,color=season,shape=weather,size=frac_casual)) +
  geom_point() +
  labs(title = "Effect of weather conditions on number of riders", x = "temperature (F)", y = "number of riders")
```

All code from lecture:
```
bike_sharing %>%
  ggplot(aes(humidity,count)) +
  geom_point(color="dodgerblue")

bike_sharing %>%
  ggplot(aes(windspeed,count)) +
  geom_point(color="dodgerblue")
  
bike_sharing %>%
  ggplot(aes(temperature_F,count)) +
  geom_point(color="dodgerblue")

bike_sharing %>%
  ggplot(aes(temperature_F,count,color=season)) +
  geom_point()

bike_sharing %>%
  ggplot(aes(temperature_F,count,color=season,shape=weather)) +
  geom_point()

bike_sharing %>%
  mutate(frac_casual = casual/count) %>%
  ggplot(aes(temperature_F,count,shape=season,color=weather)) +
  geom_point()

bike_sharing %>%
  mutate(frac_casual = casual/count) %>%
  ggplot(aes(temperature_F,count,color=season,shape=weather,size=frac_casual)) +
  geom_point()

bike_sharing %>%
  ggplot(aes(temperature_F,count,color=season,shape=weather)) +
  geom_point() + 
  labs(title="Effect of weather conditions on number of riders", x = "temperature (F)", y = "number of riders")
ggsave("weather_on_numriders.png")
```

## Vignette 2

![](https://github.com/juliaolivieri/COMP_162/blob/7f245a8eb4587db5c4e43a9707ba4692989cc715/lecture10/plots/vignette2.png)


New techniques:
* Use `dplyr` to filter a data frame and pipe into `ggplot()`

Example command with new techniques:
```
bike_sharing %>%
  mutate(frac_casual = casual/count) %>%
  filter(year == 2011) %>%
  ggplot(aes(date, frac_casual)) + 
  geom_point(color = "dodgerblue") 
```

All code from lecture:
```
bike_sharing %>%
  mutate(frac_casual = casual/count) %>%
  filter(year == 2011) %>%
  ggplot(aes(date, frac_casual)) + 
  geom_point(color = "dodgerblue") 

bike_sharing %>%
  mutate(frac_casual = casual/count) %>%
  filter(year == 2011) %>%
  ggplot(aes(date, frac_casual,color=workingday)) + 
  geom_point() 

bike_sharing %>%
  mutate(frac_casual = casual/count) %>%
  filter(year == 2011) %>%
  ggplot(aes(date, frac_casual,color=workingday)) + 
  geom_point() +
  facet_wrap(~holiday)

bike_sharing %>%
  mutate(frac_casual = casual/count) %>%
  filter(year == 2011) %>%
  ggplot(aes(date, frac_casual,color=holiday)) + 
  geom_point() +
  facet_wrap(~workingday)

bike_sharing %>%
  mutate(frac_casual = casual/count) %>%
  filter(year == 2011) %>%
  ggplot(aes(date, frac_casual,color=workingday,size=holiday)) + 
  geom_point() 

bike_sharing %>%
  mutate(frac_casual = casual/count) %>%
  filter(year == 2011) %>%
  ggplot(aes(date, frac_casual,color=workingday)) + 
  geom_point() + 
  labs(title = "Fraction of casual riders in 2011 by date and workday",y="Fraction of casual riders")
ggsave("frac_casual_by_day.png")
```

## Vignette 3

![](https://github.com/juliaolivieri/COMP_162/blob/7f245a8eb4587db5c4e43a9707ba4692989cc715/lecture10/plots/vignette3.png)


New techniques:
* Create a grouped bar plot by setting `fill` equal to a variable and `position` equal to `dodge`.

Example command with new techniques:
```
bike_sharing %>%
  ggplot(aes(weather, fill=season)) +
  geom_bar(position="dodge")
```

All code from lecture:
```
bike_sharing %>%
  ggplot(aes(weather)) +
  geom_bar(fill="dodgerblue")

bike_sharing %>%
  ggplot(aes(weather, fill=season)) +
  geom_bar()

bike_sharing %>%
  ggplot(aes(weather, fill=season)) +
  geom_bar() +
  facet_wrap(~season)

bike_sharing %>%
  ggplot(aes(weather, fill=season)) +
  geom_bar(position="dodge")

bike_sharing %>%
  ggplot(aes(weather, fill=season)) +
  geom_bar(position="dodge") +
  labs(title = "Weather by season")
ggsave("weather_by_season.png")
```

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
