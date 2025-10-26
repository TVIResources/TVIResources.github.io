---
title: "3D Printed Objects for Teaching Screen Layouts"
excerpt_separator: "<!--more-->"
date: 2025-10-26
toc: true
categories:
  - blog
tags:
  - 3d printing
  - screenreader
  - instructional materials
  - inkscape
  - openscad
  - assistive technology
search: exclude
---

When teaching students who are blind or visually impaired to use screen readers, one of the challenges is helping them understand the layout of a computer screen. While screen readers provide auditory feedback, having a tactile representation of the screen can significantly enhance comprehension and navigation skills. Unfortunately, screenreader instruction often does not explicitly teach navigation based on what are typical patterns and structures commonly used by web developers. Instead, well-meaning sighted colleagues and teachers often point to the screen and say something like, "Just go to the link on the top right", to the student. This is often extremely confusing to the student that may likely lack the clear mental model of the screen's layout. The result is that students press `Control+Home` to get to the top of the page and then just start pressing the `Tab` key repeatedly until they find what they are looking for, which is inefficient, frustrating, and ultimately demotivating.

As a way to address this, I have created a set of 3D printable objects that represent the different screen layouts that students commonly encounter during their school day. These tactile models are meant to be used in conjunction with guided screen reader instruction to help students visualize and understand the structure of a computer screen while they navigate and explore. To do this, students explore the tactile object as they listen to the screen reader's output based on their keyboard input, allowing them to correlate the auditory information with a physical representation that takes the palce of a visual one. This hands-on, multisensory approach makes it easier for students to grasp concepts like navigation, focus, and the arrangement of elements on a screen, enhancing their overall learning experience. This is also useful for sighted teachers who may not be familiar with screen reader layouts to guide their own understanding of navigable elements and how they are distributed on common websites.
<!--more-->

## Available 3D Models

All of these models are available as a free download and can be printed using any standard 3D printer with a >200 mm x 200 mm print surface. The files are slightly under 8" x 8" x 1/8" rectangles.  The files are provided in .stl format, which is widely supported by all commercial 3D printing software. [This link downloads a .zip file of the printable files](https://github.com/TVIResources/ScreenReaderTactileGraphics/archive/refs/heads/main.zip). You can see the entire GitHub Repository to download a local copy for development, create a fork to help out with development, file issues, or start Discussion Topics [here](https://github.com/TVIResources/ScreenReaderTactileGraphics)

