
## CSS Selectors

Selectors are how you tell CSS _which_ HTML elements to style. The three most important types you need to know are **Element**, **ID**, and **Class**.

### Code Example

This example shows all three selectors in action.

HTML

```
<!DOCTYPE html>
<html>
<head>
<title>CSS Selectors</title>
<style>
    /* 1. Element Selector: Targets all <p> tags */
    p {
        color: green;
    }

    /* 2. ID Selector: Targets the one element with id="special" */
    #special {
        font-weight: bold;
        font-style: italic;
    }

    /* 3. Class Selector: Targets all elements with class="highlight" */
    .highlight {
        background-color: yellow;
    }
</style>
</head>
<body>

    <p>This is a paragraph. It will be green.</p>
    
    <div id="special">This div is special. It will be bold and italic.</div>
    
    <h2 class="highlight">This heading will have a yellow background.</h2>
    <p class="highlight">This paragraph will ALSO have a yellow background.</p>

</body>
</html>
```

### Sample Output

1. The first paragraph ("This is a paragraph...") will have **green text**.
    
2. The `div` with the text "This div is special..." will be **bold and italic**.
    
3. Both the `h2` heading and the last paragraph will have a **yellow background**.
    

### Quick Explanation

- **Element Selector**: `p`
    
    - **What it does**: Selects every single `<p>` element on the page.
        
    - **Use when**: You want to apply a base style to all elements of the same type.
        
- **ID Selector**: `#special`
    
    - **What it does**: Selects the _one and only_ element with `id="special"`. An ID must be unique on a page.
        
    - **Use when**: You need to style one specific, unique element.
        
- **Class Selector**: `.highlight`
    
    - **What it does**: Selects any and all elements that have `class="highlight"`. You can reuse a class on many elements.
        
    - **Use when**: You want to apply the same style to multiple, different elements.
        

---

## Backgrounds and Borders

These properties are for styling the space inside and around an element.

### Code Example

This code styles a `div` with a background color, an image, a solid border, and rounded corners.

HTML

```
<!DOCTYPE html>
<html>
<head>
<title>Backgrounds and Borders</title>
<style>
    div {
        width: 300px;
        padding: 20px;
        font-family: sans-serif;

        /* Background Properties */
        background-color: #e0f7fa; /* A light cyan background */
        
        /* Border Properties */
        border: 4px solid #00796b; /* A thick, solid, dark teal border */
        border-radius: 15px; /* This rounds the corners */
    }
</style>
</head>
<body>

    <div>
        This box has a light cyan background, a solid dark teal border, and rounded corners.
    </div>

</body>
</html>
```

### Sample Output

You will see a box on the page. The box will have:

- A light cyan background color.
    
- A thick, dark teal line around its edges.
    
- Corners that are noticeably rounded instead of sharp 90-degree angles.
    

### Quick Explanation

- **`background-color`**: Sets a solid color for the background of the element.
    
- **`border`**: This is a shorthand property to set the border's **width** (`4px`), **style** (`solid`), and **color** (`#00796b`) all in one line. Other styles include `dashed`, `dotted`, and `double`.
    
- **`border-radius`**: Controls how rounded the corners of the element are. A higher value means a more rounded corner.