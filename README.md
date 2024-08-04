# hsBlipManager

![image](https://github.com/user-attachments/assets/5f4cfdcf-6497-4edc-ac51-0b0bf636717b)


## Overview

`hsBlipManager` is a FiveM script that allows players to create, view, manage, and share custom blips on the map. The blips are client-side only, meaning they are private and not visible to other players unless shared. This script is compatible with both ESX and QBCore frameworks and uses `ox_lib` for UI and notifications.

## Features

- Create custom blips at the player's current location.
- View and manage created blips.
- Share blips with nearby players.
- Persistent blips across server restarts.
- Restriction system for using abusive words in blip names.
- Configurable settings for blip appearance and restrictions.

## Documentation

[documentation](https://hyperscriptss.gitbook.io/).

## Support

[Discord Support](https://discord.gg/57H2HBaHB6).

Tebex Store - [Get Now](https://hyperscriptss.tebex.io/)

## Installation

1. **Download and Extract:**
   - Download the script and extract it to your FiveM resources directory.

2. **Add to Server Configuration:**
   - Add `ensure hsBlipManager` to your `server.cfg` file.

3. **Dependencies:**
   - Ensure you have `ox_lib` installed. Follow the installation instructions from the [ox_lib documentation](https://overextended.dev/ox_lib/Modules/Interface/Client/context).

## Configuration

Open the `config.lua` file to configure the script according to your server's needs.

### Example Configuration

```lua
Config = {}

-- Framework settings: 'esx' or 'qbcore'
Config.Framework = 'esx'

-- Blip defaults
Config.BlipDefaults = {
    sprite = 1,
    color = 1,
    scale = 1.0,
    name = 'Custom Blip'
}

-- Abusive words filter
Config.AbusiveWordsFilter = {
    Enabled = true,
    Words = { "badword1", "badword2", "badword3" },
    MaxAttempts = 2,
    TimeoutDuration = 300 -- in seconds
}

-- Sharing radius
Config.SharingRadius = 50.0 -- in meters

-- Debug mode
Config.Debug = false

-- Notifications
Config.Notifications = {
    BlipAdded = "Blip has been added successfully.",
    BlipDeleted = "Blip has been deleted successfully.",
    BlipTransferred = "Blip has been transferred successfully.",
    BlipReceived = "You have received a new blip.",
    InvalidBlipName = "Blip name contains abusive words.",
    MenuAccessRestricted = "You are restricted from accessing the menu."
}
```

## Usage

### Commands

- **Open Blip Menu:**
  ```
  /blipmenu
  ```

### Menu Options

1. **Mark on Map:**
   - Allows players to create a blip at their current location.
   - Prompts the player to enter a name for the blip.
   
2. **See Markers:**
   - Displays a list of all created blips.
   - Players can view and delete their blips from this menu.

3. **Transfer Marker:**
   - Displays a list of nearby players.
   - Players can share their blips with other players within the specified radius.

### Notifications

The script uses `ox_lib` for notifications. Customize the notification texts in the `config.lua` file.

### Restriction System

If a player uses abusive words in the blip name, they will receive a warning. After exceeding the maximum allowed attempts, they will be restricted from using the blip menu for a specified duration. The restriction duration is configurable in the `config.lua` file.

## Troubleshooting

- Ensure `ox_lib` is properly installed and configured.
- Check the server console for any error messages and refer to the `logError` function for debugging.
- Ensure the configuration settings in `config.lua` are correctly set up according to your framework and preferences.

## Contributing

Feel free to contribute to the project by submitting issues or pull requests on the GitHub repository.

## License

This project is licensed under the MIT License. See the LICENSE file for more details.
