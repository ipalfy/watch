# Gemini Watch Demos

This project contains a collection of HTML demos for various watch faces and calculators.

## Demos

The `html-demos` directory contains the following demos:

*   `gemini-clock-manual.html`: A manually animated clock.
*   `grok-calculator.html`: A calculator.
*   `grok-clock.html`: A clock.
*   `qwen-munich.html`: A Munich-themed watch face.
*   `qwen-watch.html`: A watch face.

## `index.html`: Braun-Style Analog Watch

The `index.html` file is a sophisticated, interactive analog watch face inspired by Braun design principles. It is a single HTML file that uses Tailwind CSS and vanilla JavaScript to create a feature-rich timekeeping experience.

### Features

*   **Analog Clock:** A classic analog display with hour, minute, and second hands.
*   **Light and Dark Modes:** The watch supports both light and dark themes, which can be toggled using a dedicated button. The theme preference is saved in the browser's local storage.
*   **Chronograph:** A functional chronograph with a sub-dial that can be started, stopped, and reset using the side buttons.
*   **Date and Digital Time:** The watch face includes a display for the full date (day of the week, day, month, and year) and a separate digital display for the current time in `HH:MM:SS` format.
*   **Dynamic Markers and Numbers:** The hour and minute markers, as well as the hour numbers, are dynamically generated with JavaScript, ensuring a crisp and precise layout.
*   **Interactive Buttons:** The watch features three interactive buttons on the side of the case for controlling the chronograph and toggling the theme.

### Technical Details

*   **Styling:** The watch is styled using a combination of Tailwind CSS for the layout and custom CSS variables for theming and fine-grained control over the appearance.
*   **JavaScript:** The clock's logic is implemented in vanilla JavaScript, with functions for updating the time, handling user interactions, and dynamically creating parts of the watch face.

## Usage

To view the demos, open the HTML files in your web browser.