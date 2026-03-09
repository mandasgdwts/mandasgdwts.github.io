<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Manda — Graphic Design, Writing & Tutoring</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;0,900;1,400;1,700&family=Lora:ital,wght@0,400;0,500;1,400&family=DM+Mono:wght@300;400&display=swap" rel="stylesheet"/>
<style>
  :root {
    --cream: #fdf6ec;
    --warm-white: #faf4e8;
    --terracotta: #c2614a;
    --terracotta-light: #e08a74;
    --terracotta-dark: #9e3f2a;
    --sage: #7a9e8e;
    --sage-light: #a8c4b8;
    --ink: #1e1a17;
    --ink-mid: #4a3f38;
    --ink-light: #8a7a72;
    --gold: #c9943a;
    --gold-light: #e8c07a;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  html { scroll-behavior: smooth; }

  body {
    font-family: 'Lora', Georgia, serif;
    background: var(--cream);
    color: var(--ink);
    cursor: none;
    overflow-x: hidden;
  }

  /* Custom cursor */
  .cursor {
    width: 12px; height: 12px;
    background: var(--terracotta);
    border-radius: 50%;
    position: fixed; top: 0; left: 0;
    pointer-events: none; z-index: 9999;
    transform: translate(-50%, -50%);
    transition: transform 0.1s, width 0.2s, height 0.2s, background 0.2s;
    mix-blend-mode: multiply;
  }
  .cursor-ring {
    width: 36px; height: 36px;
    border: 1.5px solid var(--terracotta);
    border-radius: 50%;
    position: fixed; top: 0; left: 0;
    pointer-events: none; z-index: 9998;
    transform: translate(-50%, -50%);
    transition: transform 0.18s ease-out, width 0.2s, height 0.2s, opacity 0.2s;
    opacity: 0.5;
  }
  a:hover ~ .cursor, button:hover ~ .cursor { transform: translate(-50%,-50%) scale(2); }

  /* NAV */
  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    padding: 20px 48px;
    display: flex; justify-content: space-between; align-items: center;
    background: rgba(253,246,236,0.85);
    backdrop-filter: blur(12px);
    border-bottom: 1px solid rgba(194,97,74,0.12);
    transition: all 0.3s;
  }
  .nav-logo {
    font-family: 'Playfair Display', serif;
    font-size: 22px; font-style: italic; font-weight: 700;
    color: var(--terracotta-dark);
    letter-spacing: -0.5px;
    text-decoration: none;
  }
  .nav-logo span { color: var(--gold); }
  .nav-links { display: flex; gap: 36px; list-style: none; }
  .nav-links a {
    font-family: 'DM Mono', monospace;
    font-size: 11px; letter-spacing: 1.5px; text-transform: uppercase;
    color: var(--ink-mid); text-decoration: none;
    transition: color 0.2s;
    position: relative;
  }
  .nav-links a::after {
    content: ''; position: absolute; bottom: -3px; left: 0; right: 0;
    height: 1px; background: var(--terracotta);
    transform: scaleX(0); transition: transform 0.25s;
  }
  .nav-links a:hover { color: var(--terracotta); }
  .nav-links a:hover::after { transform: scaleX(1); }
  .nav-cta {
    background: var(--terracotta); color: white !important;
    padding: 8px 20px; border-radius: 30px;
    font-family: 'DM Mono', monospace;
    font-size: 11px; letter-spacing: 1.5px;
    transition: background 0.2s, transform 0.2s !important;
  }
  .nav-cta::after { display: none !important; }
  .nav-cta:hover { background: var(--terracotta-dark) !important; transform: translateY(-1px); }

  /* HERO */
  .hero {
    min-height: 100vh;
    display: grid; grid-template-columns: 1fr 1fr;
    align-items: center;
    padding: 120px 48px 80px;
    position: relative; overflow: hidden;
  }
  .hero-bg-circle {
    position: absolute;
    border-radius: 50%;
    pointer-events: none;
  }
  .hero-bg-circle-1 {
    width: 600px; height: 600px;
    background: radial-gradient(circle, rgba(194,97,74,0.08) 0%, transparent 70%);
    top: -100px; right: -100px;
    animation: floatA 8s ease-in-out infinite;
  }
  .hero-bg-circle-2 {
    width: 400px; height: 400px;
    background: radial-gradient(circle, rgba(122,158,142,0.1) 0%, transparent 70%);
    bottom: -50px; left: 200px;
    animation: floatB 10s ease-in-out infinite;
  }
  @keyframes floatA { 0%,100%{transform:translate(0,0) scale(1);} 50%{transform:translate(-20px,20px) scale(1.05);} }
  @keyframes floatB { 0%,100%{transform:translate(0,0);} 50%{transform:translate(15px,-15px);} }

  .hero-text { position: relative; z-index: 2; }
  .hero-eyebrow {
    font-family: 'DM Mono', monospace;
    font-size: 11px; letter-spacing: 3px; text-transform: uppercase;
    color: var(--terracotta); margin-bottom: 20px;
    display: flex; align-items: center; gap: 12px;
  }
  .hero-eyebrow::before {
    content: ''; width: 40px; height: 1px; background: var(--terracotta);
  }
  .hero-headline {
    font-family: 'Playfair Display', serif;
    font-size: clamp(52px, 6vw, 86px);
    font-weight: 900; line-height: 1.0;
    letter-spacing: -2px;
    color: var(--ink);
    margin-bottom: 28px;
  }
  .hero-headline em {
    font-style: italic; color: var(--terracotta);
    display: block;
  }
  .hero-sub {
    font-size: 17px; line-height: 1.8;
    color: var(--ink-mid); max-width: 420px;
    margin-bottom: 40px;
  }
  .hero-buttons { display: flex; gap: 16px; flex-wrap: wrap; }
  .btn-primary {
    background: var(--ink);
    color: white;
    padding: 14px 32px;
    border-radius: 40px;
    font-family: 'DM Mono', monospace;
    font-size: 12px; letter-spacing: 1.5px; text-transform: uppercase;
    text-decoration: none;
    transition: background 0.2s, transform 0.2s;
    display: inline-block;
  }
  .btn-primary:hover { background: var(--terracotta); transform: translateY(-2px); }
  .btn-outline {
    background: transparent;
    color: var(--ink);
    padding: 14px 32px;
    border-radius: 40px;
    border: 1.5px solid var(--ink);
    font-family: 'DM Mono', monospace;
    font-size: 12px; letter-spacing: 1.5px; text-transform: uppercase;
    text-decoration: none;
    transition: all 0.2s;
    display: inline-block;
  }
  .btn-outline:hover { border-color: var(--terracotta); color: var(--terracotta); transform: translateY(-2px); }

  .hero-visual {
    position: relative; z-index: 2;
    display: flex; justify-content: center; align-items: center;
  }
  .hero-card-stack { position: relative; width: 340px; height: 420px; }
  .hero-card {
    position: absolute; border-radius: 16px;
    transition: transform 0.4s ease;
  }
  .hero-card-1 {
    width: 260px; height: 320px;
    background: linear-gradient(135deg, var(--sage) 0%, var(--sage-light) 100%);
    top: 60px; left: 60px;
    transform: rotate(6deg);
    display: flex; flex-direction: column; justify-content: flex-end;
    padding: 24px; color: white;
    box-shadow: 0 20px 60px rgba(0,0,0,0.15);
  }
  .hero-card-2 {
    width: 240px; height: 300px;
    background: linear-gradient(135deg, var(--terracotta) 0%, #e8856e 100%);
    top: 30px; left: 30px;
    transform: rotate(-4deg);
    display: flex; flex-direction: column; justify-content: flex-end;
    padding: 24px; color: white;
    box-shadow: 0 20px 60px rgba(0,0,0,0.18);
  }
  .hero-card-3 {
    width: 220px; height: 280px;
    background: var(--cream);
    border: 1.5px solid rgba(194,97,74,0.2);
    top: 0; left: 10px;
    transform: rotate(-1deg);
    display: flex; flex-direction: column; justify-content: center; align-items: center;
    gap: 10px;
    box-shadow: 0 10px 40px rgba(0,0,0,0.08);
  }
  .hero-card-label {
    font-family: 'DM Mono', monospace;
    font-size: 9px; letter-spacing: 2px; text-transform: uppercase;
    opacity: 0.8; margin-bottom: 4px;
  }
  .hero-card-title {
    font-family: 'Playfair Display', serif;
    font-size: 18px; font-weight: 700;
  }
  .hero-card-3-icon { font-size: 36px; }
  .hero-card-3-text {
    font-family: 'Playfair Display', serif;
    font-size: 15px; color: var(--ink-mid);
    text-align: center; font-style: italic;
  }
  .hero-card-stack:hover .hero-card-1 { transform: rotate(9deg) translateY(-8px); }
  .hero-card-stack:hover .hero-card-2 { transform: rotate(-7deg) translateY(-4px); }

  /* SERVICES */
  .services {
    padding: 100px 48px;
    background: var(--ink);
    color: var(--cream);
    position: relative; overflow: hidden;
  }
  .services-bg-text {
    position: absolute;
    font-family: 'Playfair Display', serif;
    font-size: 200px; font-weight: 900; font-style: italic;
    color: rgba(255,255,255,0.02);
    top: 50%; left: 50%;
    transform: translate(-50%, -50%);
    white-space: nowrap;
    pointer-events: none;
    letter-spacing: -8px;
  }
  .section-header { margin-bottom: 64px; }
  .section-tag {
    font-family: 'DM Mono', monospace;
    font-size: 10px; letter-spacing: 3px; text-transform: uppercase;
    color: var(--terracotta-light); margin-bottom: 16px;
    display: flex; align-items: center; gap: 12px;
  }
  .section-tag::before { content: ''; width: 32px; height: 1px; background: var(--terracotta-light); }
  .section-title {
    font-family: 'Playfair Display', serif;
    font-size: clamp(38px, 4vw, 58px);
    font-weight: 700; line-height: 1.1;
    letter-spacing: -1.5px;
  }
  .services-grid {
    display: grid; grid-template-columns: repeat(3, 1fr);
    gap: 2px; position: relative; z-index: 2;
  }
  .service-card {
    background: rgba(255,255,255,0.03);
    border: 1px solid rgba(255,255,255,0.07);
    padding: 48px 36px;
    transition: background 0.3s, transform 0.3s;
    position: relative; overflow: hidden;
  }
  .service-card::before {
    content: '';
    position: absolute; top: 0; left: 0; right: 0; height: 3px;
    background: var(--terracotta);
    transform: scaleX(0); transform-origin: left;
    transition: transform 0.35s ease;
  }
  .service-card:hover { background: rgba(255,255,255,0.06); transform: translateY(-4px); }
  .service-card:hover::before { transform: scaleX(1); }
  .service-number {
    font-family: 'DM Mono', monospace;
    font-size: 11px; color: rgba(255,255,255,0.2);
    letter-spacing: 2px; margin-bottom: 24px;
  }
  .service-icon { font-size: 40px; margin-bottom: 20px; display: block; }
  .service-name {
    font-family: 'Playfair Display', serif;
    font-size: 26px; font-weight: 700;
    margin-bottom: 16px; color: white;
    line-height: 1.2;
  }
  .service-desc {
    font-size: 15px; line-height: 1.8;
    color: rgba(255,255,255,0.55);
    margin-bottom: 28px;
  }
  .service-list {
    list-style: none;
    display: flex; flex-direction: column; gap: 8px;
  }
  .service-list li {
    font-family: 'DM Mono', monospace;
    font-size: 11px; letter-spacing: 0.5px;
    color: rgba(255,255,255,0.4);
    display: flex; align-items: center; gap: 8px;
  }
  .service-list li::before {
    content: '→'; color: var(--terracotta-light);
  }

  /* ABOUT */
  .about {
    padding: 120px 48px;
    display: grid; grid-template-columns: 1fr 1fr;
    gap: 80px; align-items: center;
    background: var(--warm-white);
  }
  .about-image-area { position: relative; }
  .about-frame {
    width: 100%; aspect-ratio: 4/5;
    background: linear-gradient(160deg, var(--sage-light) 0%, var(--sage) 50%, #5a8070 100%);
    border-radius: 8px;
    display: flex; align-items: center; justify-content: center;
    font-size: 80px;
    box-shadow: 0 32px 80px rgba(0,0,0,0.12);
    position: relative; overflow: hidden;
  }
  .about-frame-deco {
    position: absolute; bottom: -30px; right: -30px;
    width: 180px; height: 180px;
    border: 2px solid var(--terracotta);
    border-radius: 8px; z-index: -1;
  }
  .about-frame-tag {
    position: absolute; bottom: 28px; left: 28px;
    background: white; border-radius: 50px;
    padding: 10px 20px;
    font-family: 'DM Mono', monospace;
    font-size: 11px; color: var(--ink);
    display: flex; align-items: center; gap: 8px;
    box-shadow: 0 8px 24px rgba(0,0,0,0.1);
  }
  .about-frame-tag span { color: var(--terracotta); font-size: 14px; }
  .about-text .section-tag { color: var(--terracotta); }
  .about-text .section-tag::before { background: var(--terracotta); }
  .about-headline {
    font-family: 'Playfair Display', serif;
    font-size: clamp(34px, 3.5vw, 50px);
    font-weight: 700; line-height: 1.15;
    letter-spacing: -1px; margin-bottom: 24px;
  }
  .about-headline em { font-style: italic; color: var(--terracotta); }
  .about-body {
    font-size: 16px; line-height: 1.9;
    color: var(--ink-mid); margin-bottom: 16px;
  }
  .about-stats {
    display: grid; grid-template-columns: repeat(3, 1fr);
    gap: 24px; margin-top: 40px;
    padding-top: 40px; border-top: 1px solid rgba(30,26,23,0.1);
  }
  .stat-num {
    font-family: 'Playfair Display', serif;
    font-size: 38px; font-weight: 900;
    color: var(--terracotta); line-height: 1;
    margin-bottom: 6px;
  }
  .stat-label {
    font-family: 'DM Mono', monospace;
    font-size: 10px; letter-spacing: 1.5px; text-transform: uppercase;
    color: var(--ink-light);
  }

  /* PORTFOLIO */
  .portfolio {
    padding: 100px 48px;
    background: var(--cream);
  }
  .portfolio .section-tag { color: var(--terracotta); }
  .portfolio .section-tag::before { background: var(--terracotta); }
  .portfolio-tabs {
    display: flex; gap: 0; margin-bottom: 48px;
    border-bottom: 1px solid rgba(30,26,23,0.12);
  }
  .portfolio-tab {
    font-family: 'DM Mono', monospace;
    font-size: 11px; letter-spacing: 1.5px; text-transform: uppercase;
    color: var(--ink-light); padding: 12px 24px;
    cursor: pointer; border: none; background: none;
    border-bottom: 2px solid transparent;
    transition: all 0.2s; margin-bottom: -1px;
  }
  .portfolio-tab.active { color: var(--terracotta); border-bottom-color: var(--terracotta); }
  .portfolio-tab:hover { color: var(--ink); }
  .portfolio-grid {
    display: grid; grid-template-columns: repeat(3, 1fr);
    gap: 24px;
  }
  .portfolio-item {
    border-radius: 8px; overflow: hidden;
    position: relative; cursor: pointer;
    group: true;
  }
  .portfolio-thumb {
    aspect-ratio: 4/3;
    display: flex; align-items: center; justify-content: center;
    font-size: 52px;
    position: relative; overflow: hidden;
    transition: transform 0.4s ease;
  }
  .portfolio-item:hover .portfolio-thumb { transform: scale(1.03); }
  .portfolio-thumb-overlay {
    position: absolute; inset: 0;
    background: rgba(30,26,23,0.7);
    display: flex; align-items: center; justify-content: center;
    opacity: 0; transition: opacity 0.3s;
    color: white;
    font-family: 'DM Mono', monospace;
    font-size: 12px; letter-spacing: 2px;
  }
  .portfolio-item:hover .portfolio-thumb-overlay { opacity: 1; }
  .portfolio-info { padding: 18px 0 8px; }
  .portfolio-info-title {
    font-family: 'Playfair Display', serif;
    font-size: 18px; font-weight: 600; margin-bottom: 4px;
  }
  .portfolio-info-cat {
    font-family: 'DM Mono', monospace;
    font-size: 10px; letter-spacing: 1.5px; text-transform: uppercase;
    color: var(--ink-light);
  }

  /* TESTIMONIALS */
  .testimonials {
    padding: 100px 48px;
    background: var(--terracotta);
    color: white; overflow: hidden; position: relative;
  }
  .testimonials-bg {
    position: absolute; top: -80px; right: -80px;
    width: 400px; height: 400px;
    border-radius: 50%;
    background: rgba(255,255,255,0.05);
    pointer-events: none;
  }
  .testimonials .section-tag { color: rgba(255,255,255,0.6); }
  .testimonials .section-tag::before { background: rgba(255,255,255,0.6); }
  .testimonials .section-title { color: white; }
  .testimonials-grid {
    display: grid; grid-template-columns: repeat(3, 1fr);
    gap: 24px; position: relative; z-index: 2;
  }
  .testimonial-card {
    background: rgba(255,255,255,0.1);
    border: 1px solid rgba(255,255,255,0.15);
    border-radius: 12px; padding: 32px;
    backdrop-filter: blur(8px);
    transition: transform 0.3s, background 0.3s;
  }
  .testimonial-card:hover { transform: translateY(-4px); background: rgba(255,255,255,0.15); }
  .testimonial-quote {
    font-family: 'Playfair Display', serif;
    font-size: 48px; line-height: 1;
    color: rgba(255,255,255,0.3); margin-bottom: -8px;
  }
  .testimonial-text {
    font-size: 15px; line-height: 1.8;
    color: rgba(255,255,255,0.9); margin-bottom: 24px;
    font-style: italic;
  }
  .testimonial-author {
    display: flex; align-items: center; gap: 12px;
  }
  .testimonial-avatar {
    width: 42px; height: 42px; border-radius: 50%;
    display: flex; align-items: center; justify-content: center;
    font-size: 18px;
    background: rgba(255,255,255,0.2);
    flex-shrink: 0;
  }
  .testimonial-name {
    font-family: 'DM Mono', monospace;
    font-size: 12px; font-weight: 400;
    letter-spacing: 0.5px;
  }
  .testimonial-role {
    font-family: 'DM Mono', monospace;
    font-size: 10px; color: rgba(255,255,255,0.5);
    letter-spacing: 1px; margin-top: 2px;
  }

  /* CONTACT */
  .contact {
    padding: 120px 48px;
    display: grid; grid-template-columns: 1fr 1fr;
    gap: 80px; align-items: start;
    background: var(--warm-white);
  }
  .contact .section-tag { color: var(--terracotta); }
  .contact .section-tag::before { background: var(--terracotta); }
  .contact-headline {
    font-family: 'Playfair Display', serif;
    font-size: clamp(36px, 4vw, 54px);
    font-weight: 700; line-height: 1.1;
    letter-spacing: -1.5px; margin-bottom: 20px;
  }
  .contact-headline em { font-style: italic; color: var(--terracotta); }
  .contact-sub { font-size: 16px; line-height: 1.8; color: var(--ink-mid); margin-bottom: 40px; }
  .contact-methods { display: flex; flex-direction: column; gap: 16px; }
  .contact-method {
    display: flex; align-items: center; gap: 16px;
    padding: 16px 20px;
    background: white; border-radius: 8px;
    border: 1px solid rgba(30,26,23,0.08);
    text-decoration: none; color: var(--ink);
    transition: border-color 0.2s, transform 0.2s;
  }
  .contact-method:hover { border-color: var(--terracotta); transform: translateX(4px); }
  .contact-method-icon {
    width: 44px; height: 44px; border-radius: 8px;
    background: var(--cream); display: flex; align-items: center; justify-content: center;
    font-size: 20px; flex-shrink: 0;
  }
  .contact-method-label {
    font-family: 'DM Mono', monospace;
    font-size: 10px; letter-spacing: 1.5px; text-transform: uppercase;
    color: var(--ink-light); margin-bottom: 2px;
  }
  .contact-method-value { font-size: 15px; font-weight: 500; }

  /* Contact form */
  .contact-form { display: flex; flex-direction: column; gap: 20px; }
  .form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; }
  .form-group { display: flex; flex-direction: column; gap: 8px; }
  .form-label {
    font-family: 'DM Mono', monospace;
    font-size: 10px; letter-spacing: 1.5px; text-transform: uppercase;
    color: var(--ink-mid);
  }
  .form-input {
    background: white; border: 1.5px solid rgba(30,26,23,0.12);
    border-radius: 6px; padding: 14px 16px;
    font-family: 'Lora', serif; font-size: 15px;
    color: var(--ink); transition: border-color 0.2s;
    outline: none;
  }
  .form-input:focus { border-color: var(--terracotta); }
  .form-input::placeholder { color: var(--ink-light); }
  textarea.form-input { resize: vertical; min-height: 130px; }
  .form-service-select {
    display: grid; grid-template-columns: repeat(3, 1fr); gap: 10px;
  }
  .service-chip {
    background: white; border: 1.5px solid rgba(30,26,23,0.12);
    border-radius: 6px; padding: 10px 12px;
    font-family: 'DM Mono', monospace; font-size: 10px;
    letter-spacing: 1px; text-transform: uppercase;
    color: var(--ink-mid); cursor: pointer;
    transition: all 0.2s; text-align: center;
    user-select: none;
  }
  .service-chip.selected, .service-chip:hover {
    background: var(--terracotta); color: white; border-color: var(--terracotta);
  }
  .submit-btn {
    background: var(--ink); color: white;
    border: none; border-radius: 40px;
    padding: 16px 36px;
    font-family: 'DM Mono', monospace;
    font-size: 12px; letter-spacing: 2px; text-transform: uppercase;
    cursor: pointer; transition: background 0.2s, transform 0.2s;
    align-self: flex-start;
  }
  .submit-btn:hover { background: var(--terracotta); transform: translateY(-2px); }

  /* FOOTER */
  footer {
    background: var(--ink); color: var(--cream);
    padding: 60px 48px 36px;
  }
  .footer-inner {
    display: grid; grid-template-columns: 1.5fr 1fr 1fr;
    gap: 48px; padding-bottom: 48px;
    border-bottom: 1px solid rgba(255,255,255,0.08);
    margin-bottom: 32px;
  }
  .footer-brand-name {
    font-family: 'Playfair Display', serif;
    font-size: 28px; font-style: italic; font-weight: 700;
    color: white; margin-bottom: 16px;
  }
  .footer-brand-name span { color: var(--gold-light); }
  .footer-brand-desc {
    font-size: 14px; line-height: 1.8;
    color: rgba(255,255,255,0.45); max-width: 260px;
  }
  .footer-col-title {
    font-family: 'DM Mono', monospace;
    font-size: 10px; letter-spacing: 2px; text-transform: uppercase;
    color: rgba(255,255,255,0.3); margin-bottom: 20px;
  }
  .footer-links { list-style: none; display: flex; flex-direction: column; gap: 12px; }
  .footer-links a {
    color: rgba(255,255,255,0.55); text-decoration: none;
    font-size: 14px; transition: color 0.2s;
  }
  .footer-links a:hover { color: var(--terracotta-light); }
  .footer-bottom {
    display: flex; justify-content: space-between; align-items: center;
  }
  .footer-copy {
    font-family: 'DM Mono', monospace;
    font-size: 10px; color: rgba(255,255,255,0.25);
    letter-spacing: 1px;
  }
  .footer-social { display: flex; gap: 12px; }
  .social-icon {
    width: 36px; height: 36px; border-radius: 50%;
    border: 1px solid rgba(255,255,255,0.12);
    display: flex; align-items: center; justify-content: center;
    font-size: 14px; cursor: pointer; transition: all 0.2s;
    text-decoration: none; color: white;
  }
  .social-icon:hover { border-color: var(--terracotta-light); background: rgba(194,97,74,0.2); }

  /* Animations */
  .fade-up {
    opacity: 0; transform: translateY(30px);
    transition: opacity 0.7s ease, transform 0.7s ease;
  }
  .fade-up.visible { opacity: 1; transform: translateY(0); }
  .fade-up:nth-child(2) { transition-delay: 0.1s; }
  .fade-up:nth-child(3) { transition-delay: 0.2s; }

  /* Responsive */
  @media (max-width: 900px) {
    nav { padding: 16px 24px; }
    .nav-links { display: none; }
    .hero { grid-template-columns: 1fr; padding: 100px 24px 60px; }
    .hero-visual { display: none; }
    .services { padding: 60px 24px; }
    .services-grid { grid-template-columns: 1fr; }
    .about { grid-template-columns: 1fr; padding: 60px 24px; }
    .about-image-area { display: none; }
    .portfolio { padding: 60px 24px; }
    .portfolio-grid { grid-template-columns: 1fr 1fr; }
    .testimonials { padding: 60px 24px; }
    .testimonials-grid { grid-template-columns: 1fr; }
    .contact { grid-template-columns: 1fr; padding: 60px 24px; }
    .form-row { grid-template-columns: 1fr; }
    footer { padding: 48px 24px 28px; }
    .footer-inner { grid-template-columns: 1fr; }
  }
</style>
</head>
<body>

<div class="cursor" id="cursor"></div>
<div class="cursor-ring" id="cursorRing"></div>

<!-- NAV -->
<nav>
  <a href="#" class="nav-logo">Manda<span>.</span></a>
  <ul class="nav-links">
    <li><a href="#services">Services</a></li>
    <li><a href="#about">About</a></li>
    <li><a href="#portfolio">Portfolio</a></li>
    <li><a href="#contact" class="nav-cta">Work With Me</a></li>
  </ul>
</nav>

<!-- HERO -->
<section class="hero" id="home">
  <div class="hero-bg-circle hero-bg-circle-1"></div>
  <div class="hero-bg-circle hero-bg-circle-2"></div>

  <div class="hero-text">
    <div class="hero-eyebrow">Creative & Educator</div>
    <h1 class="hero-headline">
      Words.<br>
      Visuals.<br>
      <em>Knowledge.</em>
    </h1>
    <p class="hero-sub">
      I'm Manda — a graphic designer, writer, and tutor helping individuals and businesses communicate beautifully, think clearly, and grow confidently.
    </p>
    <div class="hero-buttons">
      <a href="#services" class="btn-primary">Explore Services</a>
      <a href="#portfolio" class="btn-outline">View My Work</a>
    </div>
  </div>

  <div class="hero-visual">
    <div class="hero-card-stack">
      <div class="hero-card hero-card-1">
        <div class="hero-card-label">Graphic Design</div>
        <div class="hero-card-title">Brand & Visual Identity</div>
      </div>
      <div class="hero-card hero-card-2">
        <div class="hero-card-label">Writing</div>
        <div class="hero-card-title">Words That Connect</div>
      </div>
      <div class="hero-card hero-card-3">
        <div class="hero-card-3-icon">✏️</div>
        <div class="hero-card-3-text">Tutoring &<br>Mentorship</div>
      </div>
    </div>
  </div>
</section>

<!-- SERVICES -->
<section class="services" id="services">
  <div class="services-bg-text">Manda</div>
  <div class="section-header fade-up">
    <div class="section-tag">What I Do</div>
    <h2 class="section-title" style="color:white;">Three ways I can<br><em style="font-style:italic;color:var(--terracotta-light);">help you thrive</em></h2>
  </div>
  <div class="services-grid">
    <div class="service-card fade-up">
      <div class="service-number">01</div>
      <span class="service-icon">🎨</span>
      <div class="service-name">Graphic Design</div>
      <p class="service-desc">Visual identities and layouts that communicate your essence and leave a lasting impression across every touchpoint.</p>
      <ul class="service-list">
        <li>Logo & Brand Identity</li>
        <li>Social Media Graphics</li>
        <li>Posters & Print Design</li>
        <li>Presentations & Decks</li>
        <li>Marketing Materials</li>
      </ul>
    </div>
    <div class="service-card fade-up">
      <div class="service-number">02</div>
      <span class="service-icon">✍️</span>
      <div class="service-name">Writing</div>
      <p class="service-desc">Clear, compelling, and authentic writing that tells your story, engages your audience, and drives action.</p>
      <ul class="service-list">
        <li>Copywriting & Taglines</li>
        <li>Blog Posts & Articles</li>
        <li>Website Copy</li>
        <li>Editing & Proofreading</li>
        <li>Creative Writing</li>
      </ul>
    </div>
    <div class="service-card fade-up">
      <div class="service-number">03</div>
      <span class="service-icon">📚</span>
      <div class="service-name">Tutoring</div>
      <p class="service-desc">Patient, personalised tutoring that builds skills, boosts confidence, and unlocks your full potential.</p>
      <ul class="service-list">
        <li>English & Essay Writing</li>
        <li>Reading Comprehension</li>
        <li>Academic Support</li>
        <li>Creative Writing Coaching</li>
        <li>Design Fundamentals</li>
      </ul>
    </div>
  </div>
</section>

<!-- ABOUT -->
<section class="about" id="about">
  <div class="about-image-area fade-up">
    <div class="about-frame">
      🌿
      <div class="about-frame-tag">
        <span>★</span> Available for new projects
      </div>
    </div>
    <div class="about-frame-deco"></div>
  </div>
  <div class="about-text fade-up">
    <div class="section-tag">About Manda</div>
    <h2 class="about-headline">A creative who<br><em>loves teaching</em><br>as much as making</h2>
    <p class="about-body">
      Hello! I'm Manda, and I wear a few hats — designer, writer, and educator. My work lives at the intersection of creativity and clarity. Whether I'm crafting a brand identity, writing a compelling piece of copy, or working one-on-one with a student, my goal is always the same: to make something genuinely excellent.
    </p>
    <p class="about-body">
      With years of experience across design studios, content agencies, and classrooms, I bring a rare combination of technical skill, creative vision, and the patience to help others grow. I believe great work comes from genuine collaboration.
    </p>
    <div class="about-stats">
      <div>
        <div class="stat-num">10+</div>
        <div class="stat-label">Years Experience</div>
      </div>
      <div>
        <div class="stat-num">25+</div>
        <div class="stat-label">Happy Clients</div>
      </div>
      <div>
        <div class="stat-num">60+</div>
        <div class="stat-label">Projects Done</div>
      </div>
    </div>
  </div>
</section>



<!-- TESTIMONIALS -->
<section class="testimonials" id="testimonials">
  <div class="testimonials-bg"></div>
  <div class="section-header fade-up">
    <div class="section-tag">Kind Words</div>
    <h2 class="section-title">What clients say</h2>
  </div>
  <div class="testimonials-grid">
    <div class="testimonial-card fade-up">
      <div class="testimonial-quote">"</div>
      <p class="testimonial-text">Manda completely transformed our brand. She has this rare ability to listen deeply and then translate what you mean into something beautiful you didn't even know you needed.</p>
      <div class="testimonial-author">
        <div class="testimonial-avatar">🌺</div>
        <div>
          <div class="testimonial-name">Sarah Chen</div>
          <div class="testimonial-role">Founder, Bloom Bakery</div>
        </div>
      </div>
    </div>
    <div class="testimonial-card fade-up">
      <div class="testimonial-quote">"</div>
      <p class="testimonial-text">As a tutor, Manda is truly exceptional. My son went from dreading English essays to genuinely loving them. Her patience and creativity make all the difference.</p>
      <div class="testimonial-author">
        <div class="testimonial-avatar">📖</div>
        <div>
          <div class="testimonial-name">James Thornton</div>
          <div class="testimonial-role">Parent</div>
        </div>
      </div>
    </div>
    <div class="testimonial-card fade-up">
      <div class="testimonial-quote">"</div>
      <p class="testimonial-text">The copy Manda wrote for our website completely changed how customers perceive us. Thoughtful, sharp, and perfectly on-brand. We've seen a real uptick in enquiries.</p>
      <div class="testimonial-author">
        <div class="testimonial-avatar">☕</div>
        <div>
          <div class="testimonial-name">Lena Vasquez</div>
          <div class="testimonial-role">Director, Artisan Coffee Co.</div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section class="contact" id="contact">
  <div class="fade-up">
    <div class="section-tag">Get In Touch</div>
    <h2 class="contact-headline">Let's make<br>something<br><em>wonderful</em></h2>
    <p class="contact-sub">Whether you have a project in mind or just want to explore the possibilities, I'd love to hear from you. No brief too big or too small.</p>
    <div class="contact-methods">
      <a href="mailto:mandasgdwts@gmail.com" class="contact-method">
        <div class="contact-method-icon">✉️</div>
        <div>
          <div class="contact-method-label">Email</div>
          <div class="contact-method-value">mandasgdwts@gmail.com</div>
        </div>
      </a>
      <a href="tel:+61400000000" class="contact-method">
        <div class="contact-method-icon">📞</div>
        <div>
          <div class="contact-method-label">Phone</div>
          <div class="contact-method-value">973-922-0783</div>
        </div>
      </a>
      <a href="#" class="contact-method">
        <div class="contact-method-icon">📍</div>
        <div>
          <div class="contact-method-label">Location</div>
          <div class="contact-method-value">Available Worldwide · Remote & In-Person</div>
        </div>
      </a>
    </div>
  </div>

  <div class="fade-up">
    <form class="contact-form" onsubmit="handleSubmit(event)">
      <div class="form-row">
        <div class="form-group">
          <label class="form-label">First Name</label>
          <input class="form-input" type="text" placeholder="Your first name" required />
        </div>
        <div class="form-group">
          <label class="form-label">Last Name</label>
          <input class="form-input" type="text" placeholder="Your last name" />
        </div>
      </div>
      <div class="form-group">
        <label class="form-label">Email Address</label>
        <input class="form-input" type="email" placeholder="mandasgdwts@gmail.com" required />
      </div>
      <div class="form-group">
        <label class="form-label">I'm interested in</label>
        <div class="form-service-select">
          <div class="service-chip" onclick="toggleChip(this)">Design</div>
          <div class="service-chip" onclick="toggleChip(this)">Writing</div>
          <div class="service-chip" onclick="toggleChip(this)">Tutoring</div>
        </div>
      </div>
      <div class="form-group">
        <label class="form-label">Tell me about your project</label>
        <textarea class="form-input" placeholder="What are you working on? What do you need help with?" required></textarea>
      </div>
      <button type="submit" class="submit-btn">Send Message →</button>
    </form>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-inner">
    <div>
      <div class="footer-brand-name">Manda<span>.</span></div>
      <p class="footer-brand-desc">Graphic design, writing, and tutoring services for individuals and businesses who care about quality and creativity.</p>
    </div>
    <div>
      <div class="footer-col-title">Services</div>
      <ul class="footer-links">
        <li><a href="#services">Graphic Design</a></li>
        <li><a href="#services">Writing & Copy</a></li>
        <li><a href="#services">Tutoring</a></li>
        <li><a href="#portfolio">Portfolio</a></li>
      </ul>
    </div>
    <div>
      <div class="footer-col-title">Connect</div>
      <ul class="footer-links">
         <li><a href="mailto:mandasgdwts@gmail.com">Email Me</a></li>
      </ul>
    </div>
  </div>
  <div class="footer-bottom">
    <div class="footer-copy">© 2026 Manda Creative. All rights reserved.</div>
    <div class="footer-social">
      <a href="#" class="social-icon">ig</a>
      <a href="#" class="social-icon">in</a>
      <a href="#" class="social-icon">be</a>
    </div>
  </div>
</footer>

<script>
  // Custom cursor
  const cursor = document.getElementById('cursor');
  const ring = document.getElementById('cursorRing');
  let mx = 0, my = 0, rx = 0, ry = 0;
  document.addEventListener('mousemove', e => { mx = e.clientX; my = e.clientY; cursor.style.left = mx + 'px'; cursor.style.top = my + 'px'; });
  function animateRing() {
    rx += (mx - rx) * 0.12; ry += (my - ry) * 0.12;
    ring.style.left = rx + 'px'; ring.style.top = ry + 'px';
    requestAnimationFrame(animateRing);
  }
  animateRing();
  document.querySelectorAll('a, button, .portfolio-item, .service-chip').forEach(el => {
    el.addEventListener('mouseenter', () => { cursor.style.transform = 'translate(-50%,-50%) scale(2.5)'; cursor.style.background = 'var(--terracotta)'; ring.style.opacity = '0.2'; });
    el.addEventListener('mouseleave', () => { cursor.style.transform = 'translate(-50%,-50%) scale(1)'; cursor.style.background = 'var(--terracotta)'; ring.style.opacity = '0.5'; });
  });

  // Scroll animations
  const observer = new IntersectionObserver(entries => {
    entries.forEach(e => { if (e.isIntersecting) e.target.classList.add('visible'); });
  }, { threshold: 0.12 });
  document.querySelectorAll('.fade-up').forEach(el => observer.observe(el));

  // Portfolio filter
  function filterPortfolio(cat, btn) {
    document.querySelectorAll('.portfolio-tab').forEach(t => t.classList.remove('active'));
    btn.classList.add('active');
    document.querySelectorAll('.portfolio-item').forEach(item => {
      const show = cat === 'all' || item.dataset.cat === cat;
      item.style.display = show ? 'block' : 'none';
    });
  }

  // Service chip toggle
  function toggleChip(chip) { chip.classList.toggle('selected'); }

  // Form submission
  function handleSubmit(e) {
    e.preventDefault();
    const btn = e.target.querySelector('.submit-btn');
    btn.textContent = 'Message Sent! ✓';
    btn.style.background = 'var(--sage)';
    setTimeout(() => { btn.textContent = 'Send Message →'; btn.style.background = ''; e.target.reset(); document.querySelectorAll('.service-chip').forEach(c => c.classList.remove('selected')); }, 3000);
  }

  // Smooth nav scroll
  document.querySelectorAll('a[href^="#"]').forEach(a => {
    a.addEventListener('click', e => {
      const target = document.querySelector(a.getAttribute('href'));
      if (target) { e.preventDefault(); target.scrollIntoView({ behavior: 'smooth' }); }
    });
  });
</script>
</body>
</html>
