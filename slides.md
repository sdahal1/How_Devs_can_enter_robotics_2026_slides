# Don’t Wait for the Hardware
*A Web Developer’s Path into Robotics*

Working copy of the deck content. Edit here, then hand this file back to update
`index.html`. 30 slides.

`index.html` was named `gateway_to_robotics_slides.html` until it was published
on GitHub Pages, which serves `index.html` at the root URL.

Heads up: this file has drifted. The HTML deck is at 40 slides — the full-bleed
image slides and several media slides were added straight to the HTML and never
written back here, so from slide 15 on the numbers here run 10 behind the deck.
Treat the HTML as the source of truth until this file is caught up.

## How to edit this file

Each slide is a `## Slide N — label` section built from labelled lines. Only
include the labels a slide actually uses, and delete the ones you don't need.

| Label | Becomes in HTML | Notes |
| --- | --- | --- |
| `Layout:` | `two-col`, `three-col`, `four-col`, `center`, `full`, or `cover` | `full` means no grid, content runs full width; `cover` is a full-bleed `Image:` with no text |
| `Eyebrow:` | `<div class="eyebrow">` | small uppercase orange label above the headline |
| `Headline:` | `<h2>` | add `Style: quote` for the oversized `.quote` treatment |
| `Lead:` | `<p class="muted">` | intro paragraph directly under the headline |
| `Bullets:` | `<ul class="bullets">` | markdown list, each item gets an orange dot |
| `Cards:` | `.card` inside the grid | `- **Title** — body`; prefix `[10k]` for a `.big-number` |
| `Diagram:` | `.diagram` box | value is the box's `<h3>` title |
| `Pipeline:` | `.pipe-node` chain | nodes split on `→`; `(parens)` become the small sub-label |
| `Body:` | `<p>` inside a diagram box | plain paragraph, no bullets |
| `Code:` | `.codebox` | use a fenced code block, whitespace is preserved as written |
| `Video:` | `.video-stage > video.video-player` | path to an mp4; add `Poster:` for the still shown before it loads. Portrait clips get `.media-portrait` so they sit beside a text column instead of stranded in the middle |
| `Caption:` | `.media-label` | short line above an `Image:` or `Video:` |
| `Spec list:` | `.spec-list` | `- **Name** — purpose`; name in orange on its own line, one-line purpose under it. Tighter than `Bullets:`, for naming the pieces of a stack next to a demo |
| `QR:` / `QR row:` | `.qr-solo` / `.qr-row` | one code centred, or three across; `QR label:` is the typed-out URL under it. Codes always go on a white `.qr-plate` or they stop scanning |
| `Timeline:` | `.timeline` / `.step` | numbered list, `**Title** — body` |
| `Closing:` | `<p class="mt40 muted">` | the takeaway line at the bottom of the slide |
| `Visual:` | decorative element | `orb` or `robot` |
| `Reveal:` | `.reveal-word` | big word that animates in on click or Enter; `Reveal cue:` is the placeholder text shown before it |

Anything after a `Reveal:` on the same slide (`Lead:`, `Cards:`) animates in
just behind the word. Labels render in the order you write them.

Formatting inside any text value: `**bold**` renders as orange highlight
(`<span class="orange">`). Left and right column content is separated by
`Left:` / `Right:` when a two-col slide puts different block types side by side.

The footer is identical on every slide and is not listed per slide:
`© 2026, Amazon Web Services, Inc. or its affiliates. All rights reserved.`
The one exception is the `cover` slide, where the copyright is part of the
artwork instead. Slide numbers are generated from the order of sections in this
file.

---

## Slide 1 — Title

Layout: cover
Image: images/slide1-img.png

This slide is a single full-bleed image. The artwork already contains the AWS
logo, the title, the subtitle, the presenter block and the copyright line, so
there is no HTML text on it. To change any of that wording, edit the image.

Baked into the artwork, recorded here so the deck content stays searchable:
- Title: Don’t wait for the hardware
- Subtitle: A Web Developer’s Path into Robotics
- Saurabh (Rob) Dahal
- Developer Advocate, Agentic AI
- AWS
- August, 2026

