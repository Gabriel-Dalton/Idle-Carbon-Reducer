# Idle Carbon Reducer (ICR)

**Idle Carbon Reducer (ICR)** is a lightweight JavaScript solution designed to reduce carbon emissions by detecting user inactivity (AFK) on a webpage and redirecting the user to a minimal-resource page. This reduces server load, bandwidth, and energy consumption, all while keeping the script footprint tiny.

### Features
- **Tiny footprint**: Extremely small, inlineable if desired.
- **Customizable Idle Time**: Easily customize the idle time after which the user will be redirected.
- **Customizable Redirect URL**: Define the page where idle users will be sent (e.g., a low-resource, carbon-neutral page).
- **Seamless Integration**: Simply add a `<script>` tag to any webpage to activate it.
- **Energy-Efficient**: Helps reduce energy consumption and CO₂ emissions by redirecting idle users to a minimal-impact page.
 - **Loop protection**: Avoids redirect loops when already on the eco page.
 - **Visibility-aware**: Pauses the timer while the tab is hidden to reduce unnecessary redirects.
 - **Passive listeners**: Uses passive event listeners where supported for better performance.

---

## How It Works

The **Idle Carbon Reducer (ICR)** monitors user activity such as mouse movements, keyboard inputs, and scrolling. If no activity is detected within the specified idle time (default is 5 minutes), the user will automatically be redirected to a low-carbon page (default: `low-co2-page.html`).

### Why It's Important

Every second a user spends idle on a page unnecessarily consumes server resources and bandwidth. By redirecting users to a lightweight, minimal page when they're inactive, you can reduce the amount of energy consumed by both the server and the user's device, leading to lower CO₂ emissions.

---

## How to Use

1. **Add the Script to Your Webpage:**

   Include the script (ideally late in `<head>` or right before `</body>`):

   ```html
   <script src="/idlescript.js" data-idle-time="300000" data-redirect-url="/low-co2-page.html"></script>
   ```

   - The `data-idle-time` attribute defines how long the user can be idle before redirection (in milliseconds).
   - The `data-redirect-url` attribute defines the page where users will be sent when idle (e.g., a low-resource page).

2. **Host a Minimal CO₂ Page**:

   Create a page that uses minimal server resources and bandwidth (e.g., `low-co2-page.html`):

   ```html
   <!DOCTYPE html>
   <html lang="en">
   <head>
     <meta charset="UTF-8">
     <meta name="viewport" content="width=device-width, initial-scale=1">
     <meta name="color-scheme" content="light dark">
     <title>Eco Mode Activated</title>
     <style>body{margin:0;display:grid;place-items:center;min-height:100dvh;background:Canvas;color:CanvasText;font-family:system-ui,Arial}</style>
     <script>document.head.appendChild(Object.assign(document.createElement('script'),{src:'/idlescript.js'})).setAttribute('data-exempt','');</script>
   </head>
   <body>
     <main style="text-align:center;padding:2rem;max-width:40rem">
       <h1>Eco mode is on 🌿</h1>
       <p>You're idle, so we paused heavy content to save energy.</p>
       <p><a href="javascript:history.back()">Go back</a></p>
     </main>
   </body>
   </html>
   ```

---

## Customization

You can customize the behavior of the **Idle Carbon Reducer** by changing the following attributes in the script tag:

1. **Idle Time** (`data-idle-time`):
   - Specifies how long the user must be inactive before being redirected.
   - Value is in milliseconds.
   - Example: To set a 10-second idle time:
     ```html
     <script src="/idlescript.js" data-idle-time="10000"></script>
     ```

2. **Redirect URL** (`data-redirect-url`):
   - Specifies the URL where the user will be redirected after being idle.
   - Example: To redirect to a custom page:
     ```html
     <script src="/idlescript.js" data-redirect-url="/custom-idle-page.html"></script>
     ```

3. **Exempt Current Page** (`data-exempt`):
   - Prevents the script from redirecting on the page where the attribute is present.
   - Useful for the eco page itself.
   - Example:
     ```html
     <script src="/idlescript.js" data-exempt></script>
     ```

---

## Benefits

- **Low Impact on Performance**: Adds virtually no overhead to your website.
- **Easy to Implement**: No complex setup required — just include a single line of JavaScript in your page.
- **Eco-Friendly**: Contributes to reducing energy consumption and CO₂ emissions from idle users.
- **Customizable**: Both the idle time and the redirect page can be easily customized without editing the JavaScript code.

---

## License

This project is licensed under the MIT License.

---

By implementing **Idle Carbon Reducer**, you are helping make the web a little more sustainable, one idle user at a time.
