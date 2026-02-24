# dataconf

> NOW INCLUDED AS PART OF https://github.com/lekoala/liveinit

A lightweight, json5 like, format for storing configuration object in a data attribute.

It features:
- Optional root braces
- Optional key quotes
- Allow single quotes for values (easier to nest inside double quoted attributes)

This is basically a subset of JSON5, because there is no need to support comments, multilines, trailing quotes, etc.

Example:

```html
<button id="my-button"
        data-config="label: 'Submit', onsubmit: 'handleFormSubmit'">
    Click Me
</button>

<div id="my-component"
     data-config="some: 'value', arr: [1,2,3], nested: {key:'here'}">
</div>
```

Note : this approach relies on some simple regex transforms before feeding the result to `JSON.parse`. It may
break for very complex use cases (in which case: simply use regular json).
