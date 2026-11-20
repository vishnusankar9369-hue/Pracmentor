# PracMentor – ME422S Fluid Mechanics & Hydraulic Machines Lab

A static web app (no server, no build step). It runs entirely in the browser, so it can be hosted free on GitHub Pages.

## Files

| File | What it is |
|---|---|
| `cover.html` | Animated cover page. Its **Launch PracMentor** button opens the app. |
| `index.html` | The app: Home, Course Content, Virtual Lab, Lab Chatbot, MCQ Quiz, Dashboard, Lab Materials. |
| `overview.html` | Infographic overview slide with buttons that open each app section. |
| `slides.css` | Styles and animation for the two slide pages. |
| `config.json` | Settings: course code, mode, faculty access code, cover page address. |
| `data/materials.json` | Lab materials the chatbot and quiz generator read. Edit this file to change the default materials. |
| `.nojekyll` | Tells GitHub Pages to serve the files as they are. |

## Host it on GitHub Pages

1. Create a free account at github.com and press **New repository**. Name it, for example, `pracmentor`. Choose **Public**.
2. Press **uploading an existing file**, drag in **all files and the `data` folder from inside this folder** (so `index.html` sits at the top level of the repository), then **Commit changes**.
3. Open **Settings → Pages**. Under **Build and deployment**, set **Source** to *Deploy from a branch*, branch **main**, folder **/ (root)**, then **Save**.
4. Wait a minute or two. Your site appears at `https://YOUR-USERNAME.github.io/pracmentor/`. Open `cover.html` first: `https://YOUR-USERNAME.github.io/pracmentor/cover.html`.
5. Share that link with students and faculty.

## How students and faculty use it (static hosting)

GitHub Pages has no database, so each person's progress is saved in **their own browser**.

- **Student:** open the link, choose **Student**, enter name and roll number, work through the lab, quiz and viva. On the Dashboard tab press **Send my results (download file)** and email the file to the faculty (or use **Copy results text**).
- **Faculty:** choose **Faculty**, enter the access code, open the **Dashboard**, and use **Import student results** to load the files students sent (several at once is fine). Final-mark overrides are saved in the faculty member's browser.
- Faculty-uploaded materials are also saved only in that browser. To change the materials for everyone, edit `data/materials.json` in the repository.

## Important limits

- **The faculty access code is not secret.** It sits in `config.json`, which anyone can open on a public site. It only keeps casual users out. Do not rely on it for real security.
- Results files can be edited by a student before sending. Treat them as submissions for review.
- To share results automatically across computers you need a server. Set `"mode": "http"` and `"apiBase"` in `config.json` once a server with the endpoints in the developer handoff spec exists.

## Changing settings

Edit `config.json` in GitHub (pencil icon), change `facultyCode`, and commit. Reload the site to apply it.
