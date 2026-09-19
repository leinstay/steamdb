# Steam & GOG Video Game Database

JSON dump of the [Game Gauntlets](https://gamegauntlets.com) game catalog: prices, scores and metadata
merged from Steam, GOG, SteamSpy, GameFAQs, Metacritic, IGDB, HowLongToBeat, Wikidata and an archived
GameRankings dataset. [Live preview](https://gamegauntlets.com).

Updated nightly at 23:48 UTC by the site's own export job. This README is regenerated on every update,
so the numbers below always describe the dump files sitting next to it in this same commit.

_Generated 2026-09-19T16:52:11.722Z._

## Files

| File | Rows | Size |
|---|---|---|
| `steamdb.json` | 111,134 | 427.0 MB |
| `steamdb.min.json` | 111,134 | 350.7 MB |
| `steamdb.min.json.gz` | 111,134 | 81.0 MB |
| `gogdb.json` | 2,256 | 8.9 MB |
| `gogdb.min.json` | 2,256 | 7.4 MB |
| `gogdb.min.json.gz` | 2,256 | 1.8 MB |

`steamdb.json`/`gogdb.json` are the same schema (see below); `kind` on each row tells them apart if
you concatenate the two. The pretty files are for humans; `*.min.json`/`*.min.json.gz` are what you
want to actually fetch.

## Catalog totals

| Metric | Count |
|---|---|
| Games in the catalog | 113,522 |
| Steam games | 111,250 |
| GOG-exclusive games | 2,272 |
| Steam games also matched on GOG | 4,607 |
| Exported to steamdb.json | 111,134 |
| Exported to gogdb.json | 2,256 |
| Excluded — unpurchasable | 36 |
| Excluded — delisted from Steam | 0 |
| Excluded — 100% discounted (temporary/removed promo) | 3 |

**Excluded — not a game, by class:**

| Class | Count |
|---|---|
| dlc | 4 |
| soundtrack | 5 |
| artbook | 2 |
| demo | 70 |
| tool | 6 |
| bundle | 8 |

## Schema

Every key from the original dump is kept, unchanged, in its original position — nothing already
published has been renamed or removed. New keys (schema v2, 2026-09-19) are appended after them.
"Coverage" is the share of exported games (both files combined) that currently have a non-null value
for that key — most gaps are simply games no source has finished filling in yet, not a bug.

| Key | Source | Coverage | Description |
|---|---|---|---|
| `sid` | steam | 98.0% (111,134) | Steam appid |
| `store_url` | steam | 98.0% (111,134) | Steam store page URL |
| `store_promo_url` | dropped (legacy-only) | 0.0% (0) | always null — no rewrite column |
| `store_uscore` | steam | 74.1% (84,028) | Steam all-review score, 0..100 (see steam_reviews_percent) |
| `published_store` | steam/gog | 99.8% (113,131) | store listing date (may be a re-listing, not the true release date) |
| `published_meta` | legacy snapshot | 98.1% (111,281) | frozen legacy_steamdb value, null for a rewrite-only game |
| `published_stsp` | legacy snapshot | 98.1% (111,281) | frozen legacy_steamdb value, null for a rewrite-only game |
| `published_hltb` | legacy snapshot | 98.1% (111,281) | frozen legacy_steamdb value, null for a rewrite-only game |
| `published_igdb` | legacy snapshot | 98.1% (111,281) | frozen legacy_steamdb value, null for a rewrite-only game |
| `image` | steam/gog | 100.0% (113,385) | header image URL |
| `name` | steam/gog | 100.0% (113,390) | game title |
| `description` | steam/gog | 99.9% (113,301) | English store description (raw HTML) |
| `full_price` | steam/gog | 85.8% (97,272) | USD list price, cents |
| `current_price` | steam/gog | 85.8% (97,272) | USD price after discount, cents |
| `discount` | steam/gog | 27.4% (31,019) | discount percent, 0..100 |
| `platforms` | steam/gog | 100.0% (113,387) | comma list of WIN/MAC/LNX |
| `developers` | steam/gog | 99.9% (113,332) | comma list |
| `publishers` | steam/gog | 99.8% (113,162) | comma list |
| `languages` | steam/gog | 99.8% (113,212) | comma list |
| `voiceovers` | steam/gog | 44.6% (50,591) | comma list |
| `categories` | steam/gog | 99.9% (113,269) | comma list |
| `genres` | steam/gog | 100.0% (113,372) | comma list |
| `tags` | steam/gog | 65.8% (74,611) | comma list |
| `achievements` | steam | 51.7% (58,607) | achievement count |
| `gfq_url` | gamefaqs | 67.4% (76,398) | GameFAQs product page URL |
| `gfq_difficulty` | gamefaqs | 16.3% (18,472) | GameFAQs difficulty label |
| `gfq_difficulty_comment` | dropped (legacy-only) | 0.0% (0) | always null — dead legacy column |
| `gfq_rating` | gamefaqs | 18.1% (20,518) | GameFAQs rating, 0..5 |
| `gfq_rating_comment` | dropped (legacy-only) | 0.0% (0) | always null — dead legacy column |
| `gfq_length` | dropped (legacy-only) | 0.0% (0) | always null — not persisted in the rewrite |
| `gfq_length_comment` | dropped (legacy-only) | 0.0% (0) | always null — dead legacy column |
| `stsp_owners` | steamspy | 85.6% (97,053) | owners estimate, lower bound |
| `stsp_mdntime` | dropped (legacy-only) | 0.0% (0) | always null — see average_playtime_hours instead |
| `hltb_url` | hltb | 37.8% (42,849) | HowLongToBeat page URL |
| `hltb_single` | hltb | 20.6% (23,368) | main story hours |
| `hltb_complete` | hltb | 100.0% (113,387) | completionist hours |
| `meta_url` | metacritic | 30.0% (34,047) | Metacritic page URL |
| `meta_score` | metacritic | 4.5% (5,074) | critic score, 0..100 (null unless score_critics_source=metacritic) |
| `meta_uscore` | metacritic | 6.9% (7,770) | user score, 0..100 (frozen) |
| `grnk_score` | gamerankings (legacy) | 6.2% (7,027) | archived GameRankings score, 0..100 (frozen — see gamerankings_score) |
| `igdb_url` | igdb | 80.7% (91,461) | IGDB page URL |
| `igdb_single` | dropped (legacy-only) | 0.0% (0) | always null — never requested by the parser |
| `igdb_complete` | dropped (legacy-only) | 0.0% (0) | always null — never requested by the parser |
| `igdb_score` | igdb | 7.1% (8,044) | IGDB critic score, 0..100 |
| `igdb_uscore` | igdb | 17.6% (20,002) | IGDB user score, 0..100 |
| `igdb_popularity` | dropped (legacy-only) | 0.0% (0) | always null — never requested by the parser |
| `steam_reviews_percent` | steam | 74.1% (84,028) | all-time positive review share, 0..100 |
| `steam_reviews_count` | steam | 70.7% (80,220) | all-time review count |
| `steam_reviews_label` | steam | 48.8% (55,326) | Steam's own label ("Very Positive", ...), null under 10 votes |
| `steam_recent_percent` | steam | 3.0% (3,379) | last ~30 days positive review share, 0..100 |
| `steam_recent_count` | steam | 3.0% (3,380) | last ~30 days review count |
| `steam_recent_label` | steam | 0.3% (388) | recent-reviews label, null under 10 votes |
| `average_playtime_hours` | steam/steamspy | 1.9% (2,202) | resolved average playtime, hours |
| `average_playtime_source` | steam/steamspy | 1.9% (2,202) | which source produced average_playtime_hours |
| `metacritic_reviews` | metacritic | 2.3% (2,621) | critic review count (null unless score_critics_source=metacritic) |
| `gamerankings_score` | gamerankings (legacy) | 6.2% (7,027) | readable alias of grnk_score |
| `gg_score` | rewrite (computed) | 100.0% (113,387) | Game Gauntlets' own composite score |
| `ggp` | rewrite (computed) | 100.0% (113,387) | Game Gauntlets priority score (wheel weighting) |
| `release_date` | rewrite (resolver) | 99.9% (113,259) | cross-source consensus release date |
| `release_precision` | rewrite (resolver) | 99.9% (113,259) | day/month/quarter/year/unknown |
| `kind` | rewrite | 100.0% (113,390) | 'steam' or 'gog_exclusive' |
| `gog_id` | gog/wikidata | 6.1% (6,861) | GOG catalog id (set on a Steam row too when cross-matched) |
| `gog_url` | gog/wikidata | 6.3% (7,168) | GOG store page URL |
| `early_access_date` | steam | 0.3% (340) | date the game entered Early Access, if it did |
| `price_rub` | steam | 85.0% (96,389) | RUB list price, kopecks |
| `price_final_rub` | steam | 85.0% (96,388) | RUB price after discount, kopecks |
| `discount_rub` | steam | 26.6% (30,163) | RUB discount percent |
| `price_cis_usd` | steam | 58.8% (66,676) | CIS "backup region" USD list price, cents |
| `price_final_cis_usd` | steam | 58.7% (66,602) | CIS USD price after discount, cents |
| `discount_cis_usd` | steam | 9.8% (11,116) | CIS discount percent |
| `updated_at` | rewrite | 100.0% (113,390) | last time this row changed |

## Source status

Per-source parser status, from the site's own scheduler. "Remaining" is games with no data from that
source yet, or whose last fetch is older than the source's own refresh interval — i.e. what the
scheduler still has left to do, not a total backlog. `legacy_steamdb`/`gamerankings` are historical,
one-time snapshots (no live parser, no refresh interval, "remaining" is n/a for them).

| Source | Refresh | OK | Not found | Error | Games covered | Remaining | Paused | Last run |
|---|---|---|---|---|---|---|---|---|
| steam | 1d | 8,324 | 22 | 33 | 8,327 | 105,104 | no | 2026-09-19 16:50:57 |
| gog | 7d | 6,958 | 1 | 0 | 6,854 | 106,555 | no | 2026-09-19 06:49:20 |
| wikidata | 30d | 98,528 | 0 | 0 | 98,359 | 15,114 | no | 2026-09-19 03:26:11 |
| igdb | 30d | 91,140 | 11 | 0 | 91,151 | 22,291 | no | 2026-09-19 16:51:00 |
| steamspy | 7d | 80,339 | 0 | 0 | 80,339 | 33,117 | no | 2026-09-19 04:48:21 |
| hltb | 30d | 5,695 | 24 | 0 | 5,719 | 107,689 | no | 2026-09-19 06:50:27 |
| gamefaqs | 90d | 1,448 | 47 | 0 | 1,495 | 111,903 | no | 2026-09-19 16:23:42 |
| opencritic | n/a | 0 | 0 | 0 | 0 | n/a | yes | never |
| metacritic | 60d | 4,628 | 397 | 0 | 5,032 | 108,343 | no | 2026-09-19 16:51:00 |
| legacy_steamdb | n/a | 111,528 | 0 | 0 | 111,390 | n/a | no | never |
| gamerankings | n/a | 4,652 | 0 | 0 | 4,652 | n/a | no | never |

## External links

Games matched to an external page, by site (`game_links`, one row per game per site):

| Site | Linked games | Total link rows |
|---|---|---|
| gamefaqs | 76,434 | 76,434 |
| gog | 7,187 | 7,187 |
| hltb | 42,893 | 42,893 |
| igdb | 104,806 | 104,806 |
| metacritic | 34,100 | 34,100 |
| mobygames | 40,304 | 40,304 |
| opencritic | 12,239 | 12,239 |
| steam | 111,250 | 111,250 |
| wikidata | 98,386 | 98,386 |
| wikipedia_en | 7,603 | 7,603 |
| wikipedia_ru | 3,426 | 3,426 |

## Licence

The dataset itself is released under the GNU General Public License v3.0 (see `LICENSE` in this repo).
Game names, images, descriptions and prices are the property of their respective publishers/platforms
(Steam, GOG) and third-party sources (Metacritic, IGDB, HowLongToBeat, GameFAQs, SteamSpy, GameRankings,
Wikidata) — this repo only republishes what those sites already show publicly, for convenience.
