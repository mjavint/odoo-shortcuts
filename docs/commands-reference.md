# Commands Reference

Complete list of all commands available in Odoo Shortcuts.

## 📋 Command Table

### Code Generation (Scaffold)

| Command | ID | Description |
|---------|-----|-------------|
| **New Addon** | `odooShortcuts.createNewAddonCommand` | Create complete addon structure |
| **New Module** | `odooShortcuts.createNewModuleCommand` | Create basic module |
| **New Model** | `odooShortcuts.createNewModelCommand` | Generate Python model with views |
| **New Inherit Model** | `odooShortcuts.createInheritModelCommand` | Create inherited model |
| **New Wizard** | `odooShortcuts.createWizardCommand` | Generate wizard |
| **New Controller** | `odooShortcuts.createNewControllerCommand` | Create HTTP controller |
| **New Report** | `odooShortcuts.createReportCommand` | Generate QWeb report |
| **New Paper Format** | `odooShortcuts.createNewPaperFormatCommand` | Create paper format |

### XML Views

| Command | ID | Description |
|---------|-----|-------------|
| **Create Views** | `odooShortcuts.createViewsCommand` | Generate views for a model |
| **Create Inherit Views** | `odooShortcuts.createInheritViewsCommand` | Create inherited views |
| **New View** | `odooShortcuts.selectOdooXmlFileCommand` | View scaffold |

### Actions

| Command | ID | Description |
|---------|-----|-------------|
| **New Server Actions** | `odooShortcuts.selectOdooXmlFileCommand` | Server actions |
| **New Client Actions** | `odooShortcuts.selectOdooXmlFileCommand` | Client actions |
| **New Cron Actions** | `odooShortcuts.selectOdooXmlFileCommand` | Scheduled tasks |
| **Create Report Action** | `odooShortcuts.createReportActionCommand` | Report action |

### OWL / JavaScript

| Command | ID | Description |
|---------|-----|-------------|
| **New OWL Component** | `odooShortcuts.createOWLComponentCommand` | OWL component |
| **New OWL Service** | `odooShortcuts.createOWLServiceCommand` | OWL service |
| **New JS File** | `odooShortcuts.selectOdooJSFileCommand` | JavaScript file |

### Security and Tests

| Command | ID | Description |
|---------|-----|-------------|
| **New Security File** | `odooShortcuts.selectOdooSecurityFileCommand` | Security file |
| **Import Security Access** | `odooShortcuts.importSecurityAccessCommand` | Access rules |
| **New Tests File** | `odooShortcuts.selectOdooTestsFileCommand` | Tests file |

### Configuration

| Command | ID | Description |
|---------|-----|-------------|
| **New Odoo Configuration** | `odooShortcuts.createOdooConfigCommand` | .conf file |
| **Open Config Args** | `odooShortcuts.openWebViewCommand` | Configure arguments |
| **Status Bar Arguments** | `odooShortcuts.statusBarArgsCommand` | Show arguments |

### Odoo Explorer

| Command | ID | Description |
|---------|-----|-------------|
| **Refresh Addons** | `odooShortcuts.refreshAddonCommand` | Update view |
| **Refresh Config** | `odooShortcuts.refreshConfigCommand` | Update configs |
| **Filter Addons** | `odooShortcuts.addon.filter` | Filter addons |
| **Clear Filter** | `odooShortcuts.addon.clearFilter` | Clear filter |
| **Collapse All** | `odooShortcuts.collapseAllItemsCommand` | Collapse all |

### File Operations (Explorer)

| Command | ID | Description |
|---------|-----|-------------|
| **New File** | `odooShortcuts.addon.newFile` | Create file |
| **New Folder** | `odooShortcuts.addon.newFolder` | Create folder |
| **Delete Item** | `odooShortcuts.addon.delete` | Delete item |
| **Rename Item** | `odooShortcuts.addon.rename` | Rename item |
| **Copy** | `odooShortcuts.addon.copy` | Copy item |
| **Cut** | `odooShortcuts.addon.cut` | Cut item |
| **Paste** | `odooShortcuts.addon.paste` | Paste item |
| **Copy Path** | `odooShortcuts.addon.copyPath` | Copy path |
| **Copy Relative Path** | `odooShortcuts.addon.copyRelativePath` | Copy relative path |
| **Reveal in Explorer** | `odooShortcuts.addon.revealInExplorer` | Show in system |
| **Open in Terminal** | `odooShortcuts.addon.openInTerminal` | Open terminal |
| **Find in Folder** | `odooShortcuts.addon.findInFolder` | Search in folder |

### Visibility

| Command | ID | Description |
|---------|-----|-------------|
| **Hide Repository** | `odooShortcuts.addon.hideRepository` | Hide repository |
| **Hide Addon** | `odooShortcuts.addon.hideAddon` | Hide addon |
| **Show All Hidden** | `odooShortcuts.addon.showAllHidden` | Show hidden |

### LSP

| Command | ID | Description |
|---------|-----|-------------|
| **Restart LSP** | `odooShortcuts.restartLsp` | Restart server |
| **Reindex JavaScript** | `odooShortcuts.reindexJavaScript` | Reindex JS |

### Debug

| Command | ID | Description |
|---------|-----|-------------|
| **Debug Odoo** | `odooShortcuts.debugOdooCommand` | Start Python debug |
| **Debug JS** | `odooShortcuts.debugJSCommand` | Debug JavaScript |
| **Start Odoo Server** | `odooShortcuts.startOdooServerCommand` | Start server |
| **Restart Odoo Server** | `odooShortcuts.restartOdooServerCommand` | Restart server |
| **Stop Odoo Server** | `odooShortcuts.stopOdooServerCommand` | Stop server |

### Utilities

| Command | ID | Description |
|---------|-----|-------------|
| **Get XPath** | `odooShortcuts.getCurrentXPathCommand` | Get XPath |
| **Get Import Path** | `odooShortcuts.getImportPathCommand` | Copy import path |
| **Translate PO File** | `odooShortcuts.translatePoFileCommand` | Translate PO file |
| **Transform CSV to XML** | `odooShortcuts.transformCsv2XmlCommand` | Convert CSV |
| **Open OWL File** | `odooShortcuts.openOwlFileCommand` | Go to definition |
| **Open OWL Doc** | `odooShortcuts.openOwlDocWebViewCommand` | OWL documentation |
| **Open FontAwesome** | `odooShortcuts.openFaViewCommand` | FontAwesome icons |
| **Open Model Fields Editor** | `odooShortcuts.openModelFieldsEditor` | Fields editor |
| **Import Model** | `odooShortcuts.importModelCommand` | Import model |
| **Reveal in Explorer** | `odooShortcuts.revealInExplorerCommand` | Show in system |
| **Update Configuration** | `odooShortcuts.updateConfigCommand` | Update config |

## 🔍 How to Use

### Command Palette

1. `Ctrl+Shift+P` (Windows/Linux) or `Cmd+Shift+P` (Mac)
2. Type "Odoo Shortcuts"
3. Select desired command

### Context Menu

Many commands are available in the context menu of:
- **Odoo Explorer** - Right-click on addons/files
- **Editor** - Right-click on code

### CodeLens

Some commands appear as links above code:
- Above Python models
- Above OWL components

## 🎯 Keyboard Shortcuts

Many commands have configurable keyboard shortcuts. See [Keyboard Shortcuts](./keybindings.md).

---

**Next:** [FAQ](./faq.md)
