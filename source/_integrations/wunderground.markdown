---
title: Weather Underground (WUnderground)
description: Instructions on how to integrate Weather Underground (WUnderground) Weather within Home Assistant.
ha_category:
  - Weather
ha_release: 2021.12
ha_iot_class: Cloud Polling
ha_domain: wunderground
ha_platforms:
  - sensor
---

The `wunderground` platform uses [Weather Underground](https://www.wunderground.com/) as a source for current weather information.

<div class='note'>

Weather Underground API no longer offers API keys. The API is generally not available for use, except if you own a personal weather station and provide your data to WU (PWS Uploader).

Please consider this when using the following information.

</div>

There is currently support for the following information within Home Assistant:

- Measurements:
  - Temperature
  - Humidity
  - Air Pressure
  - Heat Index
  - Dewpoint
  - Windchill
  - Solar Radiation
  - UV Index
  - Wind Speed
  - Wind Gust Speed
  - Wind Direction
  - Precipitation
  - Precipitation Rate
- Forecasts:
  - Summary of Today
  - Weather Day/Night
  - Highest Temperature
  - Lowest Temperature
  - Wind
  - Precipitation
  - Precipitation
- Weather Station Information:
  - Neighborhood Reference Name
  - Local Time
  - Station ID
  - Elevation

During configuration you can select which of these categories you want to monitor.
All of the conditions of the selected categories will be available as sensors after the configuration.

{% include integrations/config_flow.md %}

The conditions will be updated every 5 minutes.

## Forecasts

All of the forecasts except for "Summary of Today" are available for the next 5 days.

### Weather Day/Night

The monitored weather forecasts are 12 hour forecasts. To get a forecast for different period/daytime replace the `_1d` part of the sensor name.  e.g., `weather_2n` will give you forecast for tomorrow night. Valid values for day are `1` to `4` and valid values for daytime are `d` or `n`.

## Example: Measurements

![Measurements](/images/screenshots/wunderground_measurements.png)

## Example: Forecast

![Daily Forecast](/images/screenshots/wunderground_daily_forecast.png)

<div class='note'>
Note: While the platform is called “wunderground” the sensors will show up in Home Assistant as “wu” (eg: sensor.wu_weather).
</div>

Additional details about the API are available [here](https://docs.google.com/document/d/1eKCnKXI9xnoMGRRzOL1xPCBihNV2rOet08qpE_gArAY/edit).
