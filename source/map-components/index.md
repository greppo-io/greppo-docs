# Map components

The components that provide an API interface to the geospatial visualizations are described here. Greppo uses [Leaflet](https://leafletjs.com/) to render and interact with geospatial data. The main components are:

```{toctree}
:maxdepth: 1

base-layer
overlay-layer
draw-feature
```

## Base layer

This provides the base layer to be used. It is usually a link to a tile server. Although only one base layer could be visible at a particular time, you can add many base-layers as options that can be toggled in the app. 

## Overlay layer

You can add as many overlay layers as you want. At this moment, only vector overlay layers can be added. Raster layers are forseen in the coming releases.

## Draw feature

Through the provided draw feature, you can draw Point, Line or Polygon on the map and can get the data of the drawn features using the `gpo.draw_feature()` API in your script as a GeoDataFrame. At this point you can have only one draw feature, but multiple draw features are foreseen. 
