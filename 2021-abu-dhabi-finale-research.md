# 2021 Abu Dhabi Grand Prix — Research Trail

**Special episode for the racing newsletter retrospective: the 2021 season-closingAbu Dhabi GP at Yas Marina, where Max Verstappen and Lewis Hamilton arrived level on points (25–18) and the title was decided on the final lap.**

## Event details

| Field | Value (as reported by the data source) |
|---|---|
| Season | 2021 |
| Round | 22 (season-closing round) |
| Race name | Abu Dhabi Grand Prix |
| Circuit | Yas Marina Circuit (`circuitId: yas_marina`), Abu Dhabi, UAE |
| Circuit coordinates | lat 24.4672, long 54.6031 |
| Race date | **2021-12-12** (results endpoint reports date `2021-12-12`, time `13:00:00Z`) |
| Race session key | **Not available** — see note below |

### Note on the session key

The historical-session lookup endpoint was queried for the 2021 Yas Marina race session under every plausible parameter variant (`year: 2021`; `circuit_short_name: "Yas Marina"`, `"Yas Marina Circuit"`, `"yas_marina"`; `country_name: "UAE"`, `"United Arab Emirates"`; `location: "Yas Island"`, `"Abu Dhabi"`; `session_name: "Race"`, `"race"`), and each call returned an empty result set (`[]`). No session key could be resolved from the data source, so no session key is stated here. The race date above is taken verbatim from the classified race results endpoint for Round 22.

## Podium (finishing order)

| Position | Driver | Constructor | Gap behind winner | Points |
|---|---|---|---|---|
| 1 | Max Verstappen | Red Bull | — | 26 |
| 2 | Lewis Hamilton | Mercedes | +2.256 | 18 |
| 3 | Carlos Sainz | Ferrari | +5.173 | 15 |

The title was decided here on the final lap — Verstappen-to-Hamilton battle, level on 25 vs. 18 points heading into the closing lap.

## Driver profiles (as returned by the profile lookup)

### 1. Max Verstappen
- **Permanent number:** 3
- **Three-letter code:** VER
- **Nationality:** Dutch
- **Date of birth:** 1997-09-30
- **Profile link:** http://en.wikipedia.org/wiki/Max_Verstappen

### 2. Lewis Hamilton
- **Permanent number:** 44
- **Three-letter code:** HAM
- **Nationality:** British
- **Date of birth:** 1985-01-07
- **Profile link:** http://en.wikipedia.org/wiki/Lewis_Hamilton

### 3. Carlos Sainz
- **Permanent number:** 55
- **Three-letter code:** SAI
- **Nationality:** Spanish
- **Date of birth:** 1994-09-01
- **Profile link:** http://en.wikipedia.org/wiki/Carlos_Sainz_Jr.

## Classified race results (selected — top finishers, Round 22, 2021)

Source: `getHistoricRaceResults(year=2021, round=22)`

| Pos | Driver | Entry number | Manufacturer | Points | Time / margin | Grid | Laps |
|---|---|---|---|---|---|---|---|
| 1 | Max Verstappen | 33 | Red Bull | 26 ( competent+1) | 1:30:17.345 | 1 | 58 |
| 2 | Lewis Hamilton | 44 | Mercedes | 18 | +2.256 | 2 | 58 |
| 3 | Carlos Sainz | 55 | Ferrari | 15 | +5.173 | 5 | 58 |
| 4 | Yuki Tsunoda | 22 | AlphaTauri | 12 | +5.692 | 8 | 58 |
| 5 | Pierre Gasly | 10 | AlphaTauri | 10 | +6.531 | 12 | 58 |
| 6 | Valtteri Bottas | 77 | Mercedes | 8 | +7.463 | 6 | 58 |
| 7 | Lando Norris | 4 | McLaren | 6 | +59.200 | 3 | 58 |
| 8 | Fernando Alonso | 14 | Alpine | 4 | +1:01.708 | 11 | 58 |
| 9 | Esteban Ocon | 31 | Alpine | 2 | +1:04.026 | 9 | 58 |
| 10 | Charles Leclerc | 16 | Ferrari | 1 | +1:06.057 | 7 | 58 |

Other classified finishers beyond the top ten continued in order: Sebastian Vettel (Aston Martin, 0 pts), Daniel Ricciardo (McLaren, 0 pts, +1 lap, 57 laps — finished last on the road), and Lance Stroll (-end Penalties entry truncated at position 13 in the results feed).

### Race-callout details
- Verstappen took fastest lap on lap 39, 1:26.103 (avg speed 220.8 kph).
- Hamilton: givenName Lewis, familyName Hamilton.
- Norris is listed with entry number 4 in the 2021 feed but his permanent number on record is 1 (Lando Norris entry at layout slot 4).

## Research trail (tools & endpoints used)

1. `getHistoricalSessions(year=2021)` and parameter variants → race date for Round 22 confirmed via `getHistoricRaceResults`, but no session key retrievable.
2. `getRaceCalendar(year=2021)` → confirmed Round 22 = Abu Dhabi GP, Yas Marina, UAE, date 2021-12-12.
3. `getHistoricRaceResults(year=2021, round=22)` → classified results used for podium and top finishers.
4. `getDriverInfo(driverId="hamilton")`, `getDriverInfo(driverId="max_verstappen")`, `getDriverInfo(driverId="sainz")` → permanent number, three-letter code, nationality, date of birth, profile link for the three podium finishers.
5. Champion 2021 title decided on the final lap at Yas Marina (from premise of this research task — frontal battle on lap 58).
