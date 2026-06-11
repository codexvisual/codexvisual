<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Moklasur Rahman Rahat | GitHub Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&family=JetBrains+Mono:wght@300;400;700&family=Syne:wght@700;800&display=swap" rel="stylesheet" />
<style>
  :root {
    --bg: #050810;
    --surface: #0a0f1e;
    --card: #0d1428;
    --border: rgba(56, 178, 172, 0.15);
    --teal: #38B2AC;
    --teal-glow: rgba(56,178,172,0.4);
    --purple: #7C3AED;
    --pink: #EC4899;
    --gold: #F59E0B;
    --text: #E2E8F0;
    --muted: #64748B;
    --white: #ffffff;
  }

  *, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }

  html { scroll-behavior: smooth; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Space Grotesk', sans-serif;
    overflow-x: hidden;
    min-height: 100vh;
  }

  /* ===== STARFIELD BACKGROUND ===== */
  #stars-canvas {
    position: fixed;
    top: 0; left: 0;
    width: 100%; height: 100%;
    z-index: 0;
    pointer-events: none;
  }

  /* ===== GRID OVERLAY ===== */
  .grid-overlay {
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(56,178,172,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(56,178,172,0.03) 1px, transparent 1px);
    background-size: 50px 50px;
    z-index: 0;
    pointer-events: none;
  }

  .container {
    position: relative;
    z-index: 1;
    max-width: 900px;
    margin: 0 auto;
    padding: 0 20px 80px;
  }

  /* ===== HERO SECTION ===== */
  .hero {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    text-align: center;
    position: relative;
    padding: 40px 0;
  }

  /* Animated ring */
  .avatar-ring {
    position: relative;
    width: 160px;
    height: 160px;
    margin: 0 auto 32px;
  }

  .avatar-ring::before, .avatar-ring::after {
    content: '';
    position: absolute;
    border-radius: 50%;
    animation: spin-ring 4s linear infinite;
  }

  .avatar-ring::before {
    inset: -6px;
    background: conic-gradient(from 0deg, var(--teal), var(--purple), var(--pink), var(--teal));
    z-index: -1;
    animation-duration: 3s;
  }

  .avatar-ring::after {
    inset: -12px;
    background: conic-gradient(from 180deg, transparent 60%, var(--teal-glow));
    z-index: -2;
    animation-duration: 5s;
    animation-direction: reverse;
  }

  @keyframes spin-ring {
    to { transform: rotate(360deg); }
  }

  .avatar-inner {
    width: 100%;
    height: 100%;
    border-radius: 50%;
    background: linear-gradient(135deg, var(--surface), var(--card));
    border: 3px solid var(--bg);
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: 'Syne', sans-serif;
    font-size: 52px;
    font-weight: 800;
    background: linear-gradient(135deg, #38B2AC, #7C3AED);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    position: relative;
    z-index: 1;
    overflow: hidden;
  }

  .avatar-bg {
    position: absolute;
    inset: 0;
    border-radius: 50%;
    background: var(--card);
    z-index: 0;
  }

  .avatar-letter {
    position: relative;
    z-index: 1;
    background: linear-gradient(135deg, #38B2AC, #7C3AED, #EC4899);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    font-size: 60px;
    font-family: 'Syne', sans-serif;
    font-weight: 800;
    animation: pulse-letter 3s ease-in-out infinite;
  }

  @keyframes pulse-letter {
    0%, 100% { filter: drop-shadow(0 0 8px var(--teal-glow)); }
    50% { filter: drop-shadow(0 0 20px var(--teal-glow)) drop-shadow(0 0 40px rgba(124,58,237,0.3)); }
  }

  /* Name */
  .hero-name {
    font-family: 'Syne', sans-serif;
    font-size: clamp(42px, 8vw, 72px);
    font-weight: 800;
    line-height: 1;
    letter-spacing: -2px;
    background: linear-gradient(135deg, #fff 0%, #38B2AC 40%, #7C3AED 70%, #EC4899 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    margin-bottom: 8px;
    animation: gradient-shift 5s ease infinite alternate;
    background-size: 200% 200%;
  }

  @keyframes gradient-shift {
    0% { background-position: 0% 50%; }
    100% { background-position: 100% 50%; }
  }

  /* Typewriter */
  .typewriter-container {
    height: 36px;
    display: flex;
    align-items: center;
    justify-content: center;
    margin: 16px 0 28px;
  }

  .typewriter-prefix {
    color: var(--muted);
    font-family: 'JetBrains Mono', monospace;
    font-size: 15px;
    margin-right: 8px;
  }

  .typewriter-text {
    font-family: 'JetBrains Mono', monospace;
    font-size: 18px;
    font-weight: 700;
    color: var(--teal);
    border-right: 2px solid var(--teal);
    padding-right: 4px;
    animation: cursor-blink 0.7s step-end infinite;
    white-space: nowrap;
    overflow: hidden;
  }

  @keyframes cursor-blink {
    50% { border-color: transparent; }
  }

  /* Badge row */
  .badge-row {
    display: flex;
    gap: 10px;
    justify-content: center;
    flex-wrap: wrap;
    margin-bottom: 36px;
  }

  .badge {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 6px 14px;
    border-radius: 100px;
    font-size: 12px;
    font-weight: 600;
    font-family: 'JetBrains Mono', monospace;
    letter-spacing: 0.5px;
    border: 1px solid;
    transition: all 0.3s ease;
    animation: badge-float 3s ease-in-out infinite;
  }

  .badge:nth-child(2) { animation-delay: 0.3s; }
  .badge:nth-child(3) { animation-delay: 0.6s; }
  .badge:nth-child(4) { animation-delay: 0.9s; }

  @keyframes badge-float {
    0%, 100% { transform: translateY(0); }
    50% { transform: translateY(-4px); }
  }

  .badge-teal { color: var(--teal); border-color: var(--teal); background: rgba(56,178,172,0.08); }
  .badge-purple { color: #a78bfa; border-color: #7C3AED; background: rgba(124,58,237,0.08); }
  .badge-pink { color: #f472b6; border-color: #EC4899; background: rgba(236,72,153,0.08); }
  .badge-gold { color: var(--gold); border-color: var(--gold); background: rgba(245,158,11,0.08); }

  .badge:hover {
    transform: translateY(-6px) scale(1.05);
    box-shadow: 0 10px 30px rgba(56,178,172,0.2);
  }

  /* Stat mini bar */
  .hero-stats {
    display: flex;
    gap: 32px;
    justify-content: center;
    margin-top: 8px;
  }

  .stat-item {
    text-align: center;
  }

  .stat-num {
    font-family: 'Syne', sans-serif;
    font-size: 28px;
    font-weight: 800;
    color: var(--teal);
    display: block;
    animation: count-up 2s ease forwards;
  }

  .stat-label {
    font-size: 11px;
    color: var(--muted);
    font-family: 'JetBrains Mono', monospace;
    text-transform: uppercase;
    letter-spacing: 1px;
  }

  /* Scroll cue */
  .scroll-cue {
    margin-top: 50px;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 8px;
    animation: fade-in-up 1s 2s both;
  }

  .scroll-line {
    width: 1px;
    height: 50px;
    background: linear-gradient(to bottom, var(--teal), transparent);
    animation: scroll-pulse 2s ease-in-out infinite;
  }

  @keyframes scroll-pulse {
    0%, 100% { opacity: 0.3; height: 50px; }
    50% { opacity: 1; height: 70px; }
  }

  .scroll-text {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    color: var(--muted);
    letter-spacing: 3px;
    text-transform: uppercase;
  }

  /* ===== SECTION HEADERS ===== */
  .section {
    padding: 80px 0 40px;
  }

  .section-eyebrow {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    letter-spacing: 4px;
    text-transform: uppercase;
    color: var(--teal);
    margin-bottom: 12px;
    opacity: 0;
    animation: fade-in-up 0.6s ease forwards;
  }

  .section-title {
    font-family: 'Syne', sans-serif;
    font-size: clamp(28px, 5vw, 44px);
    font-weight: 800;
    color: var(--white);
    line-height: 1.1;
    margin-bottom: 16px;
    opacity: 0;
    animation: fade-in-up 0.6s 0.1s ease forwards;
  }

  .section-title span {
    background: linear-gradient(90deg, var(--teal), var(--purple));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .section-line {
    width: 60px;
    height: 3px;
    background: linear-gradient(90deg, var(--teal), var(--purple));
    border-radius: 2px;
    margin-bottom: 48px;
  }

  @keyframes fade-in-up {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
  }

  /* ===== ABOUT CARD ===== */
  .about-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 20px;
    padding: 40px;
    position: relative;
    overflow: hidden;
    transition: border-color 0.3s ease;
  }

  .about-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--teal), var(--purple), var(--pink));
  }

  .about-card:hover {
    border-color: rgba(56,178,172,0.4);
    box-shadow: 0 20px 60px rgba(56,178,172,0.08);
  }

  .about-text {
    font-size: 16px;
    line-height: 1.8;
    color: #94A3B8;
  }

  .about-text strong {
    color: var(--teal);
  }

  /* Terminal block */
  .terminal {
    background: #020408;
    border: 1px solid rgba(56,178,172,0.2);
    border-radius: 12px;
    padding: 24px;
    margin-top: 28px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 13px;
    position: relative;
    overflow: hidden;
  }

  .terminal-dots {
    display: flex;
    gap: 6px;
    margin-bottom: 20px;
  }

  .dot {
    width: 12px;
    height: 12px;
    border-radius: 50%;
  }

  .dot-r { background: #FF5F56; }
  .dot-y { background: #FFBD2E; }
  .dot-g { background: #27C93F; }

  .terminal-line {
    margin-bottom: 8px;
    opacity: 0;
    animation: terminal-appear 0.4s ease forwards;
  }

  .terminal-line:nth-child(2) { animation-delay: 0.5s; }
  .terminal-line:nth-child(3) { animation-delay: 1s; }
  .terminal-line:nth-child(4) { animation-delay: 1.5s; }
  .terminal-line:nth-child(5) { animation-delay: 2s; }
  .terminal-line:nth-child(6) { animation-delay: 2.5s; }
  .terminal-line:nth-child(7) { animation-delay: 3s; }

  @keyframes terminal-appear {
    to { opacity: 1; }
  }

  .t-prompt { color: var(--teal); }
  .t-cmd { color: #a78bfa; }
  .t-val { color: #34D399; }
  .t-str { color: #FCD34D; }
  .t-key { color: #60A5FA; }
  .t-comment { color: #475569; }

  /* ===== TECH STACK ===== */
  .stack-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(100px, 1fr));
    gap: 12px;
  }

  .tech-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 18px 12px;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 10px;
    cursor: default;
    transition: all 0.3s cubic-bezier(0.34, 1.56, 0.64, 1);
    position: relative;
    overflow: hidden;
  }

  .tech-card::after {
    content: '';
    position: absolute;
    inset: 0;
    background: radial-gradient(circle at 50% 0%, rgba(56,178,172,0.1), transparent 70%);
    opacity: 0;
    transition: opacity 0.3s;
  }

  .tech-card:hover {
    transform: translateY(-8px) scale(1.04);
    border-color: rgba(56,178,172,0.5);
    box-shadow: 0 16px 40px rgba(0,0,0,0.4), 0 0 0 1px rgba(56,178,172,0.2);
  }

  .tech-card:hover::after { opacity: 1; }

  .tech-icon {
    font-size: 28px;
    line-height: 1;
    filter: grayscale(0.3);
    transition: filter 0.3s, transform 0.3s;
  }

  .tech-card:hover .tech-icon {
    filter: grayscale(0);
    transform: scale(1.15) rotate(-5deg);
  }

  .tech-name {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    color: var(--muted);
    text-align: center;
    font-weight: 600;
    letter-spacing: 0.5px;
    transition: color 0.3s;
  }

  .tech-card:hover .tech-name { color: var(--teal); }

  /* Category label */
  .cat-label {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    color: var(--purple);
    letter-spacing: 3px;
    text-transform: uppercase;
    margin: 32px 0 16px;
    display: flex;
    align-items: center;
    gap: 12px;
  }

  .cat-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: linear-gradient(to right, rgba(124,58,237,0.3), transparent);
  }

  /* ===== SKILL BARS ===== */
  .skill-list {
    display: flex;
    flex-direction: column;
    gap: 20px;
  }

  .skill-item { }

  .skill-header {
    display: flex;
    justify-content: space-between;
    margin-bottom: 8px;
  }

  .skill-name {
    font-family: 'JetBrains Mono', monospace;
    font-size: 13px;
    color: var(--text);
    font-weight: 600;
  }

  .skill-pct {
    font-family: 'JetBrains Mono', monospace;
    font-size: 12px;
    color: var(--teal);
  }

  .skill-bar-bg {
    height: 6px;
    background: rgba(255,255,255,0.05);
    border-radius: 3px;
    overflow: hidden;
  }

  .skill-bar-fill {
    height: 100%;
    border-radius: 3px;
    background: linear-gradient(90deg, var(--teal), var(--purple));
    transform-origin: left;
    animation: bar-grow 1.5s cubic-bezier(0.22, 1, 0.36, 1) forwards;
    transform: scaleX(0);
  }

  @keyframes bar-grow {
    to { transform: scaleX(1); }
  }

  /* ===== PROJECTS ===== */
  .projects-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
    gap: 20px;
  }

  .project-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 28px 24px;
    position: relative;
    overflow: hidden;
    transition: all 0.4s cubic-bezier(0.34, 1.56, 0.64, 1);
    cursor: pointer;
  }

  .project-card::before {
    content: '';
    position: absolute;
    top: -100%;
    left: -100%;
    width: 300%;
    height: 300%;
    background: conic-gradient(from 180deg at 50% 50%, transparent 0deg, var(--teal-glow) 60deg, transparent 120deg);
    animation: card-shine 6s linear infinite;
    opacity: 0;
    transition: opacity 0.4s;
  }

  @keyframes card-shine {
    to { transform: rotate(360deg); }
  }

  .project-card:hover::before { opacity: 0.08; }

  .project-card:hover {
    transform: translateY(-10px);
    border-color: rgba(56,178,172,0.4);
    box-shadow: 0 24px 60px rgba(0,0,0,0.5), 0 0 40px rgba(56,178,172,0.05);
  }

  .project-icon {
    font-size: 36px;
    margin-bottom: 16px;
    display: block;
    animation: float 3s ease-in-out infinite;
  }

  .project-card:nth-child(2) .project-icon { animation-delay: 0.5s; }
  .project-card:nth-child(3) .project-icon { animation-delay: 1s; }
  .project-card:nth-child(4) .project-icon { animation-delay: 1.5s; }

  @keyframes float {
    0%, 100% { transform: translateY(0); }
    50% { transform: translateY(-6px); }
  }

  .project-title {
    font-family: 'Syne', sans-serif;
    font-size: 18px;
    font-weight: 700;
    color: var(--white);
    margin-bottom: 8px;
  }

  .project-desc {
    font-size: 13px;
    color: var(--muted);
    line-height: 1.6;
    margin-bottom: 20px;
  }

  .project-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
  }

  .tag {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    padding: 3px 10px;
    border-radius: 4px;
    border: 1px solid rgba(56,178,172,0.2);
    color: var(--teal);
    background: rgba(56,178,172,0.05);
    letter-spacing: 0.5px;
  }

  .project-arrow {
    position: absolute;
    top: 20px;
    right: 20px;
    width: 32px;
    height: 32px;
    border: 1px solid var(--border);
    border-radius: 8px;
    display: flex;
    align-items: center;
    justify-content: center;
    color: var(--muted);
    font-size: 14px;
    transition: all 0.3s ease;
  }

  .project-card:hover .project-arrow {
    border-color: var(--teal);
    color: var(--teal);
    transform: translate(2px, -2px);
    background: rgba(56,178,172,0.1);
  }

  /* ===== GITHUB STATS SECTION ===== */
  .stats-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
    margin-bottom: 16px;
  }

  @media (max-width: 600px) {
    .stats-grid { grid-template-columns: 1fr; }
  }

  .stat-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 28px 24px;
    position: relative;
    overflow: hidden;
    transition: all 0.3s ease;
  }

  .stat-card:hover {
    border-color: rgba(56,178,172,0.3);
    box-shadow: 0 10px 40px rgba(56,178,172,0.06);
  }

  .stat-card-title {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    color: var(--muted);
    text-transform: uppercase;
    letter-spacing: 2px;
    margin-bottom: 20px;
  }

  .stat-row {
    display: flex;
    align-items: center;
    gap: 12px;
    margin-bottom: 14px;
  }

  .stat-icon { font-size: 18px; width: 28px; text-align: center; }

  .stat-detail {
    flex: 1;
  }

  .stat-detail-name {
    font-size: 12px;
    color: var(--text);
    margin-bottom: 2px;
  }

  .stat-detail-val {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    color: var(--teal);
  }

  /* Activity calendar */
  .contrib-section {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 28px 24px;
  }

  .contrib-title {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    color: var(--muted);
    text-transform: uppercase;
    letter-spacing: 2px;
    margin-bottom: 20px;
  }

  .contrib-grid {
    display: flex;
    gap: 3px;
    flex-wrap: wrap;
  }

  .contrib-week {
    display: flex;
    flex-direction: column;
    gap: 3px;
  }

  .contrib-day {
    width: 10px;
    height: 10px;
    border-radius: 2px;
    transition: transform 0.2s ease;
  }

  .contrib-day:hover { transform: scale(1.5); }

  .c0 { background: #0d1428; border: 1px solid rgba(255,255,255,0.05); }
  .c1 { background: rgba(56,178,172,0.2); }
  .c2 { background: rgba(56,178,172,0.4); }
  .c3 { background: rgba(56,178,172,0.65); }
  .c4 { background: var(--teal); box-shadow: 0 0 6px rgba(56,178,172,0.4); }

  /* ===== CONNECT SECTION ===== */
  .connect-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    gap: 14px;
  }

  .connect-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 14px;
    padding: 20px 22px;
    display: flex;
    align-items: center;
    gap: 14px;
    cursor: pointer;
    transition: all 0.3s cubic-bezier(0.34, 1.56, 0.64, 1);
    text-decoration: none;
  }

  .connect-card:hover {
    transform: translateY(-6px) scale(1.02);
    border-color: var(--teal);
    box-shadow: 0 12px 36px rgba(56,178,172,0.12);
  }

  .connect-icon-wrap {
    width: 40px;
    height: 40px;
    border-radius: 10px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 20px;
    flex-shrink: 0;
  }

  .connect-text { }

  .connect-platform {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    color: var(--muted);
    text-transform: uppercase;
    letter-spacing: 1px;
    margin-bottom: 2px;
  }

  .connect-handle {
    font-size: 13px;
    font-weight: 600;
    color: var(--text);
  }

  /* ===== FOOTER ===== */
  .footer {
    text-align: center;
    padding: 60px 0 20px;
    border-top: 1px solid var(--border);
    margin-top: 80px;
  }

  .footer-logo {
    font-family: 'Syne', sans-serif;
    font-size: 32px;
    font-weight: 800;
    background: linear-gradient(135deg, var(--teal), var(--purple));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    margin-bottom: 12px;
  }

  .footer-tagline {
    font-family: 'JetBrains Mono', monospace;
    font-size: 12px;
    color: var(--muted);
    letter-spacing: 2px;
    text-transform: uppercase;
    margin-bottom: 24px;
  }

  .footer-wave {
    font-size: 11px;
    color: var(--muted);
    font-family: 'JetBrains Mono', monospace;
  }

  .footer-wave span { color: var(--teal); }

  /* Glowing orbs */
  .orb {
    position: fixed;
    border-radius: 50%;
    filter: blur(80px);
    pointer-events: none;
    z-index: 0;
    animation: orb-drift 12s ease-in-out infinite;
  }

  .orb-1 {
    width: 400px;
    height: 400px;
    background: rgba(56,178,172,0.06);
    top: 10%;
    right: -10%;
    animation-delay: 0s;
  }

  .orb-2 {
    width: 300px;
    height: 300px;
    background: rgba(124,58,237,0.06);
    bottom: 20%;
    left: -5%;
    animation-delay: 4s;
  }

  .orb-3 {
    width: 250px;
    height: 250px;
    background: rgba(236,72,153,0.04);
    top: 50%;
    left: 40%;
    animation-delay: 8s;
  }

  @keyframes orb-drift {
    0%, 100% { transform: translate(0, 0); }
    33% { transform: translate(30px, -20px); }
    66% { transform: translate(-20px, 30px); }
  }

  /* Divider */
  .divider {
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--border), transparent);
    margin: 10px 0;
  }

  /* Glitch name effect */
  @keyframes glitch {
    0%, 100% { clip-path: none; transform: none; }
    5% { clip-path: inset(20% 0 50% 0); transform: translate(-2px, 0); }
    10% { clip-path: inset(60% 0 10% 0); transform: translate(2px, 0); }
    15% { clip-path: none; transform: none; }
  }

  /* "NOW AVAILABLE" pill */
  .available-pill {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    background: rgba(52, 211, 153, 0.08);
    border: 1px solid rgba(52, 211, 153, 0.25);
    border-radius: 100px;
    padding: 6px 16px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    color: #34D399;
    letter-spacing: 1px;
    margin-bottom: 24px;
    text-transform: uppercase;
  }

  .pulse-dot {
    width: 8px;
    height: 8px;
    border-radius: 50%;
    background: #34D399;
    animation: pulse-green 2s ease-in-out infinite;
  }

  @keyframes pulse-green {
    0%, 100% { box-shadow: 0 0 0 0 rgba(52,211,153,0.7); }
    50% { box-shadow: 0 0 0 8px rgba(52,211,153,0); }
  }

  .lang-bar-container {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 28px 24px;
    margin-top: 16px;
  }

  .lang-bar {
    height: 12px;
    border-radius: 6px;
    overflow: hidden;
    display: flex;
    gap: 2px;
    margin-bottom: 20px;
  }

  .lang-seg {
    height: 100%;
    border-radius: 3px;
    transition: flex 0.8s ease;
  }

  .lang-legend {
    display: flex;
    flex-wrap: wrap;
    gap: 16px;
  }

  .lang-item {
    display: flex;
    align-items: center;
    gap: 8px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 12px;
    color: var(--muted);
  }

  .lang-dot {
    width: 10px;
    height: 10px;
    border-radius: 50%;
  }

  .lang-pct { color: var(--text); font-weight: 600; }

  /* ===== LIVE CLOCK ===== */
  .live-clock-wrap {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 20px;
    margin-bottom: 28px;
    flex-wrap: wrap;
  }

  .clock-block {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 14px;
    padding: 12px 20px;
    display: flex;
    align-items: center;
    gap: 10px;
    position: relative;
    overflow: hidden;
  }

  .clock-block::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--teal), transparent);
  }

  .clock-icon { font-size: 16px; }

  .clock-value {
    font-family: 'JetBrains Mono', monospace;
    font-size: 18px;
    font-weight: 700;
    color: var(--teal);
    letter-spacing: 2px;
    min-width: 80px;
    text-align: center;
  }

  .clock-label {
    font-family: 'JetBrains Mono', monospace;
    font-size: 9px;
    color: var(--muted);
    text-transform: uppercase;
    letter-spacing: 1.5px;
    margin-top: 2px;
  }

  .clock-col { display: flex; flex-direction: column; align-items: center; }

  .date-value {
    font-family: 'JetBrains Mono', monospace;
    font-size: 12px;
    font-weight: 600;
    color: #a78bfa;
    letter-spacing: 1px;
    white-space: nowrap;
  }

  /* Location badge */
  .location-badge {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    background: rgba(124,58,237,0.08);
    border: 1px solid rgba(124,58,237,0.2);
    border-radius: 100px;
    padding: 5px 14px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    color: #a78bfa;
    letter-spacing: 0.5px;
    margin-bottom: 14px;
  }

  /* Full name subtitle */
  .hero-fullname {
    font-family: 'Space Grotesk', sans-serif;
    font-size: 14px;
    color: var(--muted);
    letter-spacing: 3px;
    text-transform: uppercase;
    margin-bottom: 6px;
    font-weight: 500;
  }

  /* Quote section */
  .quote-block {
    background: linear-gradient(135deg, rgba(56,178,172,0.05), rgba(124,58,237,0.05));
    border-left: 3px solid var(--teal);
    border-radius: 0 12px 12px 0;
    padding: 20px 24px;
    margin-top: 24px;
    font-family: 'Space Grotesk', sans-serif;
    font-size: 15px;
    font-style: italic;
    color: #94A3B8;
    line-height: 1.7;
  }

  .quote-block cite {
    display: block;
    margin-top: 10px;
    font-style: normal;
    font-size: 12px;
    font-family: 'JetBrains Mono', monospace;
    color: var(--teal);
    letter-spacing: 1px;
  }

  /* Fun facts row */
  .fun-facts {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(180px, 1fr));
    gap: 12px;
    margin-top: 28px;
  }

  .fun-fact {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 16px;
    display: flex;
    align-items: flex-start;
    gap: 12px;
    transition: all 0.3s ease;
  }

  .fun-fact:hover {
    border-color: rgba(56,178,172,0.3);
    transform: translateY(-3px);
  }

  .fun-fact-icon { font-size: 22px; flex-shrink: 0; }

  .fun-fact-text {
    font-size: 12px;
    color: var(--muted);
    line-height: 1.5;
  }

  .fun-fact-text strong { color: var(--text); display: block; margin-bottom: 2px; font-size: 13px; }

  /* Currently learning */
  .learning-row {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    margin-top: 16px;
  }

  .learning-tag {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    padding: 4px 12px;
    border-radius: 6px;
    background: rgba(245,158,11,0.08);
    border: 1px solid rgba(245,158,11,0.2);
    color: var(--gold);
    letter-spacing: 0.5px;
    display: inline-flex;
    align-items: center;
    gap: 5px;
  }

