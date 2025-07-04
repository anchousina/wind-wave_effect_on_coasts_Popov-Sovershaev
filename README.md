# wind-wave_effect_on_coasts_Popov-Sovershaev

The Popov-Sovershaev method [Popov and Sovershaev, 1982; Shabanova et al., 2018; Kazhukalo et al., 2023] estimates the annual volume of water mass (in tons/year) approaching the coast due to wind-induced waves. It is based on the following formula:

WWE = (ρ / g) * V³ * d * s * x / t

Where:
    ρ — water density (t/m³)
    g — gravitational acceleration (m/s²)
    V — wind speed at 10 m above sea level (m/s), for a specific direction
    d — total duration of wave-generating wind from that direction over the study period (s)
    x — fetch length for that direction (km)
    s — scaling factor (set to 1 by default)
    t — total duration of the study period (years)

Only winds that generate waves impacting the coastline under study should be considered. Wind data can be sourced from local weather stations or, for Europe, from the Copernicus archive.

Fetch length (x) for each direction (rhumb) at each coastal transect can be computed using ArcGIS tools:

    Bearing Distance to Line — Create lines for defined azimuths from each point

    Clip — Trim lines using the coastline shapefile

    Delete Identical — Remove duplicate lines (e.g., those obstructed by islands)
    
![image](https://github.com/anchousina/wind-wave_effect_on_the_coasts_Popov-Sovershaev/assets/157022548/8c12f738-6797-4d52-b050-6e2e8e50f633)

Input

    Fetch_length.shp — Shapefile containing:
        TransectID – transect number
        Bearing – direction of the rhumb
        Shape_Leng – fetch length of the rhumb (km)
        All other fields can be dropped.

    Weather station CSV files — One file per year, with columns:
        date, time, wind_speed, wind_dir

    ⚠️ Be sure to set the appropriate set of rhumbs for your region of interest.

Output

    A CSV file containing calculated WWE values for each coastal transect.

Sample Data

Example files are provided using a case study from Crete, Greece.



