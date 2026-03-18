<h2 class="c-project-heading--task">Choose your colours</h2>
--- task ---
Set up reusable colour variables so the homepage can use the same palette everywhere.
--- /task ---

Update `default.css` so the page background, navigation bar, timeline, and captions all share the same theme values.

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
--- task ---
Click **Run** and confirm the page still loads, then hover over the navigation links to check that they have a different hover colour once you style them in the next step.
--- /task ---
