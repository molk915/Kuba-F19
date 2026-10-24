# Verification — 2026-10-24

## Automated logic checks

`node test-story.cjs`: 16/16 passed after the story and readability revision.

Verified: campaign transitions with all dialogue gates; conversations stay on
screen until advanced; acceleration, steering, inertia and drift scoring;
collision damage; pause/resume; crash blackout, exact Dzwon and Bruski lines,
then actual car photo; every part choice gets mechanic dialogue; correct part
is charged after the dialogue; all torque actions and rust event; road failure
and retry; fault radio priority; 30 km completion through actual steering and
fault responses; every negotiation choice gets four dialogue lines, a persistent
reaction and updated price; duplicate-answer prevention; replay of responses;
ending, high-score persistence, PNG export link; restart; three easter eggs;
all nine local assets.

The automated test uses mocked DOM/Canvas. Its steering controller uses actual
physics updates and obstacle avoidance; it does not disable collision damage.

## Browser checks

Story revision: checked blackout Dzwon -> Bruski -> car photo in the real
browser, with manual advancement. Checked the buyer introduction, a selected
answer and his distinct response. Checked workshop introduction and the OLX
easter egg/return. Inspected conversation at a 390 px iframe width; controls
and full speech text remain visible. Browser error/warning logs were empty
after dialogue interactions using actual Web Audio nodes. Prior revision also
checked the menu, driving canvas, part placement and PNG preview. Saved-file
download in the in-app browser remains unverified; the explicit PNG link and
manual save path remain available.

Limitations: did not manually complete the entire timed campaign in-browser;
the end-to-end campaign is covered by the deterministic logic test. No physical
phone or subjective audio listening test was performed. All six supplied images
are local assets; no runtime backend or remote scripts/fonts are used.
