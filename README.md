# Odoo Shortcuts

Creates files and folders necessary to work with Odoo in the two fundamental Frameworks Python and Javascript. When creating the files, they will be automatically generated in the general and local `__init__.py` files of each module as well as in the `__manifest__.py`.

## Demo

![Demo1](https://github.com/mjavint/odoo-shortcuts/raw/main/demo.gif)

![Demo2](https://github.com/mjavint/odoo-shortcuts/raw/main/demo-codeLens.gif)

> Note: The commands shown must be executed by clicking on the addon that is created.

## Screenshots

* General View
  ![General View](https://github.com/mjavint/odoo-shortcuts/blob/main/general.png?raw=true)
* Create views and reports, import model in `__init__.py`, import model in security model access (`ir.model.access.csv`)
  ![General View](https://github.com/mjavint/odoo-shortcuts/blob/main/code-lens.png?raw=true)
* Create Python Module
  ![Create Python Module](https://github.com/mjavint/odoo-shortcuts/blob/main/model.png?raw=true)
* Get the XPath to inherit the structure
  ![Get XPath 1](https://github.com/mjavint/odoo-shortcuts/blob/main/get-XPath-1.png?raw=true)
  ![Get XPath 2](https://github.com/mjavint/odoo-shortcuts/blob/main/get-XPath-2.png?raw=true)

## Features

* Create a new addon starting from the simplest possible structure, in addition to the possibility of choosing whether the assets will be loaded in the `__manifest__.py` according to the version of Odoo you choose.
* Create a module or several Odoo modules at once to host models, reports, controllers, wizards and more.
* Create an inherited model which will also be automatically included in the import in the `__init__.py` file in the models folder.
* Create a new model which the import will automatically include in the `__init__.py` file in the models folder, its loading in the `___manifest__.py` and its default access control in the `ir.model.access.csv`
* Create a security access control file which will be automatically loaded into the `___manifest__.py`.
* Create an OWL component of type fields, action or common
* Create an OWL services
* Get Current XPath in views `*.xml`, selecting the tag inside the quotes or selecting the parent selector of the line
* Create odoo configuration files (`*.conf`)
* Create new Report File (`*.xml`)
* Create new Wizard File (`*.xml` and `*.py`)
* Create a new controller including the template
* Create new Paper Format
* Create views and reports from the model and inherit model from the editor
* Import model and inherit model in `__init__.py` from the editor
* Import model in security model access file (`ir.model.access.csv`)

## How to install

1. Install the extension from the vscode marketplace <https://marketplace.visualstudio.com/items?itemName=mvintg.odoo-file>

## Configurations

* Configure settings with:

   * Mac or Linux
        ```json
        "odooShortcuts.addonsPath": [
            "/path_odoo_server/addons",
            "/path/custom_addons",
        ]
        ```
   * Windows
        ```json
        "odooShortcuts.addonsPath": [
            "C:\\path_odoo_server\\addons",
            "C:\\path\\custom_addons",
        ]
        ```

## Reviews

<https://marketplace.visualstudio.com/items?itemName=mvintg.odoo-file&ssr=false#review-details>

## Known Issues

You can report an issue through <https://github.com/mjavint/odoo-shortcuts/issues>
