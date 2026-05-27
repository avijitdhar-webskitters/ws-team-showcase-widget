# WS Team Showcase Widget

Custom Elementor widget plugin for a reusable agency/team section.

## Features

- Elementor `Widget_Base` architecture with OOP PHP.
- Repeater-based team member fields: name, designation, department, bio, image, social links, experience, and CTA button.
- Data source switcher for Manual Repeater or ACF Repeater.
- Backend grid controls in **Grid Settings** for desktop, tablet, and mobile cards per row.
- Optional front-end Grid/List view switcher with a configurable default view.
- `Team Showcases` custom post type with local ACF repeater fields for reusable team datasets.
- Layout controls for responsive columns, card alignment, card height, image position, popup toggle, department filter, search filter, lazy loading, skeleton loader, GSAP animation, and dark mode.
- Style controls for background, border radius, border, shadow, typography, hover effects, and button styling.
- Responsive grid layout with lazy-loaded images.
- Department filters and search powered by nonce-protected WordPress AJAX.
- Popup modal for detailed team member information opened from the member image or title.
- Search icon picker and Search Bar style controls from Elementor.
- Automatic Load More button when more than 8 members are configured.
- Skeleton loader during AJAX requests.
- Optional GSAP card entrance animation.

## Installation

1. Place the `ws-team-showcase-widget` directory inside `wp-content/plugins/`.
2. Activate **WS Team Showcase Widget** from WordPress admin.
3. Edit a page with Elementor.
4. Add the **WS Team Showcase** widget from the Basic category.

## ACF Repeater Workflow

1. Install and activate Advanced Custom Fields.
2. In WordPress admin, open **Team Showcases** and create a new showcase.
3. Add team members in the **Team Members** repeater. Fields include name, designation, department, bio, profile image, nested social links, experience, button text, and button URL.
4. Edit a page with Elementor, add **WS Team Showcase**, set **Data Source** to **ACF Repeater**, and select the Team Showcase post.

If ACF is inactive, the widget continues to work with the Manual Repeater source and shows an admin notice for the ACF source.

The **Team Showcases** post type and local ACF field group are registered automatically when the plugin is active. On plugin deletion, `uninstall.php` removes Team Showcase posts and any matching ACF field group records that were saved/synced into the database.

## Backend Managed Bonus Features

- Lazy Loading: **Layout > Lazy Loading**
- GSAP Animation: **Layout > GSAP Animation**
- Skeleton Loader: **Layout > Skeleton Loader**
- Search Filter: **Layout > Search Filter**
- Load More AJAX: automatic when more than 8 members exist
- ACF Integration: **Team Members > Data Source > ACF Repeater**
- Dark Mode Toggle: **Layout > Dark Mode Toggle**
- Department Filtering: **Layout > Department Filter**
- Grid/List Switcher: **Grid Settings > Grid / List View Switcher**
- Default Front-End View: **Grid Settings > Default View**

## Folder Structure

```text
ws-team-showcase-widget/
├── assets/
│   ├── css/
│   ├── js/
│   └── images/
├── includes/
│   ├── widgets/
│   └── ajax/
├── ws-team-showcase-widget.php
└── README.md
```

## Security Notes

- AJAX requests use `check_ajax_referer()`.
- All incoming AJAX data is sanitized before filtering or rendering.
- Output uses escaping functions such as `esc_html()`, `esc_url()`, `esc_attr()`, and `wp_kses_post()`.
- External social links use `rel="noopener noreferrer"`.

## AI Usage Report

Tool used: ChatGPT / Codex.

Prompts used:

1. "Create Elementor repeater controls for a Team Showcase widget."
   - Output: Generated the repeater control plan covering member profile fields, nested social links, and CTA fields.
2. "Create secure WordPress AJAX filtering using nonce verification."
   - Output: Produced the AJAX handler approach using `wp_ajax_*`, `wp_ajax_nopriv_*`, `check_ajax_referer()`, sanitization, filtering, and JSON responses.
3. "Generate Elementor responsive controls for grid columns."
   - Output: Produced responsive column control using CSS custom properties and Elementor selectors.
4. "Design frontend JS for Elementor widget filter, search, modal popup, and load more."
   - Output: Generated the jQuery workflow for state management, AJAX refreshes, modal rendering, and automatic load-more pagination.
5. "Create a WordPress custom post type with ACF repeater fields for reusable Elementor team showcase data."
   - Output: Added the `Team Showcases` CPT, local ACF field group, nested social links repeater, Elementor data source selector, and ACF-to-frontend member normalization.

AI-assisted outputs were reviewed and adapted for this codebase, then manually checked for WordPress escaping, sanitization, Elementor compatibility, and file organization.
