# NAVCore-TV proposed lineup update

**Prepared:** 2026-11-10  
**Status:** Proposed candidates only; not added to the live Jellyfin tuner  
**Scope:** Update the curation requirements for OWN, TLC, and Los Angeles local news.

## Confirmed curation rules

- Channel market/origin must be the United States or Mexico.
- Keep all languages.
- Keep all sports categories, including football and soccer.
- Exclude any entry tagged `Religious` or `Shop`, including mixed-category entries.
- Deduplicate by channel identity and stream URL, not display name alone.
- Keep uncertain/undefined categories for review rather than silently discarding them.
- A playlist entry is not proof of authorization, geographic availability, or working playback.

## New requested targets

### OWN — Oprah Winfrey Network

Found in the upstream IPTV-org U.S. stream catalog:

- Display name: `OWN (720p)`
- TVG ID: `OWN.us@East`
- Status: **Candidate only; not imported or playback-tested**
- Review needed: The listed stream uses a raw-IP HTTP endpoint. Its provenance, authorization, stability, and geographic availability have not been established. Do not rely on it or promote it to the active playlist until those checks pass.

### TLC — The Learning Channel

The upstream stream catalog search found:

- `TLC Latin America (1080p)`, TVG ID `TLCLatinAmerica.us@Panregional`
- `TLC Latin America Brazil (720p)`, TVG ID `TLCLatinAmerica.us@Brazil`

Neither listing establishes a U.S.-domestic or Mexico-origin feed. The Brazil feed is outside the requested market restriction. The panregional feed is not sufficiently market-specific to establish U.S. or Mexico origin. **Neither is approved for inclusion under the current geography rule.**

A U.S. domestic or Mexico-market TLC source is still needed. Do not substitute the Latin America or Brazil feeds just because the channel name matches.

### Los Angeles local news

Found in the upstream IPTV-org U.S. stream catalog:

| Candidate | TVG ID | Listed quality | Status |
|---|---|---:|---|
| CBS News Los Angeles | `CBSNewsLosAngeles.us@SD` | Not stated in entry | Candidate; not playback-tested |
| KTTV 11.1 | `Fox.us@KTTV` | 720p | Candidate; same channel identity as the next entry |
| KTTV-DT1 | `Fox.us@KTTV` | 1080p | Candidate; same channel identity as the previous entry |

For the two KTTV entries, compare actual playback and retain one preferred stream unless there is a demonstrated reason to keep both. The 1080p entry is the initial quality preference, not a verified winner.

A search of the upstream U.S. stream catalog did not surface matching entries for KABC, KCBS, KNBC, KTLA, or KCAL. This is only a finding about that catalog search; it does not prove official streams do not exist elsewhere.

## Existing source-audit baseline

The operator's TrueNAS read-only audit of the country playlists reported:

- United States: 1,492 entries.
- Mexico: 176 entries.
- Total: 1,668 entries.
- Provisional retained after excluding any category tags `Religious` and `Shop`: 1,515 entries.
- Excluded: 153 entries.
- Exact duplicate display names across the two source lists: Estrella Games, Estrella News, and Estrella TV.

These are playlist-entry counts, not counts of unique or working channels. The three duplicate names require URL and channel-identity comparison before choosing which entry to retain.

## Safety and validation boundary

- This document is a proposal and source-audit record, not an approved production playlist.
- No live Jellyfin tuner or TrueNAS configuration was changed.
- Do not add subscription-channel feeds unless their source and use are authorized.
- Test each candidate in an appropriate client, record date and outcome, and check geographic restrictions before marking it playback-tested.
- Preserve the existing NAVCore-TV playlist until a replacement has been reviewed and approved.
