# Odoo Shortcuts Documentation

Welcome to the complete documentation for **Odoo Shortcuts** - The definitive VS Code extension for Odoo development.

![General Demo](https://github.com/mjavint/odoo-shortcuts/blob/main/img/general.gif?raw=true)

## 📚 Quick Navigation

### 🚀 Getting Started
- [Quick Start Guide](./getting-started.md) - Set up your environment in 5 minutes
- [Installation and Configuration](./configuration.md) - Customize the extension

### ✨ Main Features

#### 🏗️ Code Generation (Scaffold)
- [Scaffold System](./features/scaffold-system.md) - Generate Odoo files automatically
  - Create complete addons
  - Generate Models (Python)
  - Create Views (XML)
  - Generate OWL Components (JavaScript)
  - Security files
  - Automated tests

#### 🌳 Addon Explorer
- [Odoo Explorer](./features/odoo-explorer.md) - Navigate your addons visually
  - Custom Addons view
  - Odoo Core view (Read-Only)
  - Odoo Enterprise view (Read-Only)
  - Configuration files management

#### 🔧 Development Tools
- [CodeLens](./features/codelens.md) - Quick actions on models
- [LSP / IntelliSense](./features/lsp-features.md) - Smart autocomplete
- [XPath Tools](./features/xpath-tools.md) - XML tools
- [Formatter](./features/formatter.md) - XML formatter

### 📖 Reference
- [Commands Reference](./commands-reference.md) - Complete command list
- [Keybindings](./keybindings.md) - Available shortcuts
- [Configuration](./configuration.md) - Settings options

### 🆘 Support
- [Frequently Asked Questions (FAQ)](./faq.md)
- [Troubleshooting](./troubleshooting.md)
- [Changelog](./changelog.md)

## 🎯 Highlighted Features

### 1. **Intelligent Scaffold**
Generate complete Odoo code with a single command. Supports Odoo versions 14-19 and automatically adapts syntax (e.g., `tree` vs `list` in Odoo 18+).

![Scaffold Demo](https://github.com/mjavint/odoo-shortcuts/blob/main/img/new-context.gif?raw=true)

### 2. **Visual Explorer**
Browse your addons like a file explorer. Support for:
- Multiple repositories
- Core and Enterprise addons
- Configuration files
- CRUD operations

![Explorer View](https://github.com/mjavint/odoo-shortcuts/blob/main/img/00-explorer.jpeg?raw=true)

### 3. **Advanced LSP**
Proprietary language server with:
- OWL component autocomplete
- Navigation to definitions
- Automatic reindexing
- Import support

![OWL LSP](https://github.com/mjavint/odoo-shortcuts/blob/main/img/01-owl-lsp.png?raw=true)

### 4. **Contextual CodeLens**
Quick actions directly in the code:
- Create views from models
- Generate reports
- Import security
- View OWL documentation

![CodeLens](https://github.com/mjavint/odoo-shortcuts/blob/main/img/codelens.jpeg?raw=true)

## 📝 Quick Example

```python
# Cursor position on model → CodeLens appears
class SaleOrder(models.Model):
    _name = 'sale.order'
    
# [Create Views] [Create Report] [Import Security]
```

## 🔗 Useful Links

- [GitHub Repository](https://github.com/mjavint/odoo-shortcuts)
- [Report Issues](https://github.com/mjavint/odoo-shortcuts/issues)
- [VS Code Marketplace](https://marketplace.visualstudio.com/items?itemName=mvintg.odoo-file)

---

**Need help?** Check the [quick start guide](./getting-started.md) or browse the [FAQ](./faq.md).
