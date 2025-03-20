<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>CSS Animations and Local Storage</title>
  <style>
    /* Basic styles */
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      padding: 50px;
    }

    /* CSS Animation */
    .animate-btn {
      padding: 15px 30px;
      font-size: 16px;
      background-color: #3498db;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      transition: transform 0.3s ease, background-color 0.3s ease;
    }

    .animate-btn:active {
      transform: scale(1.1);
      background-color: #2980b9;
    }

    /* Custom theme styles */
    .dark-theme {
      background-color: #2c3e50;
      color: white;
    }

    .light-theme {
      background-color: #ecf0f1;
      color: black;
    }
  </style>
</head>
<body>

  <h1>Welcome to CSS Animations and LocalStorage</h1>

  <!-- Animation-triggering button -->
  <button id="animateBtn" class="animate-btn">Click Me!</button>

  <!-- Theme Toggle -->
  <br><br>
  <button id="toggleThemeBtn" class="animate-btn">Toggle Theme</button>

  <script>
    // Get references to elements
    const animateBtn = document.getElementById('animateBtn');
    const toggleThemeBtn = document.getElementById('toggleThemeBtn');

    // Check if there's a theme saved in localStorage
    if (localStorage.getItem('theme') === 'dark') {
      document.body.classList.add('dark-theme');
    } else {
      document.body.classList.add('light-theme');
    }

    // Toggle between light and dark theme
    toggleThemeBtn.addEventListener('click', function() {
      const currentTheme = document.body.classList.contains('dark-theme') ? 'dark' : 'light';
      
      if (currentTheme === 'dark') {
        document.body.classList.remove('dark-theme');
        document.body.classList.add('light-theme');
        localStorage.setItem('theme', 'light');
      } else {
        document.body.classList.remove('light-theme');
        document.body.classList.add('dark-theme');
        localStorage.setItem('theme', 'dark');
      }
    });

    // CSS Animation Trigger (for button)
    animateBtn.addEventListener('click', function() {
      // Trigger animation (button will scale and change color)
      animateBtn.classList.add('animate-btn');
    });

  </script>
</body>
</html>
