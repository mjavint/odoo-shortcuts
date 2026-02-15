# Keyboard Shortcuts

Odoo Shortcuts provides configurable keyboard shortcuts for common actions.

## ⌨️ Default Shortcuts

### Development

| Action | Windows/Linux | Mac |
|--------|--------------|-----|
| **New Addon** | `Ctrl+K Ctrl+A` | `Cmd+K Cmd+A` |
| **Debug Odoo** | `Ctrl+K Ctrl+N` | `Cmd+K Cmd+N` |
| **Debug JavaScript** | `Ctrl+K J` | `Cmd+K J` |
| **Start Odoo Server** | `Ctrl+Shift+D` | `Cmd+Shift+D` |

### Odoo Explorer

| Action | Windows/Linux | Mac |
|--------|--------------|-----|
| **Filter Addons** | `Ctrl+K Ctrl+F` | `Cmd+K Cmd+F` |
| **Open OWL definition** | `Ctrl+Shift+D` | `Cmd+Shift+D` |

## 🔧 Customizing Shortcuts

### Add Custom Shortcut

1. Open **File** → **Preferences** → **Keyboard Shortcuts**
   - Or use `Ctrl+K Ctrl+S` / `Cmd+K Cmd+S`

2. Search for "Odoo Shortcuts"

3. Click on the command you want to add a shortcut to

4. Press the desired key combination

### Example: Add Shortcut for New Model

```json
// keybindings.json
[
  {
    "command": "odooShortcuts.createNewModelCommand",
    "key": "ctrl+shift+m",
    "mac": "cmd+shift+m",
    "when": "editorTextFocus"
  }
]
```

## 📝 Configuration File

Shortcuts are saved in `keybindings.json`:

### Location

- **Windows:** `%APPDATA%\Code\User\keybindings.json`
- **Mac:** `~/Library/Application Support/Code/User/keybindings.json`
- **Linux:** `~/.config/Code/User/keybindings.json`

### Complete Example

```json
[
  {
    "command": "odooShortcuts.createNewAddonCommand",
    "key": "ctrl+shift+a",
    "mac": "cmd+shift+a",
    "when": "editorTextFocus"
  },
  {
    "command": "odooShortcuts.createViewsCommand",
    "key": "ctrl+shift+v",
    "mac": "cmd+shift+v",
    "when": "editorLangId == python"
  },
  {
    "command": "odooShortcuts.debugOdooCommand",
    "key": "ctrl+shift+d",
    "mac": "cmd+shift+d"
  },
  {
    "command": "odooShortcuts.debugJSCommand",
    "key": "ctrl+k j",
    "mac": "cmd+k j"
  },
  {
    "command": "odooShortcuts.addon.filter",
    "key": "ctrl+k ctrl+f",
    "mac": "cmd+k cmd+f",
    "when": "view == odooAddonsExplorer"
  }
]
```

## 🎯 Contextual Conditions

Shortcuts can be activated only in certain contexts:

| Condition | Description |
|-----------|-------------|
| `editorTextFocus` | Editor has focus |
| `editorLangId == python` | Python file active |
| `editorLangId == xml` | XML file active |
| `view == odooAddonsExplorer` | Addon explorer active |
| `resourceExtname == .py` | .py file open |

## 💡 Tips

### 1. Avoid Conflicts

Verify your shortcut doesn't conflict with others:
- VS Code will show a warning if there's a conflict
- You can reassign or use unique combinations

### 2. Use Chords

"Chords" (key sequences) are useful:
```json
{
  "key": "ctrl+k ctrl+a"  // Press Ctrl+K, then Ctrl+A
}
```

### 3. Workspace Shortcuts

You can have workspace-specific shortcuts in `.vscode/keybindings.json`.

### 4. View All Shortcuts

- `Ctrl+K Ctrl+S` (Windows/Linux)
- `Cmd+K Cmd+S` (Mac)

This opens the shortcuts editor where you can:
- View all shortcuts
- Search by command
- Filter by category
- Export/Import configurations

## 🐛 Troubleshooting

### Shortcut doesn't work

1. Verify there's no conflict with another extension
2. Check the `when` condition
3. Restart VS Code

### Shortcut overridden

If another shortcut has priority:
1. Open Keyboard Shortcuts
2. Search for your shortcut
3. Reassign or remove the conflict

---

**Next:** [FAQ](./faq.md)
