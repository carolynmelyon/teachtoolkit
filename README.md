[index.html](https://github.com/user-attachments/files/27070707/index.html)
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>TEACH Toolkit &mdash; Teletherapy-Enabled Action for Caregivers at Home</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,700;1,400;1,700&family=DM+Sans:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
/* ═══════════════════════════════════════════════
   TEACH TOOLKIT — Design System
   Warm editorial · Family-centered · Accessible
═══════════════════════════════════════════════ */

/* === TOKENS === */
:root {
  /* Brand */
  --teal:        #2a9d8f;
  --teal-light:  #4dbdaf;
  --teal-dark:   #1d7a6d;
  --teal-faint:  #e6f7f5;
  --teal-faint2: #f0faf9;

  /* Warm accent */
  --terra:       #e07a5f;
  --terra-light: #f2aa96;
  --terra-faint: #fdf1ee;

  /* Neutrals */
  --ink:         #1a2e2b;
  --forest:      #264e47;
  --body:        #2d3d3a;
  --muted:       #5c7570;
  --faint:       #8aadaa;
  --border:      #c8deda;
  --border-soft: #e0eeec;
  --cream:       #f8fdfb;
  --off-white:   #fdfffe;
  --parchment:   #eef8f6;
  --sand:        #f3f9f8;

  /* Layout */
  --radius-sm:   4px;
  --radius:      10px;
  --radius-lg:   16px;
  --shadow-sm:   0 1px 4px rgba(26,46,43,0.07);
  --shadow:      0 2px 16px rgba(26,46,43,0.10);
  --shadow-lg:   0 8px 40px rgba(26,46,43,0.14);
  --trans:       all 0.22s ease;
}

/* === RESET === */
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
html { scroll-behavior: smooth; font-size: 16px; }
body {
  font-family: 'DM Sans', 'Helvetica Neue', sans-serif;
  background: var(--cream);
  color: var(--body);
  line-height: 1.75;
  overflow-x: hidden;
  -webkit-font-smoothing: antialiased;
}
a { color: var(--teal-dark); }
a:hover { color: var(--teal); }

/* === SKIP LINK === */
.skip-link {
  position: absolute; top: -120px; left: 1rem;
  background: var(--teal); color: white;
  padding: 0.5rem 1rem; border-radius: 0 0 6px 6px;
  font-size: 0.88rem; font-weight: 600;
  text-decoration: none; z-index: 9999;
  transition: top 0.2s;
}
.skip-link:focus { top: 0; }

/* === PROGRESS === */
#progress-bar {
  position: fixed; top: 0; left: 0; height: 3px;
  background: linear-gradient(90deg, var(--teal), var(--teal-light));
  width: 0%; z-index: 1001; transition: width 0.1s;
}

/* === NAV === */
nav {
  position: fixed; top: 3px; left: 0; right: 0;
  background: rgba(248,253,251,0.97);
  backdrop-filter: blur(16px) saturate(1.4);
  border-bottom: 1px solid var(--border);
  z-index: 900; padding: 0 2.5rem;
  display: flex; align-items: center;
  justify-content: space-between; height: 60px;
}
.nav-logo {
  font-family: 'Playfair Display', Georgia, serif;
  font-weight: 700; font-size: 1.05rem;
  color: var(--teal-dark); text-decoration: none;
  letter-spacing: -0.01em;
}
.nav-logo span {
  color: var(--muted); font-weight: 400; font-size: 0.73rem;
  display: block; line-height: 1.2;
  font-family: 'DM Sans', sans-serif;
  letter-spacing: 0;
}
.nav-links { display: flex; gap: 0; list-style: none; align-items: center; }
.nav-links a {
  text-decoration: none; font-size: 0.72rem; font-weight: 600;
  color: var(--muted); padding: 0.3rem 0.7rem; border-radius: 20px;
  transition: var(--trans); letter-spacing: 0.04em; text-transform: uppercase;
}
.nav-links a:hover { color: var(--teal); background: var(--teal-faint); }
.nav-links a.active { color: var(--teal); background: var(--teal-faint); }
.nav-menu-btn {
  display: none; background: none; border: none;
  cursor: pointer; padding: 0.4rem; color: var(--body);
}
.mobile-nav {
  display: none; position: fixed; top: 63px; left: 0; right: 0;
  background: var(--off-white); border-bottom: 1px solid var(--border);
  z-index: 899; padding: 0.75rem 2rem; flex-direction: column;
  box-shadow: var(--shadow);
}
.mobile-nav.open { display: flex; }
.mobile-nav a {
  text-decoration: none; font-size: 0.92rem; color: var(--muted);
  padding: 0.7rem 0; border-bottom: 1px solid var(--border-soft);
}
.mobile-nav a:last-child { border-bottom: none; }

/* === SECTION NAV === */
.section-nav {
  background: white;
  border-bottom: 1px solid var(--border);
  padding: 0 2.5rem;
  display: flex; overflow-x: auto; scrollbar-width: none;
  position: sticky; top: 63px; z-index: 800;
  box-shadow: 0 1px 0 var(--border);
}
.section-nav::-webkit-scrollbar { display: none; }
.section-pill {
  display: inline-flex; align-items: center;
  text-decoration: none; font-size: 0.71rem; font-weight: 600;
  color: var(--muted); padding: 0.9rem 0.85rem;
  white-space: nowrap; transition: var(--trans);
  letter-spacing: 0.05em; text-transform: uppercase;
  border-bottom: 2px solid transparent;
}
.section-pill:hover { color: var(--teal); border-bottom-color: var(--border); }
.section-pill.active { color: var(--teal); border-bottom-color: var(--teal); }

/* === LAYOUT === */
main { padding-top: 63px; }
.content-section { max-width: 700px; margin: 0 auto; padding: 4.5rem 2rem; }
.section-divider { border: none; border-top: 1px solid var(--border); }
.section-alt { background: white; }
.section-warm { background: var(--terra-faint); }

/* === TYPOGRAPHY === */
.section-kicker {
  display: inline-block;
  font-family: 'DM Sans', sans-serif;
  font-size: 0.7rem; font-weight: 700; letter-spacing: 0.18em;
  text-transform: uppercase; color: var(--teal);
  margin-bottom: 0.75rem;
  background: var(--teal-faint);
  padding: 0.2rem 0.65rem; border-radius: 20px;
}
h2 {
  font-family: 'Playfair Display', Georgia, serif;
  font-size: clamp(1.85rem, 3.5vw, 2.6rem);
  font-weight: 700; line-height: 1.15;
  color: var(--ink); margin-bottom: 1.5rem;
  letter-spacing: -0.02em;
}
h3 {
  font-family: 'Playfair Display', Georgia, serif;
  font-size: 1.25rem; font-weight: 700;
  color: var(--forest); margin-top: 2.5rem; margin-bottom: 0.6rem;
  letter-spacing: -0.01em;
}
p { margin-bottom: 1.15rem; line-height: 1.78; }
.lead {
  font-size: 1.1rem; color: var(--body); margin-bottom: 1.75rem;
  line-height: 1.75;
}

/* === HERO === */
.hero { position: relative; overflow: hidden; }
.hero-image-wrap { width: 100%; height: 480px; overflow: hidden; position: relative; }
.hero-image-wrap img {
  width: 100%; height: 100%; object-fit: cover;
  object-position: center 25%; display: block;
}
.hero-image-wrap::after {
  content: ''; position: absolute; inset: 0;
  background: linear-gradient(
    170deg,
    rgba(26,46,43,0.4) 0%,
    rgba(26,46,43,0.65) 45%,
    rgba(26,46,43,0.92) 100%
  );
}
.hero-text {
  position: absolute; bottom: 0; left: 0; right: 0;
  padding: 2.5rem 3.5rem 3.5rem; z-index: 2;
}
.hero-kicker {
  display: inline-block;
  font-family: 'DM Sans', sans-serif;
  font-size: 0.7rem; font-weight: 700; letter-spacing: 0.18em;
  text-transform: uppercase; color: var(--teal-light);
  margin-bottom: 1rem;
  background: rgba(77,189,175,0.18);
  border: 1px solid rgba(77,189,175,0.35);
  padding: 0.3rem 0.8rem; border-radius: 20px;
}
.hero h1 {
  font-family: 'Playfair Display', Georgia, serif;
  font-size: clamp(2.4rem, 5.5vw, 4rem);
  font-weight: 700; line-height: 1.08;
  color: white; margin-bottom: 0.5rem;
  letter-spacing: -0.03em;
}
.hero-subtitle {
  font-size: 0.78rem; color: rgba(255,255,255,0.48);
  margin-bottom: 1.25rem; letter-spacing: 0.1em;
  text-transform: uppercase; font-weight: 400;
}
.hero-intro {
  font-size: 1.1rem; line-height: 1.7;
  color: rgba(255,255,255,0.88); max-width: 540px;
}

/* === IMAGES === */
.toolkit-img {
  width: 100%; border-radius: var(--radius-lg);
  margin: 2.5rem 0 0.5rem; display: block;
  object-fit: cover; box-shadow: var(--shadow-lg);
}
.toolkit-img-caption {
  font-size: 0.8rem; color: var(--faint);
  margin-bottom: 2.25rem; font-style: italic;
  text-align: center; letter-spacing: 0.01em;
}

/* === PULLQUOTE === */
.pullquote {
  border-left: 4px solid var(--terra);
  padding: 0.25rem 0 0.25rem 1.5rem;
  margin: 2.25rem 0;
}
.pullquote p {
  font-family: 'Playfair Display', Georgia, serif;
  font-size: 1.12rem; font-style: italic;
  color: var(--forest); margin-bottom: 0; line-height: 1.65;
}

/* === CALLOUT — use sparingly === */
.callout {
  background: var(--teal-faint2);
  border: 1px solid var(--border);
  border-left: 4px solid var(--teal);
  border-radius: 0 var(--radius) var(--radius) 0;
  padding: 1.1rem 1.4rem; margin: 1.75rem 0;
}
.callout-label {
  display: block;
  font-family: 'DM Sans', sans-serif;
  font-size: 0.68rem; font-weight: 700; letter-spacing: 0.14em;
  text-transform: uppercase; color: var(--teal-dark);
  margin-bottom: 0.35rem;
}
.callout-label-sage { color: var(--forest); }
.callout p { margin-bottom: 0; font-style: italic; font-size: 0.97rem; }
.callout-plain p { font-style: normal; }

/* === SCENARIO === */
.scenario {
  background: var(--sand);
  border: 1px solid var(--border-soft);
  border-radius: var(--radius);
  padding: 1.25rem 1.5rem; margin: 1.75rem 0;
  position: relative;
}
.scenario::before {
  content: '';
  position: absolute; top: 0; left: 0;
  width: 4px; height: 100%;
  background: var(--terra);
  border-radius: var(--radius) 0 0 var(--radius);
}
.scenario-label {
  display: block;
  font-family: 'DM Sans', sans-serif;
  font-size: 0.68rem; font-weight: 700; letter-spacing: 0.14em;
  text-transform: uppercase; color: var(--terra);
  margin-bottom: 0.45rem;
}
.scenario p { margin-bottom: 0; font-style: italic; font-size: 0.97rem; }

/* === LISTS === */
.body-list {
  list-style: none; padding: 0;
  margin: 0.5rem 0 1.5rem;
  display: flex; flex-direction: column; gap: 0.5rem;
}
.body-list li {
  padding-left: 1.5rem; position: relative;
  font-size: 1rem; line-height: 1.72;
}
.body-list li::before {
  content: '→'; position: absolute; left: 0;
  color: var(--teal); font-weight: 600;
}

