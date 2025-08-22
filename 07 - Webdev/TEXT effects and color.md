
## Text Effects (like `text-shadow`)

A great way to add depth to your text is by using the **`text-shadow`** property. It applies a shadow directly behind your text.

### Code Example

Here's how to add a simple, blurry grey shadow to a heading.

HTML

```
<!DOCTYPE html>
<html>
<head>
<title>Text Shadow</title>
<style>
    body { 
        font-family: Arial, sans-serif;
        background-color: #f0f0f0;
    }
    h1 {
        font-size: 60px;
        /* h-shadow | v-shadow | blur-radius | color */
        text-shadow: 2px 2px 5px #888888;
    }
</style>
</head>
<body>

    <h1>Shadow Effect</h1>

</body>
</html>
```

### Sample Output

The text "Shadow Effect" will appear on the page with a soft, grey shadow slightly below and to the right of the letters, making it look like it's floating.

### Quick Explanation

The `text-shadow` property takes four values:

- **Horizontal offset**: How far the shadow is to the right (`+`) or left (`-`).
    
- **Vertical offset**: How far the shadow is below (`+`) or above (`-`).
    
- **Blur radius**: How blurry the shadow is. `0` is a sharp shadow.
    
- **Color**: The color of the shadow.
    

---

## Text & Background Color

This is the most fundamental styling you'll do. You use two simple properties: **`color`** for the text and **`background-color`** for the area behind the text.

### Code Example

This code styles a paragraph with white text on a dark blue background.

HTML

```
<!DOCTYPE html>
<html>
<head>
<title>Color Example</title>
<style>
    p {
        color: white; /* Sets the text color */
        background-color: #003366; /* Sets the background color (a dark blue) */
        padding: 20px; /* Adds space so the background is visible */
        font-family: sans-serif;
    }
</style>
</head>
<body>

    <p>This text is white, and its background is dark blue.</p>

</body>
</html>
```

### Sample Output

You'll see a dark blue rectangle containing the text "This text is white, and its background is dark blue," written in white.

### Quick Explanation

- **`color`**: Sets the color of the text itself.
    
- **`background-color`**: Sets the color of the element's background, which extends to the edges of its content and padding.