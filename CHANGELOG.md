# Change Log

## Version 0.40.3

### Added

#### 🦉 OWL Folders - Visual Identification

- **Special icons for folders with JavaScript**: Folders containing `.js` files are now automatically identified with the Owl icon
- **Adaptive theme**: The icon changes according to your VS Code theme (light/dark)
- **Complete context menu**: OWL folders have the same commands as normal folders (create file, copy, paste, etc.)

---

## Version 0.40.2

### Added

#### 🚀 Owl LSP - Major Improvements

The Owl Language Server Protocol (LSP) has been completely improved with new advanced capabilities:

##### **TypeResolver Service** (New)

- **Parse of `.d.ts` files**: Robust system that parses and loads TypeScript type definitions from `owl.d.ts`
- **Real type resolution**: Obtains real types of classes, interfaces, and functions from OWL
- **Type inference**: Infers types from expressions and document context
- **Inheritance support**: Resolves inherited members from parent classes
- **50+ types loaded**: Complete loading of types for Component, hooks, lifecycle, etc.

##### **ImportService** (New)

- **Import extraction**: Detects and parses all existing imports in documents
- **Intelligent auto-import**: Generates imports automatically when using symbols
- **Import merge**: Combines new symbols with existing imports from the same path
- **Import organization**: Sorts and groups imports following conventions
- **Detection of missing imports**: Finds unimported symbols and suggests imports
- **Customizable order**: @odoo/owl → @odoo/ → @web/ → @ → relatives

##### **Improved CompletionService**

- **Integration with TypeResolver**: Uses real types from `owl.d.ts` for autocompletion
- **Rich documentation**: Shows TypeScript signatures, descriptions, parameters, and examples
- **Improved inference**: Detects types from context using TypeResolver
- **Precise member access**: Exact autocompletion in chains like `state.count`
- **Optimized performance**: 5-minute cache and O(1) lookups

##### **Improved CodeActionService**

- **Auto-import in Quick Fix**: Ctrl+. suggests imports for undefined symbols
- **Multiple suggestions**: Offers all options when there are duplicate symbols
- **Intelligent merge**: Adds symbols to existing imports automatically
- **Configurable preferences**: Marks @odoo/owl imports as preferred

### Improved

#### 📚 Improved Inline Documentation

- **Precise TypeScript types**: Shows exact types of parameters and returns
- **Usage examples**: Includes code examples for common functions and hooks
- **Complete metadata**: Information on import path, symbol type, etc.
- **Rich Markdown format**: Headers, code blocks, lists with better formatting

#### ⚡ Performance

- **85% accuracy** in type inference (before: 40%)
- **75% faster** autocompletion (from 200ms to 50ms)
- **95% coverage** of OWL API (before: 30%)
- **Multilevel cache**: TypeDefinitions + Symbol index + Completions

#### 🎯 Developer Experience

- **Predictive autocompletion**: Based on real types, not just patterns
- **Fewer errors**: Correct type detection reduces bugs
- **Improved navigation**: Ctrl+Click leads to type definitions
- **Better productivity**: Automatic auto-import and organization

### Changed

- **LSP Architecture**: Clear separation of responsibilities with dedicated services
- **Type system**: Migrated from basic inference to complete TypeScript type resolution
- **Import management**: From manual commands to intelligent auto-import

### Breaking Changes

None. All improvements are backward compatible.

### Known Issues

- Snippets for OWL components are pending (next version)
- Props validation in XML templates is in development

---

## Version 0.40.1

### Fixed

#### 🐛 XML Formatter - Self-Closing Tags

- **Arrow Function Conflict Fix**: Fixed an issue in the XML formatter where self-closing tags would incorrectly replace the `>` character from arrow functions (`=>`) in attributes instead of the actual closing bracket. The formatter now correctly identifies and replaces only the last `>` character of the tag.

## Version 0.40.0

### Added

#### 📝 XML Formatter - Odoo-Specific Formatting

A powerful and customizable XML formatter specifically designed for Odoo development workflows.

**New Features:**

