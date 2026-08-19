# Model Deployment Interactive Teaching Deck

A self-contained, horizontally sliding HTML lesson that scaffolds Chapter 4 **Model Deployment** for learners with no prior deployment knowledge.

## Files
- `index.html` — complete interactive lesson (no build step)
- `TEACHER-GUIDE.md` — pacing, prompts, misconceptions and practical handoff
- `.nojekyll` — makes GitHub Pages serve the files directly
- `preview.png` — representative screenshot

## Run locally
Open `index.html` in a modern browser. No server or package installation is required.

## Navigation
- Previous / Next buttons
- Left / Right arrow keys
- Page Up / Page Down
- Home / End
- Swipe left / right on touch devices
- Clickable progress dots
- Deep links such as `#12`
- Teacher Notes toggle

## Deploy to GitHub Pages
1. Create a new GitHub repository.
2. Upload all files from this folder to the repository root.
3. In GitHub, open **Settings → Pages**.
4. Under **Build and deployment**, choose **Deploy from a branch**.
5. Select the branch containing the files (usually `main`) and the `/ (root)` folder.
6. Save. GitHub will publish the static site and show the Pages URL.

## Technical design
- Semantic HTML, CSS and vanilla JavaScript only
- No framework or build process
- No external image or JavaScript dependencies
- Responsive from mobile to projector screens
- Keyboard and touch navigation
- High-contrast interface and visible focus states
- `aria-live` feedback for interactive checks
- `prefers-reduced-motion` support

## Lesson design
The lesson uses one recurring anchor: a three-class fruit classifier (Apple, Banana, Orange). It moves from concrete experience to technical terminology, then to Flask code, local serving, cloud storage, S3/Lambda event-driven inference and the chapter's high-level Google Cloud sequence.
