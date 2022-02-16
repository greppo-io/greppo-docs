# Vector Layer

The Vector Layer is used to render vector data from a geodataframe.

## Parameters

`data` GeoPandas DataFrame representing the vector data as geometris. The column data in the geodataframe that is passed is rendered as a pop-over data.

`name` Name string value rendered on the UI, to reference it to the layer.

`description` Description string value rendered on the UI.

`style` Styling options for this layer.

`visible` Boolean toggle to turn this layer on or off.

## Styling option adopted from [leaflet](https://leafletjs.com/reference.html#path-option)

| Option | Type | Default | Description |
|---|---|---|---|
|stroke | Boolean | true | Whether to draw stroke along the path. Set it to false to disable borders on polygons or circles. |
| color | String | '#3388ff' | Stroke color |
| weight | Number | 3 | Stroke | width in pixels |
| opacity | Number | 1.0 | Stroke opacity |
| lineCap | String | 'round' | A string that defines shape to be used at the end of the stroke. |
| lineJoin | String | 'round' | A string that defines shape to be used at the corners of the stroke. |
| dashArray | String | null | A string that defines the stroke dash pattern. Doesn't work on Canvas-powered layers in some old browsers. |
| dashOffset | String | null | A string that defines the distance into the dash pattern to start the dash. Doesn't work on Canvas-powered layers in some old browsers. |
| fill | Boolean | depends | Whether to fill the path with color. Set it to false to disable filling on polygons or circles. |
| fillColor	| String | * | Fill color. Defaults to the value of the color option |
| fillOpacity | Number | 0.2 | Fill opacity. |

## Usage (General)

```python
import geopandas as gpd
from greppo import app

data_gdf = gpd.read_file("./data/communes.geojson")

app.vector_layer(
    data = data_gdf,
    name = "Communes",
    description = "Communes in Normandy, France",
    style = {"fillColor": "#F87979"},
)
```

## Choropleth

The `vector_layer` also supports the display of the polygons (geometry) as a [choropleth map](https://en.wikipedia.org/wiki/Choropleth_map). To use this feature, the choropleth styling must be specified in the `style` argument of the `vector_layer`. The styling of `choropleth` is passed as a dictionary and must have the following 3 keys:

`key_on` The column name of the data that you want to map the choropleth. The column must be present in the GeoDataFrame that is passed in the `vector_layer`.

`bins` This represents the binning of the data that is to be presented as a choropleth map. This could be an `int` value representing the number of bins, or a list of the values to bin the data in. The list then should be increasing and the binning occurs with checking the value greater than the value in the array. Meaning:  

```
for 
bins = [0, 1, 5, 10, 20, 50]

then the values are binned as:

if value > 50: then bin = 6
if value > 20: then bin = 5
if value > 10: then bin = 4
if value > 5: then bin = 3
if value > 1: then bin = 2
if value > 0: then bin = 1
```

`palette` This represents the color scheme for the choropleth map. This could be a list of the colors as Hex codes or RGB functions as `rgb(r,g,b)`. You could also mention a colorbrewer palette as a `str`. The supported colorbrewer palette names are as follows: `'YlGn', 'YlGnBu', 'GnBu', 'BuGn', 'PuBuGn', 'PuBu', 'BuPu', 'RdPu', 'PuRd', 'OrRd', 'YlOrRd', 'YlOrBr', 'Purples', 'Blues', 'Greens', 'Oranges', 'Reds', 'Greys', 'PuOr', 'BrBG', 'PRGn', 'PiYG', 'RdBu', 'RdGy', 'RdYlBu', 'Spectral', 'RdYlGn', 'Accent', 'Dark2', 'Paired', 'Pastel1', 'Pastel2', 'Set1', 'Set2', 'Set3'`

## Usage (Choropleth)

```python
import geopandas as gpd
from greppo import app

data_gdf = gpd.read_file("./data/us-states.geojson")

choropleth_style = {
    'key_on': 'density', 
    'bins': [1, 10, 20, 50, 100, 200, 500, 1000],
    'palette': 'Blues',
}

app.vector_layer(
    data = data_gdf,
    name = "US-States",
    description = "States in the US with their density info.",
    style={"choropleth": choropleth_style},
)
```