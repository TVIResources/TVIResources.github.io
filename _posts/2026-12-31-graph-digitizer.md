---
title: "Program for Digitizing Graphs into Data Points"
excerpt_separator: "<!--more-->"
date: 2026-12-31
categories:
  - blog
tags:
  - math
  - statistics
  - transcription tools
  - braille
  - software
  - coding
search: exclude
---

Graph Digitizer is a compact Julia + Gtk GUI application for extracting numeric data points from raster images of plots. It provides interactive calibration (pixel → data mapping), manual point picking and dragging, a color-based auto-trace routine, precision magnifier for pixel-level placement, and exports to structured JSON and a wide CSV (X column then Dataset1..Dataset10). The code is defensive about Gtk.jl variations and includes fallbacks for file dialogs and main-loop handling so it runs across common platforms.

Many published or embedded graphs are effectively inaccessible: the numeric data behind a plot is not available in the figure, in PDFs, or in screenshots. Graph Digitizer fills that gap by letting users recover series from images reliably — including support for logarithmic axes, multiple overplotted datasets, and color-based tracing where curves are visually distinct. This makes results reproducible, facilitates secondary analysis, and improves accessibility when original data cannot be obtained.

Quick usage: start the app (julia --project=@. graph_digitizer.jl or call run_app()), load an image, run Calibrate Clicks (click X-left, X-right, Y-bottom, Y-top), enter X/Y min/max and Apply Calibration, then add points by left-clicking (drag to move, right-click/delete to remove). Use Auto Trace for a selected dataset to auto-sample by color, and save results via Save (Ctrl+S) which writes JSON and the wide CSV; use File → Exit or Ctrl+Q to quit cleanly.

{% include staticman-form.html %}
