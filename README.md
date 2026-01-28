# Varbase Media Assets

A recipe to manage importing default demo media assets for Varbase Media Types.

This recipe provides a pre-set of default media assets (images, videos, documents) for all Varbase Media Types, which are needed in development, testing, and demos.

## Installation

Change directory to the Varbase Project in the terminal:
```bash
cd /var/www/html/projects/PROJECT_DIR_NAME
```

Install with Composer:
```bash
composer require 'drupal/varbase_media_assets'
```

Apply the recipe:
```bash
drush recipe varbase_media_assets
```

## What's Included

This recipe includes:
- Demo image files (PNG, JPG, WebP formats)
- Demo video files (MP4, remote video links)
- Pre-configured media entities for all Varbase Media Types
- Content ready for use in development and testing environments

## Usage

After applying the recipe, you can view the imported media assets by navigating to `/admin/content/media-grid` in your Drupal site.

## Related Recipes

- `varbase_media_base` - The main Varbase Media configuration
- Other Varbase base recipes

## Support

For issues and feature requests, please visit:
https://www.drupal.org/project/issues/varbase_media_assets
