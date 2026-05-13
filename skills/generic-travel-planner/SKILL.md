---
name: generic-travel-planner
description: Build reusable, city-agnostic travel plans with day-by-day routes, lodging-based adjustments, interactive maps, route variants, restaurant/phone/link markers, practical risk notes, and shareable HTML artifacts. Use when Codex is asked to plan or revise a trip for any city or region, especially when the user wants maps, versions, self-driving/public-transit logistics, food options, booking prep, or a GitHub/shareable deliverable.
---

# Generic Travel Planner

## Core Workflow

1. Capture constraints before building:
   - dates, origin, destination city/region, transport mode, travelers, must-see places, optional places, lodging, budget, food preferences, and tolerance for early starts/long drives.
   - If lodging is unknown, plan around a likely base area and mark it as provisional.
   - If lodging later changes, keep city-core sightseeing stable when possible and re-route start/end, parking, meals, and daily timing.

2. Verify current information when it can change:
   - Search current official or high-confidence sources for opening hours, holiday notices, ticket/appointment rules, weather, traffic restrictions, parking, and restaurant phone/link details.
   - Prefer official scenic-area/government pages for access rules; use booking/restaurant platforms for restaurants, phone numbers, and links.
   - Mark uncertain coordinates or unverifiable restaurant records as approximate; remove or replace them if the user supplies authoritative links.

3. Design the route as a practical itinerary, not a point list:
   - Separate travel corridors, city-core walking, day trips, and return routes.
   - Group attractions by direction and route cost.
   - Protect high-risk scarce-ticket attractions by scheduling them first in the day.
   - Include fallback rules: “if late,” “if tickets sold out,” “if parking full,” and “if tired.”

4. Maintain versions when plans branch:
   - Use version labels such as `v1 original`, `v2 add optional attraction`, `v3 lodging-adjusted`.
   - Keep earlier versions available if the user wants to compare.
   - Switch text, map layers, route lines, and version-specific markers together.

5. Add food as operational stops:
   - Classify restaurants by meal and scenario: quick meal, proper sit-down meal, local specialty, fallback, near lodging, near attraction.
   - Store phone, address, link, recommended use, and holiday cautions in marker popups.
   - Do not invent restaurants. If a source is weak, label it weak or omit it. Prefer user-supplied Meituan/Dianping/Amap links when available.

6. Deliver a shareable artifact:
   - Prefer a single local HTML map when the user wants to show others.
   - Include a left-side route book and right-side map.
   - Use version dropdowns for alternative plans.
   - Use marker categories for base/lodging, route waypoints, attractions, restaurants, parking, and risks.

## Interactive Map Pattern

Use `assets/interactive-map-template.html` as a starting point when creating a standalone map artifact.

Minimum expected map features:
- route-version dropdown;
- day-by-day route summary;
- route polylines with intermediate waypoints instead of straight “flyover” lines;
- permanent labels that appear at useful zoom levels;
- clickable popups for restaurants and practical notes;
- clearly marked assumptions and approximations.

## Planning Heuristics

- Self-driving plans must include where to park, when not to move the car, and when taxi/walking is better.
- Holiday plans must be conservative: earlier starts, fewer “maybe” stops, and stronger fallback rules.
- City-core attractions can often stay fixed while lodging changes; adjust only access, parking, meals, and start/end routes.
- When adding a new attraction to a full itinerary, replace something of similar time/route cost instead of blindly appending.
- For restaurants, prioritize “on-route and reliable” over “famous but costly to reach or queue.”
- Be explicit when a map coordinate is approximate or derived from a landmark instead of a confirmed address.

## References

- Read `references/workflow.md` for the full reusable planning checklist and artifact QA steps.
- Use `assets/interactive-map-template.html` as boilerplate for future city maps.
