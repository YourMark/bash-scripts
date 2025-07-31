# Scripts Collection

A collection of utility scripts for Laravel Herd and WordPress development.

## Scripts

### `create-wp-site`

A comprehensive WordPress site creation script that automates the entire setup process.

**Features:**
- Interactive site name input
- Multi-language support (English, Dutch, German, French, Spanish, Italian, Portuguese, Swedish, Danish, Norwegian)
- Single site or multisite installation options
- Automatic database creation and configuration
- SSL certificate setup via Laravel Herd
- Admin user creation with auto-generated secure passwords

**Usage:**
```bash
./create-wp-site [site-name]
```

**Requirements:**
- Laravel Herd
- WP-CLI
- Zsh shell

**Installation Process:**
1. Creates site directory in `$HERD_SITES_PATH` (defaults to `~/Sites`)
2. Downloads WordPress core in selected language
3. Configures database connection
4. Sets up admin user with auto-generated password
5. Optionally creates multisite with additional language subsites
6. Enables SSL via Herd

### `change_directory`

A Zsh function that automatically configures PHP, Composer, and WP-CLI commands when navigating to Laravel Herd sites.

**Features:**
- Automatically detects when you enter a Herd site directory
- Sets correct PHP version for the site
- Configures Composer to use site-specific PHP version
- Sets up WP-CLI with correct path and PHP version
- Provides `wpx` alias for WP-CLI with debug enabled
- Supports custom sites path via `HERD_SITES_PATH` environment variable

**Setup:**
1. Add to your `~/.zshrc`:
```bash
export HERD_SITES_PATH="/Users/yourusername/Sites/"
source /path/to/change_directory
```

**Aliases Created:**
- `composer` - Uses Herd's Composer with site-specific PHP
- `php` - Uses Herd's PHP for the current site
- `wp` - Uses WP-CLI with correct PHP version and path
- `wpx` - Uses WP-CLI with debug mode enabled

## Installation

1. Clone or download these scripts
2. Make them executable:
```bash
chmod +x create-wp-site
```
3. For `change_directory`, source it in your `~/.zshrc` as shown above

## Configuration

Set your sites path (optional):
```bash
export HERD_SITES_PATH="/path/to/your/sites/"
```

## Credits

The `change_directory` script is based on work by Marinus Klasen.