---

## Slide 2 — Hot take: courage

Layout: four-col
Eyebrow: Hot take
Headline: The number one skill for a web developer today is…

Reveal: courage.
Reveal cue: ask the room · click to reveal

Ask the room for answers first. Click anywhere, or press Enter, and the word
animates in, followed by the line and cards below it. Moving to another slide
resets it, so you can run the beat again.

Lead: Not a framework. Everything else got cheaper to attempt:

Cards:
- **AI coding assistants** — A patient expert for the domain you have not learned yet.
- **Lower barriers** — Advanced topics get more approachable every year.
- **GitHub repos** — Someone already solved a version of your problem. Borrow the idea.
- **Open source** — Real implementations you can read, run, and build on.

---

## Slide 3 — How it started

Layout: two-col
Eyebrow: How it started for me
Headline: A robotics and hardware hackathon for devs

Left:
Bullets:
- 
- No robotics or hardware background
- Personal interest - biomedical sciences, meditation. 
- found Emotibit device - (Used github MCP to search through github repos with agent) for hardware that you can program software with


Right:
Diagram: What the weekend forced
Pipeline: Hackathon (deadline) → Constraints (no hardware) → Simulate (fake the missing layer) → Demo (something that ran)

Closing: The hackathon never handed me hardware. It handed me a **deadline** — and that turned out to be the better gift.

---

## Slide 4 — The thesis

Layout: full
Eyebrow: The thesis
Headline: Your first robotics project does not need a robot.
Style: quote
Closing: It needs a developer willing to simulate sensors, stream data, interpret the world, and close the loop.
Visual: orb

---

## Slide 5 — The original goal

Layout: two-col
Eyebrow: I wasn’t trying to learn robotics
Headline: I wanted to build a meditation coaching app.

Left:
Bullets:
- Track physiological signals
- Understand meditation state
- Provide real-time coaching
- Make feedback feel personal and immediate

Right:
Diagram: Desired loop
Pipeline: Wearable → App → Coach

---

## Slide 6 — Gateway 1: sensors

Layout: two-col
Eyebrow: Gateway 1: sensors
Headline: The device: EmotiBit

Left:
Lead: A wearable bio-tracking device that can stream physiological and motion-related data.
Bullets:
- Heart-related signals
- Electrodermal activity
- Temperature
- Accelerometer / motion

Right:
Diagram: Developer translation
Body: A sensor is a continuous stream of imperfect measurements about the physical world.

---

## Slide 7 — The problem

Layout: three-col
Eyebrow: The problem
Headline: I didn’t have the device yet.
Lead: So instead of waiting, I did what developers do: I built around the missing dependency.

Cards:
- [1] **Ask AI** — What would this data roughly look like?
- [2] **Simulate it** — Generate believable sensor values over time.
- [3] **Stream it** — Make the app behave as if hardware exists.

---

## Slide 8 — Synthetic sensor data

Layout: two-col
Eyebrow: Fake it with AI help
Headline: Synthetic sensor data became my first simulator.

Left:
Code:
```
{
  "heartRate": 72,
  "eda": 0.41,
  "temperature": 33.8,
  "accel": { "x": 0.03, "y": -0.08, "z": 0.97 },
  "timestamp": 1786324214.382
}
```

Right:
Bullets:
- Sampling rate
- Noise
- Latency
- Dropouts
- State changes over time

---

## Slide 9 — Stream it

Layout: full
Eyebrow: Stream it with WebSockets
Headline: As far as the app knew, the device existed.
Pipeline: Synthetic EmotiBit → WebSocket stream → Backend processor → Live coach UI
Closing: Robotics concept unlocked: **sensor telemetry** + **real-time feedback loop**.

---

## Slide 10 — Gateway 2: perception

Layout: two-col
Eyebrow: Gateway 2: perception
Headline: Then I gave my computer eyes.

Left:
Lead: A basketball shot mechanics app that watches me shoot and gives feedback.
Bullets:
- Camera as a sensor
- OpenCV / pose estimation
- Landmarks instead of raw pixels
- Mechanics feedback from geometry

