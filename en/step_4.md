<h2 class="c-project-heading--task">Add interactivity</h2>

Use JavaScript to save the dark mode setting and fade in the parallax sections as they scroll into view.

<h2 class="c-project-heading--explainer">Follow these instructions</h2>

Add this code to `scripts.js`.

<div class="c-project-code">

--- code ---
---
language: javascript
filename: scripts.js
line_numbers: true
line_number_start: 1
line_highlights: 1-3,5-13,15-22,24-38
---
// COLOUR MODE
document.addEventListener("DOMContentLoaded", function () {
  const darkModeToggle = document.getElementById("darkModeToggle");

  // Check if colour mode preference is stored in local storage
  const isDarkMode = localStorage.getItem("darkMode") === "true";

  // Set initial colour mode state based on the stored preference
  document.body.classList.toggle("dark-mode", isDarkMode);
  darkModeToggle.checked = isDarkMode;

  darkModeToggle.addEventListener("change", function () {
    const isDarkMode = darkModeToggle.checked;

  // Check if colour mode is already active
  if (isDarkMode !== document.body.classList.contains("dark-mode")) {
    // Update body class and store the user's preference in local storage
    document.body.classList.toggle("dark-mode", isDarkMode);
    localStorage.setItem("darkMode", isDarkMode.toString());
  }
  });
});

// PARALLAX SCROLLING
const allParallax = document.querySelectorAll(".parallax");
const observer = new IntersectionObserver((entries) => {
  entries.forEach(
    (entry) => {
      if (entry.isIntersecting) {
        entry.target.style.opacity = 1; // Fade-in effect
        observer.unobserve(entry.target); // Stop observing once the section is visible
      }
    }
  );
},
{ threshold: 0.5}
);
allParallax.forEach((parallax) => observer.observe(parallax));
--- /code ---

</div>

## Now run your code

Click **Run**, switch dark mode on and off, then refresh the page and check that your choice stays saved and the Training and score sections fade in as you scroll.
