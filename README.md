import zipfile
import os

# Prepare the HTML content and files
html_content = """
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Top Tips to Get Huges - Pet Sim 99</title>
    <style>
        body {
            background-color: white;
            color: black;
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
        }

        .footprints {
            background-image: url('footprints.png'); /* Placeholder for footprints graphic */
            background-repeat: repeat;
            background-size: 50px;
            opacity: 0.2;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
        }

        .container {
            max-width: 800px;
            margin: auto;
            padding: 20px;
        }

        h1 {
            text-align: center;
            color: #333;
        }

        .tips {
            margin-top: 20px;
        }

        .tips li {
            margin-bottom: 10px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .vote-buttons {
            display: flex;
            gap: 10px;
        }

        .vote-buttons button {
            border: none;
            background-color: #ddd;
            padding: 5px 10px;
            border-radius: 3px;
            cursor: pointer;
        }

        .vote-buttons button:hover {
            background-color: #bbb;
        }

        .images-section {
            margin-top: 30px;
            text-align: center;
        }

        .images-section img {
            max-width: 100%;
            height: auto;
            margin: 10px 0;
        }

        .cta {
            margin-top: 20px;
            text-align: center;
        }

        .cta a {
            text-decoration: none;
            color: white;
            background-color: brown;
            padding: 10px 20px;
            border-radius: 5px;
        }

        .footer {
            margin-top: 30px;
            text-align: center;
            font-size: 14px;
            color: gray;
        }
    </style>
</head>
<body>
    <div class="footprints"></div>

    <div class="container">
        <h1>Top Tips to Get Huges in Pet Sim 99!</h1>
        <p>Welcome to your ultimate guide for getting Huges in Pet Sim 99. Follow these tips to maximize your chances of getting the best pets!</p>

        <ul class="tips">
            <li>
                <span><strong>Grind Coins:</strong> Focus on farming high-value areas to accumulate coins quickly.</span>
                <div class="vote-buttons">
                    <button>👍 Like</button>
                    <button>👎 Dislike</button>
                </div>
            </li>
            <li>
                <span><strong>Use Boosts:</strong> Activate coin and luck boosts before opening eggs.</span>
                <div class="vote-buttons">
                    <button>👍 Like</button>
                    <button>👎 Dislike</button>
                </div>
            </li>
            <li>
                <span><strong>Trade Smart:</strong> Engage in trading with other players to get rare Huges.</span>
                <div class="vote-buttons">
                    <button>👍 Like</button>
                    <button>👎 Dislike</button>
                </div>
            </li>
            <li>
                <span><strong>Participate in Events:</strong> Look out for limited-time events that increase Huge drop rates.</span>
                <div class="vote-buttons">
                    <button>👍 Like</button>
                    <button>👎 Dislike</button>
                </div>
            </li>
            <li>
                <span><strong>Upgrade Inventory:</strong> Make sure your inventory and equipment are optimized for farming.</span>
                <div class="vote-buttons">
                    <button>👍 Like</button>
                    <button>👎 Dislike</button>
                </div>
            </li>
        </ul>

        <div class="images-section">
            <h2>HUGES I OWN FROM THIS!</h2>
            <img src="golden_huge_duard_domingus.png" alt="Golden Huge Duard Domingus">
            <img src="huge_player_corgi.png" alt="Huge Player Corgi (Normal)">
        </div>

        <div class="cta">
            <a href="#">Check Back for Updates!</a>
        </div>

        <div class="footer">
            Visit us at <a href="http://www.PET.tips.com">www.PET.tips.com</a>
        </div>
    </div>
</body>
</html>
"""

# Define file paths
output_folder = '/mnt/data/PET_website'
html_file_path = os.path.join(output_folder, 'index.html')
zip_file_path = '/mnt/data/PET_website.zip'
image_files = ['golden_huge_duard_domingus.png', 'huge_player_corgi.png', 'footprints.png']

# Create the output folder
os.makedirs(output_folder, exist_ok=True)

# Save the HTML file
with open(html_file_path, 'w') as html_file:
    html_file.write(html_content)

# Create placeholder image files
for image_file in image_files:
    with open(os.path.join(output_folder, image_file), 'wb') as img_file:
        img_file.write(b'')  # Create empty placeholder files

# Create a zip file
with zipfile.ZipFile(zip_file_path, 'w') as zipf:
    for root, dirs, files in os.walk(output_folder):
        for file in files:
            zipf.write(os.path.join(root, file),
                       os.path.relpath(os.path.join(root, file), output_folder))

zip_file_path
