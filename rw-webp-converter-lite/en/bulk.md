# Bulk Conversion

Bulk Conversion allows you to convert existing JPG and PNG images in your WordPress media library into WebP format in batches.

This feature is designed to help you optimize previously uploaded images without affecting newly uploaded files.

---

## Where to Find Bulk Conversion

1. Go to **Tools → RW WebP Converter**
2. The plugin page contains three tabs
3. Bulk conversion is available on the default **Overview** tab

Most users will spend most of their time on the Overview tab, as it contains the bulk conversion tools and status information.

---

## Overview Tab Layout

The Overview tab is divided into three sections:

### 1. Statistics

This section displays real-time statistics about your media library:

- Total number of images
- Number of images already converted to WebP
- Number of images not yet converted
- Number of images skipped due to small image size

Images smaller than the configured size threshold will be skipped automatically.

---

### 2. Bulk Conversion Button

The bulk conversion process is started using a single button.

**How it works:**

1. Click the **Bulk Convert** button
2. A progress bar will appear on the page
3. Images are converted in batches using AJAX
4. Each batch processes **20 images**
5. The process continues until all eligible images are processed

⚠️ After the conversion finishes, you must **manually refresh the page** to see updated statistics and conversion records.

---

### 3. Recent Conversion Records

This section shows recent conversion activity.

- Only the **latest 20 records** are stored
- Older records are automatically removed
- Records are stored using WordPress transients (Lite version limitation)

This provides a lightweight history without increasing database load.

---

## Supported Image Formats

Bulk conversion currently supports the following image formats:

- JPG
- JPEG
- PNG

Other image formats (such as GIF or SVG) are skipped automatically.

> The plugin does not explicitly notify users when unsupported formats are skipped.

---

## Image Size Rules

You can configure a minimum image size in the **Settings** tab.

- Images with their **longest edge smaller than the configured value** (e.g. 300px)
- These images will be skipped and not converted

This helps avoid unnecessary conversion of small images.

---

## Output Behavior

- Original images are **not replaced** in the Lite version
- WebP files are generated alongside original images
- WebP filenames follow the WordPress media library naming structure
- Only the file extension is changed to `.webp`

> URL replacement is a **Pro version feature** and is not available in the Lite version.

---

## Performance Notes

- There is **no per-run image limit**
- Large media libraries may take longer to process
- The conversion process does not include timeout protection
- Shared hosting environments may experience slower processing

For best results, avoid running bulk conversion during peak traffic hours.

---

## Error Handling

- If an image fails to convert, it will be skipped
- No error message is displayed for failed conversions
- The bulk process continues with remaining images

This behavior is intended to keep the conversion process lightweight and uninterrupted.

---

## Server Requirements

RW WebP Converter Lite requires one of the following PHP extensions:

- **GD Library**
- **Imagick**

If neither extension is available, the plugin will display a notice and bulk conversion will not run.

The plugin does **not** require the server to natively serve WebP files, although PHP must be compiled with WebP support for image generation.

---

## CDN & Cache Compatibility

- The Lite version does **not** include CDN or cache integration
- Converted WebP files are generated only at the file level

Advanced delivery features are available in the Pro version.

