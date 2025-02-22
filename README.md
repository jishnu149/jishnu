# jishnu
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Simple Webpage Layout</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        body {
            font-family: Arial, sans-serif;
            background: url('C:/Users/Jishnu/Pictures/vit background.png') no-repeat center center fixed;
            background-size: cover;
            color: white;
        }
        .header {
            background: rgba(51, 51, 51, 0.8);
            color: white;
            text-align: center;
            padding: 1em;
            position: relative;
        }
        .nav {
            background: rgba(68, 68, 68, 0.8);
            padding: 0.5em;
            text-align: center;
        }
        .nav a {
            color: white;
            margin: 0 15px;
            text-decoration: none;
            cursor: pointer;
        }
        .container {
            display: flex;
            padding: 20px;
        }
        .sidebar {
            width: 25%;
            background: rgba(244, 244, 244, 0.8);
            padding: 15px;
            color: black;
        }
        .sidebar ul {
            list-style: none;
            padding: 0;
        }
        .sidebar ul li {
            padding: 10px;
            background: #ddd;
            margin: 5px 0;
            text-align: center;
            cursor: pointer;
        }
        .sidebar ul li:hover {
            background: #bbb;
        }
        .content {
            width: 75%;
            padding: 15px;
            background: rgba(0, 0, 0, 0.6);
        }
        .footer {
            background: rgba(51, 51, 51, 0.8);
            color: white;
            text-align: center;
            padding: 1em;
            position: absolute;
            bottom: 0;
            width: 100%;
        }
        .info-box {
            display: none;
            position: fixed;
            top: 50px;
            left: 50%;
            transform: translateX(-50%);
            background: rgba(0, 0, 0, 0.8);
            color: white;
            padding: 20px;
            border-radius: 5px;
        }
    </style>
</head>
<body>
    <div class="header">
        <h1>VIT EVENTS</h1>
    </div>
    <div class="nav">
        <a onclick="showInfo('home')">Home</a>
        <a onclick="showInfo('about')">About</a>
        <a onclick="showInfo('services')">Services</a>
        <a onclick="showInfo('contact')">Contact</a>
    </div>
    <div class="info-box" id="infoBox"></div>
    <div class="container">
        <div class="sidebar">
            <h2>Event Dashboard</h2>
            <input type="text" id="searchEvent" placeholder="Search Event..." onkeyup="searchEvent()">
            <ul id="eventList">
                <<li onclick="displayEventDetails('Vibrance')">Vibrance</li>
                <li onclick="displayEventDetails('Conference')">Conference</li>
                <li onclick="displayEventDetails('Workshop')">Workshop</li>
                <li onclick="displayEventDetails('Webinar')">Webinar</li>
            </ul>
        </div>
        <div class="content">
            <h2>Welcome to VIT College</h2>
            <p>Explore events and stay updated with the latest happenings.</p>
            <div id="eventDetails"></div>
        </div>
    </div>
    <div class="footer">
        <p>&copy; 2025 My Simple Webpage</p>
    </div>
    <script>
        function searchEvent() {
            let input = document.getElementById("searchEvent").value.toLowerCase();
            let items = document.querySelectorAll("#eventList li");
            items.forEach(item => {
                if (item.innerText.toLowerCase().includes(input)) {
                    item.style.display = "block";
                } else {
                    item.style.display = "none";
                }
            });
        }
        
        const infoData = {
            "home": "Welcome to our homepage! Here you can find the latest updates and news.",
            "about": "This is a platform dedicated to providing information about VIT College.",
            "services": "We offer various services including event management, student support, and more.",
            "contact": "Vandalur – Kelambakkam Road Chennai – 600 127;\n 044 3993 1555\nFax : 044 3993 2555 admin.chennai@vit.ac.in"
        };
        
        function showInfo(section) {
            document.getElementById("infoBox").innerHTML = infoData[section];
            document.getElementById("infoBox").style.display = "block";
            setTimeout(() => { document.getElementById("infoBox").style.display = "none"; }, 3000);
        }
        
        const eventDetailsData = {
            "Vibrance": "Date: February 26, 2025 to March 1, 2025<br>Time: 9:00 AM - 10:00 PM<br>Description: A festival of events and dj concert of famous celebrities. Don't miss the golden opportunity.",
            "Conference": "Date: March 15, 2025<br>Time: 10:00 AM - 12:50 PM<br>Description: A conference on emerging technologies.",
            "Workshop": "Date: April 5, 2025<br>Time: 2:00 PM - 6:00 PM<br>Description: Hands-on workshop on AI and Machine Learning.",
            "Webinar": "Date: May 10, 2025<br>Time: 5:00 PM - 7:00 PM<br>Description: An online webinar on cybersecurity trends."
        };
        
        function displayEventDetails(eventName) {
            document.getElementById("eventDetails").innerHTML = eventDetailsData[eventName] || "No details available.";
        }
    </script>
</body>
</html>
