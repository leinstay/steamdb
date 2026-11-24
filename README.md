# Steam Game Database

JSON dump of the [Game Gauntlets](https://gamegauntlets.com) game catalog: prices, scores and metadata
merged from Steam, GOG, SteamSpy, GameFAQs, Metacritic, IGDB, HowLongToBeat, Wikidata and GameRankings.

Updated nightly at 23:48 UTC.

_Generated 2026-11-24T23:50:58.562Z._

## Download

| File | Rows | Size |
|---|---|---|
| [`steamdb.json`](https://github.com/leinstay/steamdb/releases/latest/download/steamdb.json) | 202,021 | 542.0 MB |
| [`steamdb.min.json`](https://github.com/leinstay/steamdb/releases/latest/download/steamdb.min.json) | 202,021 | 367.5 MB |
| [`steamdb.min.json.gz`](https://github.com/leinstay/steamdb/releases/latest/download/steamdb.min.json.gz) | 202,021 | 56.1 MB |

Previous dump: see the [releases page](https://github.com/leinstay/steamdb/releases).

## Schema

"Coverage" is the share of exported games that currently have a value for that key. Any key may be
`null` when the value is unknown.

| Key | Type | Source | Coverage | Description |
|---|---|---|---|---|
| `id` | integer | gamegauntlets | 100.0% (202,021) | catalog id, stable across updates |
| `kind` | string | gamegauntlets | 100.0% (202,021) | 'steam' or 'gog_exclusive' |
| `name` | string | gamegauntlets | 100.0% (202,021) | game title |
| `image` | string | gamegauntlets | 100.0% (201,933) | header image URL |
| `description` | string | gamegauntlets | 99.9% (201,832) | English store description (raw HTML) |
| `steam_appid` | integer | steam | 98.8% (199,577) | Steam appid |
| `steam_url` | string | steam | 98.8% (199,577) | Steam store page URL |
| `gog_id` | integer | gog | 3.5% (7,145) | GOG catalog id |
| `gog_url` | string | gog | 4.0% (8,139) | GOG store page URL |
| `release_date` | date (`YYYY-MM-DD`) | gamegauntlets | 71.3% (144,051) | cross-source consensus release date |
| `release_precision` | string | gamegauntlets | 71.3% (144,051) | day/month/quarter/year/unknown |
| `early_access_date` | date (`YYYY-MM-DD`) | steam | 6.4% (12,902) | date the game entered Early Access, if it did |
| `store_release_date` | date (`YYYY-MM-DD`) | gamegauntlets | 69.4% (140,271) | store listing date (may be a re-listing, not the true release date) |
| `price_usd` | integer | gamegauntlets | 60.9% (122,956) | USD list price, cents |
| `price_final_usd` | integer | gamegauntlets | 60.9% (122,956) | USD price after discount, cents |
| `discount_percent` | integer | gamegauntlets | 59.9% (121,004) | discount percent, 0..100 |
| `platforms` | array of strings | gamegauntlets | 100.0% (202,005) | WIN/MAC/LNX |
| `developers` | array of strings | gamegauntlets | 99.9% (201,910) | developer names |
| `publishers` | array of strings | gamegauntlets | 99.8% (201,663) | publisher names |
| `languages` | array of strings | gamegauntlets | 99.9% (201,772) | interface language names |
| `voiceovers` | array of strings | gamegauntlets | 43.9% (88,688) | voiceover language names |
| `categories` | array of strings | gamegauntlets | 100.0% (201,953) | store category tags |
| `genres` | array of strings | gamegauntlets | 100.0% (201,929) | genre tags |
| `tags` | array of strings | gamegauntlets | 34.9% (70,473) | community tags |
| `achievements` | integer | steam | 39.5% (79,745) | achievement count |
| `steam_reviews_percent` | integer | steam | 61.4% (124,110) | all-time positive review share, 0..100 |
| `steam_reviews_count` | integer | steam | 62.1% (125,517) | all-time review count |
| `steam_reviews_label` | string | steam | 40.4% (81,689) | Steam's own label ("Very Positive", ...), null under 10 votes |
| `steam_recent_percent` | integer | steam | 55.6% (112,355) | last ~30 days positive review share, 0..100 |
| `steam_recent_count` | integer | steam | 55.6% (112,355) | last ~30 days review count |
| `steam_recent_label` | string | steam | 5.1% (10,282) | recent-reviews label, null under 10 votes |
| `steamspy_owners` | integer | steamspy | 46.9% (94,763) | owners estimate, lower bound |
| `average_playtime_hours` | number | gamegauntlets | 35.6% (71,887) | resolved average playtime, decimal hours |
| `average_playtime_source` | string | gamegauntlets | 35.6% (71,887) | which source produced average_playtime_hours |
| `hltb_url` | string | hltb | 25.8% (52,035) | HowLongToBeat page URL |
| `hltb_main_hours` | number | hltb | 15.1% (30,449) | main story hours, decimal |
| `hltb_complete_hours` | number | hltb | 100.0% (202,021) | completionist hours, decimal |
| `gamefaqs_url` | string | gamefaqs | 41.3% (83,515) | GameFAQs product page URL |
| `gamefaqs_difficulty` | string | gamefaqs | 12.5% (25,185) | GameFAQs difficulty label |
| `gamefaqs_rating` | number | gamefaqs | 13.5% (27,283) | GameFAQs rating, 0..5 |
| `metacritic_url` | string | metacritic | 86.1% (173,988) | Metacritic page URL |
| `metacritic_score` | integer | metacritic | 4.5% (9,047) | critic score, 0..100 |
| `metacritic_reviews` | integer | metacritic | 4.2% (8,484) | critic review count |
| `metacritic_user_score` | integer | metacritic | 6.2% (12,468) | user score, 0..100 |
| `igdb_url` | string | igdb | 58.4% (117,989) | IGDB page URL |
| `igdb_score` | integer | igdb | 3.9% (7,798) | IGDB critic score, 0..100 |
| `igdb_user_score` | integer | igdb | 9.3% (18,815) | IGDB user score, 0..100 |
| `gamerankings_score` | integer | gamerankings | 3.2% (6,481) | critic score, 0..100 |
| `gg_score` | integer | gamegauntlets | 100.0% (202,021) | Game Gauntlets' own composite score |
| `gg_points` | integer | gamegauntlets | 100.0% (202,021) | Game Gauntlets priority score (wheel weighting) |
| `updated_at` | datetime (ISO 8601) | gamegauntlets | 100.0% (202,021) | last time this row changed |

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
  "steam_reviews_count": 170783,
  "steam_reviews_label": "Overwhelmingly Positive",
  "steam_recent_percent": 96,
  "steam_recent_count": 650,
  "steam_recent_label": "Overwhelmingly Positive",
  "steamspy_owners": 15000000,
  "average_playtime_hours": 2.3,
  "average_playtime_source": "steamspy",
  "hltb_url": "https://howlongtobeat.com/game/1953",
  "hltb_main_hours": 25.4,
  "hltb_complete_hours": 880,
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
  "updated_at": "2026-11-24T03:00:06Z"
}
```

## License and credits

GNU General Public License v3.0, see [LICENSE](LICENSE). Game names, images, descriptions and prices belong to their respective publishers, platforms and third-party sources.
