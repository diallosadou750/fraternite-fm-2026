/* ========================================
   RADIO FRATERNITÉ FM MAMOU — STYLESHEET v3
   Dark broadcast studio — amber/gold accents
   ======================================== */

*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}

:root{
  --bg:#0a0b0e;
  --bg2:#111318;
  --bg3:#181b22;
  --border:#242830;
  --amber:#e8a020;
  --amber2:#f5c842;
  --amber-glow:rgba(232,160,32,0.15);
  --red:#e03030;
  --green:#22c55e;
  --blue:#3b82f6;
  --text:#e8e4dc;
  --muted:#7a7870;
  --white:#ffffff;
  --font-disp:'Bebas Neue',sans-serif;
  --font-serif:'Crimson Pro',serif;
  --font-body:'DM Sans',sans-serif;
  --r:12px;
  --r-lg:20px;
  --shadow:0 8px 32px rgba(0,0,0,0.6);
  --glow:0 0 40px var(--amber-glow);
  --transition:0.25s ease;
}

html{scroll-behavior:smooth}
body{background:var(--bg);color:var(--text);font-family:var(--font-body);font-size:16px;line-height:1.6;overflow-x:hidden}
a{color:var(--amber);text-decoration:none;transition:color var(--transition)}
a:hover{color:var(--amber2)}
img{max-width:100%;display:block}
::-webkit-scrollbar{width:5px}
::-webkit-scrollbar-track{background:var(--bg)}
::-webkit-scrollbar-thumb{background:var(--amber);border-radius:3px}

/* ══ LOADING SCREEN ══════════════════════════════════════════ */
.loading-screen{
  position:fixed;inset:0;z-index:9999;
  background:var(--bg);
  display:flex;align-items:center;justify-content:center;
  transition:opacity 0.5s ease, visibility 0.5s ease;
}
.loading-screen.hidden{opacity:0;visibility:hidden;pointer-events:none}
.loading-inner{text-align:center}
.loading-logo{font-size:3.5rem;margin-bottom:1rem;animation:loadingPulse 1.2s infinite}
@keyframes loadingPulse{0%,100%{transform:scale(1)}50%{transform:scale(1.15)}}
.loading-name{font-family:var(--font-disp);font-size:2rem;color:var(--amber);letter-spacing:4px;margin-bottom:1.5rem}
.loading-bar{width:200px;height:3px;background:var(--border);border-radius:3px;margin:0 auto 1rem;overflow:hidden}
.loading-fill{height:100%;background:var(--amber);border-radius:3px;width:0%;transition:width 0.1s}
.loading-text{font-size:0.78rem;color:var(--muted);letter-spacing:2px}

/* ══ TICKER ══════════════════════════════════════════════════ */
.ticker-wrap{
  background:var(--amber);
  display:flex;align-items:center;
  height:36px;overflow:hidden;
  position:sticky;top:0;z-index:1001;
}
.ticker-label{
  flex-shrink:0;
  background:rgba(0,0,0,0.25);
  color:var(--bg);font-weight:800;font-size:0.7rem;
  letter-spacing:2px;text-transform:uppercase;
  padding:0 1rem;height:100%;display:flex;align-items:center;
  white-space:nowrap;
}
.ticker-track{flex:1;overflow:hidden;height:100%}
.ticker-content{
  display:inline-flex;align-items:center;height:100%;
  white-space:nowrap;
  color:var(--bg);font-weight:600;font-size:0.82rem;
  animation:ticker 30s linear infinite;
}
@keyframes ticker{0%{transform:translateX(100vw)}100%{transform:translateX(-100%)}}
.ticker-content:hover{animation-play-state:paused}

/* ══ NAVBAR ══════════════════════════════════════════════════ */
.navbar{
  position:sticky;top:0;z-index:1000;
  padding:0 2rem;
  background:rgba(10,11,14,0.88);
  backdrop-filter:blur(16px);
  -webkit-backdrop-filter:blur(16px);
  border-bottom:1px solid var(--border);
  transition:background var(--transition),box-shadow var(--transition);
}
.navbar.scrolled{background:rgba(10,11,14,0.98);box-shadow:0 2px 24px rgba(0,0,0,0.5)}
.nav-inner{
  max-width:1200px;margin:0 auto;
  display:flex;align-items:center;justify-content:space-between;
  height:68px;
}
.nav-logo{display:flex;align-items:center;gap:10px;color:var(--white);text-decoration:none}
.logo-icon{font-size:1.6rem;flex-shrink:0}
.logo-img{height:40px;width:auto;object-fit:contain;flex-shrink:0}
.logo-text{display:flex;flex-direction:column;line-height:1.1}
.logo-main{font-family:var(--font-disp);font-size:1.2rem;color:var(--amber);letter-spacing:2px}
.logo-sub{font-size:0.6rem;color:var(--muted);letter-spacing:3px;text-transform:uppercase}
.nav-links{display:flex;list-style:none;gap:1.75rem;align-items:center}
.nav-links a{
  font-size:0.82rem;font-weight:500;letter-spacing:0.8px;
  text-transform:uppercase;color:var(--muted);
  padding-bottom:2px;border-bottom:2px solid transparent;
  transition:color var(--transition),border-color var(--transition);
}
.nav-links a:hover{color:var(--amber);border-color:var(--amber)}
.burger{display:none;background:none;border:none;cursor:pointer;flex-direction:column;gap:5px;padding:4px}
.burger span{display:block;width:24px;height:2px;background:var(--text);border-radius:2px;transition:all 0.3s}
.burger.open span:nth-child(1){transform:translateY(7px) rotate(45deg)}
.burger.open span:nth-child(2){opacity:0}
.burger.open span:nth-child(3){transform:translateY(-7px) rotate(-45deg)}

