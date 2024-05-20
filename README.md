## Overview

Overview
The PCChannel Chrome Extension is designed to fetch and display the latest feed entries from the PCChannel website. It leverages Google's Feed API to load and render the most recent 10 entries within the browser, providing a quick and simple way to stay updated with PCChannel's latest content.

##
## Features

Features
- **Feed Retrieval**: Fetches the latest 10 feed entries from PCChannel.
- **Easy Access**: Displays fetched entries in an easily accessible pop-up within the browser.
- **User-Friendly**: Simple and clean UI to quickly view the latest content.

##
## Installation Instructions

Installation Instructions
To install and set up the PCChannel Chrome Extension, follow these steps:

1. **Clone the Repository**:
```sh
git clone https://github.com/SurajAdsul/ChromeExtension.git
```

2. **Navigate to the Project Directory**:
```sh
cd ChromeExtension/chrome-extension
```

3. **Load the Extension in Chrome**:
    - Open Google Chrome and navigate to `chrome://extensions/`
    - Enable "Developer Mode" by clicking the toggle switch in the top-right corner.
    - Click on "Load unpacked" and select the directory where you cloned the repository (`chrome-extension`).

4. The PCChannel Chrome Extension is now installed and can be accessed from the Chrome toolbar.

##
## Usage Examples

Usage Examples
Once the extension is installed, you can use it as follows:

1. Click on the PCChannel icon in your Chrome toolbar.
2. The extension will display a popup with the latest 10 feed entries from PCChannel.
3. Click on any of the entries to be redirected to the full content on the PCChannel website.

##
## Code Summary

Code Summary
The main code for the Chrome Extension is located within the `pcchannel.js` file. Here's a brief overview of its structure:

File: `pcchannel.js`
```javascript
google.load("feeds", "1");

function initialize() {
  var feed = new google.feeds.Feed("http://www.pcchannel.in/feed/");
  feed.setNumEntries(10);
  var count = 1;
  feed.load(function(result) {
    if (!result.error) {
      var container = document.getElementById("feed");
      var html = "";
      for (var i = 0; i < result.feed.entries.length; i++) {
        var entry = result.feed.entries[i];
        html = "<h5>" + count++ + ". <a href='" + e
```
- **Feed Initialization**: The script uses Google's Feed API to load the feed from PCChannel.
- **Feed Loading**: The `feed.load` function handles the retrieval and display of feed entries within the extension's popup.

##
## License

License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more information.
```