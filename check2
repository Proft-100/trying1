<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Data Collection Form</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            max-width: 600px;
            margin: 0 auto;
            padding: 20px;
        }
        .form-group {
            margin-bottom: 15px;
        }
        label {
            display: block;
            margin-bottom: 5px;
            font-weight: bold;
        }
        input, textarea, select {
            width: 100%;
            padding: 8px;
            border: 1px solid #ddd;
            border-radius: 4px;
            box-sizing: border-box;
        }
        button {
            background-color: #4CAF50;
            color: white;
            padding: 10px 15px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-size: 16px;
        }
        button:hover {
            background-color: #45a049;
        }
        #success-message {
            display: none;
            color: green;
            margin-top: 10px;
        }
    </style>
</head>
<body>
    <h1>Data Collection Form</h1>
    <form id="dataForm">
        <div class="form-group">
            <label for="name">Full Name:</label>
            <input type="text" id="name" name="name" required>
        </div>
        
        <div class="form-group">
            <label for="email">Email:</label>
            <input type="email" id="email" name="email" required>
        </div>
        
        <div class="form-group">
            <label for="phone">Phone Number:</label>
            <input type="tel" id="phone" name="phone">
        </div>
        
        <div class="form-group">
            <label for="message">Message:</label>
            <textarea id="message" name="message" rows="4"></textarea>
        </div>
        
        <button type="submit">Submit</button>
    </form>
    
    <div id="success-message">
        Thank you! Your data has been submitted successfully.
    </div>

    <script>
        document.getElementById('dataForm').addEventListener('submit', function(e) {
            e.preventDefault();
            
            // Get form data
            const formData = {
                name: document.getElementById('name').value,
                email: document.getElementById('email').value,
                phone: document.getElementById('phone').value,
                message: document.getElementById('message').value,
                timestamp: new Date().toISOString(),
                userAgent: navigator.userAgent
            };
            
            // Send data to Google Apps Script
            fetch('https://script.google.com/macros/s/AKfycbyOm_J02ufoyeABsEo7Scu_xhLyy5mmZjHSApepBqrcBSR0oOC7xj1xKwqSQHXMqX91-g/exec', {
                method: 'POST',
                mode: 'no-cors',
                headers: {
                    'Content-Type': 'application/json',
                },
                body: JSON.stringify(formData)
            })
            .then(() => {
                // Show success message
                document.getElementById('success-message').style.display = 'block';
                document.getElementById('dataForm').reset();
                
                // Hide message after 5 seconds
                setTimeout(() => {
                    document.getElementById('success-message').style.display = 'none';
                }, 5000);
            })
            .catch(error => {
                console.error('Error:', error);
                alert('There was an error submitting the form. Please try again.');
            });
        });
    </script>
</body>
</html>
