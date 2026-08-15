[![Varbase](https://raw.githubusercontent.com/Vardot/varbase/11.0.x/images/varbase-logo.png)](https://www.drupal.org/project/varbase)

# Varbase Media Assets
[![pipeline status](https://git.drupalcode.org/project/varbase_media_assets/badges/1.0.x/pipeline.svg)](https://git.drupalcode.org/project/varbase_media_assets/-/pipelines)
[![Varbase Media Assets](https://img.shields.io/badge/Varbase%20Media%20Assets-1.0.0--rc1-0d6efc?labelColor=001d38&style=flat-square)](https://git.drupalcode.org/project/varbase_media_assets/-/pipelines?ref=1.0.0-rc1)
[![Automated Functional Testing](https://git.drupalcode.org/project/varbase_project/badges/11.0.x/pipeline.svg)](https://git.drupalcode.org/project/varbase_project/-/pipelines)

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
- A demo local video file (MP4)
- Pre-configured media entities for all Varbase Media Types
- Content ready for use in development and testing environments

### Optional: Remote video (oEmbed) samples

A sample Vimeo video and a sample YouTube video for the "Remote video" media
type are **not** included in the default recipe above. Importing a "Remote
video" media item requires Drupal core to make a live network request to the
oEmbed provider APIs (`oembed.com`, `vimeo.com`, `youtube.com`) to validate
the URL. That request has a short timeout and no retry, so shipping it as
part of the default, unattended `drush site:install` path made fresh
installs of this recipe fail intermittently (see
[#3608868](https://www.drupal.org/project/varbase_media_assets/issues/3608868)).

To add the two remote video samples to a site that is already installed and
has working network access, apply the companion recipe explicitly:
```bash
drush recipe web/recipes/varbase_media_assets/remote_video_samples
```
(adjust the path to wherever Composer placed the `varbase_media_assets`
recipe in your site, e.g. `recipes/varbase_media_assets/remote_video_samples`).
If the command fails due to a transient network/provider issue, it is safe
to simply retry it — it does not affect the rest of the site.

## Usage

After applying the recipe, you can view the imported media assets by navigating to `/admin/content/media-grid` in your Drupal site.

## Related Recipes

- `varbase_media_base` - The main Varbase Media configuration
- Other Varbase base recipes

## Support

For issues and feature requests, please visit:
https://www.drupal.org/project/issues/varbase_media_assets
