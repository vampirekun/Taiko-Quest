# Static frontend experiment

This branch adds an **experimental** static mode to the Taiko Web frontend. It does not replace the Flask/MongoDB/Redis server and does not include song files.

## Try it

Serve the repository's `public/` directory as the document root of a local static HTTP server (not `file://`). Open `http://localhost:8080/?static=1`. The static HTML entry point is `public/index.html`; the same folder can be copied beneath a subdirectory such as `/taiquest/taiko-web/`.

In static mode the frontend loads config, categories, and song manifests from `static/*.json`, and rewrites its root-relative frontend requests to the current subdirectory. Asset and song base URLs are relative to the static deployment directory. Accounts, online song catalogue, Google Drive integration, and multiplayer are not available. The original frontend's local custom-song import is intended to load legally obtained chart/audio files. Select the `.tja` chart and its matching audio file together.

## Important limitations

- This is a bootability experiment and has **not** yet been verified in a browser or Meta Quest.
- No song charts or music are bundled; users must import their own compatible files.
- The static frontend is not yet connected to Taiquest's WebXR controller hit events.
- Rendering this frontend on the 3D cabinet still needs a real integration; an iframe cannot simply be drawn into a WebGL texture.
- Static mode may still encounter server-only code paths. Do not deploy as a finished game or production replacement.
