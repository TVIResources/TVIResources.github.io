---
title: "Braille Math Worksheet Generator (UEB)"
excerpt_separator: "<!--more-->"
date: 2025-11-16
categories:
  - blog
tags:
  - math
  - coding
  - instructional materials
  - powershell
  - coding
  - braille
comments: true
---

Creating braille math worksheets is both time-consuming and technically demanding. Unified English braille (UEB) technical/math formatting uses precise conventions and translator-sensitive symbols; small differences in punctuation, spacing, or symbol choice can produce incorrect translation or loss of meaning in braille. Many teachers still start with printable sources (for example, Math Drills) and then manually transcribe or translate each worksheet; a slow, error-prone process that is difficult to scale.

To address this, I developed a PowerShell/Command script that generates worksheets formatted for UEB technical math. The script produces plain-text worksheets optimized for braille translation (relyong on the same open source tools used for math transcription in BrailleBlaster, NVDA, and JAWS--Liblouis) and for direct printing, reducing manual transcription and avoiding common transcription pitfalls like using an `x` rather than a unicode multiplication cross (`×`) or a hyphen (`-`) rather than a subtraction symbol (`−`).

The script generates problems for addition, subtraction, multiplication, and division. You can set the number of problems, choose number ranges, and select the worksheet format. The output is a plain text file that can be printed directly or converted to braille using the open-source Liblouis translation tool.

## Features of the Braille Math Worksheet Generator

This small tool gives teachers a fast, no-fuss way to make printable math practice sheets. From a simple menu you choose the operation (addition, subtraction, multiplication, or division), how many problems you want, and the number ranges. The script takes these information and creates ready-to-print text worksheets you can copy into a document or print directly. No programming knowledge is needed: just run the script in PowerShell (Windows) or the provided bash/zsh versions on macOS/Linux.

It includes a variety of worksheet types that are useful for elementary classrooms: standard column-style problems, mixed add/subtract sets, multiplication tables (including a “fixed first factor” mode like 2×N and flexible X×Y grids), division questions that always have whole-number quotients, and mixed multiplication/division sheets. You can generate multiple worksheets at once and the files are saved in a folder so you can reuse or edit them later.

For classrooms or students who need tactile access, the project supports optional fully automatic braille conversion using the liblouis tool (`lou_translate`). The scripts deliberately use braille-friendly Unicode symbols (×, ÷, −) and output spacing that improves translation results, and they can convert worksheets into individual or combined BRF files when the conversion tool and appropriate tables are available. Overall it’s a lightweight, teacher-friendly way to produce consistent, repeatable practice materials quickly while reducing the risk of translator errors.

<!--more-->

## Getting Started

To use the Braille Math Worksheet Generator, you will need PowerShell installed on your computer. If you are using Windows, PowerShell is included by default. For macOS and Linux users, you can use the provided bash or zsh scripts. These scripts are designed to be user-friendly, with clear prompts guiding you through the worksheet creation process.

