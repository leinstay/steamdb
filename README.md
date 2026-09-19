# Steam Game Database

JSON dump of the [Game Gauntlets](https://gamegauntlets.com) game catalog: prices, scores and metadata
merged from Steam, GOG, SteamSpy, GameFAQs, Metacritic, IGDB, HowLongToBeat, Wikidata and GameRankings.

Updated nightly at 23:48 UTC.

_Generated 2026-09-19T23:50:22.655Z._

## Files

| File | Rows | Size |
|---|---|---|
| `steamdb.json` | 117,053 | 431.8 MB |
| `steamdb.min.json` | 117,053 | 328.3 MB |
| `steamdb.min.json.gz` | 117,053 | 80.9 MB |

## Catalog totals

| Metric | Count |
|---|---|
| Games in the catalog | 117,054 |
| Steam games | 114,798 |
| GOG-exclusive games | 2,256 |
| Steam games also on GOG | 4,605 |

## Schema

"Coverage" is the share of exported games that currently have a value for that key. Any key may be
`null` when the value is unknown.

| Key | Type | Source | Coverage | Description |
|---|---|---|---|---|
| `id` | integer | gamegauntlets | 100.0% (117,054) | catalog id, stable across updates |
| `kind` | string | gamegauntlets | 100.0% (117,054) | 'steam' or 'gog_exclusive' |
| `name` | string | gamegauntlets | 100.0% (117,054) | game title |
| `image` | string | gamegauntlets | 100.0% (117,047) | header image URL |
| `description` | string | gamegauntlets | 99.9% (116,964) | English store description (raw HTML) |
| `steam_appid` | integer | steam | 98.1% (114,798) | Steam appid |
| `steam_url` | string | steam | 98.1% (114,798) | Steam store page URL |
| `gog_id` | integer | gog | 5.9% (6,861) | GOG catalog id |
| `gog_url` | string | gog | 6.1% (7,168) | GOG store page URL |
| `release_date` | date (`YYYY-MM-DD`) | gamegauntlets | 97.2% (113,832) | cross-source consensus release date |
| `release_precision` | string | gamegauntlets | 97.2% (113,832) | day/month/quarter/year/unknown |
| `early_access_date` | date (`YYYY-MM-DD`) | steam | 0.4% (428) | date the game entered Early Access, if it did |
| `store_release_date` | date (`YYYY-MM-DD`) | gamegauntlets | 97.1% (113,669) | store listing date (may be a re-listing, not the true release date) |
| `price_usd` | integer | gamegauntlets | 83.5% (97,760) | USD list price, cents |
| `price_final_usd` | integer | gamegauntlets | 83.5% (97,760) | USD price after discount, cents |
| `discount_percent` | integer | gamegauntlets | 27.2% (31,896) | discount percent, 0..100 |
| `platforms` | array of strings | gamegauntlets | 100.0% (117,049) | WIN/MAC/LNX |
| `developers` | array of strings | gamegauntlets | 99.9% (116,994) | developer names |
| `publishers` | array of strings | gamegauntlets | 99.8% (116,825) | publisher names |
| `languages` | array of strings | gamegauntlets | 99.8% (116,875) | interface language names |
| `voiceovers` | array of strings | gamegauntlets | 44.2% (51,783) | voiceover language names |
| `categories` | array of strings | gamegauntlets | 99.9% (116,932) | store category tags |
| `genres` | array of strings | gamegauntlets | 100.0% (117,035) | genre tags |
| `tags` | array of strings | gamegauntlets | 63.7% (74,606) | community tags |
| `achievements` | integer | steam | 50.3% (58,930) | achievement count |
| `steam_reviews_percent` | integer | steam | 72.0% (84,334) | all-time positive review share, 0..100 |
| `steam_reviews_count` | integer | steam | 68.8% (80,587) | all-time review count |
| `steam_reviews_label` | string | steam | 47.3% (55,422) | Steam's own label ("Very Positive", ...), null under 10 votes |
| `steam_recent_percent` | integer | steam | 3.5% (4,086) | last ~30 days positive review share, 0..100 |
| `steam_recent_count` | integer | steam | 3.5% (4,087) | last ~30 days review count |
| `steam_recent_label` | string | steam | 0.4% (486) | recent-reviews label, null under 10 votes |
| `steamspy_owners` | integer | steamspy | 82.9% (97,049) | owners estimate, lower bound |
| `average_playtime_hours` | number | gamegauntlets | 2.3% (2,635) | resolved average playtime, decimal hours |
| `average_playtime_source` | string | gamegauntlets | 2.3% (2,635) | which source produced average_playtime_hours |
| `hltb_url` | string | hltb | 36.6% (42,844) | HowLongToBeat page URL |
| `hltb_main_hours` | number | hltb | 20.0% (23,365) | main story hours, decimal |
| `hltb_complete_hours` | number | hltb | 100.0% (117,050) | completionist hours, decimal |
| `gamefaqs_url` | string | gamefaqs | 65.8% (77,040) | GameFAQs product page URL |
| `gamefaqs_difficulty` | string | gamefaqs | 16.7% (19,592) | GameFAQs difficulty label |
| `gamefaqs_rating` | number | gamefaqs | 18.4% (21,578) | GameFAQs rating, 0..5 |
| `metacritic_url` | string | metacritic | 31.7% (37,140) | Metacritic page URL |
| `metacritic_score` | integer | metacritic | 5.4% (6,358) | critic score, 0..100 |
| `metacritic_reviews` | integer | metacritic | 4.2% (4,938) | critic review count |
| `metacritic_user_score` | integer | metacritic | 8.0% (9,413) | user score, 0..100 |
| `igdb_url` | string | igdb | 89.2% (104,421) | IGDB page URL |
| `igdb_score` | integer | igdb | 7.1% (8,342) | IGDB critic score, 0..100 |
| `igdb_user_score` | integer | igdb | 17.3% (20,308) | IGDB user score, 0..100 |
| `gamerankings_score` | integer | gamerankings | 6.0% (7,025) | critic score, 0..100 |
| `gg_score` | integer | gamegauntlets | 100.0% (117,050) | Game Gauntlets' own composite score |
| `gg_points` | integer | gamegauntlets | 100.0% (117,050) | Game Gauntlets priority score (wheel weighting) |
| `updated_at` | datetime (ISO 8601) | gamegauntlets | 100.0% (117,054) | last time this row changed |

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
| steam | 1d | 12,484 | 30 | 33 | 12,489 | 104,613 | no | 2026-09-19 23:49:02 |
| gog | 7d | 6,941 | 18 | 0 | 6,837 | 110,229 | no | 2026-09-19 06:49:20 |
| wikidata | 30d | 98,475 | 53 | 0 | 98,306 | 18,792 | no | 2026-09-19 03:26:11 |
| igdb | 30d | 103,979 | 37 | 0 | 103,990 | 13,113 | no | 2026-09-19 19:01:49 |
| steamspy | 7d | 80,306 | 33 | 0 | 80,306 | 36,802 | no | 2026-09-19 04:48:21 |
| hltb | 30d | 5,694 | 25 | 0 | 5,718 | 111,375 | no | 2026-09-19 06:50:27 |
| gamefaqs | 90d | 8,413 | 459 | 0 | 8,880 | 108,186 | no | 2026-09-19 23:49:04 |
| metacritic | 60d | 12,192 | 1,301 | 0 | 13,497 | 103,572 | no | 2026-09-19 23:48:56 |

## External links

| Site | Linked games |
|---|---|
| gamefaqs | 77,073 |
| gog | 7,168 |
| hltb | 42,844 |
| igdb | 104,742 |
| metacritic | 37,159 |
| mobygames | 40,269 |
| steam | 114,818 |
| wikidata | 98,297 |
| wikipedia_en | 7,582 |
| wikipedia_ru | 3,412 |

## Licence

The dataset is released under the GNU General Public License v3.0 (see `LICENSE` in this repo). Game
names, images, descriptions and prices belong to their respective publishers, platforms and third-party
sources.
