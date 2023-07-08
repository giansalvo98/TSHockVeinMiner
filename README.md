# TSHockVeinMiner
VeinMiner Plugin for TShock, allows you to edit blocks that you want to be veinmined as well allows you to give your players certain rewards for veinmining big veins!

- Originally made by [Megghy](https://github.com/Megghy)
- Updated to **TShock** `5.0` and translated to English by [YSpood](https://github.com/YSpoof)
- Bug fixes and updated dependencies by me.

## How to Install
1. Put the .dll into the `\ServerPlugins\` folder.
2. Restart the server.
3. Give your desired group the `veinminer` permission.

## How to Use
### Config Options
- `Enable` - Determines whether the plugin is enabled or not.
- `Broadcast` - Determines whether to send a 'mining status' message to the player when a vein is being veinmined(does not affects whether or not the message sent to the player when the `Exchange`(See below) requirements are met is sent).
- `PutInInventory` - whether to put the ores mined in the player's inventory or drop it as normal(does not veinmines if the player's inventory is full).
- `Tile` - the list of tile ids representing the tiles that can be veinmined.

#### This part of the configs are fully developed yet so expect bugs:
- `Exchange` - list of configs for an "Exchange" system where the player gets certain items for veinmining veins of certain size.
  - `OnlyGiveItem` - whether to only give the the ores veinmined when Exchange requirements are met.
  - `MinSize` - the required amount of ore required in a vein for the Exchange process to happen(does not stack, for instance if `"MinSize": 10` and the player mined a vein composed of 20 ore blocks they wont receive twice the items).
  - `Type` - the tileid of the block you wish for an Exchange to occur when a certain amount is mined(can only have one value for now).
  - `Item` - the list of items along with their amounts to give to the player when the Exchange requirements are met(uses itemid).
  
#### Example:
*Example of an Exchange section:*
```json
  "Exchange": [
    {
      "OnlyGiveItem": true,
      "MinSize": 10,
      "Type": 169,
      "Item": {
        "666": 5,
        "669": 1
      }
    }
  ]
```
In the example above we can see that the tile that can trigger an exchange is platinum ore. If the player veinmines more than 10 platinum ore they get 5 `Red's Helmet` and 1 `Fish`, on top of that they also get the ores they mined from the vein.

### Commands
- `vm` (alternative: `veinmeiner`)
- `vm {any parameter}` (alternative: `veinmeiner {any parameter}`)

### Usage and Examples
- `.vm` - disables or enables veinmining for the sender.
- `/vm msg` - disables or enables the sending of the 'mining status' message for the sender when a vein is being mined.

## How to Build
1. Download the source code.
2. Open the `.sln` file.
3. Check to make sure the references are all correct and up to date.
4. Build.

## Known Issues and Workarounds
- Currently only 1 tile can be set up to have an `Exchange`.
- Players can easily exploit the `Exchange` system if `OnlyGiveItem` is off by just veinmining ores and placing back again the ores they just got again and again, easily getting an infinite supply of the items listed in the `Item` value of the configs.

## Notes
- After fixing the issues listed above i plan to add more features especially some expanding on the `Exchange` concept of the plugin.
- despite the issues, the works of Megghy in making this plugin and of YSpood in translating it are absolutely great as i cant imagine myself doing any of those in a more proper way than what they did.

## Original plugin repo
https://github.com/Megghy/VeinMiner
