# AI Agent Instructions for Lensetek CDN

## Repository Overview
This repository hosts static assets, landing pages, and learning materials for Lensetek International's academic partnerships in Indonesia. The content is served via GitHub Pages at `lensetek.github.io/lensetek-cdn/`.

## Project Structure
- **Course Materials (`Courses/`)**: Educational content following a standardized structure:
  - `{COURSE_CODE}/{WEEK_NUMBER}_{SECTION}.html` - Learning module pages
  - `{COURSE_CODE}/{WEEK_NUMBER}_{SECTION}.json` - Supporting data like rubrics
  - Example: `EXIM/4_1.html` = Week 4, Section 1 of Export-Import course

- **Landing Pages**:
  - `CONMAR/` - Content Marketing program
  - `MACOMM/` - Marketing Communications program
  - `DIGIMA-U/` - Digital Marketing materials
  - Common pattern: `index.html` with section-based layout

## Technical Patterns

### Frontend Architecture
- Uses Tailwind CSS via CDN for styling
- Standard Google Fonts integration (Inter, Poppins, Noto Sans JP)
- Vanilla JavaScript with modular components

### Common UI Patterns
```html
<!-- Standard section wrapper -->
<section class="py-12 bg-slate-50/60 border-y border-slate-200">
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
    <!-- Content -->
  </div>
</section>

<!-- Card component -->
<div class="rounded-2xl border border-slate-200 p-6 bg-white shadow-soft">
  <!-- Card content -->
</div>
```

### State Management
- Uses cookies/localStorage for user progress tracking
- Example from course modules:
```javascript
function setCookie(name, value, days=30) {
  const d = new Date();
  d.setTime(d.getTime() + (days*24*60*60*1000));
  document.cookie = `${name}=${encodeURIComponent(value)};expires=${d.toUTCString()};path=/`;
}
```

### Interactive Features
- Quiz components with scoring
- Progress tracking across modules
- Responsive navigation with mobile consideration

## Project-Specific Conventions

### Directory Structure
- Course materials: `Courses/{COURSE_CODE}/{WEEK}_{SECTION}.{ext}`
- Landing pages: `{PROGRAM_CODE}/index.html`
- AR content: `AR/{MODEL_CODE}/index.html`

### Naming Conventions
- Course codes are uppercase (e.g., EXIM, INBUS, PPM)
- Week/section numbers use underscore separator (e.g., 4_1)
- Asset files use kebab-case (e.g., hero-image.png)

## Common Tasks

### Adding New Course Module
1. Create HTML file following naming pattern: `Courses/{CODE}/{WEEK}_{SECTION}.html`
2. Copy base template with standard sections (Overview, Objectives, Tools, Steps)
3. Include Tailwind CSS and required fonts
4. Add corresponding JSON file if rubric needed

### Updating Landing Pages
1. Maintain existing section structure (Hero, Features, Curriculum, etc.)
2. Follow established component patterns for consistency
3. Keep mobile responsiveness in mind with standard breakpoints

## Key Integration Points
- GitHub Pages for content delivery
- AR.js for augmented reality features
- Google Fonts for typography
- Tailwind CSS for styling