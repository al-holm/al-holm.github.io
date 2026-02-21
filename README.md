# Alina Kholmovaia — personal site

Dark, vaguely medieval.

## Structure

```
site/
├── index.html          ← main page (about, writing list, cv, links)
├── style.css           ← shared styles
├── posts/
│   ├── _template.html  ← copy this to make a new post
│   └── one-mask.html   ← first post
└── README.md
```

## How to add a new post

Two steps:

### 1. Create the post file

Copy `posts/_template.html` and rename it, e.g. `posts/my-new-post.html`.
Open it and fill in:
- The `<title>` tag
- The date, title, and tags in the post header
- Your content in the `<div class="post-body">` section

You can use:
- `<p>` for paragraphs
- `<h2>` for subheadings
- `<code>` for inline code, `<pre><code>` for code blocks
- `<blockquote>` for quotes
- `<a href="...">` for links
- `<img src="...">` for images

### 2. Add a link on the homepage

Open `index.html`, find the Writing section, and add an entry above the existing ones:

```html
<div class="entry">
  <a href="posts/my-new-post.html">
    <div class="entry-date">Mar 5, 2026</div>
    <div class="entry-title">Your Title Here</div>
    <p class="entry-excerpt">One or two sentences about it.</p>
    <span class="tag">some-tag</span>
  </a>
</div>
```

Newest posts go on top. That's it.

## How to add creature icons

Replace any `<div class="icon-placeholder">icon</div>` with:

```html
<img src="images/your-creature.png" alt="creature">
```

Put your images in an `images/` folder (or wherever you want, just match the path).

## Deploy to GitHub Pages

1. Create a new repo on GitHub (e.g. `my-site` or `yourusername.github.io`)
2. Push this folder:

```bash
cd site
git init
git add .
git commit -m "first entry"
git remote add origin git@github.com:YOURUSERNAME/REPONAME.git
git push -u origin main
```

3. Go to repo **Settings → Pages**
4. Under "Source", pick **Deploy from a branch** → **main** → **/ (root)**
5. Hit Save

Your site will be live at `https://YOURUSERNAME.github.io/REPONAME/` within a minute or two.

If you name the repo `yourusername.github.io`, it'll be at `https://yourusername.github.io/` directly.

## Custom domain (optional)

If you buy a domain:
1. Add a file called `CNAME` containing just your domain (e.g. `ali.cool`)
2. Point your domain's DNS to GitHub Pages (their docs explain this)
