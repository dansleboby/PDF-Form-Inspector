PDF Form Field Inspector
========================

A lightweight, browser-based tool designed to help developers and QA testers inspect the internal field names of PDF forms.

You can access it via: [https://dansleboby.github.io/PDF-Form-Inspector](https://dansleboby.github.io/PDF-Form-Inspector)

Features
--------

*   **Text Field Auto-fill**: Automatically detects `PDFTextField` elements and fills them with their internal variable names.
    
*   **Widget Labeling**: Visualizes non-text fields (Checkboxes, Radio Buttons) by drawing their field name in red directly over the element.
    
*   **Client-Side Processing**: Uses `pdf-lib` to process files entirely in the browser; no data is sent to a server.
    
*   **Instant Preview**: Renders the modified PDF immediately in an embedded iframe.
    

How to Use
----------

1.  Open `index.html` in a modern web browser.
    
2.  Click **Select PDF** and choose a PDF form file from your computer.
    
3.  The original file will appear in the preview window.
    
4.  Click **Process PDF**.
    
5.  The tool will generate a new version of the PDF where:
    
    *   Text boxes contain their own names.
        
    *   Checkboxes and other widgets have red labels next to them.
        
6.  A log on the left sidebar will list all detected fields and their types.
    

Dependencies
------------

*   [**pdf-lib**](https://pdf-lib.js.org/ "null"): Used for PDF modification and inspection.
    
*   [**Tailwind CSS**](https://tailwindcss.com/ "null"): Used for styling the user interface.
    
*   [**Fontkit**](https://github.com/foliojs/fontkit "null"): Used to support custom font embedding (required by pdf-lib).
    

Technical Note
--------------

The tool iterates through PDF Annotations to find `Widget` subtypes to label non-text fields. This is necessary because some PDF forms separate the logical "Field" definition from the visual "Widget" representation on the page.