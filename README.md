# Steam Game Database

JSON dump of the [Game Gauntlets](https://gamegauntlets.com) game catalog: prices, scores and metadata
merged from Steam, GOG, SteamSpy, GameFAQs, Metacritic, IGDB, HowLongToBeat, Wikidata and GameRankings.

Updated nightly at 23:48 UTC.

_Generated 2026-10-16T23:49:40.807Z._

## Download

| File | Rows | Size |
|---|---|---|
| [`steamdb.json`](https://github.com/leinstay/steamdb/releases/latest/download/steamdb.json) | 193,048 | 517.5 MB |
| [`steamdb.min.json`](https://github.com/leinstay/steamdb/releases/latest/download/steamdb.min.json) | 193,048 | 350.7 MB |
| [`steamdb.min.json.gz`](https://github.com/leinstay/steamdb/releases/latest/download/steamdb.min.json.gz) | 193,048 | 53.6 MB |

Previous dump: see the [releases page](https://github.com/leinstay/steamdb/releases).

## Schema

"Coverage" is the share of exported games that currently have a value for that key. Any key may be
`null` when the value is unknown.

| Key | Type | Source | Coverage | Description |
|---|---|---|---|---|
| `id` | integer | gamegauntlets | 100.0% (193,048) | catalog id, stable across updates |
| `kind` | string | gamegauntlets | 100.0% (193,048) | 'steam' or 'gog_exclusive' |
| `name` | string | gamegauntlets | 100.0% (193,048) | game title |
| `image` | string | gamegauntlets | 100.0% (192,958) | header image URL |
| `description` | string | gamegauntlets | 99.9% (192,900) | English store description (raw HTML) |
| `steam_appid` | integer | steam | 98.8% (190,712) | Steam appid |
| `steam_url` | string | steam | 98.8% (190,712) | Steam store page URL |
| `gog_id` | integer | gog | 3.6% (6,990) | GOG catalog id |
| `gog_url` | string | gog | 3.8% (7,330) | GOG store page URL |
| `release_date` | date (`YYYY-MM-DD`) | gamegauntlets | 71.3% (137,658) | cross-source consensus release date |
| `release_precision` | string | gamegauntlets | 71.3% (137,658) | day/month/quarter/year/unknown |
| `early_access_date` | date (`YYYY-MM-DD`) | steam | 6.3% (12,190) | date the game entered Early Access, if it did |
| `store_release_date` | date (`YYYY-MM-DD`) | gamegauntlets | 69.0% (133,126) | store listing date (may be a re-listing, not the true release date) |
| `price_usd` | integer | gamegauntlets | 60.3% (116,418) | USD list price, cents |
| `price_final_usd` | integer | gamegauntlets | 60.3% (116,418) | USD price after discount, cents |
| `discount_percent` | integer | gamegauntlets | 59.3% (114,460) | discount percent, 0..100 |
| `platforms` | array of strings | gamegauntlets | 100.0% (193,031) | WIN/MAC/LNX |
| `developers` | array of strings | gamegauntlets | 99.9% (192,936) | developer names |
| `publishers` | array of strings | gamegauntlets | 99.8% (192,686) | publisher names |
| `languages` | array of strings | gamegauntlets | 99.9% (192,835) | interface language names |
| `voiceovers` | array of strings | gamegauntlets | 44.4% (85,719) | voiceover language names |
| `categories` | array of strings | gamegauntlets | 100.0% (192,992) | store category tags |
| `genres` | array of strings | gamegauntlets | 100.0% (192,952) | genre tags |
| `tags` | array of strings | gamegauntlets | 36.4% (70,360) | community tags |
| `achievements` | integer | steam | 38.7% (74,689) | achievement count |
| `steam_reviews_percent` | integer | steam | 62.8% (121,191) | all-time positive review share, 0..100 |
| `steam_reviews_count` | integer | steam | 63.4% (122,463) | all-time review count |
| `steam_reviews_label` | string | steam | 41.7% (80,469) | Steam's own label ("Very Positive", ...), null under 10 votes |
| `steam_recent_percent` | integer | steam | 55.0% (106,264) | last ~30 days positive review share, 0..100 |
| `steam_recent_count` | integer | steam | 55.0% (106,264) | last ~30 days review count |
| `steam_recent_label` | string | steam | 5.1% (9,859) | recent-reviews label, null under 10 votes |
| `steamspy_owners` | integer | steamspy | 47.6% (91,975) | owners estimate, lower bound |
| `average_playtime_hours` | number | gamegauntlets | 34.9% (67,299) | resolved average playtime, decimal hours |
| `average_playtime_source` | string | gamegauntlets | 34.9% (67,299) | which source produced average_playtime_hours |
| `hltb_url` | string | hltb | 25.6% (49,512) | HowLongToBeat page URL |
| `hltb_main_hours` | number | hltb | 15.2% (29,408) | main story hours, decimal |
| `hltb_complete_hours` | number | hltb | 100.0% (193,048) | completionist hours, decimal |
| `gamefaqs_url` | string | gamefaqs | 40.9% (78,893) | GameFAQs product page URL |
| `gamefaqs_difficulty` | string | gamefaqs | 11.3% (21,801) | GameFAQs difficulty label |
| `gamefaqs_rating` | number | gamefaqs | 12.3% (23,703) | GameFAQs rating, 0..5 |
| `metacritic_url` | string | metacritic | 87.1% (168,207) | Metacritic page URL |
| `metacritic_score` | integer | metacritic | 4.6% (8,976) | critic score, 0..100 |
| `metacritic_reviews` | integer | metacritic | 4.4% (8,448) | critic review count |
| `metacritic_user_score` | integer | metacritic | 6.4% (12,326) | user score, 0..100 |
| `igdb_url` | string | igdb | 60.3% (116,352) | IGDB page URL |
| `igdb_score` | integer | igdb | 4.0% (7,793) | IGDB critic score, 0..100 |
| `igdb_user_score` | integer | igdb | 9.7% (18,822) | IGDB user score, 0..100 |
| `gamerankings_score` | integer | gamerankings | 3.4% (6,485) | critic score, 0..100 |
| `gg_score` | integer | gamegauntlets | 100.0% (193,048) | Game Gauntlets' own composite score |
| `gg_points` | integer | gamegauntlets | 100.0% (193,048) | Game Gauntlets priority score (wheel weighting) |
| `updated_at` | datetime (ISO 8601) | gamegauntlets | 100.0% (193,048) | last time this row changed |

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
  "price_final_usd": 199,
  "discount_percent": 80,
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
  "steam_recent_percent": 96,
  "steam_recent_count": 664,
  "steam_recent_label": "Overwhelmingly Positive",
  "steamspy_owners": 15000000,
  "average_playtime_hours": 16.4,
  "average_playtime_source": "steam_reviews",
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
  "updated_at": "2026-10-11T03:27:21Z"
}
```

## Licence

The dataset is released under the GNU General Public License v3.0 (see `LICENSE` in this repo). Game
names, images, descriptions and prices belong to their respective publishers, platforms and third-party
sources.