Right:
Diagram: Camera → pose → mechanics
Body: ⛹️‍♂️ → 🦴 → 📊
Style: oversized emoji row, centered

---

## Slide 11 — Inspiration and a barrier

Layout: three-col
Eyebrow: Inspiration — and a barrier
Headline: I found a basketball CV project… then saw the training cost.

Cards:
- [10k] **Annotated images** — Dataset work before the app becomes useful.
- [200] **Training epochs** — Model training becomes a project by itself.
- [48h] **GPU time** — Useful, but not the lowest-friction MVP.

Closing: The question changed from: **“How do I reproduce this model?”** to **“What problem am I actually solving first?”**

---

## Slide 12 — The pivot

Layout: two-col
Eyebrow: The pivot
Headline: Form feedback is body geometry over time.

Left:
Diagram: Custom detection
Pipeline: Dataset → Training → YOLO

Right:
Diagram: Pretrained pose
Pipeline: Camera → 33 landmarks → Geometry

Closing: AI did not just write code. It helped me **reframe the problem into one I could afford to solve.**

---

## Slide 13 — Zero-training MVP

Layout: three-col
Eyebrow: Zero-training MVP
Headline: Pretrained pose estimation + trigonometry + coaching rules

Cards:
- **Measure** — Elbow angle, knee bend, torso lean, wrist height, shoulder-hip alignment.
- **Segment** — Dip → rise → release → follow-through using wrist/hip movement over time.
- **Coach** — Flag the frame, explain the issue, give one correction at a time.

Code:
```
angle = arccos( dot(a,b) / (|a| * |b|) )

if elbow_angle_at_release > threshold:
    feedback = "Elbow may be flaring at release."
```

---

## Slide 14 — Pixels became perception

Layout: full
Eyebrow: Robotics concept unlocked
Headline: Pixels became perception.
Pipeline: Pixels → Person → Skeleton → State → Feedback
Closing: A robot does the same kind of transformation: raw sensor data → useful model of the world → action.

---

## Slide 15 — Shot analysis demo

Layout: two-col
Eyebrow: Demo
Headline: Perception, running on a phone clip.
Lead: One person, one camera, no depth sensor and no trained model. Everything on screen is derived from 33 landmarks per frame.

Left:
Bullets:
- Blue skeleton — the state estimate, redrawn every frame
- Joints — shoulder, elbow, hip, knee, ankle
- Bars — per-joint activation, green calm, red loaded
- The dip, the drive and the release all read off geometry

Closing: Same loop a robot runs: sense, estimate, decide, repeat.

Right:
Video: images/shot-analysis-edward1.mp4
Poster: images/shot-analysis-poster.jpg

The clip is 720x1280, so the slide uses the `.media-portrait` variant: the
video is pinned to 352px wide and the bullets take the rest of the row.

---

## Slide 16 — Shot analysis output

Layout: full
Eyebrow: The output
Headline: Numbers out, one correction at a time.
Lead: No neural net wrote this. Smoothed joint angles, differentiated twice, ranked by when each peak arrives.
Caption: Top: per-joint activation across the shot. Bottom: speed, acceleration, a score, and the timing fixes it ranked.
Image: images/slide-after-shooting-demo-img.png

The plot is 1752x1254 and capped at 620px tall so it clears the copyright line.
Keep the headline and the caption to one line each or the image starts covering
the footer.

---

## Slide 17 — The realization

Layout: three-col
Eyebrow: The realization
Headline: I had not built a robot — but I had learned pieces of the robotics stack.

Cards:
- **Sensors & data** — Wearables, simulated telemetry, WebSockets, noisy streams.
- **Perception** — Camera frames, landmarks, motion, geometry, interpreted state.
- **Feedback loops** — Observe, estimate, decide, respond, observe again.

---

## Slide 18 — What I realized

Layout: cover
Image: images/venn-diagram.png

