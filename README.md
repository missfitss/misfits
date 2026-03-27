 (cd "$(git rev-parse --show-toplevel)" && git apply --3way <<'EOF' 
diff --git a/README.md b/README.md
index 8aaddc4600e950495c6dd25c3a72705d02b27418..d8a7cd53e51b792737a508ad7811fd1b6ddbe9e9 100644
--- a/README.md
+++ b/README.md
@@ -1 +1,68 @@
-# misfits
\ No newline at end of file
+# Misfits Creative — GitHub Pages Portfolio
+
+Single-page portfolio site for a freelancing team offering:
+- Video editing
+- Social media management
+- Content writing (blogs, transcription, descriptions)
+
+## Live deployment (GitHub Pages)
+Use the **main** branch and root folder:
+1. Open your GitHub repository.
+2. Go to **Settings → Pages**.
+3. Under **Build and deployment**, choose:
+   - **Source:** Deploy from a branch
+   - **Branch:** `main` and `/ (root)`
+4. Save. GitHub will publish your site on the default `*.github.io` URL.
+
+## How to update the site later (no coding background)
+Open `index.html` in GitHub web editor (press `.` in repo, or click the file and use the pencil icon).
+
+### 1) Update your contact details
+Search for these lines and replace with real values:
+- `yourteam@gmail.com`
+- `@yourteamhandle`
+
+Also update this JavaScript variable near the bottom:
+```js
+const TEAM_EMAIL = "yourteam@gmail.com";
+```
+
+### 2) Update Home content
+In the **Home** panel, edit:
+- Main headline (`Sleek. Sharp. Scroll-stopping.`)
+- Service descriptions
+- `Featured Work` cards with real project names and short descriptions
+
+### 3) Update About Us story
+In the **About Us** panel:
+- Replace the paragraph and bullet points with your real team story
+
+### 4) Update inquiry behavior
+The inquiry form opens the visitor's email app using `mailto:`.
+That means no backend/server is required.
+
+If you want automatic form delivery (without opening email app), you can later integrate a form service like Formspree, Basin, or Netlify Forms.
+
+### 5) Change colors/theme later
+At the top of `index.html` inside `:root`, update these variables:
+- `--pink`
+- `--charcoal`
+- `--paper`
+- `--accent`
+
+## Notes
+- The current style follows your reference image direction: bright pink base, charcoal geometric overlays, black linework, and layered floating content cards.
+- Content is placeholder-ready so you can replace it easily as your portfolio grows.
+
+## HTML validation (xmllint)
+To validate HTML locally:
+```bash
+xmllint --html --noout index.html
+```
+
+If `xmllint` is missing, install it (Ubuntu/Debian):
+```bash
+sudo apt-get update && sudo apt-get install -y libxml2-utils
+```
+
+A GitHub Actions workflow is included to run the same check on pushes and pull requests.
 
EOF
)
