---
title: "Braille Math Worksheet Generator (UEB)"
excerpt_separator: "<!--more-->"
date: 2026-12-31
categories:
  - blog
tags:
  - math
  - coding
  - instructional materials
  - powershell
  - coding
  - braille
search: exclude
---

Creating braille math worksheets can be a time-consuming task, especially when trying to ensure that the formatting adheres to the Unified English Braille (UEB) standards. At present, most of us go to Math Drills and then manually braille the worksheet in our desired braille code. To streamline this process, I developed a PowerShell script that generates braille math worksheets in UEB technical format. This tool is designed to help educators quickly produce high-quality braille math materials for their students.

What this script does is allow you to make worksheets for addition, subtraction, multiplication, and division problems. You can specify the number of problems, the range of numbers to use, and the format of the worksheet. The output is a text file that can be printed directly or converted to braille using the openm-source braille translation tool liblouis.

## Features of the Braille Math Worksheet Generator

This small tool gives teachers a fast, no-fuss way to make printable math practice sheets. From a simple menu you choose the operation (addition, subtraction, multiplication or division), how many problems you want, and the number ranges — the script then creates ready-to-print text worksheets you can copy into a document or print directly. No programming knowledge is needed: just run the script in PowerShell (Windows) or the provided bash/zsh versions on macOS/Linux.

It includes a variety of worksheet types that are useful for elementary classrooms: standard column-style problems, mixed add/subtract sets, multiplication tables (including a “fixed first factor” mode like 2×N and flexible X×Y grids), division questions that always have whole-number quotients, and mixed multiplication/division sheets. You can generate multiple worksheets at once and the files are saved in a folder so you can reuse or edit them later.

For classrooms or students who need tactile access, the project also supports optional braille conversion if you install the liblouis tool (lou_translate). The scripts use braille-friendly symbols (×, ÷, −) to improve translation results and can convert worksheets into individual or combined BRF files when the conversion tool and table are available. Overall it’s a lightweight, teacher-friendly way to produce consistent, repeatable practice materials quickly.

## Getting Started
To use the Braille Math Worksheet Generator, you will need to have PowerShell installed on your computer. If you are using Windows, PowerShell is included by default. For macOS and Linux users, you can use the provided bash or zsh scripts. These scripts are designed to be user-friendly, with clear prompts guiding you through the worksheet creation process.

You can [download the Braille Math Worksheet Generator as a zipped file here](https://github.com/TVIResources/BrailleMathWorksheetGenerator/archive/refs/heads/main.zip) and the braille conversion program (liblouis) can be found [here](https://liblouis.io/downloads). Windows users can find a precompiled version of liblouis [here](https://github.com/liblouis/liblouis/releases/download/v3.35.0/liblouis-3.35.0-win64.zip). After downloading, extract the contents of the zip file to a folder on your computer. You can then run the PowerShell script by navigating to the folder in PowerShell and executing the script file.

Further instructions and details about the script's functionality can be found in the README file included in the download package. This file provides comprehensive guidance on how to customize the worksheets to fit your specific needs.

## Customization and Contribution

You are free to go in and modify the script to better suit your needs. The project is open-source, and contributions are welcome. If you have ideas for new features or improvements, or if you find any bugs, please let us know by [submitting an issue on GitHub here](https://github.com/TVIResources/BrailleMathWorksheetGenerator) or leaving a comment below. I appreciate your feedback and will do my best to address any issues promptly.

{% include staticman-form.html %}