/* === ACTION INGREDIENT HEADER === */
.ingredient-header {
  padding-top: 2.25rem; margin-top: 3.5rem;
  border-top: 2px solid var(--border);
}
.ingredient-num {
  font-family: 'DM Sans', sans-serif;
  font-size: 0.68rem; font-weight: 700; letter-spacing: 0.18em;
  text-transform: uppercase; color: var(--teal);
  margin-bottom: 0.25rem; display: block;
  background: var(--teal-faint);
  display: inline-block;
  padding: 0.18rem 0.65rem; border-radius: 20px;
  margin-bottom: 0.6rem;
}
.ingredient-title {
  font-family: 'Playfair Display', Georgia, serif;
  font-size: clamp(1.5rem, 2.5vw, 2rem);
  font-weight: 700; color: var(--ink);
  margin-bottom: 0.5rem; line-height: 1.2;
  letter-spacing: -0.02em;
}
.ingredient-why {
  font-size: 1rem; color: var(--muted);
  font-style: italic; margin-bottom: 1.75rem; line-height: 1.7;
  padding-bottom: 1.5rem; border-bottom: 1px solid var(--border-soft);
}

/* === ACTION SUMMARY === */
.action-summary {
  background: var(--teal-faint);
  border-left: 4px solid var(--teal);
  border-radius: 0 var(--radius) var(--radius) 0;
  padding: 1.1rem 1.4rem; margin-bottom: 2rem;
}
.action-summary-label {
  font-family: 'DM Sans', sans-serif;
  font-size: 0.68rem; font-weight: 700; letter-spacing: 0.14em;
  text-transform: uppercase; color: var(--teal-dark);
  margin-bottom: 0.35rem; display: block;
}
.action-summary p { margin-bottom: 0; font-size: 0.97rem; }

/* === STEP === */
.step {
  display: flex; gap: 1.25rem; align-items: flex-start;
  padding: 1.4rem 0; border-bottom: 1px solid var(--border-soft);
}
.step:last-child { border-bottom: none; }
.step-num {
  flex-shrink: 0; width: 34px; height: 34px;
  border-radius: 50%;
  background: var(--teal);
  color: white; display: flex; align-items: center;
  justify-content: center;
  font-family: 'DM Sans', sans-serif;
  font-size: 0.82rem; font-weight: 700; margin-top: 2px;
  box-shadow: 0 2px 8px rgba(42,157,143,0.3);
}
.step-content { flex: 1; }
.step-title {
  font-family: 'Playfair Display', Georgia, serif;
  font-weight: 700; color: var(--ink);
  font-size: 1.05rem; margin-bottom: 0.3rem; display: block;
}
.step-body { font-size: 0.97rem; color: var(--body); margin-bottom: 0.5rem; }
.step-script {
  background: white;
  border: 1px solid var(--border);
  border-left: 3px solid var(--teal-light);
  border-radius: 0 var(--radius-sm) var(--radius-sm) 0;
  padding: 0.75rem 1rem; margin-top: 0.65rem;
  font-style: italic; font-size: 0.93rem; color: var(--body);
}
.step-script::before {
  content: 'What to say: ';
  font-style: normal; font-weight: 700; color: var(--teal-dark);
  font-family: 'DM Sans', sans-serif;
  font-size: 0.65rem; letter-spacing: 0.1em; text-transform: uppercase;
  display: block; margin-bottom: 0.25rem;
}
.step-note {
  font-size: 0.85rem; color: var(--muted); margin-top: 0.4rem;
  font-style: italic;
}

/* === STRATEGY BLOCK === */
.strategy-block {
  border: 1px solid var(--border);
  border-top: 3px solid var(--teal);
  border-radius: 0 0 var(--radius) var(--radius);
  padding: 1.5rem 1.6rem; margin-bottom: 1.25rem;
  background: white;
  box-shadow: var(--shadow-sm);
  transition: box-shadow 0.2s;
}
.strategy-block:hover { box-shadow: var(--shadow); }
.strategy-name {
  font-family: 'Playfair Display', Georgia, serif;
  font-weight: 700; color: var(--ink);
  font-size: 1.1rem; margin-bottom: 0.25rem; display: block;
}
.strategy-when {
  font-family: 'DM Sans', sans-serif;
  font-size: 0.68rem; font-weight: 700; letter-spacing: 0.12em;
  text-transform: uppercase; color: var(--teal);
  margin-bottom: 0.9rem; display: block;
}
.strategy-steps { margin: 0 0 0.75rem; list-style: none; padding: 0; }
.strategy-steps li {
  font-size: 0.97rem; line-height: 1.7; color: var(--body);
  padding-left: 1.4rem; position: relative; margin-bottom: 0.3rem;
}
.strategy-steps li::before {
  content: '→'; position: absolute; left: 0;
  color: var(--teal); font-weight: 600; font-size: 0.88rem;
}

/* === TABLE === */
.duo-table {
  width: 100%; border-collapse: collapse; margin: 1.5rem 0;
  font-size: 0.92rem;
}
.duo-table thead tr { border-bottom: 2px solid var(--ink); }
.duo-table thead th {
  padding: 0.65rem 1rem;
  font-family: 'DM Sans', sans-serif;
  font-size: 0.68rem; font-weight: 700;
  letter-spacing: 0.12em; text-transform: uppercase;
  text-align: left; color: var(--muted);
}
.duo-table tbody tr { border-bottom: 1px solid var(--border-soft); }
.duo-table tbody tr:last-child { border-bottom: none; }
.duo-table tbody tr:hover { background: var(--teal-faint2); }
.duo-table td { padding: 0.9rem 1rem; line-height: 1.6; vertical-align: top; }
.duo-table td:first-child { font-weight: 600; width: 44%; color: var(--forest); }

/* === RESOURCE TABLE === */
.resource-table {
  width: 100%; border-collapse: collapse; margin: 1.25rem 0;
  font-size: 0.92rem;
}
.resource-table th {
  text-align: left; padding: 0.65rem 1rem;
  font-family: 'DM Sans', sans-serif;
  font-size: 0.68rem; font-weight: 700; letter-spacing: 0.12em;
  text-transform: uppercase; color: var(--muted);
  border-bottom: 2px solid var(--ink);
}
.resource-table td {
  padding: 0.9rem 1rem; border-bottom: 1px solid var(--border-soft);
  vertical-align: top; line-height: 1.62;
}
.resource-table tr:hover td { background: var(--teal-faint2); }
.resource-table tr:last-child td { border-bottom: none; }
.resource-table td:first-child {
  font-weight: 700; color: var(--forest); width: 22%;
  font-family: 'DM Sans', sans-serif;
}

/* === IF/THEN TABLE === */
.ifthen-table {
  width: 100%; border-collapse: collapse; margin: 1.25rem 0;
  font-size: 0.93rem;
}
.ifthen-table thead tr { border-bottom: 2px solid var(--ink); }
.ifthen-table thead th {
  padding: 0.65rem 1rem;
  font-family: 'DM Sans', sans-serif;
  font-size: 0.68rem; font-weight: 700; letter-spacing: 0.12em;
  text-transform: uppercase; color: var(--muted); text-align: left;
}
.ifthen-table tbody tr { border-bottom: 1px solid var(--border-soft); }
.ifthen-table tbody tr:last-child { border-bottom: none; }
.ifthen-table tbody tr:hover { background: var(--sand); }
.ifthen-table td { padding: 0.95rem 1rem; vertical-align: top; line-height: 1.65; }
.ifthen-table td:first-child {
  font-style: italic; color: var(--forest); width: 38%;
  font-weight: 600; font-style: normal;
}

/* === DO/DONT === */
.do-dont { display: grid; grid-template-columns: 1fr 1fr; gap: 2rem; margin: 1.75rem 0; }
.do-col h4 {
  font-family: 'DM Sans', sans-serif;
  font-size: 0.68rem; font-weight: 700; letter-spacing: 0.14em;
  text-transform: uppercase; margin-bottom: 0.75rem; color: var(--teal-dark);
}
.dont-col h4 {
  font-family: 'DM Sans', sans-serif;
  font-size: 0.68rem; font-weight: 700; letter-spacing: 0.14em;
  text-transform: uppercase; margin-bottom: 0.75rem; color: var(--body);
}
.do-col ul, .dont-col ul { list-style: none; display: flex; flex-direction: column; gap: 0.4rem; }
.do-col li, .dont-col li {
  font-size: 0.93rem; line-height: 1.55;
  padding-left: 1.25rem; position: relative;
}
.do-col li::before { content: '✓'; position: absolute; left: 0; color: var(--teal); }
.dont-col li::before { content: '✗'; position: absolute; left: 0; color: var(--muted); }

/* === TIMELINE === */
.timeline { margin: 1.5rem 0; display: flex; flex-direction: column; }
.timeline-item { display: flex; gap: 1.25rem; }
.timeline-marker { display: flex; flex-direction: column; align-items: center; flex-shrink: 0; padding-top: 4px; }
.timeline-dot { width: 10px; height: 10px; border-radius: 50%; background: var(--teal); flex-shrink: 0; }
.timeline-line { width: 1px; flex: 1; min-height: 20px; background: var(--border); margin: 4px 0; }
.timeline-item:last-child .timeline-line { display: none; }
.timeline-content { padding-bottom: 1.75rem; flex: 1; }
.timeline-period {
  display: block;
  font-family: 'DM Sans', sans-serif;
  font-size: 0.68rem; font-weight: 700; letter-spacing: 0.1em;
  text-transform: uppercase; color: var(--teal); margin-bottom: 0.15rem;
}
.timeline-content h4 {
  font-family: 'Playfair Display', Georgia, serif;
  font-size: 1rem; font-weight: 700; color: var(--ink); margin: 0 0 0.3rem;
}
.timeline-content p { font-size: 0.93rem; color: var(--muted); margin-bottom: 0; }

/* === SECTION OPENER/CLOSER === */
.section-opener {
  background: white;
  border: 1px solid var(--border-soft);
  border-left: 4px solid var(--teal);
  border-radius: 0 var(--radius) var(--radius) 0;
  padding: 1.3rem 1.5rem; margin-bottom: 3rem;
  box-shadow: var(--shadow-sm);
}
.opener-label {
  font-family: 'DM Sans', sans-serif;
  font-size: 0.68rem; font-weight: 700; letter-spacing: 0.14em;
  text-transform: uppercase; color: var(--teal); margin-bottom: 0.5rem;
}
.section-opener p { font-size: 0.95rem; color: var(--body); margin-bottom: 0.75rem; font-style: italic; }
.opener-list { list-style: none; padding: 0; margin: 0; display: flex; flex-direction: column; gap: 0.3rem; }
.opener-list li {
  font-size: 0.88rem; color: var(--muted);
  padding-left: 1.1rem; position: relative; line-height: 1.5;
}
.opener-list li::before { content: '→'; position: absolute; left: 0; color: var(--teal); font-size: 0.8rem; }

.section-closer {
  background: var(--parchment);
  border: 1px solid var(--border-soft);
  border-radius: var(--radius);
  padding: 1.3rem 1.5rem; margin-top: 3rem;
}
.closer-label {
  font-family: 'DM Sans', sans-serif;
  font-size: 0.68rem; font-weight: 700; letter-spacing: 0.14em;
  text-transform: uppercase; color: var(--forest); margin-bottom: 0.75rem;
}
.closer-list { list-style: none; padding: 0; margin: 0; display: flex; flex-direction: column; gap: 0.5rem; }
.closer-list li {
  font-size: 0.93rem; color: var(--body);
  padding-left: 1.1rem; position: relative; line-height: 1.55;
}
.closer-list li::before { content: '→'; position: absolute; left: 0; color: var(--teal); font-size: 0.8rem; }

