<div align="center">

<img src="assets/logo.svg" width="110" alt="ElectroIoT logo" />

# Asset Reference

**Every graphic, widget and colour used by the ElectroIoT profile — what it is,
where it lives, and how to change it.**

<img src="https://img.shields.io/badge/SVG%20ASSETS-21-00C8FF?style=for-the-badge&labelColor=050816" alt="21 SVG assets" />
<img src="https://img.shields.io/badge/ANIMATION-SMIL%20only-00FFD5?style=for-the-badge&labelColor=050816" alt="SMIL only" />
<img src="https://img.shields.io/badge/DEPENDENCIES-Zero-0066FF?style=for-the-badge&labelColor=050816" alt="Zero dependencies" />

</div>

<img src="assets/divider.svg" width="100%" alt="" />

## Contents

1. [Design system](#design-system)
2. [Core SVG assets](#core-svg-assets)
3. [Capability cards](#capability-cards)
4. [Raster assets](#raster-assets)
5. [Generated assets](#generated-assets)
6. [External widgets](#external-widgets)
7. [Animation inventory](#animation-inventory)
8. [Technical constraints](#technical-constraints)
9. [Authoring a new asset](#authoring-a-new-asset)
10. [Licensing and attribution](#licensing-and-attribution)

<img src="assets/divider.svg" width="100%" alt="" />

## Design system

### Palette

| Token | Hex | RGB | Role |
| :--- | :--- | :--- | :--- |
| Primary | `#00C8FF` | `0, 200, 255` | Titles, borders, primary glow |
| Secondary | `#0066FF` | `0, 102, 255` | Depth, gradients, secondary strokes |
| Accent | `#00FFD5` | `0, 255, 213` | Highlights, pulses, live indicators |
| Background | `#050816` | `5, 8, 22` | Page and scene background |
| Cards | `#111827` | `17, 24, 39` | Panel and card fills |
| Text | `#EAF6FF` | `234, 246, 255` | Body copy and headings |

Two supporting shades appear inside the illustrations and are derived from the
palette rather than added to it:

| Shade | Hex | Role |
| :--- | :--- | :--- |
| Panel fill | `#0b1730` | Interior of chips, devices and consoles |
| Deep panel | `#0f2145` | Secondary interior surfaces |

### Gradient recipes

| Name | Stops | Used in |
| :--- | :--- | :--- |
| Neon sweep | `#0066FF` → `#00C8FF` → `#00FFD5` | Hero frame, logo, dividers |
| Card edge | `#00FFD5` → `#0066FF` | Card borders |
| Glass fill | `#00C8FF` 14% → `#111827` 55% → `#0066FF` 10% | Hero glass panel |
| Chart area | `#00FFD5` 42% → transparent | Trading and energy charts |
| Panel (PV) | `#0d3f8a` → `#0a2a5e` → `#061a3a` | Solar photovoltaic panels |

### Typography

All text is rendered inside the SVGs with system font stacks, so nothing has to
be downloaded and nothing shifts while loading.

| Purpose | Stack | Weight | Size range |
| :--- | :--- | :--- | :--- |
| Display / wordmark | `'Segoe UI', system-ui, sans-serif` | 800 | 17–44 px |
| Section labels | `'Segoe UI', system-ui, sans-serif` | 600 | 8.5–13 px, letter-spaced |
| Body inside cards | `'Segoe UI', system-ui, sans-serif` | 400–600 | 10.5 px |
| Code / telemetry | `'Consolas', 'SF Mono', monospace` | 400–700 | 7–17 px |

### Geometry

| Property | Value |
| :--- | :--- |
| Card radius | 16 px (cards), 18 px (illustrations), 22 px (hero glass) |
| Border width | 1.5–1.6 px |
| Glow spread | `stdDeviation` 3 (small), 4.5 (medium), 10 (large) |
| Card size | 380 × 150 |
| Illustration size | 440 × 280 |

<img src="assets/divider.svg" width="100%" alt="" />

## Core SVG assets

All paths are relative to the repository root.

### `assets/hero.svg`

| Property | Value |
| :--- | :--- |
| Dimensions | 1200 × 420 |
| Used in | README hero section |
| Animated | Yes — 40+ concurrent SMIL animations |

The single most complex asset. Composited from ten layers:

| Layer | Contents |
| :--- | :--- |
| Base | Sky gradient, 40 px grid, city haze |
| Floor | Three scan lines drifting toward the viewer |
| Skyline | Eight towers, blinking windows, two pulsing beacons |
| Circuits | Six traces with energy pulses and solder pads |
| Solar | Two skewed PV panels, mounting legs, rising energy sparks |
| ESP32 | Module with pins, shield can, die and radiating Wi-Fi arcs |
| AI mesh | Six neurons, nine synapses, three travelling activations |
| Trading | Candlesticks, animated equity curve, live price marker |
| Glass card | Avatar ring, wordmark, typing text, five chips, status pill |
| Atmosphere | Eight floating particles, scanline sweep, vignette |

The typing effect uses a `clipPath` whose rectangle width is animated, plus a
caret whose `x` follows the same keyframes. Three phrases cycle over 14 seconds.

### `assets/footer.svg`

| Property | Value |
| :--- | :--- |
| Dimensions | 1200 × 220 |
| Used in | README footer, setup guide footer |
| Animated | Yes |

Three parallax wave layers translating at 18 s, 12 s and 8 s, a neon crest
outline, a glowing horizon line, five rising sparks and a signature line. The
wave path spans two full periods so a −600 unit translate loops seamlessly.

### `assets/divider.svg`

| Property | Value |
| :--- | :--- |
| Dimensions | 1200 × 40 |
| Used in | Between every README section (16 instances) |
| Animated | Yes |

A gradient rail with a 220 px pulse crossing every 5 seconds, four circuit stubs
with solder pads, and a rotating centre diamond.

### `assets/background.svg`

| Property | Value |
| :--- | :--- |
| Dimensions | 1200 × 600 |
| Used in | Project 06 illustration; available as a section backdrop |
| Animated | Yes |

Hex mesh over a grid, a pulsing horizon sun, nine perspective rays, three racing
floor lines, a nine-node constellation, five drifting particles and a diagonal
light sweep.

### `assets/logo.svg`

| Property | Value |
| :--- | :--- |
| Dimensions | 512 × 512 (square) |
| Used in | Section headings, support card, setup guide, favicon source |
| Animated | Yes — rotating orbit, pulsing bolt, signal arcs |

Hexagonal circuit shield with an energy bolt, four internal traces with pads,
and three orbiting satellite nodes. Square canvas so it doubles as an avatar.

### Illustrations

| File | Size | Subject | Key animation |
| :--- | :--- | :--- | :--- |
| `assets/solar.svg` | 440 × 280 | PV array, hybrid inverter, battery bank | Photons falling, DC packet along the bus, cell shimmer |
| `assets/ai.svg` | 440 × 280 | Four-layer neural network, inference console | Three activations traversing the mesh, confidence meter |
| `assets/iot.svg` | 440 × 280 | ESP32 gateway, five smart devices | Broadcast rings, MQTT payloads on every link |
| `assets/trading.svg` | 440 × 280 | Candlestick chart, order book, KPI strip | Equity curve draw-on, crosshair sweep, depth bars |
| `assets/laravel.svg` | 440 × 280 | Request pipeline, queue workers, artisan console | Request packet along the pipeline, worker pulses |

<img src="assets/divider.svg" width="100%" alt="" />

## Capability cards

Eleven cards in `assets/cards/`, all 380 × 150, sharing one template:
rounded panel, gradient border, outer glow, 52 × 52 icon tile, title, two
description lines, three technology chips, and an animated bottom accent bar.

| File | Title | ID prefix | Accent |
| :--- | :--- | :--- | :--- |
| `solar-bridge.svg` | Solar Bridge | `sb-` | Accent → Secondary |
| `home-assistant.svg` | Home Assistant | `ha-` | Primary → Secondary |
| `trading-dashboard.svg` | Trading Dashboard | `td-` | Accent → Primary |
| `ai-automation.svg` | AI Automation | `aia-` | Secondary → Accent |
| `laravel-crm.svg` | Laravel CRM | `lc-` | Primary → Secondary |
| `esp32.svg` | ESP32 Projects | `e32-` | Accent → Secondary |
| `bms-monitoring.svg` | BMS Monitoring | `bms-` | Accent → Primary |
| `deye-inverter.svg` | Deye Hybrid Inverter | `dy-` | Secondary → Accent |
| `mqtt.svg` | MQTT | `mq-` | Primary → Accent |
| `docker.svg` | Docker | `dk-` | Secondary → Primary |
| `linux.svg` | Linux | `lx-` | Accent → Secondary |

> **ID prefixes matter.** When several SVGs render on one page, duplicate
> gradient or filter IDs cause one card to inherit another's colours. Every new
> card needs its own prefix.

Each card's sheen sweep is offset by 0.5 s from the previous one so the grid
shimmers in sequence rather than flashing at once.

<img src="assets/divider.svg" width="100%" alt="" />

## Raster assets

| File | Dimensions | Purpose |
| :--- | :--- | :--- |
| `assets/preview.png` | 1280 × 640 | Social preview card for link unfurls |

Set it under **Settings → General → Social preview → Upload an image**. This is
the only raster file in the repository; everything else is vector.

<img src="assets/divider.svg" width="100%" alt="" />

## Generated assets

These are produced by CI and must not be edited by hand.

### Snake animation — `.github/workflows/snake.yml`

Published to the `output` branch:

| File | Theme |
| :--- | :--- |
| `github-snake.svg` | Light |
| `github-snake-dark.svg` | Dark, neon-blue snake — the default in the README |
| `github-snake.gif` | Animated GIF fallback |

Referenced as:

```
https://raw.githubusercontent.com/electroiot/electroiot/output/github-snake-dark.svg
```

### Metrics panels — `.github/workflows/metrics.yml`

Committed to `metrics/` on `main`:

| File | Plugin | Embedded in |
| :--- | :--- | :--- |
| `metrics.svg` | base, languages, lines | Latest Activity |
| `metrics.achievements.svg` | `achievements` | Achievements |
| `metrics.languages.svg` | `languages` indepth | GitHub Analytics |
| `metrics.isocalendar.svg` | `isocalendar` | GitHub Analytics |
| `metrics.calendar.svg` | `calendar` | GitHub Analytics |
| `metrics.lines.svg` | `lines` | GitHub Analytics |
| `metrics.habits.svg` | `habits` | GitHub Analytics |
| `metrics.stars.svg` | `stars`, `stargazers` | GitHub Analytics |

<img src="assets/divider.svg" width="100%" alt="" />

## External widgets

Every third-party URL used in the README, with the parameters that carry the
palette. Replace `electroiot` with your own username when forking.

### Animated typing headline

```
https://readme-typing-svg.demolab.com?font=Fira+Code&weight=700&size=26&pause=900&color=00C8FF&background=05081600&center=true&vCenter=true&width=900&height=70&lines=...
```

| Parameter | Value | Notes |
| :--- | :--- | :--- |
| `font` | `Fira+Code` | Any Google Font, `+` for spaces |
| `color` | `00C8FF` | No `#` |
| `background` | `05081600` | 8-digit hex; trailing `00` is transparent |
| `lines` | semicolon-separated | URL-encode: space `+`, `&` as `%26` |
| `pause` | `900` | Milliseconds held before deleting |

Twelve roles cycle: Full Stack Developer, Laravel Expert, IoT Developer, Solar
Automation Engineer, Home Assistant Builder, AI Developer, ESP32 Firmware
Engineer, Open Source Contributor, Linux & Docker Practitioner, Trading
Dashboard Architect, Crypto Automation.

### GitHub Readme Stats

```
https://github-readme-stats.vercel.app/api?username=electroiot&show_icons=true&count_private=true&include_all_commits=true&hide_border=true&bg_color=050816&title_color=00C8FF&text_color=EAF6FF&icon_color=00FFD5&ring_color=00C8FF&border_radius=16
```

Top languages, compact and donut layouts:

```
https://github-readme-stats.vercel.app/api/top-langs/?username=electroiot&layout=compact&langs_count=10&hide_border=true&bg_color=050816&title_color=00C8FF&text_color=EAF6FF&border_radius=16&hide=html,css,scss,blade
https://github-readme-stats.vercel.app/api/top-langs/?username=electroiot&layout=donut&langs_count=8&...
```

### Streak stats

```
https://streak-stats.demolab.com?user=electroiot&hide_border=true&background=050816&stroke=00C8FF&ring=00C8FF&fire=00FFD5&currStreakLabel=00FFD5&currStreakNum=EAF6FF&sideNums=EAF6FF&sideLabels=00C8FF&dates=8FB3D9&border_radius=16
```

Note the parameter is `user`, not `username`.

### Activity graph

```
https://github-readme-activity-graph.vercel.app/graph?username=electroiot&bg_color=050816&color=00C8FF&line=00FFD5&point=EAF6FF&area_color=0066FF&title_color=00C8FF&area=true&hide_border=true&custom_title=...
```

### Trophies

```
https://github-profile-trophy.vercel.app/?username=electroiot&theme=algolia&no-frame=true&no-bg=true&column=7&margin-w=8&margin-h=8
```

`no-bg=true` lets the GitHub page background show through, which suits both
light and dark readers.

### Profile views

```
https://komarev.com/ghpvc/?username=electroiot&label=PROFILE+VIEWS&color=00C8FF&style=for-the-badge
```

### Skill icons

```
https://skillicons.dev/icons?i=laravel,vue,tailwind,mysql,redis,docker&theme=dark&perline=10
```

Categories used in the README:

| Section | Slugs |
| :--- | :--- |
| Languages | `php,python,js,ts,cpp,c,bash,lua,go,rust` |
| Frameworks | `laravel,vue,nuxtjs,tailwind,bootstrap,livewire,alpinejs,fastapi,flask,express` |
| Backend | `laravel,php,python,nodejs,redis,rabbitmq,graphql,nginx,apache` |
| Frontend | `html,css,js,ts,vue,tailwind,sass,vite,threejs,figma` |
| Cloud | `aws,cloudflare,digitalocean,vercel,netlify,githubactions,nginx,linux` |
| Databases | `mysql,postgres,sqlite,redis,mongodb,influxdb,prisma` |
| Embedded | `arduino,raspberrypi,cpp,c,python,platformio,linux` |
| Automation | `homeassistant,grafana,prometheus,nodered,mqtt,docker,python` |
| DevOps | `docker,githubactions,git,linux,bash,nginx,ansible,kubernetes,cloudflare` |
| Tools | `git,github,vscode,phpstorm,postman,figma,notion,markdown,regex,stackoverflow` |

### Shields.io

Two badge shapes are used:

```
https://img.shields.io/badge/LABEL-MESSAGE-00C8FF?style=for-the-badge&labelColor=050816&logo=github&logoColor=00FFD5
https://img.shields.io/badge/LABEL-MESSAGE-00C8FF?style=flat-square&labelColor=050816
```

Dynamic counters read the public GitHub API:

```
https://img.shields.io/github/followers/electroiot?label=FOLLOWERS&style=for-the-badge&color=0066FF&labelColor=050816&logo=github&logoColor=00FFD5
https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fapi.github.com%2Fusers%2Felectroiot&query=%24.public_repos&label=REPOSITORIES&style=for-the-badge&color=00FFD5&labelColor=050816
```

Escaping rules for badge text: `-` → `--`, `_` → `__`, space → `%20` or `_`.

<img src="assets/divider.svg" width="100%" alt="" />

## Animation inventory

Every animation is declarative SMIL inside the SVG. No JavaScript, no CSS
keyframes, no external stylesheet.

| Technique | Element | Where it is used |
| :--- | :--- | :--- |
| Attribute tween | `<animate>` | Opacity pulses, radius breathing, width meters |
| Transform tween | `<animateTransform>` | Rotating rings, drifting waves, moving gradients |
| Path following | `<animateMotion>` | Data packets on circuits, activations across the AI mesh |
| Stroke reveal | `stroke-dashoffset` | Chart draw-on, energy pulses along traces |
| Clip reveal | animated `clipPath` rect | Typewriter text in the hero |

### Timing

| Asset | Longest loop | Concurrent animations |
| :--- | :--- | :--- |
| `hero.svg` | 16 s (particles) | ~46 |
| `background.svg` | 26 s (particles) | ~30 |
| `footer.svg` | 18 s (back wave) | ~14 |
| `divider.svg` | 10 s (diamond) | 4 |
| Each card | 6 s (sheen) | 3–5 |

Loop lengths are deliberately co-prime-ish so the composition never settles into
a visible repeating beat.

<img src="assets/divider.svg" width="100%" alt="" />

## Technical constraints

What GitHub's Markdown pipeline does and does not allow — the rules these assets
were built against.

| Feature | Supported | Notes |
| :--- | :--- | :--- |
| SMIL animation in SVG | Yes | The basis of everything animated here |
| `<script>` in SVG | **No** | Stripped by the sanitiser |
| Inline `style` attributes in the README | **No** | Stripped; keep styling inside the SVG |
| `<style>` blocks inside an SVG file | Yes | The file is served as an image, not inlined |
| External images | Yes | Proxied and cached through Camo |
| `<img>`, `<a>`, `<table>`, `<details>`, `<picture>` | Yes | The structural toolkit |
| `align` attribute | Yes | Primary layout mechanism |
| `width` / `height` on `<img>` and `<td>` | Yes | Use percentages for responsiveness |
| `id` on headings | Auto-generated | Prefer explicit `<a name="...">` anchors |
| `prefers-color-scheme` via `<picture>` | Yes | Used for the snake |
| CSS Grid / Flexbox | **No** | Tables are the layout system |
| iframes, forms, video | **No** | Removed entirely |

### Responsiveness

GitHub does not reflow table columns on narrow viewports. Three rules keep the
layout usable on a phone:

1. Give every image `width="100%"` so it scales inside its cell
2. Use percentage widths on `<td>`, never fixed pixels
3. Cap content-heavy rows at two columns

### Accessibility

- Every decorative image carries `alt=""` so screen readers skip it
- Every meaningful image has a descriptive `alt`
- Each SVG includes a `<title>` and `role="img"` with an `aria-label`
- Contrast: `#EAF6FF` on `#050816` is roughly 17:1, well past WCAG AAA
- Readers with *prefers-reduced-motion* enabled see static first frames

### Performance

| Asset group | Approximate size |
| :--- | :--- |
| `hero.svg` | ~24 KB |
| `background.svg` | ~9 KB |
| Five illustrations | ~7 KB each |
| Eleven cards | ~3 KB each |
| `footer.svg`, `divider.svg`, `logo.svg` | ~4 KB each |
| **Total vector payload** | **under 120 KB** |

All of it is text, so gzip compresses it by roughly 75% in transit.

<img src="assets/divider.svg" width="100%" alt="" />

## Authoring a new asset

### Skeleton

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!-- ElectroIoT — <name> -->
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 380 150"
     width="380" height="150" role="img" aria-label="<description>">
  <title><Human readable title></title>

  <defs>
    <linearGradient id="xx-bg" x1="0" y1="0" x2="1" y2="1">
      <stop offset="0%" stop-color="#111827"/>
      <stop offset="100%" stop-color="#050816"/>
    </linearGradient>
    <linearGradient id="xx-edge" x1="0" y1="0" x2="1" y2="1">
      <stop offset="0%" stop-color="#00C8FF"/>
      <stop offset="100%" stop-color="#0066FF"/>
    </linearGradient>
    <filter id="xx-glow" x="-60%" y="-60%" width="220%" height="220%">
      <feGaussianBlur stdDeviation="3" result="b"/>
      <feMerge><feMergeNode in="b"/><feMergeNode in="SourceGraphic"/></feMerge>
    </filter>
  </defs>

  <rect x="2" y="2" width="376" height="146" rx="16"
        fill="url(#xx-bg)" stroke="url(#xx-edge)" stroke-width="1.5"/>
</svg>
```

### Checklist

- [ ] Unique `id` prefix on every gradient, filter and clip path
- [ ] `role="img"`, `aria-label` and `<title>` present
- [ ] Only palette colours used
- [ ] No `<script>` and no external font references
- [ ] `&` escaped as `&amp;` inside text content
- [ ] `viewBox` set so the asset scales cleanly
- [ ] Animation loop under 30 seconds
- [ ] Opens correctly in a browser before committing

### Validating locally

```bash
# Well-formedness check for every SVG
python -c "import glob,xml.dom.minidom as m; [m.parse(f) for f in glob.glob('assets/**/*.svg', recursive=True)]; print('all valid')"
```

```bash
# Optional: minify with svgo, preserving animation IDs
npx svgo --folder assets --recursive --pretty --disable=cleanupIds
```

Always pass `--disable=cleanupIds`. Renaming IDs breaks the cross-file
uniqueness that keeps the cards from bleeding into each other.

<img src="assets/divider.svg" width="100%" alt="" />

## Licensing and attribution

### This repository

All original artwork in `assets/` and all documentation is released under the
[MIT License](LICENSE). Use it, fork it, repaint it. Attribution is appreciated
but not required.

### Third-party services

| Service | Project | Licence |
| :--- | :--- | :--- |
| Readme Typing SVG | [DenverCoder1/readme-typing-svg](https://github.com/DenverCoder1/readme-typing-svg) | MIT |
| GitHub Readme Stats | [anuraghazra/github-readme-stats](https://github.com/anuraghazra/github-readme-stats) | MIT |
| Streak Stats | [DenverCoder1/github-readme-streak-stats](https://github.com/DenverCoder1/github-readme-streak-stats) | MIT |
| Activity Graph | [Ashutosh00710/github-readme-activity-graph](https://github.com/Ashutosh00710/github-readme-activity-graph) | MIT |
| Profile Trophy | [ryo-ma/github-profile-trophy](https://github.com/ryo-ma/github-profile-trophy) | MIT |
| Profile Views Counter | [antonkomarev/github-profile-views-counter](https://github.com/antonkomarev/github-profile-views-counter) | MIT |
| Skill Icons | [tandpfun/skill-icons](https://github.com/tandpfun/skill-icons) | MIT |
| Shields.io | [badges/shields](https://github.com/badges/shields) | CC0-1.0 |
| Snake Action | [Platane/snk](https://github.com/Platane/snk) | MIT |
| Metrics | [lowlighter/metrics](https://github.com/lowlighter/metrics) | MIT |

### Brand marks

Technology logos rendered by skillicons.dev and shields.io belong to their
respective owners and are used here for identification only. The stylised
Laravel mark in `assets/laravel.svg` is an original neon interpretation, not the
official logo file.

<img src="assets/divider.svg" width="100%" alt="" />

<div align="center">

<p>
  <a href="README.md">
    <img src="https://img.shields.io/badge/BACK%20TO%20PROFILE-00C8FF?style=for-the-badge&labelColor=050816&logo=github&logoColor=00FFD5" alt="Back to profile" />
  </a>
  <a href="setup-guide.md">
    <img src="https://img.shields.io/badge/SETUP%20GUIDE-0066FF?style=for-the-badge&labelColor=050816&logo=gitbook&logoColor=00FFD5" alt="Setup guide" />
  </a>
</p>

<img src="assets/footer.svg" width="100%" alt="" />

</div>
