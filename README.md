# minagrandolfo.github.io

Personal academic site for Giacomina (Mina) Grandolfo: PhD candidate in
Cognitive Neuroscience at Université Libre de Bruxelles (CRCN).

Live at: https://minagrandolfo.github.io

## Structure

```
minagrandolfo.github.io/
├── index.html            # Main page: edit the text content here
├── generic.html          # Optional internal page (not linked yet)
├── elements.html         # Reference catalogue of all Hyperspace components
├── assets/
│   ├── css/
│   │   ├── main.css      # Hyperspace base styles (do not edit)
│   │   └── custom.css    # Mina's overrides: colours, typography, layout
│   ├── sass/             # SASS sources (only needed if recompiling main.css)
│   ├── js/               # jQuery + Hyperspace scripts
│   ├── webfonts/         # Font Awesome icons
│   └── pdf/              # CV, thesis, essays (PDFs)
├── images/               # Hero photo and any inline images
└── README.md             # This file
```

## How to edit content

**Text content (publications, conferences, bio, etc.):**

Open `index.html` in any text editor (VS Code, Notepad++, etc.).
The file is divided into clear commented sections:

```html
<!-- Intro / Hero -->
<!-- Research -->
<!-- Publications -->
<!-- Conferences -->
<!-- Methods & Tools -->
<!-- Contact -->
```

Find the section you want to update and edit the text between the HTML tags.

### Adding a new publication

Inside the `<ul class="pub-list">` of the relevant subsection, add a new
`<li>` item, following the existing format:

```html
<li>
    <strong>Grandolfo, G.</strong>, Coauthor, A. (YYYY).
    Title of the paper.
    <span class="venue">Journal name.</span>
    <a href="assets/pdf/filename.pdf" class="pdf-link">[PDF]</a>
</li>
```

### Adding a new conference

Inside `<ul class="conf-list">`:

```html
<li><strong>CONFERENCE NAME</strong> &middot; Location &middot; Date
    <span class="conf-type">Poster / Oral</span>
    <br /><em>Title of the contribution.</em>
</li>
```

## How to change colours

All colours are centralised in `assets/css/custom.css` at the top of the
file. The variable-like comments near the top tell you what each colour does.
Search and replace to change them site-wide:

- Mauve primary: `#6F54CA`
- Pink gradient terminus: `#E35BA5`
- Ink (text): `#1a1a1a`
- Paper (background): `#ffffff`

## How to replace the hero photo

Save your new photo as `images/mina_portrait.jpg`. The site expects a square
image (1000 × 1000 px ideal). The site automatically converts it to black
and white with `filter: grayscale(100%)` in CSS: you don't need to preprocess.

To change the size or shape, edit `.hero-photo` in `custom.css`.

## How to deploy changes to the live site

Once the site is pushed to GitHub (see deployment section below), any commit
to the `main` branch will automatically rebuild the live site within 1-2 minutes.

```bash
git add -A
git commit -m "Update publications"
git push
```

## First-time deployment (one-off)

This repository is served via **GitHub Pages**. The repository must be named
`minagrandolfo.github.io` exactly (matches the GitHub username).

### Setup (only done once)

1. Create the repo on GitHub: https://github.com/new
   - Name: `minagrandolfo.github.io`
   - Visibility: Public
   - Do NOT initialise with README / .gitignore / license (keep empty)

2. In this local folder, run:

```bash
git init
git branch -M main
git add -A
git commit -m "Initial commit: Hyperspace site scaffold with content"
git remote add origin https://github.com/minagrandolfo/minagrandolfo.github.io.git
git push -u origin main
```

3. On GitHub, go to Settings → Pages. Confirm that the source is set to
   `Deploy from a branch`, branch `main`, folder `/ (root)`.

4. Wait 1-2 minutes. The site goes live at https://minagrandolfo.github.io

## Credits

- Template: [Hyperspace](https://html5up.net/hyperspace) by HTML5 UP (CCA 3.0).
- Custom overrides in `assets/css/custom.css` for colour palette and typography.