/* === ROLE BOX === */
.role-box {
  display: grid; grid-template-columns: 1fr 1fr; gap: 1px;
  background: var(--border);
  border: 1px solid var(--border);
  border-radius: var(--radius-lg); overflow: hidden;
  margin: 1.75rem 0; box-shadow: var(--shadow-sm);
}
.role-col { background: white; padding: 1.35rem 1.5rem; }
.role-col h4 {
  font-family: 'DM Sans', sans-serif;
  font-size: 0.68rem; font-weight: 700; letter-spacing: 0.14em;
  text-transform: uppercase; margin-bottom: 0.75rem;
}
.role-col.yours h4 { color: var(--teal-dark); }
.role-col.theirs h4 { color: var(--muted); }
.role-col ul { list-style: none; padding: 0; display: flex; flex-direction: column; gap: 0.45rem; }
.role-col li { font-size: 0.93rem; line-height: 1.55; padding-left: 1.2rem; position: relative; color: var(--body); }
.role-col.yours li::before { content: '✓'; position: absolute; left: 0; color: var(--teal); font-weight: 700; }
.role-col.theirs li::before { content: '→'; position: absolute; left: 0; color: var(--muted); }

/* === SPARKNOTES === */
.sn-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 1px; background: var(--border);
  border: 1px solid var(--border);
  border-radius: var(--radius-lg);
  overflow: hidden; margin: 2rem 0;
  box-shadow: var(--shadow);
}
.sn-block {
  padding: 1.6rem 1.6rem;
  background: white;
  transition: background 0.18s;
}
.sn-block:hover { background: var(--teal-faint2); }
.sn-block-full {
  grid-column: 1 / -1;
  background: var(--teal-faint);
  border-top: 3px solid var(--teal);
}
.sn-block-full:hover { background: var(--teal-faint); }
.sn-num {
  font-family: 'DM Sans', sans-serif;
  font-size: 0.68rem; font-weight: 700; letter-spacing: 0.1em;
  text-transform: uppercase; color: var(--teal); margin-bottom: 0.3rem;
  line-height: 1.4;
}
.sn-title {
  font-family: 'Playfair Display', Georgia, serif;
  font-size: 1rem; font-weight: 700;
  color: var(--ink); margin-bottom: 0.9rem; line-height: 1.3;
}
.sn-list { list-style: none; padding: 0; margin: 0; display: flex; flex-direction: column; gap: 0.5rem; }
.sn-list li {
  font-size: 0.91rem; line-height: 1.62; color: var(--body);
  padding-left: 1.1rem; position: relative;
}
.sn-list li::before { content: '→'; position: absolute; left: 0; color: var(--teal); font-weight: 600; }
.sn-list-two-col { columns: 2; column-gap: 2rem; }
.sn-link {
  color: var(--teal-dark); text-decoration: underline;
  text-decoration-color: rgba(42,157,143,0.3); font-weight: 700;
}
.sn-link:hover { text-decoration-color: var(--teal); color: var(--teal); }

/* === QUOTES (testimonials) === */
.quote-section {
  background: var(--parchment);
  border-top: 1px solid var(--border);
  border-bottom: 1px solid var(--border);
  padding: 4rem 2.5rem;
}
.quote-kicker {
  display: block;
  font-family: 'DM Sans', sans-serif;
  font-size: 0.68rem; font-weight: 700; letter-spacing: 0.18em;
  text-transform: uppercase; color: var(--terra); margin-bottom: 2.5rem;
}
.quote-stack { display: flex; flex-direction: column; }
.light-quote {
  padding: 1.75rem 0 1.75rem 2rem;
  border-left: 3px solid var(--terra-light);
  border-bottom: 1px solid var(--border-soft);
}
.light-quote:last-child { border-bottom: none; }
.light-quote p {
  font-family: 'Playfair Display', Georgia, serif;
  font-size: 1.05rem; font-style: italic;
  color: var(--body); line-height: 1.78; margin-bottom: 0;
}

/* === CONCLUSION === */
.light-conclusion {
  background: var(--ink);
  color: white;
  padding: 5.5rem 2.5rem;
  text-align: center;
}
.light-conclusion .conclusion-inner { max-width: 620px; margin: 0 auto; }
.light-conclusion h2 {
  color: white;
  font-family: 'Playfair Display', Georgia, serif;
}
.light-conclusion h3 {
  font-family: 'DM Sans', sans-serif;
  font-size: 0.68rem; font-weight: 700; letter-spacing: 0.18em;
  text-transform: uppercase; color: var(--teal-light); margin-top: 2.5rem;
}
.light-conclusion p { color: rgba(255,255,255,0.82); }
.light-conclusion .callout {
  background: rgba(255,255,255,0.07);
  border-color: rgba(255,255,255,0.15);
  border-left-color: var(--teal-light);
}
.light-conclusion .callout p { color: rgba(255,255,255,0.85); }
.light-conclusion .callout-label { color: var(--teal-light); }
.light-conclusion .conclusion-img {
  width: 100%; max-width: 420px;
  border-radius: var(--radius-lg);
  margin: 2.25rem auto; display: block;
  object-fit: cover;
  box-shadow: 0 12px 48px rgba(0,0,0,0.4);
}
.light-conclusion .final-message {
  font-family: 'Playfair Display', Georgia, serif;
  font-size: 1.4rem; font-style: italic; color: var(--teal-light);
  margin-top: 2.5rem; line-height: 1.55;
  border-top: 1px solid rgba(255,255,255,0.12);
  padding-top: 2.5rem;
}

/* === YOU ARE READY / APPENDIX === */
.appendix-section { background: var(--sand); border-top: 1px solid var(--border); }

/* === QUICK REFERENCE === */
#reference { background: var(--parchment); border-top: 1px solid var(--border); }
.ref-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
  gap: 1px; margin: 2rem 0 0;
  border: 1px solid var(--border);
  border-radius: var(--radius-lg); overflow: hidden;
  box-shadow: var(--shadow);
}
.ref-block {
  padding: 1.4rem 1.5rem;
  border-right: 1px solid var(--border);
  border-bottom: 1px solid var(--border);
  background: white; transition: background 0.18s;
}
.ref-block:hover { background: var(--teal-faint2); }
.ref-heading {
  font-family: 'DM Sans', sans-serif;
  font-size: 0.68rem; font-weight: 700; letter-spacing: 0.1em;
  text-transform: uppercase; color: var(--teal-dark);
  margin-bottom: 0.85rem; line-height: 1.4;
}
.ref-list { list-style: none; padding: 0; margin: 0; display: flex; flex-direction: column; gap: 0.5rem; }
.ref-list li {
  font-size: 0.91rem; line-height: 1.6; color: var(--body);
  padding-left: 1.1rem; position: relative;
}
.ref-list li::before { content: '→'; position: absolute; left: 0; color: var(--teal); font-weight: 600; }

/* === REFLECT === */
.reflect-box {
  border-top: 1px solid var(--border);
  border-bottom: 1px solid var(--border);
  padding: 2.25rem 0; margin: 2.5rem 0;
}
.reflect-box h3 { margin-top: 0; }
.reflect-label {
  display: block; font-size: 0.9rem; color: var(--muted);
  margin-bottom: 0.4rem; font-style: italic;
}
.reflect-field {
  width: 100%; min-height: 72px;
  background: white;
  border: 1.5px solid var(--border);
  border-radius: var(--radius);
  padding: 0.8rem 1rem;
  font-family: 'DM Sans', sans-serif;
  font-size: 0.95rem; color: var(--body);
  resize: vertical; transition: var(--trans);
  line-height: 1.62; margin-bottom: 1.1rem; display: block;
}
.reflect-field:focus {
  outline: none; border-color: var(--teal);
  box-shadow: 0 0 0 3px rgba(42,157,143,0.12);
}
.reflect-field::placeholder { color: var(--faint); }

/* === MANUAL COMPONENTS === */
.callout-plain p { font-style: normal; }

/* === ACCESSIBILITY === */
:focus-visible {
  outline: 3px solid var(--teal);
  outline-offset: 3px; border-radius: 3px;
}
@media (forced-colors: active) {
  .ref-block, .sn-block, .callout, .scenario, .step { border: 1px solid ButtonText; }
}
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after { transition-duration: 0.01ms !important; }
  .fade-up { opacity: 1 !important; transform: none !important; }
}

/* === ANIMATIONS === */
.fade-up { opacity: 0; transform: translateY(18px); transition: opacity 0.5s ease, transform 0.5s ease; }
.fade-up.visible { opacity: 1; transform: translateY(0); }

/* === RESPONSIVE === */
@media (max-width: 720px) {
  .nav-links { display: none; }
  .nav-menu-btn { display: block; }
  .hero-image-wrap { height: 340px; }
  .hero-text { padding: 1.5rem 1.5rem 2.5rem; }
  .content-section { padding: 3rem 1.25rem; }
  .do-dont { grid-template-columns: 1fr; gap: 1.5rem; }
  .section-nav { padding: 0 1rem; }
  .quote-section { padding: 3rem 1.5rem; }
  .light-conclusion { padding: 4rem 1.5rem; }
  .sn-list-two-col { columns: 1; }
  .role-box { grid-template-columns: 1fr; }
}

