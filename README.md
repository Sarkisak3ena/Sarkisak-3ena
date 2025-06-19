import qrcode

# HTML content for the menu page
html_content = """
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>sarkisak 3ena - Cocktail Menu</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background-color: #ffefd5;
            color: #333;
            margin: 0;
            padding: 0;
            text-align: center;
        }
        header {
            background-color: #ff69b4;
            color: white;
            padding: 20px 0;
        }
        h1 {
            margin: 0;
            font-size: 2.5em;
        }
        .menu-section {
            margin: 20px;
        }
        .menu-section h2 {
            background-color: #ff4500;
            color: white;
            padding: 10px;
            border-radius: 5px;
        }
        .menu-item {
            background-color: #fff;
            margin: 10px 0;
            padding: 10px;
            border-radius: 5px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        footer {
            background-color: #ff69b4;
            color: white;
            padding: 10px 0;
            position: fixed;
            width: 100%;
            bottom: 0;
        }
    </style>
</head>
<body>
    <header>
        <h1>sarkisak 3ena</h1>
        <p>Contact: +961 71 851 459</p>
    </header>
    <div class="menu-section">
        <h2>COCKTAILS</h2>
        <div class="menu-item">Pina colada</div>
        <div class="menu-item">Banana colada</div>
        <div class="menu-item">Pink drink</div>
        <div class="menu-item">Signature drink</div>
        <div class="menu-item">Gin basil</div>
        <div class="menu-item">Cherry basil smash</div>
        <div class="menu-item">Gin tonic</div>
        <div class="menu-item">Cherry vodka sunrise</div>
        <div class="menu-item">Tequila sunrise</div>
        <div class="menu-item">Bull frog</div>
        <div class="menu-item">Sex on the beach</div>
        <div class="menu-item">Baileys chocolatini</div>
        <div class="menu-item">Hot toddy</div>
        <div class="menu-item">Blue lagoon</div>
        <div class="menu-item">Margarita</div>
        <div class="menu-item">Cosmopolitan</div>
        <div class="menu-item">Mai tai</div>
        <div class="menu-item">Jamaica</div>
    </div>
    <footer>
        <p>Come and enjoy our vibrant cocktails!</p>
    </footer>
</body>
</html>
"""

# Save the HTML content to a file
with open("menu.html", "w") as file:
    file.write(html_content)

# Generate a QR code that links to the menu file
qr = qrcode.QRCode(
    version=1,
    error_correction=qrcode.constants.ERROR_CORRECT_H,
    box_size=10,
    border=4,
)
qr.add_data("menu.html")
qr.make(fit=True)

# Create an image from the QR Code instance
img = qr.make_image(fill='black', back_color='white')

# Save the QR code as "menu_qrcode.png"
img.save("menu_qrcode.png")

print("The menu page has been created and saved as 'menu.html'.")
print("The QR code linking to the menu has been saved as 'menu_qrcode.png'.")

