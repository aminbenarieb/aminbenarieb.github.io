# Amin Benarieb's Tech Blog

A personal tech blog built with [Hugo](https://gohugo.io/) and the [Devise theme](https://github.com/aos/tale-hugo). This blog focuses on iOS development, debugging techniques, and technical insights.

## 🌐 Live Site

Visit the blog at: [https://amin.benarieb.com](https://amin.benarieb.com)

## 📝 About

This blog covers various topics including:
- iOS development tips and tricks
- Debugging techniques and tools
- Development productivity improvements
- Open source contributions
- Technical tutorials and guides

## 🛠️ Tech Stack

- **Static Site Generator**: [Hugo](https://gohugo.io/)
- **Theme**: [Devise](https://github.com/aos/tale-hugo)
- **Deployment**: GitHub Pages (via `public` directory)
- **Analytics**: Google Analytics
- **Comments**: Disqus (configured but not active)

## 🚀 Getting Started

### Prerequisites

- [Hugo](https://gohugo.io/installation/) installed on your system
- Git

### Local Development

1. **Clone the repository**
   ```bash
   git clone https://github.com/aminbenarieb/techblog.git
   cd techblog
   ```

2. **Install Hugo theme** (if not already present)
   ```bash
   git submodule add https://github.com/aos/tale-hugo.git themes/devise
   ```

3. **Start the development server**
   ```bash
   hugo server -D
   ```

4. **View the site**
   Open your browser and navigate to `http://localhost:1313`

### Building for Production

```bash
hugo --minify
```

The generated site will be in the `public/` directory, ready for deployment.

## 📁 Project Structure

```
├── archetypes/          # Hugo content templates
├── assets/             # Static assets (images, favicon, etc.)
├── content/            # Blog posts and content
│   └── posts/          # Individual blog posts
├── css/                # Custom CSS styles
├── images/             # Blog images
├── static/             # Static files served directly
├── hugo.toml           # Hugo configuration
├── CNAME               # Custom domain configuration
└── LICENSE             # CC0 License
```

## ✍️ Writing Posts

1. **Create a new post**
   ```bash
   hugo new posts/your-post-title.md
   ```

2. **Edit the front matter** in the generated file:
   ```yaml
   ---
   title: "Your Post Title"
   date: 2023-12-01T10:00:00+01:00
   draft: false
   ---
   ```

3. **Write your content** in Markdown

4. **Add images** to the `static/images/` directory and reference them:
   ```markdown
   ![Image description](/images/your-image.png)
   ```

## 🎨 Customization

### Theme Configuration

The blog uses the Devise theme with customizations in `hugo.toml`:

- **Site Title**: "Amin Benarieb's Blog"
- **Header Subtitle**: "iOS dev"
- **Social Links**: GitHub, LinkedIn, Twitter
- **Color Scheme**: Light theme with custom background and font colors

### Adding Social Links

Edit the `[[params.social]]` sections in `hugo.toml`:

```toml
[[params.social]]
  fa_icon = "fab fa-github fa-1x"
  href = "http://github.com/yourusername"
```

## 🚀 Deployment

This blog is deployed to GitHub Pages using the `public` directory:

1. **Build the site**
   ```bash
   hugo --minify
   ```

2. **Commit and push** the `public` directory to your repository

3. **Configure GitHub Pages** to serve from the `public` directory

The site is automatically available at your custom domain: `amin.benarieb.com`

## 📄 License

This project is licensed under the [CC0 1.0 Universal](LICENSE) - Creative Commons Public Domain Dedication.

## 🤝 Contributing

While this is a personal blog, suggestions and improvements are welcome! Feel free to:

- Open issues for bugs or suggestions
- Submit pull requests for improvements
- Share feedback on content

## 📞 Contact

- **Website**: [amin.benarieb.com](https://amin.benarieb.com)
- **GitHub**: [@aminbenarieb](https://github.com/aminbenarieb)
- **LinkedIn**: [Amin Benarieb](https://www.linkedin.com/in/aminbenarieb/)
- **Twitter**: [@amin_benarieb](https://twitter.com/amin_benarieb)

---

*Built with ❤️ using Hugo and the Devise theme*