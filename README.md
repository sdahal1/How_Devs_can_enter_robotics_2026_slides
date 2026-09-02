# Don't wait for the hardware

A web developer's path into robotics. Conference deck presented at RenderATL in
August 2026 by Saurabh (Rob) Dahal, Developer Advocate for Agentic AI at AWS.

38 slides here. The deck ran with two more: an in-room feedback slide pointing at
an internal survey, and a closing contact slide. Both are commented out in
`index.html`, and the feedback QR is kept out of the repo because the image
encodes the internal URL. Uncomment the closing slide if you want it back.

Live deck: `https://sdahal1.github.io/REPO_NAME/`

## Running it locally

The deck is static HTML with an inline script and no build step or dependencies.
Open `index.html` in a browser, or serve the folder if you want the videos to
seek properly:

```
python3 -m http.server 8000
```

Then visit `http://localhost:8000`.

## Driving the deck

| Key | Action |
| --- | --- |
| Right arrow, space, page down | Next slide |
| Left arrow, page up | Previous slide |
| Enter, or a click anywhere | Trigger the reveal on slides that have one |
| F | Fullscreen |

Keys are ignored while a video has focus, so arrow keys scrub the clip instead of
skipping the slide.

The current slide number goes in the URL hash, so any slide is linkable and
survives a refresh. Slide 21 is `/#21`, and a number past the end lands on the
last slide. The deck reads the hash once on load, so the browser back button
steps through history without moving the deck.

Slides are a fixed 1600x900 stage scaled to fit the window, so the deck holds its
layout on a projector and on a phone.

## Files

| Path | Role |
| --- | --- |
| `index.html` | The deck. 40 slides, inline navigation script. |
| `slides.css` | All styling. The 1600x900 stage lives here. |
| `slides.md` | Editable source for the deck content, plus the label reference for each slide type. |
| `images/` | Slide artwork, demo videos, QR codes. |

`index.html` is the source of truth. `slides.md` runs behind it from slide 15 on,
which is noted at the top of that file.

## What the repo leaves out

`.gitignore` excludes the original screen recordings, which come to 138MB and are
not referenced by the deck: `robot-arm-demo.mov` at 92MB,
`demo-emotobit-app.mov` at 29MB, and `output_Edward 1.avi` at 17MB. It also
excludes `demo-emotobit-app.mp4`, the 3024x1804 60fps capture, because the deck
loads `demo-emotobit-app-web.mp4` instead: same clip at 1920x1146 and 30fps,
2.1MB rather than 24MB.

Keep those originals somewhere off this repo if you plan to re-cut the demos.
