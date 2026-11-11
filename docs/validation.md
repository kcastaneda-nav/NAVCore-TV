# v1 validation status

**Release:** 1.0.0  
**Checked:** 2026-11-10  
**Overall status:** Candidate playlist; not playback-validated

## Required validation
1. Confirm source provenance and authorization for intended use.
2. Test each stream in VLC or Jellyfin.
3. Record playback success, geo-restrictions, and stability.
4. Check codecs, redirects, and stream behavior.
5. Recheck duplicate channel IDs and stream URLs.
6. Add XMLTV mappings only after selecting a reliable guide source.

## Known gaps
- The inspected IPTV-org Oregon subdivision playlist did not list Portland network affiliates or OPB. This is a source-coverage gap, not proof that official streams do not exist.
- No La Liga match feed is included. Use an authorized broadcaster/provider.
- No XMLTV/EPG data is included.
- Every initial stream remains a candidate and must not be described as working until tested.

## Status vocabulary
- `Candidate - not playback-tested`: possible source only.
- `Playback-tested`: tested in a named client on a recorded date.
- `Verified source`: official/authorized provenance checked separately from playback.
- `Blocked`: known geo, rights, access, or technical restriction.
- `Retired`: removed from the active playlist.
