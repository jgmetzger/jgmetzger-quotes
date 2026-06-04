# jgmetzger. — proposals

Static site hosted on **GitHub Pages**, served at the custom domain
**[quotes.jgmetzger.com](https://quotes.jgmetzger.com)**.

Each client proposal lives in its own top-level folder and is served at
`quotes.jgmetzger.com/<Folder-Name>/`. The root `index.html` is a simple
index that links to the active proposals.

## Structure

```
/
├─ index.html            # brand index — wordmark + list of active proposals
├─ CNAME                 # custom domain: quotes.jgmetzger.com
├─ .nojekyll             # tell GitHub Pages to serve every file verbatim
├─ README.md
└─ Fabrizio-Book/        # first proposal → /Fabrizio-Book/
   ├─ index.html         # the proposal (Fabrizio-Launch-Proposal.html)
   └─ landing/
      └─ index.html      # linked demo (Fabrizio-landing-page.html) → /Fabrizio-Book/landing/
```

## Add a new proposal

1. Create a new **top-level folder**, e.g. `Acme-Rebrand/`.
2. Drop the proposal in as `Acme-Rebrand/index.html`. It will be served at
   `quotes.jgmetzger.com/Acme-Rebrand/`.
3. (Optional) Add nested demos as their own folders with an `index.html`,
   e.g. `Acme-Rebrand/landing/index.html` → `/Acme-Rebrand/landing/`. Link to
   them from the proposal with a **relative** path like `./landing/`.
4. Add a link to the new folder in the root `index.html` (in the
   `<ul class="proposals">` list).

> Folders are served as directories, so always name the entry file
> `index.html`. Because of `.nojekyll`, files and folders are published
> exactly as committed (no Jekyll processing).

## Deploy

Deployment is just **commit and push to `main`**. GitHub Pages rebuilds
automatically (usually live within a minute or two).

```bash
git add .
git commit -m "Update proposals"
git push origin main
```

## Brand tokens

Used by the root `index.html`:

| Token        | Value     |
|--------------|-----------|
| Background   | `#0a0a0b` |
| Text         | `#f2f0ed` |
| Accent       | `#7c5cfc` |

Fonts: **Outfit** (sans), **Cormorant Garamond** (italic emphasis),
**JetBrains Mono** (labels).
