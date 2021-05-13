# Field Overrides

When adding fields in with a template, you might want to control how they are displayed in relation to existing fields on your Embeds or Pages. In this case, we can use field overrides.

## Usage

```python
from dpymenus import Template, FieldStyle, FieldSort

template = Template(..., 
        field_style=FieldStyle.COMBINE, 
        field_sort=FieldSort.LAST
    )
```

Both of the override options are enumerated values.

## Field Styles

**IGNORE**: templated fields will NOT be added if there is an existing field *(default)*

**COMBINE**: templated fields will be added if there is an existing field or not

**OVERRIDE**: templated fields will overwrite existing fields

## Field Sorts

Sorting only takes effect when using the `FieldStyle.COMBINE` on your template, as this determines how the fields will actually be combined.

**FIRST**: templated fields will be displayed before existing fields

**LAST**:  templated fields will be displayed after existing fields *(default)*
