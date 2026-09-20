# Steam Game Database

JSON dump of the [Game Gauntlets](https://gamegauntlets.com) game catalog: prices, scores and metadata
merged from Steam, GOG, SteamSpy, GameFAQs, Metacritic, IGDB, HowLongToBeat, Wikidata and GameRankings.

Updated nightly at 23:48 UTC.

_Generated 2026-09-20T23:49:19.668Z._

## Files

| File | Rows | Size |
|---|---|---|
| `steamdb.json` | 121,584 | 435.4 MB |
| `steamdb.min.json` | 121,584 | 328.3 MB |
| `steamdb.min.json.gz` | 121,584 | 78.3 MB |

## Catalog totals

| Metric | Count |
|---|---|
| Games in the catalog | 121,581 |
| Steam games | 119,325 |
| GOG-exclusive games | 2,256 |
| Steam games also on GOG | 4,601 |

## Schema

"Coverage" is the share of exported games that currently have a value for that key. Any key may be
`null` when the value is unknown.

| Key | Type | Source | Coverage | Description |
|---|---|---|---|---|
| `id` | integer | gamegauntlets | 100.0% (121,581) | catalog id, stable across updates |
| `kind` | string | gamegauntlets | 100.0% (121,581) | 'steam' or 'gog_exclusive' |
| `name` | string | gamegauntlets | 100.0% (121,581) | game title |
| `image` | string | gamegauntlets | 100.0% (121,577) | header image URL |
| `description` | string | gamegauntlets | 99.9% (121,498) | English store description (raw HTML) |
| `steam_appid` | integer | steam | 98.1% (119,325) | Steam appid |
| `steam_url` | string | steam | 98.1% (119,325) | Steam store page URL |
| `gog_id` | integer | gog | 5.6% (6,857) | GOG catalog id |
| `gog_url` | string | gog | 5.9% (7,142) | GOG store page URL |
| `release_date` | date (`YYYY-MM-DD`) | gamegauntlets | 93.2% (113,326) | cross-source consensus release date |
| `release_precision` | string | gamegauntlets | 93.2% (113,326) | day/month/quarter/year/unknown |
| `early_access_date` | date (`YYYY-MM-DD`) | steam | 0.8% (1,007) | date the game entered Early Access, if it did |
| `store_release_date` | date (`YYYY-MM-DD`) | gamegauntlets | 93.1% (113,181) | store listing date (may be a re-listing, not the true release date) |
| `price_usd` | integer | gamegauntlets | 80.6% (97,946) | USD list price, cents |
| `price_final_usd` | integer | gamegauntlets | 80.6% (97,946) | USD price after discount, cents |
| `discount_percent` | integer | gamegauntlets | 30.3% (36,807) | discount percent, 0..100 |
| `platforms` | array of strings | gamegauntlets | 100.0% (121,579) | WIN/MAC/LNX |
| `developers` | array of strings | gamegauntlets | 100.0% (121,535) | developer names |
| `publishers` | array of strings | gamegauntlets | 99.8% (121,385) | publisher names |
| `languages` | array of strings | gamegauntlets | 99.9% (121,404) | interface language names |
| `voiceovers` | array of strings | gamegauntlets | 43.6% (53,052) | voiceover language names |
| `categories` | array of strings | gamegauntlets | 99.9% (121,472) | store category tags |
| `genres` | array of strings | gamegauntlets | 100.0% (121,558) | genre tags |
| `tags` | array of strings | gamegauntlets | 59.8% (72,666) | community tags |
| `achievements` | integer | steam | 48.4% (58,863) | achievement count |
| `steam_reviews_percent` | integer | steam | 68.6% (83,393) | all-time positive review share, 0..100 |
| `steam_reviews_count` | integer | steam | 65.9% (80,156) | all-time review count |
| `steam_reviews_label` | string | steam | 44.8% (54,521) | Steam's own label ("Very Positive", ...), null under 10 votes |
| `steam_recent_percent` | integer | steam | 7.4% (9,040) | last ~30 days positive review share, 0..100 |
| `steam_recent_count` | integer | steam | 7.4% (9,040) | last ~30 days review count |
| `steam_recent_label` | string | steam | 0.9% (1,101) | recent-reviews label, null under 10 votes |
| `steamspy_owners` | integer | steamspy | 78.3% (95,155) | owners estimate, lower bound |
| `average_playtime_hours` | number | gamegauntlets | 4.9% (5,947) | resolved average playtime, decimal hours |
| `average_playtime_source` | string | gamegauntlets | 4.9% (5,947) | which source produced average_playtime_hours |
| `hltb_url` | string | hltb | 34.0% (41,339) | HowLongToBeat page URL |
| `hltb_main_hours` | number | hltb | 18.8% (22,860) | main story hours, decimal |
| `hltb_complete_hours` | number | hltb | 100.0% (121,581) | completionist hours, decimal |
| `gamefaqs_url` | string | gamefaqs | 62.1% (75,554) | GameFAQs product page URL |
| `gamefaqs_difficulty` | string | gamefaqs | 15.9% (19,311) | GameFAQs difficulty label |
| `gamefaqs_rating` | number | gamefaqs | 17.4% (21,166) | GameFAQs rating, 0..5 |
| `metacritic_url` | string | metacritic | 38.6% (46,908) | Metacritic page URL |
| `metacritic_score` | integer | metacritic | 6.2% (7,563) | critic score, 0..100 |
| `metacritic_reviews` | integer | metacritic | 5.7% (6,979) | critic review count |
| `metacritic_user_score` | integer | metacritic | 8.6% (10,501) | user score, 0..100 |
| `igdb_url` | string | igdb | 84.4% (102,673) | IGDB page URL |
| `igdb_score` | integer | igdb | 6.6% (7,968) | IGDB critic score, 0..100 |
| `igdb_user_score` | integer | igdb | 15.8% (19,203) | IGDB user score, 0..100 |
| `gamerankings_score` | integer | gamerankings | 5.4% (6,543) | critic score, 0..100 |
| `gg_score` | integer | gamegauntlets | 100.0% (121,581) | Game Gauntlets' own composite score |
| `gg_points` | integer | gamegauntlets | 100.0% (121,581) | Game Gauntlets priority score (wheel weighting) |
| `updated_at` | datetime (ISO 8601) | gamegauntlets | 100.0% (121,581) | last time this row changed |

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
| steam | 1d | 25,874 | 58 | 33 | 25,878 | 110,167 | no | 2026-09-20 23:49:06 |
| gog | 7d | 6,941 | 18 | 0 | 6,837 | 114,739 | no | 2026-09-20 03:04:03 |
| wikidata | 30d | 98,614 | 53 | 0 | 98,434 | 24,955 | no | 2026-09-20 04:29:40 |
| igdb | 30d | 103,979 | 37 | 0 | 103,990 | 19,587 | no | 2026-09-20 03:00:19 |
| steamspy | 7d | 80,510 | 33 | 0 | 80,510 | 42,947 | no | 2026-09-20 13:02:03 |
| hltb | 30d | 8,079 | 36 | 0 | 8,114 | 113,892 | no | 2026-09-20 04:22:20 |
| gamefaqs | 90d | 13,481 | 813 | 0 | 14,291 | 108,007 | no | 2026-09-20 23:35:44 |
| metacritic | 60d | 35,259 | 4,408 | 0 | 39,665 | 83,158 | no | 2026-09-20 21:13:22 |

## External links

| Site | Linked games |
|---|---|
| gamefaqs | 75,546 |
| gog | 7,142 |
| hltb | 41,334 |
| igdb | 102,865 |
| metacritic | 46,900 |
| mobygames | 39,207 |
| steam | 119,317 |
| wikidata | 96,643 |
| wikipedia_en | 7,258 |
| wikipedia_ru | 3,240 |

## Licence

The dataset is released under the GNU General Public License v3.0 (see `LICENSE` in this repo). Game
names, images, descriptions and prices belong to their respective publishers, platforms and third-party
sources.
