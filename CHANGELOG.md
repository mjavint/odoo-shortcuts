# Change Log

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
