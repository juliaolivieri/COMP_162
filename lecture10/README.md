# Lecture 10

## Vignette 1 

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
