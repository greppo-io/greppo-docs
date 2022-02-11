# Tile Layer

The Tile Layer is used to render the layers served from a tile server using the URL provided.

## Parameters

`name` Str value serving as a unique identifier for this layer component. 

`url` URL representing the tile server. 

`description` Description string value rendered on the UI.

`visible` Boolean toggle to turn on or off a Base Layer. A Greppo App can have multiple Tile Layers.

`opacity` Change the opacity of the layer using a `float` value between `0.0` and `1.0`.

## Usage
```python
from greppo import app

app.tile_layer(
    name="CartoDB Light",
    url="https://cartodb-basemaps-a.global.ssl.fastly.net/light_all/{z}/{x}/{y}@2x.png",
    description="Description of the layer goes here."
    visible=True,   
    opacity=float = 1.0, 
)

```