/* === PRINT === */
@media print {
  nav, .section-nav, #progress-bar, .skip-link { display: none; }
  main { padding-top: 0; }
  .fade-up { opacity: 1; transform: none; }
  body { font-size: 11pt; font-family: Georgia, serif; }
  .hero-image-wrap { display: none; }
  .hero { background: white; }
  .hero-text { position: static; padding: 1rem 0; }
  .hero h1, .hero-subtitle, .hero-intro, .hero-kicker { color: #000; }
  .light-conclusion { background: white; text-align: left; padding: 2rem 0; color: #000; }
  .light-conclusion h2, .light-conclusion p, .light-conclusion h3 { color: #000; }
  .sn-grid, .ref-grid { grid-template-columns: repeat(2, 1fr); }
  .sn-block, .ref-block { break-inside: avoid; background: white; }
  a { color: #000; }
}

  .sn-link-row {
    margin-top: 1rem;
    padding-top: 0.75rem;
    border-top: 1px solid var(--border-soft);
  }
  .sn-link-row .sn-link {
    font-size: 0.8rem; font-weight: 700;
    letter-spacing: 0.04em;
  }
  /* Remove sn-num styling from sn-title used alone */
  .sn-block .sn-title:first-child { margin-top: 0; }


  /* Mobile table handling */
  @media (max-width: 720px) {
    .duo-table, .resource-table, .ifthen-table {
      display: block; overflow-x: auto;
      -webkit-overflow-scrolling: touch;
      white-space: nowrap;
    }
    .duo-table td, .resource-table td, .ifthen-table td,
    .duo-table th, .resource-table th, .ifthen-table th {
      white-space: normal; min-width: 120px;
    }
    .resource-table td:first-child { min-width: 90px; }
  }



  /* === ACTIONS OVERVIEW CARD GRID === */
  .actions-overview {
    margin: 2.5rem 0;
  }
  .actions-overview-header {
    margin-bottom: 1.5rem;
    padding-bottom: 1.25rem;
    border-bottom: 2px solid var(--border);
  }
  .actions-card-grid {
    display: flex;
    flex-direction: column;
    border: 1px solid var(--border);
    border-radius: var(--radius-lg);
    overflow: hidden;
    box-shadow: var(--shadow);
  }
  .action-card {
    display: flex;
    gap: 0;
    border-bottom: 1px solid var(--border);
    transition: background 0.18s;
  }
  .action-card:hover { background: var(--teal-faint2); }
  .action-card-last { border-bottom: none; }
  .action-card-num {
    flex-shrink: 0;
    width: 52px;
    display: flex;
    align-items: center;
    justify-content: center;
    background: var(--teal);
    color: white;
    font-family: 'Playfair Display', Georgia, serif;
    font-size: 1.5rem;
    font-weight: 700;
    letter-spacing: -0.02em;
    border-right: 1px solid rgba(255,255,255,0.15);
  }
  .action-card:nth-child(even) .action-card-num {
    background: var(--teal-dark);
  }
  .action-card-body {
    flex: 1;
    padding: 1.1rem 1.4rem;
    background: white;
    min-width: 0;
  }
  .action-card:hover .action-card-body { background: transparent; }
  .action-card-name {
    display: block;
    font-family: 'Playfair Display', Georgia, serif;
    font-size: 1rem;
    font-weight: 700;
    color: var(--ink);
    margin-bottom: 0.2rem;
  }
  .action-card-what {
    display: block;
    font-size: 0.85rem;
    color: var(--muted);
    font-style: italic;
    margin-bottom: 0.85rem;
    padding-bottom: 0.85rem;
    border-bottom: 1px solid var(--border-soft);
  }
  .action-card-cols {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 1.25rem;
  }
  .action-card-col-label {
    display: block;
    font-family: 'DM Sans', sans-serif;
    font-size: 0.65rem;
    font-weight: 700;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: var(--teal-dark);
    margin-bottom: 0.3rem;
  }
  .action-card-col p {
    font-size: 0.88rem;
    line-height: 1.6;
    color: var(--body);
    margin-bottom: 0;
  }
  .action-card-list {
    list-style: none;
    padding: 0; margin: 0;
    display: flex;
    flex-direction: column;
    gap: 0.3rem;
  }
  .action-card-list li {
    font-size: 0.88rem;
    line-height: 1.55;
    color: var(--body);
    padding-left: 1rem;
    position: relative;
  }
  .action-card-list li::before {
    content: '→';
    position: absolute; left: 0;
    color: var(--teal); font-weight: 600;
    font-size: 0.78rem;
  }
  /* Remove old actions-table CSS that is no longer needed */
  @media (max-width: 720px) {
    .action-card-num { width: 38px; font-size: 1.15rem; }
    .action-card-body { padding: 0.9rem 1rem; }
    .action-card-cols { grid-template-columns: 1fr; gap: 0.75rem; }
    .action-card-what { margin-bottom: 0.65rem; padding-bottom: 0.65rem; }
  }

  /* Legacy table scroll (kept for other tables) */
  .table-scroll-wrap {
    overflow-x: auto;
    -webkit-overflow-scrolling: touch;
    border-radius: var(--radius);
    border: 1px solid var(--border);
  }
  .actions-table {
    border: none;
    margin: 0;
  }
  .actions-table thead th { background: var(--ink); color: white; }
  .actions-table tbody tr:nth-child(odd) td { background: var(--teal-faint2); }
  .actions-table td { white-space: normal; vertical-align: top; font-size: 0.88rem; }
  .actions-table td:first-child { font-weight: 700; color: var(--teal-dark); }
  @media (max-width: 720px) {
    .actions-overview h3 { font-size: 1.1rem; }
  }

</style>
</head>
<body>

<a href="#main-content" class="skip-link">Skip to main content</a>
<div id="progress-bar"></div>

<nav id="top-nav">
  <a href="#sparknotes" class="nav-logo">TEACH Toolkit<span>Teletherapy-Enabled Action for Caregivers at Home</span></a>
  <ul class="nav-links" role="list">
    <li><a href="#sparknotes">Start Here</a></li>
    <li><a href="#ready">Section 1</a></li>
    <li><a href="#actions">Section 2</a></li>
    <li><a href="#section3">Section 3</a></li>
    <li><a href="#appendix">You Are Ready</a></li>
  </ul>
  <button class="nav-menu-btn" id="menu-btn" aria-label="Menu">
    <svg width="20" height="20" viewBox="0 0 20 20" fill="none" stroke="currentColor" stroke-width="1.75" stroke-linecap="round">
      <line x1="3" y1="5" x2="17" y2="5"/><line x1="3" y1="10" x2="17" y2="10"/><line x1="3" y1="15" x2="17" y2="15"/>
    </svg>
  </button>
</nav>

<div class="mobile-nav" id="mobile-nav">
  <a href="#sparknotes" onclick="closeMobileNav()">Start Here: The Essentials</a>
  <a href="#ready" onclick="closeMobileNav()">Section 1: Getting Ready for a Session</a>
  <a href="#actions" onclick="closeMobileNav()">Section 2: What to Do During a Session</a>
  <a href="#section3" onclick="closeMobileNav()">Section 3: When Things Don&rsquo;t Go as Planned</a>
  <a href="#appendix" onclick="closeMobileNav()">You Are Ready: Reflection and FAQs</a>
</div>

<main id="main-content">

<!-- ══ HERO ══ -->
<section class="hero" id="intro">
  <div class="hero-image-wrap">
    <img src="images/img00.jpg" alt="Caregiver and child engaged together during a teletherapy session">
  </div>
  <div class="hero-text">
    <span class="hero-kicker">Caregiver Resource &middot; Pediatric Occupational Therapy &middot; Teletherapy</span>
    <h1>The TEACH Toolkit</h1>
    <p class="hero-subtitle">Teletherapy-Enabled Action for Caregivers at Home</p>
    <p class="hero-intro">A practical resource for caregivers taking an active role in their child&rsquo;s teletherapy.</p>
  </div>
</section>

<div class="section-nav" role="navigation" aria-label="Jump to section">
  <a href="#sparknotes" class="section-pill">Start Here</a>
  <a href="#ready" class="section-pill">Section 1: Getting Ready</a>
  <a href="#actions" class="section-pill">Section 2: What to Do</a>
  <a href="#section3" class="section-pill">Section 3: When Things Don&rsquo;t Go as Planned</a>
  <a href="#appendix" class="section-pill">You Are Ready</a>
</div>


<!-- ══════════════════════════════════════════════════════
     START HERE: THE ESSENTIALS  (not a numbered section)
══════════════════════════════════════════════════════ -->
<div id="sparknotes" role="region" aria-label="Start Here: The Essentials">
<div class="content-section">

  <h2>Start Here: The Essentials</h2>
  <p class="lead" style="color:var(--muted); margin-top:-0.75rem; margin-bottom:2.25rem; font-size:1rem;">Everything you need, all in one place.</p>

  <!-- What to Expect full-width -->
  <div class="sn-grid fade-up">

    <div class="sn-block sn-block-full">
      <div class="sn-num">What to Expect (and How This Toolkit Helps)</div>
      <div class="sn-title">Telehealth therapy may look different than you expected.</div>
      <ul class="sn-list">
        <li>Instead of the therapist working with your child in the same room, you will take a more active role during sessions.</li>
        <li>It is common to feel unsure at first. You may wonder if you are doing the right things.</li>
        <li>This toolkit is here to help you feel more prepared, more confident, and less unsure going into teletherapy sessions with your child. It walks you through what to do before a session, what to focus on during it, and how to make sense of what happened afterward.</li>
        <li>Some sections help you get set up, some show you exactly what to do in the moment, and others help you adjust when things feel hard or off track. The seven core actions are at the center of the toolkit. They are the things you can come back to during any session.</li>
        <li>You are not responsible for planning or directing therapy. Your role is to support your child&rsquo;s participation during the session using the strategies in this toolkit.</li>
      </ul>
      <p style="margin-top:0.85rem; margin-bottom:0; font-size:0.91rem; color:var(--muted); font-style:italic;">Here&rsquo;s a quick overview of what&rsquo;s included. When you have more time, each part connects to a section in the toolkit with more detail and examples.</p>
    </div>

    <!-- What Matters Most -->
    <div class="sn-block">
      <div class="sn-title">What Matters Most</div>
      <ul class="sn-list">
        <li>Your therapist guides the session. You help your child stay in it.</li>
        <li>It will probably look messier than you expect. That is okay.</li>
        <li>Nobody knows your child better than you do. That is the most useful thing you bring.</li>
      </ul>
      <div class="sn-link-row"><a href="#ready" class="sn-link">&rarr; Section 1: Getting Ready for a Session</a></div>
    </div>

    <!-- Before Every Session -->
    <div class="sn-block">
      <div class="sn-title">Before Every Session</div>
      <ul class="sn-list">
        <li>Device charged and Wi-Fi checked</li>
        <li>Space set up, camera positioned</li>
        <li>Familiar materials within reach</li>
        <li>Distractions reduced</li>
        <li>One slow breath for yourself</li>
      </ul>
      <div class="sn-link-row"><a href="#ready" class="sn-link">&rarr; Section 1: Getting Ready for a Session</a></div>
    </div>

    <!-- Seven Core Actions -->
    <div class="sn-block">
      <div class="sn-title">The Seven Core Actions</div>
      <ul class="sn-list">
        <li><strong>Remain regulated.</strong> You first.</li>
        <li><strong>Notice.</strong> Watch your child, not the screen.</li>
        <li><strong>Narrate.</strong> Say what you see.</li>
        <li><strong>Join.</strong> Enter the activity alongside them.</li>
        <li><strong>Adjust.</strong> When something is not working, change it.</li>
        <li><strong>Use real-life moments.</strong> Point out when something at home connects to what you are working on.</li>
        <li><strong>Stay present,</strong> even when everything falls apart.</li>
      </ul>
      <div class="sn-link-row"><a href="#actions" class="sn-link">&rarr; Section 2: What to Do During a Session</a></div>
    </div>

    <!-- Three Regulation Strategies -->
    <div class="sn-block">
      <div class="sn-title">Three Regulation Strategies</div>
      <ul class="sn-list">
        <li>Slow exhale: in 3&ndash;4, out 5&ndash;6, three times</li>
        <li>Grounding: feet into floor or fingers together, 10&ndash;20 seconds</li>
        <li>Self-talk cue: &ldquo;I can handle this&rdquo; or your own phrase</li>
      </ul>
      <div class="sn-link-row"><a href="#actions" class="sn-link">&rarr; Section 2: What to Do During a Session</a></div>
    </div>

    <!-- What to Say -->
    <div class="sn-block">
      <div class="sn-title">What to Say to Your Therapist</div>
      <ul class="sn-list">
        <li>&ldquo;She&rsquo;s starting to pull away.&rdquo;</li>
        <li>&ldquo;This isn&rsquo;t working for us right now.&rdquo;</li>
        <li>&ldquo;I&rsquo;m going to give him a minute.&rdquo;</li>
        <li>&ldquo;Can we try something different?&rdquo;</li>
        <li>&ldquo;He does better with this in the morning.&rdquo;</li>
      </ul>
      <div class="sn-link-row"><a href="#actions" class="sn-link">&rarr; Section 2: What to Do During a Session</a></div>
    </div>

    <!-- When Things Don't Go as Planned -->
    <div class="sn-block">
      <div class="sn-title">When Things Don&rsquo;t Go as Planned</div>
      <ul class="sn-list">
        <li>Child refuses: start with what they are already doing</li>
        <li>Child wanders: follow, stay present, do not force</li>
        <li>Meltdown: stop, get yourself grounded, then help them</li>
        <li>Tech fails: keep engaging your child while reconnecting</li>
        <li>You feel overwhelmed: <a href="#actions" class="sn-link">look for strategies in Section 2</a></li>
      </ul>
      <div class="sn-link-row"><a href="#section3" class="sn-link">&rarr; Section 3: When Things Don&rsquo;t Go as Planned</a></div>
    </div>

    <!-- After Each Session — full width -->
    <div class="sn-block sn-block-full" style="background:white; border-top:none;">
      <div class="sn-title">After Each Session (2 Minutes)</div>
      <ul class="sn-list">
        <li><strong>Optional but useful.</strong></li>
        <li>Notice what worked, what didn&rsquo;t, and what your child responded to. Bring that into the next session.</li>
      </ul>
      <div class="sn-link-row"><a href="#appendix" class="sn-link">&rarr; You Are Ready: Reflection and FAQs</a></div>
    </div>



  </div><!-- /sn-grid -->
  <!-- What is Always True — standalone box like "One more thing" -->
  <div class="callout callout-plain fade-up" style="margin-top:1.5rem; background:var(--teal-faint); border-left-color:var(--teal); border-color:var(--border);">
    <span class="callout-label">What is Always True</span>
    <ul class="body-list" style="margin-bottom:0; margin-top:0.5rem;">
      <li>Your regulated state is the first thing your child needs</li>
      <li>Showing up is enough to start</li>
      <li>Messy sessions still give useful information</li>
      <li>Progress often shows up outside sessions first</li>
      <li>You know your child better than anyone on that screen</li>
    </ul>
  </div>

  <!-- One more thing -->
  <div class="callout callout-plain fade-up" style="margin-top:2rem;">
    <span class="callout-label">One more thing</span>
    <p>Every family is different. How comfortable you are with technology, what your child&rsquo;s day was like, whether you slept, whether your house is loud today. All of it matters. The seven actions in this toolkit work in all those situations. Your therapist is the person to talk to when you need to fit them to your specific kid.</p>
  </div>

  <!-- How to Use This Toolkit -->
  <h3 class="fade-up">How to Use This Toolkit</h3>
  <table class="duo-table fade-up">
    <thead><tr><th>When</th><th>What to Do</th></tr></thead>
    <tbody>
      <tr>
        <td>Before your first session</td>
        <td>Read through the full toolkit once so you know what to expect. <a href="#ready" class="sn-link">Section 1: Getting Ready for a Session</a> is a good place to go deeper before you begin.</td>
      </tr>
      <tr>
        <td>After your first session</td>
        <td>Come back to <a href="#sparknotes" class="sn-link">Start Here: The Essentials</a> to figure out where you want more support, then look more closely at those sections.</td>
      </tr>
      <tr>
        <td>During a session</td>
        <td>You do not need to read this during the session. The goal is to become familiar with the ideas so you can use them naturally. Instead of trying to balance reading this and supporting your child, lean back on what you remember from <a href="#actions" class="sn-link">Section 2: What to Do During a Session</a> and focus on one or two actions at a time.</td>
      </tr>
      <tr>
        <td>When something isn&rsquo;t working</td>
        <td>Think back to the ideas in <a href="#section3" class="sn-link">Section 3</a> and adjust from there. You can come back to that section later if you want more guidance.</td>
      </tr>
      <tr>
        <td>After a session</td>
        <td>Write down one thing you noticed. That becomes your starting point next time.<br><br><em>Before digging deeper, there is a <a href="#appendix" class="sn-link">Reflection and FAQ section</a> at the end of the toolkit.</em><br><br>Keep in mind what sections of the toolkit you would like to revisit before the next session.</td>
      </tr>
    </tbody>
  </table>

</div>
</div><!-- /sparknotes -->


<!-- ══════════════════════════════════════════════════════
     SECTION 1: GETTING READY FOR A SESSION
══════════════════════════════════════════════════════ -->
<hr class="section-divider">
<div id="ready" class="section-alt">
<div class="content-section">

  <span class="section-kicker">Section 1</span>
  <h2>Getting Ready for a Session</h2>

  <p class="lead fade-up">You do not need a perfect setup. But a little prep before each session makes a real difference. Most of the stuff that derails sessions is fixable ahead of time.</p>
  <p class="fade-up">Use this checklist before every session. It takes about five minutes.</p>

  <h3 class="fade-up">Before Every Session: Checklist</h3>
  <table class="resource-table fade-up">
    <thead><tr><th>Category</th><th>What to Have Ready</th></tr></thead>
    <tbody>
      <tr>
        <td>Technology</td>
        <td>Device charged or plugged in. Wifi connection checked. Camera and sound working. Do this five minutes before, not while the session is starting. Know how to reconnect if the call drops.</td>
      </tr>
      <tr>
        <td>Space</td>
        <td>A spot where your child can move freely. Camera aimed so the therapist can see your child clearly (face and hands). Enough room that you can sit next to your child or step in quickly.</td>
      </tr>
      <tr>
        <td>Materials</td>
        <td>Two or three of your child&rsquo;s favorite toys or familiar objects within reach. Any specific items your therapist asked you to have. Nothing elaborate. Familiar beats fancy every time.</td>
      </tr>
      <tr>
        <td>Distractions</td>
        <td>Siblings occupied or in another room. TV off. Your phone on silent and face-down. You need to be able to focus on your child for the full session.</td>
      </tr>
      <tr>
        <td>Your child</td>
        <td>Fed and not overtired if you can manage it. Wearing comfortable clothing for movement. Warned in advance that therapy is coming. A one-minute heads-up helps most kids transition. If they are in a bad place when the session starts, tell the therapist right away so they can adjust.</td>
      </tr>
      <tr>
        <td>Yourself</td>
        <td>Give yourself five minutes before the session. Step away from whatever you were doing. Expect it to be a little messy. Use one of the three calming strategies in Section 2 if you need to. You cannot help your child settle if you have not settled first.</td>
      </tr>
    </tbody>
  </table>

  <div class="callout fade-up">
    <span class="callout-label">About your therapist</span>
    <p>Let your therapist know you are using this toolkit. Share one observation at the start of each session: something you noticed during the week. At the end of each session, ask: &ldquo;Is there anything specific I should do differently?&rdquo; That one question will improve your sessions faster than anything else in this toolkit.</p>
  </div>

  <div class="callout fade-up">
    <span class="callout-label">If you are running late or things feel rushed</span>
    <p>Take one slow breath before you open the app. Let the therapist know you need a moment to settle. Starting a minute late is better than starting overwhelmed or reactive.</p>
  </div>

  <h3 class="fade-up">What a Good Session Space Looks Like</h3>
  <p class="fade-up">You do not need a dedicated therapy room. You need a space that works. Ideally:</p>
  <ul class="body-list fade-up">
    <li>Your child has room to move and engage without running out of the camera&rsquo;s view</li>
    <li>Lighting is good enough that the therapist can see your child&rsquo;s face and hands</li>
    <li>Background noise is low enough that you can hear the therapist clearly</li>
    <li>You can sit close enough to your child to step in quickly if needed</li>
  </ul>

  <img src="images/img01.jpg" alt="Caregiver and child working together at a laptop during a teletherapy session" class="toolkit-img fade-up">
  <p class="toolkit-img-caption fade-up">A workable space beats a perfect one every time.</p>

  <h3 class="fade-up">What If Your Child Is Not Ready When the Session Starts?</h3>
  <p class="fade-up">This is common and expected. You do not need to force engagement right away. Let the therapist know where your child is and ease in slowly. Most therapists will start with something low-key to allow your child time to warm up.</p>

</div>
</div><!-- /ready -->


<!-- ══════════════════════════════════════════════════════
     SECTION 2: WHAT TO DO DURING A SESSION
══════════════════════════════════════════════════════ -->
<hr class="section-divider">
<div id="actions">
<div class="content-section">

  <span class="section-kicker">Section 2</span>
  <h2>What to Do During a Session</h2>

  <p class="lead fade-up">There are seven things you can do during a session to help it go more smoothly. We call them actions. They are listed in order because each one builds on the next. Start with the first. Everything else depends on it.</p>

  <p class="fade-up">The first action, staying regulated, is the one everything else runs on. If you skip it, the others are harder to do well.</p>

  <p class="fade-up">Each session follows the same general flow. Before the session, you prepare (<a href="#ready">Section 1: Getting Ready for a Session</a>) and take a moment to settle yourself. During the session, you notice, narrate, join, adjust, and use real-life moments. After the session, you reflect on what you observed (<a href="#appendix">You Are Ready: Reflection and FAQs</a>). You will get to that part later.</p>

  <p class="fade-up">The shape stays the same every time: get ready, do the session, notice what happened.</p>
  <p class="fade-up">You do not need to read this during the session. The goal is to become familiar with the ideas so you can use them naturally. Start with the first action. The rest will follow.</p>

  <!-- The 7 Actions Quick Guide — inserted before Action 1 -->
  <div class="actions-overview fade-up">
    <div class="actions-overview-header">
      <span class="section-kicker" style="margin-bottom:0.5rem;">At a Glance</span>
      <h3 style="margin-top:0.25rem; margin-bottom:0.25rem;">The 7 Core Actions</h3>
      <p style="font-size:0.9rem; color:var(--muted); margin-bottom:0; font-style:italic;">Each builds on the one before it. Start with Action 1.</p>
    </div>

    <div class="actions-card-grid">

      <div class="action-card">
        <div class="action-card-num">1</div>
        <div class="action-card-body">
          <span class="action-card-name">Stay Regulated</span>
          <span class="action-card-what">Keeping yourself calm and steady during the session.</span>
          <div class="action-card-cols">
            <div class="action-card-col">
              <span class="action-card-col-label">Why it matters</span>
              <p>Your child often looks to you to understand how to react. When you are more settled, it helps them stay more settled too.</p>
            </div>
            <div class="action-card-col">
              <span class="action-card-col-label">What to do</span>
              <ul class="action-card-list">
                <li>Take one slow breath before the session starts</li>
                <li>Use a quick reset if needed: slow exhale, grounding, or a short phrase</li>
                <li>Pause before reacting</li>
              </ul>
            </div>
          </div>
        </div>
      </div>

      <div class="action-card">
        <div class="action-card-num">2</div>
        <div class="action-card-body">
          <span class="action-card-name">Notice</span>
          <span class="action-card-what">Paying attention to what your child is doing and how they are responding.</span>
          <div class="action-card-cols">
            <div class="action-card-col">
              <span class="action-card-col-label">Why it matters</span>
              <p>You can see things the therapist can&rsquo;t fully see on screen. What you notice helps guide the session.</p>
            </div>
            <div class="action-card-col">
              <span class="action-card-col-label">What to do</span>
              <ul class="action-card-list">
                <li>Watch your child more than the screen</li>
                <li>Look for small changes: getting louder, quieter, moving away</li>
                <li>Pay attention to early signs before things escalate</li>
              </ul>
            </div>
          </div>
        </div>
      </div>

      <div class="action-card">
        <div class="action-card-num">3</div>
        <div class="action-card-body">
          <span class="action-card-name">Narrate</span>
          <span class="action-card-what">Saying out loud what you are noticing.</span>
          <div class="action-card-cols">
            <div class="action-card-col">
              <span class="action-card-col-label">Why it matters</span>
              <p>Your therapist depends on your input to understand what is happening in the room.</p>
            </div>
            <div class="action-card-col">
              <span class="action-card-col-label">What to do</span>
              <ul class="action-card-list">
                <li>Say what you see in simple words</li>
                <li>Add context if you have it</li>
                <li>Let the therapist know what you&rsquo;re about to do</li>
              </ul>
            </div>
          </div>
        </div>
      </div>

      <div class="action-card">
        <div class="action-card-num">4</div>
        <div class="action-card-body">
          <span class="action-card-name">Join</span>
          <span class="action-card-what">Getting involved in the activity with your child.</span>
          <div class="action-card-cols">
            <div class="action-card-col">
              <span class="action-card-col-label">Why it matters</span>
              <p>Children are more likely to try something when they see you doing it too.</p>
            </div>
            <div class="action-card-col">
              <span class="action-card-col-label">What to do</span>
              <ul class="action-card-list">
                <li>Sit close to your child</li>
                <li>Start the activity if they aren&rsquo;t engaging</li>
                <li>Show interest and keep it light</li>
                <li>Step back once they get going</li>
              </ul>
            </div>
          </div>
        </div>
      </div>

      <div class="action-card">
        <div class="action-card-num">5</div>
        <div class="action-card-body">
          <span class="action-card-name">Adjust</span>
          <span class="action-card-what">Changing things when something isn&rsquo;t working.</span>
          <div class="action-card-cols">
            <div class="action-card-col">
              <span class="action-card-col-label">Why it matters</span>
              <p>Not every activity will work every time. Small changes can keep things from falling apart.</p>
            </div>
            <div class="action-card-col">
              <span class="action-card-col-label">What to do</span>
              <ul class="action-card-list">
                <li>If it&rsquo;s not working, change something</li>
                <li>Make the task easier or smaller</li>
                <li>Step in to help if needed</li>
                <li>Ask the therapist to try something different</li>
              </ul>
            </div>
          </div>
        </div>
      </div>

      <div class="action-card">
        <div class="action-card-num">6</div>
        <div class="action-card-body">
          <span class="action-card-name">Use Real-Life Moments</span>
          <span class="action-card-what">Using what&rsquo;s already happening in your home during the session.</span>
          <div class="action-card-cols">
            <div class="action-card-col">
              <span class="action-card-col-label">Why it matters</span>
              <p>Practicing skills in real-life situations helps them stick outside of sessions.</p>
            </div>
            <div class="action-card-col">
              <span class="action-card-col-label">What to do</span>
              <ul class="action-card-list">
                <li>Point out what&rsquo;s happening at home</li>
                <li>Connect activities to daily routines</li>
                <li>Try strategies during the week and share what happens</li>
              </ul>
            </div>
          </div>
        </div>
      </div>

      <div class="action-card action-card-last">
        <div class="action-card-num">7</div>
        <div class="action-card-body">
          <span class="action-card-name">Stay Present</span>
          <span class="action-card-what">Staying with your child, even when things are not going well.</span>
          <div class="action-card-cols">
            <div class="action-card-col">
              <span class="action-card-col-label">Why it matters</span>
              <p>Your presence helps your child feel supported, even during hard moments.</p>
            </div>
            <div class="action-card-col">
              <span class="action-card-col-label">What to do</span>
              <ul class="action-card-list">
                <li>Stay near your child</li>
                <li>Keep your body calm and open</li>
                <li>Avoid distractions</li>
                <li>Keep gently engaging without forcing</li>
              </ul>
            </div>
          </div>
        </div>
      </div>

    </div><!-- /actions-card-grid -->
  </div><!-- /actions-overview -->

    <!-- ── ACTION 1: REMAIN REGULATED ── -->
  <div class="ingredient-header fade-up" id="action1">
    <span class="ingredient-num">Action 1</span>
    <h3 class="ingredient-title">Remain Regulated</h3>
    <p class="ingredient-why">Here is something that took most parents a session or two to figure out: your child is not watching the screen as much as they are watching you. When something feels new or hard or uncertain, they look at your face first to decide how they should feel about it. Your child often looks to you to understand how to respond. When you are more settled, it can help them feel more settled too.</p>
  </div>

  <div class="action-summary fade-up">
    <span class="action-summary-label">What this means in practice</span>
    <p>Before you try to do anything for your kid, check in with yourself. If you are rushing in from a hectic morning, anxious about how the session is going to go, or already frustrated about something else entirely, that energy is going to come through. Use one of the three strategies below before you try to help. This is the best place to start, because everything else works better when you are settled first.</p>
  </div>

  <img src="images/img02.jpg" alt="Caregiver and child doing a calming breathing exercise together" class="toolkit-img fade-up">
  <p class="toolkit-img-caption fade-up">Getting yourself settled before the session is the first thing your child needs from you.</p>

  <h3 class="fade-up">Three Regulation Strategies</h3>
  <p class="fade-up">Use these before the session or any time during a session when you feel yourself reacting rather than responding.</p>

  <div class="strategy-block fade-up">
    <span class="strategy-name">1. Slow Your Exhale</span>
    <span class="strategy-when">Use: Before the session or when you feel tension rising</span>
    <ul class="strategy-steps">
      <li>Breathe in normally through your nose for 3 to 4 counts</li>
      <li>Breathe out slowly for 5 to 6 counts, longer than the inhale</li>
      <li>Repeat 3 times</li>
    </ul>
    <p class="step-note">No one on the call will notice you doing this. It works in under 30 seconds.</p>
  </div>

  <div class="strategy-block fade-up">
    <span class="strategy-name">2. Ground Through Your Body</span>
    <span class="strategy-when">Use: When things are starting to go sideways</span>
    <ul class="strategy-steps">
      <li>Press your feet into the floor and notice the pressure</li>
      <li>Or press your fingers gently together and hold for 10 to 20 seconds</li>
      <li>Focus on the sensation, not the chaos around you</li>
    </ul>
    <p class="step-note">This pulls your attention out of your head and back into your body. You can do it while staying fully present in the session.</p>
  </div>

  <div class="strategy-block fade-up">
    <span class="strategy-name">3. One Self-Talk Cue</span>
    <span class="strategy-when">Use: When your brain starts telling you this is all going wrong</span>
    <ul class="strategy-steps">
      <li>Choose one short phrase before the session starts and keep it ready</li>
      <li>When you catch yourself going down that road, say it silently once</li>
      <li>Then focus on the next immediate thing in front of you</li>
    </ul>
    <p class="step-note">Examples: &ldquo;I can handle this.&rdquo; Or: &ldquo;One step at a time.&rdquo; Or: &ldquo;It does not have to be perfect.&rdquo;</p>
  </div>

  <div class="callout fade-up">
    <span class="callout-label">How you know you are regulated enough to continue</span>
    <p>You can take a full breath. You can hear what the therapist is saying. You can watch your child without feeling like you have to immediately fix something. That is enough.</p>
  </div>

  <!-- ── ACTION 2: NOTICE ── -->
  <div class="ingredient-header fade-up" id="action2">
    <span class="ingredient-num">Action 2</span>
    <h3 class="ingredient-title">Notice</h3>
    <p class="ingredient-why">You have been watching your child your whole life. You can tell the difference between the fidget that means &ldquo;I&rsquo;m bored&rdquo; and the one that means &ldquo;I&rsquo;m about to lose it.&rdquo; You know what their pre-meltdown face looks like. You know which transitions are hard. Your therapist cannot see any of that from a screen. When you share what you notice, in real time, it changes what the therapist does next.</p>
  </div>

  <div class="action-summary fade-up">
    <span class="action-summary-label">What to watch for</span>
    <p>Watch your child, not the call. Glance at the therapist when you need to, but your main focus belongs on your kid. What you see right in front of you is more useful than anything happening on screen.</p>
  </div>

  <h3 class="fade-up">What to Notice</h3>
  <table class="duo-table fade-up">
    <thead><tr><th>What You See</th><th>What It Might Mean</th></tr></thead>
    <tbody>
      <tr><td>Child moves away from the screen</td><td>Overstimulated, bored, or needs a sensory break, not necessarily refusing</td></tr>
      <tr><td>Child gets louder or sillier</td><td>Often early dysregulation, not defiance. They may need input or movement.</td></tr>
      <tr><td>Child goes quiet or flat</td><td>May be shutting down. Check in gently before they fully disengage.</td></tr>
      <tr><td>Child repeats the same action</td><td>Often comfort-seeking. Something in the session may feel uncertain.</td></tr>
      <tr><td>Child looks at you instead of the screen</td><td>Checking your reaction. Your calm response tells them it is okay to keep going.</td></tr>
      <tr><td>Child engages indirectly</td><td>Listening or watching without facing the screen. They are still participating.</td></tr>
    </tbody>
  </table>

  <div class="scenario fade-up">
    <span class="scenario-label">What This Looks Like</span>
    <p>Your child has been doing well for ten minutes. You notice them start picking at their shirt and looking around the room. You have seen this before. It means they are running out of steam. You do not wait for them to fall apart. You make a quiet note of it so you can tell the therapist in the next moment.</p>
  </div>

  <!-- ── ACTION 3: NARRATE ── -->
  <div class="ingredient-header fade-up" id="action3">
    <span class="ingredient-num">Action 3</span>
    <h3 class="ingredient-title">Narrate</h3>
    <p class="ingredient-why">Your therapist is looking at a camera feed. You are physically in the room with your child. There is a lot happening that does not show up on a screen. When you say what you are noticing out loud, you are giving the therapist information they cannot get any other way. Say it. It is not interrupting. It is helping.</p>
  </div>

  <div class="action-summary fade-up">
    <span class="action-summary-label">The rule</span>
    <p>If you notice something, say it. You do not need to interpret it or know what it means. Just describe what you see. Your therapist will do the rest.</p>
  </div>

  <h3 class="fade-up">What to Say</h3>
  <p class="fade-up">Keep it simple and factual. You are not diagnosing. You are reporting. Short sentences work best.</p>

  <div class="step fade-up">
    <div class="step-num">1</div>
    <div class="step-content">
      <span class="step-title">Name what you see in your child&rsquo;s body or behavior</span>
      <p class="step-body">Describe what you actually see, not what you think it means.</p>
      <div class="step-script">&ldquo;She&rsquo;s starting to pull away.&rdquo; Or: &ldquo;He&rsquo;s getting louder.&rdquo; Or: &ldquo;She just went quiet.&rdquo; Or: &ldquo;He&rsquo;s looking at the door.&rdquo;</div>
    </div>
  </div>

  <div class="step fade-up">
    <div class="step-num">2</div>
    <div class="step-content">
      <span class="step-title">Add context if you have it</span>
      <p class="step-body">If you have a hunch about why, say that too. If you have no idea, that is fine. What you saw is enough.</p>
      <div class="step-script">&ldquo;This usually happens when she&rsquo;s getting tired.&rdquo; Or: &ldquo;I think the sound is bothering him.&rdquo; Or: &ldquo;He does better with this in the morning.&rdquo;</div>
    </div>
  </div>

  <div class="step fade-up">
    <div class="step-num">3</div>
    <div class="step-content">
      <span class="step-title">Tell the therapist what you are about to do</span>
      <p class="step-body">Before you step in to help your child, let the therapist know so they can adjust.</p>
      <div class="step-script">&ldquo;I&rsquo;m going to give her a minute.&rdquo; Or: &ldquo;I&rsquo;m going to move closer.&rdquo; Or: &ldquo;Can we try something different? This isn&rsquo;t landing for him right now.&rdquo;</div>
    </div>
  </div>

  <!-- ── ACTION 4: JOIN ── -->
  <div class="ingredient-header fade-up" id="action4">
    <span class="ingredient-num">Action 4</span>
    <h3 class="ingredient-title">Join</h3>
    <p class="ingredient-why">Think about the last time you tried to get your child interested in something new. It probably worked better when you were doing it too, right? Same thing here. When you pick up the toy or start the activity yourself, your child has something to watch and follow. You lower the &ldquo;I don&rsquo;t want to do this unfamiliar thing&rdquo; wall just by being in it with them.</p>
  </div>

  <div class="action-summary fade-up">
    <span class="action-summary-label">What joining looks like</span>
    <p>Pick up the toy. Start the action. Show interest in what the therapist is asking your child to do. You are not doing it for your child. You are doing it with them, or just slightly ahead of them, so they can watch and follow when they are ready.</p>
  </div>

  <div class="step fade-up">
    <div class="step-num">1</div>
    <div class="step-content">
      <span class="step-title">Position yourself near your child</span>
      <p class="step-body">Sit close enough to interact but not so close that you are doing the activity for them. Side by side is usually right.</p>
      <p class="step-note">Not hovering. Not at a distance. Close enough to reach them.</p>
    </div>
  </div>

  <div class="step fade-up">
    <div class="step-num">2</div>
    <div class="step-content">
      <span class="step-title">Pick up or touch the activity materials</span>
      <p class="step-body">If your child is not engaging, start the activity yourself. Stack the blocks. Pick up the crayon. Start drawing.</p>
      <div class="step-script">&ldquo;Look, I&rsquo;m going to try this.&rdquo; Or: &ldquo;Let&rsquo;s see what happens if we do it this way.&rdquo;</div>
    </div>
  </div>

  <div class="step fade-up">
    <div class="step-num">3</div>
    <div class="step-content">
      <span class="step-title">Act like it is actually interesting</span>
      <p class="step-body">Comment on what you are doing. Be curious out loud. Your child watches your face to decide if something is worth their attention.</p>
      <div class="step-script">&ldquo;Oh, this is interesting.&rdquo; Or: &ldquo;I wonder what this does.&rdquo; Or: &ldquo;Hm, this part is tricky.&rdquo;</div>
    </div>
  </div>

  <div class="step fade-up">
    <div class="step-num">4</div>
    <div class="step-content">
      <span class="step-title">Step back when your child joins in</span>
      <p class="step-body">Once your child is engaged, reduce your involvement gradually. The goal is to get them going, not to do it for them.</p>
      <p class="step-note">If they disengage again, step back in. This is a rhythm, not a one-time action.</p>
    </div>
  </div>

  <img src="images/img03.jpg" alt="Child and caregiver engaged together at a laptop during a session" class="toolkit-img fade-up">
  <p class="toolkit-img-caption fade-up">When you are in the activity, your child has a reason to join.</p>

  <!-- ── ACTION 5: ADJUST ── -->
  <div class="ingredient-header fade-up" id="action5">
    <span class="ingredient-num">Action 5</span>
    <h3 class="ingredient-title">Adjust</h3>
    <p class="ingredient-why">What worked last Tuesday may not work today. Your child slept badly, or had a hard morning, or just decided they are done with that activity. Adjusting in the moment is not giving up. It is reading your kid correctly. That is a skill, and it is a big one.</p>
  </div>

  <div class="action-summary fade-up">
    <span class="action-summary-label">The signal to adjust</span>
    <p>If it has been two minutes and the same thing is not working, change something. Do not wait. Do not let it build. Small adjustments early are a lot easier than big meltdowns later.</p>
  </div>

  <h3 class="fade-up">When and How to Adjust</h3>
  <table class="duo-table fade-up">
    <thead><tr><th>When You See This</th><th>Try This</th></tr></thead>
    <tbody>
      <tr><td>Child is completely stuck</td><td>Step in and assist. Break the task into a smaller piece. Narrate to the therapist what you are doing.</td></tr>
      <tr><td>Child is trying but frustrated</td><td>Stay close. Offer encouragement. Give them a moment before stepping in.</td></tr>
      <tr><td>Child is getting loud or overwhelmed or reactive</td><td>Pause the activity. Use one of your own calming strategies first. Then help your child settle before you keep going.</td></tr>
      <tr><td>Activity is not working at all</td><td>Tell the therapist directly: &ldquo;This isn&rsquo;t working for us right now.&rdquo; Ask to try something different.</td></tr>
      <tr><td>Child has moved away but is still nearby</td><td>Stay present and keep the activity going at a low level. They may re-engage when they are ready.</td></tr>
    </tbody>
  </table>

  <div class="callout callout-plain fade-up">
    <span class="callout-label">A quick adjustment toolkit</span>
    <p>When something is not working, try one of these in order:</p>
    <ul class="strategy-steps" style="margin-top:0.5rem;">
      <li>Make it smaller: break the task into one tiny piece instead of the whole thing</li>
      <li>Make it yours: start doing it yourself so your child can watch first</li>
      <li>Make it silly: lower the stakes by doing it wrong on purpose</li>
      <li>Make it theirs: ask your child what they want to do instead, then build from there</li>
    </ul>
  </div>

  <div class="callout fade-up">
    <span class="callout-label">Adjusting is not quitting</span>
    <p>You are not lowering the bar when you adjust. You are meeting your child where they are so they can keep going. That is good therapy, not failure.</p>
  </div>

  <div class="scenario fade-up">
    <span class="scenario-label">What This Looks Like</span>
    <p>The therapist introduces a new activity. Your child tries it once, then pushes it away and turns their back. You recognize this. It means they do not feel safe with something unfamiliar yet. Instead of pushing, you pick up the materials and start doing the activity yourself, narrating quietly. Within two minutes your child is watching. A minute later they join. You adjusted without making it a confrontation.</p>
  </div>

  <!-- ── ACTION 6: USE REAL-LIFE MOMENTS ── -->
  <div class="ingredient-header fade-up" id="action6">
    <span class="ingredient-num">Action 6</span>
    <h3 class="ingredient-title">Use Real-Life Moments</h3>
    <p class="ingredient-why">Here is the thing about teletherapy that nobody talks about enough: it happens in your actual house. That dog barking is not ruining the session. That sibling walking through might actually be useful. The snack your child is eating during the whole thing? Real life. And skills that get practiced where your child actually lives are way more likely to show up there later than skills practiced in a clinic and then expected to magically appear at home.</p>
  </div>

  <div class="action-summary fade-up">
    <span class="action-summary-label">What this means in practice</span>
    <p>When something in your house naturally connects to what the therapist is working on, use it. When the therapist suggests something, think about where that same thing shows up in your regular week. That is where it will actually stick.</p>
  </div>

  <div class="step fade-up">
    <div class="step-num">1</div>
    <div class="step-content">
      <span class="step-title">Name what is already happening around you</span>
      <p class="step-body">If something in the environment is relevant to what the therapist is working on, point it out. You do not need to manufacture teaching moments. You just need to notice the ones that are already there.</p>
      <div class="step-script">&ldquo;He does this same thing at dinner every night.&rdquo; Or: &ldquo;This is exactly what happens when we&rsquo;re getting ready for school.&rdquo; Or: &ldquo;She was doing this with her blocks this morning.&rdquo;</div>
    </div>
  </div>

  <div class="step fade-up">
    <div class="step-num">2</div>
    <div class="step-content">
      <span class="step-title">Connect session activities to daily routines</span>
      <p class="step-body">When the therapist introduces a strategy, ask yourself where in your daily routine you could practice the same thing. Mealtime, bath time, transitions between activities, getting dressed. These are your practice opportunities.</p>
      <div class="step-script">&ldquo;Could we try this at bath time?&rdquo; Or: &ldquo;This reminds me of what happens when we leave the park. Can we practice it that way?&rdquo;</div>
    </div>
  </div>

  <div class="step fade-up">
    <div class="step-num">3</div>
    <div class="step-content">
      <span class="step-title">Report back what you saw outside of sessions</span>
      <p class="step-body">If something from a previous session showed up in your child&rsquo;s daily life during the week, tell the therapist at the start of the next session. This is some of the most useful information a therapist can receive.</p>
      <div class="step-script">&ldquo;Something happened this week that I think is related to what we worked on.&rdquo; Or: &ldquo;He did the same thing at the grocery store on Thursday.&rdquo;</div>
    </div>
  </div>

  <div class="callout callout-plain fade-up">
    <span class="callout-label">Where to look for real-life moments</span>
    <ul class="strategy-steps" style="margin-top:0.5rem;">
      <li>Mealtime: fine motor, transitions, following directions, sitting together</li>
      <li>Getting dressed: sequencing, motor planning, frustration tolerance</li>
      <li>Leaving the house: transitions, emotional regulation, following multi-step directions</li>
      <li>Sibling or peer play: social skills, turn-taking, sharing attention</li>
      <li>Bath time: sensory regulation, body awareness, routine</li>
    </ul>
  </div>

  <div class="scenario fade-up">
    <span class="scenario-label">What This Looks Like</span>
    <p>The therapist is working on your child&rsquo;s ability to handle transitions. Your child resists every time the session activity changes. You tell the therapist: &ldquo;This is exactly what happens every morning when it is time to leave for school.&rdquo; The therapist adjusts the session to mirror that specific transition. Now you are practicing the real problem, in the real environment, with the right support. That is what home-based teletherapy makes possible.</p>
  </div>

  <!-- ── ACTION 7: STAY PRESENT ── -->
  <div class="ingredient-header fade-up" id="action7">
    <span class="ingredient-num">Action 7</span>
    <h3 class="ingredient-title">Stay Present</h3>
    <p class="ingredient-why">Some sessions are just hard. Your child refuses everything, nothing lands, you feel like you are watching a slow-motion disaster. In those moments, the most useful thing you can do is not fix it. It is just stay. Stay in the room. Stay calm. Stay with your kid. Your physical presence, just being there without panicking, tells your child more than any words could. That is real. It matters.</p>
  </div>

  <div class="action-summary fade-up">
    <span class="action-summary-label">What staying present means</span>
    <p>It means you do not check your phone. You do not wander to another room. You do not visibly give up. Even when you are not doing anything, your steady presence is working.</p>
  </div>

  <div class="step fade-up">
    <div class="step-num">1</div>
    <div class="step-content">
      <span class="step-title">Keep your body near your child</span>
      <p class="step-body">If your child moves away, follow them, at a respectful distance. You do not need to pull them back. You need to stay in the same space.</p>
    </div>
  </div>

  <div class="step fade-up">
    <div class="step-num">2</div>
    <div class="step-content">
      <span class="step-title">Keep your face neutral and open</span>
      <p class="step-body">Your child is watching your face to decide how worried they should be. A calm face, even when you do not feel calm, gives them permission to settle.</p>
      <p class="step-note">This is where regulation (Action 1) feeds directly back in. A regulated caregiver has a regulated face.</p>
    </div>
  </div>

  <div class="step fade-up">
    <div class="step-num">3</div>
    <div class="step-content">
      <span class="step-title">Keep low-level engagement going</span>
      <p class="step-body">You do not need to push the session forward. Keep interacting with the materials at a quiet level. Talk softly. Show interest without demanding anything from your child.</p>
      <div class="step-script">&ldquo;I&rsquo;m just going to keep going over here.&rdquo; Or: &ldquo;No rush. I&rsquo;ll be right here.&rdquo;</div>
    </div>
  </div>

  <div class="step fade-up">
    <div class="step-num">4</div>
    <div class="step-content">
      <span class="step-title">Let the therapist know what is happening</span>
      <p class="step-body">You do not need to manage this alone. Tell the therapist what you are seeing and what you are doing. They will adjust the plan around you.</p>
      <div class="step-script">&ldquo;He&rsquo;s not ready right now. I&rsquo;m just going to stay close.&rdquo; Or: &ldquo;I&rsquo;m giving her a minute to settle. Can we hold on?&rdquo;</div>
    </div>
  </div>

  <div class="step fade-up">
    <div class="step-num">5</div>
    <div class="step-content">
      <span class="step-title">Notice one small thing that is still working</span>
      <p class="step-body">Even in the hardest sessions, something is usually still happening. Your child is in the room. They glanced at the screen once. They picked up a toy the therapist mentioned. Find it. Name it quietly to yourself or to the therapist. That is your foothold for what comes next.</p>
      <div class="step-script">&ldquo;She&rsquo;s still in the room, which is something.&rdquo; Or: &ldquo;He picked up the block you mentioned. That&rsquo;s a start.&rdquo;</div>
    </div>
  </div>

  <img src="images/img04.jpg" alt="Caregiver staying present while child moves away during a session" class="toolkit-img fade-up">
  <p class="toolkit-img-caption fade-up">Staying nearby without forcing engagement is one of the most effective things you can do.</p>

  <div class="callout fade-up">
    <span class="callout-label">What progress looks like in early sessions</span>
    <p>Progress is often invisible at first. It might look like your child staying engaged for two minutes longer than last week, or returning to an activity after leaving it, or needing slightly less support to settle. These are real changes. Write them down after the session if you can. They add up faster than you think.</p>
  </div>

  <img src="images/img05.jpg" alt="Two scenes showing caregivers and children engaged in everyday activities" class="toolkit-img fade-up">
  <p class="toolkit-img-caption fade-up">Progress often shows up outside of sessions first, in daily routines, in transitions, in how your child handles something hard.</p>

</div>
</div><!-- /actions -->


<!-- ══════════════════════════════════════════════════════
     SECTION 3: WHEN THINGS DON'T GO AS PLANNED
══════════════════════════════════════════════════════ -->
<hr class="section-divider">
<div id="section3" class="section-warm">
<div class="content-section">

  <span class="section-kicker">Section 3</span>
  <h2>When Things Don&rsquo;t Go as Planned</h2>

  <p class="lead fade-up">Every parent has those sessions. Your kid refuses everything. The whole thing falls apart. You hang up feeling like nothing happened. It did. Hard sessions tell you and your therapist things that smooth ones never could. Flip to this section when things go sideways.</p>

  <p class="fade-up">The ideas below are ways to adjust when something is not working. The core actions themselves stay the same: notice, narrate, join, adjust, use real-life moments, stay present. What you can change is when you use them, how much you use them, and how you fit them to what your specific child needs in that moment.</p>

  <p class="fade-up">Before using any of the responses below: use Action 1 first. When you are running on empty, nothing in this toolkit works as well. That is just how it goes.</p>

  <h3 class="fade-up">If/Then Guide</h3>
  <table class="ifthen-table fade-up">
    <thead><tr><th>If this happens&hellip;</th><th>Then do this</th></tr></thead>
    <tbody>
      <tr><td>Your child refuses to start the session</td><td>Do not force it. Let the therapist know. Start with something your child is already doing. Use joining (Action 4) to ease in through their current activity rather than the planned one.</td></tr>
      <tr><td>Your child wanders away from the screen</td><td>Follow them. Stay present. Keep low-level engagement going. Tell the therapist: &ldquo;She&rsquo;s moved away. I&rsquo;m going to stay with her.&rdquo; Do not try to drag them back.</td></tr>
      <tr><td>Your child has a meltdown</td><td>Stop the activity. Tell the therapist: &ldquo;We need a minute.&rdquo; Focus on helping your child calm down, not on getting back to the activity. Use your own calming strategy first. Reconnect with the therapist once your child is settled.</td></tr>
      <tr><td>The activity falls apart completely</td><td>Tell the therapist what you are seeing. Ask to shift to something else. A session that changes direction is still a productive session.</td></tr>
      <tr><td>You feel overwhelmed mid-session</td><td>Use Action 1 immediately: slow exhale, grounding, or self-talk cue. You do not need to say anything to the therapist unless you need to pause. None of these will look weird on a video call. Nobody will notice.</td></tr>
      <tr><td>Technology fails</td><td>Keep interacting with your child while you reconnect. The session does not stop because the screen freezes. Text or call your therapist to let them know you are reconnecting.</td></tr>
      <tr><td>You are not sure if you are doing it right</td><td>If you are present, you are doing it. If you are noticing, you are doing it. Ask the therapist at the end of the session: &ldquo;Is there anything I should do differently?&rdquo; They will tell you.</td></tr>
      <tr><td>Nothing seemed to work in the whole session</td><td>That session still counted. It gave your therapist information. Note one specific thing you noticed about your child. That is your contribution from that session, even if nothing else went right.</td></tr>
    </tbody>
  </table>

  <div class="callout fade-up">
    <span class="callout-label">A note on bad sessions</span>
    <p>Every family has them. The ones who make progress are not the ones whose sessions always go well. They are the ones who show up again the next week.</p>
  </div>

</div>
</div><!-- /section3 -->


<!-- ══════════════════════════════════════════════════════
     YOU ARE READY: REFLECTION AND FAQS
══════════════════════════════════════════════════════ -->
<hr class="section-divider">
<div id="appendix" class="appendix-section">
<div class="content-section">

  <span class="section-kicker">You Are Ready</span>
  <h2>Reflection and FAQs</h2>

  <p class="lead fade-up">Every time you show up, something useful happens. Even the sessions that feel like a complete disaster. Noticing what your kid needs and trying to respond to it, even when you get it wrong, that is exactly what this is supposed to look like.</p>

  <p class="fade-up">None of the seven things in this toolkit are new to you. You already do versions of all of them. This just gives them names and a way to use them on purpose when it counts.</p>

  <img src="images/img06.jpg" alt="Grandparents and grandchild building together, representing the everyday connection that supports a child's development" class="toolkit-img fade-up">
  <p class="toolkit-img-caption fade-up">You are not just in the room with your kid. You are the reason it works.</p>

  <div class="callout fade-up">
    <span class="callout-label">What it looks like when it&rsquo;s working</span>
    <p>Over time, some caregivers may notice that sessions feel less chaotic, their child stays engaged a little longer, or skills begin to show up in daily routines.</p>
  </div>

  <!-- REFLECTION FIRST -->
  <div class="reflect-box fade-up" style="margin-top:2.5rem;">
    <h3>After Each Session: Reflect for Two Minutes</h3>
    <p style="color:var(--muted); font-style:italic; font-size:0.93rem; margin-bottom:1.5rem;">Optional but useful. The more you notice, the more you bring to the next session.</p>
    <label class="reflect-label">One thing I noticed about my child today:</label>
    <textarea class="reflect-field" aria-label="One thing I noticed about my child today" placeholder="A behavior, a reaction, something that surprised you..."></textarea>
    <label class="reflect-label">One thing that worked, even a little:</label>
    <textarea class="reflect-field" aria-label="One thing that worked" placeholder="Something you tried, something your child responded to..."></textarea>
    <label class="reflect-label">One thing to try differently next time:</label>
    <textarea class="reflect-field" aria-label="One thing to try differently" placeholder="No wrong answers..."></textarea>
  </div>

  <!-- FAQS SECOND -->
  <h3 class="fade-up">Frequently Asked Questions</h3>
  <table class="ifthen-table fade-up">
    <thead><tr><th>Question</th><th>Answer</th></tr></thead>
    <tbody>
      <tr><td>How much should I talk during a session?</td><td>As much as you need to. Narrating what you see is one of the most useful things you can do. There is no such thing as too much useful information for your therapist.</td></tr>
      <tr><td>What if I disagree with something the therapist suggests?</td><td>Say so. You know your child and your home. If a suggestion does not fit, telling the therapist is more useful than trying to make it work.</td></tr>
      <tr><td>My child ignores the video call entirely. Is this even working?</td><td>Probably yes. Kids often take in more than it looks like. Listening without looking still counts. If your child stays in the room and occasionally engages, that counts. Talk to your therapist about what you are seeing.</td></tr>
      <tr><td>How do I know if I am stepping in too much?</td><td>A simple rule: if your child is trying, step back. If your child is stuck or escalating, step in. Your therapist can also tell you when they want you to pull back. Ask them directly if you are not sure.</td></tr>
      <tr><td>What if I miss a session or have to cancel?</td><td>Contact your therapist as soon as you know. Consistent attendance matters for progress but life happens. What matters most is coming back after a gap, not the gap itself.</td></tr>
      <tr><td>Should I tell the therapist about things that happened between sessions?</td><td>Yes, always. Behaviors, reactions, breakthroughs, hard moments: anything that seems related to what you are working on is useful. Start each session with one observation from the week.</td></tr>
      <tr><td>What if my child does great in sessions but nothing changes at home?</td><td>This is common early on. This takes time. Look for the real-life moments where you can practice the same skills outside of sessions (see <a href="#action6">Section 2, Action 6</a>). Tell your therapist what you are seeing at home so they can adjust.</td></tr>
      <tr><td>Am I supposed to do activities with my child between sessions?</td><td>Your therapist may suggest things to try during the week. These are not homework assignments. They are practice opportunities. Try them when they fit naturally into your routine. Report back what happened.</td></tr>
    </tbody>
  </table>

</div>
</div><!-- /appendix -->




<div style="text-align:center; padding: 3rem 2rem 4rem; background:var(--ink);">
  <p style="font-family:'Playfair Display',Georgia,serif; font-size:1.4rem; font-style:italic; color:var(--teal-light); max-width:480px; margin:0 auto; line-height:1.55;">You are not just in the room with your kid.<br>You are the reason it works.</p>
</div>

</main>

<script>
  const pb = document.getElementById('progress-bar');
  window.addEventListener('scroll', () => {
    const p = window.scrollY / (document.documentElement.scrollHeight - window.innerHeight) * 100;
    pb.style.width = p + '%';
  });
  document.getElementById('menu-btn').addEventListener('click', () => {
    document.getElementById('mobile-nav').classList.toggle('open');
  });
  function closeMobileNav() { document.getElementById('mobile-nav').classList.remove('open'); }
  const navLinks = document.querySelectorAll('.nav-links a, .section-pill');
  document.querySelectorAll('[id]').forEach(s => {
    new IntersectionObserver(entries => {
      entries.forEach(e => {
        if (e.isIntersecting) navLinks.forEach(l => {
          l.classList[l.getAttribute('href') === '#' + e.target.id ? 'add' : 'remove']('active');
        });
      });
    }, { rootMargin: '-63px 0px -70% 0px' }).observe(s);
  });
  const fo = new IntersectionObserver(entries => {
    entries.forEach(e => {
      if (e.isIntersecting) { setTimeout(() => e.target.classList.add('visible'), 50); fo.unobserve(e.target); }
    });
  }, { rootMargin: '0px 0px -40px 0px' });
  document.querySelectorAll('.fade-up').forEach(el => fo.observe(el));
</script>
</body>
</html>
<img width="900" height="900" alt="img06" src="https://github.com/user-attachments/assets/b9201832-5348-4d4e-bcf0-507f8be80407" />
<img width="900" height="600" alt="img05" src="https://github.com/user-attachments/assets/8496c15e-88bd-4a2d-bc05-bb7a6c8b8849" />
<img width="900" height="600" alt="img04" src="https://github.com/user-attachments/assets/c24f4aba-2fd6-4b6a-82e4-ca0f19918a09" />
<img width="900" height="600" alt="img03" src="https://github.com/user-attachments/assets/dc835472-4e63-4283-b95b-cb86ffe58e8e" />
<img width="900" height="900" alt="img02" src="https://github.com/user-attachments/assets/dd30fab8-9d8e-4714-9f7d-2b174913e974" />
<img width="786" height="484" alt="img01" src="https://github.com/user-attachments/assets/bcddbdb0-a57f-4feb-adbd-37cc8f7808e0" />
<img width="900" height="717" alt="img00" src="https://github.com/user-attachments/assets/3d3b966a-af58-401d-9ce5-c13551bfa581" />

