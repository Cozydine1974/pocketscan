# PocketScan — Version 1 trial

A small, privacy-first document-scanning web app, designed for iPhone 13 Pro Max.

## Features

- Capture a photo with your phone camera, or import images from Photos.
- Adjust four crop corners; try the experimental edge suggestion.
- Straighten perspective, rotate and apply colour, greyscale or high-contrast B&W.
- Combine pages into an A4 PDF or export individual JPG pages.
- Save page data locally in Safari using IndexedDB. No cloud storage, login, tracking, advertising, external scripts or remote document processing.
- Optional Home Screen installation and offline asset caching after first visit over HTTPS.

## Run locally on a computer

Extract the files, open a terminal in this folder, and run `python -m http.server 8000` (or another static HTTP server). Visit `http://localhost:8000` in a desktop browser.

## Use it on your iPhone

An iPhone needs an **HTTPS web address** to use and install this PWA reliably. Upload the extracted project files to a static HTTPS host you control. A simple option is GitHub Pages: create a repository, upload the app files to its root, enable Pages using the main branch, then open the resulting HTTPS link in iPhone Safari. Select **Share → Add to Home Screen**. Repository source may be public when using free GitHub Pages; do not include private scans in the repository. No scanned images are transmitted to that host by the app.

This package is **source code, not a live hosted app**. Installation on the iPhone is not completed until it is hosted.

## Privacy and limits

The app makes no explicit server requests to send scans. Its HTML, CSS, JavaScript and icons are static; photos and PDFs are processed in your browser. The hosting provider can still see ordinary requests for the app files and basic connection metadata; they should not receive scanned document contents. Safari's private browsing, storage cleaning, limited free space or uninstalling may erase locally stored pages. Export important PDFs to Files and back them up yourself.

Edge detection is a rough suggestion, not Adobe Scan-class detection. Drag the four corners for an accurate crop. PDF export uses A4 pages with one JPEG image per PDF page and **does not include OCR or searchable text**. JPG images may use compression. Browser and iOS behaviour, especially the camera and downloads, need real-device testing.

## Testing checklist

1. Open app on iPhone in Safari, choose Scan with camera and take an A4 document photo.
2. Drag the corners to the page edges. Check that perspective correction looks right.
3. Add a page, scan another and check both appear in the correct order.
4. Save as PDF, open in Files and confirm both pages display correctly.
5. Open a saved page and export JPG.
6. Close and reopen app, check that scanned pages remain in local storage.
7. Turn on Airplane Mode after the first successful HTTPS load and test Home Screen app offline.
8. Delete pages and confirm they disappear.

Do not rely on PocketScan for irreplaceable documents until all these tests pass.
