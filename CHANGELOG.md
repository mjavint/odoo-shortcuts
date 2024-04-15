# Change Log

## Version 0.11.1

- Fixed error in the node tree and search that did not allow an OCA pre-commit when it has string. Thanks to *Carlos López* for detecting and reporting it. Issue Details [string attribute in \<tree\> #1](https://github.com/mjavint/odoo-shortcuts/issues/1)

## Version 0.11.0

- Added a new menu in addon elements to create views and actions.
  ![Add Odoo XML](https://github.com/mjavint/odoo-shortcuts/blob/main/add-odoo-xml.png?raw=true)

- The possibility of creating reports was added to the Odoo python files menu.

  ![Add Reports](https://github.com/mjavint/odoo-shortcuts/blob/main/add-report.png?raw=true)

## Version 0.10.0

- Translate .po files.
  ![Lang View 1](https://github.com/mjavint/odoo-shortcuts/blob/main/lang-view.png?raw=true)

  ![Lang View 2](https://github.com/mjavint/odoo-shortcuts/blob/main/lang-explorer.png?raw=true)

  ![Lang View 2](https://github.com/mjavint/odoo-shortcuts/blob/main/lang-select.png?raw=true)

## Version 0.9.0

- A new view containers has been created for Odoo.
  ![General View 1](https://github.com/mjavint/odoo-shortcuts/blob/main/general-view.png?raw=true)

- Added two tree data provider addons explorer and explorer configurations
  ![Addon Tree View](https://github.com/mjavint/odoo-shortcuts/blob/main/treeview-addon-group.png?raw=true)

- The option has been added to start the odoo server, debug python and javascript files for each of the configurations found in the environment.
  ![Config Tree View](https://github.com/mjavint/odoo-shortcuts/blob/main/config-treedata.png?raw=true)

## Version 0.8.1

- In the Tree View of the Addons they are now grouped by repositories or folders containing addons
  ![treeview-addon-group](https://github.com/mjavint/odoo-shortcuts/blob/main/treeview-addon-group.png?raw=true)
- Added odoo signature colors violet and green to icons

## Version 0.8.0

- Added a new Tree View in Explorer for the Explorer Addon
- Added a new Tree View in Explorer for the Explorer Odoo
- Added contacts mantainers in README file

## Version 0.7.3

- Create new snippets in Odoo Web Library (OWL)
  - Import Hook Service - (ooimservice)
  - Use Hook Service - (oohservice)

    ![demo-new-snippets-owl](https://github.com/mjavint/odoo-shortcuts/blob/main/demo-new-snnipets-owl.gif?raw=true)
- Create new snippets in Python File
  - Inherit Default Get Method - (oodefault)

    ![demo-new-snippets-py](https://github.com/mjavint/odoo-shortcuts/blob/main/demo-new-snnipets-py.gif?raw=true)

- Fixed minor error in __manifest__.py version 17

## Version 0.7.2

- Fixed minor error in Get Path Import

## Version 0.7.1

- Fixed the error that was not detected in the javascript file when it was with const

## Version 0.7.0

demo: https://youtu.be/leyVXKjNQlY?si=Y6_iritz4kTZMQxo

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
  ![General View](https://github.com/mjavint/odoo-shortcuts/blob/main/code-lens.png?raw=true)

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
