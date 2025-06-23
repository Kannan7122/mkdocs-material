# Kannan's MkDocs

Welcome to **Kannan's MkDocs** — the place where you document everything you **learn**, **code**, and **fix**. This serves as your personal and professional knowledge base.

---

## 🚀 Install Setup

**Material for MkDocs** is a powerful and elegant theme built on top of **MkDocs**, a static site generator that's perfect for project documentation.

### 📦 Installation via pip

It's recommended to use a virtual environment. Open a terminal and run:

```bash
pip install mkdocs-material
```

---

## 📁 Creating Your Site

Once Material for MkDocs is installed, create your documentation project using the `mkdocs` CLI.

Navigate to your project directory and run:

```bash
mkdocs new .
```

This will create the following structure:

```
.
├── docs/
│   └── index.md
└── mkdocs.yml
```

---

## ⚙️ Configuration

Update the `mkdocs.yml` configuration file to set your site name and enable the Material theme:

```yaml
site_name: My site
site_url: https://mydomain.org/mysite

theme:
  name: material
```

You can personalize `site_name` and `site_url` according to your needs.

---

## 📝 Previewing as You Write

MkDocs includes a **live preview server** that automatically refreshes the site when changes are saved.

To start the development server, run:

```bash
mkdocs serve
```

Then open your browser and navigate to:

[http://localhost:8000](http://localhost:8000)

You should see your documentation site live.

![Preview Screenshot](image.png)

---

Happy documenting! 🎉