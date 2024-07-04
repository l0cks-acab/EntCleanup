# EntCleanup

**EntCleanup** is a Rust plugin designed to clean up old entities that aren't upkept to decrease server load and increase FPS. It features configurable cleanup intervals, entity age limits, and a command for manual cleanup.

## Features

- Automatically removes specified old entities that are not within building privilege areas.
- Configurable cleanup intervals and entity age limits.
- Whitelist for important entities that should not be removed.
- Admin command for manual cleanup.
- Notifies all players when cleanup is occurring and when it finishes.

## Installation

1. Download the `EntCleanup.cs` file.
2. Place the file in your `oxide/plugins` directory.
3. Reload the plugin using the command:
    ```
    oxide.reload EntCleanup
    ```

## Configuration

The default configuration values can be customized in the `EntCleanup.json` file located in the `oxide/config` directory after the first run.

### Default Configuration

```json
{
    "CheckInterval": 3600.0,
    "MaxEntityAge": 86400.0,
    "TargetEntities": [
        "assets/prefabs/building/wall.external.high.stone/wall.external.high.stone.prefab",
        "assets/prefabs/building/wall.external.high.wood/wall.external.high.wood.prefab",
        "assets/prefabs/building/door.hinged.wood/door.hinged.wood.prefab",
        "assets/prefabs/deployable/barricade/barricade.wood.prefab",
        "assets/prefabs/deployable/barricade/barricade.wood.cover.prefab",
        "assets/prefabs/deployable/planter/planter.large.prefab",
        "assets/prefabs/deployable/planter/planter.small.prefab",
        "assets/prefabs/deployable/signs/sign.small.wood.prefab",
        "assets/prefabs/deployable/signs/sign.medium.wood.prefab",
        "assets/prefabs/deployable/signs/sign.large.wood.prefab",
        "assets/prefabs/deployable/signs/sign.huge.wood.prefab",
        "assets/prefabs/deployable/chair/chair.comfy.prefab",
        "assets/prefabs/deployable/table/table.small.prefab",
        "assets/prefabs/deployable/table/table.large.prefab",
        "assets/prefabs/deployable/barricade/barricade.stone.prefab",
        "assets/prefabs/deployable/water catcher/water_catcher_small.prefab",
        "assets/prefabs/deployable/water catcher/water_catcher_large.prefab",
        "assets/prefabs/deployable/water barrel/water_barrel.prefab"
    ],
    "WhitelistEntities": []
}
```

### Configuration Options

- **CheckInterval**: How often to check for old entities (in seconds).
- **MaxEntityAge**: Maximum age of entities in seconds before they are removed.
- **TargetEntities**: List of entity prefab names to be cleaned up.
- **WhitelistEntities**: List of entity prefab names that should not be cleaned up.

## Permissions

- **entcleanup.admin**: Allows use of the `/cleanup` command.

### Granting Permissions

To grant the `entcleanup.admin` permission to a group or user, use the following commands:

- Granting to a group:
    ```
    oxide.grant group <groupname> entcleanup.admin
    ```

- Granting to a user:
    ```
    oxide.grant user <username> entcleanup.admin
    ```

## Commands

- **/cleanup**: Forces an immediate cleanup of entities.
    - Usage: `/cleanup`
    - Permission required: `entcleanup.admin`

## Events

- **OnEntitySpawned**: Tracks the creation time of target entities for cleanup purposes.

## License

This plugin is open-source and available under the MIT License. Feel free to modify and distribute as needed.

