# Configuration

Odoo Shortcuts offers multiple configuration options to customize behavior according to your needs.

| Configuration Panel |
|:---:|
| ![Panel Config Dark](https://github.com/mjavint/odoo-shortcuts/blob/main/img/panel-config-dark.png?raw=true) |
| ![Panel Config Light](https://github.com/mjavint/odoo-shortcuts/blob/main/img/panel-config-light.png?raw=true) |

## ⚙️ Accessing Settings

1. **Settings UI:** `Ctrl+,` (Windows/Linux) or `Cmd+,` (Mac)
2. **Settings JSON:** Open Command Palette → "Preferences: Open Settings (JSON)"

## 📋 Complete Configuration

### Odoo Server Paths

**Setting:** `odooShortcuts.odooServerPaths`

Defines where Odoo source files are installed so the LSP can index them.

```json
{
  "odooShortcuts.odooServerPaths": [
    "/home/user/odoo",
    "/home/user/enterprise",
    "/opt/odoo/odoo"
  ]
}
```

**Note:** These paths are used for autocomplete and code navigation.

---

### Addon Detection

**Core Addons:** `odooShortcuts.coreAddonPatterns`

```json
{
  "odooShortcuts.coreAddonPatterns": [
    "/odoo/addons/",
    "/odoo/odoo/addons/",
    "/openerp/addons/"
  ]
}
```

**Enterprise Addons:** `odooShortcuts.enterpriseAddonPatterns`

```json
{
  "odooShortcuts.enterpriseAddonPatterns": [
    "/enterprise/",
    "/odoo/enterprise/"
  ]
}
```

---

### Manifest Files

**Setting:** `odooShortcuts.manifestFiles`

Files that identify an Odoo addon.

```json
{
  "odooShortcuts.manifestFiles": [
    "__manifest__.py"
  ]
}
```

---

### Automatic Refresh

**Setting:** `odooShortcuts.autoRefresh`

```json
{
  "odooShortcuts.autoRefresh": true
}
```

When enabled, the Odoo Explorer updates automatically when file system changes are detected.

---

### CodeLens

**Setting:** `odooFile.codelens.enabled`

```json
{
  "odooFile.codelens.enabled": true
}
```

Enables/disables CodeLens links on models and components.

---

### File Headers

#### Enable Headers

![Header License 1](https://github.com/mjavint/odoo-shortcuts/blob/main/img/00-header-license.png?raw=true)

```json
{
  "odooShortcuts.fileHeaders.enabled": true
}
```

#### Author Information

![Header License 2](https://github.com/mjavint/odoo-shortcuts/blob/main/img/01-header-license.png?raw=true)

```json
{
  "odooShortcuts.fileHeaders.author": "Your Name",
  "odooShortcuts.fileHeaders.email": "your@email.com",
  "odooShortcuts.fileHeaders.company": "Your Company",
  "odooShortcuts.fileHeaders.license": "LGPL-3"
}
```

**Available licenses:**
- `LGPL-3`
- `GPL-3`
- `AGPL-3`
- `MIT`
- `Apache-2.0`
- `BSD-3-Clause`
- `Custom`

#### Custom Template

```json
{
  "odooShortcuts.fileHeaders.customLicense": "Copyright (c) 2024 Your Company. All rights reserved.",
  "odooShortcuts.fileHeaders.pythonTemplate": "# -*- coding: utf-8 -*-\n# Copyright {{year}} {{company}}\n# License {{license}}\n\n",
  "odooShortcuts.fileHeaders.xmlTemplate": "<?xml version=\"1.0\" encoding=\"utf-8\"?>\n<!--\n  Copyright {{year}} {{company}}\n  License {{license}}\n-->\n\n",
  "odooShortcuts.fileHeaders.javascriptTemplate": "/** @odoo-module **/\n// Copyright {{year}} {{company}}\n// License {{license}}\n\n"
}
```

**Available variables:**
- `{{year}}` - Current year
- `{{author}}` - Author name
- `{{email}}` - Author email
- `{{company}}` - Company name
- `{{license}}` - License type
- `{{date}}` - Full date

---

### File Opening

**Setting:** `odooShortcuts.openFiles`

```json
{
  "odooShortcuts.openFiles": true
}
```

When enabled, generated files open automatically in the editor.

---

### Shell Configuration

**Setting:** `odooShortcuts.envFiles`

```json
{
  "odooShortcuts.envFiles": [
    "~/.zshrc",
    "~/.bashrc",
    "~/.bash_profile"
  ]
}
```

Shell configuration files to read environment variables from.

---

### XML Formatter

See [XML Formatter](./features/formatter.md) for detailed options.

```json
{
  "odooShortcuts.formatter.tabSize": 4,
  "odooShortcuts.formatter.splitAttributes": false,
  "odooShortcuts.formatter.emptyElementHandling": "selfClosing",
  "odooShortcuts.formatter.preserveComments": true,
  "odooShortcuts.formatter.odooTagSpacing": true
}
```

---

## 📝 Complete Configuration Example

```json
{
  // Odoo Shortcuts Configuration
  "odooShortcuts.odooServerPaths": [
    "/home/developer/odoo",
    "/home/developer/enterprise"
  ],
  "odooShortcuts.coreAddonPatterns": [
    "/odoo/addons/"
  ],
  "odooShortcuts.enterpriseAddonPatterns": [
    "/enterprise/"
  ],
  "odooShortcuts.autoRefresh": true,
  "odooShortcuts.openFiles": true,

  // CodeLens
  "odooFile.codelens.enabled": true,

  // File Headers
  "odooShortcuts.fileHeaders.enabled": true,
  "odooShortcuts.fileHeaders.author": "John Doe",
  "odooShortcuts.fileHeaders.email": "john@example.com",
  "odooShortcuts.fileHeaders.company": "My Company",
  "odooShortcuts.fileHeaders.license": "LGPL-3",

  // Formatter
  "odooShortcuts.formatter.tabSize": 4,
  "odooShortcuts.formatter.preserveComments": true,
  "odooShortcuts.formatter.odooTagSpacing": true
}
```

## 🎯 Workspace Configuration

You can have different configurations per project. VS Code saves them in `.vscode/settings.json` within your workspace.

```json
// .vscode/settings.json
{
  "odooShortcuts.odooServerPaths": [
    "${workspaceFolder}/../odoo"
  ]
}
```

---

**Next:** [Keybindings](./keybindings.md)
