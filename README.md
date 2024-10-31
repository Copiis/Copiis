# Image Text Reader to Clipboard

## Description
This userscript allows you to extract text from images on any webpage by clicking on the image. The extracted text is translated into German and copied to the clipboard for easy access. It uses Tesseract.js for Optical Character Recognition (OCR) and Google Translate for translation.

## Features
- Click on any image to read the text.
- Automatically cleans the extracted text for better accuracy.
- Copies the translated text directly to your clipboard.
- Easy integration with Tampermonkey for enhanced web browsing experience.

## Installation
1. Install [Tampermonkey](https://www.tampermonkey.net/) if you haven't already.
2. Click on the Tampermonkey icon in your browser and select "Create a new script."
3. Replace the default script with the content of this script.
4. Save the script.

## Usage
- Navigate to any webpage with images.
- Click on an image containing text.
- Wait for the script to recognize the text, translate it to German, and copy it to your clipboard.
- A confirmation alert will display the translated text.

## Requirements
- Tampermonkey installed in your browser.
- Internet access for Tesseract.js and Google Translate.

## Dependencies
- [Tesseract.js](https://github.com/naptha/tesseract.js): JavaScript library for OCR.
- Google Translate for translation services.

## Notes
- The script assumes the original text in the image is in English.
- If no text is recognized or if the translation fails, an alert will inform you of the issue.
- Ensure that the images clicked contain clear and readable text for better results.

## Author
- **Copiis**

## License
This script is released under the MIT License. Feel free to use and modify it as needed.
