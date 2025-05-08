# Portable Digital Library

Technologies used:

* ![Jekyll](https://img.shields.io/badge/Jekyll-CC0000?logo=jekyll\&logoColor=white)
* ![CollectionBuilder](https://img.shields.io/badge/CollectionBuilder-000000?logo=data\:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjQiIGhlaWdodD0iMjQiLz4=\&label=CollectionBuilder)
* ![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5\&logoColor=white)
* ![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3\&logoColor=white)
* ![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript\&logoColor=black)
* ![Tauri](https://img.shields.io/badge/Tauri-FFC131?logo=tauri\&logoColor=black)
* ![Rust](https://img.shields.io/badge/Rust-000000?logo=rust\&logoColor=white)
* ![Node.js](https://img.shields.io/badge/Node.js-339933?logo=node.js\&logoColor=white)

---

## Overview

This repository packages a digital collection site into a portable, cross-platform desktop application. It uses:

* `site-builder/` — to build a static digital library website using CollectionBuilder-CSV (Jekyll-based)
* `app-builder/` — to package the built site into a native desktop app using Tauri

The result is a fully offline, distributable digital library application.

---

## 📁 Folder Structure

```
portable-digital-library/
├── site-builder/     # Contains Jekyll-based CollectionBuilder source
│   └── _site/        # Output from Jekyll build
│
├── app-builder/      # Tauri app wrapper for packaging the built site
│   └── dist/         # Static files to be loaded into the Tauri window
│
├── README.md         # You are here
```

---

## 🛠️ Step 1: Build the Collection Site

1. Navigate to the `site-builder` folder:

   ```bash
   cd site-builder
   ```

2. Install Ruby gems (only once):

   ```bash
   bundle install
   ```

3. Build the static site:

   ```bash
   bundle exec jekyll build
   ```

4. This creates the `_site/` folder containing the static HTML/CSS/JS content.

---

## 📦 Step 2: Package as Desktop App

1. Copy the built site into the Tauri app folder:

   ```bash
   cp -r _site/* ../app-builder/dist/
   ```

2. Navigate to the `app-builder` folder:

   ```bash
   cd ../app-builder
   ```

3. Install dependencies (only once):

   ```bash
   npm install
   ```

4. Build the Tauri app:

   ```bash
   npm run tauri build
   ```

5. The packaged `.app`, `.exe`, or `.AppImage` will appear under:

   ```
   src-tauri/target/release/bundle/
   ```

---

## Done!

You now have a portable digital library app that runs offline and includes all collection assets (PDFs, images, metadata). Distribute the `.app` or `.exe` as needed.

---

MIT License
