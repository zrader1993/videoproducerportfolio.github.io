<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Video Producer Portfolio</title>
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <style>
    :root {
      --bg: #05060a;
      --bg-alt: #0b0d14;
      --accent: #ff4b4b;
      --accent-soft: rgba(255, 75, 75, 0.15);
      --text: #f5f5f7;
      --muted: #9a9aa5;
      --card: #11131c;
      --border: #1b1e2b;
      --radius-lg: 18px;
      --radius-md: 12px;
      --radius-pill: 999px;
      --shadow-soft: 0 18px 45px rgba(0, 0, 0, 0.55);
      --shadow-subtle: 0 10px 30px rgba(0, 0, 0, 0.35);
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      font-family: system-ui, -apple-system, BlinkMacSystemFont, "SF Pro Text",
        "Segoe UI", sans-serif;
      background: radial-gradient(circle at top, #15182a 0, #05060a 55%);
      color: var(--text);
      min-height: 100vh;
      line-height: 1.6;
    }

    a {
      color: inherit;
      text-decoration: none;
    }

    img {
      max-width: 100%;
      display: block;
    }

    .page {
      max-width: 1120px;
      margin: 0 auto;
      padding: 32px 20px 64px;
    }

    /* Header / Hero */

    header {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 24px;
      margin-bottom: 40px;
    }

    .brand {
      display: flex;
      align-items: center;
      gap: 10px;
    }

    .brand-mark {
      width: 32px;
      height: 32px;
      border-radius: 12px;
      background: radial-gradient(circle at 20% 0, #ffb347, #ff4b4b);
      display: flex;
      align-items: center;
      justify-content: center;
      font-weight: 700;
      font-size: 18px;
      box-shadow: var(--shadow-subtle);
    }

    .brand-text {
      font-size: 14px;
      text-transform: uppercase;
      letter-spacing: 0.18em;
      color: var(--muted);
    }

    nav {
      display: flex;
      align-items: center;
      gap: 18px;
      font-size: 14px;
      color: var(--muted);
    }

    nav a {
      position: relative;
      padding-bottom: 2px;
    }

    nav a::after {
      content: "";
      position: absolute;
      left: 0;
      bottom: 0;
      width: 0;
      height: 2px;
      border-radius: 999px;
      background: linear-gradient(90deg, #ff4b4b, #ffb347);
      transition: width 0.2s ease-out;
    }

    nav a:hover::after {
      width: 100%;
    }

    .nav-cta {
      padding: 8px 16px;
      border-radius: var(--radius-pill);
      border: 1px solid rgba(255, 255, 255, 0.08);
      background: linear-gradient(135deg, rgba(255, 255, 255, 0.04), transparent);
      color: var(--text);
      display: inline-flex;
      align-items: center;
      gap: 8px;
      font-size: 13px;
      cursor: pointer;
      transition: background 0.2s ease-out, transform 0.15s ease-out,
        box-shadow 0.15s ease-out;
      box-shadow: 0 0 0 rgba(0, 0, 0, 0);
    }

    .nav-cta span {
      font-size: 16px;
    }

    .nav-cta:hover {
      background: linear-gradient(135deg, rgba(255, 255, 255, 0.08), transparent);
      transform: translateY(-1px);
      box-shadow: 0 10px 25px rgba(0, 0, 0, 0.4);
    }

    /* Hero */

    .hero {
      display: grid;
      grid-template-columns: minmax(0, 1.4fr) minmax(0, 1fr);
      gap: 32px;
      align-items: center;
      margin-bottom: 40px;
    }

    .hero-copy-eyebrow {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      padding: 4px 10px;
      border-radius: var(--radius-pill);
      background: rgba(255, 255, 255, 0.03);
      border: 1px solid rgba(255, 255, 255, 0.06);
      color: var(--muted);
      font-size: 11px;
      text-transform: uppercase;
      letter-spacing: 0.18em;
      margin-bottom: 14px;
    }

    .hero-copy-eyebrow-dot {
      width: 6px;
      height: 6px;
      border-radius: 999px;
      background: #4bffa5;
      box-shadow: 0 0 0 4px rgba(75, 255, 165, 0.18);
    }

    .hero h1 {
      font-size: clamp(32px, 4vw, 40px);
      line-height: 1.1;
      margin-bottom: 14px;
    }

    .hero h1 span {
      background: linear-gradient(120deg, #ffb347, #ff4b4b);
      -webkit-background-clip: text;
      color: transparent;
    }

    .hero-subtitle {
      color: var(--muted);
      font-size: 15px;
      max-width: 460px;
      margin-bottom: 20px;
    }

    .hero-meta {
      display: flex;
      flex-wrap: wrap;
      gap: 16px;
      margin-bottom: 24px;
      font-size: 13px;
      color: var(--muted);
    }

    .hero-meta-item {
      display: inline-flex;
      align-items: center;
      gap: 6px;
      padding: 6px 10px;
      border-radius: var(--radius-pill);
      background: rgba(255, 255, 255, 0.02);
      border: 1px solid rgba(255, 255, 255, 0.04);
    }

    .hero-meta-item strong {
      color: var(--text);
      font-weight: 500;
    }

    .hero-actions {
      display: flex;
      flex-wrap: wrap;
      gap: 12px;
    }

    .btn-primary {
      padding: 11px 20px;
      border-radius: var(--radius-pill);
      border: none;
      background: linear-gradient(135deg, #ff4b4b, #ffb347);
      color: #05060a;
      font-weight: 600;
      font-size: 14px;
      cursor: pointer;
      display: inline-flex;
      align-items: center;
      gap: 8px;
      box-shadow: var(--shadow-soft);
      transition: transform 0.15s ease-out, box-shadow 0.15s ease-out,
        filter 0.15s ease-out;
    }

    .btn-primary:hover {
      transform: translateY(-1px);
      filter: brightness(1.05);
      box-shadow: 0 22px 50px rgba(0, 0, 0, 0.7);
    }

    .btn-ghost {
      padding: 10px 18px;
      border-radius: var(--radius-pill);
      border: 1px solid rgba(255, 255, 255, 0.12);
      background: rgba(255, 255, 255, 0.02);
      color: var(--text);
      font-size: 13px;
      cursor: pointer;
      display: inline-flex;
      align-items: center;
      gap: 8px;
      transition: background 0.15s ease-out, border-color 0.15s ease-out,
        transform 0.15s ease-out;
    }

    .btn-ghost:hover {
      background: rgba(255, 255, 255, 0.06);
      border-color: rgba(255, 255, 255, 0.2);
      transform: translateY(-1px);
    }

    .hero-visual {
      position: relative;
      border-radius: var(--radius-lg);
      background: radial-gradient(circle at top left, #ff4b4b22, #05060a 55%);
      padding: 18px;
      border: 1px solid rgba(255, 255, 255, 0.06);
      box-shadow: var(--shadow-soft);
      overflow: hidden;
    }

    .hero-visual-main {
      position: relative;
      border-radius: 14px;
      overflow: hidden;
      background: #000;
      aspect-ratio: 16 / 9;
      cursor: pointer;
      isolation: isolate;
    }

    .hero-visual-main::before {
      content: "";
      position: absolute;
      inset: 0;
      background: radial-gradient(circle at 20% 0, rgba(255, 255, 255, 0.12), transparent 55%);
      mix-blend-mode: screen;
      opacity: 0.7;
      pointer-events: none;
    }

    .hero-visual-main img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      transform: scale(1.02);
      transition: transform 0.4s ease-out, filter 0.4s ease-out;
      filter: saturate(1.1) contrast(1.05);
    }

    .hero-visual-main:hover img {
      transform: scale(1.06);
      filter: saturate(1.25) contrast(1.1);
    }

    .hero-visual-overlay {
      position: absolute;
      inset: 0;
      display: flex;
      align-items: center;
      justify-content: center;
      pointer-events: none;
    }

    .play-pill {
      pointer-events: auto;
      display: inline-flex;
      align-items: center;
      gap: 10px;
      padding: 9px 16px;
      border-radius: var(--radius-pill);
      background: rgba(0, 0, 0, 0.7);
      border: 1px solid rgba(255, 255, 255, 0.18);
      backdrop-filter: blur(14px);
      color: var(--text);
      font-size: 13px;
      box-shadow: 0 14px 35px rgba(0, 0, 0, 0.7);
      transition: background 0.15s ease-out, transform 0.15s ease-out,
        box-shadow 0.15s ease-out;
    }

    .hero-visual-main:hover .play-pill {
      background: rgba(0, 0, 0, 0.85);
      transform: translateY(-1px);
      box-shadow: 0 18px 40px rgba(0, 0, 0, 0.85);
    }

    .play-icon {
      width: 26px;
      height: 26px;
      border-radius: 999px;
      background: radial-gradient(circle at 30% 0, #ffb347, #ff4b4b);
      display: flex;
      align-items: center;
      justify-content: center;
      color: #05060a;
      font-size: 13px;
      box-shadow: 0 0 0 4px rgba(255, 75, 75, 0.35);
    }

    .hero-visual-tag {
      position: absolute;
      left: 18px;
      top: 18px;
      padding: 6px 10px;
      border-radius: var(--radius-pill);
      background: rgba(0, 0, 0, 0.7);
      border: 1px solid rgba(255, 255, 255, 0.16);
      font-size: 11px;
      color: var(--muted);
      backdrop-filter: blur(12px);
    }

    .hero-visual-tag strong {
      color: var(--text);
      font-weight: 500;
    }

    .hero-visual-badge {
      position: absolute;
      right: 18px;
      bottom: 18px;
      padding: 8px 12px;
      border-radius: 14px;
      background: rgba(5, 6, 10, 0.9);
      border: 1px solid rgba(255, 255, 255, 0.12);
      font-size: 11px;
      color: var(--muted);
      display: flex;
      flex-direction: column;
      gap: 2px;
      backdrop-filter: blur(14px);
    }

    .hero-visual-badge strong {
      color: var(--text);
      font-weight: 500;
    }

    /* Section heading */

    .section-heading {
      display: flex;
      align-items: baseline;
      justify-content: space-between;
      gap: 16px;
      margin: 12px 0 18px;
    }

    .section-heading h2 {
      font-size: 18px;
    }

    .section-heading p {
      font-size: 13px;
      color: var(--muted);
      max-width: 360px;
    }

    /* Video grid */

    .video-grid {
      display: grid;
      grid-template-columns: repeat(3, minmax(0, 1fr));
      gap: 18px;
      margin-bottom: 40px;
    }

    @media (max-width: 900px) {
      .video-grid {
        grid-template-columns: repeat(2, minmax(0, 1fr));
      }
    }

    @media (max-width: 640px) {
      .video-grid {
        grid-template-columns: minmax(0, 1fr);
      }
    }

    .video-card {
      position: relative;
      border-radius: var(--radius-md);
      background: radial-gradient(circle at top, #1b1e2b, #05060a);
      border: 1px solid var(--border);
      overflow: hidden;
      cursor: pointer;
      box-shadow: var(--shadow-subtle);
      transition: transform 0.18s ease-out, box-shadow 0.18s ease-out,
        border-color 0.18s ease-out, background 0.18s ease-out;
    }

    .video-card:hover {
      transform: translateY(-4px);
      box-shadow: 0 18px 40px rgba(0, 0, 0, 0.7);
      border-color: rgba(255, 255, 255, 0.16);
      background: radial-gradient(circle at top, #262a3d, #05060a);
    }

    .video-thumb {
      position: relative;
      aspect-ratio: 16 / 9;
      overflow: hidden;
    }

    .video-thumb img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      transform: scale(1.03);
      transition: transform 0.35s ease-out, filter 0.35s ease-out;
      filter: saturate(1.1) contrast(1.05);
    }

    .video-card:hover .video-thumb img {
      transform: scale(1.08);
      filter: saturate(1.25) contrast(1.1);
    }

    .video-thumb-overlay {
      position: absolute;
      inset: 0;
      background: linear-gradient(
        to top,
        rgba(0, 0, 0, 0.7),
        transparent 55%
      );
      display: flex;
      align-items: flex-end;
      justify-content: space-between;
      padding: 10px 10px 9px;
      font-size: 11px;
      color: var(--muted);
    }

    .video-thumb-overlay span {
      display: inline-flex;
      align-items: center;
      gap: 6px;
      padding: 4px 8px;
      border-radius: var(--radius-pill);
      background: rgba(0, 0, 0, 0.7);
      border: 1px solid rgba(255, 255, 255, 0.16);
      backdrop-filter: blur(10px);
    }

    .video-thumb-overlay strong {
      color: var(--text);
      font-weight: 500;
    }

    .video-body {
      padding: 12px 12px 13px;
    }

    .video-title {
      font-size: 14px;
      margin-bottom: 4px;
    }

    .video-meta {
      font-size: 12px;
      color: var(--muted);
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 8px;
    }

    .video-meta span {
      display: inline-flex;
      align-items: center;
      gap: 6px;
    }

    .video-meta-dot {
      width: 4px;
      height: 4px;
      border-radius: 999px;
      background: rgba(255, 255, 255, 0.3);
    }

    /* About / footer */

    .about {
      display: grid;
      grid-template-columns: minmax(0, 1.2fr) minmax(0, 1fr);
      gap: 24px;
      padding: 18px 18px 20px;
      border-radius: var(--radius-lg);
      background: radial-gradient(circle at top left, #1b1e2b, #05060a);
      border: 1px solid rgba(255, 255, 255, 0.08);
      box-shadow: var(--shadow-soft);
    }

    .about p {
      font-size: 14px;
      color: var(--muted);
      margin-bottom: 10px;
    }

    .about-tags {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
      margin-top: 4px;
    }

    .about-tag {
      font-size: 11px;
      padding: 5px 9px;
      border-radius: var(--radius-pill);
      background: rgba(255, 255, 255, 0.03);
      border: 1px solid rgba(255, 255, 255, 0.08);
      color: var(--muted);
    }

    .about-contact {
      display: flex;
      flex-direction: column;
      gap: 8px;
      font-size: 13px;
      color: var(--muted);
      align-items: flex-end;
      justify-content: space-between;
    }

    .about-contact a {
      color: var(--text);
      font-weight: 500;
    }

    .about-socials {
      display: flex;
      gap: 10px;
    }

    .social-pill {
      padding: 6px 10px;
      border-radius: var(--radius-pill);
      background: rgba(255, 255, 255, 0.03);
      border: 1px solid rgba(255, 255, 255, 0.08);
      font-size: 12px;
      display: inline-flex;
      align-items: center;
      gap: 6px;
      cursor: pointer;
      transition: background 0.15s ease-out, border-color 0.15s ease-out,
        transform 0.15s ease-out;
    }

    .social-pill:hover {
      background: rgba(255, 255, 255, 0.08);
      border-color: rgba(255, 255, 255, 0.2);
      transform: translateY(-1px);
    }

    footer {
      margin-top: 18px;
      font-size: 11px;
      color: var(--muted);
      text-align: center;
    }

    /* Modal */

    .modal-backdrop {
      position: fixed;
      inset: 0;
      background: rgba(0, 0, 0, 0.8);
      display: none;
      align-items: center;
      justify-content: center;
      z-index: 40;
      padding: 16px;
    }

    .modal-backdrop.active {
      display: flex;
    }

    .modal {
      width: 100%;
      max-width: 960px;
      background: #05060a;
      border-radius: 16px;
      border: 1px solid rgba(255, 255, 255, 0.12);
      box-shadow: 0 24px 60px rgba(0, 0, 0, 0.9);
      overflow: hidden;
      position: relative;
    }

    .modal-header {
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 10px 14px;
      border-bottom: 1px solid rgba(255, 255, 255, 0.08);
      font-size: 13px;
      color: var(--muted);
    }

    .modal-header strong {
      color: var(--text);
      font-weight: 500;
    }

    .modal-close {
      border: none;
      background: transparent;
      color: var(--muted);
      font-size: 18px;
      cursor: pointer;
      padding: 4px 6px;
      border-radius: 999px;
      transition: background 0.15s ease-out, color 0.15s ease-out;
    }

    .modal-close:hover {
      background: rgba(255, 255, 255, 0.08);
      color: var(--text);
    }

    .modal-body {
      padding: 10px 14px 14px;
    }

    .modal-video {
      position: relative;
      padding-bottom: 56.25%;
      height: 0;
      overflow: hidden;
      border-radius: 12px;
      background: #000;
    }

    .modal-video iframe {
      position: absolute;
      inset: 0;
      width: 100%;
      height: 100%;
      border: 0;
    }

    @media (max-width: 800px) {
      header {
        flex-direction: column;
        align-items: flex-start;
      }

      .hero {
        grid-template-columns: minmax(0, 1fr);
      }

      .hero-visual {
        order: -1;
      }

      .about {
        grid-template-columns: minmax(0, 1fr);
      }

      .about-contact {
        align-items: flex-start;
      }
    }
  </style>
</head>
<body>
  <div class="page">
    <header>
      <div class="brand">
        <div class="brand-mark">V</div>
        <div class="brand-text">Video Producer</div>
      </div>
      <nav>
        <a href="#work">Work</a>
        <a href="#about">About</a>
        <a href="#contact">Contact</a>
        <button class="nav-cta" onclick="scrollToSection('contact')">
          <span>●</span> Let’s talk
        </button>
      </nav>
    </header>

    <main>
      <section class="hero">
        <div class="hero-copy">
          <div class="hero-copy-eyebrow">
            <span class="hero-copy-eyebrow-dot"></span>
            <span>Director · Editor · Storyteller</span>
          </div>
          <h1>
            Cinematic stories for brands, artists, and
            <span>bold ideas.</span>
          </h1>
          <p class="hero-subtitle">
            I craft narrative‑driven visuals—from music videos to branded content—that feel polished, intentional, and human.
          </p>
          <div class="hero-meta">
            <div class="hero-meta-item">
              <strong>5+</strong> years in production
            </div>
            <div class="hero-meta-item">
              <strong>Concept → Delivery</strong> full‑stack workflow
            </div>
          </div>
          <div class="hero-actions">
            <button class="btn-primary" onclick="scrollToSection('work')">
              View selected work →
            </button>
            <button class="btn-ghost" onclick="scrollToSection('about')">
              Learn more
            </button>
          </div>
        </div>

        <div class="hero-visual" data-video="https://www.youtube.com/embed/x1K4teXVvVs">
          <div class="hero-visual-tag">
            Featured reel · <strong>Music / Narrative</strong>
          </div>
          <div class="hero-visual-main">
            <!-- You can swap this thumbnail for a custom frame if you like -->
            <img
              src="https://img.youtube.com/vi/x1K4teXVvVs/maxresdefault.jpg"
              alt="Featured video thumbnail"
            />
            <div class="hero-visual-overlay">
              <button class="play-pill" type="button">
                <div class="play-icon">▶</div>
                <span>Play featured piece</span>
              </button>
            </div>
          </div>
          <div class="hero-visual-badge">
            <span>Selected work · 2024</span>
            <strong>Shot · Directed · Edited</strong>
          </div>
        </div>
      </section>

      <section id="work">
        <div class="section-heading">
          <h2>Selected work</h2>
          <p>
            A snapshot of recent projects across music, narrative, and branded content. Each piece is fully produced—from pre‑production to final grade.
          </p>
        </div>

        <div class="video-grid">
          <!-- Video 1 -->
          <article
            class="video-card"
            data-video="https://www.youtube.com/embed/x1K4teXVvVs"
          >
            <div class="video-thumb">
              <img
                src="https://img.youtube.com/vi/x1K4teXVvVs/hqdefault.jpg"
                alt="Video 1 thumbnail"
              />
              <div class="video-thumb-overlay">
                <span>
                  <strong>Music / Narrative</strong>
                </span>
                <span>3:xx</span>
              </div>
            </div>
            <div class="video-body">
              <h3 class="video-title">Featured Piece · Performance & Atmosphere</h3>
              <div class="video-meta">
                <span>
                  <span class="video-meta-dot"></span>
                  Direction · Edit · Color
                </span>
                <span>2024</span>
              </div>
            </div>
          </article>

          <!-- Video 2 -->
          <article
            class="video-card"
            data-video="https://www.youtube.com/embed/tToMLlfMMc0"
          >
            <div class="video-thumb">
              <img
                src="https://img.youtube.com/vi/tToMLlfMMc0/hqdefault.jpg"
                alt="Video 2 thumbnail"
              />
              <div class="video-thumb-overlay">
                <span>
                  <strong>Music video</strong>
                </span>
                <span>3:xx</span>
              </div>
            </div>
            <div class="video-body">
              <h3 class="video-title">Artist Visual · Rhythm & Motion</h3>
              <div class="video-meta">
                <span>
                  <span class="video-meta-dot"></span>
                  Concept · Camera · Edit
                </span>
                <span>2023</span>
              </div>
            </div>
          </article>

          <!-- Video 3 -->
          <article
            class="video-card"
            data-video="https://www.youtube.com/embed/kpvV30DWhuo"
          >
            <div class="video-thumb">
              <img
                src="https://img.youtube.com/vi/kpvV30DWhuo/hqdefault.jpg"
                alt="Video 3 thumbnail"
              />
              <div class="video-thumb-overlay">
                <span>
                  <strong>Performance</strong>
                </span>
                <span>2:xx</span>
              </div>
            </div>
            <div class="video-body">
              <h3 class="video-title">Live Session · Intimate Coverage</h3>
              <div class="video-meta">
                <span>
                  <span class="video-meta-dot"></span>
                  Multi‑cam · Live mix
                </span>
                <span>2023</span>
              </div>
            </div>
          </article>

          <!-- Video 4 -->
          <article
            class="video-card"
            data-video="https://www.youtube.com/embed/9zfZ5R08Lns"
          >
            <div class="video-thumb">
              <img
                src="https://img.youtube.com/vi/9zfZ5R08Lns/hqdefault.jpg"
                alt="Video 4 thumbnail"
              />
              <div class="video-thumb-overlay">
                <span>
                  <strong>Branded</strong>
                </span>
                <span>0:xx</span>
              </div>
            </div>
            <div class="video-body">
              <h3 class="video-title">Brand Moment · Short‑form Spot</h3>
              <div class="video-meta">
                <span>
                  <span class="video-meta-dot"></span>
                  Social‑first · Vertical
                </span>
                <span>2022</span>
              </div>
            </div>
          </article>

          <!-- Video 5 -->
          <article
            class="video-card"
            data-video="https://www.youtube.com/embed/ZhCR2WicjFs"
          >
            <div class="video-thumb">
              <img
                src="https://img.youtube.com/vi/ZhCR2WicjFs/hqdefault.jpg"
                alt="Video 5 thumbnail"
              />
              <div class="video-thumb-overlay">
                <span>
                  <strong>Concept piece</strong>
                </span>
                <span>1:xx</span>
              </div>
            </div>
            <div class="video-body">
              <h3 class="video-title">Visual Experiment · Texture & Light</h3>
              <div class="video-meta">
                <span>
                  <span class="video-meta-dot"></span>
                  Experimental · In‑camera
                </span>
                <span>2022</span>
              </div>
            </div>
          </article>

          <!-- External link card -->
          <article
            class="video-card"
            onclick="window.open('https://www.youtube.com/@YOURCHANNEL', '_blank')"
          >
            <div class="video-thumb">
              <div
                style="
                  width: 100%;
                  height: 100%;
                  display: flex;
                  align-items: center;
                  justify-content: center;
                  background: radial-gradient(circle at top, #ff4b4b33, #05060a);
                  color: var(--muted);
                  font-size: 13px;
                "
              >
                View full YouTube portfolio →
              </div>
              <div class="video-thumb-overlay">
                <span>
                  <strong>More work</strong>
                </span>
                <span>YouTube</span>
              </div>
            </div>
            <div class="video-body">
              <h3 class="video-title">See the complete catalog</h3>
              <div class="video-meta">
                <span>
                  <span class="video-meta-dot"></span>
                  Playlists · BTS · Experiments
                </span>
                <span>Open channel</span>
              </div>
            </div>
          </article>
        </div>
      </section>

      <section id="about" class="about">
        <div>
          <h2 style="font-size: 16px; margin-bottom: 6px;">About the work</h2>
          <p>
            I’m a video producer focused on crafting cinematic, emotionally grounded visuals. From early
            treatment and shot‑listing to on‑set direction and final color, I’m hands‑on with every frame.
          </p>
          <p>
            I love collaborating with artists, brands, and agencies who care about story, pacing, and
            intentional visuals—whether that’s a lean run‑and‑gun shoot or a fully crewed production.
          </p>
          <div class="about-tags">
            <span class="about-tag">Pre‑production & treatments</span>
            <span class="about-tag">Directing & cinematography</span>
            <span class="about-tag">Editing & sound design</span>
            <span class="about-tag">Color grading</span>
            <span class="about-tag">Music & branded content</span>
          </div>
        </div>
        <div id="contact" class="about-contact">
          <div>
            <div style="margin-bottom: 4px;">Available for:</div>
            <div class="about-tags" style="justify-content: flex-end;">
              <span class="about-tag">Music videos</span>
              <span class="about-tag">Brand films</span>
              <span class="about-tag">Social campaigns</span>
            </div>
          </div>
          <div>
            <div style="margin-bottom: 4px;">Let’s build something:</div>
            <div>
              <a href="mailto:youremail@example.com">youremail@example.com</a>
            </div>
          </div>
          <div class="about-socials">
            <button class="social-pill" type="button">
              <span>IG</span> @yourhandle
            </button>
            <button class="social-pill" type="button">
              <span>YT</span> Channel
            </button>
          </div>
        </div>
      </section>
    </main>

    <footer>
      © <span id="year"></span> Your Name · Video Producer
    </footer>
  </div>

  <!-- Modal -->
  <div class="modal-backdrop" id="videoModal">
    <div class="modal">
      <div class="modal-header">
        <div>
          <strong>Now playing</strong>
          <span id="modalTitle" style="margin-left: 6px; color: #9a9aa5;"></span>
        </div>
        <button class="modal-close" type="button" aria-label="Close video">
          ×
        </button>
      </div>
      <div class="modal-body">
        <div class="modal-video">
          <iframe
            id="modalIframe"
            src=""
            title="YouTube video player"
            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
            allowfullscreen
          ></iframe>
        </div>
      </div>
    </div>
  </div>

  <script>
    // Smooth scroll helper
    function scrollToSection(id) {
      const el = document.getElementById(id);
      if (!el) return;
      window.scrollTo({
        top: el.offsetTop - 40,
        behavior: "smooth",
      });
    }

    // Modal logic
    const modalBackdrop = document.getElementById("videoModal");
    const modalIframe = document.getElementById("modalIframe");
    const modalTitle = document.getElementById("modalTitle");
    const modalCloseBtn = document.querySelector(".modal-close");

    function openVideoModal(videoUrl, title) {
      modalIframe.src = videoUrl + "?autoplay=1";
      modalTitle.textContent = title || "";
      modalBackdrop.classList.add("active");
    }

    function closeVideoModal() {
      modalBackdrop.classList.remove("active");
      modalIframe.src = "";
      modalTitle.textContent = "";
    }

    modalCloseBtn.addEventListener("click", closeVideoModal);
    modalBackdrop.addEventListener("click", (e) => {
      if (e.target === modalBackdrop) {
        closeVideoModal();
      }
    });

    // Attach click handlers to hero and cards
    document
      .querySelectorAll(".video-card")
      .forEach((card) => {
        card.addEventListener("click", () => {
          const url = card.getAttribute("data-video");
          const title = card.querySelector(".video-title")?.textContent || "";
          if (url) openVideoModal(url, title);
        });
      });

    const heroVisual = document.querySelector(".hero-visual");
    if (heroVisual) {
      const heroPlay = heroVisual.querySelector(".play-pill");
      const heroUrl = heroVisual.getAttribute("data-video");
      heroPlay.addEventListener("click", (e) => {
        e.stopPropagation();
        openVideoModal(heroUrl, "Featured piece");
      });
      heroVisual.addEventListener("click", (e) => {
        // Avoid double‑trigger when clicking the pill
        if (e.target.closest(".play-pill")) return;
        openVideoModal(heroUrl, "Featured piece");
      });
    }

    // Year in footer
    document.getElementById("year").textContent =
      new Date().getFullYear();
  </script>
</body>
</html>
