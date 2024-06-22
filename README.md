
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Image Upload with Password Protection</title>
    <link href="https://maxcdn.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css" rel="stylesheet">
    <style>
       /* Body and general styles */
/* Body and general styles */
.no-copy {
    -webkit-user-select: none;  /* Safari */
    -moz-user-select: none;     /* Firefox */
    -ms-user-select: none;      /* Internet Explorer/Edge */
    user-select: none;          /* Standard syntax */
}
/* General styles */
/* General styles */
body {
    font-family: 'Arial', sans-serif;
    background-color: #040000;
    margin: 0;
    padding: 0;
}

.container {
    max-width: 800px;
    margin: 20px auto;
    background-color: #fff;
    padding: 20px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    border-radius: 8px;
}

h2 {
    text-align: center;
    margin-bottom: 20px;
}

/* Form styles */
.form-group {
    margin-bottom: 20px;
}

.form-control {
    width: 100%;
    padding: 10px;
    font-size: 16px;
    border: 1px solid #ccc;
    border-radius: 4px;
    box-sizing: border-box;
}

.btn {
    display: inline-block;
    background-color: #007bff;
    color: #fff;
    padding: 10px 20px;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    transition: background-color 0.3s ease;
}

.btn:hover {
    background-color: #0056b3;
}

/* Thumbnail styles */
#thumbnailContainer {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-around;
}

.thumbnail-container {
    position: relative;
    width: calc(50% - -100px); /* Adjust thumbnail width here */
    margin-bottom: 20px;
    overflow: hidden;
    border: 1px solid #000000; /* Border around thumbnails */
    border-radius: 8px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    background-color: #fff;
    transition: transform 0.3s ease;
}

.thumbnail-container:hover {
    transform: translateY(-5px); /* Lift thumbnail on hover */
}

.thumbnail-container img {
    width: 500%;
    height: auto;
    cursor: pointer;
    transition: transform 0.3s ease;
    object-fit: cover; /* Ensure images fit within their container */
}

.thumbnail-container img.locked-image {
    width: 500px; /* Fixed size for locked images */
    height: 200px; /* Set desired height */
    object-fit: cover; /* Ensure images fit within their container */
}

.thumbnail-container img:hover {
    transform: scale(1.05); /* Zoom effect on hover */
}

.locked-overlay {
    position: absolute;
    top: 0;
    left: 0;
    width: 15;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.5);
    color: #fff;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 20px;
    font-weight: bold;
    text-align: center;
    opacity: 0;
    transition: opacity 0.3s ease;
}

.thumbnail-container:hover .locked-overlay {
    opacity: 1;
}

.thumbnail-container p {
    text-align: center;
    margin-top: 5px;
}

/* Password Popup styles */
.popup {
    display: none;
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    background-color: #fff;
    padding: 20px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    border-radius: 8px;
    z-index: 1000;
    max-width: 400px;
    width: 100%;
}

.popup h4 {
    text-align: center;
    margin-bottom: 20px;
}

.close-btn {
    position: absolute;
    top: 10px;
    right: 10px;
    font-size: 24px;
    cursor: pointer;
    color: #999;
    transition: color 0.3s ease;
}

.close-btn:hover {
    color: #666;
}

#passwordInput {
    width: calc(100% - 20px);
    padding: 10px;
    font-size: 16px;
    border: 1px solid #ccc;
    border-radius: 4px;
    box-sizing: border-box;
    margin-bottom: 10px;
}

#passwordSubmit {
    width: 100%;
    padding: 10px;
    font-size: 16px;
    background-color: #28a745;
    color: #fff;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    transition: background-color 0.3s ease;
}

#passwordSubmit:hover {
    background-color: #218838;
}

/* Loader animation */
#loader {
    text-align: center;
    display: none;
    margin-top: 10px;
}

.loader {
    border: 4px solid #f3f3f3;
    border-radius: 50%;
    border-top: 4px solid #3498db;
    width: 30px;
    height: 30px;
    animation: spin 1s linear infinite;
}

