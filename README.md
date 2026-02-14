**[English](./README.md) | [中文](./README_zh.md)**

---


<a name="english"></a>

# Bento Profile — Your Research Profile on GitHub Pages

A beautiful, interactive researcher profile page that you can host for free on GitHub Pages. Edit your profile in the browser, preview changes instantly, and publish with a single click.

---

## ✨ Features

- 🎨 **Bento Grid Layout** — Showcase your projects, papers, links, and more with a stunning card-based grid
- ✏️ **Visual Editor** — Edit everything in your browser with drag-and-drop and inline editing
- 👁️ **Real-time Preview** — See exactly how your profile will look before publishing
- 📤 **One-Click Publish** — Push your changes to GitHub and auto-deploy to GitHub Pages
- 💾 **Local-First** — All data stored in your browser; works offline
- 🆓 **Completely Free** — Host on GitHub Pages at zero cost
- 🔒 **Your Data, Your Control** — Everything lives in your GitHub repository
- 📱 **Mobile Responsive** — Looks great on all devices

### What Makes Us Different

1. **No-Code Profile Creation** — Even without development skills, as long as you have a GitHub account, you can create your profile through graphical "click-click-click" operations. You don't need to pull the code down and redeploy.

2. **Needboard Feature** — We have Needboard, which sets us apart from others. Showcase what you're seeking and offering for collaboration.

3. **Share My Site** — Once your profile is ready:
   - You or your friends can download the profile as a PNG image to share
   - You can also copy the link directly to share

---

## 🚀 Quick Start (5 minutes)

### Step 1: Create Your Repository

Click the green **"Use this template"** button at the top of this page, then select **"Create a new repository"**.

- **Repository name**: We recommend `your-username.github.io` for a clean URL, or any name you prefer
- **Visibility**: Public (required for free GitHub Pages)

### Step 2: Enable Deployment Permissions

1. Go to your new repository's **Settings** → **Actions** → **General**
2. Scroll down to **"Workflow permissions"**
3. Select **"Read and write permissions"**
4. Click **Save**

### Step 3: Configure GitHub Pages

1. Go to **Settings** → **Pages** (on the left sidebar)
2. Under **Build and deployment** → **Source**, select **GitHub Actions**

### Step 4: Trigger First Deployment

Now trigger the deployment manually:

1. Go to the **Actions** tab
2. Click **"Deploy to GitHub Pages"** on the left
3. Click **"Run workflow"** → select `main` → click the green button
4. Wait 2-3 minutes for the build to complete

### Step 5: Visit Your Profile

Your empty profile is now live at:

- If repo is `username.github.io` → `https://username.github.io`
- If repo is `my-profile` → `https://username.github.io/my-profile`

### Step 6: Edit & Publish

1. Visit your profile URL with `?mode=edit` appended:
   - `https://username.github.io/my-profile?mode=edit`
   - This opens the full editing UI on your published site
   - If you've previously published, your existing data is automatically loaded as a starting point
2. Click **Edit** to enter editing mode
3. Add your bio, avatar, social links, and research interests
4. Add cards: links, GitHub repos, HuggingFace models, images, and more
5. Click **Preview** to see the result
6. Click **Publish** to push your data to GitHub

#### First-time Publish Setup

When you click **Publish** for the first time, you'll need:

1. **GitHub Personal Access Token**
   - Go to [github.com/settings/tokens](https://github.com/settings/tokens)
   - Click "Generate new token (classic)"
   - Select the `repo` scope
   - Copy the generated token

2. **Repository URL**
   - Format: `username/repo-name` (e.g., `alice/alice.github.io`)

3. **Branch**: Leave as `main` (default)

Your credentials are cached in the browser — you won't need to enter them again.

After publishing, GitHub Actions will automatically rebuild and deploy your site in 2-3 minutes.

---

## 🎨 Card Types

| Card | Description |
|------|-------------|
| **Link** | Share websites, articles, or any URL (auto-fetches title & image) |
| **GitHub Repo** | Display your GitHub repositories with stars, language, and description |
| **HuggingFace** | Showcase your models or datasets with downloads and likes |
| **Image** | Upload photos, designs, or screenshots |
| **Text** | Rich text content with formatting |
| **Section Title** | Organize your cards with section headers |
| **NeedBoard** | Show what you're seeking and offering for collaboration |

---

## ✏️ Editing on Your Published Site

You can edit your profile directly on your published GitHub Pages site — no local development environment needed!

1. **Open edit mode**: Visit `https://username.github.io/my-profile?mode=edit`
2. **Make changes**: The full editor toolbar appears, and your published data is loaded as a starting point
3. **Preview**: Click Preview to see how it looks
4. **Publish**: Click Publish to update your live site

> **How does this work?** When you add `?mode=edit` to your URL, the site switches from read-only mode to edit mode. Your published profile data (from `profile-config.json`) is automatically imported into your browser's localStorage, where you can edit it freely. When you publish, the updated data is pushed back to GitHub and your site rebuilds.

> **Is it safe?** Yes! Only you (with your GitHub PAT) can publish changes. Other visitors who add `?mode=edit` can only see the editor UI, but any changes they make stay in their own browser and cannot be pushed to your repository without your token.

---

## 🔧 How It Works

```
You edit in browser → Data saved to localStorage
                          ↓ Click Publish
                    GitHub API commits profile-config.json to your repo
                          ↓
                    GitHub Actions builds static site
                          ↓
                    Visitors see your profile on GitHub Pages
                    (read-only, no toolbar, data from profile-config.json)
```

### Key Files

| File | Purpose |
|------|---------|
| `public/profile-config.json` | Default empty placeholder for first deployment |
| `profile-config.json` (repo root) | Your actual profile data (created by Publish) |
| `.github/workflows/deploy.yml` | Automated build & deploy pipeline |

---

## 🛠️ Local Development (Optional)

If you want to run the project locally:

```bash
# Clone your repository
git clone https://github.com/username/repo-name.git
cd repo-name

# Install dependencies
npm install

# Start development server
npm run dev

# Open http://localhost:3000/profile
```

---

## 🔐 Security

- Your GitHub token is stored **base64-encoded** in browser localStorage
- Token is sent **directly** from your browser to GitHub API (no middleman server)
- Only `repo` scope is needed
- Token can be [revoked anytime](https://github.com/settings/tokens)

**Best Practices:**
- Use a dedicated token just for this profile
- Don't commit tokens to git
- Clear browser data when using shared/public computers

---

## 📖 Tech Stack

- [Next.js 15](https://nextjs.org/) — React framework with static export
- [Tailwind CSS](https://tailwindcss.com/) + [Radix UI](https://www.radix-ui.com/) — Styling & components
- [react-grid-layout](https://github.com/react-grid-layout/react-grid-layout) — Drag-and-drop grid
- [GitHub Pages](https://pages.github.com/) — Free static hosting
- [GitHub REST API](https://docs.github.com/en/rest) — Publish data without a backend

---

## 🤝 Contributing

Contributions are welcome!

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-widget`)
3. Commit your changes (`git commit -m 'Add amazing widget'`)
4. Push to the branch (`git push origin feature/amazing-widget`)
5. Open a Pull Request

---

## 📄 License

MIT License — see [LICENSE](./LICENSE) for details.

---

## 👥 Initial Contributors

- **Liz** — Lead & Maintainer
- **Xinran** — Co-creator
- **Chijiang** — Early contributor

---

Made with ❤️ by [Research AI+](https://github.com/ResearchNexus)
