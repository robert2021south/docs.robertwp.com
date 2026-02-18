# Settings

RW WebP Converter Lite provides a simple and flexible settings panel that allows you to control how images are converted and stored.

All settings can be found in the **Settings** tab of the plugin page.

---

## Automatically Optimize Images on Upload

**Type:** Checkbox  
**Default:** Enabled

When enabled, images will be automatically converted to WebP format after they are uploaded to WordPress.

- Conversion runs after WordPress generates attachment metadata
- Only the scaled original image is processed
- Other image sizes are not converted

Disabling this option completely turns off automatic conversion.

> Users on shared hosting or who prefer manual control may choose to disable this option and use bulk conversion instead.

---

## WebP Quality

**Type:** Dropdown  
**Default:** `80`

Sets the quality level for generated WebP images.

- Higher values produce better visual quality
- Lower values result in smaller file sizes

Recommended values range from **70–85**, depending on your quality and size requirements.

> This setting affects both automatic and bulk conversions.

---

## Keep the Original Images After WebP Conversion

**Type:** Checkbox  
**Default:** Enabled

When enabled, original JPG/PNG images are kept after WebP conversion.

- Ensures compatibility with themes, plugins, and browsers
- Allows fallback to original formats if needed

If disabled, original images may be removed after successful conversion.

> This option applies to both bulk and automatic conversion.

---

## Overwrite Existing WebP Files If They Exist

**Type:** Checkbox  
**Default:** Disabled

When enabled, existing `.webp` files will be overwritten during conversion.

This option is useful when:

- You change the WebP quality setting
- You want to regenerate WebP images with new rules

When disabled, existing WebP files are skipped.

---

## Skip Images Smaller Than This Pixel Size

**Type:** Number Input  
**Default:** `300`

Defines the minimum image size (longest edge in pixels) required for conversion.

- Images with a longest edge smaller than this value are skipped
- Helps avoid converting icons, logos, and very small images

Set this value to `0` to convert **all images**, regardless of size.

This rule applies to both bulk and automatic conversion.

---

## Delete All Plugin Data on Uninstall

**Type:** Checkbox  
**Default:** Disabled

When enabled, all plugin data will be removed when the plugin is uninstalled, including:

- Plugin settings
- WebP conversion records
- Stored transients

If disabled, plugin data will remain in the database after uninstall.

> Enable this option only if you are sure you no longer need any plugin data.

---

## Pro Version Options (Disabled in Lite)

The following options are available in the Pro version and are shown in Lite as disabled features:

### Smart PNG/JPEG Optimization
Apply different compression strategies for JPEG and PNG images to better preserve quality and transparency.

### WebP & AVIF Formats
Optimize images using modern formats such as WebP and AVIF for smaller file sizes and broader browser support.

### Retina & Responsive Optimization
Automatically generate multi-size images and integrate with `srcset` and `picture` elements for responsive and high-DPI displays.

### Preserve EXIF Metadata
Keep camera, author, and copyright metadata for professional photography workflows.

### Conversion History & Advanced Logs
Store full conversion history and provide detailed error reporting and diagnostics.

### CDN / External Storage Compatibility
Serve optimized images via CDN or external storage for improved performance on high-traffic websites.

### White-label Mode
Remove plugin branding from admin pages and front-end output.

### Priority Support & Early Access
Receive priority support and early access to new features.

