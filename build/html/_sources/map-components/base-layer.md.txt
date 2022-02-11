# Base Layer
The Base Layer is used to render the Map component on the UI.

## Parameters
`provider` Supports the usage of [`xyzservices`](https://xyzservices.readthedocs.io/en/stable/introduction.html). The provider takes in a string that contains the referece to the tile-provider. Example: `provider = "CartoDB Positron"`

`name` Str value serving as a unique identifier for this UI component. (Required when `provider` is not pased. otherwise, this value overrides the value from the `provider`.)

`visible` Boolean toggle to turn on or off a Base Layer. A Greppo App can have multiple Base Layers.

`url` URL representing the resource. (Required when `provider` is not pased. otherwise, this value overrides the value from the `provider`.)

`attributions` Usage attributions for the data.

`subdomains` To point to the right subdomain of the URL passed. 

`min_zoom` Min zoom level of the tile layers.

`max_zoom` Max zoom level of the tile layers.

## Usage
```python
from greppo import app

app.base_layer(
    name="CartoDB Light",
    visible=True,
    url="https://cartodb-basemaps-a.global.ssl.fastly.net/light_all/{z}/{x}/{y}@2x.png",
    subdomains=None,
    attribution='&copy; <a target="_blank" href="http://osm.org/copyright">OpenStreetMap</a> contributors',
)

app.base_layer(
    provider = "CartoDB Positron"
)
# Possible alternative names:

provider = "CartoDB Positron"
provider = "cartodbpositron"
provider = "cartodb-positron"
provider = "carto db/positron"
provider = "CARTO_DB_POSITRON"
provider = "CartoDB.Positron"

```
