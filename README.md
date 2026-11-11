# Steam Game Database

JSON dump of the [Game Gauntlets](https://gamegauntlets.com) game catalog: prices, scores and metadata
merged from Steam, GOG, SteamSpy, GameFAQs, Metacritic, IGDB, HowLongToBeat, Wikidata and GameRankings.

Updated nightly at 23:48 UTC.

_Generated 2026-11-11T23:50:59.286Z._

## Download

| File | Rows | Size |
|---|---|---|
| [`steamdb.json`](https://github.com/leinstay/steamdb/releases/latest/download/steamdb.json) | 199,523 | 534.9 MB |
| [`steamdb.min.json`](https://github.com/leinstay/steamdb/releases/latest/download/steamdb.min.json) | 199,523 | 362.6 MB |
| [`steamdb.min.json.gz`](https://github.com/leinstay/steamdb/releases/latest/download/steamdb.min.json.gz) | 199,523 | 55.1 MB |

Previous dump: see the [releases page](https://github.com/leinstay/steamdb/releases).

## Schema

"Coverage" is the share of exported games that currently have a value for that key. Any key may be
`null` when the value is unknown.

| Key | Type | Source | Coverage | Description |
|---|---|---|---|---|
| `id` | integer | gamegauntlets | 100.0% (199,523) | catalog id, stable across updates |
| `kind` | string | gamegauntlets | 100.0% (199,523) | 'steam' or 'gog_exclusive' |
| `name` | string | gamegauntlets | 100.0% (199,523) | game title |
| `image` | string | gamegauntlets | 100.0% (199,435) | header image URL |
| `description` | string | gamegauntlets | 99.9% (199,348) | English store description (raw HTML) |
| `steam_appid` | integer | steam | 98.8% (197,099) | Steam appid |
| `steam_url` | string | steam | 98.8% (197,099) | Steam store page URL |
| `gog_id` | integer | gog | 3.6% (7,111) | GOG catalog id |
| `gog_url` | string | gog | 3.7% (7,472) | GOG store page URL |
| `release_date` | date (`YYYY-MM-DD`) | gamegauntlets | 71.0% (141,605) | cross-source consensus release date |
| `release_precision` | string | gamegauntlets | 71.0% (141,605) | day/month/quarter/year/unknown |
| `early_access_date` | date (`YYYY-MM-DD`) | steam | 6.3% (12,612) | date the game entered Early Access, if it did |
| `store_release_date` | date (`YYYY-MM-DD`) | gamegauntlets | 68.9% (137,529) | store listing date (may be a re-listing, not the true release date) |
| `price_usd` | integer | gamegauntlets | 60.4% (120,424) | USD list price, cents |
| `price_final_usd` | integer | gamegauntlets | 60.4% (120,424) | USD price after discount, cents |
| `discount_percent` | integer | gamegauntlets | 59.4% (118,470) | discount percent, 0..100 |
| `platforms` | array of strings | gamegauntlets | 100.0% (199,508) | WIN/MAC/LNX |
| `developers` | array of strings | gamegauntlets | 99.9% (199,412) | developer names |
| `publishers` | array of strings | gamegauntlets | 99.8% (199,163) | publisher names |
| `languages` | array of strings | gamegauntlets | 99.9% (199,282) | interface language names |
| `voiceovers` | array of strings | gamegauntlets | 44.1% (87,904) | voiceover language names |
| `categories` | array of strings | gamegauntlets | 100.0% (199,455) | store category tags |
| `genres` | array of strings | gamegauntlets | 100.0% (199,430) | genre tags |
| `tags` | array of strings | gamegauntlets | 35.3% (70,466) | community tags |
| `achievements` | integer | steam | 38.9% (77,697) | achievement count |
| `steam_reviews_percent` | integer | steam | 61.1% (121,813) | all-time positive review share, 0..100 |
| `steam_reviews_count` | integer | steam | 61.8% (123,276) | all-time review count |
| `steam_reviews_label` | string | steam | 40.5% (80,781) | Steam's own label ("Very Positive", ...), null under 10 votes |
| `steam_recent_percent` | integer | steam | 55.2% (110,090) | last ~30 days positive review share, 0..100 |
| `steam_recent_count` | integer | steam | 55.2% (110,090) | last ~30 days review count |
| `steam_recent_label` | string | steam | 5.2% (10,332) | recent-reviews label, null under 10 votes |
| `steamspy_owners` | integer | steamspy | 46.1% (91,983) | owners estimate, lower bound |
| `average_playtime_hours` | number | gamegauntlets | 35.1% (69,979) | resolved average playtime, decimal hours |
| `average_playtime_source` | string | gamegauntlets | 35.1% (69,979) | which source produced average_playtime_hours |
| `hltb_url` | string | hltb | 25.9% (51,760) | HowLongToBeat page URL |
| `hltb_main_hours` | number | hltb | 15.2% (30,318) | main story hours, decimal |
| `hltb_complete_hours` | number | hltb | 100.0% (199,523) | completionist hours, decimal |
| `gamefaqs_url` | string | gamefaqs | 40.0% (79,853) | GameFAQs product page URL |
| `gamefaqs_difficulty` | string | gamefaqs | 11.9% (23,796) | GameFAQs difficulty label |
| `gamefaqs_rating` | number | gamefaqs | 13.0% (25,844) | GameFAQs rating, 0..5 |
| `metacritic_url` | string | metacritic | 86.4% (172,340) | Metacritic page URL |
| `metacritic_score` | integer | metacritic | 4.5% (9,020) | critic score, 0..100 |
| `metacritic_reviews` | integer | metacritic | 4.3% (8,480) | critic review count |
| `metacritic_user_score` | integer | metacritic | 6.2% (12,356) | user score, 0..100 |
| `igdb_url` | string | igdb | 58.4% (116,526) | IGDB page URL |
| `igdb_score` | integer | igdb | 3.9% (7,797) | IGDB critic score, 0..100 |
| `igdb_user_score` | integer | igdb | 9.4% (18,822) | IGDB user score, 0..100 |
| `gamerankings_score` | integer | gamerankings | 3.2% (6,483) | critic score, 0..100 |
| `gg_score` | integer | gamegauntlets | 100.0% (199,523) | Game Gauntlets' own composite score |
| `gg_points` | integer | gamegauntlets | 100.0% (199,523) | Game Gauntlets priority score (wheel weighting) |
| `updated_at` | datetime (ISO 8601) | gamegauntlets | 100.0% (199,523) | last time this row changed |

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
  "steam_reviews_count": 170598,
  "steam_reviews_label": "Overwhelmingly Positive",
  "steam_recent_percent": 96,
  "steam_recent_count": 750,
  "steam_recent_label": "Overwhelmingly Positive",
  "steamspy_owners": 15000000,
  "average_playtime_hours": 3.8,
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
  "updated_at": "2026-11-11T03:00:06Z"
}
```

## License and credits

GNU General Public License v3.0, see [LICENSE](LICENSE). Game names, images, descriptions and prices belong to their respective publishers, platforms and third-party sources.
