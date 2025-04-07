# Elixir Phoenix Development Shell

This repository provides a Nix-based development environment for Elixir Phoenix projects. It uses Nix flakes to manage dependencies and ensure reproducible development environments.

## Prerequisites

- [Nix](https://nixos.org/download.html) installed on your system
- [Git](https://git-scm.com/downloads) installed on your system

## Getting Started


- Enter the development shell with base shell:
   ```bash
   nix develop github:not-another-boring-git/devShell
   ```

   This will drop you into a shell with all the necessary dependencies installed.

Or

- Enter the development shell using your own shell config:
   ```bash
   nix develop github:not-another-boring-git/devShell -c $SHELL -l
   ```

    This will drop you into a shell with all the necessary dependencies installed and with your own shell config.


## Available Commands

Once inside the development shell, you'll have access to:

- `mix` - Elixir's build tool
- `elixir` - Elixir runtime
- `iex` - Interactive Elixir shell
- `nodejs` - Node.js runtime
- `postgresql` - PostgreSQL database

## Building Docker Images

The repository also includes support for building Docker images. You can build them using:

```bash
nix build .#docker-image-triggered-by-<system>
```

Replace `<system>` with your target system (e.g., `x86_64-linux`, `aarch64-linux`).

## Project Structure

- `flake.nix` - Main Nix flake configuration
- `nix/` - Directory containing Nix expressions
  - `overlay.nix` - Custom package overlays
  - `shell.nix` - Development shell configuration
  - `release.nix` - Release configuration
  - `docker-image.nix` - Docker image configuration

## Troubleshooting

If you encounter any issues:

1. Make sure you have the latest version of Nix installed
2. Try cleaning your Nix store:
   ```bash
   nix store gc
   ```
3. If the shell fails to build, try:
   ```bash
   nix flake update
   ```

## Contributing

Feel free to open issues or submit pull requests for any improvements or bug fixes.

## License

This project is open source and available under the MIT License.
