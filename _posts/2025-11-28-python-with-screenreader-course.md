---
title: "Screenreader Accessible Python Course with VS Code for Education"
excerpt_separator: "<!--more-->"
date: 2025-11-28
categories:
  - blog
tags:
  - python
  - screenreader
  - instructional materials
  - coding
  - vscode
  - accessible education
comments: true
share: true
read_time: true
related: true
last_updates_at: 2025-11-30

---

Teaching Python to students who use screenreaders presents unique challenges. Traditional programming courses rely heavily on visual code formatting, graphical output, and GUI-based development environments that create barriers for blind and visually impaired learners. Many introductory computer science curricula include graphics libraries like turtle that are inaccessible to screenreader users, and online coding platforms often have terminal output that screenreaders cannot read effectively. Options that are available from the American Printing House for the Blind like Code Jumper bypass this using physical items or a rigorously predefined set of options that make it useful for learning concepts like for loops, while loops, and threading, but do not allow stduents to flexibly solve coding problems. 

To address this, I developed a screenreader-accessible Python curriculum using VS Code for Education. This course integrates foundational concepts from John Zelle's "Python Programming: An Introduction to Computer Science, 3rd Edition" (I used the 4th edition when writing it, but examples are fromt he 3rd edition since it is easier and a bit less expensive to obtain) with the practical, hands-on approach of Eric Matthes' "Python Crash Course, 3rd Edition." The curriculum focuses entirely on text-based output, console interaction, and carefully structured code that screenreaders can navigate efficiently. All graphical exercises have been replaced with text-based alternatives that teach the same programming concepts without visual dependencies.

