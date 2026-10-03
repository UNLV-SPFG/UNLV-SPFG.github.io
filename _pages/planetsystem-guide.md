---
layout: single
title: "PlanetSystem User Guide"
permalink: /planetsystem/guide/
author_profile: false
excerpt: "How to build planetary systems, run simulations, and use PlanetSystem's camera controls."
toc: true
toc_sticky: true
toc_label: "In this guide"
header:
  overlay_color: false
---
[Open PlanetSystem]({{ '/planetsystem/' | relative_url }}) · [Download the PDF guide]({{ '/planetsystem/USER_GUIDE.pdf' | relative_url }})

An interactive 3D sandbox for building planetary systems and watching them evolve under gravity,
aimed at newcomers to planetary dynamics.

## Units and conventions

| Quantity | Unit |
|---|---|
| Length | AU |
| Time | years |
| Mass | solar masses (the UI also offers Jupiter and Earth masses) |
| Angles | degrees in the UI |

Orbital elements follow the [Rebound](https://rebound.readthedocs.io) convention:
`a` semi-major axis, `e` eccentricity, `inc` inclination, `Ω` longitude of the ascending node,
`ω` argument of pericenter and `f` true anomaly (or `M` mean anomaly). The reference plane is the
horizontal grid; inclination is measured from it.

## Building a system

1. **Add star** — the first body is always massive and is placed at the origin.
2. **Add body** — every further body is defined by its orbital elements relative to a *primary*.
   Massive bodies always orbit the center of mass of the other massive bodies. Test particles can use
   that center of mass, for circumbinary orbits, or one specific massive body, for example a planet
   around one star of a binary. A grey ghost previews the body and its orbit while you adjust the sliders.
3. After each addition the whole system is shifted so that the barycenter sits at the origin,
   exactly like Rebound's `move_to_com()`.

Two kinds of bodies exist:

- **Massive** bodies (stars, giant planets) attract everything.
- **Massless test particles** feel gravity but exert none.

There is no limit on the number of bodies. Past 10 massive bodies or 20 test particles a one-time
performance warning appears. High speeds may then hit the CPU limit and run slower than requested,
but the results stay correct. Large systems are integrated on all CPU cores automatically.

## Editing

Click a body in the 3D view or in the left-hand list to select it. The right-hand panel shows its
current osculating elements; every change is applied immediately and the system is re-centered.
`Delete` removes the body; bodies that used it as primary fall back to the center of mass.

The coloured ellipse around each body is its **osculating orbit**: the Keplerian orbit it would follow
if only its primary acted on it. Massive bodies are drawn on their **barycentric** orbits, so a binary
shows two ellipses around the barycenter. The panel still edits the relative elements, for example
a, e, ... of one star with respect to the other, and reports the barycentric semi-major axis for reference.
A test particle with a specific primary is drawn around that body. During integration these ellipses
precess and tilt under perturbations, which is the main thing the demo is meant to show.

## Running the simulation

The top bar controls the time evolution:

| Control | What it does |
|---|---|
| **Integrator** | Numerical method, chosen before starting (locked while running). |
| **Speed** | Simulated years per real second, from 0.01 to 1000. Default 1 yr/s. Can be changed while running. |
| **Start / Stop** | Starts or pauses the integration. |
| **Reset** | Restores the system to its initial conditions and sets t = 0. |
| **t = …** | Simulated time since the initial conditions. |
| **Save** | Stores the current system as a named case (see below). |
| **Examples ▾** | Opens the list of preset and saved cases to load or delete. |
| **Clear all** | Start from scratch. |

The demo renders at a fixed 60 frames per second, so each frame advances the system by speed / 60 years.

### Integrators

All three integrate the full N-body problem: massive bodies attract each other, test particles feel
every massive body but exert no force. They are listed from cheapest to most expensive.

| Integrator | Order | Step | Force evaluations per step | Best for |
|---|---|---|---|---|
| Leapfrog | 2 | fixed | 1 | Fast, long runs; energy error stays bounded but orbital phases drift slowly. |
| Yoshida | 4 | fixed | 3 | Long runs that need accurate phases (resonances, precession). |
| Dormand-Prince 5(4) | 5 | adaptive | 6 | Close encounters, very eccentric orbits, scattering; not symplectic, so energy drifts slowly. |

The fixed step is chosen automatically as a small fraction of the shortest dynamical timescale in the
system, evaluated at pericenter: 3 % for Leapfrog and 6 % for Yoshida. It is adjusted so each frame
contains a whole number of equal steps. If an orbit tightens a lot during the run, for example through
Kozai-Lidov eccentricity growth, the step shrinks automatically. The adaptive integrator uses a relative
tolerance of 1e-10 per step. All of these values can be changed in the `SimulationSettings` asset.

### Status bar

The bottom bar shows the current step size, the relative energy error of the massive bodies since the
initial conditions, the number of steps per frame and the achieved speed. Integration gets at most
8 ms of CPU time per frame. When a high speed needs more than that, the simulation runs slower than
requested and the status bar says so.

Integration stops automatically when two bodies touch (their physical radii overlap). Use **Reset**
to go back to the initial conditions.

### Editing and running

Bodies cannot be added, edited or deleted while the integration runs. Selecting a body while it runs
shows its **live osculating elements**, which is a good way to watch inclination or eccentricity
oscillate. After stopping, editing a body's orbit or mass defines new initial conditions and resets
t to 0. Renaming a body or changing its colour or radius does not.

## Examples and saved cases

**Examples ▾** lists the built-in presets first, then your saved cases. Click a row to see its
description, then **Load** it or **Delete** it. Presets cannot be deleted. Loading replaces the current
system, and you are asked first if it has unsaved changes. A loaded case becomes the new initial
conditions (t = 0). It may also set the speed, and a saved case also restores its integrator.

| Preset | Contents |
|---|---|
| Solar System | The Sun and the eight planets at J2000 (JPL approximate elements), all massive, with real masses and radii, plus a massless Halley-like comet (e = 0.967, retrograde). Speed 1 yr/s. |
| Kozai–Lidov | A circular equal-mass binary (0.5 + 0.5 M☉, a = 1 AU, defined around the barycenter) and a massless particle on a circular orbit at 0.1 AU around Star A, inclined 60° to the binary plane. The particle's eccentricity grows to about 0.76 while its inclination falls to about 40°, then both cycle back, roughly every 63 yr. Uses Dormand-Prince at 10 yr/s. |
| Polar Planets | An equal-mass eccentric binary (0.5 + 0.5 M☉, a = 1 AU, e = 0.8), a Jupiter-mass planet at 5 AU and a massless planet at 10 AU. Both planets are on circular polar orbits (inc = 90°, Ω = 90°) aligned with the binary's eccentricity vector. Loaded at startup. |

**Save** works like a game save. It stores the exact positions, velocities, masses, radii and colours
of all bodies, plus the integrator and speed. Saving after a run stores the evolved state. You are asked
for a name, "Case 1" by default. An existing name can be overwritten, but preset names are reserved.
Save and Examples are disabled while the integration runs.

Saved cases are kept in `saved_cases.json` in the app's data folder. On macOS that is
`~/Library/Application Support/<Company Name>/PlanetSystem/`. It is plain JSON, so cases can be
backed up, shared or written by hand. A body may give `"elements": {"a", "e", "inc", "Omega",
"omega", "f"}`, with angles in degrees, instead of a position and velocity.

## Camera and keyboard

The app has three interaction modes: edit, free-fly and focus. **Tab** cycles through them in that
order and **Esc** always returns to edit mode.
Switching mode keeps the current camera position. The active mode, view and keys are shown at the
bottom left of the screen.

### On-screen buttons (phones and tablets)

Everything that needs a key also has a button, so the web build works on touch screens. The bottom-left
pad holds the three modes and the six preset views, with the active ones highlighted. Each button and
toolbar control shows its key, for example **Start (F5)**, and the first four rows of the body list
show F1-F4. On a touch screen, tap a body to select it and drag with one finger to look around in
free-fly. Free-fly movement (WASD/QE) and scroll zoom still need a keyboard and mouse.

### Shortcuts that work in every mode

| Key | Action |
|---|---|
| F1-F4 | Select body 1-4 (in list order) |
| F5 | Start / stop integration |
| F6 / F7 | Slower / faster |
| F | Focus mode |
| Tab | Next mode |
| Esc | Back to edit mode |

On a Mac keyboard the F keys control brightness and volume by default. Hold **fn**, or enable
"Use F1, F2, etc. keys as standard function keys" in System Settings > Keyboard.
Shortcuts are ignored while you are typing in a text field.

### Preset views (keys 1-6, both modes)

| Key | View |
|---|---|
| 1 | Oblique view from above the reference plane (startup view) |
| 2 | Top view, looking down the z axis (x right, y up) |
| 3 | Side view along the x axis (y right, z up) |
| 4 | Side view along the y axis (x right, z up) |
| 5 | Tracks the primary star: line of sight in its orbital plane, perpendicular to its eccentricity vector |
| 6 | Tracks the primary star: line of sight along its eccentricity vector |

The camera glides to the chosen view and keeps the whole system in frame. Views 5 and 6 follow the
orbit of the first massive body in the list, looking down on its orbital plane from 45 degrees with the
orbit normal pointing up on screen. For a binary this means the camera co-rotates with the binary's
orbital plane and apsidal line. You can then watch how an outer planet's orbit tilts and precesses
*relative to the binary*. If the primary is on a near-circular orbit the node line replaces the
eccentricity vector. If it has no orbit, as for a single star, the reference frame is used instead.

Returning from free-fly leaves the camera where it was until you press 1-6.
In free-fly, 1-6 glide the camera to a snapshot of that view, which then becomes the new starting
point for flying. Views 5 and 6 do not keep tracking in free-fly. Any movement or look input cancels
the glide.
Click a body, or a row in the list, to select it.

### Free-fly mode

The camera behaves like a drone.

| Input | Action |
|---|---|
| Drag (mouse or one-finger trackpad press-and-drag) | Look around |
| W / S | Forward / back along the view direction |
| A / D | Left / right |
| Q / E | Down / up |
| Scroll wheel or two-finger trackpad scroll | Dolly forward / back (a burst of W / S) |
| Shift | Move faster |
| 1-6 | Reset the camera to a preset view and keep flying from there |

Movement speed is set from the size of the system when you enter free-fly. Moving closer does not
change the movement or look sensitivity. A click without dragging still selects bodies.

### Focus mode

Focus mode follows one massive body with the camera. The camera moves with the body but never
rotates, so orbits *around* that body stay still on screen however fast the body itself moves. For
example, a planet around one star of a fast binary shows its eccentricity and inclination evolving
in place instead of smearing around the barycenter.

- **Entering**: press **F**, or Tab to it. The camera focuses on the selected body if it is massive,
  otherwise on the first massive body. The current view direction is kept.
- **Changing the target**: click, or press F1-F4 on, another massive body, and the camera glides to it.
  Clicking a test particle opens its details as usual. To edit a massive body, return to edit mode with Esc.
- **View direction**: 1-6 set the direction only, and the focused body stays centred. Views 5 and 6
  still align with the primary's orbital plane, which shows a planet's tilt relative to the binary.
- **Zoom**: the frame fits the test particles that orbit the focused body. Without any, it fits the
  scale of the body's own orbit. Scroll to zoom in or out.
- **Grid**: the reference grid moves with the focused body, so it stays still on screen.
- **Orbits shown**: only the orbits of test particles that use the focused body as primary. The other
  ellipses are hidden, because they would sweep across the moving frame. Bodies and labels stay visible.

Bodies that are not focused may still flicker at high speeds, because they move a long way between frames.

## Notes

- Rendered body sizes are exaggerated logarithmically so planets stay visible at AU scales. Bodies
  are also never drawn smaller than a few pixels, so they remain visible when zoomed far out.
- The preset views auto-frame the bound orbits. Bodies that become unbound lose their ellipse and
  may leave the view.
