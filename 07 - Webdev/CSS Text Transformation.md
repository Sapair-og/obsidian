
### Code Example

This code shows the three main values for `text-transform`: `uppercase`, `lowercase`, and `capitalize`.

HTML

```
<!DOCTYPE html>
<html>
<head>
    <title>Text Transform Example</title>
    <style>
        body { font-family: sans-serif; }
        .uppercase {
            text-transform: uppercase;
        }
        .lowercase {
            text-transform: lowercase;
        }
        .capitalize {
            text-transform: capitalize;
        }
    </style>
</head>
<body>

    <h2>Original Text: "This is some sample text."</h2>

    <p class="uppercase">This is some sample text.</p>
    <p class="lowercase">This is some sample text.</p>
    <p class="capitalize">This is some sample text.</p>

</body>
</html>
```

---

### Sample Output

Here’s how that HTML file would look in a browser.

**THIS IS SOME SAMPLE TEXT.**

**this is some sample text.**

**This Is Some Sample Text.**

### Quick Explanation

- **`uppercase`**: Makes every letter in the text a capital letter.
    
- **`lowercase`**: Makes every letter in the text a small letter.
    
- **`capitalize`**: Capitalizes the first letter of each word.