</style>
</head>
<body>

<!-- Background elements -->
<canvas id="stars-canvas"></canvas>
<div class="grid-overlay"></div>
<div class="orb orb-1"></div>
<div class="orb orb-2"></div>
<div class="orb orb-3"></div>

<div class="container">

  <!-- ===== HERO ===== -->
  <section class="hero">
    <div class="available-pill">
      <div class="pulse-dot"></div>
      Available for Collaboration
    </div>

    <div class="avatar-ring">
      <div class="avatar-bg"></div>
      <div class="avatar-inner">
        <span class="avatar-letter">R</span>
      </div>
    </div>

    <p class="hero-fullname">Moklasur Rahman</p>
    <h1 class="hero-name">Rahat</h1>
    <p style="color:var(--muted); font-family:'JetBrains Mono',monospace; font-size:13px; letter-spacing:2px; text-transform:uppercase; margin-bottom:12px;">// codexvisual</p>

    <div class="location-badge">📍 Bangladesh &nbsp;·&nbsp; 🕐 <span id="tz-label">Asia/Dhaka</span></div>

    <!-- LIVE CLOCK -->
    <div class="live-clock-wrap">
      <div class="clock-block">
        <span class="clock-icon">🕐</span>
        <div class="clock-col">
          <div class="clock-value" id="live-time">00:00:00</div>
          <div class="clock-label">Local Time (BD)</div>
        </div>
      </div>
      <div class="clock-block">
        <span class="clock-icon">📅</span>
        <div class="clock-col">
          <div class="date-value" id="live-date">—</div>
          <div class="clock-label">Today's Date</div>
        </div>
      </div>
      <div class="clock-block">
        <span class="clock-icon">📆</span>
        <div class="clock-col">
          <div class="date-value" id="live-day">—</div>
          <div class="clock-label">Day of Week</div>
        </div>
      </div>
    </div>

    <div class="typewriter-container">
      <span class="typewriter-prefix">$&nbsp;</span>
      <span class="typewriter-text" id="typewriter"></span>
    </div>

    <div class="badge-row">
      <span class="badge badge-teal">⚡ Full-Stack Dev</span>
      <span class="badge badge-purple">🔮 Laravel Expert</span>
      <span class="badge badge-pink">🌸 Django Wizard</span>
      <span class="badge badge-gold">✨ Tech Educator</span>
    </div>

    <div class="hero-stats">
      <div class="stat-item">
        <span class="stat-num" data-target="4">0</span>
        <span class="stat-label">Projects</span>
      </div>
      <div class="stat-item">
        <span class="stat-num" data-target="3" data-suffix="+">0</span>
        <span class="stat-label">Years Exp</span>
      </div>
      <div class="stat-item">
        <span class="stat-num" data-target="10" data-suffix="+">0</span>
        <span class="stat-label">Techs</span>
      </div>
      <div class="stat-item">
        <span class="stat-num" data-target="100" data-suffix="%">0</span>
        <span class="stat-label">Passion</span>
      </div>
    </div>

    <div class="scroll-cue">
      <div class="scroll-line"></div>
      <span class="scroll-text">scroll</span>
    </div>
  </section>

  <!-- ===== ABOUT ===== -->
  <section class="section">
    <div class="section-eyebrow">01 — About</div>
    <h2 class="section-title">Who <span>Am I?</span></h2>
    <div class="section-line"></div>

    <div class="about-card">
      <p class="about-text">
        I'm <strong>Moklasur Rahman Rahat</strong> — a passionate <strong>Full-Stack Developer</strong> and <strong>Tech Educator</strong> from Bangladesh who treats code like an art form.
        From designing robust backend architectures to crafting pixel-perfect frontend experiences,
        I live by one principle: <strong>clean code, best practices, zero compromises.</strong>
        My mission is to keep learning, keep building, and share knowledge with the developer community.
      </p>

      <div class="quote-block">
        "First, solve the problem. Then, write the code."
        <cite>— John Johnson &nbsp;·&nbsp; Rahat's Dev Philosophy</cite>
      </div>

      <div class="terminal">
        <div class="terminal-dots">
          <div class="dot dot-r"></div>
          <div class="dot dot-y"></div>
          <div class="dot dot-g"></div>
        </div>
        <div class="terminal-line"><span class="t-comment">// moklasur-rahman-rahat.config.js</span></div>
        <div class="terminal-line"><span class="t-key">const</span> <span class="t-val">developer</span> = {</div>
        <div class="terminal-line">&nbsp;&nbsp;<span class="t-key">fullName</span>: <span class="t-str">"Moklasur Rahman Rahat"</span>,</div>
        <div class="terminal-line">&nbsp;&nbsp;<span class="t-key">alias</span>: <span class="t-str">"codexvisual"</span>,</div>
        <div class="terminal-line">&nbsp;&nbsp;<span class="t-key">role</span>: <span class="t-str">"Full-Stack Developer &amp; Tech Educator"</span>,</div>
        <div class="terminal-line">&nbsp;&nbsp;<span class="t-key">stack</span>: [<span class="t-str">"Laravel"</span>, <span class="t-str">"Django"</span>, <span class="t-str">"React"</span>, <span class="t-str">"Next.js"</span>],</div>
        <div class="terminal-line">&nbsp;&nbsp;<span class="t-key">location</span>: <span class="t-str">"Bangladesh 🇧🇩"</span>,</div>
        <div class="terminal-line">&nbsp;&nbsp;<span class="t-key">openToWork</span>: <span class="t-val">true</span>,</div>
        <div class="terminal-line">};</div>
      </div>

      <div class="fun-facts">
        <div class="fun-fact">
          <span class="fun-fact-icon">☕</span>
          <div class="fun-fact-text"><strong>Fuel</strong>Coffee-powered developer. Runs on chai and commits.</div>
        </div>
        <div class="fun-fact">
          <span class="fun-fact-icon">🌙</span>
          <div class="fun-fact-text"><strong>Night Owl</strong>Best code written after midnight.</div>
        </div>
        <div class="fun-fact">
          <span class="fun-fact-icon">📚</span>
          <div class="fun-fact-text"><strong>Educator</strong>Loves teaching and mentoring junior devs.</div>
        </div>
        <div class="fun-fact">
          <span class="fun-fact-icon">🎯</span>
          <div class="fun-fact-text"><strong>Goal</strong>Build products that actually matter.</div>
        </div>
      </div>

      <div style="margin-top:24px;">
        <div style="font-family:'JetBrains Mono',monospace; font-size:11px; color:var(--gold); text-transform:uppercase; letter-spacing:2px; margin-bottom:10px;">⚡ Currently Learning</div>
        <div class="learning-row">
          <span class="learning-tag">🔥 AI Integration</span>
          <span class="learning-tag">⚡ Vue 3</span>
          <span class="learning-tag">☁️ AWS Cloud</span>
          <span class="learning-tag">🦀 Rust basics</span>
        </div>
      </div>
    </div>
  </section>

  <!-- ===== TECH STACK ===== -->
  <section class="section">
    <div class="section-eyebrow">02 — Arsenal</div>
    <h2 class="section-title">Tech <span>Stack</span></h2>
    <div class="section-line"></div>

    <div class="cat-label">Frontend</div>
    <div class="stack-grid">
      <div class="tech-card"><span class="tech-icon">⚛️</span><span class="tech-name">React</span></div>
      <div class="tech-card"><span class="tech-icon">🔺</span><span class="tech-name">Next.js</span></div>
      <div class="tech-card"><span class="tech-icon">🎨</span><span class="tech-name">Tailwind</span></div>
      <div class="tech-card"><span class="tech-icon">🅱️</span><span class="tech-name">Bootstrap</span></div>
      <div class="tech-card"><span class="tech-icon">🟨</span><span class="tech-name">JavaScript</span></div>
      <div class="tech-card"><span class="tech-icon">🔷</span><span class="tech-name">TypeScript</span></div>
    </div>

    <div class="cat-label">Backend</div>
    <div class="stack-grid">
      <div class="tech-card"><span class="tech-icon">🔴</span><span class="tech-name">Laravel</span></div>
      <div class="tech-card"><span class="tech-icon">🐘</span><span class="tech-name">PHP</span></div>
      <div class="tech-card"><span class="tech-icon">🐍</span><span class="tech-name">Python</span></div>
      <div class="tech-card"><span class="tech-icon">🟢</span><span class="tech-name">Django</span></div>
      <div class="tech-card"><span class="tech-icon">🐬</span><span class="tech-name">MySQL</span></div>
    </div>

    <div class="cat-label">DevOps & Tools</div>
    <div class="stack-grid">
      <div class="tech-card"><span class="tech-icon">🐙</span><span class="tech-name">Git</span></div>
      <div class="tech-card"><span class="tech-icon">🐳</span><span class="tech-name">Docker</span></div>
      <div class="tech-card"><span class="tech-icon">🐧</span><span class="tech-name">Linux</span></div>
      <div class="tech-card"><span class="tech-icon">💙</span><span class="tech-name">VS Code</span></div>
    </div>

    <!-- Skill bars -->
    <div style="margin-top: 40px;">
      <div class="skill-list">
        <div class="skill-item">
          <div class="skill-header">
            <span class="skill-name">Laravel / PHP</span>
            <span class="skill-pct">95%</span>
          </div>
          <div class="skill-bar-bg"><div class="skill-bar-fill" style="width:95%; animation-delay:0.2s;"></div></div>
        </div>
        <div class="skill-item">
          <div class="skill-header">
            <span class="skill-name">Django / Python</span>
            <span class="skill-pct">88%</span>
          </div>
          <div class="skill-bar-bg"><div class="skill-bar-fill" style="width:88%; animation-delay:0.4s;"></div></div>
        </div>
        <div class="skill-item">
          <div class="skill-header">
            <span class="skill-name">React / Next.js</span>
            <span class="skill-pct">82%</span>
          </div>
          <div class="skill-bar-bg"><div class="skill-bar-fill" style="width:82%; animation-delay:0.6s;"></div></div>
        </div>
        <div class="skill-item">
          <div class="skill-header">
            <span class="skill-name">Tailwind CSS / UI</span>
            <span class="skill-pct">92%</span>
          </div>
          <div class="skill-bar-bg"><div class="skill-bar-fill" style="width:92%; animation-delay:0.8s;"></div></div>
        </div>
        <div class="skill-item">
          <div class="skill-header">
            <span class="skill-name">Docker / DevOps</span>
            <span class="skill-pct">75%</span>
          </div>
          <div class="skill-bar-bg"><div class="skill-bar-fill" style="width:75%; animation-delay:1s;"></div></div>
        </div>
      </div>
    </div>
  </section>

  <!-- ===== PROJECTS ===== -->
  <section class="section">
    <div class="section-eyebrow">03 — Work</div>
    <h2 class="section-title">Featured <span>Projects</span></h2>
    <div class="section-line"></div>

    <div class="projects-grid">
      <div class="project-card">
        <div class="project-arrow">↗</div>
        <span class="project-icon">🌐</span>
        <div class="project-title">Blog Platform</div>
        <div class="project-desc">Full-featured blogging system with modern UI/UX and a secure backend. Includes real-time notifications and SEO optimization.</div>
        <div class="project-tags">
          <span class="tag">Laravel</span>
          <span class="tag">MySQL</span>
          <span class="tag">Tailwind</span>
        </div>
      </div>

      <div class="project-card">
        <div class="project-arrow">↗</div>
        <span class="project-icon">📊</span>
        <div class="project-title">Admin Panel</div>
        <div class="project-desc">Responsive and lightweight dashboard template built with a performance-first design philosophy. Fast, clean, and scalable.</div>
        <div class="project-tags">
          <span class="tag">HTML</span>
          <span class="tag">CSS</span>
          <span class="tag">JS</span>
        </div>
      </div>

      <div class="project-card">
        <div class="project-arrow">↗</div>
        <span class="project-icon">💼</span>
        <div class="project-title">Job Portal</div>
        <div class="project-desc">Dynamic job listing and application management system. Features advanced filters, smart search, and real-time notifications.</div>
        <div class="project-tags">
          <span class="tag">Django</span>
          <span class="tag">Python</span>
          <span class="tag">React</span>
        </div>
      </div>

      <div class="project-card">
        <div class="project-arrow">↗</div>
        <span class="project-icon">🌱</span>
        <div class="project-title">AgriSmart</div>
        <div class="project-desc">Smart web platform for managing agricultural data and operations. Features IoT data visualization and real-time crop monitoring dashboards.</div>
        <div class="project-tags">
          <span class="tag">Laravel</span>
          <span class="tag">IoT</span>
          <span class="tag">Charts</span>
        </div>
      </div>
    </div>
  </section>

  <!-- ===== GITHUB ANALYTICS ===== -->
  <section class="section">
    <div class="section-eyebrow">04 — Analytics</div>
    <h2 class="section-title">GitHub <span>Activity</span></h2>
    <div class="section-line"></div>

    <div class="stats-grid">
      <div class="stat-card">
        <div class="stat-card-title">// Stats Overview</div>
        <div class="stat-row">
          <span class="stat-icon">⭐</span>
          <div class="stat-detail">
            <div class="stat-detail-name">Total Stars</div>
            <div class="stat-detail-val">Growing...</div>
          </div>
        </div>
        <div class="stat-row">
          <span class="stat-icon">🔀</span>
          <div class="stat-detail">
            <div class="stat-detail-name">Total Commits</div>
            <div class="stat-detail-val">Active daily</div>
          </div>
        </div>
        <div class="stat-row">
          <span class="stat-icon">🐛</span>
          <div class="stat-detail">
            <div class="stat-detail-name">PRs & Issues</div>
            <div class="stat-detail-val">Open Source contributor</div>
          </div>
        </div>
      </div>

      <div class="stat-card">
        <div class="stat-card-title">// Top Languages</div>
        <div class="lang-bar">
          <div class="lang-seg" style="flex:40; background:#FF2D20;"></div>
          <div class="lang-seg" style="flex:25; background:#3776AB;"></div>
          <div class="lang-seg" style="flex:18; background:#F7DF1E;"></div>
          <div class="lang-seg" style="flex:10; background:#38B2AC;"></div>
          <div class="lang-seg" style="flex:7; background:#7C3AED;"></div>
        </div>
        <div class="lang-legend">
          <div class="lang-item"><div class="lang-dot" style="background:#FF2D20;"></div>PHP <span class="lang-pct" style="margin-left:4px;">40%</span></div>
          <div class="lang-item"><div class="lang-dot" style="background:#3776AB;"></div>Python <span class="lang-pct" style="margin-left:4px;">25%</span></div>
          <div class="lang-item"><div class="lang-dot" style="background:#F7DF1E;"></div>JS <span class="lang-pct" style="margin-left:4px;">18%</span></div>
          <div class="lang-item"><div class="lang-dot" style="background:#38B2AC;"></div>CSS <span class="lang-pct" style="margin-left:4px;">10%</span></div>
          <div class="lang-item"><div class="lang-dot" style="background:#7C3AED;"></div>Other <span class="lang-pct" style="margin-left:4px;">7%</span></div>
        </div>
      </div>
    </div>

    <!-- Contribution Calendar -->
    <div class="contrib-section">
      <div class="contrib-title">// Contribution Graph — 2026</div>
      <div class="contrib-grid" id="contrib-grid"></div>
    </div>
  </section>

  <!-- ===== CONNECT ===== -->
  <section class="section">
    <div class="section-eyebrow">05 — Connect</div>
    <h2 class="section-title">Let's <span>Build Together</span></h2>
    <div class="section-line"></div>

    <div class="connect-grid">
      <a class="connect-card" href="mailto:rahat830611@gmail.com">
        <div class="connect-icon-wrap" style="background:rgba(219,68,55,0.1);">📧</div>
        <div class="connect-text">
          <div class="connect-platform">Email</div>
          <div class="connect-handle">rahat830611@gmail.com</div>
        </div>
      </a>
      <a class="connect-card" href="https://linkedin.com/in/rahat830611">
        <div class="connect-icon-wrap" style="background:rgba(0,119,181,0.1);">💼</div>
        <div class="connect-text">
          <div class="connect-platform">LinkedIn</div>
          <div class="connect-handle">rahat830611</div>
        </div>
      </a>
      <a class="connect-card" href="https://github.com/codexvisual">
        <div class="connect-icon-wrap" style="background:rgba(255,255,255,0.05);">🐙</div>
        <div class="connect-text">
          <div class="connect-platform">GitHub</div>
          <div class="connect-handle">codexvisual</div>
        </div>
      </a>
    </div>
  </section>

  <!-- ===== FOOTER ===== -->
  <footer class="footer">
    <div class="footer-logo">CodexVisual</div>
    <div style="font-family:'Space Grotesk',sans-serif; font-size:13px; color:var(--muted); margin-bottom:8px; letter-spacing:1px;">Moklasur Rahman Rahat</div>
    <div class="footer-tagline">Building the web, one commit at a time</div>
    <div class="footer-wave">Made with <span>♥</span> by Rahat &nbsp;·&nbsp; <span id="footer-year"></span> &nbsp;·&nbsp; Bangladesh 🇧🇩</div>
  </footer>

