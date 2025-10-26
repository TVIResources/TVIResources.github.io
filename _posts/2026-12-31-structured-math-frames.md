---
title: "Structured Math Frames for UEB, Nemeth, and Print"
excerpt_separator: "<!--more-->"
date: 2026-12-31
categories:
  - blog
tags:
  - 3d printing
  - math
  - instructional materials
  - braille
search: exclude
---

These structured math frames grew out of a common and persistent challenge: visually impaired and blind students often struggle to learn the vertical alignment of numbers required for addition, subtraction, and especially multi-digit multiplication. For sighted students, graph paper or lined columns provide an immediate visual guide to keep digits under one another. A student using a Perkins braillewriter, however, must manage both the math and the tactile formatting simultaneously — keeping place value columns aligned while also composing braille. That extra layer of formatting work frequently competes with the cognitive load of solving the problem itself.

Multiplication introduces a particularly tricky hurdle: when multiplying by the tens or hundreds digit a student must conceptually and physically "add" zeros to the far right of intermediate partial products before summing. On a Perkins braillewriter this means the student must either pre-format the line with trailing placeholders or later shift focus to ensure zeros are placed correctly — a task that interrupts the math and increases errors. These frames are intended to reduce the burden of braille formatting so the student can concentrate on the mathematical reasoning rather than the layout mechanics.

## Features of the Braille Math Worksheet Generator

These are simple, ready-to-use frames that help students line up numbers the way they do on graph paper. Each frame supports addition, subtraction, multiplication, or division and shows separate columns for ones, tens, hundreds, and thousands so digits stay under the correct place value. A clear spot is provided for the operation sign (plus, minus, times, divide) so students only need to focus on the math, not the layout.

For addition and subtraction the frame includes a horizontal line to separate the problem from the answer area. The multiplication frame provides extra rows for the intermediate partial products and a final answer line, making it easier for students to place digits and trailing zeros in the right spot. Division frames include a tactile long-division area with space for the divisor, dividend, partial quotients, and final answer.
The project includes 3D-print files for a small lidded carrier and number tiles (0–9) plus operation tiles and blank filler tiles. Files are provided in both braille (UEB and Nemeth) and print-friendly versions. You can print using two filament colors to make the tactile frames and printed markings easy to distinguish for students with different needs.

### Example images

- Addition/Subtraction Frame (UEB braille)
  ![Addition/Subtraction Frame](/assets/images/structured-math-frames/addSubtractFrame.png)
- Multiplication Frame (UEB braille)
  ![Multiplication Frame](/assets/images/structured-math-frames/MultiplicationFrame.png)
- Division Frame (UEB braille)
  ![Division Frame](/assets/images/structured-math-frames/DivisionFrame.png)
- Storage Bay
  ![Storage Bay](/assets/images/structured-math-frames/StorageBay.png)
- Example of print, UEB, and Nemeth versions of the number 5 tile and Plus symbol tile
  ![Number and Plus Tiles](/assets/images/structured-math-frames/Examples.png)
- Time-Keeping Frame (UEB braille)
  ![TimeKeeping Frame](/assets/images/structured-math-frames/TimeKeepingFrame.png)

## Getting Started
Getting started is simple — there are two ways to use these materials depending on what you prefer:

- Quick download: If you just want the ready-made frames and 3D files, download the ZIP from GitHub and open the included README for simple print-and-use instructions: [Download Structured Math Frames](https://github.com/mrhunsaker/StructuredMathFrames/archive/refs/heads/main.zip).

  Note: the exported 3D print files are in the `exported_stls` folder. Files intended for UEB braille end with `_UEB.stl`, Nemeth versions end with `_Nemeth.stl`, and the print-friendly versions end with `_print.stl`.

- Use the worksheet generator: If you'd like to create custom worksheets (different sizes, number ranges, or braille/print options), the project includes small scripts that guide you through creating them. On Windows the scripts use PowerShell (included by default). macOS and Linux users can run the provided bash or zsh scripts. The README included in the download explains step-by-step how to run the scripts — no advanced coding skills required.

Printing note: I printed these files with the braille raised to the side so the dots feel correct and are not sharp to the touch. I printed on a Bambu P1S using BambuStudio with default print parameters, but used a Generic PLA filament rather than Bambu-branded PLA (I used Filastruder PLA or Elegoo PLA because they fit my budget). Your slicer may require minor adjustments for your printer and filament; start with the defaults and tweak if needed.

## Customization and Contribution

If you want to customize the frames further (change sizes, spacing, or add new components), the project includes the OpenSCAD source file used to generate the 3D models. OpenSCAD is a free, open-source 3D modeling tool that uses code to create models. You can modify the `structured_math.scad` file to adjust dimensions or add new features, then re-export the STL files for printing.

Technical note for customizers: the `structured_math.scad` file contains the code used to generate the 3D frames and tiles and is set up for use with an OpenSCAD customizer. If you want to change sizes, spacing, or add features, editing this file and re-exporting the STL files is the place to start.

Customizer instructions (adding a new component)

If you'd like to add a new component to the OpenSCAD customizer so it appears in the right-hand selector in the previewer, follow these steps:

1. Open `structured_math.scad` in OpenSCAD.
1. Find the CUSTOMIZER PARAMETERS block and add your new element name to the end of the component selection list. For example, add the new name to the end of the list in the block below:

```scad
// ===== CUSTOMIZER PARAMETERS =====

/* [Component Selection] */
// Choose which component to render
component = "none"; // [ none:None,  time_keeping_UEB:Time Keeping (UEB),  add_subtract_UEB:Addition/Subtraction (UEB),  division_UEB:Division (UEB),  multiplication_UEB:Multiplication (UEB),  operation_symbol_multiply_UEB:Multiply Symbol (UEB),  operation_symbol_add_UEB:Add Symbol (UEB),  operation_symbol_subtract_UEB:Subtract Symbol (UEB),  numbers_1_UEB:Number 1 (UEB),  numbers_2_UEB:Number 2 (UEB),  numbers_3_UEB:Number 3 (UEB),  numbers_4_UEB:Number 4 (UEB),  numbers_5_UEB:Number 5 (UEB),  numbers_6_UEB:Number 6 (UEB),  numbers_7_UEB:Number 7 (UEB),  numbers_8_UEB:Number 8 (UEB),  numbers_9_UEB:Number 9 (UEB),  numbers_0_UEB:Number 0 (UEB),  numbers_null:Number Null,  time_keeping_print:Time Keeping (Print),  add_subtract_print:Addition/Subtraction (Print),  division_print:Division (Print),  multiplication_print:Multiplication (Print),  operation_symbol_multiply_print:Multiply Symbol (Print),  operation_symbol_add_print:Add Symbol (Print),  operation_symbol_subtract_print:Subtract Symbol (Print),  numbers_1_print:Number 1 (Print),  numbers_2_print:Number 2 (Print),  numbers_3_print:Number 3 (Print),  numbers_4_print:Number 4 (Print),  numbers_5_print:Number 5 (Print),  numbers_6_print:Number 6 (Print),  numbers_7_print:Number 7 (Print),  numbers_8_print:Number 8 (Print),  numbers_9_print:Number 9 (Print),  numbers_0_print:Number 0 (Print),   division_Nemeth:Division (Nemeth),   operation_symbol_multiply_nemeth:Multiply Symbol (Nemeth),  operation_symbol_add_nemeth:Add Symbol (Nemeth),  operation_symbol_subtract_nemeth:Subtract Symbol (Nemeth),  numbers_1_nemeth:Number 1 (Nemeth),  numbers_2_nemeth:Number 2 (Nemeth),  numbers_3_nemeth:Number 3 (Nemeth),  numbers_4_nemeth:Number 4 (Nemeth),  numbers_5_nemeth:Number 5 (Nemeth),  numbers_6_nemeth:Number 6 (Nemeth),  numbers_7_nemeth:Number 7 (Nemeth),  numbers_8_nemeth:Number 8 (Nemeth),  numbers_9_nemeth:Number 9 (Nemeth),  numbers_0_nemeth:Number 0 (Nemeth), storage_bay:Storage Bay, storage_bay_case:Storage Bay Case]
```

1. Next, find a module you want to copy (look for a block that starts with `module name() { ... }`). Copy the entire module definition (from the `module` line through its matching closing `}`) and paste it below the copied module. Give the pasted module the new name you added to the customizer list and make any changes you want inside that module (dimensions, labels, etc.).
1. When done, open the Customizer panel (right side of the OpenSCAD UI), select your new component from the `component` dropdown, press F6 to fully render, and then press F7 to export the STL file. The exported STL can be opened in a slicer like BambuSlicer, OrcaSlicer, or PrusaSlicer and sent to a 3D printer.

Notes:

- Be careful to copy the full module including its closing `}` so the code remains balanced.
- Use simple names for new components (no spaces) and match the name exactly in both the customizer list and the module declaration.
- If you break the file, OpenSCAD will show an error indicating where to look; revert or undo and try again.

You are free to go in and modify the script to better suit your needs. The project is open-source, and contributions are welcome. If you have ideas for new features or improvements, or if you find any bugs, please let us know by [submitting an issue on GitHub here](https://github.com/mrhunsaker/StructuredMathFrames) or leaving a comment below. I appreciate your feedback and will do my best to address any issues promptly.

{% include staticman-form.html %}
