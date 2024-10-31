# Image Text Reader to Clipboard

A Tampermonkey user script that extracts text from images on web pages using Optical Character Recognition (OCR) and copies it to the clipboard. The text extraction is triggered by a right-click on the image.

## Features

- Uses [Tesseract.js](https://github.com/naptha/tesseract.js) for OCR to recognize text in images.
- Copies the recognized text directly to the clipboard.
- Simple right-click context menu activation.

## Installation

1. **Install Tampermonkey**: If you haven't already, install the Tampermonkey extension for your browser:
   - [Chrome](https://chrome.google.com/webstore/detail/tampermonkey/dhdgffkkebhmanafdgjjjfdkmohmdcjp)
   - [Firefox](https://addons.mozilla.org/en-US/firefox/addon/tampermonkey/)
   - [Microsoft Edge](https://microsoftedge.microsoft.com/addons/detail/tampermonkey/ffhgeephbihgjgmkdckdibgfcgdnokbb)
   - [Safari](https://apps.apple.com/us/app/tampermonkey/id1482490089)

2. **Add the Script**:
   - Open the Tampermonkey dashboard.
   - Click on the "Add a new script" button.
   - Replace the default template with the script provided below.
   - Save the script.

## Usage

1. Navigate to a web page containing images.
2. Right-click on any image.
3. The script will extract the text from the image and copy it to your clipboard.
4. You will receive an alert with the recognized text.

## Script

```javascript
// ==UserScript==
// @name         Image Text Reader to Clipboard
// @namespace    http://tampermonkey.net/
// @version      0.3
// @description  Reads text from images and copies it to the clipboard on right-click
// @author       Copiis
// @match        *://*/*
// @require      https://cdn.jsdelivr.net/npm/tesseract.js@4.0.2/dist/tesseract.min.js
// @grant        none
// ==/UserScript==

(function() {
    'use strict';

    // Function to extract text from an image and copy it to the clipboard
    async function readTextAndCopyToClipboard(imgElement) {
        const { data: { text } } = await Tesseract.recognize(imgElement.src, 'eng'); // Use 'eng' for English text
        console.log("Recognized text:", text);

        // Copy text to the clipboard
        navigator.clipboard.writeText(text).then(() => {
            alert("Text copied to clipboard: " + text);
        }).catch(err => {
            console.error("Error copying to clipboard:", err);
        });
    }

    // Loop through images on the page and set up context menu event
    document.querySelectorAll('img').forEach(img => {
        img.addEventListener('contextmenu', (event) => {
            event.preventDefault(); // Prevent the default context menu
            readTextAndCopyToClipboard(img);  // Right-click on image triggers text recognition
        });
    });
})();