</div>

<script>
// ===== LIVE CLOCK (Bangladesh Time UTC+6) =====
function updateClock() {
  const now = new Date();
  // Convert to Bangladesh Standard Time (UTC+6)
  const bdOffset = 6 * 60; // minutes
  const utc = now.getTime() + now.getTimezoneOffset() * 60000;
  const bdTime = new Date(utc + bdOffset * 60000);

  const h = String(bdTime.getHours()).padStart(2, '0');
  const m = String(bdTime.getMinutes()).padStart(2, '0');
  const s = String(bdTime.getSeconds()).padStart(2, '0');
  document.getElementById('live-time').textContent = `${h}:${m}:${s}`;

  const days = ['Sunday','Monday','Tuesday','Wednesday','Thursday','Friday','Saturday'];
  const months = ['Jan','Feb','Mar','Apr','May','Jun','Jul','Aug','Sep','Oct','Nov','Dec'];
  document.getElementById('live-date').textContent =
    `${String(bdTime.getDate()).padStart(2,'0')} ${months[bdTime.getMonth()]} ${bdTime.getFullYear()}`;
  document.getElementById('live-day').textContent = days[bdTime.getDay()];
}
updateClock();
setInterval(updateClock, 1000);

// Footer year
document.getElementById('footer-year').textContent = new Date().getFullYear();