/* ══ HERO ════════════════════════════════════════════════════ */
.hero{
  position:relative;min-height:100vh;
  display:flex;align-items:center;justify-content:center;
  padding:100px 2rem 5rem;overflow:hidden;
}
.hero-bg{position:absolute;inset:0;z-index:0}
.hero-overlay{
  position:absolute;inset:0;
  background:radial-gradient(ellipse 80% 60% at 50% 30%,rgba(26,18,0,0.85) 0%,rgba(10,11,14,0.95) 70%);
  z-index:1;
}
.hero-bg-img{
  position:absolute;inset:0;
  background-size:cover;background-position:center;background-repeat:no-repeat;
  z-index:0;
}
.hero-grid{
  position:absolute;inset:0;z-index:2;
  background-image:linear-gradient(rgba(232,160,32,0.04) 1px,transparent 1px),linear-gradient(90deg,rgba(232,160,32,0.04) 1px,transparent 1px);
  background-size:60px 60px;
  mask-image:radial-gradient(ellipse 70% 70% at 50% 50%,black 0%,transparent 80%);
}
.hero-noise{
  position:absolute;inset:0;z-index:2;opacity:0.35;pointer-events:none;
  background-image:url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.04'/%3E%3C/svg%3E");
}
.hero-content{position:relative;z-index:3;text-align:center;max-width:720px;width:100%;animation:fadeUp 0.8s ease both}
@keyframes fadeUp{from{opacity:0;transform:translateY(30px)}to{opacity:1;transform:translateY(0)}}
.live-badge{
  display:inline-flex;align-items:center;gap:8px;
  background:rgba(224,48,48,0.15);border:1px solid rgba(224,48,48,0.4);
  color:var(--red);font-size:0.72rem;font-weight:700;letter-spacing:3px;text-transform:uppercase;
  padding:6px 18px;border-radius:50px;margin-bottom:1.5rem;
}
.live-dot{width:8px;height:8px;border-radius:50%;background:var(--red);animation:pulseRed 1.4s infinite}
@keyframes pulseRed{0%,100%{opacity:1;transform:scale(1)}50%{opacity:0.5;transform:scale(1.4)}}
.hero-title{
  font-family:var(--font-disp);
  font-size:clamp(3.5rem,10vw,7rem);
  line-height:0.95;letter-spacing:3px;
  color:var(--white);margin-bottom:1rem;
  text-shadow:0 4px 32px rgba(0,0,0,0.8);
}
.hero-title em{
  font-family:var(--font-serif);font-style:italic;font-weight:300;
  color:var(--amber);display:block;font-size:0.9em;letter-spacing:1px;
}
.hero-sub{color:var(--muted);font-size:1rem;font-weight:300;letter-spacing:0.5px;margin-bottom:2.5rem}

/* ── Player Card ── */
.player-card{
  background:var(--bg2);border:1px solid var(--border);
  border-radius:var(--r-lg);padding:1.5rem 2rem;
  box-shadow:var(--shadow),var(--glow);margin-bottom:2.5rem;
  animation:fadeUp 0.8s 0.2s ease both;
}
.player-visual{display:flex;align-items:center;gap:1.5rem;margin-bottom:1.25rem}
.wave-bars{display:flex;align-items:center;gap:3px;height:48px;min-width:90px}
.wave-bars span{display:block;width:5px;background:var(--amber);border-radius:3px;height:8px;transition:height 0.1s}
.wave-bars.playing span{animation:wave 0.8s infinite ease-in-out}
.wave-bars span:nth-child(1){animation-delay:0s}.wave-bars span:nth-child(2){animation-delay:0.06s}
.wave-bars span:nth-child(3){animation-delay:0.12s}.wave-bars span:nth-child(4){animation-delay:0.18s}
.wave-bars span:nth-child(5){animation-delay:0.24s}.wave-bars span:nth-child(6){animation-delay:0.1s}
.wave-bars span:nth-child(7){animation-delay:0.16s}.wave-bars span:nth-child(8){animation-delay:0.22s}
.wave-bars span:nth-child(9){animation-delay:0.28s}.wave-bars span:nth-child(10){animation-delay:0.14s}
.wave-bars span:nth-child(11){animation-delay:0.2s}.wave-bars span:nth-child(12){animation-delay:0.08s}
.wave-bars span:nth-child(13){animation-delay:0.26s}.wave-bars span:nth-child(14){animation-delay:0.04s}
.wave-bars span:nth-child(15){animation-delay:0.3s}
@keyframes wave{0%,100%{height:6px}50%{height:40px}}
.player-station{font-family:var(--font-disp);letter-spacing:2px;font-size:1rem;color:var(--amber);margin-bottom:2px}
.player-now{font-size:0.82rem;color:var(--muted);font-style:italic}
.player-controls{display:flex;align-items:center;gap:1.5rem}
.btn-play{
  width:56px;height:56px;border-radius:50%;
  background:var(--amber);border:none;cursor:pointer;color:var(--bg);
  display:flex;align-items:center;justify-content:center;flex-shrink:0;
  transition:background var(--transition),transform 0.15s,box-shadow var(--transition);
  box-shadow:0 4px 20px rgba(232,160,32,0.4);
}
.btn-play:hover{background:var(--amber2);transform:scale(1.08);box-shadow:0 6px 28px rgba(232,160,32,0.55)}
.btn-play svg{width:22px;height:22px}
.volume-wrap{display:flex;align-items:center;gap:8px;flex:1}
.vol-icon{font-size:1rem;color:var(--muted)}
.volume-slider{-webkit-appearance:none;appearance:none;width:100%;height:4px;border-radius:4px;background:var(--border);outline:none;cursor:pointer}
.volume-slider::-webkit-slider-thumb{-webkit-appearance:none;width:16px;height:16px;border-radius:50%;background:var(--amber);cursor:pointer;box-shadow:0 0 8px rgba(232,160,32,0.5)}

