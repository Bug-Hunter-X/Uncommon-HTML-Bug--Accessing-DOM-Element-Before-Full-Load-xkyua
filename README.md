# Uncommon HTML Bug: Premature DOM Access

This repository demonstrates an uncommon bug in HTML related to accessing a DOM element's property before the element is fully loaded into the DOM.  This can lead to unexpected errors or inconsistent behavior across browsers.

## Bug Description

The bug occurs when JavaScript code attempts to access a DOM element's property (like `setAttribute`) before the browser has fully parsed and rendered that element in the page. This often happens when the script is placed in the `<head>` or early in the `<body>` before the element is created.

## Solution

The solution is to ensure the script that interacts with the DOM element runs *after* the element exists. This can be achieved by placing the script at the end of the `<body>`, using a `DOMContentLoaded` event listener, or by wrapping the script within a function that checks for element existence before continuing.