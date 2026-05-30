# Static Blog Post Assistant (Studio Pro)

A custom, lightweight suite of fully client-side static site utilities engineered specifically for managing and generating posts for the blog section of [codymkw.nekoweb.org](https://codymkw.nekoweb.org).

Hosted entirely via **GitHub Pages** for quick access and cross-device drafting.

---

## 🛠️ Included Utilities

### 1. Post Creator Studio (`post-creator.html`)
The primary content engine featuring live sandbox rendering and dedicated writing fields.
* **Dual EasyMDE Instances:** Separate input tracking blocks for Primary Content and trailing Content 2 text sections.
* **Review Score Engine:** Converts raw numeric evaluations (1-5) into structural star blocks (`★` / `☆`) on the fly.
* **Line-Ending Protection:** Optimized frontmatter engine that handles both Unix (`\n`) and Windows (`\r\n`) file submissions perfectly.

### 2. Universal Frontmatter Injector (`post-converter.html`)
A slick, glassmorphic prep utility to upgrade *any* generic Markdown file, note, or external draft into a format compliant with the studio layout.
* **Automatic Title Mapping:** Pulls text headings (`# Title`) or safely sanitizes file names to dynamically fill input attributes.
* **Disk Signature Telemetry:** Automatically queries local operating system timestamps on file drops to isolate the last-modified date and pre-fill scheduling blocks.
* **Document Stats Analyzer:** Real-time feedback monitor providing full counts for words, total lines, and characters.
* **Clipboard Utility:** Features a quick one-click **Copy Snippet** button alongside traditional local file downloads.

---

## 🚀 The Publishing Workflow

Whether you're handling a clean script, an Obsidian note, or a brand-new review draft, here is the routine:

1. **Format/Inject:** If starting with a raw or external `.md` file, run it through `post-converter.html` to instantly structure the proper frontmatter tags.
2. **Fine-Tune:** Load your structured asset into `post-creator.html` to leverage the split-pane visual layout simulator and finalize metadata values.
3. **Download:** Click **Download** to grab a perfectly formatted kebab-case Markdown file (`your-post-title.md`).
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

1. Commit both `post-creator.html` and `post-converter.html` directly into the root folder of your repository.
2. Navigate to your repository's **Settings** -> **Pages** menu on GitHub.
3. Under Build and Deployment, set the source to **Deploy from a branch** and pick your production branch (`/root`).
4. Save the configuration changes. After the automated runner finishes building, your production interfaces will be instantly live at:
   * **Main Studio Editor:** `https://<your-username>.github.io/<repo-name>/post-creator.html`
   * **Universal Metadata Injector:** `https://<your-username>.github.io/<repo-name>/post-converter.html`
