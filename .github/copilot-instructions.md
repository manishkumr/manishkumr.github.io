# Personal Portfolio Website (manishkumr.github.io)

Always reference these instructions first and fallback to search or bash commands only when you encounter unexpected information that does not match the info here.

This is a static HTML personal portfolio website hosted on GitHub Pages. It features an interactive single-page application with JavaScript navigation, a comprehensive Django & GraphQL learning module, and responsive design using Tailwind CSS.

## Working Effectively

### Bootstrap and serve the repository
- **CRITICAL**: No build process is required. This is a pure static HTML/CSS/JS website.
- Install HTML validation tools: `npm install -g html-validate`
- Start local development server: `python3 -m http.server 8080` 
  - **Timing**: Server starts in ~2 seconds. NEVER CANCEL.
  - Access at: `http://localhost:8080` or `http://localhost:8080/index.html`
- **NEVER CANCEL**: Allow full server startup time (2-3 seconds minimum)

### HTML validation and linting
- Run HTML validation: `html-validate index.html`
  - **Expected issues**: The validation will find 22 problems including accessibility issues, raw "&" characters that need encoding as "&amp;", missing button types, and multiple `<main>` elements
  - **CRITICAL**: Do not fix these automatically unless specifically requested - the site works despite these warnings
- No CSS or JavaScript linting tools are configured by default
- **Timing**: HTML validation completes in ~5 seconds. NEVER CANCEL.

### Testing the application
- **MANUAL VALIDATION REQUIREMENT**: After any changes, you MUST test complete user workflows:
  1. Navigate to all three main sections (About Me, Projects, Learning) via the navigation bar
  2. Click the "Interactive Guide to Django & GraphQL" learning card to enter the detailed module
  3. Test navigation within the learning module between different chapters
  4. Use the "Back to Profile" button to return to the main view
  5. Verify all interactive elements work (buttons, links, navigation)
- **Visual validation**: Take screenshots to verify UI changes work correctly
- Test that external links (LinkedIn, email) are functional
- **NEVER** skip manual testing - JavaScript functionality is critical to user experience

## Repository Structure

### Key files and directories
```
/home/runner/work/manishkumr.github.io/manishkumr.github.io/
├── index.html          # Main HTML file with embedded CSS/JS (39,922 bytes)
├── images/            # Profile images and assets
│   └── 8082598.jpg    # Profile picture
├── javascripts/       # JavaScript files
│   └── main.js        # Minimal JS (currently just console.log)
├── stylesheets/       # CSS files
│   ├── stylesheet.css # Main stylesheet
│   ├── github-light.css # GitHub theme
│   └── print.css      # Print styles
├── params.json        # GitHub Pages configuration
└── .project           # IDE configuration file
```

### Application architecture
- **Single-page application**: All content in `index.html` with JavaScript navigation
- **No build system**: No package.json, webpack, or bundling required
- **CDN dependencies**: Uses Tailwind CSS, Chart.js, and Google Fonts via CDN
- **Embedded code**: All CSS and JavaScript is embedded in the HTML file
- **GitHub Pages**: Automatically deployed when pushed to main branch

## Validation Scenarios

### Complete user workflow testing
**CRITICAL**: Always run these complete scenarios after making changes:

1. **Main navigation flow**:
   - Load the homepage at `http://localhost:8080`
   - Click "About Me" - verify content loads and navigation highlights
   - Click "Projects" - verify projects section displays
   - Click "Learning" - verify learning modules section shows

2. **Learning module interaction**:
   - From Learning section, click "Interactive Guide to Django & GraphQL"
   - Verify detailed view loads with navigation sidebar
   - Click different chapters in the left navigation (1. Deconstructing GraphQL, 2. GraphQL vs. REST, etc.)
   - Test interactive features like code copy buttons
   - Click "Back to Profile" to return to main view

3. **External links verification**:
   - Test email link (rishimanish123@gmail.com) opens mail client
   - Test LinkedIn link opens in new tab
   - Verify all navigation and interactive elements respond correctly

### Performance validation
- **Server startup**: ~2 seconds for Python HTTP server
- **Page load**: Instantaneous for static content 
- **Navigation**: JavaScript transitions should be smooth and immediate
- **NEVER CANCEL**: Allow at least 5 seconds for any operation to complete

## GitHub Pages Deployment

### How deployment works
- **Automatic**: GitHub Pages automatically serves the site from the repository
- **No build step**: Files are served directly as committed
- **URL**: https://manishkumr.github.io
- **Source**: Serves directly from the root of the main branch

### Making changes
- Edit `index.html` directly for content/style changes
- Test locally with `python3 -m http.server 8080`
- Commit and push to deploy to GitHub Pages
- **No deployment commands needed** - GitHub Pages handles automatically

## Common Tasks

### The following are outputs from frequently run commands. Reference them instead of viewing, searching, or running bash commands to save time.

#### Repository root contents
```bash
ls -la
total 72
drwxr-xr-x 6 runner docker  4096 Aug 14 13:01 .
drwxr-xr-x 3 runner docker  4096 Aug 14 13:01 ..
drwxr-xr-x 7 runner docker  4096 Aug 14 13:01 .git
-rw-r--r-- 1 runner docker   224 Aug 14 13:01 .project
drwxr-xr-x 2 runner docker  4096 Aug 14 13:01 images
-rw-r--r-- 1 runner docker 39922 Aug 14 13:01 index.html
drwxr-xr-x 2 runner docker  4096 Aug 14 13:01 javascripts
-rw-r--r-- 1 runner docker  1987 Aug 14 13:01 params.json
drwxr-xr-x 2 runner docker  4096 Aug 14 13:01 stylesheets
```

#### File types in repository
```bash
find . -name "*.html" -o -name "*.css" -o -name "*.js"
./javascripts/main.js
./index.html
./stylesheets/print.css
./stylesheets/github-light.css
./stylesheets/stylesheet.css
```

#### JavaScript directory contents
```bash
ls javascripts/
main.js
```

#### Stylesheets directory contents  
```bash
ls stylesheets/
github-light.css
print.css  
stylesheet.css
```

#### Git history (most recent commits)
```bash
git log --oneline -10
cc50e79 (HEAD -> copilot/fix-3, origin/copilot/fix-3) Initial plan
2befe05 (grafted) Update index.html
```

### Site content overview
- **Profile section**: Personal information, contact details, location
- **Projects section**: Placeholder project cards with GitHub links
- **Learning section**: Interactive Django & GraphQL tutorial with multiple chapters
- **Technologies**: Python/Django focus with full-stack development emphasis
- **Interactive features**: Navigation, learning modules, code copying, charts

## Important Notes

- **No Node.js/npm required** for basic operation (only for HTML validation tool)
- **No build process** - edit HTML directly
- **External dependencies via CDN** - Tailwind, Chart.js, Google Fonts
- **Single file architecture** - all code in index.html
- **Responsive design** - works on mobile and desktop
- **GitHub Pages compatible** - no server-side processing required

## Troubleshooting

### If the site doesn't load
- Check if Python HTTP server is running: `python3 -m http.server 8080`
- Verify you're accessing `http://localhost:8080` not `https://`
- Check for JavaScript console errors in browser dev tools

### If navigation doesn't work
- Verify JavaScript is enabled in browser
- Check browser console for errors
- Ensure all CDN resources are loading (may be blocked in some environments)

### If HTML validation fails
- Expected: 22 validation issues are normal and don't affect functionality
- Only fix validation issues if specifically requested for the change
- Use `html-validate index.html` to check for new issues after changes