Download the Braille Math Worksheet Generator (zip archive) from the GitHub repository: [Braille Math Worksheet Generator — zip](https://github.com/TVIResources/BrailleMathWorksheetGenerator/archive/refs/heads/main.zip). The braille translation tool, Liblouis, is available from the Liblouis downloads page: [Liblouis downloads](https://liblouis.io/downloads). Windows users can download a precompiled Windows release of Liblouis from the Liblouis GitHub releases: [Liblouis Windows release (v3.35.0)](https://github.com/liblouis/liblouis/releases/download/v3.35.0/liblouis-3.35.0-win64.zip). After downloading, extract the contents of the zip file to a folder on your computer, then run the PowerShell script by navigating to that folder in PowerShell and executing the script file.

Windows example — where to place Liblouis

If you extract the Windows release to your user profile, a convenient location is `%USERPROFILE%\liblouis`. 

1. Extract the file using Winzip, PeaZip, 7Zip, WinRar, or any other program you use to unzip things. I always extract to my downlads folder so I do not lose things
2. Move the folder to your home directory. This is the folder that has your Documents, Downloads, Photos, Videos, etc. folders in it. 
   1. You will see a folder in your home folder named something like `liblouis-3.35.0-win64`. You can rename this folder to just `liblouis` to make it easier to type later.
3. The path  to the file you will use should look like this after you move it:

~~~text
C:\Users\`your-username`\liblouis\bin\lou_translate.exe
~~~

Three quick ways to make the translator callable from scripts or the shell

1. Add Liblouis to your PATH (edit Environment Variables)

   - Open the **Start** menu and type "Environment Variables" → select **Edit the system environment variables** → click **Environment Variables...**.
   - Under **User variables for `your-username`** select `Path` and click **Edit**.
   - Click **New** and add the folder that contains the translator binary, for example: `C:\Users\your-username\liblouis\bin`.
   - Click **OK** on all dialogs to save. Close and reopen any open terminals (PowerShell/CMD) so they pick up the updated PATH.

2. Navigate to the folder and run from there (no PATH changes)

   - Open PowerShell or Command Prompt.
   - Change to the translator folder:

  ~~~powershell
  cd $env:USERPROFILE\liblouis\bin
  ~~~
  or in cmd.exe:
  ~~~cmd
  rem cd %USERPROFILE%\liblouis\bin
  ~~~

   - Run the translator explicitly from that folder. In PowerShell:

  ~~~powershell
  .\lou_translate.exe -i input.txt -o output.brf --table en-ueb-ita.ctb
  ~~~
  or in cmd.exe
  ~~~cmd
  lou_translate.exe -i input.txt -o output.brf --table en-ueb-ita.ctb
  ~~~

3. Create a persistent alias or small wrapper so you can run the translator from anywhere

   - PowerShell: add a function to your PowerShell profile so it is always available. 
   - Open PowerShell and run: 

    ~~~powershell
    notepad $PROFILE
    ~~~
    Copy this into the file that opens and save it. 
    ~~~powershell
    if (!(Test-Path -Path $PROFILE)) { New-Item -ItemType File -Force -Path $PROFILE }
    Add-Content -Path $PROFILE -Value "function lou_translate { & \"$env:USERPROFILE\\liblouis\\bin\\lou_translate.exe\" $args }"
    ~~~

     Then restart PowerShell by closing it and opening it again. Then and you can call `lou_translate input.txt -o output.brf` directly.

   - cmd.exe (persistent): create a small wrapper `.bat` file in a folder already on your PATH (for example `%USERPROFILE%\bin`) or add that folder to PATH. Example wrapper `C:\Users\yourname\bin\lou_translate.bat`:

    ~~~bat
    @echo off
    "%USERPROFILE%\liblouis\bin\lou_translate.exe" %*
    ~~~

     Save the `.bat` file and then you can call `lou_translate input.txt -o output.brf` from cmd.exe.

These three approaches let you run Liblouis reliably from within the worksheet scripts (either by relying on PATH, by invoking the translator using a full or relative path, or by using a small alias/wrapper). Choose whichever approach fits your local policy and workflow.

Further instructions and details about the script's functionality can be found in the README file included in the download package. This file provides comprehensive guidance on how to customize the worksheets to fit your specific needs.

## Customization and Contribution

You are free to modify the script to suit your needs. The project is open-source, and contributions are welcome. If you have ideas for new features or improvements, or if you find any bugs, please let us know by [submitting an issue on GitHub](https://github.com/TVIResources/BrailleMathWorksheetGenerator) or leaving a comment below. I appreciate your feedback and will do my best to address issues promptly. You are also welcome to fork the repository and submit pull requests directly with your changes.

A quick note about notation variants: I would very much like to provide a Nemeth-version of this generator, but I haven't had the time or sufficient requests to prioritize it. Utah is a mixed UEB/Nemeth state and individual LEAs choose which code they implement; if your district needs Nemeth output (or you can share examples of local requirements), please contact me or open an issue — that will help me prioritize a Nemeth conversion. It will always be a Nemeth *option* to go along with UEB as I believe there is place for both codes to co-exist within the BANA UEB framework. 

