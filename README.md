# Unifier plugin template
This is a template repository you can use to write plugins for Unifier.

> [!NOTE]
> Once you have read through everything below and know what you're doing, you're free to replace
> this README file with whatever you want.

## plugin.json
plugin.json contains the metadata of your plugin, such as the plugin ID, name, etc. Unifier will
read this file on boot, so it knows which files to load to load your plugin.

### `id`
Plugin ID. Unifier uses this as the identifier for your plugin, and no plugin
installed to your bot may have the same ID. Users will need to specify the ID as the plugin when
running install, uninstall, and upgrade for plugins.

### `name`
Plugin name. Unlike plugin IDs, this can be whatever you desire.

### `description`
Plugin description. Describe what your plugin does here.

### `version`
Plugin version. We recommend you follow [semantic versioning](https://semver.org/) for this.

### `release`
Plugin release number. Unifier will use this to tell if the plugin is up to date or not.

### `minimum`
The minimum Unifier release required to use your plugin.

### `shutdown`
If your plugin needs special code being ran before being unloaded, set this to true.
> [!WARNING]
> If this is true, your plugin will not be able to be unloaded without a `[plugin_id]_check.py`
> file. You will need to specify this in the `utils` key.

### `modules`
Plugin modules. All files in here will be loaded as an extension when loading the plugin.

### `utils`
Plugin utility scripts. If `shutdown` is true, you **must** have `[plugin_id]_check.py` in here.

----

## Examples
Need an example to know what you need to have in your repository? You might want to check out
[unifier-revolt](https://github.com/UnifierHQ/unifier-revolt).

## Installing plugins
To install a plugin, run the `install <repo_url>` command. This will install a plugin from the
Git repository you specified.

## Licensing
As Unifier is AGPLv3 licensed, your plugin must be licensed AGPLv3 as well.
