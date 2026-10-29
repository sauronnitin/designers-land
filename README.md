<h1 align="center">Designers Land</h1>

<p align="center">A cozy low-poly 3D meadow of real designers on X, hosted by Nitin Sauran.</p>

<p align="center">
  <a href="https://sauronnitin.github.io/designers-land/"><img alt="Live on GitHub Pages" src="https://img.shields.io/static/v1?label=Live%20on&amp;message=GitHub%20Pages&amp;color=2F9E6B&amp;style=flat&amp;logo=githubpages&amp;logoColor=white"></a>
  &nbsp;
  <a href="https://x.com/nitin_sauran"><img alt="Made by @nitin_sauran" src="https://img.shields.io/static/v1?label=Made%20by&amp;message=%40nitin_sauran&amp;color=1D9BF0&amp;style=flat&amp;logo=x&amp;logoColor=white"></a>
  &nbsp;
  <img alt="No build step" src="https://img.shields.io/badge/No_build_step-C48A3A?style=flat">
  &nbsp;
  <img alt="WebGL2" src="https://img.shields.io/badge/WebGL2-4F6BED?style=flat">
</p>

<p align="center">
  <a href="https://sauronnitin.github.io/designers-land/">Open the live park</a>
</p>

<p align="center">
  <img src="docs/day.png" alt="The meadow in daylight" width="49%">
  <img src="docs/night.png" alt="The meadow at night" width="49%">
</p>

<p align="center"><sub>Reference shots of the meadow, day and night. The live roster is whoever is listed in <a href="data/designers.json">data/designers.json</a>.</sub></p>

## Contents

