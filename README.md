# NAVCore-TV

**Version:** 1.0.0  
**Status:** Initial curated candidate release  
**Repository visibility:** Private

NAVCore-TV is a curated Live TV playlist project for Jellyfin and compatible IPTV clients. The initial lineup focuses on U.S. English-language channels and Mexican-market channels matching the requested interests.

## v1 selection policy

- Include U.S. channels that match the selected interests, prioritizing English-language programming.
- Include Mexican-market channels matching those interests; Spanish-language programming is expected.
- Exclude other foreign-market channels.
- Avoid duplicate entries by channel identity and stream URL.
- Keep Oregon/Portland local coverage as a known gap until suitable official sources are identified.
- La Liga match coverage is not included. Use an authorized broadcaster/provider; a public playlist entry is not evidence of sports rights.

## Repository layout

- `playlists/navcore-tv.m3u` — importable M3U candidate playlist.
- `config/channels.csv` — channel metadata and source URLs.
- `docs/validation.md` — validation status and operating notes.
- `epg/README.md` — future XMLTV/EPG notes.

## Important status notice

All v1 stream entries are **candidates, not playback-tested**. Inclusion in IPTV-org or this project does not establish that a stream is currently online, authorized for every viewer, geographically accessible, or compatible with Jellyfin. Validate each stream before relying on it.

This project does not include XMLTV guide data. M3U provides channel/stream entries; XMLTV is a separate source for schedules and program metadata.

## Sources

- [iptv-org source repository](https://github.com/iptv-org/iptv)
- [U.S. country playlist](https://iptv-org.github.io/iptv/countries/us.m3u)
- [Mexico country playlist](https://iptv-org.github.io/iptv/countries/mx.m3u)
- [Oregon subdivision playlist](https://iptv-org.github.io/iptv/subdivisions/us-or.m3u)

## Safety and maintenance

- Keep this repository private while stream URLs and source provenance are being reviewed.
- Do not commit subscription credentials, private URLs, API keys, passwords, or other secrets.
- Recheck upstream sources and test playback before promoting any entry to a verified state.
- Do not modify Jellyfin or server configuration as part of playlist repository updates.
