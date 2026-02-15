# Quick Start Guide

This guide will help you set up and start using Odoo Shortcuts in 5 minutes.

## 📦 Installation

### From VS Code Marketplace

1. Open VS Code
2. Go to the Extensions tab (`Ctrl+Shift+X` / `Cmd+Shift+X`)
3. Search for "Odoo Shortcuts"
4. Click **Install**

### From VSIX File

```bash
code --install-extension odoo-shortcuts-0.40.4.vsix
```

## ⚙️ Initial Configuration

### 1. Configure Odoo Server Paths

Open Settings (`Ctrl+,`) and search for `odooShortcuts.odooServerPaths`:

```json
{
  "odooShortcuts.odooServerPaths": [
    "/home/user/odoo",
    "/home/user/enterprise"
  ]
}
```

This allows the LSP to index Odoo files for autocomplete.

### 2. Configure Addon Detection Patterns

For the explorer to detect correctly:

```json
{
  "odooShortcuts.coreAddonPatterns": [
    "/odoo/addons/",
    "/odoo/odoo/addons/"
  ],
  "odooShortcuts.enterpriseAddonPatterns": [
    "/enterprise/"
  ]
}
```

## 🚀 First Use

### Create Your First Addon

1. Open the command palette (`Ctrl+Shift+P`)
2. Type "New Addon"
3. Select **Odoo Shortcuts: New Addon**
4. Complete the information:
   - Addon name
   - Odoo version
   - Include assets? (Only for v14 with assets)

### Explore Addons

1. Look at the left sidebar
2. Find the Odoo icon (🦉)
3. Click to open the **Odoo Explorer**

![Odoo Explorer](https://github.com/mjavint/odoo-shortcuts/blob/main/img/01-explorer.jpeg?raw=true)

## 💡 Quick Tips

### Keyboard Shortcuts

| Action | Windows/Linux | Mac |
|--------|--------------|-----|
| New Addon | `Ctrl+K Ctrl+A` | `Cmd+K Cmd+A` |
| Debug Odoo | `Ctrl+K Ctrl+N` | `Cmd+K Cmd+N` |
| Debug JS | `Ctrl+K J` | `Cmd+K J` |
| Filter Addons | `Ctrl+K Ctrl+F` | `Cmd+K Cmd+F` |
| Open OWL definition | `Ctrl+Shift+D` | `Cmd+Shift+D` |

### CodeLens

When you open a Python file with Odoo models, you'll see links above each class:

```python
class MyModel(models.Model):     # ← Links appear here
    _name = 'my.model'           # [Create Views] [Create Report]
```

Click to automatically generate code.

![CodeLens Example](https://github.com/mjavint/odoo-shortcuts/blob/main/img/codelens.gif?raw=true)

### Useful Commands

- `Odoo Shortcuts: Restart OWL/JS Language Server` - Restart LSP
- `Odoo Shortcuts: Reindex JavaScript Files` - Update index
- `Odoo Shortcuts: Open Odoo Arguments Configuration` - Configure arguments

## 🎯 Next Steps

- [Learn the Scaffold System](./features/scaffold-system.md)
- [Discover Odoo Explorer](./features/odoo-explorer.md)
- [Configure LSP](./features/lsp-features.md)

## ❓ Common Issues

**Q: I don't see the Odoo Explorer**
A: Verify you have a workspace open with Odoo files.

**Q: Autocomplete doesn't work**
A: Restart the LSP: `Ctrl+Shift+P` → "Restart OWL/JS Language Server"

**Q: My addons aren't detected**
A: Verify they have `__manifest__.py` and configure paths correctly.

---

**Ready for more?** Explore the [detailed features](./index.md).
