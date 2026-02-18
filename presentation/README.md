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
- **Speaker Notes**: Each slide has presenter notes in yellow boxes
- **Print-friendly**: Can be printed to PDF for handouts
- **Responsive**: Works on various screen sizes

### Navigation

- **Scroll down** to move through slides
- **Print to PDF** (Ctrl/Cmd + P) for a handout version
- Each slide is a separate section that prints on its own page

### Presenter Tips

1. **Open in full screen** (F11) for presentation mode
2. **Keep the Actions tab open** in another window for demos
3. **Follow the timing** in speaker notes (10 min per topic)
4. **Be ready to run workflows** manually if needed

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
