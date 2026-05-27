---
title: "3DMake GUI — VS Code Extension: Accessible 3D Modeling in Your Editor"
excerpt_separator: "<!--more-->"
date: 2026-05-27
categories:
  - blog
tags: [3dmake, VS Code, extension, education, accessibility]
search: include
---

# 3DMake GUI — VS Code Extension: Accessible 3D Modeling in Your Editor



3D modeling should be accessible to all students, including those using screen readers or keyboard navigation. The 3DMake GUI VS Code Extension brings the full power of the `3dm` workflow into Visual Studio Code, making it easy for teachers and students to build, preview, and export 3D models without leaving their editor.

<!--more-->

## Why the VS Code Extension helps

- Integrates accessible 3D modeling directly into the classroom’s preferred code editor.
- Eliminates the need for terminal commands or inaccessible GUIs.
- Provides keyboard shortcuts and screen reader support for all features.
- Enables students to work independently and efficiently.

## What students gain

- Mastery of 3D modeling workflows in a familiar environment.
- Confidence using professional tools with full accessibility.
- Ability to preview, build, and export models without barriers.
- Experience with collaborative, real-world design projects.

## Features

- Wraps every `3dm` subcommand in VS Code’s native UI.
- Tree views for project files, command options, quick actions, and settings.
- Output Channel with live, accessible feedback.
- Keyboard shortcuts for all major actions.
- Built-in STL and SVG viewers with keyboard navigation.
- OpenSCAD syntax highlighting for `.scad` files.
- Configurable binary path and project settings.

## Classroom use cases

- Assign 3D modeling projects that students complete entirely in VS Code.
- Use the Output Channel and viewers for real-time feedback during lessons.
- Support blind and low-vision students in collaborative design challenges.
- Enable quick troubleshooting and review of student work.
- Integrate 3D modeling into coding and STEM curricula.

## Teaching tips

- Demonstrate keyboard shortcuts and tree view navigation at the start.
- Encourage students to use the Quick Actions for common tasks.
- Use the Output Channel to review command results as a class.
- Assign projects that require both editing and previewing models.
- Remind students to check the STL and SVG viewers for model accuracy.

## Getting Started

1. Install the extension from a `.vsix` file or the Marketplace.
2. Open the 3DMake panel in the Activity Bar.
3. Select a project file or directory.
4. Use Quick Actions or keyboard shortcuts to build, preview, and export models.

See the [full documentation](https://github.com/mrhunsaker/3dmakeGUI) for details.

## Customization and contribution

Contribute by:

- Sharing lesson plans or classroom workflows.
- Suggesting new features or accessibility improvements.
- Reporting issues or submitting pull requests on [GitHub](https://github.com/mrhunsaker/3dmakeGUI).
- Creating custom templates or export scripts for classroom use.

We invite teachers, students, and developers to collaborate and make 3D modeling accessible for all learners.

---

Let me know if you want these as files or need further customization!

## Leave a Comment

Note, I use [Remarkbox](https://www.remarkbox.com/) for comments to prevent Disqus from showing ads or other methods requiring a GitHub login for participation in any discussions. Although you are asked for you email, there is no need to verify it through remarkbox in order to leave a comment. Verification is just so you can track discussions, etc. without the system treating you as a new person every time.  

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