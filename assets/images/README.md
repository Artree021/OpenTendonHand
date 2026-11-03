# Assets

Images used by the documentation. Keep them small; large media belongs in a
release asset, not in git history.

| Directory | Contents |
| --- | --- |
| `logo/` | Project mark (SVG), favicon exports |
| `images/` | Renders, photos, diagrams referenced by the docs |

## Naming

`<subject>-<view>-<rev>.<ext>` — e.g. `hand-front-r1.png`,
`finger-cutaway-r2.png`.

## Before committing an image

- Crop it; nobody needs 4000 px of desk.
- Export at 2× the displayed size at most.
- Prefer PNG for renders and diagrams, JPEG for photos.
- Add a caption in the document that uses it, and note the license
  (CC BY 4.0) if it is not obviously part of the docs.
