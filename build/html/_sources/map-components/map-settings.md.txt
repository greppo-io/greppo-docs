# Map Settings

To provide custom settings for the map in the front, use the `app.map()` method. The following settings are currently available. 

## Parameters

`zoom` Set the zoom value on load or for use with the home settings. The default value is `3`.

`center` Set the center of the map value on load or for use with the home settings. It takes in a array. The default value is `[0, 0]`.

`min_zoom` Set the minimum zoom posible on the map. The deafult value is `0`

`max_zoom` Set the maximum zoom posible on the map. The deafult value is `18`

## Usage
```python
from greppo import app

app.map(max_zoom=25, min_zoom=4)

```