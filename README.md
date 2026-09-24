# Steam Game Database

JSON dump of the [Game Gauntlets](https://gamegauntlets.com) game catalog: prices, scores and metadata
merged from Steam, GOG, SteamSpy, GameFAQs, Metacritic, IGDB, HowLongToBeat, Wikidata and GameRankings.

Updated nightly at 23:48 UTC.

_Generated 2026-09-24T23:49:57.553Z._

## Files

| File | Rows | Size |
|---|---|---|
| `steamdb.json` | 167,638 | 547.3 MB |
| `steamdb.min.json` | 167,638 | 403.6 MB |
| `steamdb.min.json.gz` | 167,638 | 88.4 MB |

## Catalog totals

| Metric | Count |
|---|---|
| Games in the catalog | 167,638 |
| Steam games | 165,367 |
| GOG-exclusive games | 2,271 |
| Steam games also on GOG | 4,614 |

## Schema

"Coverage" is the share of exported games that currently have a value for that key. Any key may be
`null` when the value is unknown.

| Key | Type | Source | Coverage | Description |
|---|---|---|---|---|
| `id` | integer | gamegauntlets | 100.0% (167,638) | catalog id, stable across updates |
| `kind` | string | gamegauntlets | 100.0% (167,638) | 'steam' or 'gog_exclusive' |
| `name` | string | gamegauntlets | 100.0% (167,638) | game title |
| `image` | string | gamegauntlets | 100.0% (167,625) | header image URL |
| `description` | string | gamegauntlets | 99.9% (167,549) | English store description (raw HTML) |
| `steam_appid` | integer | steam | 98.6% (165,367) | Steam appid |
| `steam_url` | string | steam | 98.6% (165,367) | Steam store page URL |
| `gog_id` | integer | gog | 4.1% (6,885) | GOG catalog id |
| `gog_url` | string | gog | 4.3% (7,144) | GOG store page URL |
| `release_date` | date (`YYYY-MM-DD`) | gamegauntlets | 77.2% (129,476) | cross-source consensus release date |
| `release_precision` | string | gamegauntlets | 77.2% (129,476) | day/month/quarter/year/unknown |
| `early_access_date` | date (`YYYY-MM-DD`) | steam | 1.9% (3,266) | date the game entered Early Access, if it did |
| `store_release_date` | date (`YYYY-MM-DD`) | gamegauntlets | 77.2% (129,346) | store listing date (may be a re-listing, not the true release date) |
| `price_usd` | integer | gamegauntlets | 67.2% (112,715) | USD list price, cents |
| `price_final_usd` | integer | gamegauntlets | 67.2% (112,715) | USD price after discount, cents |
| `discount_percent` | integer | gamegauntlets | 31.9% (53,398) | discount percent, 0..100 |
| `platforms` | array of strings | gamegauntlets | 100.0% (167,622) | WIN/MAC/LNX |
| `developers` | array of strings | gamegauntlets | 100.0% (167,572) | developer names |
| `publishers` | array of strings | gamegauntlets | 99.8% (167,381) | publisher names |
| `languages` | array of strings | gamegauntlets | 99.9% (167,457) | interface language names |
| `voiceovers` | array of strings | gamegauntlets | 43.3% (72,627) | voiceover language names |
| `categories` | array of strings | gamegauntlets | 99.9% (167,541) | store category tags |
| `genres` | array of strings | gamegauntlets | 100.0% (167,598) | genre tags |
| `tags` | array of strings | gamegauntlets | 42.0% (70,376) | community tags |
| `achievements` | integer | steam | 41.2% (69,003) | achievement count |
| `steam_reviews_percent` | integer | steam | 57.9% (97,093) | all-time positive review share, 0..100 |
| `steam_reviews_count` | integer | steam | 56.5% (94,699) | all-time review count |
| `steam_reviews_label` | string | steam | 36.6% (61,362) | Steam's own label ("Very Positive", ...), null under 10 votes |
| `steam_recent_percent` | integer | steam | 14.4% (24,156) | last ~30 days positive review share, 0..100 |
| `steam_recent_count` | integer | steam | 14.4% (24,156) | last ~30 days review count |
| `steam_recent_label` | string | steam | 2.1% (3,440) | recent-reviews label, null under 10 votes |
| `steamspy_owners` | integer | steamspy | 54.9% (92,040) | owners estimate, lower bound |
| `average_playtime_hours` | number | gamegauntlets | 7.9% (13,305) | resolved average playtime, decimal hours |
| `average_playtime_source` | string | gamegauntlets | 7.9% (13,305) | which source produced average_playtime_hours |
| `hltb_url` | string | hltb | 24.6% (41,192) | HowLongToBeat page URL |
| `hltb_main_hours` | number | hltb | 14.2% (23,766) | main story hours, decimal |
| `hltb_complete_hours` | number | hltb | 100.0% (167,638) | completionist hours, decimal |
| `gamefaqs_url` | string | gamefaqs | 43.7% (73,286) | GameFAQs product page URL |
| `gamefaqs_difficulty` | string | gamefaqs | 11.7% (19,635) | GameFAQs difficulty label |
| `gamefaqs_rating` | number | gamefaqs | 12.8% (21,430) | GameFAQs rating, 0..5 |
| `metacritic_url` | string | metacritic | 55.9% (93,748) | Metacritic page URL |
| `metacritic_score` | integer | metacritic | 4.8% (8,098) | critic score, 0..100 |
| `metacritic_reviews` | integer | metacritic | 4.5% (7,554) | critic review count |
| `metacritic_user_score` | integer | metacritic | 6.7% (11,273) | user score, 0..100 |
| `igdb_url` | string | igdb | 59.5% (99,679) | IGDB page URL |
| `igdb_score` | integer | igdb | 4.7% (7,808) | IGDB critic score, 0..100 |
| `igdb_user_score` | integer | igdb | 11.2% (18,848) | IGDB user score, 0..100 |
| `gamerankings_score` | integer | gamerankings | 3.9% (6,490) | critic score, 0..100 |
| `gg_score` | integer | gamegauntlets | 100.0% (167,638) | Game Gauntlets' own composite score |
| `gg_points` | integer | gamegauntlets | 100.0% (167,638) | Game Gauntlets priority score (wheel weighting) |
| `updated_at` | datetime (ISO 8601) | gamegauntlets | 100.0% (167,638) | last time this row changed |

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
| steam | 1d | 78,573 | 1,128 | 33 | 78,761 | 157,374 | no | 2026-09-24 23:49:09 |
| gog | 7d | 6,953 | 18 | 0 | 6,868 | 160,776 | no | 2026-09-24 03:06:49 |
| wikidata | 30d | 98,613 | 54 | 0 | 98,433 | 73,176 | no | 2026-09-20 04:29:40 |
| igdb | 30d | 103,994 | 40 | 0 | 104,005 | 68,604 | no | 2026-09-24 03:00:04 |
| steamspy | 7d | 80,511 | 33 | 0 | 80,511 | 91,308 | no | 2026-09-24 04:30:43 |
| hltb | 30d | 19,697 | 6,659 | 0 | 26,356 | 142,891 | no | 2026-09-24 06:34:43 |
| gamefaqs | 90d | 17,790 | 545 | 0 | 18,335 | 150,656 | no | 2026-09-24 23:49:16 |
| metacritic | 60d | 94,236 | 12,383 | 0 | 106,615 | 66,098 | no | 2026-09-24 19:10:18 |

## External links

| Site | Linked games |
|---|---|
| gamefaqs | 73,286 |
| gog | 7,144 |
| hltb | 41,192 |
| igdb | 99,863 |
| metacritic | 93,748 |
| mobygames | 38,458 |
| steam | 165,367 |
| wikidata | 94,486 |
| wikipedia_en | 7,110 |
| wikipedia_ru | 3,180 |

## Licence

The dataset is released under the GNU General Public License v3.0 (see `LICENSE` in this repo). Game
names, images, descriptions and prices belong to their respective publishers, platforms and third-party
sources.
