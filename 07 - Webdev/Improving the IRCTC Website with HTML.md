
### The Problem

The IRCTC website is often cluttered and uses outdated HTML practices. The key to improving it is to introduce a clean, logical structure using modern, **[[Semantic HTML]]**. This makes the code more readable, accessible, and easier to style.

---

### Solution: Improved HTML Structure & CSS

This code focuses on rebuilding the main ticket booking form in a clean, semantic way.

HTML

```
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Improved IRCTC Booking</title>
    <style>
        /* Minimal CSS to make it look decent */
        body { font-family: Arial, sans-serif; background-color: #f4f4f4; text-align: center; }
        .booking-card { 
            background-color: white; 
            width: 350px; 
            margin: 50px auto; 
            padding: 20px; 
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
            border-radius: 8px;
        }
        label { 
            display: block; /* Puts the label on its own line */
            text-align: left; 
            margin-top: 10px; 
            font-weight: bold;
        }
        input { 
            width: 95%; 
            padding: 8px; 
            margin-top: 5px; 
        }
        button { 
            width: 100%; 
            padding: 10px; 
            margin-top: 20px; 
            background-color: #fb792b; 
            color: white; 
            border: none; 
            cursor: pointer;
            font-size: 16px;
        }
    </style>
</head>
<body>

    <main>
        <section class="booking-card">
            <h2>Book Your Ticket</h2>
            <form action="/search-trains" method="post">
                <label for="from-station">From:</label>
                <input type="text" id="from-station" name="from_station" placeholder="From Station">

                <label for="to-station">To:</label>
                <input type="text" id="to-station" name="to_station" placeholder="To Station">
                
                <label for="journey-date">Date:</label>
                <input type="date" id="journey-date" name="journey_date">

                <button type="submit">Search Trains</button>
            </form>
        </section>
    </main>

</body>
</html>
```

---

### Explanation & Key Concepts

- **[[Semantic HTML]] Tags**: We use `<main>` for the primary content and `<section>` to group the related elements of the booking form. This is better than a generic `<div>` because it clearly describes the content's purpose.
    
- **[[HTML Forms]]**: The entire input area is wrapped in a `<form>` tag, which is essential for collecting and submitting user data.
    
- **[[Labels in HTML]]**: This is **critical**. Every `<input>` has a corresponding `<label>`. The `for` attribute of the label is linked to the `id` of the input. This is a huge win for **accessibility** (screen readers) and **usability** (clicking the text focuses the input box).
    
- **[[CSS]] Styling**: The basic CSS included in the `<style>` tag demonstrates how a well-structured HTML document is much easier to make visually appealing. Good structure simplifies styling.
    
