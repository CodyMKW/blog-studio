# Blog Studio Suite
A custom, lightweight suite of fully client-side static site utilities engineered specifically for managing and generating posts for the blog section of [codymkw.nekoweb.org](https://codymkw.nekoweb.org).
Hosted entirely via **GitHub Pages** for quick access and cross-device drafting.

---

## 🛠️ Included Utilities

All tools are bundled into a single file — **`index.html`** — and accessible via a tab bar at the top of the page. No page reloads, no separate files to juggle.

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
* **Full Metadata Coverage:** Supports all frontmatter fields including title, date, time, author, category, header image, video embed URL, and review rating.
* **Clipboard Utility:** Features a quick one-click **Copy Snippet** button alongside traditional local file downloads.
* **Drag & Drop Support:** Drop any `.md` file directly onto the upload zone — no file picker required.

### Tab 3 — index.json Manager
A dedicated utility for updating your post registry without manually editing JSON.

* **Upload your index.json:** Drag and drop or browse to load your existing `posts/index.json` — the tool reads the current `posts` array and displays a live count.
* **Pull from Editor:** Automatically derives the kebab-case filename from whatever title is currently set in the Post Creator or Frontmatter Injector tab — no retyping required.
* **Manual Entry:** Can also accept a filename typed directly if working outside the other tabs.
* **Duplicate Detection:** Warns you if the filename already exists in the loaded index before downloading.
* **Insert Position Control:** Choose to prepend the new entry to the top (newest-first) or append to the bottom.
* **Live JSON Preview:** The right panel shows the fully updated `index.json` output in real time before you commit to downloading.
* **One-Click Download:** Outputs a ready-to-deploy `index.json` file with the new entry cleanly inserted.

---

## 🚀 The Publishing Workflow

Whether you're handling a clean script, an Obsidian note, or a brand-new review draft, here is the routine:

1. **Format/Inject:** If starting with a raw or external `.md` file, switch to the **Frontmatter Injector** tab and drop your file in to instantly structure the proper frontmatter tags.
2. **Fine-Tune:** Switch to the **Post Creator** tab (or load your structured file directly there) to leverage the split-pane visual layout simulator and finalize all metadata values.
3. **Download the Post:** Click **Download .md File** to grab a perfectly formatted kebab-case Markdown file (`your-post-title.md`).
4. **Update the Registry:** Switch to the **index.json Manager** tab, upload your current `posts/index.json`, pull the filename from whichever editor tab you used, and click **Download Updated index.json**.
5. **Deploy to Nekoweb:**
   * Upload the `.md` file to your server's `posts/` directory.
   * Replace your existing `posts/index.json` with the updated file you just downloaded.

---

## 📦 GitHub Pages Setup & Deployment

Because these tools run entirely on client-side Web APIs (`FileReader`, `Blob`, `URL.createObjectURL`), setting them up on your repository takes less than a minute:

1. Push `index.html` to your repository.
2. Enable **GitHub Pages** under **Settings → Pages**, pointing to your target branch.
3. Access the suite at `https://<your-username>.github.io/blog-studio`.

No build step, no dependencies to install, no server required.
