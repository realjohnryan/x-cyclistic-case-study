# x-cyclistic-case-study
Cyclistic case study notes, files, code, etc.

## gameplan
business question: How do annual members and casual riders use Cyclistic bikes differently?
differentiators: avg ride time, time of day, day of week, classic or electric, top 10 stations for casuals for targeting

## cleaning
clean csv files as follows: removing outliers docked bike, rides under 45 seconds and rides over 3 hours

create duration, day of week, and hourly time of day chunk columns

since the files are generally too large for google cloud console to run sql create the needed pivot tables in excel

sample SQL:
SELECT
  start_station_name,
  count(*) as cnt
FROM `cyclistic-case-study-379315.cyclistic_ride_data_12month.february_22` 
WHERE
  member_casual = "casual" AND start_station_name IS NOT NULL
group by start_station_name order by cnt desc
limit 15;

## analysis and combination
take cleaned and trimmed workbooks with pivot tables and combine as needed for selected insights
