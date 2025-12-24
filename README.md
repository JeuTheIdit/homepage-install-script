# Homepage install script
This script installs [Homepage](https://gethomepage.dev/) from source, or updates from source if it is already installed and a newer version is available. See [`SUMMARY.md`](https://github.com/jnbolsen/homepage-install-script/blob/main/SUMMARY.md) for more detail on what the script does.

> [!NOTE]
> The script installs dependencies and builds using pnpm [as recommended](https://gethomepage.dev/installation/source/). The latest verison is installed globally using npm.

## Requirements
The following packages are installed:
- node.js
- npm
- curl

```bash
sudo apt install curl nodejs npm
```

## Usage
Download `install.sh`.

```bash
wget -O install.sh https://raw.githubusercontent.com/jnbolsen/homepage-scripts/refs/heads/main/install.sh
```

> [!NOTE]
> As of v1.0 there is one required environment variable to access Homepage via a URL, [`HOMEPAGE_ALLOWED_HOSTS`](https://gethomepage.dev/installation/).
>
> This script by default adds `localhost` and the IP address of the host to `HOMEPAGE_ALLOWED_HOSTS`. The user will also be prompted to enter an internal domain, which the `HOSTNAME`.`DOMAIN` will be added to `HOMEPAGE_ALLOWED_HOSTS` if provided.

Make the scrip executable.

```bash
sudo chmod +x install.sh
```

Run the script.

```bash
sudo ./install.sh
```

## Directories
- Installation: `/opt/homepage`
- Working (cleaned after installation): `/tmp`
- Configuration: `/opt/homepage/config`

## Tested environments
Ubuntu 22.04, 24.04, and 25.10 <br />
Debian 12 and 13

## Reference
Some ideas for this script came from the LXC Homepage scripts from [PVE community-scripts](https://community-scripts.github.io/ProxmoxVE/scripts?id=homepage).

## License

[MIT](https://github.com/jnbolsen/homepage-scripts/blob/main/LICENSE.md)