const canvas = document.getElementById('stars-canvas');
const ctx = canvas.getContext('2d');
let stars = [];
let W, H;

function resize() {
  W = canvas.width = window.innerWidth;
  H = canvas.height = window.innerHeight;
}

function initStars(n = 200) {
  stars = Array.from({ length: n }, () => ({
    x: Math.random() * W,
    y: Math.random() * H,
    r: Math.random() * 1.5 + 0.3,
    speed: Math.random() * 0.3 + 0.05,
    opacity: Math.random() * 0.7 + 0.1,
    twinkle: Math.random() * Math.PI * 2
  }));
}

function drawStars(t) {
  ctx.clearRect(0, 0, W, H);
  stars.forEach(s => {
    s.twinkle += 0.01;
    const alpha = s.opacity * (0.7 + 0.3 * Math.sin(s.twinkle));
    ctx.beginPath();
    ctx.arc(s.x, s.y, s.r, 0, Math.PI * 2);
    ctx.fillStyle = `rgba(255,255,255,${alpha})`;
    ctx.fill();
    // Occasional teal star
    if (s.r > 1.3) {
      ctx.beginPath();
      ctx.arc(s.x, s.y, s.r * 0.5, 0, Math.PI * 2);
      ctx.fillStyle = `rgba(56,178,172,${alpha * 0.6})`;
      ctx.fill();
    }
    s.y -= s.speed;
    if (s.y < -2) { s.y = H + 2; s.x = Math.random() * W; }
  });
  requestAnimationFrame(drawStars);
}

