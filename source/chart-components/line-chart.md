# Line Chart

2-D Line Chart is a UI component for rendering data.

## Parameters

`name` Str value serving as a unique identifier for this UI component. Serves as a title string rendered on the UI.

`description` - Description string rendered on the UI.

`x` - x-axis values.

`y` - y-axis values.

`color` - Choose the background color for the chart data as Hex color code as `#123123` or a RGC color code as `"rgb(200, 50, 150)"`.

## Usage

```python
from greppo import app

app.line_chart(
    name="A bar chart",
    description="A simple bar chart",
    x = ['1', '2', '3', '5'],
    y = [1, 2, 3, 4],
    color="rgb(200, 50, 150)",
)
```
