# Odoo File

Creates files and folders necessary to work with Odoo in the two fundamental Frameworks Python and Javascript. When creating the files, they will be automatically generated in the general and local `__init__.py` files of each module as well as in the `__manifest__.py`

![Odoo File Demo](demo.gif)

> Note: The commands shown must be executed by clicking on the addon that is created.

## Features

1. Create a new addon starting from the simplest possible structure, in addition to the possibility of choosing whether the assets will be loaded in the `__manifest__.py` according to the version of Odoo you choose.
2. Create a module or several Odoo modules at once to host models, reports, controllers or wizards.
3. Create an inherited model which will also be automatically included in the import in the `__init__.py` file in the models folder.
4. Create a new model which the import will automatically include in the `__init__.py` file in the models folder, its loading in the `___manifest__.py` and its default access control in the `ir.model.access.csv`
5. Create a security access control file which will be automatically loaded into the `___manifest__.py`.
6. Create an OWL component of type fields, action or common
7. Crear un servicio de OWL

## How to install

## Known Issues

You can report an issue through <https://github.com/mjavint/odoo-file/issues>

**Enjoy!**