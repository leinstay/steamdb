# Steam Game Database

JSON dump of the [Game Gauntlets](https://gamegauntlets.com) game catalog: prices, scores and metadata
merged from Steam, GOG, SteamSpy, GameFAQs, Metacritic, IGDB, HowLongToBeat, Wikidata and GameRankings.

Updated nightly at 23:48 UTC.

_Generated 2026-09-21T23:50:23.958Z._

## Files

| File | Rows | Size |
|---|---|---|
| `steamdb.json` | 128,817 | 449.2 MB |
| `steamdb.min.json` | 128,817 | 336.5 MB |
| `steamdb.min.json.gz` | 128,817 | 78.4 MB |

## Catalog totals

| Metric | Count |
|---|---|
| Games in the catalog | 128,818 |
| Steam games | 126,562 |
| GOG-exclusive games | 2,256 |
| Steam games also on GOG | 4,601 |

## Schema

"Coverage" is the share of exported games that currently have a value for that key. Any key may be
`null` when the value is unknown.

| Key | Type | Source | Coverage | Description |
|---|---|---|---|---|
| `id` | integer | gamegauntlets | 100.0% (128,818) | catalog id, stable across updates |
| `kind` | string | gamegauntlets | 100.0% (128,818) | 'steam' or 'gog_exclusive' |
| `name` | string | gamegauntlets | 100.0% (128,818) | game title |
| `image` | string | gamegauntlets | 100.0% (128,814) | header image URL |
| `description` | string | gamegauntlets | 99.9% (128,745) | English store description (raw HTML) |
| `steam_appid` | integer | steam | 98.2% (126,562) | Steam appid |
| `steam_url` | string | steam | 98.2% (126,562) | Steam store page URL |
| `gog_id` | integer | gog | 5.3% (6,857) | GOG catalog id |
| `gog_url` | string | gog | 5.5% (7,120) | GOG store page URL |
| `release_date` | date (`YYYY-MM-DD`) | gamegauntlets | 88.4% (113,848) | cross-source consensus release date |
| `release_precision` | string | gamegauntlets | 88.4% (113,848) | day/month/quarter/year/unknown |
| `early_access_date` | date (`YYYY-MM-DD`) | steam | 1.1% (1,433) | date the game entered Early Access, if it did |
| `store_release_date` | date (`YYYY-MM-DD`) | gamegauntlets | 88.3% (113,732) | store listing date (may be a re-listing, not the true release date) |
| `price_usd` | integer | gamegauntlets | 76.9% (99,045) | USD list price, cents |
| `price_final_usd` | integer | gamegauntlets | 76.9% (99,045) | USD price after discount, cents |
| `discount_percent` | integer | gamegauntlets | 30.8% (39,709) | discount percent, 0..100 |
| `platforms` | array of strings | gamegauntlets | 100.0% (128,806) | WIN/MAC/LNX |
| `developers` | array of strings | gamegauntlets | 100.0% (128,772) | developer names |
| `publishers` | array of strings | gamegauntlets | 99.9% (128,628) | publisher names |
| `languages` | array of strings | gamegauntlets | 99.9% (128,647) | interface language names |
| `voiceovers` | array of strings | gamegauntlets | 43.2% (55,610) | voiceover language names |
| `categories` | array of strings | gamegauntlets | 99.9% (128,722) | store category tags |
| `genres` | array of strings | gamegauntlets | 100.0% (128,793) | genre tags |
| `tags` | array of strings | gamegauntlets | 54.6% (70,367) | community tags |
| `achievements` | integer | steam | 46.4% (59,714) | achievement count |
| `steam_reviews_percent` | integer | steam | 65.1% (83,810) | all-time positive review share, 0..100 |
| `steam_reviews_count` | integer | steam | 62.8% (80,934) | all-time review count |
| `steam_reviews_label` | string | steam | 42.1% (54,175) | Steam's own label ("Very Positive", ...), null under 10 votes |
| `steam_recent_percent` | integer | steam | 9.2% (11,789) | last ~30 days positive review share, 0..100 |
| `steam_recent_count` | integer | steam | 9.2% (11,789) | last ~30 days review count |
| `steam_recent_label` | string | steam | 1.2% (1,557) | recent-reviews label, null under 10 votes |
| `steamspy_owners` | integer | steamspy | 71.5% (92,050) | owners estimate, lower bound |
| `average_playtime_hours` | number | gamegauntlets | 5.7% (7,343) | resolved average playtime, decimal hours |
| `average_playtime_source` | string | gamegauntlets | 5.7% (7,343) | which source produced average_playtime_hours |
| `hltb_url` | string | hltb | 31.5% (40,552) | HowLongToBeat page URL |
| `hltb_main_hours` | number | hltb | 17.8% (22,916) | main story hours, decimal |
| `hltb_complete_hours` | number | hltb | 100.0% (128,818) | completionist hours, decimal |
| `gamefaqs_url` | string | gamefaqs | 56.8% (73,149) | GameFAQs product page URL |
| `gamefaqs_difficulty` | string | gamefaqs | 15.0% (19,334) | GameFAQs difficulty label |
| `gamefaqs_rating` | number | gamefaqs | 16.4% (21,126) | GameFAQs rating, 0..5 |
| `metacritic_url` | string | metacritic | 44.0% (56,622) | Metacritic page URL |
| `metacritic_score` | integer | metacritic | 5.9% (7,621) | critic score, 0..100 |
| `metacritic_reviews` | integer | metacritic | 5.5% (7,078) | critic review count |
| `metacritic_user_score` | integer | metacritic | 8.2% (10,598) | user score, 0..100 |
| `igdb_url` | string | igdb | 77.4% (99,676) | IGDB page URL |
| `igdb_score` | integer | igdb | 6.1% (7,809) | IGDB critic score, 0..100 |
| `igdb_user_score` | integer | igdb | 14.6% (18,856) | IGDB user score, 0..100 |
| `gamerankings_score` | integer | gamerankings | 5.0% (6,491) | critic score, 0..100 |
| `gg_score` | integer | gamegauntlets | 100.0% (128,818) | Game Gauntlets' own composite score |
| `gg_points` | integer | gamegauntlets | 100.0% (128,818) | Game Gauntlets priority score (wheel weighting) |
| `updated_at` | datetime (ISO 8601) | gamegauntlets | 100.0% (128,818) | last time this row changed |

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
| steam | 1d | 39,920 | 391 | 33 | 39,924 | 118,120 | no | 2026-09-21 23:49:05 |
| gog | 7d | 6,941 | 18 | 0 | 6,837 | 121,993 | no | 2026-09-21 03:04:06 |
| wikidata | 30d | 98,614 | 53 | 0 | 98,434 | 34,351 | no | 2026-09-20 04:29:40 |
| igdb | 30d | 103,977 | 39 | 0 | 103,988 | 29,800 | no | 2026-09-21 03:00:03 |
| steamspy | 7d | 80,510 | 33 | 0 | 80,510 | 52,495 | no | 2026-09-21 04:30:43 |
| hltb | 30d | 14,238 | 58 | 0 | 14,294 | 115,596 | no | 2026-09-21 06:26:23 |
| gamefaqs | 90d | 16,520 | 955 | 0 | 17,471 | 112,659 | yes | 2026-09-21 17:37:00 |
| metacritic | 60d | 52,533 | 6,684 | 0 | 59,214 | 73,011 | no | 2026-09-21 18:54:05 |

## External links

| Site | Linked games |
|---|---|
| gamefaqs | 73,149 |
| gog | 7,120 |
| hltb | 40,552 |
| igdb | 99,860 |
| metacritic | 56,622 |
| mobygames | 38,464 |
| steam | 126,583 |
| wikidata | 94,500 |
| wikipedia_en | 7,112 |
| wikipedia_ru | 3,181 |

## Licence

The dataset is released under the GNU General Public License v3.0 (see `LICENSE` in this repo). Game
names, images, descriptions and prices belong to their respective publishers, platforms and third-party
sources.
