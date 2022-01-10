# Display

The `display` API gives you the ability to display markdown text and simple text in the frontend. As well as setting the `title` and `description` of your app.

The **About me** of the app can be set by setting the `title` and `description` of the app.

## Parameters

`name` - String value serving as a unique identifier for the display component.

- If `name = "title"`, will set the **title** of the app.
- If `name = "description"`, will set the **description** of the app.

`value` - String or a multiline string, containing the mardown ot text to be displayed. 

## Usage

```python
from greppo import app

# Setting the title of the app.
app.display(value='Title of the app', name="title")

# Setting the description of the app.
app.display(value='Description of the app.', name="description")

# Passing a markdown text to the app.
md_text = """
# Heading

## Sub heading

The data that is shown above is some text in markdown parsed into html. The
data below is some data that will be shown in its data form.

Below is a list.

- Item 1
- Item 2
- Item 3
"""
app.display(value=md_text, name="md_text")
```
