# Multiselect
Multiselect UI component that allows a user to pick one or more values from a list of values as a dropdown menu.

## Parameters
`name` - String value serving as a unique identifier for this UI component. Which is also displayed in the UI for this input.

`options` - List of possible values to select from. Value type is `[int, float, str, bool]`.

`default` - The default selection when the Greppo App is run for the first time.

## Usage
```python
from greppo import app

multiselect1 = app.multiselect(
    name="Second selector", options=["Asia", "Africa", "Europe"], default=["Asia"]
)
```