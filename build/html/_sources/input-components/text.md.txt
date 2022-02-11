# Text
Text input is a simple string value, `app.text`,

## Parameters
`name` - String value serving as a unique identifier for this UI component. Which is also displayed in the UI for this input.

`value` - Default value for the text. This value is used the first time the Greppo App is run and subsequent runs will
reuse the existing state from the UI (ie. if the user changes the value it will persist until changed).

## Usage
```python
from greppo import app

text_1 = app.text(value='Enter text', name="text input 1")
```
