# XML Formatter

Odoo Shortcuts includes a specialized XML formatter for Odoo files.

![Transform CSV to XML](https://github.com/mjavint/odoo-shortcuts/blob/main/img/transform-csv-xml-data.gif?raw=true)

## ✨ Features

- **Configurable indentation** - 4 spaces by default
- **Attributes on separate lines** - Optional
- **Odoo tag organization** - Special spacing for tags like `record`, `menuitem`, `template`
- **Comment preservation** - Maintains XML comments
- **Empty elements** - Configurable: self-closing or expanded

## ⚙️ Configuration

```json
{
  "odooShortcuts.formatter.tabSize": 4,
  "odooShortcuts.formatter.splitAttributes": false,
  "odooShortcuts.formatter.splitAttributesTags": [],
  "odooShortcuts.formatter.emptyElementHandling": "selfClosing",
  "odooShortcuts.formatter.maxLineLength": 120,
  "odooShortcuts.formatter.sortAttributes": false,
  "odooShortcuts.formatter.closeTagOnNewLine": false,
  "odooShortcuts.formatter.preserveComments": true,
  "odooShortcuts.formatter.odooTagSpacing": true,
  "odooShortcuts.formatter.odooSpacingTags": [
    "record",
    "menuitem",
    "template"
  ],
  "odooShortcuts.formatter.excludePatterns": [
    "**/odoo/**",
    "**/enterprise/**"
  ]
}
```

## 📝 Examples

### Before
```xml
<record id="res_partner_form" model="ir.ui.view"><field name="name">res.partner.form</field><field name="model">res.partner</field><field name="arch" type="xml"><form><sheet><group><field name="name"/><field name="email"/></group></sheet></form></field></record>
```

### After
```xml
<record id="res_partner_form" model="ir.ui.view">
    <field name="name">res.partner.form</field>
    <field name="model">res.partner</field>
    <field name="arch" type="xml">
        <form>
            <sheet>
                <group>
                    <field name="name"/>
                    <field name="email"/>
                </group>
            </sheet>
        </form>
    </field>
</record>
```

### Attributes on Separate Lines

```xml
<!-- With splitAttributes: true -->
<field
    name="partner_id"
    widget="many2one"
    options="{'no_create': True}"
/>
```

## 🚀 Usage

**Shortcut:** `Shift+Alt+F` (Windows/Linux) or `Shift+Option+F` (Mac)

**Command:** `Format Document`

## 🎯 Tags with Special Spacing

The following tags have blank line before them by default:
- `record` - Record definitions
- `menuitem` - Menu items
- `template` - QWeb templates

This improves readability in large XML files.

## 🚫 Exclusions

Files matching patterns in `excludePatterns` will not be formatted.

---

**Next:** [Configuration](../configuration.md)
