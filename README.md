# Quick Map Search

Quick Map Search is a Python script that allows users to quickly search for a location on Google Maps. It takes input either from command-line arguments or from the clipboard and opens the corresponding Google Maps search page in the default web browser.

## How the Code Works

This script is designed to efficiently search for addresses on Google Maps with minimal user effort. Below is a breakdown of how it works:

### 1. Importing Required Modules
```python
import webbrowser, sys, pyperclip
```
- `webbrowser`: This module provides a high-level interface to allow displaying web-based documents in the default browser.
- `sys`: Used to handle command-line arguments.
- `pyperclip`: Enables clipboard operations, allowing the script to fetch copied text.

### 2. Handling User Input
```python
if len(sys.argv) > 1:
    address = " ".join(sys.argv[1:])
else:
    address = pyperclip.paste()
```
- The script first checks if there are command-line arguments (`sys.argv`).
- If arguments are present, it joins them to form a single address string.
- If no arguments are provided, the script retrieves the last copied text from the clipboard using `pyperclip.paste()`.

### 3. Opening Google Maps
```python
webbrowser.open(f"https://www.google.com/maps/search/{address}")
```
- The script constructs a Google Maps search URL using the extracted address.
- The `webbrowser.open()` function opens this URL in the default web browser, displaying the search results instantly.

## Summary
This script simplifies the process of searching for locations on Google Maps. Users can either:
- Provide an address via command-line arguments.
- Copy an address to the clipboard and run the script without any arguments.

The combination of command-line input and clipboard functionality ensures that users can search addresses with minimal effort, making **Quick Map Search** an efficient tool for quick navigation lookups.

