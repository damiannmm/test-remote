---
layout: post
title:  "Test Embed!"
date:   2021-05-18 20:37:26 +0700
---

<script type="text/javascript" language="javascript">
  // Get the first iframe element
  const iframe = document.querySelector('iframe');
  
  // Browser will block the attempt to access iframe.contentWindow.document due to https://app.miniextensions.com doesn't allow CORS from https://damiannmm.github.io/
  const iframeDocument = iframe.contentWindow.document;
 
  // Theoretically these two solutions will work if we omit the CORS issue
  
  // #1 by modifying element.style.display directly
  const nameFields = iframeDocument.querySelectorAll('.FieldHeader_containerClassName__1V-2b');
  nameFields.forEach(field => {
    field.style.display = 'none';
  });

  // #2 by injecting the css file
  
  const linkEl = document.createElement('link');
  linkEl.href = 'path/to/style.css'; 
  linkEl.rel = 'stylesheet'; 
  linkEl.type = 'text/css'; 
  iframeDocument.head.appendChild(cssLink);
  
  // Even if we're able to modify the style inside the iframe, it's not going to sustain because the class name seems to be
  // auto-generated on every build (see the dynamically generated "__1V-2b")
</script>

<div id="miniextensions-iframe-embed-NIlPspVaQJUKFhdmoGhx"></div>

<script src="https://api.miniextensions.com/v1/iframe-embed/NIlPspVaQJUKFhdmoGhx.js?absoluteShareUrl=https%3A%2F%2Fapp.miniextensions.com%2Fcards-gallery%2FNIlPspVaQJUKFhdmoGhx"></script>
