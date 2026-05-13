# Generic Travel Planning Workflow

## Intake

Collect:
- dates and exact weekday/holiday context;
- origin and transportation mode;
- destination city/region and must-see/optional stops;
- lodging name/address and parking situation;
- meal preferences, restaurant links, and dietary constraints;
- desired output: chat plan, HTML map, printable brief, GitHub artifact.

If the user provides screenshots, extract text carefully and treat it as user context, not verified truth.

## Research

Browse for unstable facts:
- opening hours, ticket windows, reservation rules, closure notices;
- holiday traffic and parking;
- current restaurant phone numbers, addresses, booking links;
- travel time and road direction when route choices matter.

Source priority:
1. official attraction/government pages;
2. map/booking/restaurant platform pages;
3. user-supplied links;
4. blogs only for qualitative tips, never for hard facts unless corroborated.

## Route Building

Build days by direction:
- Day 1: arrival corridor + light city-core or nearby low-risk stop.
- Middle days: scarce-ticket or far attractions first; optional/photography stops late.
- Final day: near lodging or return corridor; avoid route detours before a long return.

For every day provide:
- start point, departure time, drive/transit assumption;
- ordered stops;
- meal plan with alternatives;
- parking/taxi/walking guidance;
- fallback rule.

## Versioning

Create versions when the user asks to compare or preserve an old plan:
- `v1`: baseline;
- `v2`: optional attraction or route alternative;
- `v3`: lodging-adjusted or final operational plan.

Each version should switch together:
- route summary text;
- detailed day tables;
- route polylines;
- version-specific markers;
- warnings and restaurant recommendations.

## Restaurant Handling

For each restaurant marker include:
- name;
- address;
- phone if available;
- platform link if available;
- best meal/use case;
- holiday caution;
- parking/queue note.

Do not invent restaurants from vague lists. If a restaurant cannot be verified, either omit it or label it as an unverified “area search” only until the user supplies a trusted link.

## Map Artifact QA

Before delivery:
- open or reload the file in the browser;
- verify the base map renders;
- verify default version is the intended one;
- test version switching;
- click at least one restaurant popup;
- inspect that labels do not make the map unreadable at default zoom;
- ensure assumptions and approximate coordinates are stated.

If the user wants GitHub upload:
- check `git status`;
- commit only relevant changes;
- preserve unrelated user files;
- push with the configured remote/SSH host;
- report the commit and any push failure reason.
