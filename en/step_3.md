<h2 class="c-project-heading--task">Choose your colours</h2>

### Step 1
Set up reusable colour variables so the homepage and timeline page share the same palette.

Update `default.css` so the page background, navigation bar, timeline, and captions all use the same theme values.

<div class="c-project-code">

--- code ---
---
language: css
filename: default.css
line_numbers: true
line_number_start: 1
line_highlights: 1-16
---
/* Set up colour palette and fonts using variables */
:root {
  --body-background-colour: #000000;
  --body-text-colour: #FFFFFF;
  --nav-background-colour: #333333;
  --event-background-colour: #333333;
  --nav-font-colour: #dddddd;
  --link-hover-colour: #ffc107;
  --event-background-colour: #333333;
  --event-border-colour: #cccccc;
  --slider-colour: #cccccc;
  --slider-on-colour: #2196f3;
  --nav-light-mode: #8e6363;
  --textSection-bgcol: #823d0b;
  --border-bgcol: #2c3233;
}
--- /code ---

</div>

<h2 class="c-project-heading--task">Test</h2>
### Step 2
Click **Run** and check that the page now uses your chosen colours for the navigation bar, text panel, caption labels, and dark mode background.
