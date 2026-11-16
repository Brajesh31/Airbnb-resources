# Installation and Local Preview

This guide explains how to obtain the repository and preview the current static page. There is no application installation step because the project has no package dependencies or compilation stage.

## 1. Requirements

Required:
- A modern browser such as a current version of Chrome, Firefox, Safari, or Edge.
- Git, if you want to clone the repository.

Recommended:
- Python 3 for a simple local HTTP server.
- A code editor that supports HTML and CSS syntax highlighting.
- A terminal opened at the repository root.

Not required:
- Node.js or npm.
- React, Vue, Angular, or another frontend framework.
- A database or backend runtime.
- An API key or environment configuration.
- A bundler, transpiler, or package manager.

The repository intentionally remains dependency-free. Do not run `npm install` unless a future, reviewed change introduces a package manifest.

## 2. Clone the repository

```bash
git clone https://github.com/Brajesh31/Airbnb-resources.git
cd Airbnb-resources
```

To confirm that you are in the correct directory:

```bash
git status
ls
```

The root should contain `index.html`, `airbnbstyle.css`, local image assets, and the repository documentation.

## 3. Start a local HTTP server

### Python

From the repository root:

```bash
python -m http.server 8000
```

Open [http://localhost:8000](http://localhost:8000) in your browser. Stop the server with `Ctrl+C`.

If the `python` command is unavailable, try:

```bash
python3 -m http.server 8000
```

### Node.js alternative

Node.js is not a project dependency. If it is already installed and you prefer an npm-based static server, use a temporary one without adding it to the repository:

```bash
npx --yes http-server . -p 8000
```

This command downloads and executes a tool through npx. It is optional and does not mean the project itself requires Node.js.

### Other static servers

Any server that serves the repository root and returns `index.html` for the root path is suitable. Keep the server's document root at the folder containing `index.html`.

## 4. Open the page directly

You can double-click `index.html` and open it with a browser. This is useful for a quick glance, but a local server is preferred. HTTP hosting more closely matches deployment behavior and makes it easier to inspect requests and missing files in the browser's Network panel.

## 5. Verify the preview

After the page loads:
1. Confirm the title and main page content appear.
2. Confirm the stylesheet is applied.
3. Confirm SVG, JPEG, and WebP assets load.
4. Resize the browser to narrow and wide widths.
5. Open Developer Tools and check Console and Network for errors.
6. Use Tab and Shift+Tab to inspect keyboard focus.
7. Confirm that controls which are only visual examples are not mistaken for working booking or search functionality.

## 6. Common setup problems

| Symptom | Likely cause | Action |
|---|---|---|
| Browser shows a directory listing | Server is not serving the expected root or index file | Start the server in the repository root |
| Page loads without styling | CSS path is wrong, file missing, or cached | Inspect the Network panel and stylesheet URL |
| Images return 404 | Filename case or relative path mismatch | Compare the HTML reference with the exact tracked filename |
| Port is already in use | Another process is listening on port 8000 | Use another port, such as 8080 |
| Changes do not appear | Browser cache or wrong local directory | Hard refresh and verify the current working directory |

To use another port:

```bash
python -m http.server 8080
```

Then visit `http://localhost:8080`.

## 7. No environment setup

The current project does not read environment variables. The `.env.example` file exists only to make that absence explicit. Do not create real credentials or secrets for this static page.

## 8. Uninstalling or cleaning up

The project does not install packages or create a local database. Stop the local server and delete the cloned directory if you no longer need it. If you used npx, its downloaded cache is managed by npm, not by this repository.

## 9. Next steps

After the page runs, read [Development](development.md), [HTML and CSS standards](html-css-style-guide.md), and [Browser testing](browser-testing.md) before making changes.
