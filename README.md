# Steam Game Database

JSON dump of the [Game Gauntlets](https://gamegauntlets.com) game catalog: prices, scores and metadata
merged from Steam, GOG, SteamSpy, GameFAQs, Metacritic, IGDB, HowLongToBeat, Wikidata and GameRankings.

Updated nightly at 23:48 UTC.

_Generated 2026-09-22T23:50:15.219Z._

## Files

| File | Rows | Size |
|---|---|---|
| `steamdb.json` | 143,161 | 485.6 MB |
| `steamdb.min.json` | 143,161 | 361.4 MB |
| `steamdb.min.json.gz` | 143,161 | 82.2 MB |

## Catalog totals

| Metric | Count |
|---|---|
| Games in the catalog | 143,162 |
| Steam games | 140,899 |
| GOG-exclusive games | 2,263 |
| Steam games also on GOG | 4,613 |

## Schema

"Coverage" is the share of exported games that currently have a value for that key. Any key may be
`null` when the value is unknown.

| Key | Type | Source | Coverage | Description |
|---|---|---|---|---|
| `id` | integer | gamegauntlets | 100.0% (143,162) | catalog id, stable across updates |
| `kind` | string | gamegauntlets | 100.0% (143,162) | 'steam' or 'gog_exclusive' |
| `name` | string | gamegauntlets | 100.0% (143,162) | game title |
| `image` | string | gamegauntlets | 100.0% (143,157) | header image URL |
| `description` | string | gamegauntlets | 99.9% (143,084) | English store description (raw HTML) |
| `steam_appid` | integer | steam | 98.4% (140,899) | Steam appid |
| `steam_url` | string | steam | 98.4% (140,899) | Steam store page URL |
| `gog_id` | integer | gog | 4.8% (6,876) | GOG catalog id |
| `gog_url` | string | gog | 5.0% (7,135) | GOG store page URL |
| `release_date` | date (`YYYY-MM-DD`) | gamegauntlets | 84.1% (120,440) | cross-source consensus release date |
| `release_precision` | string | gamegauntlets | 84.1% (120,440) | day/month/quarter/year/unknown |
| `early_access_date` | date (`YYYY-MM-DD`) | steam | 1.5% (2,159) | date the game entered Early Access, if it did |
| `store_release_date` | date (`YYYY-MM-DD`) | gamegauntlets | 84.0% (120,322) | store listing date (may be a re-listing, not the true release date) |
| `price_usd` | integer | gamegauntlets | 73.1% (104,695) | USD list price, cents |
| `price_final_usd` | integer | gamegauntlets | 73.1% (104,695) | USD price after discount, cents |
| `discount_percent` | integer | gamegauntlets | 31.7% (45,370) | discount percent, 0..100 |
| `platforms` | array of strings | gamegauntlets | 100.0% (143,147) | WIN/MAC/LNX |
| `developers` | array of strings | gamegauntlets | 100.0% (143,111) | developer names |
| `publishers` | array of strings | gamegauntlets | 99.9% (142,950) | publisher names |
| `languages` | array of strings | gamegauntlets | 99.9% (142,989) | interface language names |
| `voiceovers` | array of strings | gamegauntlets | 43.0% (61,561) | voiceover language names |
| `categories` | array of strings | gamegauntlets | 99.9% (143,065) | store category tags |
| `genres` | array of strings | gamegauntlets | 100.0% (143,134) | genre tags |
| `tags` | array of strings | gamegauntlets | 49.2% (70,374) | community tags |
| `achievements` | integer | steam | 44.3% (63,391) | achievement count |
| `steam_reviews_percent` | integer | steam | 62.3% (89,128) | all-time positive review share, 0..100 |
| `steam_reviews_count` | integer | steam | 60.4% (86,494) | all-time review count |
| `steam_reviews_label` | string | steam | 39.5% (56,596) | Steam's own label ("Very Positive", ...), null under 10 votes |
| `steam_recent_percent` | integer | steam | 11.7% (16,737) | last ~30 days positive review share, 0..100 |
| `steam_recent_count` | integer | steam | 11.7% (16,737) | last ~30 days review count |
| `steam_recent_label` | string | steam | 1.5% (2,200) | recent-reviews label, null under 10 votes |
| `steamspy_owners` | integer | steamspy | 64.3% (92,046) | owners estimate, lower bound |
| `average_playtime_hours` | number | gamegauntlets | 6.7% (9,576) | resolved average playtime, decimal hours |
| `average_playtime_source` | string | gamegauntlets | 6.7% (9,576) | which source produced average_playtime_hours |
| `hltb_url` | string | hltb | 28.4% (40,677) | HowLongToBeat page URL |
| `hltb_main_hours` | number | hltb | 16.2% (23,160) | main story hours, decimal |
| `hltb_complete_hours` | number | hltb | 100.0% (143,161) | completionist hours, decimal |
| `gamefaqs_url` | string | gamefaqs | 51.1% (73,173) | GameFAQs product page URL |
| `gamefaqs_difficulty` | string | gamefaqs | 13.6% (19,457) | GameFAQs difficulty label |
| `gamefaqs_rating` | number | gamefaqs | 14.8% (21,245) | GameFAQs rating, 0..5 |
| `metacritic_url` | string | metacritic | 48.2% (69,044) | Metacritic page URL |
| `metacritic_score` | integer | metacritic | 5.4% (7,669) | critic score, 0..100 |
| `metacritic_reviews` | integer | metacritic | 5.0% (7,131) | critic review count |
| `metacritic_user_score` | integer | metacritic | 7.5% (10,697) | user score, 0..100 |
| `igdb_url` | string | igdb | 69.6% (99,682) | IGDB page URL |
| `igdb_score` | integer | igdb | 5.5% (7,808) | IGDB critic score, 0..100 |
| `igdb_user_score` | integer | igdb | 13.2% (18,854) | IGDB user score, 0..100 |
| `gamerankings_score` | integer | gamerankings | 4.5% (6,490) | critic score, 0..100 |
| `gg_score` | integer | gamegauntlets | 100.0% (143,161) | Game Gauntlets' own composite score |
| `gg_points` | integer | gamegauntlets | 100.0% (143,161) | Game Gauntlets priority score (wheel weighting) |
| `updated_at` | datetime (ISO 8601) | gamegauntlets | 100.0% (143,162) | last time this row changed |

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
| steam | 1d | 54,272 | 410 | 33 | 54,277 | 128,834 | no | 2026-09-22 23:49:08 |
| gog | 7d | 6,942 | 18 | 0 | 6,857 | 136,319 | no | 2026-09-22 03:36:25 |
| wikidata | 30d | 98,613 | 54 | 0 | 98,433 | 48,700 | no | 2026-09-20 04:29:40 |
| igdb | 30d | 103,986 | 40 | 0 | 103,997 | 44,139 | no | 2026-09-22 03:00:22 |
| steamspy | 7d | 80,510 | 33 | 0 | 80,510 | 66,844 | no | 2026-09-22 04:30:41 |
| hltb | 30d | 18,081 | 0 | 0 | 18,081 | 126,356 | no | 2026-09-22 17:22:12 |
| gamefaqs | 90d | 17,041 | 36 | 0 | 17,076 | 127,340 | no | 2026-09-22 22:33:21 |
| metacritic | 60d | 69,253 | 238 | 0 | 69,487 | 77,654 | no | 2026-09-22 19:00:18 |

## External links

| Site | Linked games |
|---|---|
| gamefaqs | 73,173 |
| gog | 7,135 |
| hltb | 40,677 |
| igdb | 99,866 |
| metacritic | 69,044 |
| mobygames | 38,460 |
| steam | 140,918 |
| wikidata | 94,496 |
| wikipedia_en | 7,110 |
| wikipedia_ru | 3,180 |

## Licence

The dataset is released under the GNU General Public License v3.0 (see `LICENSE` in this repo). Game
names, images, descriptions and prices belong to their respective publishers, platforms and third-party
sources.
