---
title: "Graph Digitizer"
excerpt_separator: "<!--more-->"
date: 2025-11-20
categories:
  - blog
tags:
  - math
  - statistics
  - data extraction
  - software
---

Many teachers encounter graphs in textbooks, reports, or PDFs that lack the underlying numbers. Graph Digitizer is a compact, easy-to-use GUI that sits between a quick demo and a full-featured extractor: it provides a simple point-and-click workflow (load an image, calibrate axes, click or auto-trace points) for non-technical users while still offering optional advanced features when needed.

<!--more-->

## What this tool offers

- Load PNG/JPEG images and view them on a zoomable canvas so you can inspect fine detail.
- Quick calibration: mark four anchor pixels (left/right X and bottom/top Y) and enter their numeric values; the app converts pixels to data automatically.
- Point-and-click capture: click to record points, drag to adjust, and delete mistakes with a button or the keyboard.
- Optional auto-trace: extract a curve automatically when it is visually distinct (different color) from the background.
- Multiple datasets: manage more than one curve in the same image and export them together.
- Export options: CSV for immediate spreadsheet use, JSON/project save to preserve axis metadata and colors.

## A teacher-friendly workflow (5 minutes)

1. Open Graph Digitizer and click **Load Image**.
2. Click **Calibrate** and follow the prompts to click the four axis anchor pixels, then type the real numeric values.
3. Choose a dataset (one per curve), then click points on the curve to capture them. Use the precision zoom or zoom controls for tight areas.
4. Optionally use **Auto-trace** for clearly colored curves to populate many points at once.
5. Click **Save → CSV** to download a spreadsheet-ready file and open it in Excel or Google Sheets.

This workflow intentionally avoids command-line steps for everyday use. If you want to install and run the app locally, the repository's README includes straightforward one-line commands and platform notes.

## Practical notes and tips

- CSV vs JSON: CSV is the easiest to share with colleagues and to import into lesson plans; JSON saves the full project state if you want to return and edit later.
- When auto-trace doesn't capture the curve perfectly, use point-and-click to correct gaps or outliers.
- For logarithmic plots, be sure to select the log option before exporting so axis transforms are preserved in JSON (CSV will contain the data values).
- The app is cross-platform (Windows/macOS/Linux). The README has simple setup instructions if you need them; you don't need to understand Julia to use the GUI after it's running.

## Want to try it?

Download or browse the project on GitHub: [Graph Digitizer repository](https://github.com/TVIResources/Graph_Digitizer). The repo contains a full README, examples, and troubleshooting notes. If you try the tool and have feedback or a teaching example to share, please open an issue or leave a comment — real classroom examples help prioritize improvements.

If you'd like, I can add a short screenshot and an example CSV preview to this post so teachers can quickly see what the output looks like before downloading.
