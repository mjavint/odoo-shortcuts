# CodeLens

CodeLens provides contextual actions directly in the editor, showing useful links above relevant classes and methods.

## 🎯 Features

CodeLens automatically appears above:

- **Odoo Models** - Actions to create views, reports, security
- **OWL Classes** - Documentation and references
- **Specific functions** - Contextual actions

## 📝 Python Models

When you open a Python file with Odoo models, you'll see links above each class:

```python
class SaleOrder(models.Model):  # ← [Create Views] [Create Report] [Import Security]
    _name = 'sale.order'
    _description = 'Sales Order'
```

### Available Actions

| Action | Description | Alternative Command |
|--------|-------------|---------------------|
| **Create Views** | Generates XML file with views | `Odoo Shortcuts: Create Views` |
| **Create Report** | Generates QWeb report | `Odoo Shortcuts: New Report` |
| **Import Security** | Creates access rules | `Odoo Shortcuts: Import Security Model Access` |
| **Create Inherit View** | Generates inherited views | `Odoo Shortcuts: Create Inherit Views` |

## 🎨 OWL Components

For OWL components, CodeLens shows:

```javascript
/** @odoo-module **/
export class MyComponent extends Component {  // ← [OWL Documentation]
    static template = "my_module.MyComponent";
}
```

### OWL Actions

| Action | Description |
|--------|-------------|
| **OWL Documentation** | Opens OWL documentation in webview |

## ⚙️ Configuration

### Enable/Disable CodeLens

```json
{
  "odooFile.codelens.enabled": true  // or false to disable
}
```

### Language Configuration

CodeLens automatically activates for:
- Python files (`.py`)
- JavaScript files (`.js`)
- TypeScript files (`.ts`)

## 🚀 Usage

### How to Use CodeLens

1. **Open** a file with Odoo models or OWL components
2. **Wait** a moment (CodeLens loads asynchronously)
3. **Click** on the links that appear above classes
4. **Follow** the command instructions

![CodeLens in Action](https://github.com/mjavint/odoo-shortcuts/blob/main/img/codelens.gif?raw=true)

### Complete Example

```python
# Open models/sale_order.py

class SaleOrder(models.Model):  
    # [Create Views] [Create Report] [Import Security]  ← Appears here
    
    _name = 'sale.order'
    _description = 'Sales Order'
    
    name = fields.Char(string='Name')
    partner_id = fields.Many2one('res.partner', string='Customer')
```

**You click [Create Views]:**
1. Select Odoo version
2. Generates `views/sale_order_views.xml`
3. Updates `__manifest__.py`
4. Opens generated file

## 🎨 Appearance

CodeLens appears as light gray text above definitions:

![CodeLens Appearance](https://github.com/mjavint/odoo-shortcuts/blob/main/img/codelens.jpeg?raw=true)

```
[Create Views] [Create Report] [Import Security]
class MyModel(models.Model):
```

Color and style follow the VS Code theme.

## 🐛 Troubleshooting

### CodeLens doesn't appear

1. Verify the file is detected as Python
2. Check that `odooFile.codelens.enabled` is `true`
3. Wait a few seconds (loads asynchronously)
4. Restart VS Code if necessary

### CodeLens appears in wrong files

CodeLens uses heuristics to detect Odoo models:
- Looks for `models.Model` in code
- Verifies class structure
- Checks file is in a valid addon

### Slow performance

If CodeLens slows down the editor:

1. Temporarily disable: `"odooFile.codelens.enabled": false`
2. Close unrelated large files
3. Consider splitting very large files

## 💡 Tips

### 1. Quick Use
CodeLens is the fastest way to generate code related to a model.

### 2. Visual Context
Links only appear when relevant, keeping the editor clean.

### 3. Multi-model
If a file has multiple models, each will have its own CodeLens links.

## 📊 Comparison with Commands

| Feature | CodeLens | Commands |
|---------------|----------|----------|
| **Speed** | One click | Command palette |
| **Context** | Model specific | General |
| **Discovery** | Automatic visual | Memorize shortcuts |
| **Flexibility** | Current model | Any model |

**Recommendation:** Use CodeLens for the current model, commands for other models.

## 🔧 Technical Implementation

CodeLens works through:

1. **CodeLens Provider** - Registers provider for Python/JS
2. **AST Analysis** - Parses code to find classes
3. **Symbol Resolution** - Identifies Odoo models and OWL components
4. **Command Generation** - Creates links for each case

Analysis is done in real-time as you edit.

---

**Next:** [XPath Tools](./xpath-tools.md)
