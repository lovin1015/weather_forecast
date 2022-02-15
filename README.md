# AstroWeather

This is a *Custom Integration* for [Home Assistant](https://www.home-assistant.io/). It uses the forecast data from 7Timer! to create sensor data for Home Assistant. It uses the public [Machine-readable API](http://www.7timer.info/doc.php?lang=en#machine_readable_api) to pull data from 7Timer!.

![GitHub release](https://img.shields.io/badge/release-v0.20.0-blue)
[![hacs_badge](https://img.shields.io/badge/HACS-Default-orange.svg)](https://github.com/custom-components/hacs)

There is currently support for the following entity types within Home Assistant:

* Sensor
* Binary Sensor
* Weather

Forecast data is provided by 7Timer! on a three *hourly* basis.

There is also a custom weather card available [here](https://github.com/mawinkler/astroweather-card).

## Installation

### HACS installation

This Integration is part of the default HACS store, so go to the HACS page and search for *AstroWeather* within the integrations.

### Manual Installation

To add AstroWeather to your installation, create this folder structure in your /config directory:

`custom_components/astroweather`.

Then drop the following files into that folder:

```yaml
__init__.py
binary_sensor.py
config_flow.py
const.py
entity.py
manifest.json
sensor.py
strings.json
weather.py
translation (Directory with all files)
```

## Configuration

To add AstroWeather to your installation, go to the Integration page inside the configuration panel and AstroWeather.

During installation you will have the option to:

- verify the longitude and latitude for the forecast
- set the elevation
- set the interval for updating forecast data

The interval for updating forecast data can also be changed after you add the Integration, by using the *Options* link on the Integration widget.

## Lovelace

There is now a custom weather card available [here](https://github.com/mawinkler/astroweather-card).

## Entities

The following entities are being added to Home Assistant. All have a unique ID, so you can rename them to whatever you like afterwards.

***Binary Sensors:***

Name | Explanation
---- | -----------
binary_sensor.astroweather_deep_sky_view | True, if current conditions should allow deep sky observation.

***Sensors:***

Name | Explanation
---- | -----------
sensor.astroweather_10m_wind_direction | Wind direction at 10m height.
sensor.astroweather_10m_wind_speed | Wind speed in m/s
sensor.astroweather_10m_wind_speed_plain | Wind speed in plain text
sensor.astroweather_2m_relative_humidity | Relative humidity at 2m
sensor.astroweather_2m_relative_humidity_plain | Relative humidity at 2m in plain text
sensor.astroweather_2m_temperature | Temperature at 2m in °C
sensor.astroweather_clouds | Cloud cover quality as a percentage (the higher, the value, the lesser clouds)
sensor.astroweather_clouds_plain | Cloud cover quality as a percentage in plain text
sensor.astroweather_condition | Viewing conditions as a percentage (the higher, the better)
sensor.astroweather_deepsky_forecast_today | Forecast for viewing conditions this evening as a percentage (the higher, the better)
sensor.astroweather_deepsky_forecast_today_desc | Forecast for viewing conditions this evening in plain text
sensor.astroweather_deepsky_forecast_today_plain | Forecast for viewing conditions this evening as *Good-Excellent-Good*
sensor.astroweather_deepsky_forecast_tomorrow | Forecast for viewing conditions tomorrow evening as a percentage (the higher, the better)
sensor.astroweather_deepsky_forecast_tomorrow_desc | Forecast for viewing conditions tomorrow evening in plain text
sensor.astroweather_deepsky_forecast_tomorrow_plain | Forecast for viewing conditions tomorrow evening as *Good-Excellent-Good*
sensor.astroweather_elevation | Elevation configured for this AstroWeather instance
sensor.astroweather_latitude | Latitude configured for this AstroWeather instance
sensor.astroweather_lifted_index | Lifted index in degrees
sensor.astroweather_lifted_index_plain | Lifted index in plain text
sensor.astroweather_longitude | Longitude configured for this AstroWeather instance
sensor.astroweather_moon_next_rising | Next rising of the Moon
sensor.astroweather_moon_next_setting | Nect setting of the Moon
sensor.astroweather_moon_phase | Current Moon phase as a percentage
sensor.astroweather_precipitation_type | Expected Precipitation Type in plain text (snow, rain, frzr (freezing rain), icep (ice pellets), none)
sensor.astroweather_seeing | Seeing conditions as a percentage (the higher, the better)
sensor.astroweather_seeing_plain | Seeing conditions in plain text in arcsec range
sensor.astroweather_sun_next_rising | Next rising of the Sun, calculated for the civil twilight
sensor.astroweather_sun_next_rising_astronomical | Next rising of the Sun, calculated for the astronomical twilight (-18°)
sensor.astroweather_sun_next_setting | Next setting of the Sun, calculated for the civil twilight
sensor.astroweather_sun_next_setting_astronomical | Next setting of the Sun, calculated for the astronomical twilight (-18°)
sensor.astroweather_timestamp | Timestamp of current data
sensor.astroweather_transparency | Atmospheric transparency as a percentage (the higher, the better)
sensor.astroweather_transparency_plain | Atmospheric transparency in plain text in magnitudes

***Weather:***

Name | Explanation
---- | -----------
weather.astroweather_LONGITUDE_LATITUDE | An instance of a weather object for Home Assistant

It contains some of the sensor values as additional state attributes for use in the custome Lovelace card.