resize();
initStars();
window.addEventListener('resize', () => { resize(); initStars(); });
requestAnimationFrame(drawStars);

// ===== TYPEWRITER =====
const lines = [
  'building scalable systems',
  'crafting clean code',
  'teaching the next gen',
  'shipping great products',
  'open source contributor'
];
let li = 0, ci = 0, deleting = false;
const tw = document.getElementById('typewriter');

function typeLoop() {
  const txt = lines[li];
  if (!deleting) {
    tw.textContent = txt.slice(0, ++ci);
    if (ci >= txt.length) { deleting = true; setTimeout(typeLoop, 1800); return; }
    setTimeout(typeLoop, 70);
  } else {
    tw.textContent = txt.slice(0, --ci);
    if (ci === 0) { deleting = false; li = (li + 1) % lines.length; setTimeout(typeLoop, 300); return; }
    setTimeout(typeLoop, 35);
  }
}
typeLoop();

// ===== COUNTER ANIMATION =====
function animateCounter(el) {
  const target = parseInt(el.dataset.target);
  const suffix = el.dataset.suffix || '';
  let current = 0;
  const step = Math.ceil(target / 40);
  const timer = setInterval(() => {
    current = Math.min(current + step, target);
    el.textContent = current + suffix;
    if (current >= target) clearInterval(timer);
  }, 40);
}

