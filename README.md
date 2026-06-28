<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>GitHub Profile README Redesign - Preview</title>
  
  <!-- GitHub Markdown CSS -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/github-markdown-css/5.2.0/github-markdown-5.2.0.min.css" integrity="sha512-7M9iJ4cWc/C4U7qB7V3Y0X1aMceG9oMypEsgpFi8Nn5G/9v4Jq02X96UuN7JbM2p0qgA0k7R1c51q8H9z7R1Fw==" crossorigin="anonymous" referrerpolicy="no-referrer" />
  
  <!-- Marked.js Markdown Parser -->
  <script src="https://cdn.jsdelivr.net/npm/marked/marked.min.js"></script>
  
  <style>
    :root {
      --bg-gradient: linear-gradient(135deg, #0f172a 0%, #020617 100%);
      --accent-color: #00f7ff;
    }
    
    body {
      margin: 0;
      padding: 0;
      background: var(--bg-gradient);
      color: #e2e8f0;
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Helvetica, Arial, sans-serif;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      align-items: center;
    }
    
    header {
      width: 100%;
      max-width: 1000px;
      padding: 2rem 1rem 1rem 1rem;
      box-sizing: border-box;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }
    
    .badge {
      background: rgba(0, 247, 255, 0.1);
      border: 1px solid rgba(0, 247, 255, 0.2);
      color: var(--accent-color);
      padding: 0.35rem 0.75rem;
      border-radius: 9999px;
      font-size: 0.85rem;
      font-weight: 600;
    }
    
    main {
      width: 100%;
      max-width: 1000px;
      padding: 1rem;
      box-sizing: border-box;
      margin-bottom: 4rem;
    }
    
    .preview-card {
      background: rgba(15, 23, 42, 0.6);
      backdrop-filter: blur(12px);
      border: 1px solid rgba(255, 255, 255, 0.08);
      border-radius: 16px;
      padding: 2.5rem;
      box-shadow: 0 20px 40px rgba(0, 0, 0, 0.4);
    }
    
    /* Override GitHub dark theme background to match our glass card */
    .markdown-body {
      background-color: transparent !important;
      color: #e2e8f0 !important;
    }
    
    .markdown-body table {
      display: table;
      width: 100%;
      background: transparent;
      border-collapse: collapse;
      margin-top: 1rem;
      margin-bottom: 1rem;
    }
    
    .markdown-body table tr,
    .markdown-body table th,
    .markdown-body table td {
      background: transparent !important;
      border: none !important;
    }

    .markdown-body table td {
      padding: 12px !important;
    }
    
    .markdown-body h2 {
      border-bottom: 1px solid rgba(255, 255, 255, 0.1) !important;
      padding-bottom: 0.3em;
    }
    
    .markdown-body hr {
      background-color: rgba(255, 255, 255, 0.1) !important;
      height: 1px !important;
    }
    
    .instructions {
      max-width: 1000px;
      width: calc(100% - 2rem);
      background: rgba(255, 255, 255, 0.03);
      border: 1px dashed rgba(255, 255, 255, 0.15);
      border-radius: 12px;
      padding: 1.5rem;
      margin-bottom: 2rem;
      box-sizing: border-box;
    }
    
    .instructions h3 {
      margin-top: 0;
      color: #38bdf8;
    }
    
    .instructions ol {
      margin: 0;
      padding-left: 1.2rem;
      color: #94a3b8;
      line-height: 1.6;
    }
    
    .instructions code {
      background: rgba(255, 255, 255, 0.1);
      padding: 0.2rem 0.4rem;
      border-radius: 4px;
      color: #f1f5f9;
      font-size: 0.9em;
    }
  </style>
</head>
<body class="markdown-body-dark">

  <header>
    <div>
      <h1 style="margin: 0; font-size: 1.75rem; font-weight: 700; color: #fff;">Atri Mandal</h1>
      <p style="margin: 0.25rem 0 0 0; color: #94a3b8;">GitHub Profile README Redesign</p>
    </div>
    <span class="badge">Modern & Elegant Layout</span>
  </header>

  <main>
    <div class="instructions">
      <h3>🚀 How to use this redesign</h3>
      <ol>
        <li>Open the generated file <a href="file:///c:/laragon/www/README_redesign.md" style="color: #38bdf8; text-decoration: underline;">README_redesign.md</a> in VS Code.</li>
        <li>Copy the entire content of that file (<code>Ctrl+A</code> then <code>Ctrl+C</code>).</li>
        <li>Go to your GitHub profile repository edit page (which you currently have open in Chrome as seen in your screenshot: <code>https://github.com/Atriman123/Atriman123/edit/main/README.md</code>).</li>
        <li>Replace all of the current content with this new content and click <strong>Commit changes...</strong></li>
      </ol>
    </div>

    <div class="preview-card">
      <div id="readme-content" class="markdown-body">
        <p>Loading preview...</p>
      </div>
    </div>
  </main>

  <script>
    // Fetch and render the local markdown file
    fetch('README_redesign.md')
      .then(response => response.text())
      .then(markdownText => {
        // Set marked.js options
        marked.setOptions({
          gfm: true,
          breaks: true
        });
        
        document.getElementById('readme-content').innerHTML = marked.parse(markdownText);
      })
      .catch(error => {
        document.getElementById('readme-content').innerHTML = `
          <p style="color: #ef4444;">Error loading README_redesign.md: ${error.message}</p>
          <p>Make sure you are running a local server or that the file path is accessible.</p>
        `;
      });
  </script>
</body>
</html>