/* Stats */
.hero-stats{display:flex;justify-content:center;gap:3rem;animation:fadeUp 0.8s 0.4s ease both}
.stat{text-align:center}
.stat-num{display:block;font-family:var(--font-disp);font-size:2.5rem;color:var(--amber);line-height:1}
.stat-lbl{font-size:0.7rem;color:var(--muted);text-transform:uppercase;letter-spacing:2px}

/* Scroll hint */
.scroll-hint{
  position:absolute;bottom:2rem;left:50%;transform:translateX(-50%);
  z-index:3;color:var(--muted);animation:scrollBounce 2s infinite;
}
.scroll-arrow{font-size:1.4rem}
@keyframes scrollBounce{0%,100%{transform:translateX(-50%) translateY(0)}50%{transform:translateX(-50%) translateY(8px)}}

/* ══ SECTIONS GENERAL ════════════════════════════════════════ */
.section{padding:6rem 2rem;max-width:1200px;margin:0 auto}
.section-label{font-size:0.68rem;font-weight:700;letter-spacing:4px;text-transform:uppercase;color:var(--amber);margin-bottom:0.75rem}
.section-title{font-family:var(--font-disp);font-size:clamp(2.2rem,5vw,3.5rem);line-height:1;letter-spacing:2px;color:var(--white);margin-bottom:1rem}
.section-title em{font-family:var(--font-serif);font-style:italic;color:var(--amber);font-size:0.95em}
.section-desc{color:var(--muted);max-width:520px;font-size:0.95rem;margin-bottom:3rem}

/* ══ VIDEO ══════════════════════════════════════════════════ */
.video-section{padding:6rem 2rem;max-width:1200px;margin:0 auto}
.video-tabs{display:flex;gap:0.5rem;margin-bottom:1.5rem}
.vtab{
  padding:0.5rem 1.5rem;background:var(--bg3);border:1px solid var(--border);
  border-radius:50px;color:var(--muted);font-size:0.85rem;
  font-family:var(--font-body);font-weight:500;cursor:pointer;transition:all var(--transition);
}
.vtab.active,.vtab:hover{background:var(--amber);border-color:var(--amber);color:var(--bg);font-weight:700}
.video-pane{display:none}
.video-pane.active{display:block}
.fb-video-wrap{
  position:relative;width:100%;padding-top:56.25%;
  background:var(--bg3);border-radius:var(--r-lg);overflow:hidden;
  border:1px solid var(--border);
}
.fb-video-wrap iframe{position:absolute;inset:0;width:100%;height:100%;border:none}
.video-overlay{
  position:absolute;inset:0;z-index:2;
  background:rgba(10,11,14,0.88);
  display:flex;align-items:center;justify-content:center;
  backdrop-filter:blur(4px);
}
.overlay-inner{text-align:center}
.overlay-icon{font-size:3.5rem;color:var(--amber);line-height:1;margin-bottom:1rem;animation:pulseAmber 2s infinite}
@keyframes pulseAmber{0%,100%{transform:scale(1)}50%{transform:scale(1.1)}}
.overlay-inner p{color:var(--muted);margin-bottom:1.5rem;font-size:0.9rem}
.btn-load-video{
  padding:0.75rem 2rem;background:var(--amber);border:none;border-radius:50px;
  color:var(--bg);font-weight:700;font-size:0.9rem;cursor:pointer;font-family:var(--font-body);
  transition:background var(--transition),transform 0.15s;
}
.btn-load-video:hover{background:var(--amber2);transform:scale(1.04)}

/* ══ PROGRAMMES ══════════════════════════════════════════════ */
.prog-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(280px,1fr));gap:1.25rem}
.prog-card{
  background:var(--bg2);border:1px solid var(--border);border-radius:var(--r);
  padding:1.5rem;transition:border-color var(--transition),transform 0.2s,box-shadow var(--transition);
}
.prog-card:hover{border-color:var(--amber);transform:translateY(-4px);box-shadow:0 8px 32px rgba(232,160,32,0.12)}
.prog-time{font-family:var(--font-disp);font-size:0.9rem;letter-spacing:2px;color:var(--amber);margin-bottom:6px}
.prog-name{font-size:1.05rem;font-weight:700;color:var(--white);margin-bottom:6px}
.prog-host{font-size:0.8rem;color:var(--muted)}
.prog-tag{
  display:inline-block;margin-top:10px;font-size:0.65rem;font-weight:700;letter-spacing:1px;text-transform:uppercase;
  padding:3px 10px;border-radius:50px;
  background:rgba(232,160,32,0.12);color:var(--amber);border:1px solid rgba(232,160,32,0.25);
}
.prog-tag.live{background:rgba(224,48,48,0.12);color:var(--red);border-color:rgba(224,48,48,0.25)}

/* ══ ACTUALITÉS ══════════════════════════════════════════════ */
.news-section{border-top:1px solid var(--border)}
.news-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(300px,1fr));gap:1.5rem}
.news-card{
  background:var(--bg2);border:1px solid var(--border);border-radius:var(--r);
  overflow:hidden;transition:transform 0.2s,box-shadow 0.2s;
}
.news-card:hover{transform:translateY(-5px);box-shadow:var(--shadow)}
.news-img{
  width:100%;height:180px;object-fit:cover;
  background:var(--bg3);display:flex;align-items:center;justify-content:center;font-size:3rem;
}
.news-body{padding:1.25rem}
.news-cat{font-size:0.65rem;font-weight:700;letter-spacing:2px;text-transform:uppercase;color:var(--amber);margin-bottom:8px}
.news-title{font-size:1rem;font-weight:600;color:var(--white);margin-bottom:8px;line-height:1.4}
.news-excerpt{font-size:0.82rem;color:var(--muted);line-height:1.5;margin-bottom:12px}
.news-date{font-size:0.72rem;color:var(--border)}

