
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
     <!-- Remove the unwanted code snippet -->
    <!-- Begin Jekyll SEO tag v2.8.0 -->
    <!-- ... -->
    <!-- end custom head snippets -->
   <center> <title>Need Help</title>
    <!-- Link your CSS file -->
    <link rel="stylesheet" href="/NEED-HELP/assets/css/style.css?v=eeac4e013c39aee2e5eefcc373dde28a9bc4baa2">
    <!-- Start custom head snippets, customize with your own _includes/head-custom.html file -->
    <!-- Setup Google Analytics -->
    <!-- You can set your favicon here -->
    <!-- end custom head snippets -->
    <title>Chat with Employee</title>
    <!-- Bootstrap CSS -->
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css">
    <!-- Custom CSS -->
    <style>
        /* Your custom styles here */
        .loader-container {
            text-align: center;
        }

        body {
            background-color: #333;
        }

        .loader {
            border: 4px solid #333;
            border-radius: 50%;
            border-top: 4px solid #3498db;
            width: 30px;
            height: 30px;
            animation: spin 1s linear infinite;
            margin: 0 auto;
        }

        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        .loader-container {
            text-align: center;
        }

        /* New loader style */
        .loader {
            border: 4px solid #333;
            border-radius: 5px;
            border-top: 4px solid #3498db;
            width: 50px;
            height: 20px;
            animation: pulse 1s ease-in-out infinite;
            margin: 0 auto;
        }

        @keyframes pulse {
            0% {
                transform: scale(0.8);
            }
            50% {
                transform: scale(1);
            }
            100% {
                transform: scale(0.8);
            }
        }
    </style>

<body>

<div class="container mt-5">
    <div class="row">
        <div class="col-md-8 offset-md-2">
            <div class="card">
                <div class="card-header">
                    <img id="support-img" src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRdIdXtxpWsa_WmQn1iz94zBsJtmZVdVBOFcohHTu59Uw&s" alt="Customer Support Logo" width="30">
                    Helping Employee
                </div>
                <div class="card-body">
                    <!-- Chat messages will be displayed here -->
                    <div id="chat-container"></div>
                </div>
                <div class="card-footer">
                    <div id="loader" class="loader-container">
                        <div class="loader"></div>
                        <p>Please wait, checking for employee availability...</p>
                    </div>
                    <div id="green-mark" class="d-none green-mark">Employee is available</div>
                    <div class="input-group mt-3">
                        <select id="issue-select" class="custom-select">
                            <option value="" selected>Select Issue...</option>
                            <option value="mobile">Mobile Number Incorrect</option>
                            <option value="password">Password Error</option>
                            <option value="backup">Backup Code Error</option>
                            <option value="download">Download APK Error</option>
                            <option value="other">Other Error</option>
                        </select>
                        <div class="input-group-append">
                            <button id="send-btn" class="btn btn-primary" disabled>Send</button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</div>

