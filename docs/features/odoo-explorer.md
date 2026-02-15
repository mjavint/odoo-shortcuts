# Odoo Explorer

The Odoo Explorer provides a visual interface to navigate and manage your Odoo addons directly from VS Code.

![Odoo Explorer Overview](https://github.com/mjavint/odoo-shortcuts/blob/main/img/00-explorer.jpeg?raw=true)

## 🌳 Explorer Structure

The panel is divided into four sections:

### 1. Custom Addons
Shows addons from your workspace and custom repositories.

![Custom Addons View](https://github.com/mjavint/odoo-shortcuts/blob/main/img/01-explorer.jpeg?raw=true)

**Available Operations:**
- 📁 Navigate folder structure
- 📄 Open files
- ➕ Create new files/folders
- ✏️ Rename items
- 🗑️ Delete items
- 📋 Copy/Cut/Paste
- 🔍 Search in folder
- 📂 Reveal in system explorer
- 💻 Open in terminal

### 2. Odoo Core (Read-Only)
Shows Odoo Core addons detected in configured paths.

- Read-only access
- Useful for consulting source code
- Quick reference

### 3. Odoo Enterprise (Read-Only)
Shows Odoo Enterprise addons if available.

- Read-only access
- Requires Enterprise license

![Core and Enterprise View](https://github.com/mjavint/odoo-shortcuts/blob/main/img/explorer-core-enterprise-view.gif?raw=true)

### 4. Configuration Files
Shows `.conf` configuration files found.

**Operations:**
- Edit configuration
- Copy path
- Reveal in explorer

![Configuration Files](https://github.com/mjavint/odoo-shortcuts/blob/main/img/02-explorer.jpeg?raw=true)

## 🎯 Explorer Commands

### Title Bar

| Icon | Command | Description |
|-------|---------|-------------|
| 🔄 | Refresh | Update addons view |
| 🔍 | Filter | Filter addons by name |
| ❌ | Clear Filter | Clear current filter |
| 👁️ | Show All Hidden | Show hidden repositories |
| 📁 | New File | Create new file |
| 📂 | New Folder | Create new folder |

### Context Menu

Right-click on any item for:

**Addons/Repositories:**
- New Addon
- Filter Addons
- Refresh
- Hide Repository/Addon
- Show All Hidden

**Files:**
- Open File
- Copy
- Cut
- Paste
- Copy Path
- Copy Relative Path
- Reveal in Explorer
- Open in Terminal
- Find in Folder

![Search in Folder](https://github.com/mjavint/odoo-shortcuts/blob/main/img/search-in-folder.jpeg?raw=true)

**Folders:**
- New File
- New Folder
- (All file options)

## ⚙️ Configuration

### Odoo Server Paths

```json
{
  "odooShortcuts.odooServerPaths": [
    "/home/user/odoo",
    "/home/user/enterprise"
  ]
}
```

### Detection Patterns

**Core Addons:**
```json
{
  "odooShortcuts.coreAddonPatterns": [
    "/odoo/addons/",
    "/odoo/odoo/addons/",
    "/openerp/addons/"
  ]
}
```

**Enterprise:**
```json
{
  "odooShortcuts.enterpriseAddonPatterns": [
    "/enterprise/",
    "/odoo/enterprise/"
  ]
}
```

## 📁 Icons and Types

The explorer shows different icons by type:

- 🏢 **Repository** - Root of addon repository
- 📦 **Addon** - Odoo addon (with `__manifest__.py`)
- 📁 **Folder** - Standard directory
- 📄 **File** - Generic file
- 🐍 **Python** - `.py` files
- 🌐 **XML** - `.xml` files
- 📊 **CSV** - `.csv` files
- 🌍 **PO** - Translation `.po` files

## 🔍 Filters

### Filter Addons

1. Click the 🔍 icon in the title bar
2. Select the addons you want to see
3. Other addons are temporarily hidden

![Filter Addons](https://github.com/mjavint/odoo-shortcuts/blob/main/img/repos-filter.gif?raw=true)

### Hidden Repositories

- **Hide Repository** - Hides a specific repository
- **Hide Addon** - Hides a specific addon
- **Show All Hidden** - Shows all hidden items

![Hide/Show Repositories](https://github.com/mjavint/odoo-shortcuts/blob/main/img/hide-show-addon-repo.gif?raw=true)

## 🚀 Keyboard Shortcuts

| Action | Shortcut |
|--------|----------|
| Update addons | Configurable in VS Code |
| Filter addons | `Ctrl+K Ctrl+F` / `Cmd+K Cmd+F` |
| Create file | Context menu |
| Create folder | Context menu |

## 💡 Tips

### 1. Drag & Drop
The explorer supports drag and drop operations within the view.

### 2. Multi-selection
Use `Ctrl+Click` or `Cmd+Click` to select multiple items.

### 3. Command Integration
From the context menu you can directly access:
- Create Python files
- Create XML files
- Create JS components
- etc.

### 4. Automatic Synchronization
If you enable `odooShortcuts.autoRefresh`, the explorer updates automatically when file system changes are detected.

## 🐛 Troubleshooting

### My addons don't appear

1. Verify they have `__manifest__.py`
2. Configure `odooShortcuts.odooServerPaths`
3. Use the "Refresh" command

### Odoo Core/Enterprise not detected

1. Verify paths in `odooServerPaths`
2. Check patterns in `coreAddonPatterns` and `enterpriseAddonPatterns`
3. Ensure directories exist

### Slow performance

If you have many addons:
- Hide repositories you don't use
- Disable `autoRefresh` and update manually
- Exclude large directories in `.gitignore`

---

**Next:** [LSP and IntelliSense](./lsp-features.md)
