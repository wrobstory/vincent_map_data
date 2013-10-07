vincent_map_data
================

A geodata repository for Vincent examples

I used Mike Bostock's [us-atlas](https://github.com/mbostock/us-atlas) to grab the shapefiles. The GeoJSON was generated with ogr2ogr using the following command:

```shell
$ ogr2ogr -f GeoJSON -t_srs EPSG:4326 output.geojson input.shp
```

The following shell commands were used to generate the topojson:

```shell
$ topojson -o world-countries.topo.json -- world-countries.geo.json
$ topojson -o us_states.topo.json -p FIPS -q 6000 -- us_states.geo.json
$ topojson -o us_counties.topo.json -p FIPS -q 8000 -- us_counties.geo.json
$ topojson -o or_counties.topo.json -p FIPS,COUNTY -q 8000 -- or_counties.geo.json
```
