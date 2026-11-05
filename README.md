# Imageboard

A simple PHP imageboard. Supports threads with images, expiry, passwords, and a moderator panel.

## Key Features

- **Public and private threads** – threads can be public (visible on the homepage) or private (password protected).
- **Thread passwords** – optional password encrypts content and images (AES-256-CBC). Threads can be opened with a link like `?thread=ID&password=...`.
- **Image uploads** – JPEG images are scaled (optionally) and stamped; in protected threads they are encrypted.
- **Interactive viewing** – image lightbox, thread preview, active-users counter, auto-refresh.
- **Thread expiry** – threads are removed after a chosen duration (15 min – 7 days).
- **Freezing** – threads can stop accepting new posts after a period of inactivity.
- **Updater** – update the whole board from a ZIP package while preserving `threads/`, `boardban.json`, `ipnotes.json` and merging `config.php`.
- **Moderator panel** – manage threads and keep notes about IP addresses.
- **Terms of service & cookie nick** – requires accepting terms and assigns a random nickname via cookie.

## Structure

- `index.php` – application router
- `controller/` – controllers
- `model/` – thread data access (`threads/`)
- `view/` – PHP views
- `include/` – helper functions and configuration
- `updater.php` – update from a ZIP package
- `moderator/` – moderator panel
- `style.css` – stylesheet

## Configuration

Define in `include/config.php`:
- `SECRET_KEY` – application key
- `IP_NOTES_FILE` – IP notes file (default `ipnotes.json`)
- `MAX_IMAGE_HEIGHT`, `SHOULD_SCALE_IMAGE` – image scaling

## Requirements

- PHP with `openssl` and `zip` extensions
- Web server (Apache/Nginx) with write access to the board directory and `threads/`

## License

OpenSource