Full-bleed artwork, no HTML text of its own. The file is 1536x1024, so it is
fitted whole with `letterbox` and the 125px strips either side are painted
`linear-gradient(90deg,#00010b,#00040f)` to match the artwork's own edges. The
copyright line stays on this one: the bottom-left of the artwork is empty at
that height.

Baked into the artwork, recorded here so the deck content stays searchable:
- Title: What I realized
- I started with a **meditation app** and a **basketball project**
- I ended up learning the core pieces of **robotics**
- **The robot wasn't the starting point. Curiosity was.**
- Starting from what you love can lead you to the bigger picture. That's how I found **robotics**.
- Venn circle — **Sensors & data**: collecting real-world information using sensors like PPG, IMU, GSR, temperature
- Venn circle — **Perception**: making sense of data through filtering, feature extraction, pattern recognition
- Venn circle — **Planning & control**: deciding what to do and how to do it, motion planning, control algorithms, feedback loops
- Where all three overlap — **Robotics**: the integration of perception, decision and action
- Closing line: from **curiosity** to understanding. From projects I love to skills that **build robots**.

This covers the same beat as slide 17 in richer form. Worth deciding whether the
three-card version still earns its place in front of it.

---

## Slide 19 — Gateway 3: robotics simulation

Layout: two-col
Eyebrow: Gateway 3: robotics simulation
Headline: Then I wanted to build a robot… and again, I had no hardware.

Left:
Lead: This time the answer was familiar:
Subhead: simulate again.
Bullets:
- Virtual robot
- Virtual sensors
- Virtual environment
- Real robotics concepts

Right:
Visual: robot

---

## Slide 20 — A simple simulated robot project

Layout: full
Eyebrow: A simple simulated robot project
Headline: Get from A to B without hitting anything.
Pipeline: Sensors (LiDAR / camera / IMU) → Perception (What is around me?) → Localization (Where am I?) → Planning (Where do I go?) → Control (How do I move?)
Closing: Now the pieces from the earlier projects have a robotics home.

---

## Slide 21 — Robot arm demo

Layout: two-col
Eyebrow: Demo
Headline: An arm I can command. Still no arm.
Lead: ArmLab — a simulated SO-101 behind an HTTP API. Every skill on the right is a tool the agent can call; here I am clicking them myself.

Left:
Video: images/robot-arm-demo.mp4
Poster: images/robot-arm-poster.jpg

Right:
Spec list:
- **Strands agent** — Turns one plain-language goal into ordered tool calls.
- **Amazon Bedrock** — The model doing the reasoning behind each call.
- **strands-robots** — Robot("so101") gives the agent hands. Sim or real, same code.
- **MuJoCo** — Physics stands in for the hardware. No GPU, no arm.
- **Skills** — park, scan, pick and place. Primitives the agent composes.
- **Joint & scene state** — Six joints and the cube, streamed back as feedback.

The source recording is `images/robot-arm-demo.mov`, 3024x1804 and 96MB. The mp4
in the deck is the same 41s downscaled to 1920 wide at 30fps, 2.5MB — same
`.mov` → `.mp4` step the EmotiBit demo went through. The slide uses
`.media-aside`: video pinned to 960px on the left, `.spec-list` on the right.

Note: slide 22 restates in a pipeline what this demo already shows running.
Worth deciding which one leads.

---

## Slide 22 — Where Strands fits

Layout: full
Eyebrow: Where Strands fits
Headline: Agentic AI can sit above the robot stack.
Pipeline: Human goal (“Inspect the room”) → Strands agent (plan & reason) → Robot tools (navigate / observe) → Policy / control (physical actions) → Simulator (feedback)
Closing: The agent decides **what** to do. The robot stack handles **how** movement happens.

---

## Slide 23 — Developer skill map

Layout: two-col
Eyebrow: A developer skill map
Headline: Your web skills transfer more than you think.

Left:
Bullets:
- WebSockets → sensor streams
- React state → system state
- APIs → hardware interfaces
- Event-driven systems → robot events
- Dashboards → mission control
- Debugging → robotics survival skill

