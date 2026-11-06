Lab 5 — Seattle Vessel Trajectories Thea Weng


1.This map shows Seattle and nearby Puget Sound waters using AIS data requested from [MarineCadastre AccessAIS](https://marinecadastre.gov/accessais/) for October 29, 2025 (UTC). I chose this area to examine passenger and commercial vessel movement around Seattle. Selecting one day and a limited area kept the dataset manageable while allowing changes within the day to be explored.

The CSV was converted using the class notebook's conversion code. The resulting dataset contains 960 vessels and 277,525 position observations after duplicate records were removed. The map displays paths with at least two positions. Original timestamps are UTC, while the map displays Seattle local time with its time zone.


2.At approximately 19:08 PDT on October 28, the Passenger filter selects 33 paths. Several visible trails approach or leave the Seattle waterfront along different directions. This shows how passenger movement connects the waterfront with surrounding waters. The selected count describes paths in the dataset, not the number of vessels moving at that exact moment.

The displayed October 28 date is consistent with the requested October 29 UTC data because Seattle local time is seven hours behind UTC on this date. The one-hour trails show recent movement rather than all movement during the entire day. Pausing and using the slider makes it easier to inspect individual moments without overlapping a full day's trajectories.

These observations represent one day's recorded AIS positions. They do not establish typical daily traffic or the busiest hour. Lines connect successive reports, so gaps in reporting may hide the actual route traveled.


3.A potential user is a transportation planner examining passenger vessel routes near Seattle. I propose a trail-length slider that lets the user compare shorter and longer periods of recent movement.

The [deck.gl TripsLayer documentation](https://deck.gl/docs/api-reference/geo-layers/trips-layer) explains how `trailLength` controls the visible duration of a trajectory. This inspired the proposal: shorter trails could help separate recent movements, while longer trails could reveal more of the routes. The current map uses a fixed one-hour trail; the proposed control would let the planner adjust that window.