When you download the zipped folder of these models, the files that you import into a slicer like [BambuStudio](https://bambulab.com/en/download/studio), [OrcaSlicer](https://www.orcaslicer.com/), or [PrusaSlicer](https://www.prusa3d.com/page/prusaslicer_424/) are located in the "Final3dPrintFiles" folder. The other folders contain the original .svg files created in Inkscape and OpenSCAD files used to generate the .stl 3d print files. These .svg files can be used to generate PDF tactile graphics if you have access to a tactile graphics embosser or swell paper printer.

### Available models (as of October 26, 2025):
- CavasDashboard.stl
  ![CanvasDashboard](/assets/images/3dprint-screenreader/CanvasDashboard.png)
- CavasModules.stl
  ![CanvasModules](/assets/images/3dprint-screenreader/CanvasModules.png)
- Copilot365Online.stl
  ![Copilot365Online](/assets/images/3dprint-screenreader/Copilot365Online.png)
- Desktop.stl
  ![Desktop](/assets/images/3dprint-screenreader/Desktop.png)
- DesktopAltTab.stl
  ![DesktopAltTab](/assets/images/3dprint-screenreader/Desktop_AltTab.png)
- DesktopCopilot.stl
  ![DesktopCopilot](/assets/images/3dprint-screenreader/Desktop_Copilot.png)
- DesktopStartMenu.stl
  ![DesktopStartMenu](/assets/images/3dprint-screenreader/Desktop_StartMenu.png)
- ExcelOnline.stl
  ![ExcelOnline](/assets/images/3dprint-screenreader/ExcelOnline.png)
- FileExplorerDetails.stl
  ![FileExplorerDetails](/assets/images/3dprint-screenreader/FileExplorer_Details.png)
- FileExplorerIcons.stl
  ![FileExplorerIcons](/assets/images/3dprint-screenreader/FileExplorer_Icons.png)
- GMailOnline.stl
  ![GMailOnline](/assets/images/3dprint-screenreader/GMailOnline.png)
- GoogleDocOnline.stl
  ![GoogleDocOnline](/assets/images/3dprint-screenreader/GoogleDocOnline.png)
- GoogleHome.stl
  ![GoogleHome](/assets/images/3dprint-screenreader/GoogleHome.png)
- GoogleResults.stl
  ![GoogleResults](/assets/images/3dprint-screenreader/GoogleResults.png)
- GoogleSheetsOnline.stl
  ![GoogleSheetsOnline](/assets/images/3dprint-screenreader/GoogleSheetsOnline.png)
- GoogleSlidesOnline.stl
  ![GoogleSlidesOnline](/assets/images/3dprint-screenreader/GoogleSlidesOnline.png)
- OfficeSplashPage.stl
  ![OfficeSplashPage](/assets/images/3dprint-screenreader/OfficeSplashPage.png)
- OutlookOnline.stl
  ![OutlookOnline](/assets/images/3dprint-screenreader/OutlookOnline.png)
- PPTOnline.stl
  ![PPTOnline](/assets/images/3dprint-screenreader/PowerpointOnline.png)
- WebsiteWithHeadings.stl
 ![WebsiteWithHeadings](/assets/images/3dprint-screenreader/WebsiteWithHeadings.png)
- WordOnline.stl
  ![WordOnline](/assets/images/3dprint-screenreader/WordOnline.png)

### Printing Instructions

These models are designed to be printed flat. Attempts to print them upright resulted in extremely poor quality prints. The models can be printed using PLA, PET-G, ABS, or any other rigid filament that is  commonly used materials for 3D printing. You also, if supported by your printer, set the files up so the raised areas can print in a high contrast color to the base for use with low-vision students that still need the tactile support. These [instructions](https://wiki.bambulab.com/en/software/bambu-studio/color-painting-tool) describe how to do this is Bambu Studio using the COlor Painting Tool/Height Range Tool.

I printed these models using a BambuLab P1S printer with a 0.4 mm nozzle. All print settings in Bambu Studio were left at the program defaults except I changed the PLA filament source from Bambu PLA to be Generic PLA (I use Filastruder PLA+ filament because it fit my price point, which means as inexpensive as I was able to get while trusting the quality). Splice3D, Bambu Labs, and Elegoo PLA filament have also worked well. I printed them all in a single color since I am using them with students that would not benefit from color contrast and I try to avoid visual teaching of screenreaders whenever possible.

## How You Can Customize this Resource

If you have access to a 3D printer and are familiar with 3D modeling software, you can customize these models to better suit your specific needs. The original design files are included in the download package, allowing you to modify dimensions, add or remove features, or create entirely new layouts based on the provided templates.

The main design files are created using [OpenSCAD](https://openscad.org/), a free and open-source software for creating 3D CAD models. The vector graphics used in the designs were created using [Inkscape](https://inkscape.org/), which is also free and open-source. Both of these tools have active communities and plenty of tutorials available online to help you get started.

Here are the steps I recommend for customizing the models:
- Install OpenSCAD and Inkscape on your computer.
- Open the .svg files and modify them as needed using Inkscape.
  - All of my application based models are Office365 or Google Docs, so the browser tabs and search bar are omnipresent. This means these componsents are present for use in other application models.
  - If you want to remove these components, you can delete them from the .svg files using Inkscape.
- Save the svg file after making changes. I save them to a folder names svg_intermediate_files to keep them separate from the final files I will create.
- Export the svg file you just saves as a png file from Inkscape. I use a resolution of 300 dpi.
- Open the png file in Inkscape and do the following:
  - Go along the top menu and select Path -> Trace Bitmap.
  - In the Trace Bitmap window, select "Brightness cutoff" and set the threshold to 0.500. Click OK.
  - Delete the original png image from the Inkscape window, leaving only the traced vector image.
  - Save the image as a plain svg file. I save these files to a folder named svg_final_files.
  This has to be done because there is a quirk in openSCAD that prevents it from importing certain types of svg files correctly. Exporting the traced bitmap as a plain svg file resolves this issue.
- Open the ScreenReaderVisualizationsOverall.scad file in OpenSCAD.
  - In OpenSCAD, find a line like this and copy it, and paste right after the `}` and before the next `elseif`:
~~~lua
else if (design == "CavasModules") {
translate([-15, -15, 1.75])
color(c="yellow") {
    linear_extrude(height=1.25)
        import("../svg_final/CanvasModules_traced.svg");
}
}
~~~
    becomes
~~~lua
else if (design == "CavasModules") {
translate([-15, -15, 1.75])
color(c="yellow") {
    linear_extrude(height=1.25)
        import("../svg_final/CanvasModules_traced.svg");
}
}
else if (design == "CanvasModules") {
translate([-15, -15, 1.75])
color(c="yellow") {
    linear_extrude(height=1.25)
        import("../svg_final/CavasModules.svg");
}
}
else if ...
~~~
  - Change the second `CavasModules` to the name of your new design. Make sure it matches the name you will use when you export the stl file.
  - If you go to the top of the file where is says this:
~~~lua
// Universal 3D Print Generator
// Choose which design to render by changing the 'design' parameter
// DESIGN SELECTOR - Change this value to select which design to render
design = "CavasDashboard"; // [
                                CavasDashboard,
                                CavasModules,
                                Copilot365Online,
                                desktop,
                                desktopStartMenu,
                                desktopAltTab,
                                desktopCopilot,
                                ExcelOnline,
                                FileExplorerDetails,
                                FileExplorerIcons,
                                GMailOnline,
                                GoogleDocOnline,
                                GoogleHome,
                                GoogleResults,
                                GoogleSheetsOnline,
                                GoogleSlidesOnline,
                                OfficeSplashPage,
                                OutlookOnline,
                                PPTOnline,
                                WebsiteWithHeadings,
                                WordOnline]
~~~
  - Add your new design name to the list of options in the comment. If you want it to immediately show your new design in the preview without you having to select it from tyhe dropdown change the `design` parameter from "CanvasDashboard" to "MYNEWDESIGN". For example:
~~~lua
// Universal 3D Print Generator
// Choose which design to render by changing the 'design' parameter
// DESIGN SELECTOR - Change this value to select which design to render
design = "CavasDashboard"; // [
                                CavasDashboard,
                                CavasModules,
                                Copilot365Online,
                                desktop,
                                desktopStartMenu,
                                desktopAltTab,
                                desktopCopilot,
                                ExcelOnline,
                                FileExplorerDetails,
                                FileExplorerIcons,
                                GMailOnline,
                                GoogleDocOnline,
                                GoogleHome,
                                GoogleResults,
                                GoogleSheetsOnline,
                                GoogleSlidesOnline,
                                OfficeSplashPage,
                                OutlookOnline,
                                PPTOnline,
                                WebsiteWithHeadings,
                                WordOnline,
                                MYNEWDESIGN]
~~~
- The cutomizer on the right of the screen will let you choose your new design from the dropdown menu.
- Click the Render button (or press `F6`) to generate the 3D model. Press `F6` to render the model
- Once the model is rendered, press `F7` to save the 3D model file as an stl file. Name the file according to your design (e.g., `MYNEWDESIGN.stl`) and save it in the `Final3dPrintFiles` folder.

If any of this is too difficult feel free to post a comment below and/or  [contact me](mailto:ryhunsaker@dsdmail.net?subject=Tactile%20Graphics%20For%20Screenreaders%20Question) and I can answer any questions directly.

{% include staticman-form.html %}
