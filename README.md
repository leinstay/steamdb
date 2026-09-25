# Steam Game Database

JSON dump of the [Game Gauntlets](https://gamegauntlets.com) game catalog: prices, scores and metadata
merged from Steam, GOG, SteamSpy, GameFAQs, Metacritic, IGDB, HowLongToBeat, Wikidata and GameRankings.

Updated nightly at 23:48 UTC.

_Generated 2026-09-25T23:50:07.127Z._

## Files

| File | Rows | Size |
|---|---|---|
| `steamdb.json` | 178,493 | 574.0 MB |
| `steamdb.min.json` | 178,493 | 421.9 MB |
| `steamdb.min.json.gz` | 178,493 | 90.9 MB |

## Catalog totals

| Metric | Count |
|---|---|
| Games in the catalog | 178,495 |
| Steam games | 176,203 |
| GOG-exclusive games | 2,292 |
| Steam games also on GOG | 4,625 |

## Schema

"Coverage" is the share of exported games that currently have a value for that key. Any key may be
`null` when the value is unknown.

| Key | Type | Source | Coverage | Description |
|---|---|---|---|---|
| `id` | integer | gamegauntlets | 100.0% (178,495) | catalog id, stable across updates |
| `kind` | string | gamegauntlets | 100.0% (178,495) | 'steam' or 'gog_exclusive' |
| `name` | string | gamegauntlets | 100.0% (178,495) | game title |
| `image` | string | gamegauntlets | 100.0% (178,460) | header image URL |
| `description` | string | gamegauntlets | 99.9% (178,376) | English store description (raw HTML) |
| `steam_appid` | integer | steam | 98.7% (176,203) | Steam appid |
| `steam_url` | string | steam | 98.7% (176,203) | Steam store page URL |
| `gog_id` | integer | gog | 3.9% (6,917) | GOG catalog id |
| `gog_url` | string | gog | 4.0% (7,174) | GOG store page URL |
| `release_date` | date (`YYYY-MM-DD`) | gamegauntlets | 74.3% (132,672) | cross-source consensus release date |
| `release_precision` | string | gamegauntlets | 74.3% (132,672) | day/month/quarter/year/unknown |
| `early_access_date` | date (`YYYY-MM-DD`) | steam | 2.0% (3,589) | date the game entered Early Access, if it did |
| `store_release_date` | date (`YYYY-MM-DD`) | gamegauntlets | 73.3% (130,857) | store listing date (may be a re-listing, not the true release date) |
| `price_usd` | integer | gamegauntlets | 63.9% (114,083) | USD list price, cents |
| `price_final_usd` | integer | gamegauntlets | 63.9% (114,083) | USD price after discount, cents |
| `discount_percent` | integer | gamegauntlets | 30.7% (54,770) | discount percent, 0..100 |
| `platforms` | array of strings | gamegauntlets | 100.0% (178,476) | WIN/MAC/LNX |
| `developers` | array of strings | gamegauntlets | 100.0% (178,410) | developer names |
| `publishers` | array of strings | gamegauntlets | 99.8% (178,195) | publisher names |
| `languages` | array of strings | gamegauntlets | 99.9% (178,295) | interface language names |
| `voiceovers` | array of strings | gamegauntlets | 43.9% (78,301) | voiceover language names |
| `categories` | array of strings | gamegauntlets | 99.9% (178,397) | store category tags |
| `genres` | array of strings | gamegauntlets | 100.0% (178,434) | genre tags |
| `tags` | array of strings | gamegauntlets | 39.5% (70,421) | community tags |
| `achievements` | integer | steam | 39.2% (69,919) | achievement count |
| `steam_reviews_percent` | integer | steam | 55.2% (98,459) | all-time positive review share, 0..100 |
| `steam_reviews_count` | integer | steam | 53.8% (96,093) | all-time review count |
| `steam_reviews_label` | string | steam | 34.9% (62,308) | Steam's own label ("Very Positive", ...), null under 10 votes |
| `steam_recent_percent` | integer | steam | 14.2% (25,431) | last ~30 days positive review share, 0..100 |
| `steam_recent_count` | integer | steam | 14.2% (25,431) | last ~30 days review count |
| `steam_recent_label` | string | steam | 2.1% (3,694) | recent-reviews label, null under 10 votes |
| `steamspy_owners` | integer | steamspy | 51.6% (92,062) | owners estimate, lower bound |
| `average_playtime_hours` | number | gamegauntlets | 7.9% (14,015) | resolved average playtime, decimal hours |
| `average_playtime_source` | string | gamegauntlets | 7.9% (14,015) | which source produced average_playtime_hours |
| `hltb_url` | string | hltb | 23.2% (41,388) | HowLongToBeat page URL |
| `hltb_main_hours` | number | hltb | 13.4% (23,981) | main story hours, decimal |
| `hltb_complete_hours` | number | hltb | 100.0% (178,494) | completionist hours, decimal |
| `gamefaqs_url` | string | gamefaqs | 41.1% (73,313) | GameFAQs product page URL |
| `gamefaqs_difficulty` | string | gamefaqs | 11.0% (19,640) | GameFAQs difficulty label |
| `gamefaqs_rating` | number | gamefaqs | 12.0% (21,440) | GameFAQs rating, 0..5 |
| `metacritic_url` | string | metacritic | 61.4% (109,564) | Metacritic page URL |
| `metacritic_score` | integer | metacritic | 4.8% (8,508) | critic score, 0..100 |
| `metacritic_reviews` | integer | metacritic | 4.5% (7,974) | critic review count |
| `metacritic_user_score` | integer | metacritic | 6.6% (11,728) | user score, 0..100 |
| `igdb_url` | string | igdb | 55.9% (99,698) | IGDB page URL |
| `igdb_score` | integer | igdb | 4.4% (7,811) | IGDB critic score, 0..100 |
| `igdb_user_score` | integer | igdb | 10.6% (18,854) | IGDB user score, 0..100 |
| `gamerankings_score` | integer | gamerankings | 3.6% (6,491) | critic score, 0..100 |
| `gg_score` | integer | gamegauntlets | 100.0% (178,494) | Game Gauntlets' own composite score |
| `gg_points` | integer | gamegauntlets | 100.0% (178,494) | Game Gauntlets priority score (wheel weighting) |
| `updated_at` | datetime (ISO 8601) | gamegauntlets | 100.0% (178,495) | last time this row changed |

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
| steam | 1d | 89,110 | 2,821 | 33 | 89,587 | 167,591 | no | 2026-09-25 23:49:19 |
| gog | 7d | 6,973 | 19 | 0 | 6,900 | 171,608 | no | 2026-09-25 03:54:17 |
| wikidata | 30d | 98,613 | 54 | 0 | 98,433 | 84,026 | no | 2026-09-20 04:29:40 |
| igdb | 30d | 103,994 | 40 | 0 | 104,005 | 79,450 | no | 2026-09-25 03:00:03 |
| steamspy | 7d | 80,514 | 33 | 0 | 80,514 | 102,150 | no | 2026-09-25 04:30:42 |
| hltb | 30d | 24,138 | 9,896 | 0 | 34,034 | 146,567 | no | 2026-09-25 06:38:13 |
| gamefaqs | 90d | 17,798 | 555 | 0 | 18,345 | 161,496 | no | 2026-09-25 23:49:13 |
| metacritic | 60d | 109,085 | 14,941 | 0 | 124,022 | 59,542 | no | 2026-09-25 18:11:31 |

## External links

| Site | Linked games |
|---|---|
| gamefaqs | 73,313 |
| gog | 7,174 |
| hltb | 41,388 |
| igdb | 99,882 |
| metacritic | 109,564 |
| mobygames | 38,470 |
| steam | 176,215 |
| wikidata | 94,500 |
| wikipedia_en | 7,116 |
| wikipedia_ru | 3,183 |

## Licence

The dataset is released under the GNU General Public License v3.0 (see `LICENSE` in this repo). Game
names, images, descriptions and prices belong to their respective publishers, platforms and third-party
sources.
