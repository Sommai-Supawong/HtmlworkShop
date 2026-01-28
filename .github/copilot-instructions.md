# Copilot Instructions for HtmlWorkShop

## Project Overview

This is an HTML/CSS learning workshop project featuring multiple educational modules on HTML fundamentals (headings, formatting, links, images, etc.) with modern, responsive styling. Each module is a standalone HTML file demonstrating specific web concepts.

## Architecture & Structure

- **Content Pages**: Individual `.html` files (W04_1_Headings.html, W06_03_HTMLlinks.html, etc.) represent separate workshop modules
- **Index**: `index.html` serves as the main landing page with navigation to all modules
- **Styling**: Global styles in `css/style.css` with many pages using embedded `<style>` tags for quick iteration
- **Assets**: `image/` folder contains images; external assets (fonts, icons) loaded from CDNs

## Key Design Patterns

### Styling Conventions

1. **Kanit Font**: All pages use `font-family: 'Kanit', sans-serif` (imported from Google Fonts)
2. **Card Component**: Consistent white `.card` containers with:
   - `border-radius: 12px` to `25px`
   - `box-shadow: 0 4px 12px rgba(...)` for depth
   - Border-top accent colors (default `#c4005a`)
3. **Color Scheme**:
   - Primary accent: `#c4005a` (pink/magenta) or `#ff0066`
   - Secondary: `#333` (dark text), `#555` (gray text)
   - Module-specific gradients (see `myGrade.html` for examples)
4. **Interactive Effects**:
   - Smooth transitions: `transition: all 0.3s ease` or `transition: 0.9s`
   - Hover transforms: `transform: translateY(-10px)` for lift effect
   - Rainbow gradient text animations (used in `index.html` navigation links)

### Layout Patterns

- **Container**: `.container { max-width: 900px; margin: 40px auto; padding: 0 20px; }`
- **Fixed Header**: Set `position: fixed; top: 0; width: 100%` with `scroll-padding-top: 250px` on html
- **Flexbox Navigation**: Use `.btn-text-link` as flex container with `gap: 10px` for button groups
- **Responsive**: Include `<meta name="viewport" content="width=device-width, initial-scale=1.0">`

## Content Conventions

- Page structure: `<header>` (nav) → `<section class="container">` (content cards) → `<footer>`
- Code examples shown in `<pre>` tags with left border: `border-left: 4px solid #c4005a`
- Learning notes in `.note` divs with emoji prefix (`💡 `)
- Links formatted with `text-decoration: none` and custom hover effects

## Common Edits & Workflows

- **Update Navigation**: Edit the nav links in `index.html` or individual page headers (often duplicated per page)
- **Add Modules**: Create new `.html` file following W04/W06/W07 naming pattern, copy header structure from existing pages
- **Global Style Changes**: Prefer `css/style.css` for shared styles; use embedded `<style>` for page-specific tweaks
- **Color Updates**: Search for hex colors like `#c4005a`, `#ff0066`, or class names like `.module-1`, `.module-2`, `.module-3`

## Important Notes

- Some pages have embedded styles overlapping `css/style.css` — check both locations when styling
- Font imports vary: some pages use Google Fonts Kanit, others reference system fonts; keep consistent
- External dependencies: Font Awesome icons (CDN link in myGrade.html), Google Fonts (multiple pages)
- No build process — files serve directly; test locally by opening `.html` files in browser

## File Reference Map

- **Headings module**: [W04_1_Headings.html](W04_1_Headings.html)
- **Links module**: [W06_03_HTMLlinks.html](W06_03_HTMLlinks.html)
- **Images module**: [W07_04_image.html](W07_04_image.html)
- **Grade tracking**: [myGrade.html](myGrade.html) (advanced styling example with gradients & cards)
- **Shared styles**: [css/style.css](css/style.css)
