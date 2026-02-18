# Presentation Guide

## Viewing the Presentation

The presentation is a self-contained HTML file located at `presentation/index.html`.

### How to View

**Option 1: Direct File Open**
- Navigate to the `presentation` directory
- Double-click `index.html`
- Opens in your default web browser

**Option 2: From Repository**
- Download or clone this repository
- Open `presentation/index.html` in any modern web browser

**Option 3: GitHub Pages (if enabled)**
- Access via GitHub Pages URL if configured

### Presentation Features

- **Self-contained**: No external dependencies, works offline
- **Single-slide view**: Only one slide visible at a time for focused presentation
- **Navigation controls**: Previous/Next buttons to advance through slides
- **Keyboard navigation**: Use arrow keys, spacebar, or Page Up/Down to navigate
- **Speaker Notes window**: Open notes in a separate browser window that syncs with the current slide
- **Slide counter**: Always know which slide you're on (e.g., "Slide 5 of 20")
- **Print-friendly**: Can be printed to PDF for handouts
- **Responsive**: Works on various screen sizes

### Navigation

**Button Controls:**
- **Next → button**: Advance to the next slide
- **← Previous button**: Go back to the previous slide
- **📝 Speaker Notes button**: Open speaker notes in a separate window

**Keyboard Shortcuts:**
- **Arrow Right / Arrow Down / Space / Page Down**: Next slide
- **Arrow Left / Arrow Up / Page Up**: Previous slide
- **Home**: Jump to first slide
- **End**: Jump to last slide

**Speaker Notes:**
- Click the "📝 Speaker Notes" button to open notes in a new window
- The notes window automatically updates as you navigate through slides
- Shows the current slide title and all presenter notes
- The notes window stays in sync with the main presentation window

### Presenter Tips

1. **Open in full screen** (F11) for presentation mode
2. **Open the Speaker Notes window** by clicking the "📝 Speaker Notes" button
3. **Position windows**: Place the main presentation on the projector/main screen and the speaker notes on your laptop screen
4. **Use keyboard navigation** for smooth transitions (arrow keys or spacebar)
5. **Keep the Actions tab open** in another browser tab for demos
6. **Follow the timing** in speaker notes (10 min per topic)
7. **Be ready to run workflows** manually if needed

### Customization

The presentation uses inline CSS and can be easily customized:
- Colors: Edit the gradient and color variables in the `<style>` section
- Fonts: Change the `font-family` properties
- Layout: Modify the `.slide` class properties
- Content: Edit any slide content directly in the HTML

### Content Overview

- **Title Slide**: Introduction
- **Agenda**: 5 topics + timing
- **16 Content Slides**: 
  - Introduction slide for each topic (5)
  - Simple demo slide for each topic (5)
  - Advanced demo slide for each topic (5)
  - Best Practices (1)
- **Q&A Slide**: Questions and wrap-up
- **Resources Slide**: Additional learning materials

**Total Time**: 55 minutes (50 presentation + 5 Q&A)

### Demo Integration

Each demo slide includes:
- Demo badge with number and name
- Code examples showing key concepts
- Link to workflow file in repository
- Expected results and behavior
- Presenter notes with timing and talking points

The demos are designed to be shown live from the GitHub Actions tab, with the presentation providing context and explanation.