/* ══ À PROPOS ════════════════════════════════════════════════ */
.apropos-section{
  background:var(--bg2);border-top:1px solid var(--border);border-bottom:1px solid var(--border);
  padding:6rem 2rem;
}
.apropos-inner{
  max-width:1200px;margin:0 auto;
  display:grid;grid-template-columns:1fr 1fr;gap:4rem;align-items:center;
}
.apropos-text .section-title{margin-bottom:1.25rem}
.apropos-text p{color:var(--muted);font-size:0.98rem;line-height:1.8;margin-bottom:2rem}
.apropos-badges{display:flex;flex-wrap:wrap;gap:.75rem}
.apropos-badge{
  display:inline-flex;align-items:center;gap:.5rem;
  background:var(--bg3);border:1px solid var(--border);
  border-radius:50px;padding:0.45rem 1rem;
  font-size:0.8rem;color:var(--text);
  transition:border-color var(--transition);
}
.apropos-badge:hover{border-color:var(--amber)}

.apropos-visual{display:flex;align-items:center;justify-content:center}
.apropos-card{
  background:var(--bg);border:1px solid var(--border);
  border-radius:24px;padding:3rem 2.5rem;text-align:center;
  box-shadow:var(--shadow),var(--glow);min-width:280px;
}
.apropos-wave{display:flex;align-items:center;justify-content:center;gap:4px;height:64px;margin-bottom:1.5rem}
.apropos-wave span{
  display:block;width:6px;background:var(--amber);border-radius:3px;
  animation:wave 0.8s infinite ease-in-out;
}
.apropos-wave span:nth-child(1){animation-delay:0s;height:20px}
.apropos-wave span:nth-child(2){animation-delay:0.1s;height:35px}
.apropos-wave span:nth-child(3){animation-delay:0.2s;height:50px}
.apropos-wave span:nth-child(4){animation-delay:0.15s;height:40px}
.apropos-wave span:nth-child(5){animation-delay:0.05s;height:28px}
.apropos-wave span:nth-child(6){animation-delay:0.25s;height:55px}
.apropos-wave span:nth-child(7){animation-delay:0.1s;height:38px}
.apropos-wave span:nth-child(8){animation-delay:0.18s;height:45px}
.apropos-wave span:nth-child(9){animation-delay:0.08s;height:30px}
.apropos-wave span:nth-child(10){animation-delay:0.22s;height:20px}
.apropos-freq{font-family:var(--font-disp);font-size:3rem;color:var(--amber);line-height:1;letter-spacing:3px}
.apropos-name{font-family:var(--font-disp);font-size:1.3rem;color:var(--white);letter-spacing:4px;margin:0.5rem 0 0.25rem}
.apropos-loc{font-size:0.72rem;color:var(--muted);letter-spacing:4px;text-transform:uppercase}

/* ══ ÉQUIPE ══════════════════════════════════════════════════ */
.team-section{border-top:1px solid var(--border)}
.team-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(460px,1fr));gap:1.5rem}
.team-card{
  display:flex;align-items:flex-start;gap:1.5rem;
  background:var(--bg2);border:1px solid var(--border);border-radius:var(--r);
  padding:1.75rem;transition:border-color var(--transition),transform 0.2s,box-shadow var(--transition);
}
.team-card:hover{transform:translateY(-4px);box-shadow:0 8px 32px rgba(0,0,0,0.3);border-color:rgba(232,160,32,0.3)}
.team-avatar{
  flex-shrink:0;width:72px;height:72px;border-radius:50%;border:2px solid;
  display:flex;align-items:center;justify-content:center;overflow:hidden;
}
.team-avatar img{width:100%;height:100%;object-fit:cover}
.team-initiales{font-family:var(--font-disp);font-size:1.4rem;letter-spacing:1px}
.team-nom{font-size:1.05rem;font-weight:700;color:var(--white);margin-bottom:4px}
.team-poste{font-size:0.78rem;font-weight:600;letter-spacing:1px;text-transform:uppercase;margin-bottom:10px}
.team-desc{font-size:0.83rem;color:var(--muted);line-height:1.6}

