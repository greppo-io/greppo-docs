# WMS Tile Layer

The Web-Map Service (WMS) Tile Layer is used to render the layers served from a server using the URL provided, along with the `format` which it serves.

## Parameters

`name` Str value serving as a unique identifier for this layer component. 

`url` URL representing the WMS tile server. 

`description` Description string value rendered on the UI.

`visible` Boolean toggle to turn on or off a Base Layer. A Greppo App can have multiple Tile Layers.

`opacity` Change the opacity of the layer using a `float` value between `0.0` and `1.0`.

`layers` Name of the layers that are to be queried.

`subdomains` The subdomains through which the layers are served. A string or a list.

`attributions` Usage attributions for the data.

`format` For mat in which the tiles are served. The default is `'image/jpeg'`.

`transparent` If true, the WMS service will return images with transparency.

## Usage
```python
from greppo import app

app.wms_tile_layer(
    url='http://mesonet.agron.iastate.edu/cgi-bin/wms/nexrad/n0r.cgi', 
    name='Weather Data', 
    format='image/png', 
    layers='nexrad-n0r-900913', 
    description='Weather WMS tile layer'
    )
```