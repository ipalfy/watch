# `index.html` - AI Watch Face Gallery Main Page

This `index.html` file serves as the main entry point for the AI Watch Face Gallery. It showcases a dynamic, interactive analog watch face with various features, including a chronometer, dark/light mode, 12-hour/24-hour time display, and sun/moon phase indicators. It also provides a navigation menu to other AI-generated watch face demos within the `demos/` directory.

## Structure

The HTML document is structured as follows:

*   **`<!DOCTYPE html>` and `<html>`**: Standard HTML5 declaration and root element.
*   **`<head>`**:
    *   `meta` tags for character set and viewport.
    *   `<title>`: "Braun-Style Analog Watch".
    *   **External Scripts (CDNs)**:
        *   `suncalc.min.js`: For calculating sun and moon positions/phases.
        *   `tailwindcss.com`: Tailwind CSS framework for utility-first styling.
    *   **Google Fonts**: `Inter` font for typography.
    *   **Internal `<style>` block**: Contains custom CSS variables and styles for the watch components, including:
        *   Color variables for light and dark modes.
        *   Styling for the watch case, face, markers, hands, date display, chronometer, and buttons.
        *   Neumorphic-like shadows for the watch case.
*   **`<body>`**:
    *   `light-mode` class applied by default, with `flex` and `items-center justify-center min-h-screen` for centering content.
    *   **Navigation Menu**:
        *   A `div` containing a menu button (`#menu-button`) and a hidden menu (`#menu`).
        *   The menu lists links to various demo pages in the `demos/` directory (e.g., `grok-sunclock.html`, `chrono-demo.html`, `qwen-munich.html`).
    *   **Main Watch Container (`#watch`)**:
        *   A `div` with `watch` class, `rounded-full`, and flex properties for centering its content.
        *   **Watch Face (`.watch-face`)**:
            *   Absolute positioned, full-width/height, rounded-full div acting as the watch dial.
            *   **Sun/Moon Symbols (`#sun-moon-symbols`)**: A hidden container for dynamically added sun/moon phase icons.
            *   **Markers (`.markers-container`)**: Container for the hour and minute markers.
            *   **Numbers (`.numbers-container`)**: Container for the hour numbers.
            *   **Button Labels**: `div` elements with `button-label` class to provide text labels for the watch buttons (Start/Stop, Reset, Light/Dark, 12h/24h, Sun/Moon).
            *   **Hands**: `div` elements for `hour-hand`, `minute-hand`, and `second-hand`.
            *   **Center Pivot**: A small circle at the center of the watch face.
            *   **Date Display (`.date-display`)**: Shows the current day of the week, date, and year.
            *   **Digital Display (`.digital-display`)**: Shows the current time in digital format.
            *   **Chronometer (`.chrono-dial`)**:
                *   A smaller, rounded dial for the chronometer.
                *   Contains a `chrono-hand` and a `chrono-number` display.
            *   **Buttons**: `button` elements (`#start-stop-button`, `#reset-button`, `#mode-toggle`, `#time-mode-button`, `#sun-moon-toggle`) styled as watch buttons.
    *   **Internal `<script>` block**: Contains all the JavaScript logic for the watch face.

## Styling

The project uses a combination of Tailwind CSS and custom CSS:

*   **Tailwind CSS**: Included via CDN, providing utility classes for layout (flexbox), spacing, sizing, colors, and responsiveness.
*   **Custom CSS (`<style>` block)**:
    *   Defines CSS variables for colors, allowing easy theme switching between light and dark modes.
    *   Applies specific styles for watch components like hands, markers, and dials, including transitions for smooth animations.
    *   Implements neumorphic-like box shadows for the watch case, giving it a 3D, embossed appearance.
    *   Positions watch buttons and their labels using `transform` for rotation and translation to simulate a physical watch.

## Functionality (JavaScript)

The embedded JavaScript handles the core functionality of the watch:

*   **DOM Element Selection**: Selects various HTML elements for manipulation.
*   **State Variables**: Manages the state of the chronometer (`isChronoRunning`, `chronoSeconds`), time mode (`is24HourMode`), and sun/moon data visibility (`symbolsVisible`, `sunMoonData`).
*   **`createMarkers()`**: Dynamically generates minute and hour markers around the watch face based on `is24HourMode`.
*   **`createHourNumbers()`**: Dynamically generates and positions hour numbers (1-12 or 1-24) around the watch face. Includes animation for mode switching.
*   **`setDate()`**: Updates the rotation of the hour, minute, and second hands based on the current time. Also updates the date and digital time displays. This function is called every second using `setInterval`.
*   **Chronometer Logic (`handleStartStop()`, `handleReset()`, `formatSeconds()`)**:
    *   Manages starting, stopping, and resetting the chronometer.
    *   Calculates and displays elapsed time on the chronometer hand and digital display.
    *   Uses `localStorage` to persist chronometer state across sessions.
*   **Sun/Moon Data Integration**:
    *   `getLocation()`: Attempts to get the user's current geolocation to fetch accurate sun/moon data using `SunCalc.getTimes()`. Falls back to Munich's coordinates if geolocation fails or is denied.
    *   `createSunMoonSymbols()`: Dynamically adds sun (sunrise, sunset, solar noon) and moon phase symbols to the watch face when in 24-hour mode and symbols are visible.
    *   `updateWatchFaceGradient()`: Applies a `conic-gradient` background to the watch face to visually represent day and night based on sun data.
    *   `toggleSunMoonSymbols()`: Toggles the visibility of sun/moon symbols and manages the time mode switch if necessary.
*   **Mode Toggles**:
    *   `toggleMode()`: Switches between light and dark themes by toggling CSS classes on the `<body>` and updating button labels. Persists theme preference in `localStorage`.
    *   `toggleTimeMode()`: Switches between 12-hour and 24-hour time display, affecting hand rotation, marker generation, and number display. Persists time mode preference in `localStorage`.
*   **Persistence**: Uses `localStorage` to remember the last selected theme, time mode, and chronometer state.
*   **Event Listeners**: Attaches click event listeners to all interactive buttons to trigger their respective functions.
*   **Initialization**: Calls functions to load saved preferences, create initial markers and numbers, set the current time, and fetch geolocation data upon page load.

## External Dependencies

*   **SunCalc (CDN)**: A JavaScript library for calculating sun and moon positions and phases.
*   **Tailwind CSS (CDN)**: A utility-first CSS framework.
*   **Google Fonts (CDN)**: For the 'Inter' typeface.

## Purpose

`index.html` serves as a sophisticated demonstration of an AI-generated watch face, showcasing dynamic UI updates, interactive controls, and integration with external data (geolocation for sun/moon times). It also acts as a central hub to navigate to other individual watch face demos.