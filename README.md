# Steam Game Database

JSON dump of the [Game Gauntlets](https://gamegauntlets.com) game catalog: prices, scores and metadata
merged from Steam, GOG, SteamSpy, GameFAQs, Metacritic, IGDB, HowLongToBeat, Wikidata and GameRankings.

Updated nightly at 23:48 UTC.

_Generated 2026-09-19T22:27:52.871Z._

## Files

| File | Rows | Size |
|---|---|---|
| `steamdb.json` | 116,228 | 429.7 MB |
| `steamdb.min.json` | 116,228 | 326.8 MB |
| `steamdb.min.json.gz` | 116,228 | 80.7 MB |

## Catalog totals

| Metric | Count |
|---|---|
| Games in the catalog | 116,229 |
| Steam games | 113,973 |
| GOG-exclusive games | 2,256 |
| Steam games also on GOG | 4,605 |

## Schema

"Coverage" is the share of exported games that currently have a value for that key. Any key may be
`null` when the value is unknown.

| Key | Type | Source | Coverage | Description |
|---|---|---|---|---|
| `id` | integer | gamegauntlets | 100.0% (116,229) | catalog id, stable across updates |
| `kind` | string | gamegauntlets | 100.0% (116,229) | 'steam' or 'gog_exclusive' |
| `name` | string | gamegauntlets | 100.0% (116,229) | game title |
| `image` | string | gamegauntlets | 100.0% (116,222) | header image URL |
| `description` | string | gamegauntlets | 99.9% (116,139) | English store description (raw HTML) |
| `steam_appid` | integer | steam | 98.1% (113,973) | Steam appid |
| `steam_url` | string | steam | 98.1% (113,973) | Steam store page URL |
| `gog_id` | integer | gog | 5.9% (6,861) | GOG catalog id |
| `gog_url` | string | gog | 6.2% (7,168) | GOG store page URL |
| `release_date` | date (`YYYY-MM-DD`) | gamegauntlets | 97.9% (113,764) | cross-source consensus release date |
| `release_precision` | string | gamegauntlets | 97.9% (113,764) | day/month/quarter/year/unknown |
| `early_access_date` | date (`YYYY-MM-DD`) | steam | 0.4% (422) | date the game entered Early Access, if it did |
| `store_release_date` | date (`YYYY-MM-DD`) | gamegauntlets | 97.7% (113,601) | store listing date (may be a re-listing, not the true release date) |
| `price_usd` | integer | gamegauntlets | 84.1% (97,696) | USD list price, cents |
| `price_final_usd` | integer | gamegauntlets | 84.1% (97,696) | USD price after discount, cents |
| `discount_percent` | integer | gamegauntlets | 27.4% (31,832) | discount percent, 0..100 |
| `platforms` | array of strings | gamegauntlets | 100.0% (116,225) | WIN/MAC/LNX |
| `developers` | array of strings | gamegauntlets | 99.9% (116,169) | developer names |
| `publishers` | array of strings | gamegauntlets | 99.8% (116,000) | publisher names |
| `languages` | array of strings | gamegauntlets | 99.8% (116,050) | interface language names |
| `voiceovers` | array of strings | gamegauntlets | 44.3% (51,510) | voiceover language names |
| `categories` | array of strings | gamegauntlets | 99.9% (116,107) | store category tags |
| `genres` | array of strings | gamegauntlets | 100.0% (116,210) | genre tags |
| `tags` | array of strings | gamegauntlets | 64.2% (74,606) | community tags |
| `achievements` | integer | steam | 50.7% (58,884) | achievement count |
| `steam_reviews_percent` | integer | steam | 72.5% (84,305) | all-time positive review share, 0..100 |
| `steam_reviews_count` | integer | steam | 69.3% (80,556) | all-time review count |
| `steam_reviews_label` | string | steam | 47.7% (55,416) | Steam's own label ("Very Positive", ...), null under 10 votes |
| `steam_recent_percent` | integer | steam | 3.5% (4,060) | last ~30 days positive review share, 0..100 |
| `steam_recent_count` | integer | steam | 3.5% (4,061) | last ~30 days review count |
| `steam_recent_label` | string | steam | 0.4% (479) | recent-reviews label, null under 10 votes |
| `steamspy_owners` | integer | steamspy | 83.5% (97,049) | owners estimate, lower bound |
| `average_playtime_hours` | number | gamegauntlets | 2.3% (2,617) | resolved average playtime, decimal hours |
| `average_playtime_source` | string | gamegauntlets | 2.3% (2,617) | which source produced average_playtime_hours |
| `hltb_url` | string | hltb | 36.9% (42,844) | HowLongToBeat page URL |
| `hltb_main_hours` | number | hltb | 20.1% (23,365) | main story hours, decimal |
| `hltb_complete_hours` | number | hltb | 100.0% (116,225) | completionist hours, decimal |
| `gamefaqs_url` | string | gamefaqs | 65.9% (76,645) | GameFAQs product page URL |
| `gamefaqs_difficulty` | string | gamefaqs | 16.5% (19,200) | GameFAQs difficulty label |
| `gamefaqs_rating` | number | gamefaqs | 18.2% (21,185) | GameFAQs rating, 0..5 |
| `metacritic_url` | string | metacritic | 31.4% (36,498) | Metacritic page URL |
| `metacritic_score` | integer | metacritic | 5.3% (6,159) | critic score, 0..100 |
| `metacritic_reviews` | integer | metacritic | 3.9% (4,584) | critic review count |
| `metacritic_user_score` | integer | metacritic | 7.9% (9,182) | user score, 0..100 |
| `igdb_url` | string | igdb | 89.8% (104,421) | IGDB page URL |
| `igdb_score` | integer | igdb | 7.2% (8,342) | IGDB critic score, 0..100 |
| `igdb_user_score` | integer | igdb | 17.5% (20,308) | IGDB user score, 0..100 |
| `gamerankings_score` | integer | gamerankings | 6.0% (7,025) | critic score, 0..100 |
| `gg_score` | integer | gamegauntlets | 100.0% (116,225) | Game Gauntlets' own composite score |
| `gg_points` | integer | gamegauntlets | 100.0% (116,225) | Game Gauntlets priority score (wheel weighting) |
| `updated_at` | datetime (ISO 8601) | gamegauntlets | 100.0% (116,229) | last time this row changed |

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
  "metacritic_url": null,
  "metacritic_score": 88,
  "metacritic_reviews": null,
  "metacritic_user_score": null,
  "igdb_url": "https://www.igdb.com/games/counter-strike",
  "igdb_score": 70,
  "igdb_user_score": 83,
  "gamerankings_score": 89,
  "gg_score": 78,
  "gg_points": 218,
  "updated_at": "2026-09-19T16:09:00Z"
}
```

## Source status

"Remaining" is games with no data from that source yet, or whose last fetch is older than the source's own refresh interval.

| Source | Refresh | OK | Not found | Error | Games covered | Remaining | Paused | Last run |
|---|---|---|---|---|---|---|---|---|
| steam | 1d | 11,659 | 30 | 33 | 11,664 | 104,613 | no | 2026-09-19 22:26:31 |
| gog | 7d | 6,941 | 18 | 0 | 6,837 | 109,404 | no | 2026-09-19 06:49:20 |
| wikidata | 30d | 98,475 | 53 | 0 | 98,306 | 17,967 | no | 2026-09-19 03:26:11 |
| igdb | 30d | 103,979 | 37 | 0 | 103,990 | 12,288 | no | 2026-09-19 19:01:49 |
| steamspy | 7d | 80,306 | 33 | 0 | 80,306 | 35,977 | no | 2026-09-19 04:48:21 |
| hltb | 30d | 5,694 | 25 | 0 | 5,718 | 110,550 | no | 2026-09-19 06:50:27 |
| gamefaqs | 90d | 6,909 | 321 | 0 | 7,239 | 109,001 | no | 2026-09-19 22:26:31 |
| metacritic | 60d | 10,597 | 1,098 | 0 | 11,703 | 104,534 | no | 2026-09-19 22:26:32 |

## External links

| Site | Linked games |
|---|---|
| gamefaqs | 76,646 |
| gog | 7,168 |
| hltb | 42,844 |
| igdb | 104,742 |
| metacritic | 36,508 |
| mobygames | 40,269 |
| steam | 113,993 |
| wikidata | 98,297 |
| wikipedia_en | 7,582 |
| wikipedia_ru | 3,412 |

## Licence

The dataset is released under the GNU General Public License v3.0 (see `LICENSE` in this repo). Game
names, images, descriptions and prices belong to their respective publishers, platforms and third-party
sources.
