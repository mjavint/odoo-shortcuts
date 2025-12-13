# Odoo Shortcuts

> Supercharge your Odoo development workflow with intelligent scaffolding, debugging, and productivity tools.

[![Version](https://img.shields.io/visual-studio-marketplace/v/mvintg.odoo-file)](https://marketplace.visualstudio.com/items?itemName=mvintg.odoo-file)
[![Installs](https://img.shields.io/visual-studio-marketplace/i/mvintg.odoo-file)](https://marketplace.visualstudio.com/items?itemName=mvintg.odoo-file)
[![Rating](https://img.shields.io/visual-studio-marketplace/r/mvintg.odoo-file)](https://marketplace.visualstudio.com/items?itemName=mvintg.odoo-file&ssr=false#review-details)

Odoo Shortcuts is a comprehensive VS Code extension designed to boost your productivity when developing Odoo applications. Create scaffolds for addons, modules, models, views, controllers, wizards, reports, OWL components, and more with just a few clicks.

## 📋 Table of Contents

- [Features](#-features)
- [Installation](#-installation)
- [Quick Start](#-quick-start)
- [Core Features](#-core-features)
  - [OWL/JavaScript Language Server](#1-owljavascript-language-server-)
  - [Addon Explorer](#2-addon-explorer)
  - [Scaffold Generation](#3-scaffold-generation)
  - [CodeLens Integration](#4-codelens-integration)
  - [Server Management](#5-server-management)
  - [Model Fields Visual Editor](#6-model-fields-visual-editor-)
  - [XML Formatter](#7-xml-formatter-)
  - [Developer Tools](#8-developer-tools)
- [Commands](#-commands)
- [Configuration](#-configuration)
- [Keyboard Shortcuts](#-keyboard-shortcuts)
- [Known Issues](#-known-issues)
- [Contributing](#-contributing)
- [Support](#-support)

## 🎯 Features

### Core Capabilities

- **🚀 OWL/JavaScript Language Server (NEW!)** - Intelligent code completion, navigation, and type checking for OWL components
- **🎨 Model Fields Visual Editor (NEW!)** - Visual interface to manage Odoo model fields with CRUD operations
- **📝 XML Formatter (NEW!)** - Odoo-specific XML formatter with smart attribute splitting and tag spacing
- **🔍 Folder Search (NEW!)** - Quick search within specific folders in Odoo Explorer
- **🏗️ Intelligent Scaffolding** - Generate complete Odoo structures with proper imports and manifest updates
- **🔍 Smart Explorer** - Navigate your Odoo addons with a dedicated tree view
- **💡 CodeLens Integration** - Quick actions directly in your Python model files
- **🐛 Debug Support** - Integrated debugging for Python and JavaScript/OWL
- **🚀 Server Management** - Start, stop, and restart Odoo servers from VS Code
- **📝 Auto-refresh** - Tree view updates automatically when files are created or modified
- **🔧 XPath Tools** - Extract and evaluate XPath expressions from XML files
- **🌐 Translation Support** - Edit `.po` files with ease
- **📊 CSV to XML** - Convert CSV data files to Odoo XML format

## 📦 Installation

### Quick Install

1. Open the Extensions view (`Ctrl+Shift+X` or `Cmd+Shift+X`)
2. Search for "Odoo Shortcuts"
3. Click Install

[→ View on Marketplace](https://marketplace.visualstudio.com/items?itemName=mvintg.odoo-file)

## 🚀 Quick Start

1. **Open an Odoo workspace** containing addon folders
2. **Open the Odoo Explorer** (sidebar icon)
3. **Right-click** on any addon or folder to see available scaffold options
4. **Create your first model**:
   - Right-click on an addon → "Odoo Shortcuts" → "Odoo Python File" → "Model"
   - Enter model name (e.g., `sale.order.custom`)
   - Select Odoo version
   - Done! Model, views, and security files are created automatically

## 🎨 Core Features

### 1. OWL/JavaScript Language Server 🆕

#### Screenshots

| OWL/JavaScript Language Server |
|---|
| ![01](https://github.com/mjavint/odoo-shortcuts/blob/main/img/00-owl-lsp.png?raw=true) |
| ![02](https://github.com/mjavint/odoo-shortcuts/blob/main/img/01-owl-lsp.png?raw=true) |
| ![03](https://github.com/mjavint/odoo-shortcuts/blob/main/img/02-owl-lsp.png?raw=true) |
| ![04](https://github.com/mjavint/odoo-shortcuts/blob/main/img/03-owl-lsp.png?raw=true) |

A powerful Language Server Protocol (LSP) implementation providing intelligent code completion, navigation, and type checking for OWL/JavaScript development.

**✨ Key Features:**

#### Intelligent Code Completion

- **Auto-completion** for all functions, classes, hooks, and constants from OWL and your addons
- **Smart Auto-Import** - Automatically adds import statements
- **Member Completion** - Type `object.` to see all methods and properties

```javascript
// Example: Type and get instant suggestions
import { Component, useState } from '@odoo/owl';  // Auto-imported!

class MyComponent extends Component {
    setup() {
        this.state = useState({ count: 0 });  // Auto-complete
        this.  // Shows all Component methods
    }
}

MyComponent.  // Shows: template, components, props, etc.
```

#### Advanced Navigation

- **Go to Definition** (`F12`) - Jump to any symbol definition
- **Cross-Addon Navigation** - Navigate between addons seamlessly
- **Automatic OWL Detection** - Finds and indexes OWL library automatically

#### Rich Documentation

- **Hover Information** - View documentation on hover
- **Signature Help** - Parameter hints while typing
- **Type Information** - See parameter types and return types

#### Smart Type Inference

- Infers types from JSDoc, TypeScript annotations, and code patterns
- Tracks variable types through assignments
- Resolves chained property access

#### Comprehensive Symbol Support

- **OWL Framework**: Component, hooks (`useState`, `useRef`, `useEffect`), lifecycle methods
- **Odoo Core**: `registry`, `services`, common patterns
- **Custom Addons**: All your exported symbols
- **40+ Type Definitions** included

**🎯 Examples:**

```javascript
// Cross-addon imports with autocomplete
import { MyHelper } from '@my_addon/utils/helpers';

// Component with full IntelliSense
class MyComponent extends Component {
    static template = xml`<div>...</div>`;
    static components = { OtherComponent };  // Autocompletes from your addons

    setup() {
        this.state = useState({ items: [] });
        this.env.services.  // Autocompletes available services
    }
}
```

**⚡ Commands:**

- `Restart Odoo LSP` - Restart the language server
- `Reindex JavaScript` - Manually re-index all JavaScript files

---

### 2. Addon Explorer

A dedicated tree view for navigating your Odoo projects.
![Explorer 1](https://github.com/mjavint/odoo-shortcuts/blob/main/img/00-explorer.jpeg?raw=true)
![Explorer 2](https://github.com/mjavint/odoo-shortcuts/blob/main/img/01-explorer.jpeg?raw=true)
![Explorer 3](https://github.com/mjavint/odoo-shortcuts/blob/main/img/02-explorer.jpeg?raw=true)
![Explorer 4](https://github.com/mjavint/odoo-shortcuts/blob/main/img/03-explorer.jpeg?raw=true)
![Explorer 5](https://github.com/mjavint/odoo-shortcuts/blob/main/img/04-explorer.jpeg?raw=true)
![Explorer 6](https://github.com/mjavint/odoo-shortcuts/blob/main/img/05-explorer.jpeg?raw=true)

**Features:**
- 📁 Browse all addons in your workspace
- 🔍 Filter addons by repository (`Ctrl+K Ctrl+F` / `Cmd+K Cmd+F`)
- 📂 Hierarchical view of addon structure
- 🔄 Auto-refresh when files change
- ⚡ Quick actions via context menu

**Usage:**
1. Open the "Odoo Addons" view in the Activity Bar
2. Browse your addon structure
3. Right-click on any item for context actions

### 3. Scaffold Generation

Create complete Odoo structures with proper boilerplate code.

#### Python Files

**Command:** Right-click → Odoo Shortcuts → Odoo Python File

**Available Templates:**

| Type | Description | Creates |
|------|-------------|---------|
| **Model** | Standard Odoo model | Model class, views (form/tree/search), security access |
| **Inherit** | Inherit existing model | Inherited model with `_inherit` |
| **Wizard** | TransientModel wizard | Wizard model, view, and action |
| **Report** | Abstract report model | Report model with QWeb template |
| **Controller** | HTTP controller | Controller with routes |

**Example - Creating a Model:**
```python
# Input: sale.custom.line
# Generates: models/sale_custom_line.py

class SaleCustomLine(models.Model):
    _name = 'sale.custom.line'
    _description = 'Sale Custom Line'

    name = fields.Char(string='Name', required=True)
    # ... more fields
```

**Auto-generated files:**
- `models/sale_custom_line.py` - Model definition
- `views/sale_custom_line_views.xml` - Form, tree, and search views
- `security/ir.model.access.csv` - Access rights
- Updates `__init__.py` and `__manifest__.py` automatically

#### XML Files

**Command:** Right-click → Odoo Shortcuts → Odoo XML File

**Available Templates:**

| Type | Description | Creates |
|------|-------------|---------|
| **View** | UI views | Form, tree, kanban, calendar, graph, pivot, search views |
| **View Inherit** | Inherit existing view | View with XPath inheritance |
| **Window Actions** | Menu actions | `ir.actions.act_window` records |
| **Cron Actions** | Scheduled actions | `ir.cron` records |
| **Client Actions** | Client-side actions | `ir.actions.client` records |
| **Server Actions** | Server-side actions | `ir.actions.server` records |
| **Paper Format** | Report formats | `report.paperformat` records |

**Example - Creating Views:**
1. Right-click addon → Odoo XML File → View
2. Enter model name: `sale.order`
3. Select view types: Form, Tree, Search
4. Generated: `views/sale_order_views.xml` with all selected views

#### OWL Components

**Command:** Right-click → Odoo Shortcuts → Odoo JS File

**Available Templates:**

- Field components
- View widgets
- Actions
- Common components
- Public components
- Services

#### Security Files

**Command:** Right-click → Odoo Shortcuts → Odoo Security File

**Available Templates:**

- Security Groups (`res.groups`)
- Access Rights (`ir.model.access.csv`)
- Record Rules (`ir.rule`)

#### Tests

**Command:** Right-click → Odoo Shortcuts → Odoo Tests File

**Available Templates:**

- Python tests (TransactionCase, HttpCase, etc.)
- JavaScript/OWL tests

### 4. CodeLens Integration

Quick actions appear directly above your model definitions.

![CodeLens](https://github.com/mjavint/odoo-shortcuts/blob/main/img/codelens.jpeg?raw=true)

**Available Actions:**

```python
class SaleOrder(models.Model):
    _name = 'sale.order'
    _inherit = ['mail.thread']
    # ⬇️ CodeLens actions appear here:
    # Create Views | Create Report | Import Model | Import Security
```

- **Create Views** - Generate form, tree, and search views for the model
- **Create Report** - Generate QWeb report template
- **Import Model** - Add import to `__init__.py`
- **Import Security** - Add access rule to `ir.model.access.csv`

**For Inherited Models:**

- **Create Inherit Views** - Generate view inheritance structure

### 5. Server Management

Manage Odoo server instances directly from VS Code.

![Debug](https://github.com/mjavint/odoo-shortcuts/blob/main/img/debug.gif?raw=true)

**Features:**

- ▶️ Start Odoo server
- ⏹️ Stop Odoo server
- 🔄 Restart Odoo server
- 🐛 Debug Python (with breakpoints)
- 🐛 Debug JavaScript/OWL components
- 📊 Status bar integration
- 🔧 Configuration panel for server settings

**Configuration:**

1. Click the Odoo icon in the status bar
2. Create/edit server configurations
3. Set paths, ports, database settings
4. Save and launch

**Debug Configuration:**

```json
{
  "name": "Odoo",
  "type": "debugpy",
  "request": "launch",
  "program": "${workspaceFolder}/odoo-bin",
  "args": ["-c", "${workspaceFolder}/odoo.conf", "-d", "my_database"]
}
```

### 6. Model Fields Visual Editor 🆕

Manage Odoo model fields through an intuitive visual interface.
| Model Fields Visual Editor |
|---|
| ![Model Fields Editor1](https://github.com/mjavint/odoo-shortcuts/blob/main/img/01-model-editor-fields.jpeg?raw=true) |
| ![Model Fields Editor2](https://github.com/mjavint/odoo-shortcuts/blob/main/img/02-model-editor-fields.jpeg?raw=true) |

**✨ Key Features:**

#### Interactive Field Management

- **Visual Editor** - Manage model fields without writing code
- **Field CRUD** - Create, edit, and delete fields with intuitive forms
- **All Field Types** - Support for Char, Text, Integer, Float, Boolean, Date, Datetime, Selection, Many2one, One2many, Many2many, and more
- **Smart Attributes** - Priority attributes shown first based on field type
- **Real-time Sync** - Changes immediately reflected in Python files
- **Multi-Model Support** - Handle multiple models in the same file with tabs

#### Safety Features

- **Delete Confirmation** - Modal dialog confirms field deletion
- **Validation** - Required attributes validated before saving
- **Auto-formatting** - Generated code follows Odoo conventions
- **Backup Safe** - Only modifies model files, keeps backups via version control

**Usage:**

1. Right-click on a model file (`.py`) → "Open with Model Fields Editor"
2. Click **Add Field** to create a new field
3. Click on any field card to **edit** its properties
4. Click **Delete** button with confirmation to remove fields
5. All changes are immediately saved to the Python file

**Example Workflow:**

```python
# Before: Empty model
class SaleOrder(models.Model):
    _name = 'sale.order'
    _description = 'Sales Order'

# After: Using visual editor to add fields
class SaleOrder(models.Model):
    _name = 'sale.order'
    _description = 'Sales Order'

    name = fields.Char(string='Order Reference', required=True)
    partner_id = fields.Many2one('res.partner', string='Customer')
    date_order = fields.Datetime(string='Order Date', default=fields.Datetime.now)
    state = fields.Selection([
        ('draft', 'Draft'),
        ('confirmed', 'Confirmed'),
        ('done', 'Done')
    ], string='Status', default='draft')
```

**Supported Attributes:**

- **Common**: string, required, readonly, default, help, copy, index, store
- **Computed**: compute, related, depends, inverse, search
- **Relational**: comodel_name, inverse_name, relation, domain, context, ondelete
- **Selection**: selection, selection_add
- **Specific**: digits, currency_field, size, translate, sanitize, and many more

### 7. XML Formatter 🆕

A powerful and customizable XML formatter specifically designed for Odoo development.

**✨ Key Features:**

- **Odoo-Specific Formatting** - Understands Odoo XML structure and conventions
- **Smart Attribute Splitting** - Automatically splits attributes onto new lines when they exceed line length or for specific tags
- **Tag Spacing** - Automatically adds blank lines before major Odoo tags (record, menuitem, template, etc.)
- **Comment Preservation** - Keeps your comments exactly where you put them
- **QWeb Support** - Special handling for QWeb attributes (`t-`) ensuring they come first
- **Configurable** - Extensive configuration options to match your coding style
- **Exclude Patterns** - Prevent formatting of Odoo core and enterprise modules

**Recommended Configuration:**

Add this to your VS Code settings (`settings.json`) for optimal Odoo XML formatting:

```json
{
  "odooShortcuts.formatter.splitAttributes": true,
  "odooShortcuts.formatter.maxLineLength": 88,
  "odooShortcuts.formatter.odooSpacingTags": [
    "record",
    "menuitem"
  ],
  "odooShortcuts.formatter.excludePatterns": [
    "**/odoo/**",
    "**/enterprise/**"
  ]
}
```

**Configuration Options:**

- **splitAttributes**: Automatically split attributes onto new lines when they exceed `maxLineLength`
- **maxLineLength**: Maximum line length before attributes are split (default: 88, matching Python's Black formatter)
- **odooSpacingTags**: Tags that should have a blank line before them for better readability
- **excludePatterns**: File patterns to exclude from formatting (useful for core Odoo and enterprise modules)

**Usage:**

1. Open any XML file in your Odoo project
2. Right-click → "Format Document" or use `Shift+Alt+F` (Windows/Linux) / `Shift+Option+F` (Mac)
3. The formatter will automatically apply Odoo-specific formatting rules

### 8. Developer Tools

#### Folder Search in Odoo Explorer 🆕

Quickly search within specific folders of the Odoo Explorer.

![Folder Search](https://github.com/mjavint/odoo-shortcuts/blob/main/img/search-in-folder.jpeg?raw=true)

**Features:**

- **Quick Search** - Search within any folder using `Ctrl+F` (Windows/Linux) or `Cmd+F` (Mac)
- **Context Menu** - Right-click on any folder → "Search in Folder"
- **Scoped Results** - Only shows files within the selected folder
- **Fast Indexing** - Instant results with workspace indexing
- **Pattern Matching** - Supports wildcards and regex patterns

**Usage:**

1. Right-click on any folder in Odoo Explorer
2. Select "Search in Folder"
3. Enter search pattern (e.g., `*.py`, `sale_order`, `def create`)
4. Results filtered to selected folder only

**Benefits:**

- Find files quickly in large addon repositories
- Scope searches to specific modules or folders
- Reduce noise from workspace-wide searches
- Navigate large codebases efficiently

---

#### XPath Tools

Extract and work with XPath expressions from XML views.

![XPath](https://github.com/mjavint/odoo-shortcuts/blob/main/img/get-XPath-1.png?raw=true)

**Commands:**
- **Get Current XPath** - Copy XPath of current XML element
- **Evaluate XPath** - Test XPath expressions

**Usage:**
1. Open an XML file
2. Place cursor on an element
3. Right-click → Get XPath
4. XPath copied to clipboard

#### CSV to XML Converter

Convert CSV data files to Odoo XML format.

![CSV to XML](https://github.com/mjavint/odoo-shortcuts/blob/main/img/transform-csv-xml-data.gif?raw=true)

**Usage:**

1. Right-click on a CSV file
2. Select "Transform CSV to XML"
3. XML file generated with `noupdate="1"`

#### Translation Editor

Edit `.po` translation files with syntax highlighting and validation.

**Features:**

- Syntax highlighting
- Translation validation
- Quick navigation
- Search and replace

#### String Converters

- **Python** - Convert strings to f-strings
- **JavaScript** - Convert strings to template literals

**Usage:**

1. Select a string in code
2. Right-click → Convert to f-string/template literal

## 📝 Commands

All commands are accessible via:

- Command Palette (`Ctrl+Shift+P` / `Cmd+Shift+P`)
- Context menus (right-click)
- Keyboard shortcuts

### Scaffold Commands

| Command | Description |
|---------|-------------|
| `Odoo: Create New Addon` | Create a complete addon structure |
| `Odoo: Create Odoo Config` | Generate Odoo configuration file |
| `Odoo: Create Python Module` | Create a Python module folder |
| `Odoo: Python File` | Create Python files (Model, Wizard, etc.) |
| `Odoo: XML File` | Create XML files (Views, Actions, etc.) |
| `Odoo: Security File` | Create security files |
| `Odoo: JS File` | Create OWL/JavaScript components |
| `Odoo: Tests File` | Create test files |

### Server Commands

| Command | Description |
|---------|-------------|
| `Odoo: Start Server` | Start Odoo server |
| `Odoo: Stop Server` | Stop Odoo server |
| `Odoo: Restart Server` | Restart Odoo server |
| `Odoo: Debug Python` | Start Python debugger |
| `Odoo: Debug JavaScript` | Start JS/OWL debugger |

### Explorer Commands

| Command | Description |
|---------|-------------|
| `Odoo: Refresh Addons` | Refresh addon tree |
| `Odoo: Filter Addons` | Filter addons by repository |
| `Odoo: Clear Filter` | Clear addon filter |
| `Odoo: Collapse All` | Collapse all tree items |

### LSP Commands

| Command | Description |
|---------|-------------|
| `Odoo: Restart LSP` | Restart the OWL/JavaScript language server |
| `Odoo: Reindex JavaScript` | Manually re-index all JavaScript files |

### Developer Commands

| Command | Description |
|---------|-------------|
| `Odoo: Get XPath` | Copy XPath of current element |
| `Odoo: Evaluate XPath` | Evaluate XPath expression |
| `Odoo: Transform CSV to XML` | Convert CSV to XML |
| `Odoo: Translate PO File` | Open translation editor |
| `Odoo: Get Import Path` | Copy OWL import path |
| `Odoo: Open OWL File` | Quick open OWL component |

## ⚙️ Configuration

Configure the extension via VS Code settings (`Ctrl+,` / `Cmd+,`):

### General Settings

```json
{
  // Auto-open files after creation
  "odooShortcuts.openFiles": true,

  // Manifest file patterns to detect Odoo addons
  "odooShortcuts.manifestFiles": [
    "__manifest__.py",
    "__openerp__.py"
  ],

  // Auto-refresh tree view when files change
  "odooShortcuts.autoRefresh": true,

  // Custom documentation sites
  "odooShortcuts.sites": [
    {
      "label": "Odoo Documentation",
      "url": "https://www.odoo.com/documentation"
    },
    {
      "label": "OWL Documentation",
      "url": "https://github.com/odoo/owl"
    }
  ]
}
```

### Odoo Server Paths

Configure paths to Odoo core and enterprise addons for read-only exploration:

```json
{
  // Absolute paths to Odoo server directories (can be anywhere in your system)
  "odooShortcuts.odooServerPaths": [
    "/home/user/odoo",           // Linux/macOS
    "/opt/odoo/enterprise",      // Linux/macOS
    "C:\\odoo",                  // Windows
    "D:\\Projects\\odoo\\enterprise"  // Windows
  ],

  // Path patterns to detect Odoo core addons (shown as read-only)
  "odooShortcuts.coreAddonPatterns": [
    "/odoo/addons/",
    "/odoo/odoo/addons/",
    "/openerp/addons/"
  ],

  // Path patterns to detect Odoo enterprise addons (shown as read-only)
  "odooShortcuts.enterpriseAddonPatterns": [
    "/enterprise/",
    "/odoo/enterprise/"
  ]
}
```

### CodeLens Settings

```json
{
  // Enable/disable CodeLens for Odoo models
  "odooFile.codelens.enabled": true
}
```

### File Header Templates

Configure automatic file headers with license and copyright information:

```json
{
  // Enable automatic file headers
  "odooShortcuts.fileHeaders.enabled": false,

  // Author information
  "odooShortcuts.fileHeaders.author": "Your Name",
  "odooShortcuts.fileHeaders.email": "your.email@example.com",
  "odooShortcuts.fileHeaders.company": "Your Company",

  // License type
  "odooShortcuts.fileHeaders.license": "LGPL-3",
  // Options: "LGPL-3", "GPL-3", "AGPL-3", "MIT", "Apache-2.0", "BSD-3-Clause", "Custom"

  // Custom license text (when license is "Custom")
  "odooShortcuts.fileHeaders.customLicense": "",

  // Python file header template
  "odooShortcuts.fileHeaders.pythonTemplate": "# -*- coding: utf-8 -*-\n# Copyright {{year}} {{company}}\n# License {{license}}\n\n",

  // XML file header template
  "odooShortcuts.fileHeaders.xmlTemplate": "<?xml version=\"1.0\" encoding=\"utf-8\"?>\n<!--\n  Copyright {{year}} {{company}}\n  License {{license}}\n-->\n\n",

  // JavaScript file header template
  "odooShortcuts.fileHeaders.javascriptTemplate": "/** @odoo-module **/\n// Copyright {{year}} {{company}}\n// License {{license}}\n\n"
}
```

**Available template variables:**
- `{{year}}` - Current year
- `{{author}}` - Author name
- `{{email}}` - Author email
- `{{company}}` - Company name
- `{{license}}` - License type
- `{{date}}` - Current date (YYYY-MM-DD)

### Environment Variables

Configure shell files to read environment variables from:

```json
{
  // Shell configuration files for environment variable expansion
  "odooShortcuts.envFiles": [
    "~/.zshrc",
    "~/.bashrc",
    "~/.bash_profile",
    "~/.env"
  ]
}
```

**Usage in launch configurations:**
```json
{
  "label": "Production",
  "odooBinPath": "${HOME}/odoo/odoo-bin",
  "config": [
    "--database", "$DB_NAME",
    "--db-host", "${DB_HOST}"
  ]
}
```

### Server Settings

Configure Odoo servers via the Configuration Panel (status bar icon) or directly in `.vscode/shortcuts.json`:

```json
{
  "configurations": [
    {
      "label": "Odoo 17 - Development",
      "config": [
        "/path/to/odoo-bin",
        "-c", "/path/to/odoo.conf",
        "-d", "odoo17_dev",
        "-u", "all"
      ]
    }
  ]
}
```

## ⌨️ Keyboard Shortcuts

### Windows/Linux

| Shortcut | Command | Description |
|----------|---------|-------------|
| `Ctrl+Shift+D` | Open OWL File | Open file from import and navigate to definition |
| `Ctrl+K N` | Start Odoo Server | Start the Odoo server with selected configuration |
| `Ctrl+K Ctrl+N` | Debug Odoo Server | Start Odoo server in debug mode |
| `Ctrl+K J` | Debug JavaScript | Start JavaScript/OWL debugger |
| `Ctrl+K Ctrl+A` | Open Configuration | Open Odoo launch configuration panel |
| `Ctrl+K Ctrl+F` | Filter Addons | Filter addons in Odoo Explorer |

### macOS

| Shortcut | Command | Description |
|----------|---------|-------------|
| `Cmd+Shift+D` | Open OWL File | Open file from import and navigate to definition |
| `Cmd+K N` | Start Odoo Server | Start the Odoo server with selected configuration |
| `Cmd+K Cmd+N` | Debug Odoo Server | Start Odoo server in debug mode |
| `Cmd+K J` | Debug JavaScript | Start JavaScript/OWL debugger |
| `Cmd+K Cmd+A` | Open Configuration | Open Odoo launch configuration panel |
| `Cmd+K Cmd+F` | Filter Addons | Filter addons in Odoo Explorer |

## 🐛 Known Issues

Report issues at: [GitHub Issues](https://github.com/mjavint/odoo-shortcuts/issues)

## 📞 Support

### Get Help

- 📖 [Documentation](https://github.com/mjavint/odoo-shortcuts)
- 🐛 [Report Issues](https://github.com/mjavint/odoo-shortcuts/issues)
- ⭐ [Rate & Review](https://marketplace.visualstudio.com/items?itemName=mvintg.odoo-file&ssr=false#review-details)

### Maintainer

- **Ing. Manuel Vinent Guilarte** - [mjavint@gmail.com](mailto:mjavint@gmail.com)

## 📄 License

This extension is licensed under the [MIT License](LICENSE).

## 🎉 Acknowledgments

Special thanks to all contributors and users who have helped improve this extension!

---

**Enjoy developing with Odoo Shortcuts!** 🚀

If you find this extension helpful, please consider:

- ⭐ [Starring the repository](https://github.com/mjavint/odoo-shortcuts)
- ✍️ [Leaving a review](https://marketplace.visualstudio.com/items?itemName=mvintg.odoo-file&ssr=false#review-details)
- 🐛 [Reporting issues](https://github.com/mjavint/odoo-shortcuts/issues)
- 🤝 [Contributing](https://github.com/mjavint/odoo-shortcuts/pulls)
