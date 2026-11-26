# Kule — 3D Interactive Floor And Task Tracker

An interactive, single-file **3D architectural diorama and cloud-connected facility/task management application** modeling three **Kule** towers atop a procedurally generated floating island above the clouds.

> **Legal Disclaimer:** This project is created strictly as a non-commercial personal hobby, educational, and 3D WebGL/Three.js visualization experiment. It has **no affiliation, partnership, sponsorship, license, or official connection with Türkiye İş Bankası A.Ş.** or any public/private institution. Users are solely responsible for any content entered or synchronized; never enter confidential corporate data or sensitive personal information (KVKK / GDPR).

> **Live Demo:** Use the application directly in your browser with zero installation:
> [**https://egegurkan.github.io/Tower/**](https://egegurkan.github.io/Tower/)

Built inside a single `index.html` file powered by **Three.js**, every building floor, architectural detail, texture, GLSL shader, and procedural Web Audio soundscape is generated directly in code—requiring zero build tools and zero external 3D asset files, while synchronizing all tasks, notes, reminders, and release changelogs live with an online **Google Sheets / Google Drive** workbook.

---

## Key Features

### 1. Procedural 3D Architectural Model And Floating Island

- **Three Selectable Towers:**
  - **Tower 1 (Kule 1):** Ground floor (`0`) + 41 floors featuring a 4-level stone podium, glass curtain walls, upper-level setbacks (floors `36–39`), mechanical crown, rotating cooling tower fans, and a 190m rooftop flag mast.
  - **Towers 2 & 3 (Kule 2 & Kule 3):** Entrance floor (`-1`), Mezzanine (*Ara Kat*, `0`), and floors `1–27` with upper setbacks and pitched mechanical crowns.
- **Detailed Campus Architecture:** Podium blocks, central atrium glass dome, arched *Kule Çarşı* clock portal with radial glass crown, rooftop `H` helipad, enclosed pitched glass skylight, capped barrel-vault glass galleries, curved glass Auditorium entrance, sunken `-1` cafeteria courtyard, the **Kibele** marble monument with stepped waterfall, west-entry glass smoking pavilion and outdoor shelters, multi-story parking garage, two open parking lots with EV chargers and automated barrier arms, fountain roundabout, curved green wall, pond, stream, and waterfall.
- **Floating Rock Ecosystem (High Quality Mode):** Procedural underside strata with hanging roots and thin root-colored vines across the main island and orbiting satellite islets, 4 additional cliffside waterfalls emerging seamlessly from the rock, rare falling/respawning rock and soil particles, and flocking birds in High graphics mode.
- **National Holiday Giant Flags:** On Turkish national holidays, giant animated Turkish flags automatically drape down the facades of Tower 1 (*Auto / Always On / Off* in Settings).

### 2. Visual Styles, Live Istanbul Weather And Analytical Views

- **Four Render Styles (`Q` / `W` / `E` / `P`):**
  - **Normal:** Stylized architectural daylight and night lighting with dynamic reflections and glowing office windows (floors with active tasks shine brighter).
  - **Blender:** 3D viewport mode with **Material, Solid, Clay, and Wireframe** sub-modes, wireframe overlay toggle, infinite ground grid, and an interactive XYZ orientation gizmo.
  - **Cyberpunk:** Dark neon cityscape with glowing outlines, animated holographic rings and signage, wet reflections, chromatic aberration/scanline post-processing, rain, and synthwave chords.
  - **Steampunk:** Sepia film-grain post-processing, brass and copper facades, rotating interlocking facade gears, illuminated rooftop tower clocks synced to scene time, steaming chimneys, and orbiting airships.
- **Time Of Day (`1`–`4`):** Smoothly transition between **Day, Noon, Evening, Night**, a **5-Minute Auto Day/Night Cycle** (configurable), or **Real-Time** synced to the system clock.
- **Live Real-Time Istanbul Weather (`Y`):**
  - On startup, automatically queries **Istanbul's live current-hour meteorological weather** and applies it to the scene (**Clear, Rain, Snow, Fog, or Storm**), then smoothly transitions back to **Clear / Sunny** weather after **1 minute**.
  - **Snow & Ice Physics:** Roads whiten progressively with snowfall rather than turning white instantly; both the pond and the stream freeze into ice during snow.
- **Analytical View Modes (`N` / `X` / `H`):**
  - **X-Ray:** Renders tower facades translucent while highlighting individual floor slabs.
  - **Heatmap:** Color-codes every floor by **Open Task Count**, **Overdue Tasks**, or **Completion Progress (%)** with an interactive legend.

### 3. Living Campus Ecosystem, Smart Traffic And Aviation

- **Pond Regulars, Birds, Jumping Fish And Winter Skaters:** Five regulars sit on the benches around the pond tossing bread crumbs to ground-pecking birds and pond fish that leap out of the water with expanding ripples. When snow freezes the pond, they put on winter scarves/beanies to **ice-skate**, returning to their benches just before the snow clears.
- **Rooftop Helicopter Operations:** A corporate helicopter (`Pilot`) periodically approaches, lands on the podium helipad, idles its rotors, and departs. During **Fog, Rain, Snow, and Storm**, the helicopter sways gently in the wind across approach, landing, takeoff, and departure.
- **Year-Round Patrol Snowplow:** The snowplow (`Operatör`) patrols the island ring road in all seasons; when snow accumulates, it lowers its plow blade, clears a smooth asphalt wake (`3` vehicle lengths behind) with snow spray, and allows snow to gradually re-accumulate in cleaning order.
- **Counter-Flow Service Vehicles And Jam-Free Parking:**
  - **Fire Truck** (rescues cats stuck in trees with an extendable ladder) and **Police Car** (occasionally escorts an employee for a lost badge inquiry and brings them back) patrol the **inner lane**, while the **Ambulance** and **Snowplow** patrol the **outer lane in the opposite direction** with automatic anti-bunching spacing.
  - Multi-story and open parking lots prevent entrance bottlenecks and automatically **despawn stuck inner vehicles** if a queue forms.
  - In **Fog, Rain, Snow, and Storm**, all vehicles and the helicopter move **25% slower** (`0.75x`).
- **Two-Way Micro-Mobility, Zero Crushing And Lateral Sidestepping:**
  - Cyclists, skateboarders, and scooter riders travel along both inner and outer shoulders of the ring road.
  - Vehicles and pedestrians yield to one another; **Paşa**, his canine friend, and 14 campus cats flee onto the grass when wheels approach; walkers, joggers, and riders smoothly **sidestep left/right** to pass without colliding.
- **Campus Waste Bins And Cleanup Crew:** Workers dispose of food/drink items in campus recycling bins; on rare occasions when an item is forgotten on a landscape bench, a facility (`İŞMER`) staff member dispatches to collect and bin it.
- **Context-Aware Speech Bubbles:** Click any person, rider, skater, helicopter, snowplow, emergency vehicle, dog, or cat to read witty thoughts and critiques reflecting live task loads, weather, and visual style.

### 4. Online Cloud Architecture And Floor Task Management

- **100% Online Data Source (`Tower` Google Sheets):**
  - No tasks or changelogs are hardcoded inside `index.html` or stored in `localStorage` (only local UI/audio preferences and consent status are saved in the browser).
  - All floors, tasks, Markdown notes, checklists, reminders, activity logs, and release changelogs (`v0.1 – v1.3`) are read from and written to the online **Tower** Google Sheets workbook (`Info`, `Görevler`, and `Changelogs` tabs) via a Google Apps Script Web App (`JSONP`, `POST`, chunked `Base64URL`, and `gviz` fallback—compatible with both local `file://` files and HTTPS hosting).
  - **Pre-Add Cloud Refresh:** Clicking **New Task (`Yeni görev`)** automatically refreshes state from Google Drive first so concurrent updates are never overwritten.
  - **Auto-Sync Interval:** Synchronizes automatically every **5 minutes** by default (configurable from `1–120` minutes in Settings), alongside manual **Load From Drive** and **Write To Drive Now** actions.
- **Interactive Floor Drawer & Shared Spaces (`A`):** Manage tasks, pinned Markdown sticky notes (with live preview), color tags, and chronological activity timelines across all tower floors and campus spaces (*Çarşı, -1 Cafeteria, Auditorium, Open Parking/EV, -4 Garage, Landscape*). Executive floors (`36–38`) carry restricted-access badges.
- **List & Drag-And-Drop Kanban Workflows:** Track status (*To Do, In Progress, Waiting, Done*), priorities, start/due dates, tags, checklists, recurring schedules (*Daily, Weekly, Monthly, Quarterly, Yearly*), discipline categories, and workload-balanced auto-assignment.

### 5. Management Dashboard, Team Locator And Data Portability

- **Management Dashboard (`D`):** Includes five tabs—**Summary** (KPIs and charts), **Jobs (`İşler`)** (searchable, filterable list of every task with tower/floor, status, and full description), **Workload Distribution** (with one-click auto-distribution), **30-Day Agenda**, and **Team Roster**.
- **Team Member Locator & Camera Follow (`B`):** Click the target icon in the top bar (or press `B`) to locate and continuously follow a team member walking on campus; pressing again cycles to the next member, automatically orbiting around buildings so the camera never clips inside facades.
- **Reminders (`T`) & Global Search (`Ctrl + K`):** Desktop and in-app reminder cards with snooze presets (`10m`, `1h`, `Tomorrow 09:00`), audio chimes, missed-alert catch-up, and instant global search that flies the camera to any matching floor, task, note, or person.
- **Smart Upsert Import & Multi-Format Export:**
  - **JSON Export & Smart Import:** Importing overwrites matching floors/tasks/notes/reminders while preserving non-matching existing data, creating an in-session restore point automatically.
  - **CSV & Calendar (`.ics`) Exports:** Download Excel-ready task tables or export due dates and reminders to Outlook, Google Calendar, or Apple Calendar.

### 6. Procedural Dual-Channel Audio And Legal Consent Flow

- **Separate Ambiance And Music Channels (`5%` Default):**
  - Procedural **Web Audio API** ambiance (wind, birds, rain, thunder, night hum, cyberpunk synth) and winter **Music** have separate toggles and volume sliders in Settings, both enabled at **`5%`** by default.
  - Every time **Snow** weather is activated, a polyphonic Web Audio winter melody fades in, plays **1 full loop**, and fades out cleanly.
- **Instant Consent Gate & Deferred World Boot:** First-time visitors are greeted by an instant, zero-lag Legal Disclaimer & Terms of Use modal before 3D world generation starts. Accepting transitions seamlessly into the animated loading screen (with zero premature scene flash), persists across future visits (`✓ Accepted` badge in Settings), and remains accessible anytime under the 3-tab **Help (`?`)** dialog (*Terms of Use & DMCA, Shortcuts, Release Notes*).

---

## Controls And Keyboard Shortcuts

### Mouse And Touch Controls

| Input | Action |
| --- | --- |
| **Left-Click + Drag** / **1-Finger Drag** | Orbit camera |
| **Right-Click + Drag** / **2-Finger Drag** | Pan camera |
| **Scroll Wheel** / **Pinch** | Zoom in / out (scrolls horizontally when hovering a narrow top bar) |
| **Click / Tap** | Select a floor/space or open a speech bubble on people, riders, vehicles & pets |

### Keyboard Shortcuts

| Key | Action |
| --- | --- |
| `1` · `2` · `3` · `4` | Switch time of day (Day · Noon · Evening · Night) |
| `Q` · `W` · `E` · `P` | Switch visual style (Normal · Blender · Cyberpunk · Steampunk) |
| `N` · `X` · `H` | Switch view mode (Normal · X-Ray · Heatmap) |
| `Y` | Cycle weather (Clear · Rain · Snow · Fog · Storm) |
| `B` | Locate and follow a team member (press again to cycle to the next member) |
| `D` | Open Management Dashboard (Summary, Jobs, Workload, Agenda, Team) |
| `A` | Open Shared Spaces & Floor Directory |
| `T` | Open Reminders |
| `↑` / `↓` | Step up or down floors in the selected tower |
| `F` | Focus camera on the selected floor |
| `R` | Full Reset (General camera · Day · Clear/Sunny weather · Normal style & view) |
| `Ctrl + K` | Global Search across all floors, tasks, notes, and people |
| `Ctrl + Z` | Undo last change |
| `Esc` | Stop team follow, or close active dropdown, speech bubble, modal, or panel |
| `?` | Open Terms of Use (DMCA / KVKK), Shortcuts, and Online Release Notes |

---

## Running Locally And Cloud Setup

No bundlers, Node.js packages, or build steps are required.

1. Clone the repository:
   ```bash
   git clone https://github.com/EgeGurkan/Tower.git
   cd Tower
   ```
2. Open `index.html` directly in any modern WebGL2 browser (**Chrome**, **Edge**, **Firefox**, or **Safari**)—even over `file://`—or serve it locally:
   ```bash
   python -m http.server 8000
   ```
3. **Google Sheets / Apps Script Backend (`google-apps-script-changelog.gs`):**
   - Bound to the online **Tower** Google Spreadsheet containing three tabs: **`Info`** (JSON state key-value store), **`Görevler`** (structured flat task table), and **`Changelogs`** (version history).
   - Deployed as a Google Apps Script Web App with **Execute as: Me** and **Who has access: Anyone (`Herkes`)** to support seamless anonymous read/write synchronization from both local `file://` and GitHub Pages.

---

## Configuration And Customization

Core architectural, visual, and organizational parameters live in the `CONFIG` block near the top of `index.html`:

- `CONFIG.towers`: Coordinates, floor counts, slab heights, setbacks, dimensions, and facade palettes.
- `CONFIG.podium` & `CONFIG.site`: Podium geometry, helipad, skylight, galleries, courtyard, smoking pavilion, parking lots, and landscape layout.
- `CONFIG.team`: Default facility management roster, roles, groups, and discipline mappings.
- `CONFIG.floorInfo` & `CONFIG.spaces`: Default floor department names, restricted-floor flags, and campus-wide shared spaces.
- `CONFIG.holidays`: Calendar dates (`MM-DD`) that trigger the giant facade Turkish flag on Tower 1.

---

## Technical Overview

- **3D Engine & Post-Processing:** Three.js (`v0.160.0` via ES Module `importmap`), `WebGLRenderer` (`ACESFilmicToneMapping`, `PCFSoftShadowMap`), `EffectComposer` (`RenderPass`, `SSAOPass`, `OutlinePass`, `UnrealBloomPass`, `SMAAPass`, custom Cyberpunk & Steampunk GLSL passes, and `OutputPass`), plus `InstancedMesh` crowd/traffic rendering and `DataTexture` progressive road-snow shaders.
- **Audio Engine:** Zero-asset procedural **Web Audio API** synthesizer for ambient layers and polyphonic winter chimes.
- **Performance Presets:** Full-width **Low / Medium / High** quality selector (defaulting to `15s` idle auto-rotation wait and `5m` day cycle), plus individual toggles for shadows, particles, campus life, and SSAO.
- **License:** MIT License — see repository license details for educational and hobbyist reuse.
