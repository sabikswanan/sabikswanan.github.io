<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0A1A3F,50:1E3A8A,100:60A5FA&height=270&section=header&text=sabikswanan.github.io&fontSize=50&fontColor=A5D8FF&fontAlignY=38&stroke=0A1A3F&strokeWidth=2&animation=fadeIn&desc=Personal%20portfolio%20%E2%80%A2%20Machine%20Learning%20%E2%80%A2%20Data%20Science%20%E2%80%A2%20Software&descSize=17&descAlignY=58&descAlign=50" alt="sabikswanan.github.io" width="100%"/>

<a href="https://sabikswanan.github.io"><img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=20&duration=2600&pause=900&color=38BDF8&center=true&vCenter=true&width=780&lines=Hi%2C+this+is+Sabik+Swanan.;%3E+A+portfolio+built+like+a+ground+station;%3E+Live+contour+map+%C2%B7+bank+probe+%C2%B7+river+dividers;%3E+Zero+frameworks.+Zero+dependencies.+One+page." alt="Hi, this is Sabik Swanan. A portfolio built like a ground station."/></a>

<br/>

<a href="https://sabikswanan.github.io"><img src="https://img.shields.io/badge/%E2%86%97%20OPEN%20THE%20LIVE%20SITE-sabikswanan.github.io-2563EB?style=for-the-badge&labelColor=0A1A3F" alt="Open the live site"/></a>

<br/><br/>

<img src="https://img.shields.io/badge/HTML5-0A1A3F?style=for-the-badge&logo=html5&logoColor=60A5FA" alt="HTML5"/>
<img src="https://img.shields.io/badge/CSS3-0A1A3F?style=for-the-badge&logo=css&logoColor=60A5FA" alt="CSS3"/>
<img src="https://img.shields.io/badge/JavaScript-0A1A3F?style=for-the-badge&logo=javascript&logoColor=60A5FA" alt="JavaScript"/>
<img src="https://img.shields.io/badge/Canvas%202D-0A1A3F?style=for-the-badge&logo=html5&logoColor=A5D8FF" alt="Canvas 2D"/>
<img src="https://img.shields.io/badge/GitHub%20Pages-0A1A3F?style=for-the-badge&logo=githubpages&logoColor=A5D8FF" alt="GitHub Pages"/>

<img src="https://img.shields.io/badge/FRAMEWORKS-0-60A5FA?style=for-the-badge&labelColor=0A1A3F" alt="0 frameworks"/>
<img src="https://img.shields.io/badge/DEPENDENCIES-0-60A5FA?style=for-the-badge&labelColor=0A1A3F" alt="0 dependencies"/>
<img src="https://img.shields.io/badge/SECTIONS-10-38BDF8?style=for-the-badge&labelColor=0A1A3F" alt="10 sections"/>
<img src="https://img.shields.io/badge/THEMES-Dark%20%2B%20Light-A5D8FF?style=for-the-badge&labelColor=0A1A3F" alt="Dark and light themes"/>

<br/><br/>

