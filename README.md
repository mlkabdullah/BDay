<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Birthday Invitation</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts - Inter -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #f3e8ff; /* Light purple background */
        }
        .card-container {
            background: linear-gradient(135deg, #f0abfc 0%, #a78bfa 100%); /* Purple gradient */
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.2);
        }
        .btn {
            background-color: #3b82f6; /* Blue button */
            transition: transform 0.2s ease-in-out;
        }
        .btn:hover {
            transform: scale(1.05);
            background-color: #2563eb;
        }
        /* Custom modal for messages */
        .modal {
            display: none;
            position: fixed;
            z-index: 1000;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            overflow: auto;
            background-color: rgba(0,0,0,0.6);
            backdrop-filter: blur(5px);
            -webkit-backdrop-filter: blur(5px);
        }
        .modal-content {
            background-color: #fefefe;
            margin: 15% auto;
            padding: 30px;
            border-radius: 12px;
            width: 80%;
            max-width: 400px;
            text-align: center;
            box-shadow: 0 5px 15px rgba(0,0,0,0.3);
        }
        .close-btn {
            color: #aaa;
            float: right;
            font-size: 28px;
            font-weight: bold;
        }
        .close-btn:hover,
        .close-btn:focus {
            color: black;
            text-decoration: none;
            cursor: pointer;
        }
    </style>
</head>
<body class="flex items-center justify-center min-h-screen p-4">

    <!-- Invitation Card -->
    <div class="card-container text-white p-8 md:p-12 rounded-2xl w-full max-w-sm text-center">
        <h1 class="text-4xl font-bold mb-2">You're Invited!</h1>
        <p class="text-lg mb-6">Join us to celebrate</p>

        <!-- Dynamic Content Section -->
        <div id="content" class="space-y-4">
            <!-- Event Title -->
            <h2 class="text-3xl font-semibold mb-2">Abdullah's Birthday</h2>

            <!-- Event Details -->
            <div class="flex items-center justify-center space-x-3 text-lg">
                <span class="text-2xl">📅</span>
                <p>Date: September 14th</p>
            </div>
            <div class="flex items-center justify-center space-x-3 text-lg">
                <span class="text-2xl">🕔</span>
                <p>Time: 6:00 PM</p>
            </div>
            <div class="flex items-center justify-center space-x-3 text-lg">
                <span class="text-2xl">📍</span>
                <p>Location: Your Place</p>
            </div>
            <div class="text-center mt-6">
                <p class="text-xl font-medium">For a special Hi-Tea gathering!</p>
            </div>
        </div>

        <!-- Call to Action Button -->
        <button id="rsvp-btn" class="btn w-full mt-8 py-3 rounded-full font-bold text-white text-lg shadow-lg">
            RSVP
        </button>

        <p class="text-sm mt-4 opacity-80">We can't wait to see you!</p>
    </div>

    <!-- RSVP Modal -->
    <div id="rsvp-modal" class="modal">
      <div class="modal-content">
        <span class="close-btn">&times;</span>
        <h2 class="text-2xl font-bold mb-4 text-gray-800">Thank you!</h2>
        <p class="text-gray-600">Your RSVP has been noted. We look forward to celebrating with you!</p>
      </div>
    </div>

    <script>
        // Get the modal and the button
        const modal = document.getElementById('rsvp-modal');
        const btn = document.getElementById('rsvp-btn');
        const closeBtn = document.querySelector('.close-btn');

        // Function to show the modal
        function showModal() {
            modal.style.display = 'block';
        }

        // Function to hide the modal
        function hideModal() {
            modal.style.display = 'none';
        }

        // When the user clicks the button, open the modal
        btn.onclick = function() {
            showModal();
        }

        // When the user clicks on <span> (x), close the modal
        closeBtn.onclick = function() {
            hideModal();
        }

        // When the user clicks anywhere outside of the modal, close it
        window.onclick = function(event) {
            if (event.target == modal) {
                hideModal();
            }
        }
    </script>
</body>
</html>

