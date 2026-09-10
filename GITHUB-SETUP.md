# Publish your academic website on GitHub Pages

Prepared for Asma Hassannezhad · 9 September 2026

Your website is already built. It uses ordinary HTML pages, one CSS stylesheet and two lecture-note PDFs. Its academic design has a pale blue identity sidebar, deep blue headings, burgundy accents and compact publication lists. No installation, paid theme or command-line work is needed to publish these files.

This package is designed to be hosted directly on GitHub Pages. Follow the steps below to publish your public website.

## 1. Download and open the files

Download `Asma-Hassannezhad-Website.zip` and double-click it on your Mac to unzip it. Open the extracted `Asma-Hassannezhad-Website` folder. Double-click `index.html` to view your homepage in a browser. Research, Teaching and the PDF links also work locally.

Review your biography, recent papers and contact details. Teaching entries are explicitly labelled as past teaching because the original page only supplies dates through 2024.

## 2. Sign in to GitHub

Go to [GitHub](https://github.com/) and sign in, or create an account. Verify your email if GitHub asks. Make a note of your exact username; this is different from your displayed full name.

## 3. Create the website repository

A repository is the folder where GitHub stores your website and its editing history.

Choose **+ → New repository**. Select your own account as the owner. Name the repository `YOUR-USERNAME.github.io`, replacing `YOUR-USERNAME` with your actual GitHub username in lowercase. For example, if your username were `asma-example`, the repository would be `asma-example.github.io`. This example does not assume that username is yours or available.

Choose **Public**, turn **Add README** on, then select **Create repository**. Public repositories can use GitHub Pages on GitHub Free. If a repository with that name already contains your website, download a backup and use that existing repository rather than deleting it. [GitHub: creating a Pages site](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site).

## 4. Upload the website contents

In the repository, choose **Add file → Upload files**. Open the extracted website folder in Finder and drag its contents into GitHub's upload area. Include `index.html`, the `assets`, `research`, `teaching` and `wp-content` folders, and the Markdown instructions.

Upload the **contents**, not the ZIP or the outer `Asma-Hassannezhad-Website` folder. You should see `index.html` immediately when viewing the repository, rather than inside another folder. Choose **Commit changes** to save the upload to the `main` branch. GitHub may replace the initial README with the supplied README.

The package also contains a file named `.nojekyll`, which tells GitHub to serve the static files directly. Finder may hide it. If it was not uploaded, choose **Add file → Create new file**, enter `.nojekyll` as the name, put `Static website` in its contents and select **Commit changes**. Its contents do not matter.

## 5. Switch on GitHub Pages

Open the repository's **Settings**, then select **Pages** in the sidebar. Under **Build and deployment**, set **Source** to **Deploy from a branch**. Set the branch to **main** and the folder to **/(root)**, then select **Save**. [GitHub: configuring the publishing source](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site).

## 6. Open the public website

Return to **Settings → Pages** and use **Visit site** when it appears. The address will follow the pattern `https://YOUR-USERNAME.github.io/`. GitHub says publishing can take up to ten minutes. [GitHub: viewing your published site](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site#viewing-your-published-site).

Open Home, Research and Teaching on your computer and phone. Open both lecture-note PDFs, and check the email link. The navigation stays visible on small screens; the site includes keyboard focus indicators and a responsive layout.

## 7. Direct visitors from WordPress

Once the GitHub copy works, add a prominent link on your old WordPress homepage saying that your website has moved, with the new address. Update links on your Bristol profile, ORCID and other academic profiles when convenient.

Your `.wordpress.com` address remains managed by WordPress; publishing files on GitHub does not transfer that address. If you want visitors automatically redirected, WordPress offers a paid Site Redirect option. Check the current terms and setup instructions before buying it. [WordPress: Site Redirect](https://wordpress.com/support/domains/site-redirect/).

The new site keeps `/research/` and `/teaching/`, and includes copies of your existing image and PDF paths under `wp-content/uploads/2021/09/`. These help preserve incoming links if you later enable a redirect. Automatically generated WordPress attachment pages, comments and WordPress account features are not part of this static site.

## 8. Make future changes

For a small update, open the relevant file on GitHub and select the pencil icon to edit it. Change the text, then select **Commit changes**. GitHub Pages republishes automatically. [GitHub: editing files](https://docs.github.com/en/repositories/working-with-files/managing-files/editing-files).

| What you want to change | File to edit |
| --- | --- |
| Your title, biography and three featured papers | `index.html` |
| Full publication list | `research/index.html` |
| Courses, dates and mini-courses | `teaching/index.html` |
| Colours, fonts, spacing and mobile layout | `assets/style.css` |
| Lecture-note PDFs | Files inside `assets/notes/` |
| Your name, title, sidebar links or contact details | The corresponding section in all three HTML pages |

HTML comments mark the biography, publication and teaching sections. Edit the wording between the tags, keeping the tags intact. Use `&amp;` for an ampersand in HTML text. If you add a paper to the full list and want it featured on the homepage, update both pages.

To add a publication, copy an entire `<li class="paper"> ... </li>` entry in `research/index.html`. Replace its title, coauthors, journal information and links, then insert it in the correct section. A minimal entry looks like this:

```html
<li class="paper">
  <h3>Your paper title</h3>
  <p class="authors">With your coauthors</p>
  <p class="venue">Journal, volume, year and pages — or Preprint · year</p>
  <div class="paper-links">
    <a href="https://arxiv.org/abs/YOUR-ARXIV-ID">arXiv</a>
  </div>
</li>
```

Replace the example link with the real link before publishing. If there is no public paper link yet, omit the `paper-links` block. Add a PDF by uploading it inside `assets/notes/` and linking to it from the relevant HTML page. Keep PDF filenames short and avoid spaces.

## Keep the design professional

The design uses a pale blue identity sidebar, deep blue headings, thin dividing lines and burgundy accents. Keep the homepage brief and the full bibliography on Research. Use dated teaching entries and consistent journal details. A current publication list is more useful than a news section that becomes stale.

The main pages use typography and colour without a photograph. A separate collaborator directory is omitted; coauthors remain part of the bibliographic citations. Existing WordPress photographs are retained only at their old paths to help preserve incoming links.

To change colours or fonts, edit the variables at the beginning of `assets/style.css`. Keep sufficient contrast between text and the white background. The website needs no JavaScript, external fonts, theme subscription or build software.

A custom domain is optional. Start with your GitHub address; if you later purchase a domain, follow [GitHub's custom-domain instructions](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site). No domain purchase is needed to use the supplied site.

## If something does not work

| Symptom | What to check |
| --- | --- |
| A 404 error on the homepage | Repository spelling, `main` + `/(root)` in Pages settings, and `index.html` at the repository's top level. |
| No styling or missing PDFs | The `assets` folder must sit next to `index.html`; keep folder and filename capitalisation unchanged. |
| A paper or PDF link fails | Check that its link is complete and the uploaded filename matches exactly. |
| An edit has not appeared | Wait for the Pages deployment in the repository's Actions tab to finish, then refresh the browser. |
| Local editing damages the HTML | Use a plain-text or code editor; on a Mac, avoid saving HTML as a rich-text TextEdit document. GitHub's editor is the simplest option. |

For a public copy of this website inside an existing project repository instead, the same files use relative paths and can live at `https://YOUR-USERNAME.github.io/REPOSITORY/`. The personal `YOUR-USERNAME.github.io` repository gives you the shorter address recommended above.
