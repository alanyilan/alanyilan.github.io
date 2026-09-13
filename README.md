# Alan Xu — personal site

Plain HTML and CSS. No build step, no framework, no dependencies. You edit a file,
you upload it, it's live. It will still work in ten years, and it will run on any
host you ever move it to.

## Three things to add before you publish

The site references three files that aren't here yet. Add them and everything works.

1. `files/Alan_Xu_CV.pdf` — download the PDF from Google Drive and drop it in the
   `files/` folder. Keep the filename exactly as written, or update the link in
   `cv.html`.
2. `images/enumerator.jpg` — the undergraduate enumerator photo from your Stuff page.
3. `images/lake-erie-2019.jpg` — the Lake Erie beach survey photo.

Resize the photos to about 1200px on the long edge and save at ~75% JPEG quality.
They'll drop to roughly 150KB each, which matters on a slow connection.

## Publishing on GitHub Pages

1. Create a GitHub account if you don't have one.
2. Create a new **public** repository named `yourusername.github.io` — the name
   matters, it's what makes Pages serve it at the root.
3. Upload every file in this folder using the web uploader. No command line needed:
   **Add file → Upload files**, drag the whole folder in, commit.
4. Go to **Settings → Pages**, set the source to the `main` branch, root folder.
5. Two minutes later you're live at `https://yourusername.github.io`.

To edit later: open any `.html` file on GitHub, click the pencil icon, change the
text, commit. That editor works from mainland China, which the Google Sites editor
does not.

## Getting your own domain

Worth the roughly $12 a year. Buy `alanxu.com` or similar from Cloudflare Registrar
or Porkbun, then in your repo add a file named `CNAME` containing just your domain
on one line, and point the domain's DNS at GitHub Pages. GitHub's docs walk through
the exact records.

The reason to do this: your address stops depending on your host. When you outgrow
GitHub Pages, or GitHub changes its terms, you move the files and nothing breaks.
Every paper that cites your site, every application that lists it, keeps working.
That's the failure you're recovering from right now.

## About the syllabus links

The syllabus links on the Teaching page still point at Google Drive, so they work
today but will not open in mainland China. To fix that, put the PDFs in `files/`
and change each link from the long Drive URL to something like
`files/AGRI-860-syllabus.pdf`. Same fix, better result: the files load faster
everywhere and won't break when Drive sharing permissions drift.

## Editing

Each page repeats its own navigation menu. That's the trade-off for having no build
step — if you add a sixth page, add one `<li>` line to the menu in all five existing
files. Search for `class="nav"` to find it.

Colors and type live at the top of `style.css` under `:root`. Change a hex value
there and it updates everywhere.

## What was deliberately left out

No Google Fonts, no Font Awesome, no jQuery, no analytics, no cookie banner. Every
one of those is a request to a server that may not answer, and a site that hangs
half-loaded is worse than a plain one. If you later want visitor statistics, use
your host's own logs rather than a third-party script.
