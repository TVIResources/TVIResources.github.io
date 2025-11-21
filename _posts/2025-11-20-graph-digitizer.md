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

## Graph Digitizer v1.1 — Java 21 Edition

This project has moved to a modern Java 21 / JavaFX implementation. The release available in this repo is a Java-based desktop application intended for teachers and researchers who need an easy way to extract numeric data from raster images of graphs.

If you prefer a quick run without building from source, the README includes downloadable artifacts and packaging instructions. Developers and power users can build and run the application locally (see commands below).

## Documentation and downloads

- Quick Reference Guide: `QUICK_REFERENCE.md` — keyboard shortcuts and common tasks
- Developer Guide: `DEVELOPER.md` — architecture and extension points
- Accessibility docs: `ACCESSIBILITY.md`, `ACCESSIBILITY_QUICK_START.md`, and `ACCESSIBILITY_IMPLEMENTATION_COMPLETE.md` (audit fixes applied)
- Packaging & Distribution: `packaging/README.md` — instructions for creating AppImage/DEB/RPM/DMG/EXE installers

You can run the packaged JAR (after building) with:

```bash
java -jar target/graph_digitizer_1.0-beta.jar
```

Or run directly from Maven while developing:

```bash
mvn javafx:run
```

If you want a single distributable for end users, see the Packaging & Distribution docs for `jlink` + `jpackage` recipes.

## Quick start (teacher-friendly)

1. Install Java 21 (or later) on your computer. If you don't have Java installed, the packaging instructions describe creating a self-contained installer so students don't need Java installed.
   - For most of you on Windows 11 the easiest way will be to do the following:
     - Open your terminal or command prompt
     - Type the following command and press enter:
      
      ```ps1
       winget install Microsoft.OpenJDK.21
       ```
     - After installation is complete, you can verify Java is installed by typing the following command and pressing enter:
     
     ```ps1
      java -version
     ```
2. Download or clone the repository and follow the README to open the app or run the provided JAR.
3. Load a PNG or JPEG of the graph and press **Calibrate** to set four known points on the axes.
4. Select a dataset color and click points on a curve (or use Auto-trace for clearly colored lines).
5. Export to CSV to use in Excel/Google Sheets, or save the project as JSON to preserve axis metadata and colors.

This workflow is made to avoid command-line steps for everyday classroom use — teachers can run the packaged app and use the GUI only.

A quick screenshot of the application is shown below to give a sense of the interface (calibration controls at left, image/canvas in the center, and dataset controls at the right).

![Graph Digitizer application window: left column contains calibration controls with four anchor-point fields and numeric axis range inputs; center shows a zoomable canvas displaying a raster graph image with overlaid color-coded data points and gridlines; right column lists dataset controls with color swatches, dataset names, visibility toggles, and export buttons. Toolbar at top shows common actions like Open, Calibrate, Auto-trace, and Export.](/assets/images/graph-digitizer/Screenshot%202025-11-19%20073537.png)

*Screenshot shows a sample session. Associated sample files: [Sample_Graph_20251119-073453.json](/assets/data/Sample_Graph_20251119-073453.json) and [Sample_Graph_20251119-073453.csv](/assets/data/Sample_Graph_20251119-073453.csv).*

## Example outputs and sample files

Below are small sample files you can download and open to see the exact formats produced by Graph Digitizer. They live in the `assets/data` folder of this site.

- General example (six datasets, 5 points each): [graph_digitizer_example.json](/assets/data/graph_digitizer_example.json) and [graph_digitizer_example.csv](/assets/data/graph_digitizer_example.csv)
- Log-scale example (x axis logarithmic): [graph_digitizer_example_log.json](/assets/data/graph_digitizer_example_log.json) and [graph_digitizer_example_log.csv](/assets/data/graph_digitizer_example_log.csv)
- Missing values example (nulls / empty cells): [graph_digitizer_example_missing.json](/assets/data/graph_digitizer_example_missing.json) and [graph_digitizer_example_missing.csv](/assets/data/graph_digitizer_example_missing.csv)

Short CSV preview (first three rows of the general example):

```csv
x,Dataset_1,Dataset_2,Dataset_3,Dataset_4,Dataset_5,Dataset_6
0.0,0.5,0.8,0.2,1.0,0.4,0.6
1.0,1.2,1.5,0.9,1.9,0.7,1.1
```

Use the JSON files if you want full project metadata (axis ranges, log flags, colors) and the CSV files for quick spreadsheet analysis.

First example dataset (JSON excerpt):

```json
{
  "name": "Dataset 1",
  "color": "#1f77b4",
  "points": [[0.0, 0.5], [1.0, 1.2], [2.0, 2.4], [3.0, 3.1], [4.0, 4.0]]
}
```


## Key features

- Load PNG/JPEG images and view them on a zoomable canvas.
- Calibration with four anchor points and numeric axis ranges (linear & log support).
- Point-and-click capture plus drag-to-adjust and delete.
- Auto-trace for color-distinct curves.
- Multiple datasets (color-coded) and export to CSV and JSON.
- Designed with accessibility in mind — see the accessibility docs for screen reader guidance and keyboard-first workflows.

## Packaging notes (for IT / power users)

The project includes Maven profiles and helper scripts to create a self-contained installer using `jlink`/`jpackage`, or a fat JAR using the Maven Shade plugin. See the `packaging/README.md` for platform-specific commands and signing instructions.

## Want to contribute or test?

- Browse the repo: [Graph Digitizer (Java) repository](https://github.com/mrhunsaker/Graph_Digitizer_Java_Implementation)
- Report issues, request features, or share classroom examples via GitHub Issues.
