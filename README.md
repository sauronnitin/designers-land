<h1 align="center">Designers Land</h1>

<p align="center">A chill open-world park for designers on X.</p>

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
  <a href="https://sauronnitin.github.io/designers-land/"><img src="docs/day.png" alt="Designers Land in daylight: designers gathered in a meadow of trees, with Nitin's Oak in the middle" width="100%"></a>
</p>

## 🌤️ Day and night

<table>
  <tr>
    <td width="50%"><img src="docs/day.png" alt="The meadow in daylight" width="100%"></td>
    <td width="50%"><img src="docs/night.png" alt="The same meadow at night" width="100%"></td>
  </tr>
  <tr>
    <td align="center"><sub>Day</sub></td>
    <td align="center"><sub>Night</sub></td>
  </tr>
</table>

## 🌿 What is this

Every designer who replies to Nitin's intro post on X lands in an endless open-world meadow as a unique 3D character, styled from their public profile.

The world starts with Nitin and grows as real designers join, with a live counter.

## 💬 How to join

Reply to [@nitin_sauran](https://x.com/nitin_sauran)'s intro post on X. Real designers with design work on their timeline get added and receive their personal link.

## 🌱 A living land

Nitin stands at the center, next to a giant celebratory AI prompt box: "make it look like Apple but different". It bursts into confetti.

A gold "DESIGNERS LAND" monument with sweeping searchlights stands next to Nitin.

Walk up to Nitin and he waves and opens his card, with X and his website.

About 10 designer-meme artifacts are scattered around:

- Moving Day
- Purple Gradient Monolith
- Make It Pop
- Just One Small Change
- Pixel Perfect vs Close Enough
- The Exposure Jar
- Full-Stack Designer Signpost
- The Rectangle Benchmark
- Liquid Glass Puddle
- The LIVE Badge

You can swim in the ponds and the stream. Picnic blankets are trampolines. Day and night follow the visitor's local time.

## 🕹️ Controls

| | |
| --- | --- |
| Orbit | Drag |
| Zoom | Scroll or pinch |
| Walk | WASD or the arrow keys |
| Sprint | Shift |
| Jump | Space |
| Play | F |
| Speed | Slider from 0.5x to 4x |
| Open a designer | Click them to open their card |
| Quality | Under More |

## 🌸 Things to play with

- Fountain splash
- Ducks
- Butterflies
- Flowers to bloom and pick
- Birds
- Stone skipping
- Sitting
- Picnic blankets, which are trampolines
- The swing on Nitin's Oak
- Crit notes

## ⚙️ Under the hood

- Static `index.html` and `bundle.js`. No build step.
- Custom WebGL2 renderer with 3D/Mixed/2D adaptive modes and a software fallback.
- AI-generated 360 sky panorama, embedded in the bundle. `sky/` holds the source images.
- `.nojekyll` is included so GitHub Pages serves the files as they are.

## 💻 Run locally

Any static server will do. From the repo root:

```bash
npx serve .
```

or

```bash
python3 -m http.server
```

Open the address the server prints.

## ☀️ Credits

Designers Land is by [@nitin_sauran](https://x.com/nitin_sauran).

The park is live at [sauronnitin.github.io/designers-land](https://sauronnitin.github.io/designers-land/).
