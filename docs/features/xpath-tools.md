# XPath Tools

Odoo Shortcuts provides tools for working with XPath in Odoo XML files.

## 🎯 Get Current XPath

Gets the XPath path of the current XML element.

**Command:** `Odoo Shortcuts: Get XPath`

![Get XPath 1](https://github.com/mjavint/odoo-shortcuts/blob/main/img/get-XPath-1.png?raw=true)
![Get XPath 2](https://github.com/mjavint/odoo-shortcuts/blob/main/img/get-XPath-2.png?raw=true)

**Usage:**
1. Place cursor on an XML element
2. Execute command
3. XPath is copied to clipboard

**Example:**
```xml
<record id="view_form" model="ir.ui.view">
    <field name="arch" type="xml">
        <form>
            <group>     <!-- ← Cursor here -->
                <field name="name"/>
            </group>
        </form>
    </field>
</record>
```

**Result:**
```
//form/group
```

## 🔍 Evaluate XPath

Evaluates an XPath expression in the current document.

**Command:** `Odoo Shortcuts: Evaluate XPath`

**Features:**
- Validates XPath syntax
- Shows matching results
- Navigate to found elements

## 💡 Usage Tips

### 1. Creating Inherited Views

```xml
<!-- Copy XPath from element to extend -->
<xpath expr="//field[@name='name']" position="after">
    <field name="new_field"/>
</xpath>
```

### 2. Debugging

When an inherited view doesn't work:
1. Use "Get XPath" to get exact path
2. Verify XPath is correct
3. Adjust as necessary

### 3. Complex Selections

```xml
<!-- Select specific field within a group -->
//group[@string='General']/field[@name='name']

<!-- Select by multiple attributes -->
//field[@name='partner_id' and @widget='many2one']
```

## 🐛 Troubleshooting

### XPath doesn't find elements

1. Verify XML structure
2. Check namespaces if any
3. Use `//*` to search by attributes regardless of tag

### Invalid XPath

The command validates syntax and shows specific errors if the expression is invalid.

---

**Next:** [XML Formatter](./formatter.md)
