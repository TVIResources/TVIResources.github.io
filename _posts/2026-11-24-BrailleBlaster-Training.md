---
title: "BrailleBlaster Training""
date: 2026-11-24
categories:
  - blog
tags:
  - 3d printing
  - braille
  - instructional materials
  - inkscape
  - openscad
search: exclude
comments: true

---

# BrailleBlaster v3 Training

A hands-on curriculum for learning **BrailleBlaster**, the free, open-source braille transcription program from the American Printing House for the Blind (APH). It is written for teachers of students with visual impairments, paraeducators, braille transcribers, and the trainers who teach them.

**Read the book online:** <https://mrhunsaker.github.io/BrailleBlaster_Training>

## What is in the book

- **32 lessons** in four units: Universal (1 to 13), Advanced (14 to 19), Transcriber-Focused (20 to 24), and Specialized Content (25 to 32)
- **9 labs** that use real sample files, and a **drill bank** with answer keys
- Every lesson has objectives, a concept section, step-by-step menu paths, a worked demonstration, a practice document, and an answer key, with citations to *Braille Formats 2016*
- A **capstone** transcription project with a scoring rubric
- An **Instructor Guide** with pacing plans, teaching notes, and assessment guidance
- **Reference** pages: shortcuts, glossary, troubleshooting, and resources

About 69 hours of material including Unit 4 and the capstone. Pacing plans for a twelve-week course, a five-day intensive, a one-day workshop, and self-paced study are on the Syllabus page.

## Repository layout

```text
.
├── README.md
├── mdbook_generate.sh / .ps1   Build helpers
├── version.json                Book version
├── my-book/
│   ├── book.toml               mdBook configuration
│   ├── src/                    The editable manuscript
│   │   ├── SUMMARY.md          Table of contents
│   │   ├── README.md           Book introduction
│   │   ├── start/              How to use, setup, syllabus
│   │   ├── units/              Unit overviews and checkpoints
│   │   ├── lessons/            Lessons 1 to 32
│   │   ├── labs/               Nine integrated labs
│   │   ├── samples/            Practice files (generated)
│   │   ├── capstone/
│   │   ├── instructor/         Teaching notes, session plans, assessment
│   │   ├── reference/          Shortcuts, drills, job aids, glossary, and more
│   │   └── about/
│   └── theme/                  Custom mdBook theme
├── tools/                      build_samples.py, check_book.py, instructor_expansion.py
├── AddlFiles/                  Earlier source drafts (see AddlFiles/README.md)
├── CURRICULUM_REVIEW.md        Editorial notes for maintainers
├── VERIFICATION.md             What has and has not been checked
├── PROFESSIONALIZATION_ROADMAP.md  What the curriculum needs next
├── CONTRIBUTING.md, CHANGELOG.md, CITATION.cff
```

`my-book/docs` is generated output and is not committed.

## Building the book

Install mdBook (version 0.5 or later is recommended, because the custom theme uses features from recent releases):

```bash
cargo install mdbook --locked
```

Then build from the repository root:

```bash
bash mdbook_generate.sh        # Linux or macOS
.\mdbook_generate.ps1          # Windows PowerShell
```

or directly:

```bash
cd my-book
mdbook build       # writes my-book/docs/html and my-book/docs/markdown
mdbook serve       # live preview at http://localhost:3000
```

GitHub Actions builds and deploys the site to GitHub Pages on every push to `main` (`.github/workflows/deploy.yml`) and attaches the Markdown output to tagged releases.

## Quality checks

```bash
python3 tools/check_book.py     # links, anchors, headings, lesson structure, sample files
python3 tools/build_samples.py  # regenerate the practice files
```

GitHub Actions runs the checks on every pull request (`.github/workflows/quality.yml`).

## Editing guidance

- Edit files in `my-book/src`. Never edit `my-book/docs`.
- Follow the lesson pattern: Lesson at a glance, Learning objectives, Why this matters, How to use this lesson, The Concept, Step by step, Worked Demonstration, Practice Document, Answer Key, Key takeaways, Source Citations.
- Use **bold** menu paths with `>` (for example **File > Open**) and code style for shortcuts.
- Each Markdown file has exactly one `#` heading.
- Cite *Braille Formats 2016* sections where a rule is stated, and verify menu paths against the current BrailleBlaster documentation.
- When you add or rename a lesson, update `my-book/src/SUMMARY.md`, the unit page, the Syllabus table, and the shortcuts "Where tools live" table.

## Versioning

Version information is in `version.json`.

## Credits and license

Written by Michael Ryan Hunsaker, M.Ed., Ph.D. Released under the Apache License 2.0. See `LICENSE`.

BrailleBlaster is developed by the American Printing House for the Blind and released under the GNU Public License v3. This is an independent training resource and is not an official APH publication.


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