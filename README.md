## DDEV Dragonfly

## Overview

[Dragonfly](https://dragonflydb.io/) is a modern in-memory datastore, fully compatible with Redis and Memcached APIs. It delivers up to 25x more throughput and 80% memory efficiency compared to Redis.

This add-on integrates Dragonfly into your [DDEV](https://ddev.com/) project with data persistence enabled by default. Perfect for any application that needs a high-performance key-value store.

## Installation

```bash
ddev add-on get cyppe/ddev-dragonfly
ddev restart
```

After installation, make sure to commit the `.ddev` directory to version control.

## Usage

| Command | Description |
| ------- | ----------- |
| `ddev dragonfly-cli` | Run `redis-cli` inside the Dragonfly container |
| `ddev redis-cli` | Alias for `ddev dragonfly-cli` |
| `ddev dragonfly-flush` | Flush all cache inside the Dragonfly container |
| `ddev describe` | View service status and used ports for Dragonfly |
| `ddev logs -s dragonfly` | Check Dragonfly logs |

Dragonfly is available inside Docker containers with `dragonfly:6379` (Redis-compatible endpoint).

## Configuration

Dragonfly uses **command-line parameters** for configuration instead of configuration files, making it much simpler than Redis.

- ✅ **No configuration files needed**
- ✅ **Optimization built-in by default**
- ✅ **All settings handled via Docker Compose**
- ✅ **No authentication required** (Redis-compatible apps work out of the box)

For more information about Dragonfly, see the [Dragonfly documentation](https://dragonflydb.io/docs).

## Advanced Customization

Dragonfly works great out of the box with no additional configuration needed!

If you need to customize Dragonfly parameters, you can modify the `docker-compose.dragonfly.yaml` file directly. The default configuration provides:

- **Detailed logging** (`--logtostderr`)
- **Data persistence** (via Docker volume)
- **Optimal memory usage** (Dragonfly's built-in optimization)

The addon uses the official Dragonfly image: `docker.dragonflydb.io/dragonflydb/dragonfly`
