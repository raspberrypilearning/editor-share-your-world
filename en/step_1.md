<h2 class="c-project-heading--task">Build the home page</h2>

Add a navigation bar and scrolling sections to turn the starter page into a Wildcats homepage.

<h2 class="c-project-heading--explainer">Follow these instructions</h2>

Replace the contents of `index.html` with this page structure.

<div class="c-project-code">

--- code ---
---
language: html
filename: index.html
line_numbers: true
line_number_start: 1
line_highlights: 6-12,16-27,29,31-35,37-41,43-59,61-69
---
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link rel="stylesheet" href="style.css" />
    <link rel="stylesheet" href="default.css" />
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Anton&family=Kdam+Thmor+Pro&family=Oswald:wght@200&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:opsz,wght,FILL,GRAD@24,400,0,0" />
    <title>Wildcats</title>
  </head>
  <body>

    <div class="grid-container">
      <nav class="navigation">
        <a href="index.html">Wildcats</a> 
        <a href="timeline.html">Timeline</a> 
        <div class="toggle-container">
          <label class="switch">
            <input type="checkbox" id="darkModeToggle" />
            <span class="slider"></span>
          </label>
          <span class="toggle-label material-symbols-outlined">light_mode</span>
        </div>
      </nav>
      
      <div class="scrolling-section">

        <div class="bball">
          <div class="caption">
            <span class="border">Wellington Wildcats</span>
          </div>
        </div>

        <div class="ball parallax">
          <div class="caption">
            <span class="border">Training</span>
          </div>
        </div>

        <div class="textSection">
          <p>
            The Wildcats want you in their next training session. We know the
            streets can be tough, but so are you, and that's what makes you
            perfect for this.
          </p>
          <p>
            A court where your skills are not just appreciated but celebrated,
            where your dedication to the game is recognised and nurtured. You're
            not just honing your skills; you're becoming a part of a family that
            stands together through thick and thin.
          </p>
          <p>
            Your journey starts here, and we can't wait to see you bring your
            spirit to the Wildcats family.
          </p>
        </div>

        <div class="score parallax">
          <div class="caption">
            <span class="border">LATEST SCORE - 23:11</span>
          </div>
        </div>
      </div>
    </div>
  </body>
  <script type="text/javascript" src="scripts.js"></script>  
</html>
--- /code ---

</div>

## Now run your code

Click **Run** and check that your page shows a navigation bar, a Wildcats title panel, a Training panel, welcoming text, and a score panel.
