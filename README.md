# Video Game Database

JSON dump of the [Game Gauntlets](https://gamegauntlets.com) game catalog: prices, scores and metadata
merged from Steam, GOG, SteamSpy, GameFAQs, Metacritic, IGDB, HowLongToBeat, Wikidata and an archived
GameRankings dataset. [Live preview](https://gamegauntlets.com).

Updated nightly at 23:48 UTC by the site's own export job. This README is regenerated on every update,
so the numbers below always describe the dump files sitting next to it in this same commit.

_Generated 2026-09-19T17:46:20.499Z._

## Files

| File | Rows | Size |
|---|---|---|
| `steamdb.json` | 113,412 | 435.7 MB |
| `steamdb.min.json` | 113,412 | 357.8 MB |
| `steamdb.min.json.gz` | 113,412 | 82.7 MB |

`kind` on each row tells Steam and GOG-exclusive games apart. The pretty file is for humans;
`steamdb.min.json`/`steamdb.min.json.gz` are what you want to actually fetch.

## Catalog totals

| Metric | Count |
|---|---|
| Games in the catalog | 113,414 |
| Steam games | 111,158 |
| GOG-exclusive games | 2,256 |
| Steam games also on GOG | 4,605 |

## Schema

Every key from the original dump is kept, unchanged, in its original position — nothing already
published has been renamed or removed. New keys (schema v2, 2026-09-19) are appended after them.
"Coverage" is the share of exported games that currently have a non-null value for that key — most
gaps are simply games no source has finished filling in yet, not a bug.

| Key | Source | Coverage | Description |
|---|---|---|---|
| `sid` | steam | 98.0% (111,158) | Steam appid |
| `store_url` | steam | 98.0% (111,158) | Steam store page URL |
| `store_promo_url` | dropped (legacy-only) | 0.0% (0) | always null — no rewrite column |
| `store_uscore` | steam | 74.1% (84,034) | Steam all-review score, 0..100 (see steam_reviews_percent) |
| `published_store` | steam/gog | 99.8% (113,132) | store listing date (may be a re-listing, not the true release date) |
| `published_meta` | legacy snapshot | 98.1% (111,278) | frozen legacy_steamdb value, null for a rewrite-only game |
| `published_stsp` | legacy snapshot | 98.1% (111,278) | frozen legacy_steamdb value, null for a rewrite-only game |
| `published_hltb` | legacy snapshot | 98.1% (111,278) | frozen legacy_steamdb value, null for a rewrite-only game |
| `published_igdb` | legacy snapshot | 98.1% (111,278) | frozen legacy_steamdb value, null for a rewrite-only game |
| `image` | steam/gog | 100.0% (113,408) | header image URL |
| `name` | steam/gog | 100.0% (113,414) | game title |
| `description` | steam/gog | 99.9% (113,324) | English store description (raw HTML) |
| `full_price` | steam/gog | 85.8% (97,278) | USD list price, cents |
| `current_price` | steam/gog | 85.8% (97,278) | USD price after discount, cents |
| `discount` | steam/gog | 27.7% (31,406) | discount percent, 0..100 |
| `platforms` | steam/gog | 100.0% (113,410) | comma list of WIN/MAC/LNX |
| `developers` | steam/gog | 99.9% (113,356) | comma list |
| `publishers` | steam/gog | 99.8% (113,188) | comma list |
| `languages` | steam/gog | 99.8% (113,235) | comma list |
| `voiceovers` | steam/gog | 44.6% (50,603) | comma list |
| `categories` | steam/gog | 99.9% (113,292) | comma list |
| `genres` | steam/gog | 100.0% (113,395) | comma list |
| `tags` | steam/gog | 65.8% (74,608) | comma list |
| `achievements` | steam | 51.7% (58,617) | achievement count |
| `gfq_url` | gamefaqs | 67.4% (76,395) | GameFAQs product page URL |
| `gfq_difficulty` | gamefaqs | 16.3% (18,474) | GameFAQs difficulty label |
| `gfq_difficulty_comment` | dropped (legacy-only) | 0.0% (0) | always null — dead legacy column |
| `gfq_rating` | gamefaqs | 18.1% (20,520) | GameFAQs rating, 0..5 |
| `gfq_rating_comment` | dropped (legacy-only) | 0.0% (0) | always null — dead legacy column |
| `gfq_length` | dropped (legacy-only) | 0.0% (0) | always null — not persisted in the rewrite |
| `gfq_length_comment` | dropped (legacy-only) | 0.0% (0) | always null — dead legacy column |
| `stsp_owners` | steamspy | 85.6% (97,051) | owners estimate, lower bound |
| `stsp_mdntime` | dropped (legacy-only) | 0.0% (0) | always null — see average_playtime_hours instead |
| `hltb_url` | hltb | 37.8% (42,846) | HowLongToBeat page URL |
| `hltb_single` | hltb | 20.6% (23,367) | main story hours |
| `hltb_complete` | hltb | 100.0% (113,410) | completionist hours |
| `meta_url` | metacritic | 30.4% (34,451) | Metacritic page URL |
| `meta_score` | metacritic | 4.7% (5,278) | critic score, 0..100 (null unless score_critics_source=metacritic) |
| `meta_uscore` | metacritic | 7.1% (8,083) | user score, 0..100 (frozen) |
| `grnk_score` | gamerankings (legacy) | 6.2% (7,027) | archived GameRankings score, 0..100 (frozen — see gamerankings_score) |
| `igdb_url` | igdb | 84.5% (95,876) | IGDB page URL |
| `igdb_single` | dropped (legacy-only) | 0.0% (0) | always null — never requested by the parser |
| `igdb_complete` | dropped (legacy-only) | 0.0% (0) | always null — never requested by the parser |
| `igdb_score` | igdb | 7.2% (8,147) | IGDB critic score, 0..100 |
| `igdb_uscore` | igdb | 17.8% (20,145) | IGDB user score, 0..100 |
| `igdb_popularity` | dropped (legacy-only) | 0.0% (0) | always null — never requested by the parser |
| `steam_reviews_percent` | steam | 74.1% (84,034) | all-time positive review share, 0..100 |
| `steam_reviews_count` | steam | 70.8% (80,257) | all-time review count |
| `steam_reviews_label` | steam | 48.8% (55,357) | Steam's own label ("Very Positive", ...), null under 10 votes |
| `steam_recent_percent` | steam | 3.3% (3,798) | last ~30 days positive review share, 0..100 |
| `steam_recent_count` | steam | 3.3% (3,799) | last ~30 days review count |
| `steam_recent_label` | steam | 0.4% (420) | recent-reviews label, null under 10 votes |
| `average_playtime_hours` | steam/steamspy | 2.2% (2,455) | resolved average playtime, hours |
| `average_playtime_source` | steam/steamspy | 2.2% (2,455) | which source produced average_playtime_hours |
| `metacritic_reviews` | metacritic | 2.6% (2,996) | critic review count (null unless score_critics_source=metacritic) |
| `gamerankings_score` | gamerankings (legacy) | 6.2% (7,027) | readable alias of grnk_score |
| `gg_score` | rewrite (computed) | 100.0% (113,410) | Game Gauntlets' own composite score |
| `ggp` | rewrite (computed) | 100.0% (113,410) | Game Gauntlets priority score (wheel weighting) |
| `release_date` | rewrite (resolver) | 99.9% (113,283) | cross-source consensus release date |
| `release_precision` | rewrite (resolver) | 99.9% (113,283) | day/month/quarter/year/unknown |
| `kind` | rewrite | 100.0% (113,414) | 'steam' or 'gog_exclusive' |
| `gog_id` | gog/wikidata | 6.0% (6,861) | GOG catalog id (set on a Steam row too when cross-matched) |
| `gog_url` | gog/wikidata | 6.3% (7,168) | GOG store page URL |
| `early_access_date` | steam | 0.3% (372) | date the game entered Early Access, if it did |
| `price_rub` | steam | 85.0% (96,395) | RUB list price, kopecks |
| `price_final_rub` | steam | 85.0% (96,394) | RUB price after discount, kopecks |
| `discount_rub` | steam | 26.9% (30,538) | RUB discount percent |
| `price_cis_usd` | steam | 58.8% (66,682) | CIS "backup region" USD list price, cents |
| `price_final_cis_usd` | steam | 58.7% (66,608) | CIS USD price after discount, cents |
| `discount_cis_usd` | steam | 10.2% (11,535) | CIS discount percent |
| `updated_at` | rewrite | 100.0% (113,414) | last time this row changed |

## Source status

Per-source parser status, from the site's own scheduler. "Remaining" is games with no data from that
source yet, or whose last fetch is older than the source's own refresh interval — i.e. what the
scheduler still has left to do, not a total backlog.

| Source | Refresh | OK | Not found | Error | Games covered | Remaining | Paused | Last run |
|---|---|---|---|---|---|---|---|---|
| steam | 1d | 8,851 | 30 | 33 | 8,854 | 104,613 | no | 2026-09-19 17:45:03 |
| gog | 7d | 6,941 | 18 | 0 | 6,837 | 106,597 | no | 2026-09-19 06:49:20 |
| wikidata | 30d | 98,475 | 53 | 0 | 98,306 | 15,158 | no | 2026-09-19 03:26:11 |
| igdb | 30d | 95,623 | 34 | 0 | 95,668 | 17,715 | no | 2026-09-19 17:45:07 |
| steamspy | 7d | 80,306 | 33 | 0 | 80,306 | 33,168 | no | 2026-09-19 04:48:21 |
| hltb | 30d | 5,694 | 25 | 0 | 5,718 | 107,741 | no | 2026-09-19 06:50:27 |
| gamefaqs | 90d | 1,578 | 52 | 0 | 1,636 | 111,787 | no | 2026-09-19 17:45:07 |
| metacritic | 60d | 5,632 | 500 | 0 | 6,132 | 107,298 | no | 2026-09-19 17:45:06 |

A couple of one-time snapshots feed the catalog with no live parser behind them: legacy data (111,314 games) and the GameRankings archive (4,652 games).

## External links

Games matched to a page on an external site, by site:

| Site | Linked games |
|---|---|
| gamefaqs | 76,395 |
| gog | 7,168 |
| hltb | 42,846 |
| igdb | 104,744 |
| metacritic | 34,473 |
| mobygames | 40,271 |
| steam | 111,185 |
| wikidata | 98,299 |
| wikipedia_en | 7,583 |
| wikipedia_ru | 3,413 |

## Licence

The dataset itself is released under the GNU General Public License v3.0 (see `LICENSE` in this repo).
Game names, images, descriptions and prices are the property of their respective publishers/platforms
(Steam, GOG) and third-party sources (Metacritic, IGDB, HowLongToBeat, GameFAQs, SteamSpy, GameRankings,
Wikidata) — this repo only republishes what those sites already show publicly, for convenience.
