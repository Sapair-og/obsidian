
### HTML Code for Registration Form

This code creates a simple form with fields for name, email, a course selection using checkboxes, and a submit button.

```html
<!DOCTYPE html>
<html>
<head>
    <title>Student Course Registration</title>
    <style>
        body { font-family: sans-serif; }
        form { width: 400px; margin: 20px auto; padding: 20px; border: 1px solid #ccc; border-radius: 5px; }
        label { display: block; margin-bottom: 5px; font-weight: bold; }
        input, select { width: 100%; padding: 8px; margin-bottom: 10px; box-sizing: border-box; }
        .checkbox-group label { display: inline-block; margin-right: 15px; font-weight: normal; }
        button { background-color: #007bff; color: white; padding: 10px 15px; border: none; border-radius: 5px; cursor: pointer; font-size: 16px; }
    </style>
</head>
<body>

    <h2>Student Course Registration</h2>

    <form action="/register" method="post">
        <div>
            <label for="name">Name:</label>
            <input type="text" id="name" name="name" required placeholder="Your Full Name">
        </div>

        <div>
            <label for="email">Email:</label>
            <input type="email" id="email" name="email" required placeholder="Your Email Address">
        </div>

        <div class="checkbox-group">
            <label>Select Courses:</label><br>
            <input type="checkbox" id="math" name="courses" value="math">
            <label for="math">Mathematics</label>

            <input type="checkbox" id="science" name="courses" value="science">
            <label for="science">Science</label>

            <input type="checkbox" id="history" name="courses" value="history">
            <label for="history">History</label>
        </div>

        <button type="submit">Register</button>
    </form>

</body>
</html>
```

-----

### Sample Output

When you open this HTML in a browser, you'll see a form with the following elements:

1.  A heading that says "**Student Course Registration**".
2.  A text input field labeled "**Name:**" where students can enter their full name. This field is marked as required.
3.  A text input field labeled "**Email:**" for their email address, also required.
4.  A section labeled "**Select Courses:**" with three checkboxes:
      * **Mathematics**
      * **Science**
      * **History**
        Students can select one or more of these courses.
5.  A button that says "**Register**". Clicking this button would submit the form data.

The minimal CSS included just makes it look a bit more organized and readable. You can copy and paste this directly into an HTML file to see it in your browser.