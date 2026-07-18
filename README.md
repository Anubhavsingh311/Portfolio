# Anubhav Singh — Portfolio

A single-page personal portfolio built from scratch in React, covering five years of CS, AI/ML, and web work. This isn't a template — every layout decision, animation, color, and interaction was written by hand.

**Live:** [Portfolio's Link](https://anubhavsingh311.github.io/Portfolio/)

---

## What's in here

The site is a fully client-side React app compiled to a static bundle — no backend, no CMS, no framework magic. What ships is:

| File | What it is |
|------|-----------|
| `index.html` | The HTML shell |
| `assets/script.js` | The entire app, compiled and minified (340 KB — React 19, Framer Motion, and all component code) |
| `assets/style.css` | Tailwind v4 compiled output (36 KB) |
| `assets/Photo_on_22-03-26_at_12.34_PM-B-DnQteN.jpg` | Portrait photo used in the hero (332 KB) |

Open `index.html` in a browser and it runs — no build step, no dependencies to install.

---

## How the visual layer works

**Palette** — Deep navy (`#101e33`) base with ivory text (`#f6f2e8`) and a single gold accent (`#f2c94c`). Each project in the Selected Work section gets its own accent color (gold, burnt orange, teal, purple, blue) applied to the glyph, eyebrow label, and active state. The Toolkit section intentionally flips to an ivory background to break the rhythm.

**Typography** — DM Sans (400–700) for everything typographic; DM Mono (400) exclusively for labels, nav items, eyebrow text, tag chips, and the scroll HUD. The contrast between the two faces does most of the visual work — no decorative fonts.

**Scroll canvas** — The page background isn't a static color. It shifts hue as you scroll via a CSS custom property (`--scroll`) driven by a `requestAnimationFrame` loop:

```css
.scroll-canvas {
  background: hsl(calc(211deg + var(--scroll) * 72deg) 53% calc(13% + var(--scroll) * 7%));
}
```

At the top it's deep navy. By the contact section it's drifted noticeably warmer. It's subtle enough that most people don't consciously notice it.

**Aurora blobs** — Three radial gradient blobs (gold, blue, pink) are fixed to the viewport behind the content. Their position is tied to `--scroll` and their scale responds to `--energy`, a separate value that tracks scroll velocity and decays at 35ms intervals. Scroll fast and they pulse; stop and they settle.

**Scroll HUD** — Bottom-right corner. Shows current chapter name, a progress bar, and a percentage. The progress bar's glow intensity is driven by `--energy` so it brightens while you're actively scrolling. Hidden on reduced-motion.

**Custom cursor** — Replaced the system cursor on pointer devices. A gold ring (18px) with an inner dot and a 32px horizontal hairline. The ring morphs based on what it's hovering: links, email, LinkedIn, GitHub, and Instagram each get a distinct size, shape, and color. No magnetic attraction — it just follows the mouse directly. Hidden on touch devices.

**Active chapter tracking** — An `IntersectionObserver` watches five `[data-chapter]` sections. The HUD and nav update reactively as you scroll. The observer fires at 0.25, 0.5, and 0.75 thresholds and picks whichever visible section has the highest intersection ratio.

**Motion primitives** — Built six reusable components in `src/components/motion/`: `Reveal` (directional fade/slide with `useInView`), `RevealText` (per-character stagger), `Parallax` (Y translate tied to element scroll progress), `ScrollScale` (scale/fade from section progress), `Marquee` (velocity-coupled horizontal ticker with `useSpring` smoothing), and `StickySection` (scroll-pinned section with internal transform progress). All honor `prefers-reduced-motion`.

**Project selector** — The Selected Work section uses a `layoutId` animated bar that slides between active project rows via Framer Motion's shared layout. The featured panel cross-fades and slides 8px when `activeProject` state changes. The large glyph watermark rotates continuously via a CSS `calc()` on `--scroll`.

**Social hover fills** — LinkedIn, GitHub, and Instagram buttons each restore to their brand colors on hover (LinkedIn blue `#63a9e9`, ivory for GitHub, Instagram pink `#ee7ca8`) with a `translateY(-5px) skewX(-3deg)` lift.

---

## Projects

**[Gesture AI](https://github.com/Anubhavsingh311/handdetection)** · [Live Demo](https://handdetection-nine.vercel.app/)
12 gesture-controlled browser experiences in one local-first tool. Real-time hand tracking via MediaPipe, all processing in-browser.
`React` `MediaPipe` `Tailwind` `Vite`

**[Fraud Detection Pipeline](https://github.com/Anubhavsingh311/Fraud-Detection-Pipeline)**
End-to-end fraud detection from raw transaction data to evaluated risk model. Built as a repeatable Python pipeline.
`Python` `Pandas` `scikit-learn`

**[NLP & Sentiment Analysis](https://github.com/Anubhavsingh311/NLP_and_Sentiment-Analysis)**
Sentiment pipeline on 2,000 IMDB reviews. TF-IDF + Naive Bayes, 83–85% across accuracy, precision, recall, and F1.
`Python` `NLTK` `TF-IDF` `Naive Bayes`

**[Customer Segmentation](https://github.com/Anubhavsingh311/Customer-Segmentation-Unsupervised-ML)**
1,200 transaction records → 14 raw fields → 20 features → 13 principal components → 5 customer personas.
`Python` `PCA` `K-Means` `Seaborn`

**[AudioCast](https://github.com/Anubhavsingh311/AudioCast)** · [Live Demo](https://anubhavsingh311.github.io/AudioCast/)
Privacy-first in-browser PDF reader with text-to-speech, multi-PDF drag-and-drop, 0.5×–2× playback speeds, and live sentence tracking.
`HTML` `PDF.js` `Web Speech API`

---

## Experience

**Data Science Internship — DecodeLabs**
Four shipped projects: sentiment analysis, fraud detection, customer segmentation, and feature engineering. Raw data to evaluated models, all the way through.

**Job Simulations**
- Deloitte Australia — Cyber Job Simulation (Forage)
- Tata — GenAI Powered Data Analytics Simulation (Forage)

---

## Certifications

- [Microsoft Certified: Azure Fundamentals](https://www.credly.com/badges/0b813400-9262-4d4c-a351-099633cdec00/linked_in_profile)
- [Introduction to Generative AI Learning Path](https://www.coursera.org/account/accomplishments/specialization/83RAFSJVK1K2) — Google
- [Claude 101](https://verify.skilljar.com/c/9yvbdqhe6833) — Anthropic

---

## Stack

| Area | Tools |
|------|-------|
| Languages | Python · JavaScript · Java · C |
| Data & ML | Pandas · NumPy · TensorFlow · PyTorch · scikit-learn |
| Web | React · Node.js · HTML · Tailwind CSS · Bootstrap |
| Tools | Git · GitHub Actions · Docker · MySQL · Supabase |

---

## Connect

[anubhav.singh.chaudary311@gmail.com](mailto:anubhav.singh.chaudary311@gmail.com)
[LinkedIn](https://www.linkedin.com/in/anubhav-singh3116/) · [GitHub](https://github.com/Anubhavsingh311) · [Instagram](https://www.instagram.com/anubhavsingh3117/)