@keyframes spin {
    0% { transform: rotate(0deg); }
    100% { transform: rotate(360deg); }
}

#exitLogo {
        position: absolute;
        top: 10px;
        right: 10px;
        width: 50px; /* Fixed width */
        height: 50px; /* Fixed height */
        display: flex;
        justify-content: center;
        align-items: center;
      }
      
      #exitLogo img {
        width: 100%;
        height: 100%;
        object-fit: contain; /* Maintain aspect ratio */
      }
      h1{
      display:none;
      }
    </style>
</head>
<body>

<div class="container mt-5">
    <div class="no-copy">
    <h2 class="text-center">Upload an Image</h2>
    <form id="uploadForm" class="mb-4">
        <a href="https://igtradingmaster.github.io/Home/" id="exitLogo">
            <img src="https://t3.ftcdn.net/jpg/04/51/52/52/360_F_451525222_IKqxMEeAVBS6Pj5JpJU0MxnQAtasHZPe.jpg" alt="Exit Logo">
          </a>
        <div class="form-group">
            <input type="file" id="imageInput" class="form-control">
        </div>
        <div class="form-group">
            <input type="text" id="imageName" class="form-control" placeholder="Enter image name" required>
        </div>
        <div class="form-group">
            <input type="password" id="imagePassword" class="form-control" placeholder="Create a password" required>
        </div>
        <button type="submit" class="btn btn-primary btn-block">Submit</button>
    </form>
    <div id="thumbnailContainer" class="text-center"></div>
</div>
</div>
<div id="passwordPopup" class="popup">
    <h4 class="text-center">Enter Password</h4>
    <button class="close-btn">&times;</button> <!-- Close button added -->
    <input type="password" id="passwordInput" class="form-control mb-2">
    <button id="passwordSubmit" class="btn btn-primary btn-block">Submit</button>
    <div id="loader" class="text-center mt-2" style="display:none;">
        <div class="loader"></div>
        <span>Checking...</span>
    </div>
</div>