**[Overview](#overview)** &nbsp;|&nbsp;
**[Tour](#tour)** &nbsp;|&nbsp;
**[How It Works](#how-it-works)** &nbsp;|&nbsp;
**[Performance](#performance)** &nbsp;|&nbsp;
**[Terminal](#terminal)** &nbsp;|&nbsp;
**[Structure](#structure)** &nbsp;|&nbsp;
**[Run It](#run-it)**

</div>

<br/>

<a name="overview"></a>

## 🛰️ Overview

This is the source of my personal portfolio, live at **[sabikswanan.github.io](https://sabikswanan.github.io)**.

My undergraduate thesis predicts **riverbank erosion on the Jamuna** from decades of satellite imagery, so the
site is designed like a **remote-sensing ground station**: the hero is a live contour map with a meandering
river and a probe that reads out erosion risk, sections are joined by river-shaped dividers, and the intro
"acquires" the page before it opens.

Everything is **hand-written HTML, CSS and JavaScript** in a single `index.html`. No React, no build step, no
animation library, no physics engine. It is fast on phones, works in **dark and light** mode, and respects
**reduced-motion** settings.

<br/>

<a name="tour"></a>

## 🧭 A Tour of the Site

| # | Section | What you can do there |
|:-:|---|---|
| 00 | **Intro** | *"Hi, this is"* types out, the name rises letter by letter, a river draws itself, then two curtains lift |
| — | **Hero** | Move over the animated **contour map** to drive the **bank probe** (latitude, distance to channel, erosion risk) |
| 01 | **About** | Photo card with a rotating light border and quick facts |
| 02 | **What I do** | Three kinds of problems I like to work on |
| 03 | **Research** | Step through my thesis pipeline, from Landsat tiles to the LLM report layer |
| 04 | **Work** | Four project cards with live mini-visualisations, filters and full case studies |
| 05 | **Terminal** | A working shell. Type `help` |
| 06 | **Toolbox** | Every tool I have shipped with, plus a scrolling tech strip |
| 07 | **Coursework** | **27 course balls** with real physics. Grab, throw, shake, tap one to read about it |
| 08 | **Journey** | Timeline from SSC to the thesis |
| 09 | **Proof** | Certificate gallery with a lightbox, DofE first |
| 10 | **Contact** | Copy-to-clipboard email and a message form |

<br/>

<a name="how-it-works"></a>

## ⚙️ How It Works

```mermaid
%%{init: {"theme": "base", "themeVariables": {"fontFamily": "monospace", "lineColor": "#60A5FA"}}}%%
flowchart LR
    U(["Visitor"]) --> I["Intro<br/>typing · letter rise · curtains"]
    I --> H["Hero<br/>contour map + bank probe"]
    H --> S["10 sections<br/>river dividers · section numbers"]
    S --> X{"Interactions"}
    X --> T["Terminal"]
    X --> B["Course ball physics"]
    X --> C["Case studies"]
    X --> G["Certificate lightbox"]
    X --> R["Résumé viewer"]

    classDef dark fill:#0A1A3F,stroke:#60A5FA,color:#E7F0FF,stroke-width:1.5px
    classDef mid fill:#1E3A8A,stroke:#A5D8FF,color:#FFFFFF,stroke-width:1.5px
    classDef light fill:#DBEAFE,stroke:#2563EB,color:#0A1A3F,stroke-width:1.5px
    class U,I dark
    class H,S,X mid
    class T,B,C,G,R light
```

| Piece | How it is built |
|---|---|
| **Contour map** | Value noise → height grid → **marching squares** on a `<canvas>`, with a river carved through the terrain. Contours are cached on an offscreen canvas and redrawn every few frames |
| **Bank probe** | Reads the river's curvature and the cursor's distance from the channel to estimate an illustrative erosion risk |
| **Course balls** | A small custom physics engine: gravity, wall bounce, ball-to-ball impulses, drag-and-throw with pointer velocity |
| **Section transitions** | An SVG river path draws itself with scroll progress while a glowing probe rides along it |
| **Smooth scroll** | Inertia scrolling for mouse and trackpad, eased glides for every in-page link, native momentum kept on phones |
| **Reveals** | `IntersectionObserver` triggers fades, word-by-word titles and decoding labels only when a section enters view |
| **Themes** | CSS custom properties with a dark default, a light override and a manual toggle |

<br/>

<a name="performance"></a>

## ⚡ Performance

Smooth on a mid-range phone was a hard requirement, so every moving part only runs when it is needed.

```mermaid
%%{init: {"theme": "base", "themeVariables": {"fontFamily": "monospace", "lineColor": "#60A5FA", "edgeLabelBackground": "#DBEAFE", "textColor": "#0A1A3F"}}}%%
flowchart TB
    A["Is it on screen?"] -->|no| P["Paused"]
    A -->|yes| B["Is it moving?"]
    B -->|no| Z["Sleeps until touched"]
    B -->|yes| C["Runs at a capped frame rate"]

    classDef q fill:#1E3A8A,stroke:#A5D8FF,color:#FFFFFF,stroke-width:1.5px
    classDef s fill:#DBEAFE,stroke:#2563EB,color:#0A1A3F,stroke-width:1.5px
    class A,B q
    class P,Z,C s
```

- The hero map pauses off screen and in background tabs, caches its contour layer and runs at a lower resolution and frame rate on phones
- Ball physics, the custom cursor and the hero glow **go to sleep** once they stop moving
- The tech strip pauses when it scrolls out of view
- Expensive effects (backdrop blur, `shadowBlur`, animated `filter`) were replaced with cheaper equivalents
- Certificate thumbnails are embedded, full-size images are preloaded after the page settles
- In a 4× CPU-throttled test, a performance pass cut the page's scripting time to about **one third**

<br/>

<a name="terminal"></a>

## 💻 Terminal Commands

The site has a small shell in the **Terminal** section. Try these:

| Command | Output |
|---|---|
| `help` | List every command |
| `whoami` | Who I am and what I focus on |
| `projects` | One-line summary of each project |
| `thesis` | My research in one paragraph |
| `skills` | Tools I use, by area |
| `contact` · `social` | Email, LinkedIn and GitHub |
| `resume` | Opens the résumé viewer |
| `ls` · `date` | Exactly what you would expect |
| `sudo hire sabik` | 🤫 |
| `clear` | Clear the screen |

<br/>

<a name="structure"></a>

## 📁 Structure

```text
sabikswanan.github.io/
├── index.html              ← the whole site: markup, styles and scripts
├── profile.jpg             ← About photo
├── Sabik_Swanan_CV.pdf     ← downloadable résumé
├── cv-page-1.jpg           ← résumé preview, page 1
├── cv-page-2.jpg           ← résumé preview, page 2
└── certs/
    ├── *.jpg               ← full-size certificates for the lightbox
    └── thumb/*.jpg         ← small certificate thumbnails
```

<br/>

<a name="run-it"></a>

## 🚀 Run It

**Locally:** download or clone the repo and open `index.html` in any modern browser. No install, no build.

```bash
git clone https://github.com/sabikswanan/sabikswanan.github.io.git
cd sabikswanan.github.io
# open index.html, or serve the folder:
python -m http.server 8000
```

**Deploy:** this repo is served by **GitHub Pages** from the `main` branch root. Any commit to `main` goes live
in a minute or two.

> [!TIP]
> To update the résumé, replace `Sabik_Swanan_CV.pdf`, `cv-page-1.jpg` and `cv-page-2.jpg` with new files
> of the same names and commit.

<br/>

<div align="center">

**Sabik Swanan**<br/>
B.Sc. in Computer Science · BRAC University · Dhaka

<br/>

<a href="https://sabikswanan.github.io"><img src="https://img.shields.io/badge/Portfolio-sabikswanan.github.io-2563EB?style=for-the-badge&logo=googlechrome&logoColor=white&labelColor=0A1A3F" alt="Portfolio"/></a>
<a href="https://github.com/sabikswanan"><img src="https://img.shields.io/badge/GitHub-sabikswanan-1E3A8A?style=for-the-badge&logo=github&logoColor=white&labelColor=0A1A3F" alt="GitHub"/></a>
<a href="https://www.linkedin.com/in/sabikswanan"><img src="https://img.shields.io/badge/LinkedIn-sabikswanan-A5D8FF?style=for-the-badge&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCA0NDggNTEyIj48cGF0aCBmaWxsPSJ3aGl0ZSIgZD0iTTQxNiAzMkgzMS45QzE0LjMgMzIgMCA0Ni41IDAgNjQuM3YzODMuNEMwIDQ2NS41IDE0LjMgNDgwIDMxLjkgNDgwSDQxNmMxNy42IDAgMzItMTQuNSAzMi0zMi4zVjY0LjNjMC0xNy44LTE0LjQtMzIuMy0zMi0zMi4zek0xMzUuNCA0MTZINjlWMjAyLjJoNjYuNVY0MTZ6bS0zMy4yLTI0M2MtMjEuMyAwLTM4LjUtMTcuMy0zOC41LTM4LjVTODAuOSA5NiAxMDIuMiA5NmMyMS4yIDAgMzguNSAxNy4zIDM4LjUgMzguNSAwIDIxLjMtMTcuMiAzOC41LTM4LjUgMzguNXptMjgyLjEgMjQzaC02Ni40VjMxMmMwLTI0LjgtLjUtNTYuNy0zNC41LTU2LjctMzQuNiAwLTM5LjkgMjctMzkuOSA1NC45VjQxNmgtNjYuNFYyMDIuMmg2My43djI5LjJoLjljOC45LTE2LjggMzAuNi0zNC41IDYyLjktMzQuNSA2Ny4yIDAgNzkuNyA0NC4zIDc5LjcgMTAxLjlWNDE2eiIvPjwvc3ZnPg%3D%3D&logoColor=A5D8FF&labelColor=0A1A3F" alt="LinkedIn"/></a>
<a href="https://mail.google.com/mail/?view=cm&fs=1&to=sabikswanan@gmail.com"><img src="https://img.shields.io/badge/Email-sabikswanan%40gmail.com-60A5FA?style=for-the-badge&logo=gmail&logoColor=white&labelColor=0A1A3F" alt="Email"/></a>

<br/><br/>

<sub>⭐ Star this repo if you liked the site</sub>

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:60A5FA,50:1E3A8A,100:0A1A3F&height=130&section=footer" alt="" width="100%"/>

</div>
