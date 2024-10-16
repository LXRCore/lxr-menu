# Menu System for LXRCore Framework 📄

## Screenshots
![Menu2](https://cdn.discordapp.com/attachments/1021700112776437760/1183289410226229338/image.png?ex=6587cb23&is=65755623&hm=aa95a9d46ebd56839cff7d00ce5451fb9933e2a6e9dcbc3592368fb694b15785&)

---

## Features
- Create dynamic and interactive menus for a wide variety of purposes.
- Simple yet powerful API to easily create multi-option menus with sub-menus.

---

## Example

Here’s how you can create and use a menu in **LXR-Menu**:

```lua
RegisterCommand("lxrmenutest", function(source, args, raw)
    openMenu({
        {
            header = "Main Title",
            isMenuHeader = true,
        },
        {
            header = "Sub Menu Button",
            txt = "This goes to a sub menu",
            params = {
                event = "lxr-menu:client:testMenu2",
                args = {
                    number = 1,
                }
            }
        },
        {
            header = "Sub Menu Button",
            txt = "This goes to a sub menu",
            disabled = true,
            params = {
                event = "lxr-menu:client:testMenu2",
                args = {
                    number = 1,
                }
            }
        },
    })
end)
```

```lua
RegisterNetEvent('lxr-menu:client:testMenu2', function(data)
    local number = data.number
    openMenu({
        {
            header = "< Go Back",
        },
        {
            header = "Number: "..number,
            txt = "Other",
            params = {
                event = "lxr-menu:client:testButton",
                args = {
                    message = "This was called by clicking this button"
                }
            }
        },
    })
end)
```

```lua
RegisterNetEvent('lxr-menu:client:testButton', function(data)
    TriggerEvent('LXRCore:Notify', data.message)
end)
```

---

## Installation

1. **Download the script** and place it in the `[lxr]` directory of your server.
2. **Add** the necessary configuration to your `server.cfg` to ensure **lxr-menu** loads properly.

```bash
ensure lxr-core
ensure lxr-menu
```

---

## License 📄

```
LXRCore Framework
Copyright (C) 2024

This program is free software: you can redistribute it and/or modify
it under the terms of the MIT License.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.
```

---

With **LXR-Menu**, creating interactive, easy-to-use menus has never been simpler. Whether for player interactions, shop menus, or custom systems, **LXR-Menu** is your go-to solution for all your server's menu needs!
