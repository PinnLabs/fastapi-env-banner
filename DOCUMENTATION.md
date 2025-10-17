# Documentation Guide

This project uses [MkDocs](https://www.mkdocs.org/) with the [Material theme](https://squidfunk.github.io/mkdocs-material/) for documentation.

## 📚 Documentation Site

The documentation is available at: **https://pinnlabs.github.io/fastapi-env-banner/**

## 🚀 Quick Start

### Install Documentation Dependencies

```bash
pip install ".[docs]"
```

Or with uv:

```bash
uv pip install ".[docs]"
```

### Preview Documentation Locally

```bash
mkdocs serve
```

Then open your browser to `http://127.0.0.1:8000`

The documentation will automatically reload when you make changes.

### Build Documentation

```bash
mkdocs build
```

The static site will be generated in the `site/` directory.

## 📁 Documentation Structure

```
docs/
├── index.md                 # Home page (Get Started)
├── installation.md          # Installation guide
├── usage/
│   ├── quick-start.md      # Quick start guide
│   ├── configuration.md    # Configuration options
│   └── examples.md         # Usage examples
├── api/
│   ├── config.md           # EnvBannerConfig API reference
│   ├── middleware.md       # EnvBannerMiddleware API reference
│   └── swagger.md          # setup_swagger_ui API reference
└── contributing.md         # Contributing guide
```

## 🔧 Configuration

The documentation is configured in `mkdocs.yml`:

- **Theme**: Material for MkDocs with green color scheme
- **Features**: Navigation tabs, search, code copy, dark mode
- **Extensions**: Syntax highlighting, admonitions, emoji support
- **Navigation**: Organized by sections (Get Started, Usage, API Reference)

## 📝 Writing Documentation

### Markdown Files

All documentation is written in Markdown format. Place files in the `docs/` directory.

### Code Blocks

Use fenced code blocks with language specification:

````markdown
```python
from fastapi import FastAPI
from fastapi_env_banner import EnvBannerConfig

app = FastAPI()
config = EnvBannerConfig.from_env()
```
````

### Admonitions

Use admonitions for notes, warnings, and tips:

```markdown
!!! note
    This is a note.

!!! warning
    This is a warning.

!!! tip
    This is a tip.
```

### Links

Link to other documentation pages:

```markdown
[Configuration Guide](usage/configuration.md)
```

## 🚢 Deployment

### Automatic Deployment

Documentation is automatically deployed to GitHub Pages when changes are pushed to the `main` branch.

The GitHub Actions workflow is defined in `.github/workflows/docs.yml`.

### Manual Deployment

To manually deploy (requires GitHub Pages to be enabled):

```bash
mkdocs gh-deploy
```

This will build the documentation and push it to the `gh-pages` branch.

## 🔍 Testing Documentation

Before committing changes:

1. **Build locally** to check for errors:
   ```bash
   mkdocs build --strict
   ```

2. **Preview locally** to verify appearance:
   ```bash
   mkdocs serve
   ```

3. **Check all links** work correctly

4. **Verify code examples** are accurate

## 📋 Checklist for New Documentation

- [ ] Create/update Markdown files in `docs/`
- [ ] Add to navigation in `mkdocs.yml` if needed
- [ ] Include code examples
- [ ] Add cross-references to related pages
- [ ] Test locally with `mkdocs serve`
- [ ] Build with `mkdocs build --strict`
- [ ] Commit and push to trigger deployment

## 🎨 Customization

### Theme Colors

Edit `mkdocs.yml` to change colors:

```yaml
theme:
  palette:
    primary: green  # Change primary color
    accent: green   # Change accent color
```

### Navigation

Edit `mkdocs.yml` to modify navigation structure:

```yaml
nav:
  - Home: index.md
  - Your Section:
      - Page 1: section/page1.md
      - Page 2: section/page2.md
```

## 📚 Resources

- [MkDocs Documentation](https://www.mkdocs.org/)
- [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/)
- [Markdown Guide](https://www.markdownguide.org/)
- [PyMdown Extensions](https://facelessuser.github.io/pymdown-extensions/)

## 🆘 Troubleshooting

### Documentation Not Building

1. Check for syntax errors in Markdown files
2. Verify all referenced files exist
3. Run `mkdocs build --strict` to see detailed errors

### Changes Not Appearing

1. Clear browser cache
2. Wait for GitHub Actions to complete (check Actions tab)
3. Verify GitHub Pages is enabled in repository settings

### Local Server Issues

1. Ensure dependencies are installed: `pip install ".[docs]"`
2. Check port 8000 is not in use
3. Try a different port: `mkdocs serve -a localhost:8001`

## 💡 Tips

- Use `mkdocs serve` during development for live reload
- Keep documentation close to code changes
- Include practical examples
- Use clear, concise language
- Add screenshots where helpful
- Link to related documentation
- Keep API reference up to date
