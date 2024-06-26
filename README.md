# .vscode

## Table of Contents

- [.vscode](#vscode)
  - [Table of Contents](#table-of-contents)
  - [Description](#description)
    - [Extensions](#extensions)
      - [Save Extensions Windows](#save-extensions-windows)
      - [Save Extensions Linux](#save-extensions-linux)
      - [Load Extensions Windows](#load-extensions-windows)
      - [Load Extensions Linux](#load-extensions-linux)
    - [Settings](#settings)
      - [Save Settings Windows](#save-settings-windows)
      - [Save Settings Linux](#save-settings-linux)
      - [Load Settings](#load-settings)
      - [Load Settings Windows](#load-settings-windows)
        - [Load Settings Linux](#load-settings-linux)
    - [Keybindings](#keybindings)
      - [Save Keybindings Windows](#save-keybindings-windows)
      - [Save Keybindings Linux](#save-keybindings-linux)
      - [Load Keybindings Windows](#load-keybindings-windows)
      - [Load Keybindings Linux](#load-keybindings-linux)
  - [License](#license)

## Description

> Note: Windows commands are untested and written using Github Copilot.

My vscode settings and extensions.
In near future, I will add backup for another profiles.
Each profile will has unique name. In this README, I will use `default` as a profile name.

### Extensions

#### Save Extensions Windows

```cmd
code --list-extensions > extensions\default.txt
```

#### Save Extensions Linux

```bash
code --list-extensions > extensions/default.txt
```

#### Load Extensions Windows

> Before running the command, make sure that you have a backup of your current extensions.

Backup your current extensions:

```PowerShell
code --list-extensions > extensions\default_backup.txt
```

Restore extensions:
(Optional) Remove all installed extensions:

```PowerShell
Get-Content extensions\default_backup.txt | ForEach-Object { code --uninstall-extension $_ }
```

#### Load Extensions Linux

> Before running the command, make sure that you have a backup of your current extensions.

Backup your current extensions:

```bash
code --list-extensions > extensions/default_backup.txt
```

Restore extensions:
(Optional) Remove all installed extensions:

```bash
cat extensions/default_backup.txt | xargs -L 1 code --uninstall-extension
```

Install extensions:

```bash
cat extensions/default.txt | xargs -L 1 code --install-extension
```

### Settings

#### Save Settings Windows

```PowerShell
copy %APPDATA%\Code\User\settings.json config\default.jsonp
```

#### Save Settings Linux

```bash
cp ~/.config/Code/User/settings.json config/default.jsonp
```

#### Load Settings

#### Load Settings Windows

> Before running the command, make sure that you have a backup of your current settings.

Backup your current settings:

```PowerShell
copy %APPDATA%\Code\User\settings.json %APPDATA%\Code\User\settings_backup.json
```

Load settings:

```PowerShell
copy config\default.jsonp %APPDATA%\Code\User\settings.json
```

##### Load Settings Linux

> Before running the command, make sure that you have a backup of your current settings.

Backup your current settings:

```bash
cp ~/.config/Code/User/settings.json ~/.config/Code/User/settings_backup.json
```

Load settings:

```bash
cp config/default.jsonp ~/.config/Code/User/settings.json
```

### Keybindings

#### Save Keybindings Windows

```PowerShell
copy %APPDATA%\Code\User\keybindings.json keybindings\default.jsonc
```

#### Save Keybindings Linux

```bash
cp ~/.config/Code/User/keybindings.json keybindings/default.jsonc
```

#### Load Keybindings Windows

> Before running the command, make sure that you have a backup of your current keybindings.

Backup your current keybindings:

```PowerShell
copy %APPDATA%\Code\User\keybindings.json %APPDATA%\Code\User\keybindings_backup.json
```

Load keybindings:

```PowerShell
copy keybindings\default.jsonc %APPDATA%\Code\User\keybindings.json
```

#### Load Keybindings Linux

> Before running the command, make sure that you have a backup of your current keybindings.

Backup your current keybindings:

```bash
cp ~/.config/Code/User/keybindings.json ~/.config/Code/User/keybindings_backup.json
```

Load keybindings:

```bash
cp keybindings/default.jsonp ~/.config/Code/User/keybindings.json
```

## License

[MIT](LICENSE)
