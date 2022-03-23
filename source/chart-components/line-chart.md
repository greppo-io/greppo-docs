# Line Chart

2-D Line Chart is a UI component for rendering data.

## Parameters

`name` Str value serving as a unique identifier for this UI component. Serves as a title string rendered on the UI.

`description` - Description string rendered on the UI.

`x` - x-axis values.

`y` - y-axis values. In case of a multi-line chart, pass in a 2-dimensional list (list of list). In this case, the length of `color` and `label` should match the number of line dataset.

`label` - label of the data. Default is the name of the chart. In the case of a multi-line chart, should match the length of the number of line dataset.

`color` - Choose the background color for the chart data as Hex color code as `#123123` or a RGC color code as `"rgb(200, 50, 150)"`. In the case of a multi-line chart, should match the length of the number of line dataset.

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

# Multi-line chart
app.line_chart(
    name="A multi line chart",
    description="A simple multi line chart",
    x = ['1', '2', '3', '4'],
    y=[[3, 2, 1, 4],[3, 6, 2, 7]],
    label=['line 1', 'line 2'],
    color=["rgb(200, 50, 150)", "rgb(100, 50, 150)"],
)
```
