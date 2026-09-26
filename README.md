# Steam Game Database

JSON dump of the [Game Gauntlets](https://gamegauntlets.com) game catalog: prices, scores and metadata
merged from Steam, GOG, SteamSpy, GameFAQs, Metacritic, IGDB, HowLongToBeat, Wikidata and GameRankings.

Updated nightly at 23:48 UTC.

_Generated 2026-09-26T23:50:07.768Z._

## Files

| File | Rows | Size |
|---|---|---|
| `steamdb.json` | 188,485 | 595.0 MB |
| `steamdb.min.json` | 188,485 | 435.3 MB |
| `steamdb.min.json.gz` | 188,485 | 91.9 MB |

## Catalog totals

| Metric | Count |
|---|---|
| Games in the catalog | 188,485 |
| Steam games | 186,190 |
| GOG-exclusive games | 2,295 |
| Steam games also on GOG | 4,628 |

## Schema

"Coverage" is the share of exported games that currently have a value for that key. Any key may be
`null` when the value is unknown.

| Key | Type | Source | Coverage | Description |
|---|---|---|---|---|
| `id` | integer | gamegauntlets | 100.0% (188,485) | catalog id, stable across updates |
| `kind` | string | gamegauntlets | 100.0% (188,485) | 'steam' or 'gog_exclusive' |
| `name` | string | gamegauntlets | 100.0% (188,485) | game title |
| `image` | string | gamegauntlets | 100.0% (188,393) | header image URL |
| `description` | string | gamegauntlets | 99.9% (188,331) | English store description (raw HTML) |
| `steam_appid` | integer | steam | 98.8% (186,190) | Steam appid |
| `steam_url` | string | steam | 98.8% (186,190) | Steam store page URL |
| `gog_id` | integer | gog | 3.7% (6,923) | GOG catalog id |
| `gog_url` | string | gog | 3.8% (7,180) | GOG store page URL |
| `release_date` | date (`YYYY-MM-DD`) | gamegauntlets | 71.4% (134,533) | cross-source consensus release date |
| `release_precision` | string | gamegauntlets | 71.4% (134,533) | day/month/quarter/year/unknown |
| `early_access_date` | date (`YYYY-MM-DD`) | steam | 2.1% (3,972) | date the game entered Early Access, if it did |
| `store_release_date` | date (`YYYY-MM-DD`) | gamegauntlets | 69.8% (131,622) | store listing date (may be a re-listing, not the true release date) |
| `price_usd` | integer | gamegauntlets | 60.9% (114,777) | USD list price, cents |
| `price_final_usd` | integer | gamegauntlets | 60.9% (114,777) | USD price after discount, cents |
| `discount_percent` | integer | gamegauntlets | 30.5% (57,481) | discount percent, 0..100 |
| `platforms` | array of strings | gamegauntlets | 100.0% (188,467) | WIN/MAC/LNX |
| `developers` | array of strings | gamegauntlets | 99.9% (188,371) | developer names |
| `publishers` | array of strings | gamegauntlets | 99.8% (188,103) | publisher names |
| `languages` | array of strings | gamegauntlets | 99.9% (188,267) | interface language names |
| `voiceovers` | array of strings | gamegauntlets | 44.4% (83,653) | voiceover language names |
| `categories` | array of strings | gamegauntlets | 99.9% (188,388) | store category tags |
| `genres` | array of strings | gamegauntlets | 99.9% (188,388) | genre tags |
| `tags` | array of strings | gamegauntlets | 37.4% (70,431) | community tags |
| `achievements` | integer | steam | 37.4% (70,510) | achievement count |
| `steam_reviews_percent` | integer | steam | 53.9% (101,532) | all-time positive review share, 0..100 |
| `steam_reviews_count` | integer | steam | 52.7% (99,318) | all-time review count |
| `steam_reviews_label` | string | steam | 33.9% (63,873) | Steam's own label ("Very Positive", ...), null under 10 votes |
| `steam_recent_percent` | integer | steam | 15.0% (28,235) | last ~30 days positive review share, 0..100 |
| `steam_recent_count` | integer | steam | 15.0% (28,235) | last ~30 days review count |
| `steam_recent_label` | string | steam | 2.1% (3,889) | recent-reviews label, null under 10 votes |
| `steamspy_owners` | integer | steamspy | 48.9% (92,092) | owners estimate, lower bound |
| `average_playtime_hours` | number | gamegauntlets | 8.1% (15,201) | resolved average playtime, decimal hours |
| `average_playtime_source` | string | gamegauntlets | 8.1% (15,201) | which source produced average_playtime_hours |
| `hltb_url` | string | hltb | 22.0% (41,458) | HowLongToBeat page URL |
| `hltb_main_hours` | number | hltb | 12.8% (24,105) | main story hours, decimal |
| `hltb_complete_hours` | number | hltb | 100.0% (188,485) | completionist hours, decimal |
| `gamefaqs_url` | string | gamefaqs | 38.9% (73,325) | GameFAQs product page URL |
| `gamefaqs_difficulty` | string | gamefaqs | 10.4% (19,643) | GameFAQs difficulty label |
| `gamefaqs_rating` | number | gamefaqs | 11.4% (21,443) | GameFAQs rating, 0..5 |
| `metacritic_url` | string | metacritic | 66.5% (125,403) | Metacritic page URL |
| `metacritic_score` | integer | metacritic | 4.6% (8,587) | critic score, 0..100 |
| `metacritic_reviews` | integer | metacritic | 4.3% (8,049) | critic review count |
| `metacritic_user_score` | integer | metacritic | 6.3% (11,798) | user score, 0..100 |
| `igdb_url` | string | igdb | 52.9% (99,705) | IGDB page URL |
| `igdb_score` | integer | igdb | 4.1% (7,811) | IGDB critic score, 0..100 |
| `igdb_user_score` | integer | igdb | 10.0% (18,854) | IGDB user score, 0..100 |
| `gamerankings_score` | integer | gamerankings | 3.4% (6,491) | critic score, 0..100 |
| `gg_score` | integer | gamegauntlets | 100.0% (188,485) | Game Gauntlets' own composite score |
| `gg_points` | integer | gamegauntlets | 100.0% (188,485) | Game Gauntlets priority score (wheel weighting) |
| `updated_at` | datetime (ISO 8601) | gamegauntlets | 100.0% (188,485) | last time this row changed |

## Example

```json
{
  "id": 1,
  "kind": "steam",
  "name": "Counter-Strike",
  "image": "https://shared.akamai.steamstatic.com/store_item_assets/steam/apps/10/header.jpg?t=1745368572",
  "description": "Play the world's number 1 online action game. Engage in an incredibly realistic brand of terrorist warfare in this wildly popular team-based game. Ally with teammates to complete strategic missions. Take out enemy sites. Rescue hostages. Your role affects your team's success. Your team's success affects your role.",
  "steam_appid": 10,
  "steam_url": "https://store.steampowered.com/app/10",
  "gog_id": null,
  "gog_url": null,
  "release_date": "2000-11-01",
  "release_precision": "day",
  "early_access_date": null,
  "store_release_date": "2000-11-01",
  "price_usd": 999,
  "price_final_usd": 999,
  "discount_percent": 0,
  "platforms": [
    "WIN",
    "MAC",
    "LNX"
  ],
  "developers": [
    "Valve"
  ],
  "publishers": [
    "Valve",
    "Nexon",
    "Sierra Entertainment"
  ],
  "languages": [
    "English",
    "French",
    "German",
    "Italian",
    "Spanish - Spain",
    "Simplified Chinese",
    "Traditional Chinese",
    "Korean"
  ],
  "voiceovers": [
    "English",
    "French",
    "German",
    "Italian",
    "Spanish - Spain",
    "Simplified Chinese",
    "Traditional Chinese",
    "Korean"
  ],
  "categories": [
    "Multi-player",
    "PvP",
    "Online PvP",
    "Shared/Split Screen PvP",
    "Valve Anti-Cheat enabled",
    "Color Alternatives",
    "Custom Volume Controls",
    "Keyboard Only Option",
    "Stereo Sound",
    "Family Sharing"
  ],
  "genres": [
    "Action",
    "Shooter"
  ],
  "tags": [
    "Action",
    "FPS",
    "Multiplayer",
    "Shooter",
    "Classic",
    "Team-Based",
    "First-Person",
    "Competitive",
    "Tactical",
    "1990's",
    "e-sports",
    "PvP",
    "Old School",
    "Military",
    "Strategy",
    "Survival",
    "Score Attack",
    "1980s",
    "Assassin",
    "Nostalgia"
  ],
  "achievements": null,
  "steam_reviews_percent": 97,
  "steam_reviews_count": 250245,
  "steam_reviews_label": "Overwhelmingly Positive",
  "steam_recent_percent": null,
  "steam_recent_count": null,
  "steam_recent_label": null,
  "steamspy_owners": 15000000,
  "average_playtime_hours": null,
  "average_playtime_source": null,
  "hltb_url": "https://howlongtobeat.com/game/1953",
  "hltb_main_hours": 25.4,
  "hltb_complete_hours": 775,
  "gamefaqs_url": "https://gamefaqs.gamespot.com/-/429818-",
  "gamefaqs_difficulty": "Just Right-Tough",
  "gamefaqs_rating": 3.9,
  "metacritic_url": "https://www.metacritic.com/game/counter-strike/",
  "metacritic_score": 88,
  "metacritic_reviews": 11,
  "metacritic_user_score": 79,
  "igdb_url": "https://www.igdb.com/games/counter-strike",
  "igdb_score": 70,
  "igdb_user_score": 83,
  "gamerankings_score": 89,
  "gg_score": 81,
  "gg_points": 223,
  "updated_at": "2026-09-20T04:45:47Z"
}
```

## Source status

"Remaining" is games with no data from that source yet, or whose last fetch is older than the source's own refresh interval.

| Source | Refresh | OK | Not found | Error | Games covered | Remaining | Paused | Last run |
|---|---|---|---|---|---|---|---|---|
| steam | 1d | 102,061 | 4,239 | 33 | 102,830 | 175,262 | no | 2026-09-26 23:49:27 |
| gog | 7d | 6,979 | 19 | 0 | 6,906 | 184,388 | no | 2026-09-26 03:04:38 |
| wikidata | 30d | 98,613 | 54 | 0 | 98,433 | 94,003 | no | 2026-09-20 04:29:40 |
| igdb | 30d | 103,995 | 40 | 0 | 104,006 | 89,427 | no | 2026-09-26 03:00:02 |
| steamspy | 7d | 80,539 | 33 | 0 | 80,539 | 112,175 | no | 2026-09-26 04:30:42 |
| hltb | 30d | 28,405 | 12,970 | 0 | 41,375 | 149,854 | no | 2026-09-26 06:33:02 |
| gamefaqs | 90d | 17,804 | 568 | 0 | 18,363 | 171,462 | no | 2026-09-26 23:49:16 |
| metacritic | 60d | 124,403 | 16,511 | 0 | 140,910 | 52,632 | no | 2026-09-26 17:26:29 |

## External links

| Site | Linked games |
|---|---|
| gamefaqs | 73,325 |
| gog | 7,180 |
| hltb | 41,458 |
| igdb | 99,889 |
| metacritic | 125,403 |
| mobygames | 38,473 |
| steam | 186,190 |
| wikidata | 94,506 |
| wikipedia_en | 7,117 |
| wikipedia_ru | 3,183 |

## Licence

The dataset is released under the GNU General Public License v3.0 (see `LICENSE` in this repo). Game
names, images, descriptions and prices belong to their respective publishers, platforms and third-party
sources.
