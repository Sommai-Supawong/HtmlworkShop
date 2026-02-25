# Copilot Instructions for HtmlWorkShop

## Project Overview

HTML/CSS learning workshop with standalone educational modules (W04_1_Headings.html, W06_03_HTMLlinks.html, etc.). No build process—files serve directly to browsers. Central landing page is `index.html`; advanced blog template in `W10_01_blogweb.html` linked to dedicated stylesheet `css/blogweb.css`.

## Architecture & Structure

**Three Stylesheet Zones:**
1. **Global styles**: `css/style.css` (used by W04-W07 modules) — sets `.container` (900px max), header positioning, base colors
2. **Blog styles**: `css/blogweb.css` (independent, used by W10_01_blogweb.html) — `.wrapper` pattern (1100px max), navbar gradients, hero sections
3. **Embedded styles**: Each module page has `<style>` tags for page-specific tweaks (card designs, module colors)

**Module Naming Convention:**
- `W04_*`: HTML basics (headings, formatting)
- `W06_*`: HTML intermediate (links)
- `W07_*`: HTML intermediate (images)
- `W10_*`: Advanced projects (blog, multi-section layouts)

## Critical Styling Patterns

### Core Design System
- **Font**: Kanit (Thai-optimized) imported from Google Fonts; fallback to sans-serif
- **Primary colors**: `#c4005a` (pink, borders/accents) or `#ff0066` (alternate accent)
- **Text colors**: `#333` (dark), `#555` (medium), `#999` (light)
- **Card component**: White bg, `border-radius: 12px`, `border-top: 4px solid #c4005a`, `box-shadow: 0 4px 12px rgba(0,0,0,0.08)`

### Interactive Animations
- **Hover effect**: `transform: translateY(-10px)` with `transition: 0.3s ease` on cards/links
- **Rainbow gradient text**: Used in `index.html` nav links—applies animated multi-color gradient with `background-clip: text`
- **Smooth scroll**: `scroll-behavior: smooth` on html; modules add `scroll-padding-top: 250px` for fixed headers

### Layout Structure
- **Simple modules** (W04-W07): `.container { max-width: 900px; margin: 40px auto; padding: 0 20px; }`
- **Blog** (W10): `.wrapper { width: 1100px; max-width: 90%; margin: 0 auto; }` for sidebar layouts
- **Fixed navigation**: `position: fixed; top: 0; width: 100%;` on `.header` (W10 uses `.site-header + .main-nav`)

## Content & Component Patterns

- **Page template**: `<header>` (nav) → `<section class="container">` (content) → `<footer>`
- **Code blocks**: `<pre>` with `background: #f0f0f0`, `border-left: 4px solid #c4005a`
- **Notes**: `.note` div with `::before { content: "💡 "; }` for emoji prefix
- **Buttons**: `.read-more` links in hero sections; blog uses flexbox nav with hover underlines
- **Responsive**: All pages include `<meta name="viewport" content="width=device-width, initial-scale=1.0">`

## Development Workflows

**Adding a Module:**
1. Create `W0X_##_topic.html` following nearest W0X pattern
2. Copy header/footer from similar module
3. Add embedded `<style>` tag with `.container` + `.card` styling
4. Decide: use `css/style.css` or create embedded styles for consistency

**Styling Changes:**
- **Shared**: Edit `css/style.css` (affects all W04-W07 modules)
- **Blog only**: Edit `css/blogweb.css` (only W10_01_blogweb.html)
- **One page**: Use embedded `<style>` in that `.html` file

**Navigation Updates:**
- `index.html` has inline `<a>` tags with gradient hover effects—update here for main landing
- Each W0X module duplicates its own header with links (check multiple places)
- Blog uses `<ul class="nav-menu">` inside `.main-nav`

## Critical Dependencies & Integration Points

- **Google Fonts**: Every page loads Kanit from CDN; some also use `<link rel="stylesheet" href="...">` 
- **Font Awesome Icons**: Loaded in `W10_01_blogweb.html` and `myGrade.html` (`css/all.min.css` from CDN)
- **Images**: Stored in `image/` folder; blog also uses external image URLs (background images)
- **No JavaScript**: All interactivity via CSS (animations, hover states, gradients)

## Important Caveats

- **Overlapping styles**: `css/style.css` and embedded styles can conflict—embedded wins (higher specificity). Always check both when debugging.
- **Font inconsistency**: Some pages hardcode `font-family: kanit, sans-serif` instead of inheriting—look for inline style declarations
- **Fixed header spacing**: W04-W07 pages add `scroll-padding-top: 250px` on `html` to offset fixed header. Blog (W10) doesn't have this set—may need adjustment.
- **No minification or build**: All files are human-readable source; test directly in browser

## File Reference Map

- **Landing page**: `index.html` (rainbow nav animation example)
- **Headings module**: `W04_1_Headings.html` (card + note patterns)
- **Blog template**: `W10_01_blogweb.html` (complex layout with navbar, hero, sidebar)
- **Grade tracker**: `myGrade.html` (gradient cards, Font Awesome icons)
- **Global styles**: `css/style.css` (W04-W07 consistency)
- **Blog styles**: `css/blogweb.css` (independent, 958 lines, `.wrapper` pattern)
