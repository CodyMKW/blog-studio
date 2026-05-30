# Blog Studio Suite
A custom, lightweight suite of fully client-side static site utilities engineered specifically for managing and generating posts for the blog section of [codymkw.nekoweb.org](https://codymkw.nekoweb.org).
Hosted entirely via **GitHub Pages** for quick access and cross-device drafting.

---

## 🛠️ Included Utilities

Both tools are bundled into a single file — **`blog-studio.html`** — and accessible via a tab bar at the top of the page. No page reloads, no separate files to juggle.

### Tab 1 — Post Creator & Editor
The primary content engine featuring live sandbox rendering and dedicated writing fields.

* **Dual EasyMDE Instances:** Separate input tracking blocks for Primary Content and trailing Content 2 text sections.
* **Review Score Engine:** Converts raw numeric evaluations (1–5) into structural star blocks (`★` / `☆`) on the fly.
* **Line-Ending Protection:** Optimized frontmatter engine that handles both Unix (`\n`) and Windows (`\r\n`) file submissions perfectly.
* **Load Existing Posts:** Import any previously created `.md` file back into the editor to continue drafting or make updates.

### Tab 2 — Universal Frontmatter Injector
A slick prep utility to upgrade *any* generic Markdown file, note, or external draft into a format compliant with the studio layout.

* **Automatic Title Mapping:** Pulls text headings (`# Title`) or safely sanitizes file names to dynamically fill input attributes.
* **Disk Signature Telemetry:** Automatically queries local OS timestamps on file drops to pre-fill scheduling blocks with the last-modified date.
* **Document Stats Analyzer:** Real-time feedback providing full counts for words, total lines, and characters.
* **Clipboard Utility:** Features a quick one-click **Copy Snippet** button alongside traditional local file downloads.
* **Drag & Drop Support:** Drop any `.md` file directly onto the upload zone — no file picker required.

---

## 🚀 The Publishing Workflow

Whether you're handling a clean script, an Obsidian note, or a brand-new review draft, here is the routine:

1. **Format/Inject:** If starting with a raw or external `.md` file, switch to the **Frontmatter Injector** tab and drop your file in to instantly structure the proper frontmatter tags.
2. **Fine-Tune:** Switch to the **Post Creator** tab (or load your structured file directly there) to leverage the split-pane visual layout simulator and finalize all metadata values.
3. **Download:** Click **Download .md File** to grab a perfectly formatted kebab-case Markdown file (`your-post-title.md`).
4. **Deploy to Nekoweb:**
   * Drop the updated `.md` file directly into your server's `posts/` directory.
   * Open your master post registry file at `posts/index.json` and prepend your new file name right into the structural list array:

```json
{
  "posts": [
    "your-new-filename.md",
    "older-blog-entry.md"
  ]
}
```

---

## 📦 GitHub Pages Setup & Deployment

Because these tools run entirely on client-side Web APIs (`FileReader`, `Blob`, `URL.createObjectURL`), setting them up on your repository takes less than a minute:

1. Push `blog-studio.html` to your repository.
2. Enable **GitHub Pages** under **Settings → Pages**, pointing to your target branch.
3. Access the suite at `https://<your-username>.github.io/<repo-name>/blog-studio.html`.

No build step, no dependencies to install, no server required.
