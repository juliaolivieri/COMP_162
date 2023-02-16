# Lecture 10

## Classwork questions (work through as many as you have time for)
1. Modify your commands from the previous classwork to pipe the data frame into `ggplot()`.
2. Use `mutate()` to create a new column (perhaps `count/temperature_F`) and plot the new column vs `date` using `geom_points()`
3. Add labels to a plot using `labs()`
4. Filter your observations to only days for which the weather is `clear` before plotting.
5. Create a bar plot of `weather`, determining `fill` by `weekday` (remember to use `position = "dodge"`)
6. Create a bar plot of `weekday`, determining `fill` by `weather` (remember to use `position = "dodge"`)
7. Which of the plots from 5 and 6 is more informative?

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
