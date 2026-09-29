# Steam Game Database

JSON dump of the [Game Gauntlets](https://gamegauntlets.com) game catalog: prices, scores and metadata
merged from Steam, GOG, SteamSpy, GameFAQs, Metacritic, IGDB, HowLongToBeat, Wikidata and GameRankings.

Updated nightly at 23:48 UTC.

_Generated 2026-09-29T23:49:41.289Z._

## Download

| File | Rows | Size |
|---|---|---|
| [`steamdb.json`](https://github.com/leinstay/steamdb/releases/latest/download/steamdb.json) | 188,796 | 560.2 MB |
| [`steamdb.min.json`](https://github.com/leinstay/steamdb/releases/latest/download/steamdb.min.json) | 188,796 | 399.4 MB |
| [`steamdb.min.json.gz`](https://github.com/leinstay/steamdb/releases/latest/download/steamdb.min.json.gz) | 188,796 | 76.7 MB |

Previous dump: see the [releases page](https://github.com/leinstay/steamdb/releases).

## Schema

"Coverage" is the share of exported games that currently have a value for that key. Any key may be
`null` when the value is unknown.

| Key | Type | Source | Coverage | Description |
|---|---|---|---|---|
| `id` | integer | gamegauntlets | 100.0% (188,796) | catalog id, stable across updates |
| `kind` | string | gamegauntlets | 100.0% (188,796) | 'steam' or 'gog_exclusive' |
| `name` | string | gamegauntlets | 100.0% (188,796) | game title |
| `image` | string | gamegauntlets | 100.0% (188,704) | header image URL |
| `description` | string | gamegauntlets | 99.9% (188,642) | English store description (raw HTML) |
| `steam_appid` | integer | steam | 98.8% (186,497) | Steam appid |
| `steam_url` | string | steam | 98.8% (186,497) | Steam store page URL |
| `gog_id` | integer | gog | 3.7% (6,929) | GOG catalog id |
| `gog_url` | string | gog | 3.8% (7,250) | GOG store page URL |
| `release_date` | date (`YYYY-MM-DD`) | gamegauntlets | 72.1% (136,215) | cross-source consensus release date |
| `release_precision` | string | gamegauntlets | 72.1% (136,215) | day/month/quarter/year/unknown |
| `early_access_date` | date (`YYYY-MM-DD`) | steam | 3.7% (7,062) | date the game entered Early Access, if it did |
| `store_release_date` | date (`YYYY-MM-DD`) | gamegauntlets | 69.7% (131,658) | store listing date (may be a re-listing, not the true release date) |
| `price_usd` | integer | gamegauntlets | 60.8% (114,854) | USD list price, cents |
| `price_final_usd` | integer | gamegauntlets | 60.8% (114,854) | USD price after discount, cents |
| `discount_percent` | integer | gamegauntlets | 42.7% (80,707) | discount percent, 0..100 |
| `platforms` | array of strings | gamegauntlets | 100.0% (188,778) | WIN/MAC/LNX |
| `developers` | array of strings | gamegauntlets | 99.9% (188,682) | developer names |
| `publishers` | array of strings | gamegauntlets | 99.8% (188,415) | publisher names |
| `languages` | array of strings | gamegauntlets | 99.9% (188,580) | interface language names |
| `voiceovers` | array of strings | gamegauntlets | 44.4% (83,902) | voiceover language names |
| `categories` | array of strings | gamegauntlets | 100.0% (188,706) | store category tags |
| `genres` | array of strings | gamegauntlets | 99.9% (188,699) | genre tags |
| `tags` | array of strings | gamegauntlets | 37.3% (70,458) | community tags |
| `achievements` | integer | steam | 37.9% (71,605) | achievement count |
| `steam_reviews_percent` | integer | steam | 60.1% (113,462) | all-time positive review share, 0..100 |
| `steam_reviews_count` | integer | steam | 59.5% (112,250) | all-time review count |
| `steam_reviews_label` | string | steam | 38.5% (72,675) | Steam's own label ("Very Positive", ...), null under 10 votes |
| `steam_recent_percent` | integer | steam | 30.0% (56,612) | last ~30 days positive review share, 0..100 |
| `steam_recent_count` | integer | steam | 30.0% (56,612) | last ~30 days review count |
| `steam_recent_label` | string | steam | 3.0% (5,624) | recent-reviews label, null under 10 votes |
| `steamspy_owners` | integer | steamspy | 48.8% (92,149) | owners estimate, lower bound |
| `average_playtime_hours` | number | gamegauntlets | 16.1% (30,305) | resolved average playtime, decimal hours |
| `average_playtime_source` | string | gamegauntlets | 16.1% (30,305) | which source produced average_playtime_hours |
| `hltb_url` | string | hltb | 22.7% (42,818) | HowLongToBeat page URL |
| `hltb_main_hours` | number | hltb | 13.1% (24,737) | main story hours, decimal |
| `hltb_complete_hours` | number | hltb | 100.0% (188,796) | completionist hours, decimal |
| `gamefaqs_url` | string | gamefaqs | 38.9% (73,502) | GameFAQs product page URL |
| `gamefaqs_difficulty` | string | gamefaqs | 10.4% (19,670) | GameFAQs difficulty label |
| `gamefaqs_rating` | number | gamefaqs | 11.4% (21,468) | GameFAQs rating, 0..5 |
| `metacritic_url` | string | metacritic | 87.3% (164,790) | Metacritic page URL |
| `metacritic_score` | integer | metacritic | 4.7% (8,902) | critic score, 0..100 |
| `metacritic_reviews` | integer | metacritic | 4.5% (8,445) | critic review count |
| `metacritic_user_score` | integer | metacritic | 6.5% (12,319) | user score, 0..100 |
| `igdb_url` | string | igdb | 61.6% (116,373) | IGDB page URL |
| `igdb_score` | integer | igdb | 4.1% (7,820) | IGDB critic score, 0..100 |
| `igdb_user_score` | integer | igdb | 10.0% (18,888) | IGDB user score, 0..100 |
| `gamerankings_score` | integer | gamerankings | 3.4% (6,504) | critic score, 0..100 |
| `gg_score` | integer | gamegauntlets | 100.0% (188,796) | Game Gauntlets' own composite score |
| `gg_points` | integer | gamegauntlets | 100.0% (188,796) | Game Gauntlets priority score (wheel weighting) |
| `updated_at` | datetime (ISO 8601) | gamegauntlets | 100.0% (188,796) | last time this row changed |

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

## Licence

The dataset is released under the GNU General Public License v3.0 (see `LICENSE` in this repo). Game
names, images, descriptions and prices belong to their respective publishers, platforms and third-party
sources.
