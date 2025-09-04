# Project: AI Watch Face Gallery

## Directory Overview

This directory contains a collection of AI-generated watch face demos. The project is a static website built with HTML and styled with Tailwind CSS. The main page (`index.html`) serves as a gallery for the different watch face implementations available in the `demos/` directory.

The project seems to be organized for showcasing and experimenting with different AI-generated designs, with prompts stored in the `prompts/` directory.

## Key Files

*   `index.html`: The main gallery page that links to all the watch face demos.
*   `demos/`: This directory contains the individual HTML files for each watch face demo. Each file is self-contained.
*   `prompts/`: This directory holds the prompts that were likely used to generate the watch face designs with an AI model.
*   `tailwind.config.js`: The configuration file for Tailwind CSS.
*   `_config.yml`: A configuration file, likely for Jekyll, though the project appears to be a simple static site.

## Building and Running

This is a static website with no build process. The `index.html` file uses the Tailwind CSS CDN, so you can open it directly in a web browser to view the gallery.

To view a specific demo, you can open the corresponding HTML file from the `demos/` directory in your browser.

## Development Conventions

*   **Styling:** The project uses Tailwind CSS for styling, with utility classes directly in the HTML.
*   **Structure:** Each watch face demo is a standalone HTML file in the `demos/` directory.
*   **Prompts:** The prompts used for generation are stored as Markdown files in the `prompts/` directory, which is a good practice for reproducibility.
