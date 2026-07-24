# Orbital Illumination Screen

A single-page field tool for UAP/UFO investigators. Given the time, place, and
reported sky position of a light, it computes whether sunlight could have
reached an object in Earth orbit along that line of sight, and what class of
instrument would have been able to see it.

**Live tool:** https://USERNAME.github.io/REPO/

## What it screens

One hypothesis: satellite or orbital debris illumination. A negative result is
strong — it eliminates satellites and debris on physical grounds. A positive
result eliminates nothing; it means the hypothesis survives and still needs a
pass prediction, a motion check, and a brightness check.

**This tool never identifies an object.**

## Method

- Solar position via the NOAA general solar position algorithm (no refraction
  correction).
- Earth's shadow modelled as a cylinder, radius 6371 km, with an 80 km
  allowance for the opaque atmosphere.
- The shadow ceiling has two branches. Above the Sun's depression angle the
  line of sight leaves the shadow on the near side. Below it, the sightline
  crosses the shadow axis and exits the far side at a much greater distance,
  never closer than R·(csc β/2 − 1). Directions below the depression angle are
  demanding, not impossible; the tool solves both branches and reports which
  one applies.
- Brightness figures are order-of-magnitude estimates. They depend on object
  size, shape, coating, and phase angle. Treat them as guidance, not
  measurement.

Verify any surviving hypothesis against real orbital elements dated within a
few days of the sighting: heavens-above.com, celestrak.org, n2yo.com.

## Running it

No build step, no dependencies, no backend, no data collection. Open
`index.html` in any browser, or serve it as a static file. It works offline
from local disk; only the web font requires a network connection, and there is
a fallback stack.

## Deploying

Repository must be public for free GitHub Pages hosting. Settings → Pages →
Build and deployment → Deploy from a branch → `main` → `/ (root)` → Save.

## Licence

Add your preferred licence here.
