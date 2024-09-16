# world-elevation-wgs84-database

Database featuring elevation data in tabular format instead of satellite GeoTIFF image for easy application in python pandas dataframes, QGIS, etc. No more need to process and extract elevation data from satellite images.

Parquet filetype chosen due to compression/filesize (SQLite 6.7 GB vs parquet 0.4 GB). Parquet file can also be loaded into a python pandas df and then converted to a csv for easy import into QGIS.

Database file available under 'Releases'.

Key features:
- Each data point in the parquet dataframe is the **_maximum_** elevation value of the raster/tile area it represents
- Resolution is one datapoint per raster/tile of 800m (lon) * 900m (lat)
- Datapoints only included for those tiles where maximum elevation > 0 metres above mean sea level (AMSL)
- The accuracy of the value for maximum elevation is rounded to metres (integers)
- Data is extracted from the GMTED2010 satellite images (https://catalog.data.gov/dataset/global-multi-resolution-terrain-elevation-data-2010-gmted2010)
- Global coverage except poles
- WGS 84 reference
- Vertical reference is EGM96: mean sea level (MSL) is defined as 0 and vertical unit is metres above mean sea level (AMSL)

Data can be applied to create elevation/topographic charts such as below (examples by the author). For tailor-made charts, please contact me.
![ir example](https://github.com/MrAirspace/world-elevation-wgs84-database/assets/144953682/7b4701bd-e78c-4b38-8b43-1033a1914625)
![pt example](https://github.com/MrAirspace/world-elevation-wgs84-database/assets/144953682/fb0473d3-ed93-43f3-aea8-2cf6c325fadd)
