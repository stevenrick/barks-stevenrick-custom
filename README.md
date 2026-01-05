# Barks Steven Rick Custom Theme

Custom theme extensions for the [Barks Hugo theme](https://github.com/timothygebhard/barks), adding features specifically designed for academic and professional personal websites.

## Overview

This theme is designed to work **in composition** with the base Barks theme. It extends Barks with additional features while maintaining compatibility with the original theme.

## Features

- **Portfolio Grid System**: Responsive 3-column grid layout for showcasing projects
- **Publications Page**: Academic publication listing with year sections
- **Affiliations Page**: Professional roles and service page
- **Enhanced Landing Page**: Multi-section academic profile with customizable cards
- **Improved Typography**: Better readability and modern spacing
- **Card-Based Layouts**: Hover effects and visual hierarchy
- **Responsive Design**: Mobile-first approach with multiple breakpoints

## Installation

### Prerequisites

- Hugo Extended version >= 0.128.0
- Base [Barks theme](https://github.com/timothygebhard/barks) installed

### Setup

1. Add both themes to your Hugo site:

```bash
cd themes
git submodule add https://github.com/timothygebhard/barks.git
git submodule add https://github.com/stevenrick/barks-stevenrick-custom.git
```

2. Configure your `hugo.toml` to use both themes:

```toml
theme = ['barks-stevenrick-custom', 'barks']
```

**Important**: The order matters! `barks-stevenrick-custom` must come first so its templates and styles override the base theme.

## Usage

### Portfolio Section

Create portfolio items in `content/portfolio/`:

```markdown
+++
title = "Project Name"
featured_image = "images/project-thumbnail.jpg"
+++

## Overview
Project description...

## Artifacts
- [Paper](https://doi.org/...)
```

### Publications Page

Create `content/publications.md`:

```markdown
+++
title = 'Publications'
layout = 'publications'
+++

#### 2025

Author et al. (2025). [Title](https://doi.org/...).
*Venue*
```

### Affiliations Page

Create `content/links.md`:

```markdown
+++
title = 'Affiliations & Service'
layout = 'affiliations'
+++

## Current Roles

**Organization** (Role)
Description [Link →](https://example.com)
```

### Landing Page

Set the layout in `content/_index.md`:

```markdown
+++
layout = 'landing_page'
image = 'images/headshot.jpg'
+++

Tagline

## Current
- Item

## Prior
- Item

---
Call to action text
```

## Customization

All styling respects the color variables defined in your main `hugo.toml`:

```toml
[params.colors]
  background_color = "#fcfbf9"
  text_color = "#333333"
  link_color = "#60c17d"

[params.typography]
  title_font = "Roboto Serif"
  body_font = "Roboto Sans Serif"
```

## Architecture

This theme uses Hugo's theme composition feature:

1. **Base Imports**: Imports original Barks SCSS files
2. **Custom Overrides**: Adds `custom-*.scss` files that layer on top
3. **New Features**: Adds completely new layouts and styles

### File Structure

```
barks-stevenrick-custom/
├── assets/
│   ├── styles.scss              # Main entry point
│   ├── custom-*.scss            # Override files
│   ├── affiliations.scss        # New feature
│   ├── portfolio-single.scss    # New feature
│   └── publications.scss        # New feature
├── layouts/
│   ├── _default/
│   │   ├── affiliations.html
│   │   ├── publications.html
│   │   └── section.html         # Grid layout
│   ├── portfolio/
│   │   └── single.html
│   ├── partials/
│   │   ├── image-hero-small.html
│   │   └── navigation.html
│   └── landing_page.html        # Enhanced layout
├── theme.toml
├── LICENSE
└── README.md
```

## License

MIT License - see [LICENSE](LICENSE) for details.

## Credits

Built on top of the excellent [Barks theme](https://github.com/timothygebhard/barks) by Timothy Gebhard.

## Author

**Steven R. Rick**
- Website: [stevenrick.com](https://stevenrick.com)
- GitHub: [@stevenrick](https://github.com/stevenrick)
