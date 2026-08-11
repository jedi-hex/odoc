# Support

ODOC supports the latest macOS and Windows desktop releases listed on the
release page. Before opening an issue, record the ODOC version, operating
system and update channel. Logs may contain local paths or document titles;
remove private information before attaching them.

Alpha releases are intended for evaluation and may include data migrations.
Back up important local data before switching to Alpha.

## macOS: "ODOC.AI is damaged and can't be opened"

macOS builds are not yet signed with an Apple Developer ID or notarized, so
Gatekeeper quarantines the downloaded app and reports it as damaged. The app is
not actually corrupted. Remove the quarantine attribute after moving it to
Applications:

```bash
xattr -cr /Applications/ODOC.AI.app
```

Then open the app normally. This is required once per installed build, and
again after each update until signing and notarization are in place.

Only run this on a build you downloaded from this repository's Releases page.
