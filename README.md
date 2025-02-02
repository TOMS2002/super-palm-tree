# Initial setup to create a basic site structure (mockup example)
# This will simulate the creation of a lightweight structure for the requested platform.

import os

# File structure for the mockup project
project_structure = {
    "project_name": "opera_restaurant_mockup",
    "folders": [
        "css",
        "js",
        "images",
        "pages"
    ],
    "files": {
        "index.html": """
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Opera Restaurant</title>
    <link rel="stylesheet" href="css/styles.css">
</head>
<body>
    <header>
        <h1>Welcome to Opera Restaurant</h1>
        <nav>
            <ul>
                <li><a href="#menu">Menu</a></li>
                <li><a href="#reservation">Reservation</a></li>
                <li><a href="#contact">Contact Us</a></li>
            </ul>
        </nav>
    </header>

    <section id="menu">
        <h2>Our Menu</h2>
        <p>Explore our delicious options of pizzas, desserts, and drinks.</p>
        <!-- Sample menu items -->
        <ul>
            <li>Margherita Pizza - $10</li>
            <li>Chocolate Cake - $5</li>
            <li>Mango Smoothie - $3</li>
        </ul>
    </section>

    <section id="reservation">
        <h2>Reserve a Table</h2>
        <form action="#" method="post">
            <label for="name">Name:</label>
            <input type="text" id="name" name="name" required><br>
            <label for="date">Date:</label>
            <input type="date" id="date" name="date" required><br>
            <label for="time">Time:</label>
            <input type="time" id="time" name="time" required><br>
            <label for="guests">Number of Guests:</label>
            <input type="number" id="guests" name="guests" min="1" required><br>
            <button type="submit">Reserve</button>
        </form>
    </section>

    <section id="contact">
        <h2>Contact Us</h2>
        <p>Address: 123 Opera Street, Lomé</p>
        <p>Phone: +228 90 68 88 88</p>
        <p>Email: info@opera-demo.com</p>
    </section>

    <footer>
        <p>&copy; 2025 Opera Restaurant. All rights reserved.</p>
    </footer>
</body>
</html>
        """,
        "css/styles.css": """
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    background-color: #f9f9f9;
    color: #333;
}

header {
    background-color: #333;
    color: #fff;
    padding: 1em;
    text-align: center;
}

header nav ul {
    list-style: none;
    padding: 0;
}

header nav ul li {
    display: inline;
    margin: 0 10px;
}

header nav ul li a {
    color: #fff;
    text-decoration: none;
}

section {
    padding: 2em;
    border-bottom: 1px solid #ddd;
}

footer {
    text-align: center;
    padding: 1em;
    background-color: #333;
    color: #fff;
}
        """
    }
}

# Create the mockup directory structure
base_path = "/mnt/data/" + project_structure["project_name"]
os.makedirs(base_path, exist_ok=True)

# Create subfolders and files
for folder in project_structure["folders"]:
    os.makedirs(os.path.join(base_path, folder), exist_ok=True)

for file_name, content in project_structure["files"].items():
    file_path = os.path.join(base_path, file_name)
    with open(file_path, "w") as file:
        file.write(content)

base_path
