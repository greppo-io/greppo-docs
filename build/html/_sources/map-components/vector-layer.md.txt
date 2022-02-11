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

## Usage

```python
import geopandas as gpd
from greppo import app

data_gdf_1 = gpd.read_file("tests/data/communes.geojson")

app.vector_layer(
    data = data_gdf_1,
    name = "Communes",
    description = "Communes in Normandy, France",
    style = {"fillColor": "#F87979"},
    visible = True,
)
```
