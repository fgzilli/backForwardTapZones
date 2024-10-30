# backForwardTapZones

This project provides a custom video player plugin for Brightcove players that adds interactive tap zones on the video player's left, middle, and right areas. The left and right zones allow users to skip backward or forward, while the middle zone pauses or resumes playback.

Table of Contents
Installation
Usage
Customization
License
Installation
Clone the Repository or download the two main files:

video-player-styles.css (for styling the tap zones)
video-player-plugin.js (for tap zone functionality)
Include the CSS and JavaScript files in your HTML file where the Brightcove player is embedded.

Ensure your HTML structure matches the code below for the video player and tap zones.

Usage
Step 1: HTML Setup
Create a container for your Brightcove player and add three div elements for the left, middle, and right tap zones. Link to the CSS and JavaScript files as shown:

html
Copy code
<div style="max-width: 960px; position: relative;">
    <!-- Link to external CSS file -->
    <link rel="stylesheet" href="video-player-styles.css">

    <!-- Brightcove Video Player Embed -->
    <video-js
      id="myBrightcovePlayer"
      data-account="6415621439001"
      data-player="kHD3bM2Xr"
      data-embed="default"
      controls=""
      playsinline
      data-video-id="6361900776112"
      class="vjs-fluid">
    </video-js>

    <!-- Left, Middle, and Right Tap Zones -->
    <div class="tap-zone left-tap">
        <div class="arrow arrow-left"></div>
    </div>
    <div class="tap-zone middle-tap"></div>
    <div class="tap-zone right-tap">
        <div class="arrow arrow-right"></div>
    </div>
</div>

<!-- Link to Brightcove and custom JavaScript files -->
<script src="https://players.brightcove.net/6415621439001/kHD3bM2Xr_default/index.min.js"></script>
<script src="video-player-plugin.js"></script>
Step 2: Initialize the Plugin
The video-player-plugin.js JavaScript file automatically initializes the plugin when the player is ready.

Step 3: Customization
The plugin's default jumpAmount is set to 15 seconds, meaning each tap will skip forward or back by 15 seconds. To adjust this:

Open video-player-plugin.js.
Update the jumpAmount value on the registerPlugin call, like this:
javascript
Copy code
videojs.registerPlugin('backForwardTapZones', function(jumpAmount = 20) {
    // The rest of the code...
});
This example changes the jump amount to 20 seconds.

License
This project is open-source and can be used or modified freely.


