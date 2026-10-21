# Little Orbit

A colorful learning game for children ages 3–5, with counting, colors, shape recognition, and picture matching. Large touch targets, adjustable age levels, spoken prompts, and gentle five-round adventures.

## Publish to your existing GitHub repository

No build, package installation, API keys, or paid game services are required. The complete game is in `index.html`.

### 1. Add the files

Unzip the download first. Put the contents directly in your repository's root, alongside any existing README. Do not upload the ZIP itself, and do not place the game inside an extra `little-orbit-github` folder.

Required paths:

| Path | Purpose |
| --- | --- |
| `index.html` | Complete game, illustrations, styling, and JavaScript |
| `.github/workflows/deploy-pages.yml` | Publishes the game with GitHub Actions |
| `.nojekyll` | Supports static publishing if you later use branch deployment |
| `.gitignore` | Keeps temporary build and system files out of Git |
| `README.md` | These setup and maintenance instructions |

**Using the GitHub website:** Open the repository, select **Add file → Upload files**, add the extracted files, and commit them to your default branch. Check that `index.html` is visible at the repository root. The `.github` directory must also be included. Files and directories beginning with a dot can be hidden by your computer's file picker.

**If `.github` is missing after upload:** On GitHub, select **Add file → Create new file**. Enter `.github/workflows/deploy-pages.yml` as the filename. Open the matching file from this package in a text editor, paste its full contents into GitHub, and commit it. GitHub creates the folders from that path. You do not need to make any edits to the workflow.

**Using GitHub Desktop:** Clone your existing repository, copy all package contents into the local repository including `.github`, then commit and push. On macOS, Command + Shift + Period shows hidden files in Finder. Merge with an existing `.github` folder instead of replacing it. If your repository already has a homepage or deployment workflow, reconcile those files before replacing them.

### 2. Enable GitHub Pages

1. In the repository, open **Settings → Pages**.
2. Under **Build and deployment**, set **Source** to **GitHub Actions**.
3. This package already contains the workflow; do not create a second starter workflow.

GitHub Pages is available for public repositories on GitHub Free. Publishing from a private repository requires an eligible GitHub plan. If Pages is unavailable, check repository visibility, your plan, or organization restrictions.

### 3. Run the deployment

1. Open the repository's **Actions** tab.
2. Select **Publish Little Orbit**.
3. If the latest run succeeded, continue to step 4. If the initial run failed because Pages was not enabled yet, select **Run workflow**, choose the repository's default branch, and run it again. You can also rerun the failed run after enabling Pages.
4. Wait for the deployment to finish successfully. Open its **github-pages** environment link, or return to **Settings → Pages** and select **Visit site**.

The workflow automatically uses your repository's default branch. Future pushes to that branch redeploy the game. Pushes to other branches do not deploy.

### 4. Share your game URL

For a typical project repository, the address has this format:

`https://YOUR-USERNAME.github.io/YOUR-REPOSITORY/`

Replace the placeholders with your actual GitHub username and repository name. This is a format example, not an already published URL. The authoritative URL is shown by GitHub after deployment. A repository named `YOUR-USERNAME.github.io` normally publishes at the domain root instead.

## Simpler alternative: publish from a branch

If you prefer to avoid adding a workflow file, upload `index.html` and `.nojekyll` to the repository root. In **Settings → Pages**, choose **Deploy from a branch**, select your default branch and **/(root)**, then **Save**. Use this route instead of the custom workflow route above. Do not add the custom workflow for this option. GitHub will show the live URL after publishing.

## Local use

Open `index.html` in a modern browser. It also remains a standalone downloadable HTML game. The game assets require no network requests. Offline speech depends on voices available on the device and browser.

## Features and device behavior

- Star Counter: tap stars to count, then choose the total.
- Color Pop: select the requested color.
- Shape Explorer: match the requested shape.
- Memory Garden: uncover matching pictures.
- Age 3: 1–3 stars, two choices, two memory pairs.
- Age 4: 1–5 stars, three choices, three memory pairs.
- Age 5: 1–10 stars, four choices, four memory pairs.
- No timers, purchases, sign-in, external fonts, or third-party assets.
- Reduced-motion support and labeled controls.

Sound begins after interaction. Use the question speaker to repeat a prompt. Device/browser voices vary; an adult can read prompts when speech is unavailable. Layouts adapt to phones, tablets, and larger displays. Some mobile browsers may restrict direct local HTML file opening; the GitHub Pages URL provides browser access to the hosted game.

## Progress and privacy

The game sends no analytics or player information. It saves stars and settings in browser local storage when available. If storage is blocked, it plays with temporary session progress. Clearing browser data resets progress. Local file progress does not automatically transfer to the hosted URL or to another device. Hosting traffic is handled by GitHub under its own policies.

## Updating the game

Edit or replace `index.html`, commit, and push to your default branch. The workflow republishes it. No npm commands or build output are needed. No custom domain is configured by this package.

## Troubleshooting

| Symptom | Check |
| --- | --- |
| A README appears instead of the game | Confirm lowercase `index.html` is at the repository root, not inside an extra folder. |
| The URL returns 404 | Confirm a deployment completed and use the URL from Settings → Pages. Check repository eligibility and the exact repository path. |
| No workflow is listed | Confirm `.github/workflows/deploy-pages.yml` exists on the default branch and Actions is enabled. |
| Setup Pages fails | Set the Pages source to GitHub Actions, then rerun the workflow. |
| A run is skipped | Run it on the repository's default branch. |
| A deployment waits for approval | Check your repository's github-pages environment rules and approve the deployment if configured. |
| Your organization blocks an action | Ask the repository administrator to allow the official actions referenced by the workflow. |
| No spoken audio | Tap a game or the question speaker; check the sound toggle, device volume, and browser voice support. |
| Old content is shown | Confirm the latest deployment succeeded, then refresh or clear the page cache. |

## Verification

The original game logic passed 60 simulated rounds across every age level and activity, including retries, matching, session transitions, duplicate answers, and unavailable-storage fallback. This package preserves that HTML exactly under the filename `index.html`. The archive structure and workflow configuration were checked locally. The workflow has not been run in your repository; a live deployment and visual/touch/audio testing on your devices remain to be completed.

## GitHub references

- [Configure a publishing source](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)
- [Use custom workflows with GitHub Pages](https://docs.github.com/en/pages/getting-started-with-github-pages/using-custom-workflows-with-github-pages)
