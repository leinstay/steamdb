# Steam Game Database

JSON dump of the [Game Gauntlets](https://gamegauntlets.com) game catalog: prices, scores and metadata
merged from Steam, GOG, SteamSpy, GameFAQs, Metacritic, IGDB, HowLongToBeat, Wikidata and GameRankings.

Updated nightly at 23:48 UTC.

_Generated 2026-09-23T23:50:46.188Z._

## Files

| File | Rows | Size |
|---|---|---|
| `steamdb.json` | 157,505 | 521.8 MB |
| `steamdb.min.json` | 157,505 | 386.1 MB |
| `steamdb.min.json.gz` | 157,505 | 85.9 MB |

## Catalog totals

| Metric | Count |
|---|---|
| Games in the catalog | 157,507 |
| Steam games | 155,239 |
| GOG-exclusive games | 2,268 |
| Steam games also on GOG | 4,613 |

## Schema

"Coverage" is the share of exported games that currently have a value for that key. Any key may be
`null` when the value is unknown.

| Key | Type | Source | Coverage | Description |
|---|---|---|---|---|
| `id` | integer | gamegauntlets | 100.0% (157,507) | catalog id, stable across updates |
| `kind` | string | gamegauntlets | 100.0% (157,507) | 'steam' or 'gog_exclusive' |
| `name` | string | gamegauntlets | 100.0% (157,507) | game title |
| `image` | string | gamegauntlets | 100.0% (157,501) | header image URL |
| `description` | string | gamegauntlets | 99.9% (157,425) | English store description (raw HTML) |
| `steam_appid` | integer | steam | 98.6% (155,239) | Steam appid |
| `steam_url` | string | steam | 98.6% (155,239) | Steam store page URL |
| `gog_id` | integer | gog | 4.4% (6,881) | GOG catalog id |
| `gog_url` | string | gog | 4.5% (7,140) | GOG store page URL |
| `release_date` | date (`YYYY-MM-DD`) | gamegauntlets | 80.5% (126,810) | cross-source consensus release date |
| `release_precision` | string | gamegauntlets | 80.5% (126,810) | day/month/quarter/year/unknown |
| `early_access_date` | date (`YYYY-MM-DD`) | steam | 1.8% (2,843) | date the game entered Early Access, if it did |
| `store_release_date` | date (`YYYY-MM-DD`) | gamegauntlets | 80.4% (126,684) | store listing date (may be a re-listing, not the true release date) |
| `price_usd` | integer | gamegauntlets | 70.0% (110,297) | USD list price, cents |
| `price_final_usd` | integer | gamegauntlets | 70.0% (110,297) | USD price after discount, cents |
| `discount_percent` | integer | gamegauntlets | 32.4% (50,976) | discount percent, 0..100 |
| `platforms` | array of strings | gamegauntlets | 100.0% (157,491) | WIN/MAC/LNX |
| `developers` | array of strings | gamegauntlets | 100.0% (157,448) | developer names |
| `publishers` | array of strings | gamegauntlets | 99.8% (157,269) | publisher names |
| `languages` | array of strings | gamegauntlets | 99.9% (157,333) | interface language names |
| `voiceovers` | array of strings | gamegauntlets | 43.1% (67,898) | voiceover language names |
| `categories` | array of strings | gamegauntlets | 99.9% (157,410) | store category tags |
| `genres` | array of strings | gamegauntlets | 100.0% (157,476) | genre tags |
| `tags` | array of strings | gamegauntlets | 44.7% (70,378) | community tags |
| `achievements` | integer | steam | 42.7% (67,206) | achievement count |
| `steam_reviews_percent` | integer | steam | 60.1% (94,650) | all-time positive review share, 0..100 |
| `steam_reviews_count` | integer | steam | 58.5% (92,204) | all-time review count |
| `steam_reviews_label` | string | steam | 37.9% (59,686) | Steam's own label ("Very Positive", ...), null under 10 votes |
| `steam_recent_percent` | integer | steam | 13.9% (21,884) | last ~30 days positive review share, 0..100 |
| `steam_recent_count` | integer | steam | 13.9% (21,884) | last ~30 days review count |
| `steam_recent_label` | string | steam | 1.9% (2,964) | recent-reviews label, null under 10 votes |
| `steamspy_owners` | integer | steamspy | 58.4% (92,045) | owners estimate, lower bound |
| `average_playtime_hours` | number | gamegauntlets | 7.6% (12,036) | resolved average playtime, decimal hours |
| `average_playtime_source` | string | gamegauntlets | 7.6% (12,036) | which source produced average_playtime_hours |
| `hltb_url` | string | hltb | 26.1% (41,040) | HowLongToBeat page URL |
| `hltb_main_hours` | number | hltb | 15.0% (23,658) | main story hours, decimal |
| `hltb_complete_hours` | number | hltb | 100.0% (157,506) | completionist hours, decimal |
| `gamefaqs_url` | string | gamefaqs | 46.5% (73,207) | GameFAQs product page URL |
| `gamefaqs_difficulty` | string | gamefaqs | 12.4% (19,485) | GameFAQs difficulty label |
| `gamefaqs_rating` | number | gamefaqs | 13.5% (21,273) | GameFAQs rating, 0..5 |
| `metacritic_url` | string | metacritic | 49.7% (78,353) | Metacritic page URL |
| `metacritic_score` | integer | metacritic | 5.0% (7,860) | critic score, 0..100 |
| `metacritic_reviews` | integer | metacritic | 4.6% (7,318) | critic review count |
| `metacritic_user_score` | integer | metacritic | 7.0% (10,975) | user score, 0..100 |
| `igdb_url` | string | igdb | 63.3% (99,685) | IGDB page URL |
| `igdb_score` | integer | igdb | 5.0% (7,808) | IGDB critic score, 0..100 |
| `igdb_user_score` | integer | igdb | 12.0% (18,854) | IGDB user score, 0..100 |
| `gamerankings_score` | integer | gamerankings | 4.1% (6,490) | critic score, 0..100 |
| `gg_score` | integer | gamegauntlets | 100.0% (157,506) | Game Gauntlets' own composite score |
| `gg_points` | integer | gamegauntlets | 100.0% (157,506) | Game Gauntlets priority score (wheel weighting) |
| `updated_at` | datetime (ISO 8601) | gamegauntlets | 100.0% (157,507) | last time this row changed |

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
| steam | 1d | 68,620 | 430 | 33 | 68,629 | 143,171 | no | 2026-09-23 23:49:12 |
| gog | 7d | 6,948 | 18 | 0 | 6,863 | 150,659 | no | 2026-09-23 03:04:31 |
| wikidata | 30d | 98,613 | 54 | 0 | 98,433 | 63,048 | no | 2026-09-20 04:29:40 |
| igdb | 30d | 103,992 | 40 | 0 | 104,003 | 58,481 | no | 2026-09-23 03:00:05 |
| steamspy | 7d | 80,510 | 33 | 0 | 80,510 | 81,190 | no | 2026-09-23 04:30:45 |
| hltb | 30d | 19,439 | 0 | 0 | 19,439 | 139,351 | no | 2026-09-23 06:38:55 |
| gamefaqs | 90d | 17,080 | 209 | 0 | 17,288 | 141,499 | no | 2026-09-23 23:49:12 |
| metacritic | 60d | 79,158 | 9,101 | 0 | 88,255 | 74,289 | no | 2026-09-23 21:06:19 |

## External links

| Site | Linked games |
|---|---|
| gamefaqs | 73,207 |
| gog | 7,140 |
| hltb | 41,040 |
| igdb | 99,869 |
| metacritic | 78,353 |
| mobygames | 38,460 |
| steam | 155,262 |
| wikidata | 94,493 |
| wikipedia_en | 7,110 |
| wikipedia_ru | 3,180 |

## Licence

The dataset is released under the GNU General Public License v3.0 (see `LICENSE` in this repo). Game
names, images, descriptions and prices belong to their respective publishers, platforms and third-party
sources.
