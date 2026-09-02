# Lebanon Administrative Divisions / لبنان



## Overview

| Item | Details |
|------|---------|
| Governorate | 8 |
| District | 26 |
| Cadastre | 1,610 |
| Coordinates | ✅ Included (all levels) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-09-02 |
| Website | [openadmindata.org/lb](https://openadmindata.org/lb/) |
| API | [openadmindata.org/api/lb](https://openadmindata.org/api/lb/) |
| Flag | [PNG](https://onlygames.me/flags-png/lb/) · [CDN](https://www.freeflags.org/cdn/) · [CSS](https://www.freeflags.org/css/) · [Collections](https://www.freeflags.org/collections/) |
| National Anthem | [🎵 Listen & Download Lebanon National Anthem MP3](https://onlygames.me/national-anthems/lb/) |

## Browse by Governorate

| # | Governorate | Districts | Cadastres | Link |
|---|----|----|----|------|
| 1 | عكار (Akkar) | 1 | 168 | [Browse](divisions/akkar-lb7/) |
| 2 | بعلبك - الهرمل (Baalbek-El Hermel) | 2 | 100 | [Browse](divisions/baalbek-el-hermel-lb8/) |
| 3 | بيروت (Beirut) | 1 | 13 | [Browse](divisions/beirut-lb1/) |
| 4 | البقاع (Bekaa) | 3 | 144 | [Browse](divisions/bekaa-lb2/) |
| 5 | النبطية (El Nabatieh) | 4 | 145 | [Browse](divisions/el-nabatieh-lb4/) |
| 6 | جبل لبنان (Mount Lebanon) | 6 | 536 | [Browse](divisions/mount-lebanon-lb3/) |
| 7 | الشمال (North) | 6 | 273 | [Browse](divisions/north-lb5/) |
| 8 | الجنوب (South) | 3 | 231 | [Browse](divisions/south-lb6/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-governorate.json](data/all-governorate.json) | JSON | All 8 governorate records |
| [all-district.json](data/all-district.json) | JSON | All 26 district records |
| [all-cadastre.json](data/all-cadastre.json) | JSON | All 1,610 cadastre records |
| [all-flat.json](data/all-flat.json) | JSON | Levels 1-2 flat array |
| [all-flat.ndjson](data/all-flat.ndjson) | NDJSON | Streaming format |
| [all-flat.csv](data/all-flat.csv) | CSV | Spreadsheet format |
| [hierarchy.json](data/hierarchy.json) | JSON | Nested tree |
| [schema.json](data/schema.json) | JSON Schema | Data schema |

## Quick Start

### Python

```python
import json

with open("data/all-governorate.json", "r", encoding="utf-8") as f:
    data = json.load(f)

for r in data:
    print(f"{r['name']['local']} ({r['name']['en']}) — {r['children_count']['district']} districts")
```

### JavaScript

```javascript
import { readFileSync } from "fs";

const data = JSON.parse(readFileSync("data/all-governorate.json", "utf-8"));
console.log(`Total: ${data.length} governorates`);
```

## Schema

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier |
| `level` | integer | 1=governorate, 2=district, 3=cadastre |
| `level_name` | object | Level label (local + English) |
| `name.local` | string | Name in local script |
| `name.en` | string | English name |
| `name.slug` | string | URL-safe slug |
| `parent` | object/null | Parent division reference |
| `ancestors` | array | Full ancestor chain |
| `children_count` | object | Count of children per level |
| `zip_codes` | array | Postal codes (where available) |
| `geo.lat` | string | Latitude (WGS84) |
| `geo.lon` | string | Longitude (WGS84) |

Full schema: [data/schema.json](data/schema.json)

## Hierarchy Browse

```
divisions/{governorate-slug}/
divisions/{governorate-slug}/{district-slug}/
```

Cadastres are listed inline in each district's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-governorate links
- [Per-governorate data](docs/llms-full/) — Full data by governorate

## Citation

```
Lebanon Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/lebanon-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [Open Admin Data](https://openadmindata.org) — Browse, search and explore administrative divisions for every country
- [open-admin-data](https://github.com/open-admin-data) — GitHub organization with all country repos
- [ListBase](https://www.listbase.org) — Structured reference data for every country
- [FreeFlags.org](https://www.freeflags.org) — Free flag images for every country
- [Flag CDN](https://www.freeflags.org/cdn/) — Hotlink flag images directly
- [Flag CSS](https://www.freeflags.org/css/) — CSS flag sprites for web projects
- [Flag Collections](https://www.freeflags.org/collections/) — Curated flag image packs
