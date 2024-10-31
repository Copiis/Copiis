# Image Text Reader

## Description

The **Image Text Reader** is a Tampermonkey userscript that allows users to extract text from images on any webpage. By clicking on an image, the script utilizes Optical Character Recognition (OCR) to recognize the text and automatically copies it to the clipboard for easy pasting.

## Features

- Extracts text from images using Tesseract.js
- Automatically copies the recognized text to the clipboard
- Easy to install and use with Tampermonkey

## Installation

1. Install the [Tampermonkey](https://www.tampermonkey.net/) extension for your web browser.
2. Create a new userscript in Tampermonkey.
3. Copy and paste the following code into the new script:

```javascript
// ==UserScript==
// @name         Image Text Reader
// @namespace    http://tampermonkey.net/
// @version      0.2
// @description  Liest Text aus Bildern
// @match        *://*/*
// @require      https://cdn.jsdelivr.net/npm/tesseract.js@4.0.2/dist/tesseract.min.js
// @grant        none
// ==/UserScript==

(function() {
    'use strict';

    // Funktion, um Text aus einem Bild zu extrahieren
    async function readTextFromImage(imgElement) {
        const { data: { text } } = await Tesseract.recognize(imgElement.src, 'deu'); // 'deu' für deutschen Text
        console.log(text);  // Ausgabe des erkannten Textes in der Konsole
        navigator.clipboard.writeText(text); // Kopiert den Text in die Zwischenablage
    }

    // Bilder auf der Seite durchlaufen und OCR ausführen
    document.querySelectorAll('img').forEach(img => {
        img.addEventListener('click', () => readTextFromImage(img));  // Klick auf Bild startet Texterkennung
    });
})();
