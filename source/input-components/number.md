# Number
Number input is a simple scalar value, `app.number`,

## Parameters
`name` - String value serving as a unique identifier for this UI component. Which is also displayed in the UI for this input.

`value` - Default value for the number. This value is used the first time the Greppo App is run and subsequent runs will
reuse the existing state from the UI (ie. if the user changes the value it will persist until changed).

## Usage
```python
from greppo import app

number_1 = app.number(value=10, name="Number input 1")
```
