# 🎨 Advanced Pixel Art Generator

[![GitHub Pages](https://img.shields.io/badge/GitHub-Pages-brightgreen?style=for-the-badge&logo=github)](https://immagowithathiya.github.io/pixel_art_project/)

A high-performance, browser-based tool for converting any image into stylized pixel art using K-means clustering and multiple error-diffusion dithering algorithms, all implemented from scratch in pure JavaScript.

**[➡️ View Live Webpage](https://immagowithathiya.github.io/pixel_art_project/)**


## ✨ Core Features

* **K-means Color Quantization:** Implements the K-means clustering algorithm from scratch to intelligently reduce the image's color palette to a user-defined number (2-32 colors).
* **Multiple Dithering Algorithms:** Includes a selection of three classic error-diffusion algorithms to preserve detail and create the illusion of more colors:
    * Floyd-Steinberg (Classic)
    * Jarvis-Judice-Ninke (Smoother)
    * Stucki (Sharper)
* **True Pixelation:** A "Pixel Size" slider enables resolution reduction by downscaling the image with pixel averaging *before* processing, achieving an authentic blocky aesthetic.
* **Non-Blocking Performance:** All heavy computations (downscaling, K-means, dithering) run in a separate **Web Worker** thread, ensuring the UI remains 100% responsive and never freezes.
* **Algorithm Visualization:** A dynamic dashboard appears after processing, showing the generated K-means palette, a 2D plot of the color clusters, and key performance stats (processing time, K-means iterations).
* **Interactive Comparison:** A sleek, touch-enabled slider allows for easy before-and-after comparison.
* **Multi-Scale Export:** Download the final pixel art as a PNG at 1x, 2x, or 4x scale.
* **Automated Deployment:** Includes a GitHub Actions workflow for automatic CI/CD deployment to GitHub Pages on every push to the `main` branch.

---

## 🚀 How to Use

1.  **Upload Image:** Click "Choose Image" to upload your own file.
2.  **Adjust Settings:**
    * **Number of Colors:** Select how many colors (2-32) the K-means algorithm should use.
    * **Pixel Size:** Set the "chunkiness" of the pixels. `1x` is original resolution, `8x` means an 8x8 block of original pixels becomes one new pixel.
    * **Dithering Algorithm:** Choose your preferred dithering method. `None` shows the raw K-means result, while `Floyd-Steinberg` is a great all-rounder.
3.  **Process:** Click "Process Image" and watch the live progress bar.
4.  **Compare:** Use the interactive slider to compare the "Original" vs. "Pixel Art" result.
5.  **Analyze:** Check the "Algorithm Visualization" dashboard to see the generated palette and stats.
6.  **Download:** Click "Download Options" to save your work as a PNG.

---

## 🛠️ Technology Stack

This project is built from the ground up with **zero external frameworks or libraries**.

* **Core:** Vanilla JavaScript (ES6+), HTML5, CSS3
* **Layout:** CSS Flexbox & Grid
* **Key Web APIs:**
    * **Web Workers API:** For all asynchronous processing.
    * **HTML5 Canvas API:** For all pixel-level reading (`getImageData`) and writing (`putImageData`).
    * **File API & Blob API:** For image uploading and PNG downloading.
* **DevOps:** GitHub Actions for Continuous Integration & Deployment (CI/CD).

---

## 📦 How to Run Locally

No build tools, compilers, or `npm install` required.

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/immagowithathiya/pixel_art_project.git](https://github.com/immagowithathiya/pixel_art_project.git)
    ```
2.  **Navigate to the directory:**
    ```bash
    cd pixel_art_project
    ```
3.  **Open the file:**
    Simply open the `index.html` file in your web browser.

    *(Note: Some browsers require a local server for Web Workers to function. If it doesn't run from the file, use a simple HTTP server.)*
   