<script src="https://code.jquery.com/jquery-3.5.1.min.js"></script>
<script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.5.2/js/bootstrap.min.js"></script>
<script>
 $(document).ready(function() {
    // Load existing images from localStorage on page load
    loadImages();

    // Function to load existing images from localStorage
    function loadImages() {
        const images = JSON.parse(localStorage.getItem('userImages')) || [];
        images.forEach(imageData => {
            addThumbnail(imageData.id, imageData.name);
        });
    }

    // Function to handle form submission and image upload
    $('#uploadForm').on('submit', function(e) {
        e.preventDefault();
        const file = $('#imageInput')[0].files[0];
        const imageName = $('#imageName').val();
        const imagePassword = $('#imagePassword').val();

        // Validate file type
        if (file && isValidImageFile(file)) {
            const reader = new FileReader();
            reader.onload = function(e) {
                const imageData = e.target.result;
                const imageId = new Date().getTime();
                // Check if image with the same name already exists
                if (isImageNameAvailable(imageName)) {
                    saveImage(imageId, imageName, imagePassword, imageData);
                    addThumbnail(imageId, imageName); // Add thumbnail to display
                    $('#uploadForm')[0].reset(); // Reset form fields
                } else {
                    alert('Image with the same name already exists. Please use a different name.');
                }
            };
            reader.readAsDataURL(file); // Read uploaded file as data URL
        } else {
            alert('Please select a valid image file (jpg, jpeg, png, gif).');
        }
    });

    // Function to validate file type
    function isValidImageFile(file) {
        const acceptedImageTypes = ['image/jpeg', 'image/jpg', 'image/png', 'image/gif'];
        return acceptedImageTypes.includes(file.type);
    }

    // Function to check if image name is available
    function isImageNameAvailable(name) {
        const images = JSON.parse(localStorage.getItem('userImages')) || [];
        return images.every(img => img.name !== name);
    }

    // Function to save image data to localStorage permanently
    function saveImage(id, name, password, data) {
        let images = JSON.parse(localStorage.getItem('userImages')) || [];
        images.push({
            id: id,
            name: name,
            password: password,
            data: data
        });
        localStorage.setItem('userImages', JSON.stringify(images));
    }

    // Function to add thumbnail of uploaded image
    function addThumbnail(id, name) {
    const thumbnailHtml = `
        <div class="col-md-4">
            <div class="thumbnail-container">
                <img src="locked.png" class="img-thumbnail locked-image" data-id="${id}">
                <div class="locked-overlay">Locked</div>
                <p>${name}</p>
            </div>
            <button class="delete-btn btn btn-danger btn-block" data-id="${id}">Delete</button>
        </div>
    `;
    $('#thumbnailContainer').append(thumbnailHtml); // Append thumbnail HTML
}


    // Event handler for clicking on a thumbnail to open password popup
    $('#thumbnailContainer').on('click', '.thumbnail-container', function() {
        const imageId = $(this).find('img').data('id');
        $('#passwordPopup').data('image-id', imageId).show(); // Show password popup
    });

    // Event handler for clicking delete button to remove image
    $('#thumbnailContainer').on('click', '.delete-btn', function(e) {
        e.stopPropagation(); // Prevent click from bubbling to parent
        const imageId = $(this).data('id');
        deleteImage(imageId); // Delete image from localStorage and UI
    });

    // Event handler for closing the password popup
    $('#passwordPopup').on('click', '.close-btn', function() {
        $('#passwordPopup').hide();
        $('#passwordInput').val(''); // Clear password input
    });

    // Event handler for submitting password to view image
    $('#passwordSubmit').on('click', function() {
        const imageId = $('#passwordPopup').data('image-id');
        const enteredPassword = $('#passwordInput').val();
        const images = JSON.parse(localStorage.getItem('userImages')) || [];
        const imageData = images.find(img => img.id === imageId);
        $('#loader').show(); // Show loader animation
        setTimeout(() => {
            $('#loader').hide(); // Hide loader animation after timeout
            if (imageData && enteredPassword === imageData.password) {
                $('#passwordPopup').hide(); // Hide password popup
                const newWindow = window.open("", "ImageWindow", "width=600,height=400");
                if (newWindow) {
                    newWindow.document.write(`<img src="${imageData.data}" style="max-width: 100%; max-height: 100%;">`);
                    // Check if new window is closed to lock image again
                    const checkWindowClosed = setInterval(() => {
                        if (newWindow.closed) {
                            clearInterval(checkWindowClosed);
                            lockImage(imageId); // Lock image after window is closed
                        }
                    }, 500);
                } else {
                    alert('Popup window blocked. Please allow popups for this site.');
                }
            } else {
                alert('Wrong password'); // Show alert for wrong password
            }
        }, 5000); // Simulate checking process
    });

    // Function to lock image and clear password input
    function lockImage(imageId) {
        $('#passwordInput').val(''); // Clear password input
        $('.thumbnail-container img[data-id="' + imageId + '"]').attr('src', 'locked.png'); // Lock image
        $('.thumbnail-container img[data-id="' + imageId + '"]').siblings('.locked-overlay').show(); // Show locked overlay
    }

    // Function to delete image from localStorage and UI
    function deleteImage(imageId) {
        let images = JSON.parse(localStorage.getItem('userImages')) || [];
        images = images.filter(img => img.id !== imageId);
        localStorage.setItem('userImages', JSON.stringify(images));
        $(`.delete-btn[data-id="${imageId}"]`).parent().remove(); // Remove thumbnail and delete button from UI
    }

    // Event listener for tracking user activity (closing window, device shutdown)
    $(window).on('beforeunload', function() {
        // Do not clear localStorage here to keep data permanent
    });
});

   </script>
