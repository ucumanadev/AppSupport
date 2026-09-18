# App Support

A standalone, dependency-free static website for public support and legal information for mobile apps. It is designed to work on GitHub Pages project sites, including repositories served from `https://USERNAME.github.io/REPOSITORY/`.

## Structure

```text
/
├── index.html                 # App directory / landing page
├── styles.css                 # Shared responsive styles
├── lucy/
│   ├── index.html             # Lucy overview
│   ├── support/index.html
│   ├── privacy/index.html
│   └── terms/index.html
└── README.md
```

All links are relative. No custom-domain or root-path assumption is required.

## Preview locally

Because browsers restrict some behavior for `file://` URLs, use a small local static server. From this directory, run one of these commands if available:

```bash
python3 -m http.server 8000
```

Then visit `http://localhost:8000/`. Stop the server with `Ctrl+C`.

## Add another app

1. Create a new app directory, such as `new-app/`.
2. Add `index.html`, `support/index.html`, `privacy/index.html`, and `terms/index.html` using the Lucy pages as a starting structure.
3. Update relative stylesheet paths based on page depth (`../styles.css` for an app overview and `../../styles.css` for nested pages).
4. Add the app card and links to the root `index.html`.
5. Keep each app’s facts, SDKs, permissions, and legal content specific to that app.

## Deploy with GitHub Pages

1. Create a GitHub repository and upload or commit this project.
2. In the repository, open **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**.
4. Choose the branch containing this project (usually `main`) and the `/ (root)` folder, then select **Save**.
5. Wait for the deployment to finish. GitHub will show the project-site URL under the Pages settings.
6. Open the published URL and click through every navigation and legal link on desktop and mobile widths.

## Before adding future apps

When adding another app, search the new app pages for `[TODO]` placeholders and complete them before publishing. Confirm that each app’s policies match its production behavior, SDK configuration, store disclosures, and legal review requirements.
