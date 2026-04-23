<h2 class="c-project-heading--task">Build a timeline page</h2>

Create a second page where visitors can add and save memorable Wildcats events on a timeline.

<h2 class="c-project-heading--explainer">Follow these instructions</h2>

Create two new files for the timeline page.

**Code snippet 1: Add the new page structure in `timeline.html`.**

<div class="c-project-code">

--- code ---
---
language: html
filename: timeline.html
line_numbers: true
line_number_start: 1
line_highlights: 1-28,30-45
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
    <div class="content">
      <h1>Keep your favourite Wildcats moments!</h1>

      <section id="timeline">
        <div id="line"></div>
        <div id="nodes"></div>
      </section>
      <section class="entry">
        <label for="year-input">Year:</label>
        <input type="number" id="year-input" required />
        <label for="event-input">Event:</label>
        <input type="text" id="event-input" required />
        <button id="add-event-btn">Add Event</button>
      </section>
    </div>
  </body>
  <script type="text/javascript" src="scripts.js"></script>
  <script type="text/javascript" src="timeline.js"></script>
</html>
--- /code ---

</div>

**Code snippet 2: Add the timeline logic in `timeline.js`.**

<div class="c-project-code">

--- code ---
---
language: javascript
filename: timeline.js
line_numbers: true
line_number_start: 1
line_highlights: 1-2,4-9,11-26,28-46,48-56,58-68,70-76,78-91
---
// TIMELINE
const currentDate = new Date();

document.addEventListener("DOMContentLoaded", function () {
  const nodesContainer = document.getElementById("nodes");
  const addButton = document.getElementById("add-event-btn");
  const inputYear = document.getElementById("year-input");
  const inputEvent = document.getElementById("event-input");
  var historicalEvents = [];

  function loadEventsFromLocalStorage() {
    const storedEvents = localStorage.getItem("historicalEvents");
    if (storedEvents) {
      historicalEvents = JSON.parse(storedEvents);
      renderTimelineEvents();
    } else {
      // Initial events
        historicalEvents = [
          { year: 1977, event: "Wildcats formed" },
          { year: 1980, event: "Joined National League" },
          { year: 1996, event: "Won Championship trophy" },
          { year: currentDate.getFullYear(), event: "Now" },
        ];
        renderTimelineEvents();
    }
  } 

  // Function to put events on the timeline
  function renderTimelineEvents() {
    nodesContainer.innerHTML = "";
    const minYear = historicalEvents[0].year;
    const maxYear = historicalEvents[historicalEvents.length - 1].year;
    const totalYears = maxYear - minYear;

    historicalEvents.forEach((event) => {
      const node = document.createElement("div");
      node.classList.add("event");

      // Calculate the percentage width based on the time difference
      let percentageWidth = ((event.year - minYear) / totalYears) * 100;
      console.log(percentageWidth);
      node.style.left = percentageWidth + "%";
      node.innerHTML = `<span class="year">${event.year}</span><span class="event-description">${event.event}</span>`;
      nodesContainer.appendChild(node);
    });
  }

  // Function to add a new event
  function addNewEvent(year, event) {
    const newEvent = { year: parseInt(year), event: event };
    historicalEvents.push(newEvent);
    historicalEvents.sort((a, b) => a.year - b.year); // Sort events chronologically
    renderTimelineEvents();
    localStorage.setItem("historicalEvents", JSON.stringify(historicalEvents));

  }

  // Add initial events when the page loads
  loadEventsFromLocalStorage(); 

  // Mouse rollover
  nodesContainer.addEventListener("mouseover", function (event) {
    const targetNode = event.target.closest(".event");
    if (targetNode) {
      const description = targetNode.querySelector(".event-description");
      description.style.display = "block";
    }
  });

  nodesContainer.addEventListener("mouseout", function (event) {
    const targetNode = event.target.closest(".event");
    if (targetNode) {
      const description = targetNode.querySelector(".event-description");
      description.style.display = "none";
    }
  });

  // Add event listener for adding a new event
  addButton.addEventListener("click", function () {
    const yearInputValue = inputYear.value;
    const eventInputValue = inputEvent.value;

    if (yearInputValue && eventInputValue) {
      addNewEvent(yearInputValue, eventInputValue);
      inputYear.value = "";
      inputEvent.value = "";
    } else {
      alert("Please fill in both the year and event fields.");
    }
  });
});
--- /code ---

</div>

## Now run your code

Click **Run**, open the **Timeline** page, add a year and event, and check that a new marker appears on the line and is still there after you refresh the page.

Confirm the observable result.