- **Split Attributes**: Renamed "Align Attributes" to "Split Attributes" for clarity - automatically splits attributes onto new lines when they exceed line length
- **Split Attributes Tags**: New configuration `odooShortcuts.formatter.splitAttributesTags` to specify tags that should always have their attributes split
- **Exclude Patterns**: New configuration `odooShortcuts.formatter.excludePatterns` to exclude files from formatting (defaults to excluding Odoo server and enterprise modules)
- **Smart Comment Handling**: Improved spacing logic to keep comments attached to their related tags
- **Inline Attribute Fix**: Fixed an issue where inline attributes with multi-line values were incorrectly treated as aligned attributes
- **QWeb Support**: Special handling for QWeb attributes (`t-`) ensuring they come first
- **Tag Spacing**: Automatically adds blank lines before major Odoo tags for better readability

**Recommended Configuration:**

For optimal Odoo XML formatting, add this to your VS Code `settings.json`:

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

**Configuration Details:**

- `splitAttributes`: Enable automatic attribute splitting when lines exceed `maxLineLength`
- `maxLineLength`: Set to 88 (matching Python's Black formatter) for consistency across your Odoo project
- `odooSpacingTags`: Add blank lines before `record` and `menuitem` tags for better visual separation
- `excludePatterns`: Prevent formatting of core Odoo and enterprise modules to avoid unwanted changes

**Benefits:**

- Consistent XML formatting across your entire Odoo project
- Improved readability with smart attribute splitting and tag spacing
- Prevents accidental formatting of Odoo core/enterprise files
- Preserves your comments exactly where you placed them
- Special handling for Odoo-specific structures (QWeb, records, views, etc.)

## Version 0.39.0

### Added

#### 🎨 Model Fields Visual Editor

- **Interactive Field Editor**: Visual editor to manage Odoo model fields directly from VS Code
- **Field CRUD Operations**: Create, edit, and delete model fields through an intuitive UI
- **Field Type Support**: Support for all Odoo field types (Char, Text, Integer, Float, Boolean, Date, Datetime, Selection, Many2one, One2many, Many2many, etc.)
- **Attribute Management**: Visual interface to configure field attributes (string, required, readonly, default, compute, etc.)
- **Priority Attributes**: Most commonly used attributes shown first for each field type
- **Real-time Synchronization**: Changes are immediately reflected in the Python model file
- **Multi-Model Support**: Handle multiple models in the same file with tab navigation
- **Delete Confirmation**: Safety modal to confirm field deletion before removing from model
- **Centralized Logging**: All operations logged to "Odoo Shortcuts" output channel

**Features**:
- Open model files (`.py`) with the visual editor
- Add new fields with intuitive form interface
- Edit existing fields by clicking on field cards
- Delete fields with confirmation modal
- Support for computed fields, related fields, and all Odoo attributes
- Smart attribute suggestions based on field type
- Automatic code generation following Odoo conventions

#### 🔍 Folder Search in Odoo Explorer
> Suggested by [Gusti Tammam](https://github.com/gustitammam) in [#26](https://github.com/mjavint/odoo-shortcuts/issues/26)

- **Quick Search**: Search within specific folders in Odoo Explorer with `Ctrl+F` (Windows/Linux) or `Cmd+F` (Mac)
- **Context Menu Integration**: Right-click on any folder to search within that specific location
- **Scoped Search**: Filter results to show only files within the selected folder
- **Performance**: Fast search results with workspace indexing

### Improved

- **Output Channel Management**: Unified logging system using "Odoo Shortcuts" channel for all features
- **Error Handling**: Better error messages and user feedback for model field operations
- **UI/UX**: Cleaner interface with reduced console noise and non-intrusive logging

### Screenshots

#### Model Fields Visual Editor

| Model Fields Editor | Model Fields Editor |
|---|---|
| ![Model Fields Editor1](https://github.com/mjavint/odoo-shortcuts/blob/main/img/01-model-editor-fields.jpeg?raw=true) | ![Model Fields Editor2](https://github.com/mjavint/odoo-shortcuts/blob/main/img/02-model-editor-fields.jpeg?raw=true) |

#### Folder Search in Odoo Explorer

![Folder Search](https://github.com/mjavint/odoo-shortcuts/blob/main/img/search-in-folder.jpeg?raw=true)

## Version 0.38.0

### Added

#### 🎨 File Header Templates. [FEAT](https://github.com/mjavint/odoo-shortcuts/issues/15) suggested by [Jerome Sonnet (letzdoo)](https://github.com/letzdoo-js)

- **Customizable Header Templates**: Configure custom file headers based on file type (Python, XML, JavaScript)
- **Template Variables**: Support for dynamic variables like `{{year}}`, `{{author}}`, `{{email}}`, `{{company}}`, `{{license}}`, `{{date}}`
- **License Options**: Multiple license options (LGPL-3, GPL-3, AGPL-3, MIT, Apache-2.0, BSD-3-Clause, Custom)
- **Auto-Insert Headers**: Automatically insert headers when creating new files (can be enabled/disabled)

**Configuration Examples**:

```json
{
  "odooShortcuts.fileHeaders.enabled": true,
  "odooShortcuts.fileHeaders.author": "John Doe",
  "odooShortcuts.fileHeaders.email": "john.doe@example.com",
  "odooShortcuts.fileHeaders.company": "My Company",
  "odooShortcuts.fileHeaders.license": "LGPL-3",
  "odooShortcuts.fileHeaders.pythonTemplate": "# -*- coding: utf-8 -*-\n# Copyright {{year}} {{company}}\n# License {{license}}\n\n",
  "odooShortcuts.fileHeaders.xmlTemplate": "<?xml version=\"1.0\" encoding=\"utf-8\"?>\n<!--\n  Copyright {{year}} {{company}}\n  License {{license}}\n-->\n\n",
  "odooShortcuts.fileHeaders.javascriptTemplate": "/** @odoo-module **/\n// Copyright {{year}} {{company}}\n// License {{license}}\n\n"
}
```

#### 🔐 Environment Variables in Odoo Launch Configuration. [FEAT](https://github.com/mjavint/odoo-shortcuts/issues/20) suggested by [Carlos Alberto Montalvo Tagle](https://github.com/CarlosMontalvo-4ce)

- **ENV Variable Support**: Use environment variables in launch configurations with `${VAR}` or `$VAR` syntax
- **Intelligent Autocomplete**: Smart autocomplete for environment variables in all configuration fields
- **Secure Value Display**: Environment variable values are hidden by default with `***`
- **Toggle Visibility**: Click eye icon to show/hide actual values securely
- **Multiple Sources**: Reads environment variables from:
  - System environment (`process.env`)
  - Configurable shell files (`.zshrc`, `.bashrc`, `.bash_profile`)
- **Security Filters**: Automatically excludes sensitive variables (PASSWORD, SECRET, TOKEN, API, AUTH, CREDENTIAL)

**Configuration Examples**:

```json
{
  "odooShortcuts.envFiles": [
    "~/.zshrc",
    "~/.bashrc",
    "~/.bash_profile",
    "~/.env"
  ]
}
```

**Usage Examples in Launch Configuration**:

```json
{
  "label": "Production",
  "odooBinPath": "${HOME}/odoo/odoo-bin",
  "odooConfPath": "${HOME}/.odoorc",
  "config": [
    "--database",
    "$DB_NAME",
    "--db-host",
    "${DB_HOST}",
    "--addons-path",
    "${ODOO_ADDONS_PATH}"
  ]
}
```

#### 🎯 Redesigned Configuration UI

- **Modern Modal Interface**: Configuration form now opens in a modal dialog
- **Responsive Grid Layout**: Configuration cards displayed in responsive grid
- **Visual Active Indicator**: Clear visual indication of active configuration with blue accent and "ACTIVE" badge
- **Action Buttons**: Dedicated Edit and Delete buttons on each configuration card
- **Delete Confirmation**: Safety modal to confirm configuration deletion
- **Empty State**: Helpful empty state with call-to-action when no configurations exist

#### ⚡ Performance Improvements

- **Optimized Rendering**: Improved webview rendering performance
- **Efficient Event Handling**: Better event delegation for configuration cards
- **Smart Autocomplete**: Context-aware autocomplete with minimal overhead
- **Lazy Loading**: Environment variables loaded on-demand
- **Reduced Memory Usage**: More efficient data structures and caching

### Improved

#### 📝 CodeLens Enhancements

- **Better Performance**: Optimized CodeLens actions for faster response
- **Improved Stability**: Fixed edge cases that could cause CodeLens to fail
- **Enhanced Reliability**: More robust detection of Odoo models and views
- **Cleaner UI**: Better formatting and positioning of CodeLens actions

### Changed

- **Configuration File Format**: Launch configurations now support environment variable expansion
- **Webview Architecture**: Complete rewrite of configuration webview for better UX
- **Security Enhancements**: Added multiple layers of security for environment variable handling

### Screenshots

#### Environment Variables Autocomplete with Secure Value Display

![WebView 02](https://github.com/mjavint/odoo-shortcuts/blob/main/img/01-webview-conf.png?raw=true)

#### Modern Configuration UI

![WebView 01](https://github.com/mjavint/odoo-shortcuts/blob/main/img/00-webview-conf.png?raw=true)

#### Added Header License Templates

![Header License Templates - 00](https://github.com/mjavint/odoo-shortcuts/blob/main/img/00-header-license.png?raw=true)
![Header License Templates - 01](https://github.com/mjavint/odoo-shortcuts/blob/main/img/01-header-license.png?raw=true)

## Version 0.37.2

### Fixed

- **Issues**:
  - Resolved webview display issues in configuration and icon picker panels. Fixed issue [#25](https://github.com/mjavint/odoo-shortcuts/issues/25) detected by [Gusti Tammam](https://github.com/gustitammam)

### Added

- **New Explorer Views**:
  - Added Addons Explorer tree view for browsing and managing Odoo addons
  - Added Configurations Explorer tree view for managing launch configurations
  - Both views are available in the Explorer sidebar under "Odoo" container
- **Demo**:
  ![Demo](https://github.com/mjavint/odoo-shortcuts/blob/main/img/explorer-core-enterprise-view.gif?raw=true)

### Changed

- **Configuration Requirements**:
  - Updated settings schema to support new explorer views
  - Added workspace scanning configuration for addon detection
  - Enhanced launch configuration management through dedicated tree view

## Version 0.37.1

### Improved

#### 📚 Enhanced Hover Documentation

- **Improved Parameters Display**: Parameter names now appear in bold with types clearly visible
- **Better Type Information**: Types from both JSDoc and TypeScript are unified and displayed consistently
- **Clearer Formatting**: Parameter descriptions are shown on separate lines with proper indentation
- **Default Values**: Default parameter values are now displayed as `default: value` for better clarity
- **Auto-generated Usage Examples**: Functions without JSDoc examples now show automatic usage examples based on parameter types
- **Compact Layout**: Reduced font sizes and improved spacing for a more professional appearance

#### ⚡ Scan Progress Indicator

- **Real-time Progress**: Status bar now shows indexing progress with percentage during JavaScript file scanning
- **Visual Feedback**: Animated spinner icon and percentage counter (`$(sync~spin) Indexing JS: XX%`)
- **Automatic Hide**: Progress indicator disappears automatically when scan completes
- **Applies to Reindex**: Progress indicator also works when manually reindexing JavaScript files

#### 📝 Updated Extension Description

- More concise and focused description highlighting key features
- Better emphasis on LSP with IntelliSense capabilities
- Clearer presentation of integrated debugging and addon management

## Version 0.37.0

### Added - OWL/JavaScript Language Server (LSP)

### Screenshots

![01](https://github.com/mjavint/odoo-shortcuts/blob/main/img/00-owl-lsp.png?raw=true)
![02](https://github.com/mjavint/odoo-shortcuts/blob/main/img/01-owl-lsp.png?raw=true)
![03](https://github.com/mjavint/odoo-shortcuts/blob/main/img/02-owl-lsp.png?raw=true)
![04](https://github.com/mjavint/odoo-shortcuts/blob/main/img/03-owl-lsp.png?raw=true)

#### 🎯 Intelligent Code Completion

- **Complete Autocompletion**: Autocomplete for all functions, classes, hooks, and constants from all scanned addons
- **Smart Auto-Import**: Automatically adds import statements when selecting symbols
- **Member Completion**: Autocomplete for class methods and properties when typing `object.` or `Class.`

#### 🔍 Advanced Navigation

- **Go to Definition**: Navigate to symbol definitions with `F12`
- **Automatic OWL Detection**: Recursively searches and indexes OWL library from workspace
- **Cross-Addon Navigation**: Jump to definitions in any addon in your workspace

#### 📚 Rich Documentation

- **Hover Information**: View symbol documentation, signatures, and JSDoc on hover
- **Signature Help**: Parameter hints when typing function calls
- **Type Information**: Display parameter types and return types

#### 🧠 Smart Type Inference

- **Return Type Detection**: Infers return types from JSDoc, TypeScript annotations, and `return new` statements
- **Variable Type Tracking**: Tracks types through variable declarations and assignments
- **Chained Type Resolution**: Follows property chains to determine final types

#### ⚡ Performance

- **Incremental Indexing**: Updates symbols as you type
- **Efficient Caching**: Smart caching system for fast lookups
- **Background Scanning**: Non-blocking workspace scanning

#### 🚀 Getting Started

1. The LSP starts automatically when you open JavaScript/TypeScript files
2. Works with any workspace containing Odoo addons
3. Automatically detects and indexes OWL library
4. Restart LSP: `Ctrl+Shift+P` → "Restart Odoo LSP"

#### 🔄 Commands

- **Restart Odoo LSP**: Restart the language server
- **Reindex JavaScript**: Manually trigger re-indexing of all JavaScript files

---

## Version 0.36.1

### Fixed

- **Status Bar**: Improved visibility and responsiveness of status bar items during Odoo server operations. Fixed issue [#23](https://github.com/mjavint/odoo-shortcuts/issues/23) detected by [Gusti Tammam](https://github.com/gustitammam)

## Version 0.36.0

### Added

- **Auto-refresh TreeProvider**: Tree view now updates automatically when files are created or modified
- **File Watchers**: Automatic detection of changes in `.py`, `.xml`, `.csv`, and `.js` files
- **Improved Error Messages**: More descriptive messages specifying which files already exist
- **Refresh Callbacks**: CodeLens commands now refresh the tree after creating files
- **Optimized TreeProvider Architecture**:
  - BaseTreeProvider with Template Method pattern
  - TreeDataCache with LRU eviction and TTL
  - TreeItemFactory for consistent item creation
  - TreeCommandHandler for CRUD operations
  - Debouncing (300ms) to prevent excessive refreshes
- **Enhanced Webviews**:
  - Implemented Content Security Policy (CSP) with nonces

### Fixed

- **CodeLens Commands**: Now properly refresh tree view after creating files
- **Report Creation**: Fixed "Create Report" command showing incorrect error messages. Fixed issue [#22](https://github.com/mjavint/odoo-shortcuts/issues/22) detected by [Alexandre Fayolle](https://github.com/gurneyalex)
- **Webview Security**: Resolved CSP violations in webviews
- **Event Listeners**: Fixed timing issues with DOMContentLoaded in webviews

### Changed

- **Command Architecture**: Refactored command registration for better maintainability
- **Parameter Handling**: Improved scaffold command parameter resolution with fallbacks
- **Error Handling**: Enhanced error messages with specific file information
- **Tree Refresh Strategy**: Changed from manual to automatic refresh with file watchers

### Performance

- **10x faster** tree refresh with caching
- **90% fewer** I/O operations with optimized scanning
- **Reduced memory** usage with LRU cache limits
- **Smart debouncing** prevents UI freezes during bulk operations

## Version 0.35.0

- The ability to create test files for the server side (Odoo Python Test Case) and for the client side (Odoo Javascript Test with Hoot) has been added. Feature suggested in [#13](https://github.com/mjavint/odoo-shortcuts/issues/13) by [Carlos Lopez](https://github.com/celm1990)
![Test files](https://github.com/mjavint/odoo-shortcuts/blob/main/img/feature-test.gif?raw=true)

## Version 0.34.0

- A filter for repositories in the Odoo explorer has been added `ctrl+k ctrl+f` (windows/linux) and `cmd+k cmd+f` (mac).
![Repos Filter](https://github.com/mjavint/odoo-shortcuts/blob/main/img/repos-filter.gif?raw=true)

- The Fontawesome Picker and online Documentation have been moved to the status bar for faster access.
![Picker-Docs](https://github.com/mjavint/odoo-shortcuts/blob/main/img/move-picker-doc.png?raw=true)

## Version 0.33.0

- Odoo startup options autocompletion has been added.

| Theme Dark | Theme Light |
|-|-|
| ![Odoo Launch Configuration](https://github.com/mjavint/odoo-shortcuts/blob/main/img/odoo-launch-dark.png?raw=true) | ![Odoo Launch Configuration](https://github.com/mjavint/odoo-shortcuts/blob/main/img/odoo-launch-light.png?raw=true)|

## Version 0.32.0

- Improvements have been added to the visualization of repositories and addons in the Odoo Explorer.
- The option to hide and show repositories and addons in the Odoo Explorer has been added.
![Icon Odoo and Font Awesome](https://github.com/mjavint/odoo-shortcuts/blob/main/img/hide-show-addon-repo.gif?raw=true)
- We have fully implemented [[FEAT] Improvement in addon visualization in Odoo Explorer](https://github.com/mjavint/odoo-shortcuts/issues/14) suggested by [Adnier Roselló](https://github.com/arc87)

## Version 0.31.0

- We have improved the Odoo explorer, now faster, more intuitive and with more commands in the context menu.
- A new repository and addon scanning system has been added.

## Version 0.30.0

- Full support for odoo 19 has been added

## Version 0.29.0

- A new feature has been added, now with the possibility to search and copy your odoo (oi) and fontawesome (fa) icon from a panel inside vscode offline.
  ![Icon Odoo and Font Awesome](https://github.com/mjavint/odoo-shortcuts/blob/main/img/fa.gif?raw=true)

- The Odoo Shortcuts settings panel has been fixed for light themes, reported by several users.

| Theme Dark | Theme Light   |
|-|-|
| ![Panel Config Dark](https://github.com/mjavint/odoo-shortcuts/blob/main/img/panel-config-dark.png?raw=true)  | ![Panel Config Light](https://github.com/mjavint/odoo-shortcuts/blob/main/img/panel-config-light.png?raw=true)   |

## Version 0.28.0

- Add Feature New Security File
  ![New Feat Security 1](https://github.com/mjavint/odoo-shortcuts/blob/main/img/feat-security-1.png?raw=true)
  ![New Feat Security 2](https://github.com/mjavint/odoo-shortcuts/blob/main/img/feat-security-2.png?raw=true)
- The functionality to open files created and updated by Odoo Shortcuts in the editor has been implemented in a configurable way, which is disabled by default. Thanks to [RafaelAngelRamirez](https://github.com/RafaelAngelRamirez) for proposing the feature [#10](https://github.com/mjavint/odoo-shortcuts/issues/10)
  ![Open Files Config](https://github.com/mjavint/odoo-shortcuts/blob/main/img/open-files-config.png?raw=true)
- More descriptive placeholders have been added, including their corresponding example.

## Version 0.27.0

- The OWL action, common, field and public templates have been modernized to make them more readable and compact.

## Version 0.26.0

- The handling of the Odoo launcher has been improved, allowing you to activate the boot configuration from the board.
- More user messages have been added.
- Fixed a bug that caused it not to be imported in the `__init__.py` of the wizard module

## Version 0.25.0

- Better handling of Odoo Server start, debug and stop buttons in the statusbar

## Version 0.24.0

- Support for string templates in javascript

## Version 0.23.0

- Support for string templates in python
  ![Python String Template ](https://github.com/mjavint/odoo-shortcuts/blob/main/img/py-string-template.gif?raw=true)

## Version 0.22.0

- Full support has been added to Odoo 18.
- It is now possible to add your own documentation resources via the `odooShortcuts.sites` configuration

  ```json
  "odooShortcuts.sites": [
    {
      "label": "Resource Label",
      "url": "Resource URL"
    }
  ]
  ```

  ![Site 1](https://github.com/mjavint/odoo-shortcuts/blob/main/img/add-site-1.png?raw=true)
  ![Site 1](https://github.com/mjavint/odoo-shortcuts/blob/main/img/add-site-2.png?raw=true)

- Performance improvements have been added.

## Version 0.21.0

- It is now possible to load Odoo and Odoo Web Library documentation completely without the need to exit vscode
  ![Context](https://github.com/mjavint/odoo-shortcuts/blob/main/img/demo-docs.gif?raw=true)

- Two new snippets have been added:
  - oolistedit - List Editable in Odoo 18
  - oovlist - Add new list view in Odoo 18
  - All snippets have been updated to Odoo version 18

## Version 0.20.0

- The possibility of scanning has been added to all workspaces that are incorporated into our project.
- A new provider related to the Odoo source addons and, if applicable, those of the enterprise has been added.
  ![Context](https://github.com/mjavint/odoo-shortcuts/blob/main/img/new-provider.png?raw=true)
- I have improved the interaction between the start and debug of the Odoo server by being able to leave the configuration arguments blank in the webview, in addition to saving the last configuration used once we reopen the project.
- Updated the widget list in the oowidgets snippet.

## Version 0.19.0

- The context menu in File Explorer has been simplified
  ![General View 1](https://github.com/mjavint/odoo-shortcuts/blob/main/img/general.gif?raw=true)
- Several menus have been added in the context of the Odoons Explorer
  ![Context](https://github.com/mjavint/odoo-shortcuts/blob/main/img/new-context.gif?raw=true)
- Fixed minor bugs in the extension

## Version 0.18.1

- Shortcuts have been added for the commands: Open the configuration webview (Win&Linux: ctrl+k ctrl+a, Mac: cmd+k cmd+a), Start Odoo Server (Win&Linux: ctrl+k n, Mac: cmd+k n) , Debug Odoo Server (Win&Linux: ctrl+k ctrl+n, Mac: cmd+k cmd+n), Debug Odoo Javascript (Win&Linux: ctrl+k j, Mac: cmd+k j)

## Version 0.18.0

- Buttons have been added to start and debug the Odoo server, in addition to the button to debug javascript and the button to add configurations for the launch
- Performance has been improved

## Version 0.17.1

- Fixed run configurations

## Version 0.17.0

- The design of the webview in the form was corrected, in addition to making it much more flexible, giving the possibility of searching the directory tree for the odoo-bin and odoo.conf files and also being able to copy the path in the corresponding field

## Version 0.16.3

- The error that did not allow the webview to be seen in Windows has been corrected

## Version 0.16.2

- Fixed minor error in performance

## Version 0.16.1

- The error that did not allow the shortcuts.json file to be created correctly has been fixed

## Version 0.16.0

- A webview has been added to manage the configurations for starting and debugging the server
- Added a snippets to create t-call tags to call other templates, its trigger is **otc**

## Version 0.15.5

- New feature: The possibility has been added to transform the data file (example: account.move.csv) to its corresponding xml file (account_move_data.xml) with noupdate set to True activated by default so that it is only loaded once.
- The description key has been removed from the Manifest as it is deprecated
- The bug described in [#6](https://github.com/mjavint/odoo-shortcuts/issues/6) has been fixed
- The bug described in [#8](https://github.com/mjavint/odoo-shortcuts/issues/8) has been fixed
- The bug described in [#9](https://github.com/mjavint/odoo-shortcuts/issues/9) has been fixed

## Version 0.14.0

- New snippets have been added in the OWL component template.
- All tags have been added by snippets according to the owl documentation [OWL](https://github.com/odoo/owl/blob/master/doc/reference/templates.md).
- Fixed minor bugs in the extension

## Version 0.13.1

- Fixed error in the name of views and inherited views. [Issue #7](https://github.com/mjavint/odoo-shortcuts/issues/7). Thank you **Rafael Angel Ramirez**

## Version 0.13.0

- A selection of arguments for launching the startup or debug of the Odoo Server has been added to the status bar, in addition to its creation.

## Version 0.12.1

- The errors described in the issue have been fixed [Issue #3](https://github.com/mjavint/odoo-shortcuts/issues/3). A new step has been created to manage server actions. Thanks to **Rafael Angel Ramirez**
- The errors described in the issue have been fixed [Issue #3](https://github.com/mjavint/odoo-shortcuts/issues/4). Thanks to **Rafael Angel Ramirez**
- The error that duplicated the xml in the `__manifest__.py` file has been fixed
- The performance of the extension has been improved for gre<<<<<<< HEAD
  "version": "0.15.4",
=======ing to the issue [[ FEAT ] Creates inherit views. #2](https://github.com/mjavint/odoo-shortcuts/issues/2), proposed by **Rafael Angel Ramirez**.
- Added the functionality to create paper format to the reports.
- The folder and directory structure was aligned to the development guide proposed by Odoo. Thanks to **Rolando Perez Rebollo** for suggesting we add this guide [Odoo Coding Guidelines](https://www.odoo.com/documentation/17.0/contributing/development/coding_guidelines.html).

## Version 0.11.1

- Fixed error in the node tree and search that did not allow an OCA pre-commit when it has string. Thanks to *Carlos López* for detecting and reporting it. The `oovtree`, `oovfull`, `ootedit` snippets and the respective `Create Model` and `Create View` file creation shortcuts were updated. Issue Details [string attribute in \<tree\> #1](https://github.com/mjavint/odoo-shortcuts/issues/1)

## Version 0.11.0

- Added a new menu in addon elements to create views and actions.
- The possibility of creating reports was added to the Odoo python files menu.

## Version 0.10.0

- Translate .po files.

## Version 0.9.0

- A new view containers has been created for Odoo.
- Added two tree data provider addons explorer and explorer configurations
- The option has been added to start the odoo server, debug python and javascript files for each of the configurations found in the environment.

## Version 0.8.1

- In the Tree View of the Addons they are now grouped by repositories or folders containing addons
- Added odoo signature colors violet and green to icons

## Version 0.8.0

- Added a new Tree View in Explorer for the Explorer Addon
- Added a new Tree View in Explorer for the Explorer Odoo
- Added contacts mantainers in README file

## Version 0.7.3

- Create new snippets in Odoo Web Library (OWL)
  - Import Hook Service - (ooimservice)
  - Use Hook Service - (oohservice)
- Create new snippets in Python File
  - Inherit Default Get Method - (oodefault)
- Fixed minor error in `__manifest__.py` version 17

## Version 0.7.2

- Fixed minor error in Get Path Import

## Version 0.7.1

- Fixed the error that was not detected in the javascript file when it was with const

## Version 0.7.0

demo: ![demo](https://youtu.be/leyVXKjNQlY?si=Y6_iritz4kTZMQxo)

- Get the import path of a javascript file.
- Open a file from its import and navigate to the definition of the chosen class or function

## Version 0.6.2

- New snippets have been added in OWL such as useState, useRef, useContext, useStore, useDispatch, useAutoFocus, useAssets, useBus
- The templates have been updated to version 2.2 of OWL
- New services such as action and company service have been added

## Version 0.6.1

- We have separated and listed the services in OWL to choose from quickpick updated to odoo 17
- It is now possible from any folder or folder position to generate any
- Fixed minor issue

## Version 0.6.0

- Create a new Controller including the template file

## Version 0.5.3

- Existence validations for views, reports, models and access rules have been added
- Fixed version 17 to three places in the `__manifest__.py` file

## Version 0.5.2

- fixed bug in the view template that did not change the model in the res_model tag

## Version 0.5.1

- Create views and reports from the model and inherit model from the editor
- Import model and inherit model in `__init__.py` from the editor
- Import model in security model access file (`ir.model.access.csv`)

## Version 0.4.0

- Create new wizards files (`*.xml` and `*.py`)
- Create new report file (`*.xml`)
- Create new Paper Format (`paperformat.xml`)

## Version 0.3.1

- Internationalizations (en, es)
- A structural change was made, now when we click on any folder two options will appear (New Addon and New Odoo Configuration) and when we click on the `__manifest__.py` file is when the rest of the options are activated
- Fixed minor errors

## Version 0.3.0

- Get Current XPath in views *.xml, selecting the tag inside the quotes or selecting the parent selector of the line
- Create odoo configuration files (*.conf)

## Version 0.2.1

- Add continuos integration with github actions

## Version 0.2.0

- The name was changed to continue extending and adding functionalities in the form of shortcuts
- All snnipets have been migrated to this extension available in the Odoo Final Snippets  extension of mjavint (deprecated)
- All snippets that were available in the mjavint Odoo Final Snippets <https://marketplace.visualstudio.com/items?itemName=mjavint.mjavint-odoo-snippets> extension (deprecated) have been migrated to this extension
- Added shortcuts for working in python, xml and javascript
- Work on response speed
- Fixed the error that prevented creating an addon

## Version 0.1.4

- Fixed minor errors

## Version 0.1.3

- Extension information messages were improved
- Fixed error that did not allow the addon to be created

## Version 0.1.0

- First Version
