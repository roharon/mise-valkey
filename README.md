# mise-valkey

[mise](https://github.com/jdx/mise) plugin for [Valkey](https://valkey.io/), the high-performance key-value store.

## Installation

```
mise plugins install valkey https://github.com/roharon/mise-valkey.git
```

## Usage

```bash
# Install a specific version
mise install valkey@8.1.1

# Set a version globally
mise use -g valkey@8.1.1

# Set a version locally in the current directory
mise use valkey@8.1.1

# Run valkey-server with a specific version without installing it
mise exec valkey@8.1.1 -- valkey-server
```

## Features

- Installs Valkey from the [official valkey repository](https://github.com/valkey-io/valkey)
- Creates convenient symlinks for valkey-server and valkey-cli
- Supports multiple architectures and operating systems

## Available Versions

To see all available versions:

```bash
mise ls-remote valkey
```

## Try it out

1. Start Valkey server: `valkey-server`
2. Open another terminal and connect using the CLI: `valkey-cli`
3. Test key operations:
   ```bash
   127.0.0.1:6379> set mykey "Hello Valkey"
   OK
   127.0.0.1:6379> get mykey
   "Hello Valkey"
   ```

## Development

This plugin has a simple structure:

- `bin/list-all` - Script to list all available versions of Valkey
- `bin/install` - Script to install a specific version of Valkey

### Setup Local Development Environment

1. Clone this repository:
   ```bash
   git clone https://github.com/roharon/mise-valkey.git
   cd mise-valkey
   ```

2. Set up mise to use your local copy of the plugin:
   ```bash
   mise plugins link valkey .
   ```

3. Test installation:
   ```bash
   mise install valkey@latest
   ```

### Plugin Structure

- **bin/list-all**: Queries GitHub for available Valkey versions
- **bin/install**: Handles downloading and installing Valkey binaries

## Contributing

Contributions are welcome! See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## Acknowledgements

This project was inspired by [mise-redis](https://github.com/mise-plugins/mise-redis).

## License

MIT License
