# ModernAgile.org Website

## Quick Start

### New Contributors (First Time)
```bash
# One-command setup for new contributors
./onboard
```
This interactive script will check your system, set up everything needed, and optionally start the development server.

### Returning Contributors
```bash
# Start development server
./run

# Run tests
./run_tests

# Reset to clean state (clean untracked files, pull latest, update deps, test)
./clean_start
```

**💡 Tip:** Run `./clean_start` before beginning each new feature to ensure you're working with the latest code and clean dependencies.

## Development Server

The project includes a custom Node.js development server that:
- Serves all static files with proper MIME types
- Automatically opens your browser
- Provides real-time request logging  
- Enables CORS for development
- Handles all project file types (HTML, CSS, JS, images, fonts, etc.)

### Alternative Server Options
If you prefer other web servers:
- **Node.js http-server**: `npx http-server . -p 8080 -o --cors`
- **Python 3**: `python -m http.server 8000` (basic, no auto-reload)
- **Other**: Any static web server of your choice

## Testing

The project uses QUnit + Grunt + PhantomJS for testing. The test suite includes:
- **18 total test assertions** (all passing ✅)
- **Tests for FancyList component** (pagination, rendering, controls)
- **Async pagination testing** with proper handling of UI animation delays
- **Current status**: All tests passing and maintained

### Running Tests

Run the full test suite:
```bash
./run_tests
```

**Expected output:** All 18 assertions should pass. You may see a harmless warning about `http_parser` module - this doesn't affect test functionality.

### Manual Testing
View tests in browser: `http://localhost:8080/tests/FancyList-tests.html` (when development server is running)

### Test Coverage
- ✅ **FancyList rendering** - Component initialization and DOM structure
- ✅ **Pagination controls** - Button creation and state management  
- ✅ **Navigation functionality** - Next/previous buttons and page number clicks
- ✅ **Async behavior** - Proper handling of 500ms animation delays
- ✅ **Edge cases** - Disabled states on first/last pages

## MA Wheel Translations
See the [Template Engine](git@github.com:modernagile/template-engine.git) project to create a new media kit for each translation.  Instructions are in its README.md file.


## CD pipeline

We don't know how this works currently. Someone set it up, so when you push main code line here it will go live in some few minutes.

## Maintenance

Check out the data/ subdirectory. In there are entries for the cheatsheet and the learn more section. If you edit those data files and deploy, the pages will reflect the additional entries automagically. 

learn more: `data/learnMoreEntries.js`

cheatsheets: `data/cheatSheetEntries.js`

upcoming events: `upcomingEventsEntries.js`

Anything other changes will most likely require editing the `index.html`, and possibly the `./js/*` and/or `./css/* files`.