- [What it is](#what-it-is)
- [Joining](#joining)
- [Controls](#controls)
- [Nitin's spot](#nitins-spot)
- [Cards](#cards)
- [Here now and live chat](#here-now-and-live-chat)
- [Feedback](#feedback)
- [The #tour demo](#the-tour-demo)
- [Phones](#phones)
- [On the map](#on-the-map)
- [Data files](#data-files)
- [How it's built](#how-its-built)
- [Privacy](#privacy)
- [Run it locally](#run-it-locally)
- [Credits](#credits)

## What it is

[Designers Land](https://sauronnitin.github.io/designers-land/) is a cozy low-poly 3D open world of real designers on X. [Nitin Sauran](https://x.com/nitin_sauran) (@nitin_sauran) is the host, and he stands at the center.

The world is one open meadow. There are no paths and no zones. Hills, pits, water, groves, and flowers fill the ground, and the land grows new elements as more designers join. You can swim in the ponds and the stream. Picnic blankets are trampolines.

Day and night follow each visitor's local clock. A `time=day`, `time=night`, or `time=dusk` query on the page can pin the light for a recording.

## Joining

Reply to [Nitin's intro post on X](https://x.com/nitin_sauran/status/2115843607760695516).

Any visible design work qualifies: a design post, a bio, or a portfolio link. There is no follower minimum and no age minimum. Pure connect-farming, or self-promo with no design work, is declined.

Approved designers get three things:

- A character built from their real X profile and posts.
- A screenshot reply on X.
- A personal link that walks their own character.

Plain visitors walk a Visitor character. A personal `#me=` link walks you as yourself.

## Controls

| | |
| --- | --- |
| Walk | WASD or the arrow keys. The on-screen arrow pad does the same thing. |
| Sprint | Hold Shift. |
| Jump | Space. |
| Play with something nearby | F. |
| Orbit | Drag. |
| Zoom | Scroll, or the on-screen + and - buttons. |
| Speed | The walk-speed slider, from 0.5x to 4x. The choice is remembered in the browser. |
| See a card | Click a person. |
| Find someone | The Focus menu lists people by X handle. |
| Meet Nitin | The Meet Nitin button frames him and says hello. |
| Reset view | Reset view puts the camera back. |
| More | Opens Quality (Auto, 3D, Mixed, or 2D). |

Walking, jumping, or pressing F also claims the Visitor body if you arrived without a personal link.

## Nitin's spot

Nitin's character is a studio bomber with a pencil behind the ear, and a UFO with a cow orbiting him. His hair and beard follow his profile. Walk up to him, or click him, and he waves and says "Hi, good to see you!" His real X card then slides open: avatar, banner, bio, counts, the top 6 posts by engagement, and his website.

Next to him is a gold DESIGNERS LAND monument in the style of the 20th Century Fox logo. Searchlights sweep behind the letters, and gold and white sparkles drift around it. The joke AI prompt, "make it look like Apple but different", is fixed on the base. Click the monument and the celebration plays. It also plays on its own from time to time.

## Cards

A card is public X data only. The park does not write a generated blurb for anyone.

What you see is the profile that was synced into the repo: name, handle, bio, counts, posts, and website, when X has them.

## Here now and live chat

The "here now" count in the top bar is live presence. Visitors and the chat share a public MQTT connection over secure WebSockets. The client tries HiveMQ first (`wss://broker.hivemq.com:8884/mqtt`) and falls back to the Eclipse Mosquitto test broker (`wss://test.mosquitto.org:8081/mqtt`).

Chat sits at the bottom right. Lines also appear as speech bubbles over people in the world. A visitor who has not been given a name shows up as an anonymous animal (Capybara, Axolotl, and the rest of that list). The animal and its color stay in the browser.

Moderation runs in the browser, on the way out and again when a line arrives:

- 200 characters maximum.
- At most one message every 3 seconds, and at most 5 messages in 30 seconds.
- A repeat of one of your last few lines is dropped.
- Links are neutralized so they are not clickable.
- Profanity is masked.
- You can mute a person. Their later lines are ignored on your machine.
- Messages are drawn as text. They are not rendered as HTML.

This moderation is client-side only. There is no server checking messages. A modified client can skip the filters, and the brokers are public, so treat the room as an open channel.

If the socket is down, the composer says chat is offline.

## Feedback

Feedback is 1 to 5 stars, plus an optional note ("What should Nitin add, fix or keep?"). **Send as DM** opens a prefilled X direct message to Nitin in a new tab. Nothing is stored here. There is no backend.

The Feedback button is hidden during `#tour`.

## The #tour demo

`#tour` on the URL is a hidden, scripted camera demo for clips. That hash does not open the presence connection, so a tour does not count in "here now" and does not join chat.

## Phones

The same page runs on a phone. The on-screen pad, zoom buttons, and speed slider are there for touch. When the client decides it is on a phone, or WebGL2 is missing, the renderer steps down. Quality can also be set by hand to 3D, Mixed, or 2D. With no WebGL2 the view is software-rendered.

## On the map

Press F near a piece, or click it, to play its joke. Landmarks and designer-meme artifacts are both on the ground.

### Landmarks

| Piece | What it is |
| --- | --- |
| The Monument | A golden monument with one very clear brief. |
| Lasso Ranch | A fenced paddock, marching ants for a rope, and one very selected sheep. |
| Bezier Bridge | A pen-tool bridge whose handles are still showing. |
| Gradient Mesh Hot Spring | A warm pool of gradient-mesh water, steam at 40% opacity. |
| Color Picker Orchard | Trees tagged with hex codes, and a giant eyedropper. |
| 8pt Grid Garden | Pink layout columns, shrubs trimmed to the nearest 8. |
| Dark Mode Cave | A cave that flips light and dark. The bats only use dark mode. |
| Pen Tool Totem | A giant pen nib and a crowd of accidental anchor points. |
| Component Library Silo | A stack of main components, each an instance of the one below. |
| Contrast Lighthouse | A striped light looking for gray text on white. |
| Stock Photo Campfire | Stock-photo people, salads, and handshakes. |
| Moodboard Meadow | Easels of inspiration the finished work will not resemble. |

### Designer memes

| Piece | What it is |
| --- | --- |
| Moving Day | Boxes of components on the way to Claude, Cursor, and a terminal. |
| Purple Gradient Monolith | The AI landing-page starter pack: purple gradient, three icon cards, Inter, and a rocket. |
| The LIVE Badge | A pulsing green LIVE pill. Live what is left open. |
| Make It Pop | A balloon that does exactly what the client asked. |
| Just One Small Change | Dominoes labeled "quick tweak". |
| Pixel Perfect vs Close Enough | Two towers: the spec, and what shipped. |
| The Exposure Jar | Where "great exposure" payments go. It is mostly air. |
| Full-Stack Designer Signpost | A sign that points at design, code, prompts, video, and SEO all at once. |
| The Rectangle Benchmark | Two thousand rectangles, still waiting to see which tool melts. |
| Liquid Glass Puddle | A wobbly glass blob. Expensive, and slightly unreadable. |

## Data files

These are the files the page reads. Hourly syncs replace `data/host.json` in place. Approved designers are added under `data/`.

### `data/host.json`

Nitin's card, synced from X about once an hour by his assistant automation, which commits the new file to this repo. The current shape is the wider card with the top 6 posts. `version` is the sync hash. The v8 file shipped as `cf7218ba2d09`. A later sync replaces that hash.

Fields in the file today:

| Field | Meaning |
| --- | --- |
| `schema` | Card schema. Currently `1`. |
| `version` | Sync hash for this snapshot. |
| `userId` | Nitin's numeric X user id. |
| `name`, `handle`, `profileUrl` | Display name, X handle, profile URL. |
| `bio`, `discipline`, `location` | Bio line, a short discipline read from the profile, and location. |
| `website`, `websiteLabel` | Site URL and the short label shown on the card. |
| `followers`, `following`, `postCount`, `likes` | Public counts. |
| `joined`, `latestPostAt` | ISO timestamps. |
| `avatarSrc`, `bannerSrc` | `./data/avatar.jpg` and `./data/banner.jpg`. |
| `avatarColors`, `bannerColors` | A few sampled colors from those images. |
| `keywords` | Short words taken from the profile. |
| `speech` | A greeting line available when you are not standing on top of him. |
| `feel` | Look direction for the character: `mood`, `shapeLanguage`, `texture`, `palette`, `mediaStyle`. |
| `topPosts` | The six posts with the most engagement. |

Each post in `topPosts` has `id`, `url`, `date`, `text`, `kind`, `mediaType`, `likes`, `replies`, `reposts`, and, when there is an image, `imageSrc` (under `data/media/`) plus `imageColors`.

### `data/designers.json`

The list of approved designers, plus a `version` for the file. Each entry uses the same public profile fields as the host card, with these differences:

- There is an `admission` note (how they were added, and when).
- There is no `schema`, `speech`, `likes`, or per-person `version`.
- `avatarSrc` and `bannerSrc` point at `data/designers/<folder>/`.
- `topPosts` use the same post fields. Images live next to that person's avatar, not in `data/media/`.

The folder name is the handle in lowercase. Right now the file lists @itzSaasified, with images in [`data/designers/itzsaasified/`](data/designers/itzsaasified/).

### Media

| Path | What it is |
| --- | --- |
| `data/avatar.jpg` | Nitin's avatar. |
| `data/banner.jpg` | Nitin's banner. |
| `data/media/<post id>.jpg` | Images for Nitin's posts. |
| `data/designers/<handle>/avatar.jpg` | That designer's avatar. |
| `data/designers/<handle>/banner.jpg` | That designer's banner. |
| `data/designers/<handle>/<post id>.jpg` | Images for that designer's posts. |

`sky/` holds source frames for the day and night sky. The running page uses the copy baked into `bundle.js`.

## How it's built

This is a static site. GitHub Pages serves the `main` branch from the repository root. [`.nojekyll`](.nojekyll) is an empty file so Pages does not run Jekyll.

[`index.html`](index.html) is a shell: a title, a viewport, and one script tag. It loads `./bundle.js?v=` plus the first 8 characters of the bundle's sha256, so browsers pick up a new build instead of a cached one. The live page currently asks for `bundle.js?v=e072163c`.

`bundle.js` is a prebuilt file. Do not rebuild it from this repo. Inside it is a custom WebGL2 renderer with 3D, Mixed, and 2D modes, and a software fallback when WebGL2 is unavailable.

Two of Nitin's assistant automations write data and commit it here:

- The X sync refreshes `data/host.json` about once an hour.
- The reply watcher adds approved designers and their media.

There is no application server for chat, presence, or feedback.

## Privacy

Only public X data is copied into this repo and shown on the cards. Designers can ask to be removed by DMing [@nitin_sauran](https://x.com/nitin_sauran).

Chat and presence go through public MQTT brokers. Do not type anything there that you would not say in a public room.

## Run it locally

Any static file server works. From the repo root:

```bash
npx serve .
```

or

```bash
python3 -m http.server
```

Open the address the server prints. Chat and the here-now count need a network path to the public brokers. The meadow itself does not.

## Credits

Designers Land is by [Nitin Sauran](https://x.com/nitin_sauran).

The park is live at [sauronnitin.github.io/designers-land](https://sauronnitin.github.io/designers-land/).

### Versions

- **v6.** The gold monument and the sharper look.
- **v7.** Live chat, and star feedback that opens a DM.
- **v8.** Nitin's remake (studio bomber, profile-matched hair and beard), the prompt box fixed on the monument, the wider host card, and the top 6 posts.
