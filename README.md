# Idle Carbon Reducer (ICR)

A lightweight JavaScript solution (just 5KB) that helps websites reduce their carbon footprint by detecting user inactivity and redirecting idle users to a minimal CO₂ page. This project was conceived by Gabriel Dalton to promote sustainability in web design by reducing the energy used when users leave browser tabs open for extended periods.

## Features
- **Idle Detection**: Detects when the user has been idle (AFK) for a specified amount of time.
- **Automatic Redirection**: Redirects the user to a low-CO₂ webpage that uses minimal resources, reducing server load and CO₂ emissions.
- **Lightweight**: The script is only 5KB, ensuring minimal impact on website performance.
- **Customizable**: Easily set the idle time duration and the destination URL for the redirection.

## How It Works

The **Idle Carbon Reducer** monitors user activity such as mouse movement, keyboard input, and scrolling. If the user is inactive for a set period (e.g., 5 minutes), the script automatically redirects them to a low-resource webpage, thereby reducing unnecessary energy consumption.

### Idle Detection JavaScript Code
```javascript
(function() {
  // Idle time in milliseconds (e.g., 5 minutes)
  var idleTime = 5 * 60 * 1000; 
  var idleTimer;

  // URL of the low-CO₂ page
  var redirectURL = 'low-co2-page.html';

  // Reset the idle timer on user interaction
  function resetTimer() {
    clearTimeout(idleTimer);
    idleTimer = setTimeout(goIdle, idleTime);
  }

  // Redirect to the low-CO₂ page
  function goIdle() {
    window.location.href = redirectURL;
  }

  // Events to detect user activity
  ['mousemove', 'keydown', 'mousedown', 'touchstart', 'scroll'].forEach(function(evt) {
    document.addEventListener(evt, resetTimer, false);
  });

  // Start the timer when the page loads
  resetTimer();
})();