Right:
Diagram: New concepts you learn progressively
Body: Coordinate frames, kinematics, signal processing, state estimation, perception, planning, control, ROS, simulation.

---

## Slide 24 — AI changed the entry cost

Layout: three-col
Eyebrow: AI coding assistants changed the entry cost
Headline: Not because they remove learning — because they help you cross unfamiliar boundaries.

Cards:
- **Translate** — “Explain ROS topics like I understand WebSockets.”
- **Substitute** — “What can I simulate so I do not need hardware yet?”
- **Reframe** — “Do I need a trained model, or can I use pretrained pose?”

---

## Slide 25 — The project ladder

Layout: full
Eyebrow: The project ladder
Headline: Start small. Grow toward real robots.

Timeline:
1. **Synthetic sensor dashboard** — Generate data, stream it, visualize it.
2. **Computer vision coach** — Camera → pose → geometry → feedback.
3. **Multi-sensor fusion** — Combine webcam + fake IMU + event logic.
4. **Simulated robot** — Virtual sensors, planning, control.
5. **Real hardware** — Replace simulated interfaces when ready.

---

## Slide 26 — Closing

Layout: three-col
Eyebrow: Closing
Headline: Don’t let the most expensive layer of a system stop you from learning the rest of the stack.
Style: quote

Cards:
- **Missing sensor?** — Simulate the data.
- **Missing model?** — Use pretrained perception.
- **Missing robot?** — Simulate the robot.

---

## Slide 27 — Final line

Layout: center
Headline: Your first robotics project doesn’t need a robot.
Style: quote
Closing: Simulate it. Build around it. Learn why it works. Then make it real.

---

## Slide 28 — Helpful resources

Layout: three-col
Eyebrow: Resources
Headline: Helpful resources to get started

QR row:
- **Kiro** — The only configurations you need for your first project. — images/qr-codes/qr-kiro-setup.svg — builder.aws.com
- **Agent Toolkit for AWS** — Wire it into Kiro, Codex, Claude Code or Cursor. — images/qr-codes/qr-agent-toolkit.svg — builder.aws.com
- **Strands Robots** — One Robot() call, in simulation or on hardware. — images/qr-codes/qr-strands-robots.svg — strandsagents.com/docs/labs/robots

---

## Slide 29 — Feedback

Layout: center
Eyebrow: Before you go
Headline: Tell me what landed.
QR: (internal survey code, not published)
QR label: (internal survey URL, not published)
Closing: Session feedback. It shapes what I build and talk about next.

This slide ran in the room and is commented out of `index.html`. The QR pointed
at an internal survey that is closed and unreachable from the public web, so
neither the code nor the URL is in this repo. Both are in the original deck if
you need to run the slide again at another event.

---

## Slide 30 — LinkedIn

Layout: center
Eyebrow: Stay in touch
Headline: Connect with me on LinkedIn.
QR: images/qr-codes/qr-linkedin.svg
QR label: linkedin.com/in/saurabhdahal
Closing: Saurabh (Rob) Dahal — Developer Advocate, Agentic AI, AWS.

### What the codes point at

Decoded from the files, so the labels can be checked against the destinations:

| File | Destination |
| --- | --- |
| `qr-kiro-setup.svg` | builder.aws.com — "The only Kiro configurations you need for your first project" |
| `qr-agent-toolkit.svg` | builder.aws.com — "Setting up the Agent Toolkit for AWS in Kiro and Codex, Claude Code and Cursor" |
| `qr-strands-robots.svg` | https://strandsagents.com/docs/labs/robots/ |
| `qr-linkedin.svg` | https://www.linkedin.com/in/saurabhdahal/ |

The feedback code is not listed. It resolved to an internal survey and is kept
out of this repo.

Both builder.aws.com URLs carry `trk` / `sc_channel` tracking parameters, which
is why only the domain is printed on the slide - the full string is far too long
to type off a screen.

Every code sits on a white `.qr-plate`. That is not decoration: the files are
black modules on white with their own quiet zone, and putting them straight onto
the dark slide breaks scanning. Re-check with a phone after resizing any of them.
