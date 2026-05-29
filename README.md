# Static Blog Post Assistant (Studio Pro)

A custom, lightweight, fully client-side Markdown editor and frontmatter generator engineered specifically for managing and creating posts for the blog section of [codymkw.nekoweb.org](https://codymkw.nekoweb.org).

Hosted entirely via **GitHub Pages** for quick access from any device.

---

## 🚀 Features

* **Dual EasyMDE Instances:** Dedicated rich-text markdown panels for writing Primary Content and an optional trailing Content 2 block (ideal for breaking text around media embeds).
* **Robust Frontmatter Parser:** Instantly load existing `.md` posts to update titles, tags, header images, ratings, or text. Fully optimized to handle both Unix (`\n`) and Windows (`\r\n`) line endings without breaking regex matchers.
* **Real-Time Core Layout Rendering:** Live visual sandbox that displays exactly how metadata, feature images, video embeds, and Markdown styling translate into HTML layout items.
* **Custom Review Score Engine:** Built-in calculation module that renders numeric review values (1-5) into a clean star block layout (`★` / `☆`) with automatic quality verdicts.
* **100% Client-Side & Dark Theme Native:** Processes everything directly in the browser via native Web APIs (`FileReader`, `Blob`, `URL.createObjectURL`). Zero server dependencies, zero tracking, and designed with a dedicated dark UI to keep eye strain at a minimum.

---

## 🛠️ Personalized Publishing Workflow

Whenever writing a new update or altering an old post, follow this simple routine:

1. **Launch the Studio:** Open your deployed GitHub Pages URL.
2. **Draft or Edit:** * To start fresh, just fill out the metadata fields and write away.
   * To edit an older log, click **Load Existing .md Post** and choose the original file from your computer.
3. **Download:** Click **Download .md File** to export a perfectly structured Markdown asset with clean kebab-case file naming (`your-post-title.md`).
4. **Deploy to Nekoweb:**
   * Drop the downloaded `.md` file directly into your server's `posts/` directory.
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

## 📦 Local Project Setup & Deployment

Since this entire utility operates inside a single isolated HTML file, initializing it on GitHub Pages takes less than a minute:

1. Create a new public or private GitHub repository.
2. Commit your main interface file to the repository as `post-creator.html`.
3. Head over to **Settings** -> **Pages** on your GitHub repository console.
4. Set the build source parameter to **Deploy from a branch** and select your main production branch (`/root`).
5. Save, wait a moment for the automated GitHub Pages runner to compile, and your live studio will be ready at:
   `https://codymkw.github.io/post-creator/post-creator`