/* ══ COMMUNAUTÉ ══════════════════════════════════════════════ */
.community-section{background:var(--bg2);border-top:1px solid var(--border);border-bottom:1px solid var(--border);padding:0}
.comm-inner{
  max-width:1200px;margin:0 auto;
  display:grid;grid-template-columns:1fr 1fr;gap:4rem;padding:6rem 2rem;align-items:start;
}
.comm-text .section-title{margin-bottom:1rem}
.comm-text p{color:var(--muted);font-size:0.95rem;margin-bottom:2rem}
.social-links{display:flex;flex-wrap:wrap;gap:0.75rem}
.social-btn{
  display:inline-flex;align-items:center;gap:8px;
  padding:0.6rem 1.25rem;border-radius:8px;
  font-size:0.85rem;font-weight:600;color:var(--white);
  transition:transform 0.15s,opacity 0.15s;
}
.social-btn:hover{transform:translateY(-2px);opacity:0.88;color:var(--white)}
.social-btn.fb{background:#1877f2}
.social-btn.wa{background:#25d366}
.social-btn.yt{background:#ff0000}
.social-btn.ig{background:linear-gradient(135deg,#f09433,#e6683c,#dc2743,#cc2366,#bc1888)}
.social-btn.tt{background:#000}
.comm-form h3{font-family:var(--font-disp);font-size:1.6rem;color:var(--white);margin-bottom:1.25rem;letter-spacing:1px}
.form-ded{display:flex;flex-direction:column;gap:0.75rem}
.form-ded input,.form-ded textarea{
  background:var(--bg3);border:1px solid var(--border);border-radius:var(--r);
  color:var(--text);font-family:var(--font-body);font-size:0.9rem;padding:0.75rem 1rem;
  outline:none;transition:border-color var(--transition);
}
.form-ded input:focus,.form-ded textarea:focus{border-color:var(--amber)}
.form-ded textarea{resize:vertical}
.btn-submit{
  padding:0.85rem 2rem;background:var(--amber);border:none;border-radius:var(--r);
  color:var(--bg);font-weight:700;font-family:var(--font-body);font-size:0.9rem;
  cursor:pointer;transition:background var(--transition),transform 0.15s;
}
.btn-submit:hover{background:var(--amber2);transform:scale(1.02)}
.form-success{
  background:rgba(34,197,94,0.12);border:1px solid rgba(34,197,94,0.3);
  color:var(--green);padding:1rem;border-radius:var(--r);font-size:0.88rem;
}

/* ══ FOOTER ═════════════════════════════════════════════════ */
.footer{background:var(--bg);border-top:1px solid var(--border);padding:4rem 2rem 2rem}
.footer-inner{max-width:1200px;margin:0 auto}
.footer-top{display:grid;grid-template-columns:auto 1fr;gap:4rem;margin-bottom:3rem;padding-bottom:3rem;border-bottom:1px solid var(--border)}
.footer-brand{display:flex;align-items:flex-start;gap:12px}
.footer-logo-img{height:48px;width:auto;object-fit:contain}
.footer-name{font-family:var(--font-disp);color:var(--amber);font-size:1.2rem;letter-spacing:2px;margin-bottom:4px}
.footer-tagline{font-size:0.82rem;color:var(--muted);margin-bottom:8px}
.footer-freq-badge{font-size:0.75rem;color:var(--text);background:rgba(232,160,32,0.1);border:1px solid rgba(232,160,32,0.2);padding:4px 10px;border-radius:50px;display:inline-block}
.footer-cols{display:grid;grid-template-columns:repeat(3,1fr);gap:2rem}
.footer-col{display:flex;flex-direction:column;gap:0.6rem}
.footer-col-title{font-size:0.7rem;font-weight:700;letter-spacing:2px;text-transform:uppercase;color:var(--amber);margin-bottom:0.25rem}
.footer-col a{font-size:0.85rem;color:var(--muted);transition:color var(--transition)}
.footer-col a:hover{color:var(--amber)}
.footer-bottom{display:flex;justify-content:space-between;align-items:center;flex-wrap:wrap;gap:1rem;font-size:0.72rem;color:var(--border)}

/* ══ MINI PLAYER ═════════════════════════════════════════════ */
.mini-player{
  position:fixed;bottom:0;left:0;right:0;z-index:999;
  background:rgba(17,19,24,0.97);backdrop-filter:blur(12px);
  border-top:1px solid var(--border);
  display:flex;align-items:center;justify-content:space-between;
  padding:0.75rem 2rem;
  transform:translateY(100%);transition:transform 0.4s cubic-bezier(0.34,1.56,0.64,1);
  box-shadow:0 -4px 24px rgba(0,0,0,0.4);
}
.mini-player.visible{transform:translateY(0)}
.mini-left{display:flex;align-items:center;gap:12px}
.mini-wave{display:flex;align-items:center;gap:2px;height:32px}
.mini-wave span{display:block;width:4px;background:var(--amber);border-radius:3px;height:6px}
.mini-wave.playing span{animation:wave 0.8s infinite ease-in-out}
.mini-wave span:nth-child(1){animation-delay:0s}.mini-wave span:nth-child(2){animation-delay:0.1s}
.mini-wave span:nth-child(3){animation-delay:0.2s}.mini-wave span:nth-child(4){animation-delay:0.15s}
.mini-wave span:nth-child(5){animation-delay:0.05s}
.mini-name{display:block;font-family:var(--font-disp);color:var(--amber);font-size:0.95rem;letter-spacing:1px}
.mini-freq{display:block;font-size:0.7rem;color:var(--muted)}
.mini-play{
  width:42px;height:42px;border-radius:50%;background:var(--amber);
  border:none;color:var(--bg);display:flex;align-items:center;justify-content:center;
  cursor:pointer;transition:background var(--transition),transform 0.15s;
}
.mini-play:hover{background:var(--amber2);transform:scale(1.08)}
.mini-play svg{width:16px;height:16px}

/* ══ RESPONSIVE ══════════════════════════════════════════════ */
@media(max-width:1024px){
  .footer-top{grid-template-columns:1fr;gap:2rem}
}
@media(max-width:900px){
  .comm-inner{grid-template-columns:1fr;gap:3rem}
  .apropos-inner{grid-template-columns:1fr;gap:3rem}
  .apropos-visual{display:none}
}
@media(max-width:768px){
  .nav-links{
    display:none;flex-direction:column;gap:0;
    position:absolute;top:68px;left:0;right:0;
    background:rgba(10,11,14,0.98);border-bottom:1px solid var(--border);padding:1rem 0;
  }
  .nav-links.open{display:flex}
  .nav-links a{padding:0.75rem 2rem;border-bottom:none}
  .burger{display:flex}
  .hero-stats{gap:1.5rem}
  .stat-num{font-size:2rem}
  .player-card{padding:1.25rem}
  .section{padding:4rem 1.25rem}
  .video-section{padding:4rem 1.25rem}
  .footer-cols{grid-template-columns:1fr 1fr;gap:1.5rem}
  .mini-player{padding:0.6rem 1.25rem}
}
@media(max-width:600px){
  .team-grid{grid-template-columns:1fr}
  .team-card{flex-direction:column;align-items:center;text-align:center}
  .footer-cols{grid-template-columns:1fr}
  .footer-bottom{flex-direction:column;text-align:center}
  .hero-stats{gap:1rem}
}

/* ══════════════════════════════════════════
   DONS MOBILE MONEY
══════════════════════════════════════════ */
.dons-section { border-top: 1px solid var(--border); }
.dons-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 1.5rem;
}

.don-card {
  background: var(--bg2);
  border: 1px solid var(--border);
  border-radius: var(--r-lg);
  padding: 1.75rem;
  transition: border-color var(--transition), transform 0.2s;
}
.don-card:hover { border-color: rgba(232,160,32,0.35); transform: translateY(-3px); }
.don-card.featured { border-color: rgba(232,160,32,0.3); box-shadow: var(--glow); }

.don-card-header { display: flex; align-items: center; gap: 1rem; margin-bottom: 1.5rem; }
.don-icon { font-size: 2rem; flex-shrink: 0; }
.don-title { font-weight: 700; font-size: 1.05rem; color: var(--white); margin-bottom: 2px; }
.don-sub { font-size: 0.78rem; color: var(--muted); }

/* Mobile Money options */
.mm-options { display: flex; flex-direction: column; gap: 0.75rem; margin-bottom: 1.25rem; }
.mm-item {
  display: flex; align-items: center; gap: 0.75rem;
  background: var(--bg3); border: 1px solid var(--border);
  border-radius: var(--r); padding: 0.85rem 1rem;
}
.mm-item.orange { border-left: 3px solid #ff6600; }
.mm-item.mtn    { border-left: 3px solid #ffcc00; }
.mm-logo { font-size: 1.4rem; flex-shrink: 0; }
.mm-info { flex: 1; }
.mm-name { font-size: 0.82rem; font-weight: 700; color: var(--text); }
.mm-num  { font-size: 0.88rem; color: var(--amber); font-family: monospace; letter-spacing: 1px; }
.btn-copy-num {
  flex-shrink: 0; padding: 0.4rem 0.9rem;
  background: rgba(232,160,32,0.12); border: 1px solid rgba(232,160,32,0.3);
  border-radius: 8px; color: var(--amber); font-size: 0.75rem;
  font-weight: 700; cursor: pointer; font-family: var(--font-body);
  transition: all var(--transition);
}
.btn-copy-num:hover { background: rgba(232,160,32,0.25); }
.btn-copy-num.copied { background: rgba(34,197,94,0.15); border-color: rgba(34,197,94,0.4); color: var(--green); }

.mm-instructions {
  font-size: 0.78rem; color: var(--muted); line-height: 1.6;
  background: var(--bg3); border-radius: var(--r); padding: 0.85rem;
  border-left: 3px solid var(--amber);
}

/* Montants suggérés */
.don-amounts {
  display: grid; grid-template-columns: 1fr 1fr;
  gap: 0.6rem; margin-bottom: 1.25rem;
}
.don-amount {
  background: var(--bg3); border: 1px solid var(--border);
  border-radius: var(--r); padding: 0.85rem 0.6rem;
  text-align: center; cursor: pointer;
  transition: all var(--transition);
}
.don-amount:hover, .don-amount.active {
  border-color: var(--amber); background: rgba(232,160,32,0.08);
}
.don-amount.featured-amt {
  border-color: rgba(232,160,32,0.4);
  background: rgba(232,160,32,0.06);
  grid-column: span 2;
}
.don-amt-val { display: block; font-family: var(--font-disp); font-size: 1.1rem; color: var(--amber); }
.don-amt-lbl { display: block; font-size: 0.68rem; color: var(--muted); text-transform: uppercase; letter-spacing: 1px; margin-top: 2px; }

.btn-don-wa {
  width: 100%; padding: 0.85rem;
  background: #25d366; border: none; border-radius: var(--r);
  color: var(--white); font-weight: 700; font-family: var(--font-body);
  font-size: 0.9rem; cursor: pointer; margin-bottom: 0.75rem;
  transition: opacity var(--transition), transform 0.15s;
}
.btn-don-wa:hover { opacity: 0.88; transform: scale(1.02); }
.don-note { font-size: 0.75rem; color: var(--muted); text-align: center; }

/* Goal card */
.goal-card { display: flex; flex-direction: column; gap: 0.5rem; }
.goal-progress-wrap { margin: 0.5rem 0; }
.goal-bar {
  width: 100%; height: 10px;
  background: var(--border); border-radius: 10px; overflow: hidden;
  margin-bottom: 0.5rem;
}
.goal-fill {
  height: 100%; background: linear-gradient(90deg, var(--amber), var(--amber2));
  border-radius: 10px; transition: width 1.5s cubic-bezier(0.4,0,0.2,1);
}
.goal-nums {
  display: flex; justify-content: space-between;
  font-size: 0.75rem; color: var(--muted);
}
.goal-pct { font-family: var(--font-disp); font-size: 1.5rem; color: var(--amber); }
.amb-title { font-size: 0.75rem; font-weight: 700; letter-spacing: 1px; color: var(--amber); text-transform: uppercase; margin-top: 0.5rem; }
.amb-list { display: flex; flex-wrap: wrap; gap: 0.4rem; margin-top: 0.5rem; }
.amb-tag {
  font-size: 0.72rem; background: rgba(232,160,32,0.1);
  border: 1px solid rgba(232,160,32,0.2);
  color: var(--text); padding: 3px 8px; border-radius: 50px;
}

/* ══════════════════════════════════════════
   SPONSORS / PUBLICITÉ
══════════════════════════════════════════ */
.sponsors-section {
  background: var(--bg2);
  border-top: 1px solid var(--border);
  border-bottom: 1px solid var(--border);
  padding: 6rem 2rem;
}
.sponsors-inner {
  max-width: 1200px; margin: 0 auto;
  display: grid; grid-template-columns: 1fr 1fr;
  gap: 4rem; align-items: start;
}
.sponsors-text .section-title { margin-bottom: 1rem; }
.sponsors-text > p { color: var(--muted); font-size: 0.95rem; margin-bottom: 2rem; }

/* Packages */
.sponsor-packages { display: flex; flex-direction: column; gap: 0.75rem; }
.pkg-card {
  background: var(--bg3); border: 1px solid var(--border);
  border-radius: var(--r); padding: 1.25rem;
  position: relative;
  transition: border-color var(--transition), transform 0.2s;
}
.pkg-card:hover { border-color: rgba(232,160,32,0.35); transform: translateX(4px); }
.pkg-card.featured-pkg {
  border-color: var(--amber);
  background: rgba(232,160,32,0.05);
  box-shadow: 0 4px 20px rgba(232,160,32,0.12);
}
.pkg-badge {
  position: absolute; top: -10px; right: 1rem;
  background: var(--amber); color: var(--bg);
  font-size: 0.6rem; font-weight: 800; letter-spacing: 2px;
  padding: 3px 10px; border-radius: 50px; text-transform: uppercase;
}
.pkg-name { font-size: 1rem; font-weight: 700; color: var(--white); margin-bottom: 4px; }
.pkg-price { font-family: var(--font-disp); font-size: 1.4rem; color: var(--amber); letter-spacing: 1px; margin-bottom: 0.75rem; }
.pkg-price span { font-family: var(--font-body); font-size: 0.75rem; color: var(--muted); }
.pkg-features { list-style: none; display: flex; flex-direction: column; gap: 4px; }
.pkg-features li { font-size: 0.8rem; color: var(--muted); }

/* Sponsor form */
.sponsors-form h3 {
  font-family: var(--font-disp); font-size: 1.6rem;
  color: var(--white); letter-spacing: 1px; margin-bottom: 1.25rem;
}
.sponsors-form select {
  background: var(--bg3); border: 1px solid var(--border);
  border-radius: var(--r); color: var(--text);
  font-family: var(--font-body); font-size: 0.9rem;
  padding: 0.75rem 1rem; outline: none; width: 100%;
  transition: border-color var(--transition); cursor: pointer;
}
.sponsors-form select:focus { border-color: var(--amber); }
.sponsors-form select option { background: var(--bg3); }
.sponsors-reassurance {
  display: flex; flex-wrap: wrap; gap: 0.75rem;
  margin-top: 1rem;
}
.sponsors-reassurance span {
  font-size: 0.72rem; color: var(--muted);
  background: var(--bg3); border: 1px solid var(--border);
  padding: 4px 10px; border-radius: 50px;
}

@media (max-width: 900px) {
  .sponsors-inner { grid-template-columns: 1fr; }
  .sponsor-packages { flex-direction: row; flex-wrap: wrap; }
  .pkg-card { flex: 1; min-width: 200px; }
}
@media (max-width: 600px) {
  .dons-grid { grid-template-columns: 1fr; }
  .don-amounts { grid-template-columns: 1fr 1fr; }
  .don-amount.featured-amt { grid-column: span 2; }
  .sponsor-packages { flex-direction: column; }
}

/* ══════════════════════════════════════════
   NOTIFICATION BANNER
══════════════════════════════════════════ */
.notif-banner {
  position: fixed; bottom: 0; left: 0; right: 0; z-index: 998;
  background: var(--bg2); border-top: 1px solid rgba(232,160,32,0.3);
  padding: 1rem 2rem;
  display: flex; align-items: center; justify-content: space-between;
  flex-wrap: wrap; gap: 1rem;
  box-shadow: 0 -4px 24px rgba(0,0,0,0.4);
  animation: slideUp 0.4s ease;
}
@keyframes slideUp { from { transform: translateY(100%); } to { transform: translateY(0); } }
.notif-content { display: flex; align-items: center; gap: 0.75rem; }
.notif-icon { font-size: 1.5rem; flex-shrink: 0; }
.notif-text { font-size: 0.88rem; color: var(--text); }
.notif-actions { display: flex; gap: 0.5rem; }
.btn-notif-yes {
  padding: 0.5rem 1.25rem; background: var(--amber); border: none;
  border-radius: 8px; color: var(--bg); font-weight: 700;
  font-family: var(--font-body); font-size: 0.85rem; cursor: pointer;
  transition: background var(--transition);
}
.btn-notif-yes:hover { background: var(--amber2); }
.btn-notif-no {
  padding: 0.5rem 1rem; background: none;
  border: 1px solid var(--border); border-radius: 8px;
  color: var(--muted); font-family: var(--font-body);
  font-size: 0.85rem; cursor: pointer;
  transition: border-color var(--transition), color var(--transition);
}
.btn-notif-no:hover { border-color: var(--muted); color: var(--text); }

/* ══════════════════════════════════════════
   CLIPS VIDÉO
══════════════════════════════════════════ */
.clips-section { border-top: 1px solid var(--border); }
.clips-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
  gap: 1.25rem;
  margin-bottom: 2rem;
}
.clip-card {
  background: var(--bg2); border: 1px solid var(--border);
  border-radius: var(--r); overflow: hidden;
  transition: transform 0.2s, border-color var(--transition), box-shadow 0.2s;
  cursor: pointer;
}
.clip-card:hover {
  transform: translateY(-5px);
  border-color: rgba(232,160,32,0.4);
  box-shadow: 0 8px 28px rgba(0,0,0,0.4);
}
.clip-thumb {
  position: relative; width: 100%; padding-top: 56.25%;
  background: var(--bg3);
  display: flex; align-items: center; justify-content: center;
}
.clip-thumb-inner {
  position: absolute; inset: 0;
  display: flex; align-items: center; justify-content: center;
  background: linear-gradient(135deg, var(--bg3) 0%, rgba(232,160,32,0.05) 100%);
}
.clip-thumb-emoji { font-size: 3rem; }
.clip-thumb-yt {
  position: absolute; inset: 0; border: none; width: 100%; height: 100%;
  pointer-events: none;
}
.clip-play-btn {
  position: absolute; inset: 0;
  display: flex; align-items: center; justify-content: center;
  background: rgba(10,11,14,0.5);
  transition: background var(--transition);
}
.clip-play-btn:hover { background: rgba(10,11,14,0.3); }
.clip-play-icon {
  width: 52px; height: 52px; border-radius: 50%;
  background: var(--amber); color: var(--bg);
  display: flex; align-items: center; justify-content: center;
  font-size: 1.2rem; box-shadow: 0 4px 20px rgba(0,0,0,0.5);
  transition: transform 0.2s, background var(--transition);
}
.clip-card:hover .clip-play-icon { transform: scale(1.1); background: var(--amber2); }
.clip-duree {
  position: absolute; bottom: 8px; right: 8px;
  background: rgba(0,0,0,0.8); color: var(--white);
  font-size: 0.72rem; font-weight: 700; padding: 2px 7px;
  border-radius: 4px; letter-spacing: 0.5px;
}
.clip-body { padding: 1rem; }
.clip-cat {
  font-size: 0.62rem; font-weight: 700; letter-spacing: 2px;
  text-transform: uppercase; color: var(--amber); margin-bottom: 6px;
}
.clip-titre {
  font-size: 0.9rem; font-weight: 600; color: var(--white);
  line-height: 1.4; margin-bottom: 6px;
}
.clip-desc { font-size: 0.78rem; color: var(--muted); line-height: 1.5; margin-bottom: 8px; }
.clip-date { font-size: 0.68rem; color: var(--border); }

/* Modal clip */
.clip-modal {
  position: fixed; inset: 0; z-index: 9000;
  background: rgba(0,0,0,0.92); backdrop-filter: blur(8px);
  display: flex; align-items: center; justify-content: center;
  padding: 1rem;
  opacity: 0; visibility: hidden;
  transition: opacity 0.3s, visibility 0.3s;
}
.clip-modal.open { opacity: 1; visibility: visible; }
.clip-modal-inner {
  width: 100%; max-width: 860px;
  background: var(--bg2); border: 1px solid var(--border);
  border-radius: var(--r-lg); overflow: hidden;
}
.clip-modal-video { position: relative; width: 100%; padding-top: 56.25%; }
.clip-modal-video iframe {
  position: absolute; inset: 0; width: 100%; height: 100%; border: none;
}
.clip-modal-placeholder {
  position: absolute; inset: 0;
  display: flex; flex-direction: column; align-items: center; justify-content: center;
  gap: 1rem; background: var(--bg3);
}
.clip-modal-placeholder .big-emoji { font-size: 4rem; }
.clip-modal-placeholder p { color: var(--muted); font-size: 0.9rem; text-align: center; padding: 0 2rem; }
.clip-modal-placeholder a {
  padding: 0.65rem 1.5rem; background: var(--amber);
  border-radius: 8px; color: var(--bg); font-weight: 700;
  font-size: 0.85rem; transition: background var(--transition);
}
.clip-modal-placeholder a:hover { background: var(--amber2); }
.clip-modal-info { padding: 1.25rem 1.5rem; display: flex; justify-content: space-between; align-items: flex-start; gap: 1rem; }
.clip-modal-title { font-size: 1rem; font-weight: 700; color: var(--white); margin-bottom: 4px; }
.clip-modal-meta { font-size: 0.78rem; color: var(--muted); }
.clip-modal-close {
  flex-shrink: 0; width: 36px; height: 36px; border-radius: 50%;
  background: var(--bg3); border: 1px solid var(--border);
  color: var(--muted); font-size: 1.1rem; cursor: pointer;
  display: flex; align-items: center; justify-content: center;
  transition: all var(--transition);
}
.clip-modal-close:hover { background: var(--red); border-color: var(--red); color: var(--white); }

.clips-more { text-align: center; }
.btn-clips-more {
  display: inline-flex; align-items: center; gap: 0.5rem;
  padding: 0.75rem 2rem; background: var(--bg2);
  border: 1px solid var(--border); border-radius: 50px;
  color: var(--text); font-size: 0.88rem; font-weight: 500;
  transition: all var(--transition);
}
.btn-clips-more:hover {
  border-color: var(--amber); color: var(--amber);
  background: rgba(232,160,32,0.05);
}

@media (max-width: 600px) {
  .clips-grid { grid-template-columns: 1fr 1fr; }
  .notif-banner { flex-direction: column; gap: 0.75rem; }
}
@media (max-width: 400px) {
  .clips-grid { grid-template-columns: 1fr; }
}
