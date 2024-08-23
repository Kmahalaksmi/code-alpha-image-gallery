<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Image Gallery with Navigation</title>
    <style>
        /* CSS styles go here */

        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background: url('https://source.unsplash.com/random/1920x1080') no-repeat center center/cover;
            position: relative;
            overflow: hidden;
        }

        body::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.6); /* Dark overlay */
            z-index: 1;
        }

        .gallery-container {
            width: 80%;
            max-width: 1200px;
            text-align: center;
            background: rgba(255, 255, 255, 0.15);
            backdrop-filter: blur(10px);
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.5);
            position: relative;
            z-index: 2;
        }

        .selected-image {
            margin-bottom: 20px;
            position: relative;
        }

        .selected-image img {
            width: 100%;
            max-height: 500px;
            object-fit: contain;
            border: 2px solid #ddd;
            border-radius: 5px;
        }

        .thumbnail-container {
            display: flex;
            justify-content: space-between;
            margin-top: 20px;
        }

        .thumbnail {
            width: 23%;
            cursor: pointer;
            transition: transform 0.2s ease;
            border: 2px solid #ddd;
            border-radius: 5px;
        }

        .thumbnail:hover {
            transform: scale(1.05);
        }

        .thumbnail:active {
            transform: scale(0.95);
        }

        .nav-button {
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
            background-color: rgba(0, 0, 0, 0.7);
            color: white;
            border: none;
            padding: 10px;
            cursor: pointer;
            font-size: 18px;
            border-radius: 50%;
            z-index: 3;
        }

        .prev-button {
            left: 10px;
        }

        .next-button {
            right: 10px;
        }

        .nav-button:hover {
            background-color: rgba(0, 0, 0, 0.9);
        }
    </style>
</head>
<body>
    <div class="gallery-container">
        <div class="selected-image">
            <button class="nav-button prev-button" onclick="navigate(-1)">&#10094;</button>
            <img id="mainImage" src="C:/Users/22ad086/Documents/image galey/images/image4.PNG" alt="Selected Image">
            <button class="nav-button next-button" onclick="navigate(1)">&#10095;</button>
        </div>
        <div class="thumbnail-container">
            <img class="thumbnail" src="C:/Users/22ad086/Documents/image galey/images/image4.PNG" alt="Thumbnail 1" onclick="showImage(0)">
            <img class="thumbnail" src="C:/Users/22ad086/Documents/image galey/images/image3.PNG" alt="Thumbnail 2" onclick="showImage(1)">
            <img class="thumbnail" src="C:/Users/22ad086/Documents/image galey/images/image2.PNG" alt="Thumbnail 3" onclick="showImage(2)">
            <img class="thumbnail" src="C:/Users/22ad086/Documents/image galey/images/image1.PNG" alt="Thumbnail 4" onclick="showImage(3)">
        </div>
    </div>

    <script>
        // JavaScript code goes here

        const images = [
            'C:/Users/22ad086/Documents/image galey/images/image4.PNG',
            'C:/Users/22ad086/Documents/image galey/images/image3.PNG',
            'C:/Users/22ad086/Documents/image galey/images/image2.PNG',
            'C:/Users/22ad086/Documents/image galey/images/image1.PNG'
        ];

        let currentIndex = 0;

        function showImage(index) {
            currentIndex = index;
            const mainImage = document.getElementById('mainImage');
            mainImage.src = images[currentIndex];
        }

        function navigate(direction) {
            currentIndex += direction;
            if (currentIndex < 0) {
                currentIndex = images.length - 1;
            } else if (currentIndex >= images.length) {
                currentIndex = 0;
            }
            showImage(currentIndex);
        }
    </script>
</body>
</html>
# code-alpha-image-gallery
