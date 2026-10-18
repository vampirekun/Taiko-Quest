# Static frontend experiment

This branch adds an **experimental** static mode to the Taiko Web frontend. It does not replace the Flask/MongoDB/Redis server and does not include any song files.

## Try it

Serve the repository's `public/` directory as the document root of a local static HTTP server (not `file://`). Open `/` with `?static=1` appended, for example `http://localhost:8080/?static=1`.

The static mode substitutes three server endpoints with JSON manifests under `/static/`: config, categories, and song catalogue. Accounts, online song catalogue, Google Drive integration, and multiplayer are not available in this mode. The original frontend's **local custom-song import** is the intended way to load legally obtained chart/audio files. In static mode the picker is switched to multi-file selection (including on Android-based browsers), so select the `.tja` chart and its matching audio file together. This mobile picker path is not yet verified on Meta Quest.

## Important limitations

- This is only a first bootability spike; it has not yet been verified in a browser or Meta Quest.
- The paths currently assume the static site is hosted at the domain root. Hosting under a subpath requires a follow-up base-path change.
- No audio/chart assets are bundled. A song must be imported locally by the user.
- This does not yet connect controller motion from Taiquest to the game's `GameInput`; that integration is a separate step after static startup works.
- Do not deploy this branch as the production game yet.
