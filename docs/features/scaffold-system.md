# Scaffold System (Code Generation)

The Odoo Shortcuts scaffold system allows you to generate complete Odoo code quickly and consistently. Supports Odoo versions 14-19 and automatically adapts syntax according to the version.

![Scaffold Demo](https://github.com/mjavint/odoo-shortcuts/blob/main/img/new-context.gif?raw=true)

## 📋 Generator Index

- [Complete Addons](#complete-addons)
- [Python Models](#python-models)
- [XML Views](#xml-views)
- [OWL Components](#owl-components)
- [Actions](#actions)
- [Security](#security)
- [Tests](#tests)
- [Configuration](#configuration)

---

## Complete Addons

### New Addon
Creates a complete addon with standard structure.

**Command:** `Odoo Shortcuts: New Addon`

**Requested Fields:**
- Addon name
- Odoo version (14-19)
- Include assets (only relevant for v14)

**Generated Structure:**
```
my_addon/
├── __init__.py
├── __manifest__.py
├── models/
│   └── __init__.py
├── views/
├── security/
├── static/
│   └── src/
│       └── components/
└── README.md
```

### New Module
Similar to New Addon, creates a module with basic structure.

---

## Python Models

### Model
Generates a complete Odoo model with:
- Python model file
- XML views (form, tree/list, search)
- Window action
- Access rules

**Command:** `Odoo Shortcuts: New Model`

![Model Fields Editor](https://github.com/mjavint/odoo-shortcuts/blob/main/img/01-model-editor-fields.jpeg?raw=true)

**Generated Template (Odoo 18+):**
```python
class MyModel(models.Model):
    _name = 'my.model'
    _description = 'My Model'

    name = fields.Char(string='Name', required=True)
```

**Generated Views:**
- Form view with standard layout
- List/tree view (adapted to version)
- Search view with filters
- Window action

### Inherit Model
Creates a model that inherits from an existing one.

**Command:** `Odoo Shortcuts: New Inherit Model`

**Template:**
```python
class MyModelInherited(models.Model):
    _inherit = 'original.model'

    new_field = fields.Char(string='New Field')
```

### Wizard
Generates a wizard (transient model) with:
- Python model
- XML view
- Window action

**Command:** `Odoo Shortcuts: New Wizard`

### Controller
Generates an HTTP controller.

**Command:** `Odoo Shortcuts: New Controller`

**Template:**
```python
class MyController(http.Controller):
    @http.route('/my/route', type='http', auth='public')
    def my_route(self, **kw):
        return request.render('template_id', {})
```

### Report
Generates a QWeb report.

**Command:** `Odoo Shortcuts: New Report`

---

## XML Views

### Views
Generates a complete view file for a model.

**Command:** `Odoo Shortcuts: Create Views`

**Supported View Types:**
- Form
- Tree/List (adapted to version)
- Search
- Kanban
- Calendar
- Graph
- Pivot

**Version Adaptation:**
- Odoo < 18: `<tree>`, `view_mode="tree,form"`
- Odoo 18+: `<list>`, `view_mode="list,form"`

### Inherit Views
Generates inherited views (inherit) to extend existing views.

**Command:** `Odoo Shortcuts: Create Inherit Views`

**Template:**
```xml
<record id="view_model_form_inherit" model="ir.ui.view">
    <field name="name">model.form.inherit</field>
    <field name="model">my.model</field>
    <field name="inherit_id" ref="original_module.view_id"/>
    <field name="arch" type="xml">
        <xpath expr="//field[@name='name']" position="after">
            <field name="new_field"/>
        </xpath>
    </field>
</record>
```

---

## OWL Components

### OWL Component
Generates a complete OWL component.

**Command:** `Odoo Shortcuts: New OWL Component`

**Generated Files:**
- `component_name.js` - Component class
- `component_name.xml` - XML template
- `component_name.scss` - Styles (optional)

**JavaScript Template:**
```javascript
/** @odoo-module **/
import { Component, useState } from "@odoo/owl";

export class MyComponent extends Component {
    static template = "addon_name.MyComponent";
    static props = {};
    
    setup() {
        this.state = useState({});
    }
}
```

### OWL Service
Generates an OWL service.

**Command:** `Odoo Shortcuts: New OWL Service`

**Template:**
```javascript
/** @odoo-module **/
import { registry } from "@web/core/registry";

export const myService = {
    dependencies: [],
    
    start(env) {
        return {
            // Service methods
        };
    }
};

registry.category("services").add("myService", myService);
```

---

## Actions

### Server Actions
Generates server actions (ir.actions.server).

**Command:** `Odoo Shortcuts: New Server Actions`

### Client Actions
Generates client actions.

**Command:** `Odoo Shortcuts: New Client Actions`

### Cron Actions
Generates scheduled tasks (cron).

**Command:** `Odoo Shortcuts: New Cron Actions`

**Template:**
```xml
<record id="ir_cron_my_action" model="ir.cron">
    <field name="name">My Scheduled Action</field>
    <field name="model_id" ref="model_my_model"/>
    <field name="state">code</field>
    <field name="code">model.my_method()</field>
    <field name="interval_number">1</field>
    <field name="interval_type">days</field>
    <field name="numbercall">-1</field>
</record>
```

### Paper Format
Generates custom paper formats for reports.

**Command:** `Odoo Shortcuts: New Paper Format`

---

## Security

### Security Access CSV
Generates `ir.model.access.csv` file with access rules.

**Command:** `Odoo Shortcuts: New Security File`

![Security Feature 1](https://github.com/mjavint/odoo-shortcuts/blob/main/img/feat-security-1.png?raw=true)
![Security Feature 2](https://github.com/mjavint/odoo-shortcuts/blob/main/img/feat-security-2.png?raw=true)

**Template:**
```csv
id,name,model_id:id,group_id:id,perm_read,perm_write,perm_create,perm_unlink
access_my_model_user,My Model User,model_my_model,base.group_user,1,1,1,0
```

### Import Security Access
Generates access rules for an existing model.

**Command:** Available via CodeLens on models

---

## Tests

### Python Tests
Generates tests in Python.

**Command:** `Odoo Shortcuts: New Tests File`

**Available Templates:**
- TransactionCase
- SavepointCase
- HttpCase

### JavaScript Tests
Generates tests for OWL components.

**Template:**
```javascript
/** @odoo-module **/
import { click, getFixture, mount } from "@web/../tests/helpers/utils";
import { makeTestEnv } from "@web/../tests/helpers/mock_env";

QUnit.module("My Component", {});

QUnit.test("Test description", async (assert) => {
    // Test code
});
```

---

## Configuration

### Odoo Configuration
Generates `.conf` configuration files.

**Command:** `Odoo Shortcuts: New Odoo Configuration`

**Template:**
```ini
[options]
addons_path = /path/to/addons
admin_passwd = admin
db_host = localhost
db_port = 5432
db_user = odoo
db_password = odoo
```

---

## 🎯 Usage Tips

### 1. Use CodeLens
Python models show CodeLens above the class to generate views, reports, etc.

### 2. Contextual Selection
Some commands automatically detect:
- Current addon
- Model you're working on
- Configured Odoo version

### 3. Adaptive Templates
The system detects Odoo version and adjusts:
- XML syntax (`tree` vs `list`)
- File structure
- Specific imports

### 4. Manifest Update
Scaffolds automatically update `__manifest__.py` to include new files.

---

## 🔧 Customization

Templates use the File Headers system configured in settings. You can customize:

- Author
- Email
- Company
- License
- Custom templates

See [Configuration](../configuration.md) for more details.
