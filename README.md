🪐 Astro-Verse WEB UI (v009)
~ https://the-astro-bruh.github.io/astroverse_WebUI ~
A feature-rich, single-file web interface for advanced image generation and editing, powered by the Google Gemini API.

Created with 💙 by theAstroBruh

🚀 Overview

Astro-Verse is a powerful, self-contained web application that provides a sophisticated user interface for interacting with Google's generative AI models. It allows users to generate new images from text prompts, perform complex image edits using reference images, and manage a library of their favorite prompts.

This entire application runs from a single index.html file, leveraging vanilla JavaScript, Tailwind CSS, and direct API calls to gemini-2.5-flash-image-preview and gemini-2.5-flash-preview-09-2025.

✨ Features

Three Core Modes:

Prompt Mode: Generate images directly from text.

Edit Mode: Use reference images to perform targeted edits.

PNG Info Mode: Read embedded prompts from existing generated images.

Advanced Prompt Tools:

Prompt Enchanter: Uses AI (gemini-2.5-flash) to automatically expand and detail your simple prompts.

Prompt Album: Save your favorite prompts and load pre-made prompt collections from a local .json file or a URL.

Prompt History: Automatically saves your recent prompts for easy reuse.

Image Editing Suite (Edit Mode):

Perspective Changer: Alter the camera angle of a subject (e.g., "Bird's-eye View", "Low Angle View").

Hairstyle Changer: Modify a subject's hairstyle and color.

Background Changer: Replace the background with a new scene, solid color, or custom description.

Reference Image Slots: Upload up to three images to guide the AI in "Edit Mode" or as inspiration in "Prompt Mode".

Embedded Metadata: All generated images are automatically saved with the prompt embedded in the PNG's metadata (tEXt chunk).

Interactive Image Viewer:

Click any generated image to open a full-screen magnify modal.

Supports pan (click/drag or touch), zoom (scroll, pinch, or double-tap), and an "immersive" UI-hiding mode.

Modern UI/UX:

Sleek, responsive dark theme with blur and transparency effects.

Generation cooldown (8 seconds) to prevent API spam, visualized with a button-integrated cooldown bar.

Loading spinners and particle animations during generation.

Clear modal popups for errors, successes, and prompts.

🛠️ Modes of Operation

1. Prompt Mode

This is the default mode for text-to-image generation.

Type your desired prompt in the Prompt Box.

(Optional) Use the ✨ Enchant button to improve your prompt.

(Optional) Upload reference images to influence the style or subject.

Click Generate.

2. Edit Mode

This mode requires at least one reference image to perform edits.

Upload an image to one of the Reference slots.

Switch to Edit Mode.

Select an edit type: Perspective, Hairstyle, or Background.

Choose the desired options (e.g., select "Rear View" or type "long wavy hair").

Click Generate to apply the edit to your reference image.

3. PNG Info Mode

Use this to discover the prompt used to create an existing AI-generated image.

Switch to PNG Info Mode.

Drag and drop or click to upload a PNG file.

The app will read the file's metadata and display the embedded prompt (if one exists).

You can then click "Use Image & Prompt" to load both directly into Prompt Mode.

⚙️ Setup & Installation

This app is designed to be run directly from the index.html file.

Download: Get the index.html file.

Add API Key: Open index.html in a text editor.

Find the API_KEY constant in the <script> section (near the top):

// --- API Configuration ---
const API_KEY = ""; // <--- PASTE YOUR GOOGLE AI STUDIO API KEY HERE
const IMAGE_API_URL = `https://generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash-image-preview:generateContent?key=${API_KEY}`;
const TEXT_API_URL = `https://generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash-preview-09-2025:generateContent?key=${API_KEY}`;


Paste your Google AI Studio API key inside the quotes.

Run: Save the file and open it in any modern web browser.

💻 Technical Stack

HTML5

CSS3:

Tailwind CSS (loaded via CDN)

Custom Keyframe Animations (Glow, Bounce, Particles)

JavaScript (ES6+):

Vanilla JS for all DOM manipulation, state management, and event handling.

fetch API with exponential backoff for API requests.

FileReader and atob/btoa for Base64 conversion.

Custom PNG metadata embedding/extraction logic.

APIs:

Google Gemini 2.5 Flash Image Preview: For all image generation and editing tasks.

Google Gemini 2.5 Flash: For the "Enchant Prompt" text generation feature.

📄 License

This project is open-sourced and available under the MIT License.
