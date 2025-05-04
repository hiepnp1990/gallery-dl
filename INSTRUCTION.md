# TikTok Download Guide

## Basic Usage
```bash
gallery-dl "https://www.tiktok.com/@user/photo/POST_ID"
```

## Filename Customization
### Command-line (one-time use)
```bash
gallery-dl -o "filename=rr_0002_{num}.{extension}" "URL"
```

### Config File (persistent)
1. Create/edit `~/.config/gallery-dl/config.json`
2. Add:
```json
{
    "extractor": {
        "tiktok": {
            "filename": "rr_0002_{num}.{extension}",
            "directory": "/path/to/save/folder"
        }
    }
}
```

## Available Filename Tokens
| Variable      | Description               | Example           |
|---------------|---------------------------|-------------------|
| `{num}`       | Image sequence number     | 01, 02            |
| `{user}`      | Creator's username        | reverserizzler    |
| `{post_id}`   | TikTok's unique post ID   | 7261260969735703814 |
| `{timestamp}` | UNIX timestamp            | 1690831200        |
| `{date}`      | Upload date               | 2023-08-01        |

## Authentication Required
Add browser cookies for restricted content:
```bash
gallery-dl --cookies-from-browser [chrome|firefox] "URL"
```

> **Note:** Command-line `-o` options override config file settings 