# Add a new Country

1. Download shapefiles from https://gadm.org/download_country_v3.html. Higher version map higher map details

2. Convert shapefiles into geojson file

3. Add ISO 3166-2 with column name ISO in states_district_cities.csv and geojson file.

4. Put your geojson file in next folder : */superset/assets/src/visualizations/countries* with the next name : *malaysia.geojson*

5. Go in file *superset/assets/src/explore/controls.jsx.* Add ‘Malaysia in component ‘select_country’
```
select_country: {
    type: 'SelectControl',
    label: 'Country Name Type',
    default: 'France',
    choices: [
    'Belgium',
    'Brazil',
    'China',
    'Egypt',
    'France',
    'Germany',
    'Italy',
    'Malaysia',
    'Morocco',
    'Netherlands',
    'Russia',
    'Singapore',
    'Spain',
    'Uk',
    'Usa',
    ].map(s => [s, s]),
    description: 'The name of country that Superset should display',
```
6. Rebuild front end assets in */incubator-superset/superset/assets/*

   yarn
   yarn run build

7. Start a web server in */incubator-superset/superset/assets/* that manages and updates the assets as it being modified

   npm run dev

8. Run superset
