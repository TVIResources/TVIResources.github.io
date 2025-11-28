---
title: "Graph Digitizer"
excerpt_separator: "<!--more-->"
date: 2025-11-20
last_updates_at: 2025-11-25
categories:
  - blog
tags:
  - math
  - statistics
  - data extraction
  - software
comments: true
---

Many teachers encounter graphs in textbooks, reports, or PDFs that lack the underlying numbers. Graph Digitizer is a compact, easy-to-use GUI that sits between a quick demo and a full-featured extractor: it provides a simple point-and-click workflow (load an image, calibrate axes, click or auto-trace points) for non-technical users while still offering optional advanced features when needed.

<!--more-->

## Graph Digitizer v1.1 — Java 21 Edition 

This project has moved to a modern Java 21 / JavaFX implementation. The release available in this repo is a Java-based desktop application (version **1.0**) intended for teachers and researchers who need an easy way to extract numeric data from raster images of graphs.

If you prefer a quick run without building from source, **Windows users can download a pre-built x64 executable from the [GitHub release page](https://github.com/mrhunsaker/Graph_Digitizer_Java_Implementation/releases)** — no Java installation required. Developers and power users can build and run the application locally (see commands below).

## Documentation and downloads

The project includes comprehensive documentation covering all aspects of the tool:

**User Documentation:**
- Quick Reference Guide: `QUICK_REFERENCE.md` — keyboard shortcuts and common tasks
- Accessibility docs: `ACCESSIBILITY.md`, `ACCESSIBILITY_QUICK_START.md`, `ACCESSIBILITY_IMPLEMENTATION_COMPLETE.md` (audit fixes applied), and `ACCESSIBILITY_CHECKLIST.md`

**Developer Documentation:**
- Developer Guide: `DEVELOPER.md` — architecture, patterns, and extension guide
- Project Summary: `PROJECT_SUMMARY.md` — complete project overview
- Documentation Index: `INDEX.md` — comprehensive index of all documentation

**Advanced Topics:**
- Packaging & Distribution: `packaging/README.md` — instructions for AppImage/DEB/RPM/DMG/EXE/MSI installers
- jlink/jpackage Guide: `docs/JPACKAGE.md` — runtime images, cross-architecture builds, and native packaging
- Packaging Scripts: `scripts/README.md` — helper scripts including Windows MSI generation

**API Documentation:**
- Latest Javadoc: [API Documentation](https://mrhunsaker.github.io/Graph_Digitizer_Java_Implementation/) — generated from current main branch
- Versioned archives available per release (e.g., `/1.1/`, `/1.2/`)

You can run the packaged JAR (after building) with:

```bash
java -jar target/graph_digitizer_1.0-beta.jar
```

Or run directly from Maven while developing:

```bash
mvn javafx:run
```

If you want a single distributable for end users, see the Packaging & Distribution docs for `jlink` + `jpackage` recipes, or download the pre-built Windows executable from the releases page.

## Quick start (teacher-friendly)

**For Windows users with the pre-built executable:**
1. Visit the [GitHub release page](https://github.com/mrhunsaker/Graph_Digitizer_Java_Implementation/releases)
2. Download the Windows x64 executable
3. Run it directly — no installation or Java setup required
4. Skip to step 3 below

**For other platforms or building from source:**
1. Install Java 21 (or later) on your computer. If you don't have Java installed, the packaging instructions describe creating a self-contained installer so end users don't need Java installed.
   - For Windows 11, the easiest way is:
     - Open your terminal or command prompt
     - Type the following command and press enter:
      
      ```ps1
       winget install Microsoft.OpenJDK.21
       ```
     - After installation is complete, verify Java is installed by typing:
     
     ```ps1
      java -version
     ```
   - For macOS: `brew install openjdk@21`
   - For Linux: Use your package manager (e.g., `apt-get install openjdk-21-jdk`)

2. Download or clone the repository and follow the README to build the app:

   ```bash
   mvn clean package
   java -jar target/graph_digitizer_1.0-beta.jar
   ```

**Digitizing your graph (all platforms):**

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

- **Load PNG/JPEG images** and view them on a zoomable canvas.
- **Non-blocking calibration** with four anchor points and numeric axis ranges (linear & logarithmic support).
- **Point-and-click capture** plus drag-to-adjust and delete operations.
- **Auto-trace** for automatically extracting color-distinct curves.
- **Multiple datasets** (up to 6 color-coded) with independent visibility toggles.
- **Linear & log scale support** for both axes independently.
- **Export formats**: CSV (tabular, spreadsheet-compatible) and JSON (full metadata with colors and log flags).
- **Responsive UI**: Modern JavaFX 21 interface with intuitive controls.
- **Accessibility first**: Full support for screen readers, keyboard navigation, and low-vision themes (see accessibility docs for details).

## Architecture highlights

The application is built with clean architecture principles:

- **Core package** (`com.digitizer.core`): Pure business logic with no GUI dependencies — coordinate transforms, color operations, and data models. All core logic can be tested and reused independently.
- **Image package** (`com.digitizer.image`): Image loading and automatic curve extraction.
- **IO package** (`com.digitizer.io`): JSON and CSV export with full format support.
- **UI package** (`com.digitizer.ui`): JavaFX-based graphical interface.

This modular design makes the tool easy to extend and embed in other applications.

## Packaging options (for IT / power users)

The project includes multiple distribution options:

- **Pre-built Windows x64 executable** (recommended for most Windows users) — download from [releases page](https://github.com/mrhunsaker/Graph_Digitizer_Java_Implementation/releases)
- **Fat JAR** using Maven Shade plugin — single JAR file (requires Java 21 installed)
- **Native installers** (MSI for Windows, DMG/PKG for macOS, DEB/RPM/AppImage for Linux) using `jlink` + `jpackage`
- **Self-contained app images** for each platform using `jpackage`

See `packaging/README.md` and `scripts/README.md` for platform-specific commands and signing instructions. The unified Maven command simplifies cross-platform builds:

```bash
mvn clean package -Dnative
```

## Want to contribute or test?

- Browse the repo: [Graph Digitizer (Java) repository](https://github.com/mrhunsaker/Graph_Digitizer_Java_Implementation)
- Report issues, request features, or share classroom examples via [GitHub Issues](https://github.com/mrhunsaker/Graph_Digitizer_Java_Implementation/issues)
- Read the Developer Guide for architecture details and extension points
