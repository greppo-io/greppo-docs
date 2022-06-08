# Raster Layer

The Raster Layer is used to render numpy arrays extracted from a TIFF, geoTIFF or of any similar format. 

## Parameters

`data` the ndarray. The data to be drawn on the map. 

`bounds` Bounds for the image on the map in the form `[[lat_min, lon_min], [lat_max, lon_max]]`

`name` Str value serving as a unique identifier for this layer component. Which will also appear in the layer controls.

`description` Description string value rendered on the UI.

`origin` (['upper' | 'lower'], optional, default 'upper') Where to place the [0,0] index of the bounds array in the upper left or lower left corner of the axes.

`visible` Boolean toggle to turn on or off a Base Layer. A Greppo App can have multiple Tile Layers.

`opacity` Change the opacity of the layer using a `float` value between `0.0` and `1.0`.

`colormap` Function of the form [x -> (r,g,b)] or [x -> (r,g,b,a)] for transforming a mono image into RGB. It must output iterables of length 3 or 4, with values between 0 and 1. Hint: you can use colormaps from matplotlib.cm.

## Usage (General)

```python
from greppo import app
import numpy as np

band = np.zeros((61, 61))
band[0, :] = 1.0
band[60, :] = 1.0
band[:, 0] = 1.0
band[:, 60] = 1.0

app.raster_layer(
    data=band,
    bounds=[[0, -60], [60, 60]],
    colormap=lambda x: (1, 0, 0, x),
    name='Rectangle',
    description='A large red rectangle on a map.',
    visible=True,
)

```



