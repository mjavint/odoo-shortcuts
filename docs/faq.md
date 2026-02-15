# Frequently Asked Questions (FAQ)

## 🚀 Installation and Configuration

### How do I install Odoo Shortcuts?

**From Marketplace:**
1. Open VS Code
2. Go to Extensions (`Ctrl+Shift+X`)
3. Search for "Odoo Shortcuts"
4. Click **Install**

**From VSIX:**
```bash
code --install-extension odoo-shortcuts-0.40.4.vsix
```

### What do I need to configure after installation?

Configure Odoo Server paths for the LSP:

```json
{
  "odooShortcuts.odooServerPaths": [
    "/home/user/odoo",
    "/home/user/enterprise"
  ]
}
```

### Why doesn't the Odoo Explorer appear?

1. Verify you have a workspace open
2. Check that there are addons with `__manifest__.py`
3. Update the view: click on 🔄

## 🏗️ Scaffold and Code Generation

### How do I create a new addon?

Use the command: `Odoo Shortcuts: New Addon`

Or use the shortcut: `Ctrl+K Ctrl+A`

### Can I customize the generated templates?

Yes, configure custom headers in settings:

```json
{
  "odooShortcuts.fileHeaders.enabled": true,
  "odooShortcuts.fileHeaders.author": "Your Name",
  "odooShortcuts.fileHeaders.company": "Your Company"
}
```

### Why does it generate `<tree>` instead of `<list>`?

The system automatically detects Odoo version:
- Odoo < 18: generates `<tree>`
- Odoo 18+: generates `<list>`

Make sure to select the correct version when prompted.

### How do I generate inherited views?

Use: `Odoo Shortcuts: Create Inherit Views`

Or use CodeLens on an existing model: `[Create Inherit View]`

## 🌳 Odoo Explorer

### How do I add my addons to the explorer?

The explorer automatically detects addons in your workspace. Make sure:
1. They have `__manifest__.py`
2. They are in the open workspace

### Can I view Odoo Core addons?

Yes, configure:

```json
{
  "odooShortcuts.odooServerPaths": ["/path/to/odoo"],
  "odooShortcuts.coreAddonPatterns": ["/odoo/addons/"]
}
```

### Why do some addons appear in gray?

Read-only addons (Core/Enterprise) appear with different icons and don't allow editing.

## 🔧 LSP and Autocomplete

### Why doesn't autocomplete work?

1. Wait for initial indexing to finish (progress bar)
2. Restart the LSP: `Odoo Shortcuts: Restart OWL/JS Language Server`
3. Verify files have `/** @odoo-module **/`

### How do I reindex JavaScript files?

Use: `Odoo Shortcuts: Reindex JavaScript Files (LSP)`

### What if the LSP doesn't start?

1. Check Developer Console (`Ctrl+Shift+I`) for errors
2. Restart VS Code
3. Reinstall the extension if necessary

## 💻 CodeLens

### Why don't I see CodeLens links?

1. Verify it's enabled: `odooFile.codelens.enabled: true`
2. Wait a few seconds (loads asynchronously)
3. File must be Python or JavaScript

### How do I disable CodeLens?

```json
{
  "odooFile.codelens.enabled": false
}
```

## 🐛 Common Errors

### "Addon not found"

Verify that:
1. Directory has `__manifest__.py`
2. You're in the correct workspace
3. Structure is valid for Odoo

### "Could not generate file"

Possible causes:
1. Write permissions in directory
2. File already exists
3. Invalid addon structure

### "ENOENT" error

Directory or file doesn't exist. Verify path and create necessary folders.

## ⚡ Performance

### How do I improve performance?

If you work with many addons:

1. Disable auto-refresh: `"odooShortcuts.autoRefresh": false`
2. Hide unused repositories
3. Exclude large directories in settings

### Why does the LSP use so much memory?

Initial indexing requires memory. You can:
1. Reduce paths in `odooServerPaths`
2. Restart VS Code periodically
3. Close unused files

## 📝 Other Questions

### Does it support Odoo 17/18/19?

Yes, the extension supports Odoo 14-19 and automatically adapts templates according to version.

### Does it work with Odoo.sh?

Yes, the extension works with any Odoo addon structure, including Odoo.sh.

### Can I use it with multiple workspaces?

Yes, the Odoo Explorer shows addons from all folders in the workspace.

### How do I report bugs or request features?

Open an issue on GitHub: https://github.com/mjavint/odoo-shortcuts/issues

### Where can I find more information?

- Full documentation: [docs/index.md](./index.md)
- Changelog: [CHANGELOG.md](../CHANGELOG.md)
- Repository: [GitHub](https://github.com/mjavint/odoo-shortcuts)

## 💡 Tips

### Productivity

1. **Use CodeLens** to generate code quickly
2. **Learn keyboard** shortcuts
3. **Configure automatic** headers for your files
4. **Explore the context menu** in Odoo Explorer

### Debugging

1. Check developer console for errors
2. Restart LSP if there are autocomplete issues
3. Verify paths are configured correctly

---

**Don't see your question?** Open an issue on GitHub or check the complete documentation.
