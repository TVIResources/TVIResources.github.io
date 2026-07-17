---
title: "Accessibility Project Manager"
date: 2026-07-16
categories:
  - blog
tags:
  - braille
  - instructional materials
  - organization
search: include
comments: true

---

As a teacher managing multiple accessibility production workflows, I need tools that consolidate disparate processes without adding complexity. The Accessibility Project Management (APM) (https://github.com/mrhunsaker/AccessibilityProjectManagement) application does exactly that—it's a NiceGUI-based local web application that manages braille transcription, tactile graphics, 3-D printing jobs, and more, all backed by SQLite and running entirely on-premises.                                                  
     
From a technical perspective, what makes APM stand out is its integrated approach to accessibility workflows. Instead of juggling  separate spreadsheets, file folders, and tracking systems for braille jobs, 3-D prints, and tactile graphics, everything lives in one place with full metadata support (Dublin Core, PREMIS, METS), file ingestion with SHA-256 checksums, and provenance tracking. For teams producing braille tracking materials, spatial vocabulary models, or STEM tactile aids, this means a single source of truth for job status, inventory levels, and delivery records.                                                   

I built this system with local-first deployment as a core requirement. APM runs as a standalone executable via PyInstaller, in a Podman container, or directly from source—no cloud account, no external service dependency, and no student data leaving the district network. The inventory module tracks filament by brand, color, type, and cost, with low-stock warnings that prevent the mid-lesson discovery that you're out of PLA. For braille production, it manages paper types, embosser configurations, and step-level file attachments throughout the workflow.                                                               
For blind and low-vision educators, this is not just a convenience feature. It is an equity feature. APM's role-based access control (administrator, operator, reviewer) combined with its browser-only interface means it works with screen readers out of the box, and the self-hosted model ensures that accessibility teams maintain full control over their production data. The QA integration with tools like DAISY Ace, EPUBCheck, and Liblouis means validation happens within the same interface where jobs are managed, reducing context-switching and making independent workflow management realistic. That is why I encourage other teachers of students with visual impairments to evaluate this tool: it is technically sound, instructionally practical, and designed so that the people creating accessible materials can manage the entire process themselves.    

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