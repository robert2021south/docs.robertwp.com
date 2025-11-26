# RW PostViewStats Pro (RWPSP) - User Guide

**Plugin Version:** 1.0.0  
**Compatible with WordPress:** 6.8  
**Minimum PHP Version:** 8.2  
**Minimum MySQL Version:** 8.0  
**Summary:** A multisite-supported view counter and data management tool for WordPress.

---

## 1. Installation & Configuration

### Installation Methods

- **Free Version:** Available in the WordPress plugin directory or via manual ZIP upload.
- **Pro Version:** Downloadable from Codecanyon.net. Install manually via ZIP upload in WordPress.

### Initial Setup

- After activation, the plugin starts working immediately.
- An optional **Settings** button is available next to the plugin entry in the WordPress admin panel.

### Multisite

- Requires **Network Admin** privileges.
- Fully compatible with WordPress Multisite architecture.

---

## 2. Feature Modules

### 2.1 View Counter

- **Supports:** Posts, Pages, Custom Post Types.
- **Excludes:** No specific exclusions — attachments, WooCommerce products, and other post types are counted unless manually disabled by the user.
- **Anti-Duplication Logic:** A view is counted only once per browser within a 12-hour window. Switching to another browser may generate an additional view because the system does not use IP restrictions.
- **User Scope:** Views are counted the same way for all visitors — logged-in and non-logged-in users are treated equally.
- **Tracking Method:** Automatically integrated — no manual code insertion required.

---

### 2.2 Data Management

#### Cleaning

- **Functionality:** 
 
    The cleaning tool removes outdated tracking data but never deletes all statistics at once. It always retains data newer than the specified date.

 
- **Lite Version Behavior:** 
  - Automatically restricts cleaning to data older than 30 days.
  - Always keeps statistics from the most recent 30 days.
  - Post type is limited to post and page only.
 
 
- **Pro / Lifetime Version Behavior:** 
  - Allows selecting any custom date to decide which data to keep.
  - Data older than the chosen date will be removed.
  - Supports cleaning for any registered post type.


- **Safety:** Only expired data is removed; valid and recent data is retained and recalculated, ensuring that total counts remain accurate.

#### Export

- **Formats:** CSV.
- **Fields:** Post ID, Title, Views.

---

### 2.3 Shortcodes

Example:
```shortcode
[rwpsp_post_views post_id="123"]
```

- **Parameters:**
  - `post_id` — NQuery a specific post by its ID. Example: [rwpsp_post_views post_id="123"]. (Lite/Pro/Lifetime)
  - `date` — Show views for a specific date. Format: YYYY-MM-DD. Example: [rwpsp_post_views date="2023-01-01"]. (Pro only)
  - `start` — Start date for a range query. Format: YYYY-MM-DD. Used together with end. Example: [rwpsp_post_views start="2023-01-01" end="2023-01-31"]. (Pro only)
  - `end` — End date for a range query. Format: YYYY-MM-DD. Used together with start. (Pro only)
- **Theme Dependency:** Not required.

---

### 2.4 REST API

- **Endpoint Example:**
  ```
  /wp-json/rwpsp/v1/views/{post_id}?days=7
  ```

- **Authentication:** Basic Auth or WordPress REST authentication.
- **Sample JSON Response:**
```json
{
  "post_id": 123,
  "total_views": 1578,
  "daily_views": {
    "2025-07-01": 300,
    "2025-07-02": 220
  }
}
```

---

### 2.5 Multisite Support

- **Per-Site Tracking:** Each site maintains its own view counts.
- **Network Admin Controls:** Super admins can enter the purchase code in the Network Admin to activate Pro features and push unified settings to child sites, but they cannot view or manage individual sites’ statistics from a single, network-wide dashboard.

---

## Support

For more details, licensing, or updates, visit [Codecanyon - RWPSP](https://codecanyon.net/item/rw-postviewstats-pro/12345678).

