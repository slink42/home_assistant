# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## High-Level Code Architecture and Structure

This project is a client-side web application for a Home Assistant (HA) dashboard, primarily built with HTML, inline CSS, and JavaScript. It does not have a backend component within this repository.

- **Core Functionality:** The main logic resides in `climate_cast.html`, which communicates with a Home Assistant instance to fetch entity states (`haGetStates`) and control services (`haCall`).
- **Configuration:** `climate_cast_config.js` is used for managing Home Assistant token and configuration.
- **Data Visualization:** Chart.js (included via CDN) is used for rendering historical sensor data in popup charts.
- **UI Updates:** Functions like `updateClock`, `setMode`, `toggleZone`, `adjustZoneSetpoint`, `applyPreset`, `applyZoneUI`, and `applyControllerUI` handle user interface interactions and updates.
- **Sensor and Zone Management:** `ENTITIES`, `SENSOR_CONFIG`, `SENSOR_ENTITY_MAP`, and `SENSOR_ZONE_MAP` define the structure for sensors and zones.
- **Historical Data:** `fetchHistory`, `fetchZoneHistory`, `buildSetpointSeries`, `computeAndRenderStats`, and `openChart` are responsible for fetching and displaying historical data.
- **Real-time Updates:** The `loadState` function ensures the UI reflects current sensor data, weather, and rate of change.
- **User Feedback:** `showToast` provides transient messages to the user.

## Common Development Tasks

### Build
There is no explicit build process. The project consists of static HTML and JavaScript files.

### Lint / Test
No linting or testing configurations/frameworks are currently in place.

### Run
To run the dashboard locally:
1.  Ensure you have a running Home Assistant instance.
2.  Generate a Long-Lived Access Token from your Home Assistant profile.
3.  Open any of the HTML dashboard files (e.g., `climate_cast.html`, `climate_dashboard.html`, `living_room_dashboard.html`, `lounge_dashboard.html`) in a web browser.
4.  When prompted by the dashboard overlay, enter your Home Assistant token.