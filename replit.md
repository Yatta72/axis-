# VideoEditBot

A Discord bot that performs video editing commands via chat messages. Users can apply effects, concatenate videos, download media, and more.

## Architecture

- **Language**: Python 3.12
- **Entry point**: `discordBot.py`
- **No frontend** - runs as a console workflow

## Key Files

- `discordBot.py` - Main bot entry point and command router
- `config.json` - Runtime configuration (not committed to git)
- `config.json.template` - Template for config.json
- `combiner.py` - Video concatenation logic
- `func_helper.py` - Async task/action helpers
- `editor/` - Video editing modules (effects, captions, download, etc.)

## Configuration

`config.json` controls timeouts, command limits, donor system, and response messages. The Discord token is read from the `DISCORD_TOKEN` environment secret (falls back to `config.json`).

Donor checking is disabled by default (`disable_donor_check: true`). To enable it, set a valid `donor_guild_id` and set `disable_donor_check` to `false`.

## Dependencies

### System packages
- `ffmpeg` - Video processing
- `sox` - Audio processing

### Python packages
- `discord.py` - Discord API
- `ffmpeg-python`, `ffprobe-python` - FFmpeg bindings
- `yt-dlp` - Video downloading
- `pydub` - Audio manipulation
- `Pillow` - Image processing
- `pyjson5` - JSON5 config parsing
- `psutil`, `requests` - Utilities

## Secrets

- `DISCORD_TOKEN` - Discord bot token (from Discord Developer Portal)

## Workflow

- **Start application**: `python discordBot.py` (console output)
