# wind-wave_effect_on_the_coasts_Popov-Sovershaev

Wind wave effect (WWE) [Popov and Sovershaev, 1982; Shabanova et al., 2018; Kazhukalo et al., 2023] is based on the wave energy theory and correlations between wind speed and parameters of wind-induced waves. WWE is expressed as a water mass approaching to the coast per year (tons/year) and is proportional to the wind speed (V) to the power of three, duration of action of wave-generating winds (d) and wave fetch (x):

WWE = ρ/g * V^3 * d s *x / t

Where ρ is density of the water (t/m3), g is gravitational acceleration (m/s2), V is wind speed of the specific direction at the height at 10 m above sea level (m/s), d is duration of the wind of the current direction for the period of the study (s), x is length of the fetch of the current wind direction (km), t is duration of studied period (years).

Winds directions and speeds can be obtained from the weather stations' archives or from the Copernicus data (for Europe). Only the directions of winds inducing waves influencing the studied coasts should be taken into account. 

The length of the wave fetch for every rhumb in every point (corresponds to every coastal transect) can be calculated automatically in ArcGIS using such tools as Bearing Distance to Line (build the lines for defined points for the defined azimuths for the defined distances), Clip (clip the lines constructed on the previous step with the shape of coastal line of the area) and Delete Identical (to remove the duplicate lines formed on the previous step from the areas of islands’ shadows, for example).

Figure explaining calculation of wave fetch length for every transect in ArcGIS:
![image](https://github.com/anchousina/wind-wave_effect_on_the_coasts_Popov-Sovershaev/assets/157022548/8c12f738-6797-4d52-b050-6e2e8e50f633)


Input:
  - Fetch_length.shp is a shapefile containing information on the transect number (TransectID field), direction of the line of every rhumb for every transect (Bearing) and length of the line of every rhumb for every transect (Shape_Leng). Other fields of the shapefile can be dropped.
  - Folder containing the csv files with the weather station data for every year of study. Every file contains the fields: date, time, wind_speed, wind_dir.
 
 ! Don't forget to change the set of the rhumbs for your specific area.

Output:
  - Csv file containing the WWE calculated for the every coastal transect.
     
The sample files contains the data for the key site located on Crete, Greece. 