<!-- Bootstrap JS and jQuery -->
<script src="https://code.jquery.com/jquery-3.5.1.slim.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/@popperjs/core@2.5.4/dist/umd/popper.min.js"></script>
<script src="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/js/bootstrap.min.js"></script>
<!-- Custom JavaScript -->
<script>
    // Array of Indian male names
    const indianMaleNames = ['Raj', 'Arun', 'Suresh', 'Manoj', 'Rakesh', 'Vikram', 'Rahul', 'Amit', 'Kiran'];

    // Array of Indian female names
    const indianFemaleNames = ['Priya', 'Neha', 'Pooja', 'Anita', 'Kavita', 'Divya', 'Anjali', 'Shweta', 'Sunita'];

    // Flag to track if the user can send a message
    let canSendMessage = false;

    // Function to generate a random Indian employee name
    function generateIndianEmployeeName() {
        const gender = Math.random() < 0.5 ? 'male' : 'female';
        const names = gender === 'male' ? indianMaleNames : indianFemaleNames;
        const randomIndex = Math.floor(Math.random() * names.length);
        return names[randomIndex];
    }

    function handleEmployeeResponse(response) {
        displayTypingAnimation(); // Show typing animation
        setTimeout(function() {
            document.getElementById('support-img').src = "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRdIdXtxpWsa_WmQn1iz94zBsJtmZVdVBOFcohHTu59Uw&s"; // Change the image to employee's image
            const employeeName = generateIndianEmployeeName();
            displayMessage('employee', response);
            if (response === "Your error has been noted. A fix will be provided soon. Thank you!") {
                // Show the full-screen popup modal
                $('#errorNotedModal').modal('show');
            }
        }, 3000); // Display the answer after 3 seconds
    }

    // Function to reset the chat process
    function resetChatProcess() {
        document.getElementById('issue-select').style.display = "block";
        document.getElementById('send-btn').style.display = "inline-block";
        document.getElementById('chat-input').remove();
        document.querySelector('.card-footer button').remove();
    }

    // Function to display messages in the chat container
    function displayMessage(sender, message) {
        const chatContainer = document.getElementById('chat-container');
        const messageElement = document.createElement('div');
        messageElement.classList.add('mb-2', 'px-3', 'py-2', 'rounded');
        if (sender === 'user') {
            messageElement.classList.add('bg-primary', 'text-white', 'float-left');
            messageElement.innerHTML = `
                <img src="https://t4.ftcdn.net/jpg/02/29/75/83/360_F_229758328_7x8jwCwjtBMmC6rgFzLFhZoEpLobB6L8.jpg" alt="" width="30" class="mr-2">
                ${message}
            `;
        } else if (sender === 'employee') {
            messageElement.classList.add('bg-secondary', 'text-white', 'float-right');
            messageElement.innerHTML = `
                <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRdIdXtxpWsa_WmQn1iz94zBsJtmZVdVBOFcohHTu59Uw&s" alt="Employee Logo" width="30" class="mr-2">
                ${message}
            `;
        }
        chatContainer.appendChild(messageElement);
    }

    // Function to display typing animation
    function displayTypingAnimation() {
        const chatContainer = document.getElementById('chat-container');
        const typingAnimation = document.createElement('div');
        typingAnimation.classList.add('mb-2', 'px-3', 'py-2', 'rounded');
        typingAnimation.innerHTML = `
            <img src="https://t3.ftcdn.net/jpg/05/06/55/22/360_F_506552238_j3Y4oq4rrlLEgzVG30AdEe0TaRINtUKr.jpg" alt="Typing Animation" width="30" class="mr-2">
            <div class="typing-animation bg-secondary text-white float-right"></div>
        `;
        chatContainer.appendChild(typingAnimation);
    }

    // Simulate checking for employee availability
    setTimeout(function() {
        document.getElementById('loader').classList.add('d-none');
        document.getElementById('green-mark').classList.remove('d-none');
        document.getElementById('send-btn').removeAttribute('disabled');
        canSendMessage = true; // Allow user to send messages
        displayMessage('employee', `Hello dear friend, my name is ${generateIndianEmployeeName()}. How can I help you?`);
    }, 3000);

    // Function to handle user's selection and display messages
    document.getElementById('send-btn').addEventListener('click', function() {
        if (canSendMessage) {
            const selectedIssue = document.getElementById('issue-select').value;
            if (selectedIssue !== "") {
                let response = "";
                if (selectedIssue === "backup") {
                    response = "Please use only digits 0-9 digits dont use alphabets. thanks for contact in employe!";
                } else if (selectedIssue === "password") {
                    response = "The minimum and maximum password length is 8 digits. Please create an 8-digit password! thanks for contact in employe!";
                } else if (selectedIssue === "mobile") {
                    response = "Please enter your 10-digit mobile number without using the country code. thanks for contact in employe!";
                } else if (selectedIssue === "download") {
                    response = "You have already downloaded the APK. thanks for contact in employe!";
                } else if (selectedIssue === "other") {
                    // Display the chat box for the user to type their error
                    document.getElementById('issue-select').style.display = "none";
                    document.getElementById('send-btn').style.display = "none";
                    const chatInput = document.createElement('textarea');
                    chatInput.id = "chat-input";
                    chatInput.classList.add('form-control', 'mt-3');
                    chatInput.placeholder = "Type your error...";
                    document.querySelector('.card-footer').appendChild(chatInput);
                    const sendChatBtn = document.createElement('button');
                    sendChatBtn.classList.add('btn', 'btn-primary', 'mt-3');
                    sendChatBtn.textContent = "Send";
                    document.querySelector('.card-footer').appendChild(sendChatBtn);
                    sendChatBtn.addEventListener('click', function() {
                        const userError = document.getElementById('chat-input').value;
                        if (userError.trim() !== "") {
                            displayMessage('user', userError);
                            // Store user's error in localStorage
                            let storedErrors = JSON.parse(localStorage.getItem('storedErrors')) || [];
                            storedErrors.push(userError);
                            localStorage.setItem('storedErrors', JSON.stringify(storedErrors));
                            handleEmployeeResponse("Your error has been noted. A fix will be provided soon. Thank you!");
                        }
                    });
                    return; // Exit the function early to prevent further execution
                } else {
                    response = "An error occurred. Please try again later.";
                }
                displayMessage('user', selectedIssue); // Display user's selected issue
                handleEmployeeResponse(response);
            }
        }
    });
</script>

<!-- Full-screen popup modal -->
<div class="modal" id="errorNotedModal" tabindex="-1" role="dialog" aria-labelledby="errorNotedModalLabel" aria-hidden="true">
    <div class="modal-dialog modal-dialog-centered" role="document">
        <div class="modal-content">
            <div class="modal-header">
                <h5 class="modal-title" id="errorNotedModalLabel">Error Noted</h5>
                <button type="button" class="close" data-dismiss="modal" aria-label="Close">
                    <span aria-hidden="true">&times;</span>
                </button>
            </div>
            <div class="modal-body">
                Your error has been noted. A fix will be provided soon. Thank you!
            </div>
            <div class="modal-footer">
                <button type="button" class="btn btn-primary" data-dismiss="modal">OK</button>
            </div>
        </div>
    </div>
</div>