The course is delivered through [VS Code for Education](https://vscodeedu.com/), a web-based learning platform that provides guided instruction with embedded code exercises. Students read the course content on the platform, but the course is specifically designed to be run locally in VS Code on their own computer because the VS Code for Education online terminal output is not reliably accessible to screenreaders. This hybrid approach gives students the structure of guided lessons while ensuring full accessibility when executing and debugging code. I prefer this over a typical LMS based system like CodeHS, Summit Learning, Canvas, Blackboard, etc -- all of which I have personally found to be insufficienrtly accessible and clunky when it comes to coding instruction.  

<!--more-->

## Why This Course Helps

- Eliminates visual dependencies found in traditional Python courses, replacing graphics-based exercises with text alternatives that teach identical programming concepts.
- Provides explicit instruction on Python indentation rules and strategies for managing whitespace with screenreaders, removing a major barrier for blind learners.
- Teaches screenreader-specific VS Code navigation patterns (accessible view, error navigation, terminal interaction) that students will use throughout their programming education.
- Uses real-world, console-based projects from Python Crash Course (games, data visualization with text output, web scraping) that mirror professional programming workflows.
- Addresses the terminal accessibility gap in online coding platforms by instructing students to run code locally while following web-based lessons.

## What Students Gain

- Practical Python skills applicable to data analysis, automation, web development, and scripting tasks commonly used by blind professionals.
- Confidence navigating code using screenreader keyboard commands, auditory feedback from error messages, and accessible debugging techniques.
- Understanding of fundamental computer science concepts (variables, loops, functions, classes, data structures) through accessible, hands-on practice.
- Experience with industry-standard tools (VS Code, Git, Python package management) configured for screenreader accessibility.
- A portfolio of text-based projects demonstrating programming competency without reliance on visual output.

## Features

The course is structured in modules that build progressively from basic Python syntax to more complex programming concepts. Each module includes text-based explanations, code examples formatted for screenreader navigation, and hands-on exercises that students complete in their local VS Code environment. The curriculum avoids all graphical libraries and instead uses console output, file manipulation, and text-based data processing to teach programming fundamentals.

The course emphasizes accessible coding practices throughout. Every lesson includes explicit discussion of Python indentation with strategies for managing spaces and tabs using screenreader feedback. Code examples include descriptive comments and docstrings that screenreaders announce clearly, and error messages are explained in detail so students learn to interpret Python tracebacks independently. The course teaches keyboard-driven navigation patterns specific to VS Code, including accessible view (`Shift+Alt+F2` on Windows/Linux, `Shift+Option+F2` on macOS) for reviewing code without distractions, and error navigation commands (`F8` and `Shift+F8`) for moving between problems in code.

The curriculum replaces visual exercises with text alternatives that preserve the learning objectives. Instead of turtle graphics for teaching loops and functions, students write text-based ASCII art generators and pattern printers. Instead of GUI-based games, students build console games like text adventures, word games, and number guessing games that use input/output and conditional logic. Data visualization exercises use CSV output and descriptive statistics rather than charts, teaching the same data analysis concepts through accessible formats.

The course integrates content from two complementary textbooks. Zelle's "Python Programming" provides the conceptual foundation with clear explanations of computer science principles, while Matthes' "Python Crash Course" supplies practical, project-based exercises. This combination gives students both theoretical understanding and applied skills. The course structure follows a hands-on learning model: students read concepts in short segments, then immediately practice by writing and running code locally in VS Code where terminal output is fully accessible.

## Classroom Use Cases

- **Computer Science Foundations for Blind Students**: Use this course as a complete introduction to programming for high school or college students who use screenreaders, covering the same core concepts as sighted peers through accessible exercises.
- **Transition-Age Technology Skills**: Teach employable programming skills to transition-age students, focusing on automation and data processing tasks that blind professionals use in workplace environments.
- **Accessible Coding Electives**: Offer this course as an elective in inclusive classrooms, allowing blind students to participate fully in coding education alongside sighted peers who use the same curriculum.
- **Self-Paced Learning for Adult Learners**: Provide this course to adult learners who are blind or visually impaired and want to develop programming skills for career advancement or personal projects.
- **Professional Development for Educators**: Use the course content to train teachers and technology specialists in accessible coding instruction, demonstrating practical techniques for teaching Python without visual dependencies.

## Teaching Tips

- **Set up VS Code accessibility features from day one**: Walk students through enabling screenreader mode, configuring accessible view, and testing terminal output before starting the curriculum to ensure smooth navigation throughout the course.
- **Teach indentation management explicitly**: Dedicate focused time to indentation practices, including how to verify spaces versus tabs using screenreader feedback, how to navigate by indentation level, and how to fix indentation errors.
- **Run all code locally, not in the web platform**: Instruct students to read lesson content on the VS Code for Education website, but always execute code in their local VS Code installation where terminal output is reliably accessible.
- **Emphasize error message literacy**: Teach students to read Python tracebacks systematically from bottom to top, locate the error type, find the line number, and interpret the error description, treating error messages as teaching tools rather than obstacles.
- **Use structured pair programming**: Pair blind and sighted students for collaborative coding sessions, assigning clear roles (driver and navigator) that leverage each student's strengths and foster inclusive learning.

## Getting Started

To access the course, visit the [VS Code for Education course link](https://vscode.dev/edu?courseId=df2f45f9-e840-409f-b2bc-7666056c961b&workspace-scheme=vscode-edu-workspace&profile=default-dark&otac=Nw6fcgCrrI&requestId=c557c64d-c807-459b-a4f9-64ca365f9acd&region=westus3#account-id=a89e44bc-d40b-42dc-a120-928bc125ab94). Note that this link works best in Chrome or Edge browsers; Firefox users may experience compatibility issues with the VS Code for Education platform. You will read the course lessons and instructions on this web platform, but you should always run the code exercises locally in your own VS Code installation to ensure accessible terminal output.

If you prefer to clone the course repository and work entirely offline, you can access the GitHub repository: [Intro to Coding with Python with a Screenreader](https://github.com/mrhunsaker/Intro-to-Coding-with-Python-with-a-Screenreader). The repository contains all course materials and can be imported into VS Code for Education (vscodeedu.com) if you want to use the platform's guided learning features with your local copy. This version does *NOT* open and play well in desktop vscode, so it has to be used when creating a course form a template in VS Code Edu. 

### Installations 

Before beginning the course, ensure you have the following tools installed on your local computer. Or, work with the student so that *they* install these along with you on their system, so they understand how to do so from the beginning:

- **Python 3** (latest stable version): Download from [Python.org](https://www.python.org/downloads/) or use WinGet in Windows 11, use Homebrew on macOS/Linux, or your relevant repository for Linux distributiosns (making sure to always install both `python3.xx` and `python3.xx-pip`). During installation on Windows 11, check the option to add Python to your system PATH so it can be run from the command line, this saves a **lot** of time and tinkering later on.
  - For added fun, you can download pyenv or pyenv-win and thsi lets you play with multiple versions of python. The installation scripts are pretty good
- **Visual Studio Code**: Download from [code.visualstudio.com](https://code.visualstudio.com/) or WinGet on Windows. VS Code has excellent built-in accessibility features and works well with NVDA, JAWS, and VoiceOver.
- **Screenreader**: NVDA (Windows, free), JAWS (Windows, commercial), you can use Windows Narrator (Windows, built-in), VoiceOver (macOS, built-in), or Orca (Linux, sometiems built in, sometimes not. Installable through the relevant linux repository).

### Recommended VS Code Extensions

Install these extensions in VS Code to enhance your Python development experience:

- **Python** (Official Microsoft extension): Provides IntelliSense, linting, debugging, and code formatting. Install by opening VS Code, pressing `Ctrl+Shift+X` (`Cmd+Shift+X` on macOS), searching for "Python," and clicking Install.

### Setting Up VS Code for Screenreader Use

When you first open VS Code, press `Alt` to activate the menu bar, then navigate to File > Preferences > Settings (or use `Ctrl+Comma`). Search for "screenreader" and ensure the screenreader mode is enabled. VS Code will detect most screenreaders automatically, but you can force this setting if needed. Always start the screenreader before entering VSCode if you rely on automatic detection.

### Learn these essential keyboard shortcuts for screenreader navigation in VS Code:

- **Accessible View**: `Shift+Alt+F2` (Windows/Linux) or `Shift+Option+F2` (macOS). Opens a simplified text view of the current file or terminal output that is easier for screenreaders to navigate.
- **Navigate Errors**: `F8` (next error) and `Shift+F8` (previous error). Moves the cursor to the next or previous error or warning in your code.
- **Open Terminal**: Ctrl+`  (backtick). Opens the integrated terminal where you will run Python code.
- **Run Python File**: Open the file you want to run, then use `Ctrl+Alt+N` if you have Code Runner installed, or open the terminal and type `python filename.py` (my preference for generalization across coding tools is to favor this latter option).

### Configuring Python Indentation

Python requires consistent indentation, typically four spaces per indentation level. Configure VS Code to use spaces instead of tabs: open Settings (`Ctrl+Comma`), search for "insert spaces," and ensure "Editor: Insert Spaces" is checked and "Editor: Tab Size" is set to 4. This ensures pressing `Tab` inserts four spaces, maintaining consistency that screenreaders report clearly.

To verify indentation in your code, place the cursor on a line and press `Ctrl+Shift+P` (`Cmd+Shift+P` on macOS) to open the command palette, then type "show whitespace" and select "View: Toggle Render Whitespace." This makes VS Code announce spaces and tabs explicitly when your screenreader reads the line, helping you confirm correct indentation. NVDA also has a function called "indent beep" that will play a series of ascending tones based on indent level.

### Run Your Code Locally

When you work through the course, follow this workflow:

1. Read the lesson content on the VS Code for Education website using your browser.
2. Open VS Code locally on your computer.
3. Create a new Python file (`Ctrl+N`, then `Ctrl+S` to save with a `.py` extension).
4. Type or copy the code from the lesson into your local file.
5. Run the code in your local terminal (Ctrl+` (backtick) to open terminal, then type `python filename.py`).
6. Read the output in the terminal using your screenreader's cursor review commands. If output is difficult to read, use accessible view (`Shift+Alt+F2`) to review it in a cleaner format.

This workflow ensures you have the full accessibility features of your local VS Code installation while following the structured lessons from the online course.

### Course Resources

The course integrates concepts and exercises from two textbooks:

- Matthes, E. (2023). *Python Crash Course: A Hands-On, Project-Based Introduction to Programming* (3rd ed.). No Starch Press. [Purchase from No Starch Press](https://nostarch.com/python-crash-course-3rd-edition)
- Zelle, J. M. (2017). *Python Programming: An Introduction to Computer Science* (3rd ed.). Franklin, Beedle & Associates. [Purchase from Franklin Beedle](https://fbeedle.com/our-books/23-python-programming-an-introduction-to-computer-science-3rd-ed-9781590282755.html)

You do not need to purchase these books to complete the course, as the curriculum includes all necessary content, but they provide valuable supplementary reading and additional practice exercises.

## Important Note About Terminal Accessibility

The VS Code for Education platform (vscode.dev/edu) displays course content and provides an integrated coding environment in your web browser. While this is convenient for reading lessons, the web-based terminal does not reliably output text that screenreaders can access. This is a limitation of the online platform, not a problem with screenreaders or VS Code itself.

To ensure full accessibility, always run your code locally in the VS Code desktop application installed on your computer. The desktop version has a fully accessible integrated terminal that works correctly with NVDA, JAWS, Windows Narrator, and VoiceOver (it is 85% accessible with Orca on Linux distributions). Use the web platform to read course instructions and view lesson content, but execute all code and review all terminal output in your local VS Code installation.

This hybrid approach gives you the structure of guided lessons while ensuring you can independently read program output, error messages, and debugging information—critical skills for successful programming.

## Customization and Contribution

This course is an open educational resource, and contributions are welcome. If you are an educator who has adapted the curriculum for your students, a screenreader user who has suggestions for improving accessibility, or a developer who wants to add additional exercises, please share your feedback. You can contribute by [submitting an issue on GitHub](https://github.com/mrhunsaker/Intro-to-Coding-with-Python-with-a-Screenreader/issues) describing your suggestions. YOu also can contact me with your GitHUb repo created by VS Code for Education and I can integrate any changes.

### Specific contributions that would extend the course's usefulness include:

- Additional text-based projects that teach advanced Python concepts (object-oriented programming, file handling, web scraping) without visual dependencies.
- Assessment rubrics for evaluating student progress in an accessible format.
- Lesson plans or teaching guides for instructors who are new to teaching programming to screenreader users.
- Translations or adaptations of the curriculum for different screenreaders or international accessibility standards.
- Examples of successful classroom implementations with blind or visually impaired students.

I am particularly interested in feedback from students and educators who use the course. If you encounter sections that are unclear, exercises that are difficult to complete with a screenreader, or features that would improve the learning experience, please let me know by opening an issue or leaving a comment below. Your input helps make programming education more accessible for all learners. I am planning on keeping this course updated as I use it every year or so to teach students who are blind/visually impaired programming skills, but by no means is this tool only intended for them, it is intended for anyone wanting to learn. 

## Leave a Comment

Note, I use [Remarkbox](https://www.remarkbox.com/) for comments to prevent Disqus from showing adds or other methods requiring a GitHub login for participation in any discussions. Although you are asked for you email, there is no need to verify it through remarkbox in order to leave a comment. Verification is just so you can track discussions, etc. without the system treating you as a new person every time.  

<!-- Remarkbox - Your readers want to communicate with you -->
<div id="remarkbox-div">
  <noscript>
    <iframe id=remarkbox-iframe src="https://my.remarkbox.com/embed?nojs=true&mode=light" style="height:600px;width:100%;border:none!important" tabindex=0></iframe>
  </noscript>
</div>
<script src="https://my.remarkbox.com/static/js/iframe-resizer/iframeResizer.min.js"></script>
<script>
  var rb_owner_key = "a11e8d2f-cd40-11f0-ad89-040140774501";
  var thread_uri = window.location.href;
  var thread_title = window.document.title;
  var thread_fragment = window.location.hash;

  // rb owner was here.
  var rb_src = "https://my.remarkbox.com/embed" +
      "?rb_owner_key=" + rb_owner_key +
      "&thread_title=" + encodeURI(thread_title) +
      "&thread_uri=" + encodeURIComponent(thread_uri) +
      "&mode=light" +
      thread_fragment;

  function create_remarkbox_iframe() {
    var ifrm = document.createElement("iframe");
    ifrm.setAttribute("id", "remarkbox-iframe");
    ifrm.setAttribute("scrolling", "no");
    ifrm.setAttribute("src", rb_src);
    ifrm.setAttribute("frameborder", "0");
    ifrm.setAttribute("tabindex", "0");
    ifrm.setAttribute("title", "Remarkbox");
    ifrm.style.width = "100%";
    document.getElementById("remarkbox-div").appendChild(ifrm);
  }
  create_remarkbox_iframe();
  iFrameResize(
    {
      checkOrigin: ["https://my.remarkbox.com"],
      inPageLinks: true,
      initCallback: function(e) {e.iFrameResizer.moveToAnchor(thread_fragment)}
    },
    document.getElementById("remarkbox-iframe")
  );
</script>