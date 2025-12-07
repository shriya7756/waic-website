# Modular Website Structure

## Overview
The website has been reorganized into a modular structure for better maintainability and organization. The long HTML and CSS files have been separated into individual section files.

## File Structure

```
waicf/
├── sections/
│   ├── html/
│   │   ├── navbar.html      # Navigation bar
│   │   ├── hero.html        # Hero section with mission statement
│   │   ├── about.html       # About/Who we are section
│   │   ├── impact.html      # Statistics and impact section
│   │   ├── solutions.html   # How we solve the problem section
│   │   ├── programs.html    # Our flagship programs section
│   │   ├── testimonials.html # Customer testimonials section
│   │   ├── footer.html      # Footer with links and contact
│   │   └── cta.html         # Call-to-action "Join Us" section
│   └── css/
│       ├── main.css         # Main CSS file that imports all sections
│       ├── navbar.css       # Navbar-specific styles
│       ├── hero.css         # Hero section styles
│       ├── about.css        # About section styles
│       ├── impact.css       # Impact section styles
│       ├── solutions.css    # Solutions section styles
│       ├── programs.css     # Programs section styles
│       ├── testimonials.css # Testimonials section styles
│       ├── footer.css       # Footer section styles
│       └── cta.css          # CTA section styles
├── index.html               # Original monolithic file
├── index-modular.html       # New modular version
├── style.css               # Original CSS file
└── ...other files
```

## How It Works

### HTML Structure
- **index-modular.html**: Main HTML file that loads all sections dynamically
- **sections/html/**: Individual HTML files for each website section
- Each section is loaded via JavaScript into designated containers

### CSS Structure
- **sections/css/main.css**: Central CSS file that imports all section-specific styles
- **sections/css/[section].css**: Individual CSS files containing styles for each section
- Maintains all original styling while organizing code by functionality

### JavaScript Loading
The modular version uses JavaScript to dynamically load HTML sections:

```javascript
// Loads each section asynchronously
loadSection('navbar-section', 'navbar.html');
loadSection('hero-section', 'hero.html');
// ... etc
```

## Benefits

1. **Maintainability**: Each section can be edited independently
2. **Organization**: Related HTML and CSS are grouped together
3. **Reusability**: Sections can be easily reused or rearranged
4. **Collaboration**: Multiple developers can work on different sections
5. **Performance**: Sections can be lazy-loaded if needed
6. **Debugging**: Easier to isolate and fix issues in specific sections

## Usage

### Development
- Edit individual section files in `sections/html/` and `sections/css/`
- Use `index-modular.html` for the modular version
- Original `index.html` remains unchanged for compatibility

### Adding New Sections
1. Create HTML file in `sections/html/`
2. Create CSS file in `sections/css/`
3. Add CSS import to `sections/css/main.css`
4. Add section loading to `index-modular.html`

### Deployment
- Ensure all section files are deployed with the main files
- The modular version requires a web server (not file:// protocol) due to fetch() usage

## Files Overview

| Section | Purpose | Key Classes |
|---------|---------|-------------|
| navbar | Navigation bar | `.navbar`, `.nav-bar`, `.nav-nav-menu` |
| hero | Main hero section | `.pink-light-gradient`, `.we-are-on-a-mission` |
| about | About/Who we are | `.who-we-are`, `.text-content-box` |
| impact | Statistics | `.impact`, `.transparent-card` |
| solutions | Problem solving approach | `.how-we-solve-the`, `.pillars` |
| programs | Course offerings | `.our-program`, `.card` |
| testimonials | Customer reviews | `.testimonial`, `.frame-19` |
| footer | Footer links | `.footer`, `.footer-link` |
| cta | Call-to-action | `.JOIN-US`, `.frame-30` |

## Migration Notes
- All original functionality is preserved
- CSS variables and global styles remain in the main files
- JavaScript interactions work the same way
- Images and assets use the same paths
