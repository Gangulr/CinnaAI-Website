CinnaAI website  (plain HTML + CSS, no build step)

STRUCTURE
index.html, domain.html, milestones.html, documents.html, presentations.html, about.html, contact.html
css/style.css        all styling (colours are the variables at the top)
assets/images/       member and supervisor photos
assets/documents/    PUT YOUR DOCUMENT PDFs HERE
assets/slides/       PUT YOUR SLIDE PDFs HERE
vercel.json          makes PDFs open inline in the browser on Vercel

ADD A DOCUMENT (view + download for visitors)
1. Copy the PDF into assets/documents/ using the exact file name already in documents.html:
     project-charter.pdf, proposal-document.pdf, checklist.pdf, final-main.pdf,
     final-ranaweera1.pdf, final-wanasinghe1.pdf, final-samaraweera1.pdf
2. Open documents.html, find that document's  <article class="doc is-pending" ...>
   and delete the word  is-pending  (keep class="doc").
3. Save and redeploy. The card now shows "Available" with View, Download and an in-page Preview.
Slides work the same way: files go in assets/slides/ (proposal.pdf, progress-1.pdf, progress-2.pdf, final.pdf)
and you edit presentations.html.
To add a new document: copy one whole <article class="doc is-pending"> block, change the title and file name.

DEPLOY TO VERCEL
Option A (no tools): push this folder to a GitHub repo, then on vercel.com choose Add New > Project,
  import the repo, Framework Preset = Other, leave Build Command and Output Directory empty, Deploy.
Option B (CLI): install Node, run  npm i -g vercel  then, inside this folder, run  vercel --prod
Every time you add a PDF, redeploy (git push, or run vercel --prod again).

NOTES
- Compress big PDFs first (the PP1 deck is about 61 MB). Small PDFs load and preview much faster.
- Fonts come from Google Fonts and fall back to system fonts if offline. If your course site forbids
  external links, delete the three <link ...fonts...> lines in each HTML file.
- Search all files for "To be added", "example.com", "+94 00" and replace with real details.
