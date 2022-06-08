# Image Layer

The Image Layer is used to render image layers that have or do not have geospatial-embedded data in them. These layers typically handle .TIFF, .png, .jpeg, and could be from a local folder or from a url.

## Parameters

`image` file path to an image file or a url to the image. 

`bounds` Bounds for the image on the map in the form `[[lat_min, lon_min], [lat_max, lon_max]]`

`name` Str value serving as a unique identifier for this layer component. Which will also appear in the layer controls.

`description` Description string value rendered on the UI.

`visible` Boolean toggle to turn on or off a Base Layer. A Greppo App can have multiple Tile Layers.

`opacity` Change the opacity of the layer using a `float` value between `0.0` and `1.0`.

## Usage (General)

```python
from greppo import app

app.image_layer(
    image='/data/europe.jpg',
    bounds=[        
        [26.954778413559467, -18.960764010156442],
        [69.17386061853473, 52.828854567988834],
    ],
    name='Eruope pic',
    description='Random picture of europe',
    visible=True,
)
```