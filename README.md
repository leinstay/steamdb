# Steam Game Database

JSON dump of the [Game Gauntlets](https://gamegauntlets.com) game catalog: prices, scores and metadata
merged from Steam, GOG, SteamSpy, GameFAQs, Metacritic, IGDB, HowLongToBeat, Wikidata and GameRankings.

Updated nightly at 23:48 UTC.

_Generated 2026-09-27T23:50:41.495Z._

## Files

| File | Rows | Size |
|---|---|---|
| `steamdb.json` | 188,869 | 586.1 MB |
| `steamdb.min.json` | 188,869 | 425.9 MB |
| `steamdb.min.json.gz` | 188,869 | 87.6 MB |

## Catalog totals

| Metric | Count |
|---|---|
| Games in the catalog | 188,869 |
| Steam games | 186,574 |
| GOG-exclusive games | 2,295 |
| Steam games also on GOG | 4,628 |

## Schema

"Coverage" is the share of exported games that currently have a value for that key. Any key may be
`null` when the value is unknown.

| Key | Type | Source | Coverage | Description |
|---|---|---|---|---|
| `id` | integer | gamegauntlets | 100.0% (188,869) | catalog id, stable across updates |
| `kind` | string | gamegauntlets | 100.0% (188,869) | 'steam' or 'gog_exclusive' |
| `name` | string | gamegauntlets | 100.0% (188,869) | game title |
| `image` | string | gamegauntlets | 100.0% (188,777) | header image URL |
| `description` | string | gamegauntlets | 99.9% (188,717) | English store description (raw HTML) |
| `steam_appid` | integer | steam | 98.8% (186,574) | Steam appid |
| `steam_url` | string | steam | 98.8% (186,574) | Steam store page URL |
| `gog_id` | integer | gog | 3.7% (6,923) | GOG catalog id |
| `gog_url` | string | gog | 3.8% (7,247) | GOG store page URL |
| `release_date` | date (`YYYY-MM-DD`) | gamegauntlets | 71.7% (135,500) | cross-source consensus release date |
| `release_precision` | string | gamegauntlets | 71.7% (135,500) | day/month/quarter/year/unknown |
| `early_access_date` | date (`YYYY-MM-DD`) | steam | 2.6% (4,823) | date the game entered Early Access, if it did |
| `store_release_date` | date (`YYYY-MM-DD`) | gamegauntlets | 69.9% (131,947) | store listing date (may be a re-listing, not the true release date) |
| `price_usd` | integer | gamegauntlets | 60.9% (114,994) | USD list price, cents |
| `price_final_usd` | integer | gamegauntlets | 60.9% (114,994) | USD price after discount, cents |
| `discount_percent` | integer | gamegauntlets | 34.5% (65,254) | discount percent, 0..100 |
| `platforms` | array of strings | gamegauntlets | 100.0% (188,851) | WIN/MAC/LNX |
| `developers` | array of strings | gamegauntlets | 99.9% (188,756) | developer names |
| `publishers` | array of strings | gamegauntlets | 99.8% (188,489) | publisher names |
| `languages` | array of strings | gamegauntlets | 99.9% (188,651) | interface language names |
| `voiceovers` | array of strings | gamegauntlets | 44.4% (83,890) | voiceover language names |
| `categories` | array of strings | gamegauntlets | 99.9% (188,773) | store category tags |
| `genres` | array of strings | gamegauntlets | 99.9% (188,772) | genre tags |
| `tags` | array of strings | gamegauntlets | 37.4% (70,655) | community tags |
| `achievements` | integer | steam | 37.6% (70,965) | achievement count |
| `steam_reviews_percent` | integer | steam | 56.4% (106,540) | all-time positive review share, 0..100 |
| `steam_reviews_count` | integer | steam | 55.4% (104,562) | all-time review count |
| `steam_reviews_label` | string | steam | 35.5% (67,001) | Steam's own label ("Very Positive", ...), null under 10 votes |
| `steam_recent_percent` | integer | steam | 19.4% (36,714) | last ~30 days positive review share, 0..100 |
| `steam_recent_count` | integer | steam | 19.4% (36,714) | last ~30 days review count |
| `steam_recent_label` | string | steam | 2.3% (4,251) | recent-reviews label, null under 10 votes |
| `steamspy_owners` | integer | steamspy | 48.9% (92,441) | owners estimate, lower bound |
| `average_playtime_hours` | number | gamegauntlets | 10.2% (19,339) | resolved average playtime, decimal hours |
| `average_playtime_source` | string | gamegauntlets | 10.2% (19,339) | which source produced average_playtime_hours |
| `hltb_url` | string | hltb | 22.5% (42,537) | HowLongToBeat page URL |
| `hltb_main_hours` | number | hltb | 12.9% (24,377) | main story hours, decimal |
| `hltb_complete_hours` | number | hltb | 100.0% (188,869) | completionist hours, decimal |
| `gamefaqs_url` | string | gamefaqs | 39.0% (73,744) | GameFAQs product page URL |
| `gamefaqs_difficulty` | string | gamefaqs | 10.5% (19,749) | GameFAQs difficulty label |
| `gamefaqs_rating` | number | gamefaqs | 11.4% (21,556) | GameFAQs rating, 0..5 |
| `metacritic_url` | string | metacritic | 72.4% (136,794) | Metacritic page URL |
| `metacritic_score` | integer | metacritic | 4.7% (8,837) | critic score, 0..100 |
| `metacritic_reviews` | integer | metacritic | 4.4% (8,387) | critic review count |
| `metacritic_user_score` | integer | metacritic | 6.5% (12,227) | user score, 0..100 |
| `igdb_url` | string | igdb | 61.8% (116,659) | IGDB page URL |
| `igdb_score` | integer | igdb | 4.2% (7,874) | IGDB critic score, 0..100 |
| `igdb_user_score` | integer | igdb | 10.0% (18,932) | IGDB user score, 0..100 |
| `gamerankings_score` | integer | gamerankings | 3.4% (6,498) | critic score, 0..100 |
| `gg_score` | integer | gamegauntlets | 100.0% (188,869) | Game Gauntlets' own composite score |
| `gg_points` | integer | gamegauntlets | 100.0% (188,869) | Game Gauntlets priority score (wheel weighting) |
| `updated_at` | datetime (ISO 8601) | gamegauntlets | 100.0% (188,869) | last time this row changed |

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
    "Valve",
    "Valve Corporation"
  ],
  "publishers": [
    "Valve",
    "Valve Corporation",
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
  "updated_at": "2026-09-27T03:22:37Z"
}
```

## Source status

"Remaining" is games with no data from that source yet, or whose last fetch is older than the source's own refresh interval.

| Source | Refresh | OK | Not found | Error | Games covered | Remaining | Paused | Last run |
|---|---|---|---|---|---|---|---|---|
| steam | 1d | 112,107 | 5,995 | 33 | 114,672 | 176,936 | no | 2026-09-27 23:49:16 |
| gog | 7d | 6,979 | 19 | 0 | 6,906 | 184,772 | no | 2026-09-27 03:04:07 |
| wikidata | 30d | 120,070 | 53 | 0 | 119,872 | 72,659 | no | 2026-09-27 03:22:56 |
| igdb | 30d | 104,001 | 40 | 0 | 104,012 | 89,511 | no | 2026-09-27 03:00:04 |
| steamspy | 7d | 80,619 | 32 | 0 | 80,619 | 112,251 | no | 2026-09-27 04:30:53 |
| hltb | 30d | 30,862 | 17,431 | 0 | 48,293 | 143,691 | no | 2026-09-27 06:39:28 |
| gamefaqs | 90d | 17,814 | 621 | 0 | 18,425 | 171,701 | no | 2026-09-27 23:48:40 |
| metacritic | 60d | 136,489 | 21,698 | 0 | 158,182 | 35,602 | no | 2026-09-27 17:43:05 |

## External links

| Site | Linked games |
|---|---|
| gamefaqs | 73,744 |
| gog | 7,247 |
| hltb | 42,537 |
| igdb | 116,843 |
| metacritic | 136,794 |
| mobygames | 40,328 |
| steam | 186,574 |
| wikidata | 116,237 |
| wikipedia_en | 7,425 |
| wikipedia_ru | 3,295 |

## Licence

The dataset is released under the GNU General Public License v3.0 (see `LICENSE` in this repo). Game
names, images, descriptions and prices belong to their respective publishers, platforms and third-party
sources.
