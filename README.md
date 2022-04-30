# minecraft-playbook
Ansible Playbook to deploy minecraft server with plugins.

## Environment vars
Create `pd_settings.yml` under `var/game_type` folder and add these vars into it:
- `pd_host`: the domain name of your pterodactyl panel
- `pd_token`: the **ADMIN** API token of your pterodactyl panel

## Update plugins only
- `mnt_dir` is the directory where the plugins will be or has been installed.
- `game_type` is the type of list of plugins variables.
```bash
ansible-playbook playbook-plugin.yml -e "game_type=<what_vars_folder_name> mnt_dir=<where_plugins_saved> do_update=yes"
```
## Create symlinks only
- `server_external_id` is the "External Identifier" in your pterodactyl server detail. You can find it in the `admin panel`->`server`->`detail`->`Base Information`.
```bash
ansible-playbook playbook-plugin.yml -e "game_type=<what_vars_folder_name> mnt_dir=<where_plugins_saved> server_external_id=<> do_update=yes do_symlink=yes"
```