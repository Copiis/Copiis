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
