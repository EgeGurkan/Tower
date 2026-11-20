# 3D Interactive Floor \& Task Tracker

An interactive, single-file **3D architectural diorama and facility/task management application** modeling Istanbul's iconic **Towers** atop a procedurally generated floating island above the clouds.

> **Live Demo:** You can try the application directly in your browser without any installation at [**https://egegurkan.github.io/Tower/**](https://egegurkan.github.io/Tower/).

Built entirely inside a single `index.html` file with **Three.js**, every building floor, landscape element, texture, shader effect, and ambient soundscape is procedurally generated in code—requiring zero build steps and zero external 3D asset files.

## Key Features

### 1. Procedural 3D Architectural Model

- **Three Selectable Towers:**
    - **Tower 1 (Kule 1):** Ground floor (`0`) + 41 floors, featuring a 4-level stone podium, glass curtain walls, upper-level setbacks (floors 36–39), technical crown, cooling tower fans, and a 190m rooftop flag mast.
    - **Towers 2 \& 3 (Kule 2 \& Kule 3):** Ground floor, Mezzanine (*Ara Kat*), and floors `1–27` with upper setbacks and pitched mechanical crowns.
- **Detailed Campus \& Floating Island:** Podium blocks, atrium dome, arched *Kule Çarşı* clock entrance, rooftop helipad, barrel-vault glass galleries, curved Auditorium entrance, sunken `-1` cafeteria courtyard with dining tables, the **Kibele** marble sculpture with a stepped waterfall, covered glass smoking pavilion, multi-story parking garage, open parking lots with EV chargers and animated barrier arms, fountain roundabout, curved green wall, pond, stream, cascading waterfall, and floating satellite rock islets.
- **National Holiday Giant Flags:** On Turkish national holidays and **August 26** (Türkiye İş Bankası's founding anniversary), giant animated Turkish flags automatically drape down the facades of Tower 1 (configurable as *Auto / Always On / Off* in Settings).

### 2. Visual Styles, Time \& Weather

- **Four Render Styles (`Q`** **/** **`W`** **/** **`E`** **/** **`P`):**
    - **Normal:** Stylized architectural daylight and night lighting with dynamic glass reflections and glowing office windows (floors with active tasks illuminate brighter).
    - **Blender:** 3D viewport mode with **Material, Solid, Clay, and Wireframe** sub-modes, wireframe overlay toggle, infinite floor grid, and an interactive XYZ orientation gizmo.
    - **Cyberpunk:** Dark neon cityscape with glowing architectural outlines, animated holographic rings \& *Neo-Levent* signage, wet reflections, chromatic aberration/scanline post-processing, rain, and procedural synthwave audio.
    - **Steampunk:** Sepia film-grain post-processing, brass and copper facades, interlocking rotating facade gears, illuminated rooftop tower clocks synced to scene time, steaming copper chimneys, and orbiting airships.
- **Time of Day (`1`–`4`):** Smoothly transition between **Day, Noon, Evening, Night**, an **Auto Day/Night Cycle**, or **Real-Time** synced to your system clock.
- **Dynamic Weather (`Y`):** Switch between **Clear, Rain** (wet surfaces and pedestrians opening umbrellas), **Snow** (gradual snow accumulation on upward-facing geometry), **Fog**, and **Storm** (lightning flashes with delayed procedural thunder).
- **Analytical View Modes (`N`** **/** **`X`** **/** **`H`):**
    - **X-Ray:** Makes tower exteriors translucent while highlighting floor slabs.
    - **Heatmap:** Color-codes every floor by **Open Task Count**, **Overdue Tasks**, or **Completion Progress (%)**, complete with an on-screen legend.

### 3. Living Diorama ("Yaşam")

- **Autonomous Campus Life:** Office workers navigate walkways using a visibility-graph pathfinder, sit on landscaped benches and courtyard dining tables, take breaks in designated smoking zones, and jog around the island ring road.
- **Traffic \& Emergency Events:** Cars depart and park across the open lots and parking garage with automated gate barriers. Emergency vehicles patrol the ring road—including a **Fire Truck** that deploys an extendable ladder to rescue cats stuck in trees, an **Ambulance**, and a **Police Car** that occasionally escorts an employee away and brings them back.
- **Campus Pets:** Features **Paşa** (the island's resident dog), his canine friend, and 14 named campus cats roaming the grounds.
- **Interactive Speech Bubbles:** Click any pedestrian, driver, emergency vehicle, dog, or cat to read humorous, context-aware thoughts and office critiques—including live references to your actual overdue tasks, busiest floors, team workloads, current weather, and active visual style.

### 4. Floor \& Facility Task Tracking

- **Interactive Floor Panel:** Hover to highlight and pop out any floor; click to open its detail drawer. Edit floor name, department owner, description, and color tag (displayed as glowing indicators on the building facade).
- **Shared Spaces Directory (`A`):** Manage tasks, notes, and reminders not only for tower floors, but also for campus-wide areas (*Çarşı, -1 Cafeteria, Auditorium, Open Parking/EV, -4 Garage, Landscape*). Restricted executive floors (`36–38`) are marked accordingly.
- **Full Task Management:**
    - Switch between **List** and drag-and-drop **Kanban** views (*To Do, In Progress, Waiting, Done*).
    - Priority levels, start/due dates, overdue \& due-today visual highlights, tags, checklists with progress bars, and task Move/Copy between floors.
    - **Disciplines \& Auto-Assignment:** Categorize tasks by discipline (*Architecture, Civil, Electrical, Mechanical, Maintenance, Management, Security, Cleaning, IT*) and automatically assign them to the team member with the lowest weighted workload.
    - **Recurring Tasks:** Configure daily, weekly, monthly, quarterly, or yearly intervals—completing a task automatically generates the next occurrence.
- **Markdown Sticky Notes:** Color-coded, pinnable, searchable notes with a split-screen live Markdown preview.
- **Activity Timeline:** Per-floor chronological log of all edits, status changes, and moves.

### 5. Management Dashboard, Reminders \& Data Portability

- **Management Dashboard (`D`):** View executive KPIs, open tasks by discipline/tower, a team workload distribution table, one-click auto-distribution of unassigned tasks, a 30-day agenda, and an editable team roster.
- **Reminders (`T`):** Attach reminders to tasks or create standalone alerts. Fires in-app notification cards with snooze controls, audio chimes, optional Browser Desktop Notifications, and catches up on missed reminders on page load.
- **Global Search (`Ctrl + K`):** Instant keyboard-navigable search across all floors, shared spaces, tasks, notes, and assignees, flying the camera straight to the selected result.
- **Persistence, Undo \& Export:**
    - Automatically saves to browser `localStorage` with multi-step Undo (`Ctrl + Z`).
    - **JSON Export / Import:** Full backup including tasks, notes, activity, reminders, team, settings, and camera position. Importing provides a validation preview, *Overwrite* or *Merge* options, and automatic pre-import backup with one-click restore.
    - **CSV Export:** Excel-ready spreadsheet export of all tasks.
    - **Calendar Export (`.ics`):** Export due dates, recurring rules, and reminders to Outlook, Apple Calendar, or Google Calendar.

## Controls \& Keyboard Shortcuts

### Mouse \& Touch

| Input | Action |
| --- | --- |
| **Left-click + Drag** / **1-finger drag** | Orbit camera |
| **Right-click + Drag** / **2-finger drag** | Pan camera |
| **Scroll Wheel** / **Pinch** | Zoom in / out |
| **Click / Tap** | Select floor or open speech bubble on people, cars \& pets |

### Keyboard Shortcuts

| Key | Action |
| --- | --- |
| `1` `2` `3` `4` | Switch time of day (Day / Noon / Evening / Night) |
| `Q` `W` `E` `P` | Switch visual style (Normal / Blender / Cyberpunk / Steampunk) |
| `N` `X` `H` | Switch view mode (Normal / X-Ray / Heatmap) |
| `Y` | Cycle weather (Clear / Rain / Snow / Fog / Storm) |
| `↑` / `↓` | Move up or down floors in the selected tower |
| `F` | Focus camera on the selected floor |
| `R` | Reset camera to the default overview |
| `D` | Open Management Dashboard |
| `A` | Open Shared Spaces \& Floor Directory |
| `T` | Open Reminders |
| `Ctrl + K` | Global Search |
| `Ctrl + Z` | Undo last data change |
| `Esc` | Close active modal, panel, or speech bubble |
| `?` | Open Help \& Shortcuts overlay |

## Running Locally

No build tools, bundlers, or package installations are required.

1. Clone or download this repository:\
   git clone https://github.com/egegurkan/Tower.git\
   cd Tower\
2. Open `index.html` in a modern WebGL-capable browser (**Chrome**, **Edge**, or **Firefox**), or serve it via any static server:\
   npx serve .\
   \# or\
   python -m http.server 8000\

> **Note:** An active internet connection is only needed to load **Three.js (v0.160.0)** and the **Inter** font from CDN. All 3D geometry, textures, shaders, and Web Audio soundscapes are generated locally in the browser.

## Customization

All core architectural and organizational parameters are centralized in the `CONFIG` object inside `index.html`:

- `CONFIG.towers`: Tower coordinates, floor counts, base heights, height overrides, setbacks, facade dimensions, and color palettes.
- `CONFIG.podium` \& `CONFIG.site`: Podium blocks, canopies, courtyard, smoking zones, parking lots, and landscaping layout.
- `CONFIG.team`: Default facility management team roster and discipline mappings.
- `CONFIG.floorInfo` \& `CONFIG.spaces`: Predefined floor functions, restricted access flags, and shared campus spaces.
- `CONFIG.holidays`: Dates (`MM-DD`) when the giant facade Turkish flag is automatically displayed.

## Technical Overview

- **Rendering:** Three.js (`WebGLRenderer`, `ACESFilmicToneMapping`, `PMREMGenerator`, `EffectComposer` with `SSAOPass`, `OutlinePass`, `UnrealBloomPass`, `SMAAPass`, and custom GLSL shaders).
- **Audio:** Zero-asset procedural ambient audio engine built on the **Web Audio API** (wind, birds, rain, thunder, city hum, and synthwave chords).
- **Performance Controls:** Built-in **Low / Medium / High** quality presets plus toggles for shadows, particles, campus life, SSAO, and idle auto-rotation.
- **Storage:** Client-side `localStorage` (`isKuleleri.data.v2`) with an automatic safety backup slot (`isKuleleri.backup.v2`).