const observer = new IntersectionObserver(entries => {
  entries.forEach(e => {
    if (e.isIntersecting) {
      const nums = e.target.querySelectorAll('[data-target]');
      nums.forEach(animateCounter);
      observer.unobserve(e.target);
    }
  });
}, { threshold: 0.3 });

document.querySelectorAll('.hero-stats').forEach(el => observer.observe(el));

// ===== CONTRIBUTION CALENDAR =====
function buildCalendar() {
  const grid = document.getElementById('contrib-grid');
  const weeks = 26;
  const days = 7;
  const levels = [0,0,0,1,1,2,2,3,4];
  for (let w = 0; w < weeks; w++) {
    const week = document.createElement('div');
    week.className = 'contrib-week';
    for (let d = 0; d < days; d++) {
      const cell = document.createElement('div');
      const lvl = levels[Math.floor(Math.random() * levels.length)];
      cell.className = `contrib-day c${lvl}`;
      cell.style.animationDelay = `${(w * 7 + d) * 8}ms`;
      week.appendChild(cell);
    }
    grid.appendChild(week);
  }
}
buildCalendar();

// ===== SCROLL REVEAL =====
const revealObs = new IntersectionObserver(entries => {
  entries.forEach(e => {
    if (e.isIntersecting) {
      e.target.style.opacity = '1';
      e.target.style.transform = 'translateY(0)';
    }
  });
}, { threshold: 0.1 });

document.querySelectorAll('.project-card, .tech-card, .stat-card, .connect-card, .about-card, .contrib-section, .lang-bar-container').forEach(el => {
  el.style.opacity = '0';
  el.style.transform = 'translateY(24px)';
  el.style.transition = 'opacity 0.6s ease, transform 0.6s ease';
  revealObs.observe(el);
});

// ===== MOUSE PARALLAX on hero =====
document.addEventListener('mousemove', e => {
  const cx = window.innerWidth / 2, cy = window.innerHeight / 2;
  const dx = (e.clientX - cx) / cx, dy = (e.clientY - cy) / cy;
  const ring = document.querySelector('.avatar-ring');
  if (ring) ring.style.transform = `translate(${dx * 8}px, ${dy * 8}px)`;
});
</script>
</body>
</html>
