/* ========================================
   RADIO FRATERNITÉ FM MAMOU — APP JS v3
   Tout est piloté par _data/settings.json
   ======================================== */
'use strict';

const $ = (s, c=document) => c.querySelector(s);
const $$ = (s, c=document) => [...c.querySelectorAll(s)];
async function fetchJSON(url) {
  try { const r = await fetch(url+'?v='+Date.now()); return r.ok ? await r.json() : null; }
  catch { return null; }
}

// ════════════════════════════════════════
//  APPLY SETTINGS — cœur du système
// ════════════════════════════════════════
function applySettings(s) {
  if (!s) return;


  // Meta description dynamique
  if (s.site_nom || s.site_tagline) {
    const desc = document.getElementById('pageDesc');
    if (desc) desc.setAttribute('content', `${s.site_nom||'Fraternité FM'} ${s.frequence||'95.0'} MHz — ${s.site_tagline||'Radio en direct, Guinée'}`);
  }
  // CSS Variables dynamiques (couleurs)
  const styleEl = $('#settingsStyle');
  if (styleEl && s.couleur_accent) {
    const c = s.couleur_accent;
    const r = parseInt(c.slice(1,3),16), g = parseInt(c.slice(3,5),16), b = parseInt(c.slice(5,7),16);
    styleEl.textContent = `:root {
      --amber: ${c};
      --amber2: ${adjustColor(c, 30)};
      --amber-glow: rgba(${r},${g},${b},0.15);
    }`;
  }

  // Titre de la page
  const freq = s.frequence || '95.0';
  document.title = `${s.site_nom || 'Fraternité FM'} ${freq} — En Direct`;

  // Hero
  if (s.hero_titre_1)  setText('heroTitle1', s.hero_titre_1);
  if (s.hero_titre_2)  setText('heroTitle2', s.hero_titre_2);
  if (s.site_tagline)  setText('heroTagline', s.site_tagline);
  if (s.frequence) {
    setText('heroFreq', freq + ' MHz');
    setText('playerStation', `${s.site_nom || 'Fraternité FM'} — ${freq} MHz`);
    setText('miniFreq', `${freq} MHz · Mamou`);
    setText('aproposMHz', `${freq} MHz`);
    setText('aproposFreq', `${freq} MHz`);
    setText('footerFreq', `📡 ${freq} MHz — Mamou, Guinée`);
  }

  // Stats héros
  setStatEl('stat1Val', 'stat1Lbl', s.stat_1_val, s.stat_1_lbl);
  setStatEl('stat2Val', 'stat2Lbl', s.stat_2_val, s.stat_2_lbl);
  setStatEl('stat3Val', 'stat3Lbl', s.stat_3_val, s.stat_3_lbl);

  // Logo
  if (s.logo_url) {
    $$('.logo-img').forEach(img => { img.src = s.logo_url; img.style.display = 'block'; });
    $$('.logo-icon, .footer-logo-icon').forEach(el => el.style.display = 'none');
  }

  // Hero background image
  if (s.hero_bg_image) {
    const heroBg = $('#heroBg');
    if (heroBg) {
      let bgImg = heroBg.querySelector('.hero-bg-img');
      if (!bgImg) { bgImg = document.createElement('div'); bgImg.className = 'hero-bg-img'; heroBg.prepend(bgImg); }
      bgImg.style.backgroundImage = `url('${s.hero_bg_image}')`;
    }
  }

  // Navbar
  if (s.site_nom) {
    const nm = s.site_nom.replace(/Radio\s*/i,'').toUpperCase();
    setText('logoMain', nm.length > 20 ? nm.slice(0,20) + '…' : nm);
    setText('miniName', s.site_nom.replace(/Radio\s*/i,''));
    setText('aproposName', nm);
  }

  // Stream audio
  if (s.stream_url) {
    const src = $('#audioSource');
    if (src) src.src = s.stream_url;
  }

  // À propos
  if (s.apropos_texte) setText('aproposTexte', s.apropos_texte);

  // Footer
  if (s.site_nom) setText('footerName', s.site_nom);
  if (s.footer_texte) { setText('footerTagline', s.footer_texte); setText('footerBottomText', s.footer_texte); }


  // Dons : objectif et numéros
  if (s.don_objectif_label) {
    document.querySelectorAll('.don-sub').forEach((el, i) => {
      if (i === 2) el.textContent = s.don_objectif_label;
    });
  }
  if (s.don_objectif_montant && s.don_collecte_actuel) {
    const objectif = parseInt(s.don_objectif_montant);
    const collecte = parseInt(s.don_collecte_actuel);
    const pct = Math.min(100, Math.round((collecte / objectif) * 100));
    const fill = document.getElementById('goalFill');
    if (fill) fill.style.width = pct + '%';
    const pctEl = document.querySelector('.goal-pct');
    if (pctEl) pctEl.textContent = pct + '% atteint';
    const nums = document.querySelectorAll('.goal-nums span');
    if (nums[0]) nums[0].textContent = parseInt(s.don_collecte_actuel).toLocaleString('fr-FR') + ' GNF';
    if (nums[1]) nums[1].textContent = parseInt(s.don_objectif_montant).toLocaleString('fr-FR') + ' GNF';
  }
  if (s.whatsapp_don_numero) {
    document.querySelectorAll('.mm-num').forEach(el => {
      const n = s.whatsapp_don_numero;
      el.textContent = '+' + n.slice(0,3) + ' ' + n.slice(3,6) + ' ' + n.slice(6,9) + ' ' + n.slice(9);
    });
    document.querySelectorAll('.btn-copy-num').forEach(btn => {
      btn.setAttribute('onclick', `copyNum(this,'${s.whatsapp_don_numero}','Mobile Money')`);
    });
  }

  // SEO : mettre à jour schema.org dynamiquement
  if (s.site_url) {
    const schema = document.querySelector('script[type="application/ld+json"]');
    if (schema) {
      try {
        const data = JSON.parse(schema.textContent);
        data.url = s.site_url;
        if (s.site_nom) data.name = s.site_nom;
        if (s.frequence) data.broadcastFrequency.broadcastFrequencyValue = s.frequence;
        schema.textContent = JSON.stringify(data, null, 2);
      } catch(e) {}
    }
    // Canonical
    const canonical = document.querySelector('link[rel="canonical"]');
    if (canonical) canonical.href = s.site_url + '/';
  }
  // Réseaux sociaux
  if (s.facebook_url) {
    setHref('btnFb', s.facebook_url);
    setHref('footerFb', s.facebook_url);
    // Update FB iframe
    const fbFrame = $('#fbFrame');
    if (fbFrame && s.facebook_page_id) {
      fbFrame.src = `https://www.facebook.com/plugins/video.php?href=https%3A%2F%2Fwww.facebook.com%2F${s.facebook_page_id}%2Fvideos%2F&show_text=false&autoplay=0`;
    }
  }
  if (s.whatsapp_numero) {
    const waUrl = `https://wa.me/${s.whatsapp_numero}?text=Bonjour+Fraternité+FM`;
    setHref('btnWa', waUrl); setHref('footerWa', `https://wa.me/${s.whatsapp_numero}`);
  }
  if (s.youtube_channel_id) {
    const ytSrc = `https://www.youtube.com/embed/live_stream?channel=${s.youtube_channel_id}&autoplay=0`;
    const ytFrame = $('#ytFrame'); if (ytFrame) ytFrame.dataset.src = ytSrc;
  }
  if (s.youtube_url) { setHref('btnYt', s.youtube_url); setHref('footerYt', s.youtube_url); setHref('clipsYtLink', s.youtube_url); }

  // Instagram / TikTok (optionnels)
  const socialLinks = $('#socialLinks');
  if (socialLinks) {
    if (s.instagram_url) {
      if (!$('#btnIg')) {
        const a = document.createElement('a'); a.id='btnIg'; a.className='social-btn ig';
        a.target='_blank'; a.rel='noopener'; a.innerHTML='<span>◉</span> Instagram';
        a.href = s.instagram_url; socialLinks.appendChild(a);
      } else { setHref('btnIg', s.instagram_url); }
    }
    if (s.tiktok_url) {
      if (!$('#btnTt')) {
        const a = document.createElement('a'); a.id='btnTt'; a.className='social-btn tt';
        a.target='_blank'; a.rel='noopener'; a.innerHTML='<span>♪</span> TikTok';
        a.href = s.tiktok_url; socialLinks.appendChild(a);
      }
    }
  }

  // Ticker
  if (s.ticker_actif && s.ticker_messages) {
    const wrap = $('#tickerWrap');
    const content = $('#tickerContent');
    if (wrap && content) {
      wrap.style.display = 'flex';
      const msgs = s.ticker_messages.split('|').map(m => m.trim()).filter(Boolean);
      content.textContent = msgs.join('   ·   ') + '   ·   ' + msgs.join('   ·   ');
    }
  }
}

// Helpers
function setText(id, val) { const el = $(('#' + id)); if (el) el.textContent = val; }
function setHref(id, val) { const el = $('#' + id); if (el) el.href = val; }
function setStatEl(valId, lblId, val, lbl) {
  if (val) { const el = $('#'+valId); if (el) { el.dataset.target = val; el.textContent = '0'; } }
  if (lbl) setText(lblId, lbl);
}
function adjustColor(hex, amount) {
  const r = Math.min(255, parseInt(hex.slice(1,3),16)+amount);
  const g = Math.min(255, parseInt(hex.slice(3,5),16)+amount);
  const b = Math.min(255, parseInt(hex.slice(5,7),16)+amount);
  return `#${r.toString(16).padStart(2,'0')}${g.toString(16).padStart(2,'0')}${b.toString(16).padStart(2,'0')}`;
}

// ════════════════════════════════════════
//  LOADING SCREEN
// ════════════════════════════════════════
function showLoadingProgress(pct) {
  const fill = $('#loadingFill');
  if (fill) fill.style.width = pct + '%';
}
function hideLoading() {
  const ls = $('#loadingScreen');
  if (ls) { ls.classList.add('hidden'); setTimeout(() => ls.remove(), 600); }
}

// ════════════════════════════════════════
//  NAVBAR
// ════════════════════════════════════════
const navbar = $('#navbar');
window.addEventListener('scroll', () => {
  navbar.classList.toggle('scrolled', window.scrollY > 40);
  updateMiniPlayer();
}, { passive: true });
const burger = $('#burger'), navLinks = $('#navLinks');
burger.addEventListener('click', () => { burger.classList.toggle('open'); navLinks.classList.toggle('open'); });
$$('.nav-links a').forEach(l => l.addEventListener('click', () => { burger.classList.remove('open'); navLinks.classList.remove('open'); }));

// ════════════════════════════════════════
//  RADIO PLAYER
// ════════════════════════════════════════
const audio = $('#radioAudio'), btnPlay = $('#btnPlay'), waveBars = $('#waveBars'), playerNow = $('#playerNow');
let isPlaying = false;
let PROGRAMMES_DATA = [];
let currentProgramme = null;

function setPlaying(state) {
  isPlaying = state;
  $('#iconPlay').style.display  = state?'none':'block';
  $('#iconPause').style.display = state?'block':'none';
  $('#miniIconPlay').style.display  = state?'none':'block';
  $('#miniIconPause').style.display = state?'block':'none';
  waveBars.classList.toggle('playing', state);
  $('#miniWave').classList.toggle('playing', state);
  if (typeof updateCurrentProgramme === 'function') {
    updateCurrentProgramme();
  } else {
    playerNow.textContent = state ? 'En cours de diffusion…' : 'Cliquez ▶ pour écouter';
  }
}
btnPlay.addEventListener('click', () => {
  if (isPlaying) { audio.pause(); setPlaying(false); }
  else { audio.load(); audio.play().then(()=>setPlaying(true)).catch(()=>{ playerNow.textContent='⚠ Stream momentanément indisponible.'; }); }
});
$('#miniBtnPlay').addEventListener('click', () => btnPlay.click());
$('#volume').addEventListener('input', e => { audio.volume = parseFloat(e.target.value); });
audio.addEventListener('error', () => { setPlaying(false); playerNow.textContent='⚠ Impossible de charger le stream.'; });

// ════════════════════════════════════════
//  MINI PLAYER
// ════════════════════════════════════════
const miniPlayer = $('#miniPlayer'), heroSection = $('#direct');
function updateMiniPlayer() { miniPlayer.classList.toggle('visible', heroSection.getBoundingClientRect().bottom < 0); }

// ════════════════════════════════════════
//  VIDEO TABS
// ════════════════════════════════════════
$$('.vtab').forEach(tab => tab.addEventListener('click', () => {
  $$('.vtab').forEach(t=>t.classList.remove('active')); tab.classList.add('active');
  $$('.video-pane').forEach(p=>p.classList.remove('active')); $(`#tab-${tab.dataset.tab}`).classList.add('active');
}));
$('#loadFb').addEventListener('click', () => { $('#fbOverlay').style.display='none'; });
$('#loadYt').addEventListener('click', () => { const f=$('#ytFrame'); f.src=f.dataset.src; $('#ytOverlay').style.display='none'; });

// ════════════════════════════════════════
//  RENDERERS
// ════════════════════════════════════════
function renderProgrammes(data) {
  const grid = $('#progGrid');
  const sorted = [...data].sort((a,b)=>(a.ordre||0)-(b.ordre||0));
  grid.innerHTML = sorted.map(p=>`
    <div class="prog-card">
      <div class="prog-time">${p.heure_debut} – ${p.heure_fin}</div>
      <div class="prog-name">${p.nom_emission}</div>
      <div class="prog-host">Animé par ${p.animateur}</div>
      <span class="prog-tag ${p.live_video?'live':''}">${p.live_video?'🔴 Live vidéo':p.tag}</span>
    </div>`).join('');
}

function parseTimeToMinutes(str) {
  if (!str || typeof str !== 'string') return NaN;
  const [h, m] = str.split(':').map(v => parseInt(v, 10));
  if (Number.isNaN(h) || Number.isNaN(m)) return NaN;
  return h * 60 + m;
}

function getCurrentProgramme(now = new Date()) {
  if (!PROGRAMMES_DATA || !PROGRAMMES_DATA.length) return null;
  const minutesNow = now.getHours() * 60 + now.getMinutes();
  // On parcourt dans l'ordre d'affichage
  for (const p of PROGRAMMES_DATA) {
    const start = parseTimeToMinutes(p.heure_debut);
    const end   = parseTimeToMinutes(p.heure_fin);
    if (Number.isNaN(start) || Number.isNaN(end)) continue;
    if (minutesNow >= start && minutesNow < end) return p;
  }
  return null;
}

function updateCurrentProgramme() {
  if (!playerNow) return;
  currentProgramme = getCurrentProgramme();
  if (isPlaying) {
    if (currentProgramme) {
      playerNow.textContent = `En direct : ${currentProgramme.nom_emission} (${currentProgramme.heure_debut} – ${currentProgramme.heure_fin})`;
    } else {
      playerNow.textContent = 'En cours de diffusion…';
    }
  } else {
    if (currentProgramme) {
      playerNow.textContent = `En ce moment : ${currentProgramme.nom_emission} — ${currentProgramme.animateur}`;
    } else {
      playerNow.textContent = 'Cliquez ▶ pour écouter';
    }
  }
}

function startProgrammeWatcher() {
  updateCurrentProgramme();
  // Mise à jour toutes les 60 secondes
  setInterval(updateCurrentProgramme, 60000);
}

function renderNews(data) {
  const grid = $('#newsGrid');
  const sorted = [...data].slice(0, 9);
  grid.innerHTML = sorted.map(n=>`
    <div class="news-card">
      <div class="news-img">${n.emoji||'📰'}</div>
      <div class="news-body">
        <div class="news-cat">${n.categorie||n.cat||''}</div>
        <div class="news-title">${n.title}</div>
        <div class="news-excerpt">${n.excerpt}</div>
        <div class="news-date">${n.date}</div>
      </div>
    </div>`).join('');
}

function renderTeam(data) {
  const grid = $('#teamGrid'); if (!grid) return;
  const sorted = [...data].sort((a,b)=>(a.ordre||0)-(b.ordre||0));
  grid.innerHTML = sorted.map(m=>`
    <div class="team-card">
      <div class="team-avatar" style="background:${m.couleur}22;border-color:${m.couleur}44">
        ${m.photo ? `<img src="${m.photo}" alt="${m.nom}"/>` : `<span class="team-initiales" style="color:${m.couleur}">${m.initiales}</span>`}
      </div>
      <div class="team-info">
        <div class="team-nom">${m.nom}</div>
        <div class="team-poste" style="color:${m.couleur}">${m.poste}</div>
        <p class="team-desc">${m.bio}</p>
      </div>
    </div>`).join('');
}

// ════════════════════════════════════════
//  COUNTER ANIMATION
// ════════════════════════════════════════
function animateCounters() {
  const obs = new IntersectionObserver(entries => entries.forEach(e => {
    if (!e.isIntersecting) return;
    const el = e.target, target = parseInt(el.dataset.target, 10);
    if (isNaN(target)) return;
    let cur=0; const step=Math.ceil(target/40);
    const t=setInterval(()=>{ cur=Math.min(cur+step,target); el.textContent=cur; if(cur>=target)clearInterval(t); },40);
    obs.unobserve(el);
  }), {threshold:0.5});
  $$('.stat-num').forEach(n=>obs.observe(n));
}

// ════════════════════════════════════════
//  DÉDICACE FORM
// ════════════════════════════════════════
$('#dedicaceForm').addEventListener('submit', e => {
  e.preventDefault();
  const d = new FormData(e.target);
  // Récupérer le bon numéro depuis le DOM (mis à jour par applySettings)
  const waLink = $('#btnWa');
  const num = waLink ? new URL(waLink.href).pathname.slice(1) : '224629020259';
  const text = encodeURIComponent(
    `🎵 Dédicace de ${d.get('prenom')} à ${d.get('destinataire')}` +
    (d.get('chanson')?`\nChanson: ${d.get('chanson')}`:'') +
    (d.get('message')?`\nMessage: ${d.get('message')}`:'') +
    `\n\n— Envoyé via le site de Fraternité FM`
  );
  window.open(`https://wa.me/${num}?text=${text}`, '_blank');
  e.target.reset();
  const s=$('#formSuccess'); s.style.display='block';
  setTimeout(()=>{ s.style.display='none'; },6000);
});

// ════════════════════════════════════════
//  SCROLL REVEAL
// ════════════════════════════════════════
function initScrollReveal() {
  const els = $$('.prog-card,.news-card,.team-card,.section-title,.section-desc,.section-label,.apropos-badge');
  const obs = new IntersectionObserver(entries => entries.forEach(e => {
    if (e.isIntersecting) { e.target.style.opacity='1'; e.target.style.transform='translateY(0)'; obs.unobserve(e.target); }
  }), {threshold:0.1});
  els.forEach((el,i) => {
    el.style.opacity='0'; el.style.transform='translateY(22px)';
    el.style.transition=`opacity 0.55s ${i*0.035}s ease,transform 0.55s ${i*0.035}s ease`;
    obs.observe(el);
  });
}

// ════════════════════════════════════════
//  FALLBACK DATA
// ════════════════════════════════════════
const FB_NEWS=[
  {categorie:'Économie',   title:'Le marché de Mamou en plein essor',                 excerpt:'La ville de Mamou attire de nouveaux investisseurs grâce à sa position stratégique au carrefour de la Moyenne Guinée.',    date:'15 mars 2026',emoji:'📈'},
  {categorie:'Culture',    title:'Festival de musique Pular 2026 annoncé à Labé',     excerpt:'Le grand festival de la culture Peul revient avec plus de 50 artistes de la sous-région.',                                date:'13 mars 2026',emoji:'🎵'},
  {categorie:'Santé',      title:'10.000 enfants vaccinés en Moyenne Guinée',          excerpt:'Le ministère de la Santé atteint un taux de couverture record dans les préfectures de Mamou, Dalaba et Pita.',            date:'10 mars 2026',emoji:'💉'},
  {categorie:'Agriculture',title:'Bonne récolte de pommes de terre à Dalaba',         excerpt:'Les agriculteurs de Dalaba annoncent une production record cette saison.',                                                   date:'8 mars 2026', emoji:'🥔'},
  {categorie:'Éducation',  title:'Ouverture d\'un lycée technique à Mamou',           excerpt:'Le gouvernement guinéen inaugure un lycée technique moderne pour former les jeunes.',                                       date:'5 mars 2026', emoji:'🏫'},
  {categorie:'Sport',      title:'Tournoi de football : Mamou en finale',             excerpt:'L\'équipe de football de Mamou se qualifie pour la grande finale régionale.',                                              date:'2 mars 2026', emoji:'⚽'},
];
const FB_PROGS=[
  {heure_debut:'06:00',heure_fin:'08:00',nom_emission:'Réveil Fraternité', animateur:'Animateur du matin',   tag:'Matinale',      live_video:false,ordre:1},
  {heure_debut:'08:00',heure_fin:'10:00',nom_emission:'Journal du Matin',  animateur:'Rédaction FM',         tag:'Information',   live_video:true, ordre:2},
  {heure_debut:'10:00',heure_fin:'12:00',nom_emission:'Matin Détente',     animateur:'Animateur Musical',    tag:'Musique',       live_video:false,ordre:3},
  {heure_debut:'12:00',heure_fin:'13:00',nom_emission:'Flash Info Midi',   animateur:'Rédaction FM',         tag:'Information',   live_video:true, ordre:4},
  {heure_debut:'13:00',heure_fin:'15:00',nom_emission:'Carrefour Culturel',animateur:'Rubrique Culture',     tag:'Culture Pular', live_video:false,ordre:5},
  {heure_debut:'17:00',heure_fin:'19:00',nom_emission:'Débat du Soir',     animateur:'Équipe Fraternité FM', tag:'Débat',         live_video:true, ordre:6},
  {heure_debut:'19:00',heure_fin:'21:00',nom_emission:'Soirée Fraternité', animateur:'Équipe Fraternité FM', tag:'Magazine',      live_video:true, ordre:7},
];
const FB_TEAM=[
  {nom:'M. Sidi Diallo',            poste:'Président Directeur Général',initiales:'SD', couleur:'#e8a020',ordre:1,bio:'Fondateur et visionnaire de Fraternité FM, M. Sidi Diallo pilote la stratégie et le développement de la radio. Vice-maire de Mamou, il incarne l\'ancrage profond de la station dans la vie de la communauté.'},
  {nom:'M. Sadou Diallo',           poste:'Directeur Général',          initiales:'SAD',couleur:'#3b82f6',ordre:2,bio:'M. Sadou Diallo assure la gestion quotidienne de la station et coordonne les équipes pour diffuser des programmes de qualité sur les ondes de la Moyenne Guinée.'},
  {nom:'M. Lougmane Diallo',        poste:'Rédacteur en Chef',          initiales:'LD', couleur:'#22c55e',ordre:3,bio:'Garant de la ligne éditoriale, M. Lougmane Diallo supervise l\'ensemble de la production journalistique et assure la rigueur de l\'information diffusée.'},
  {nom:'Mme Fatoumata Binta Keita', poste:'Responsable Technique',      initiales:'FBK',couleur:'#e03060',ordre:4,bio:'Mme Fatoumata Binta Keita garantit la qualité du signal FM et du streaming en ligne, supervisant le matériel de diffusion et la continuité de service 24h/24.'},
];

// ════════════════════════════════════════
//  INIT
// ════════════════════════════════════════
async function init() {
  showLoadingProgress(10);

  // 1. Charger les paramètres
  const settings = await fetchJSON('/_data/settings.json');
  showLoadingProgress(30);
  applySettings(settings);
  showLoadingProgress(50);

  // 2. Charger les données
  const [artIdx, progIdx, teamIdx] = await Promise.all([
    fetchJSON('/_data/articles/index.json'),
    fetchJSON('/_data/programmes/index.json'),
    fetchJSON('/_data/equipe/index.json'),
  ]);
  showLoadingProgress(70);

  if (artIdx) { const d=await Promise.all(artIdx.map(f=>fetchJSON(`/_data/articles/${f}`))); renderNews(d.filter(Boolean)); }
  else renderNews(FB_NEWS);

  if (progIdx) {
    const d = await Promise.all(progIdx.map(f => fetchJSON(`/_data/programmes/${f}`)));
    PROGRAMMES_DATA = d.filter(Boolean);
    renderProgrammes(PROGRAMMES_DATA);
  } else {
    PROGRAMMES_DATA = FB_PROGS;
    renderProgrammes(FB_PROGS);
  }

  if (teamIdx) { const d=await Promise.all(teamIdx.map(f=>fetchJSON(`/_data/equipe/${f}`))); renderTeam(d.filter(Boolean)); }
  else renderTeam(FB_TEAM);

  // Clips
  const clipsIdx = await fetchJSON('/_data/clips/index.json');
  if (clipsIdx) {
    const clips = await Promise.all(clipsIdx.map(f => fetchJSON(`/_data/clips/${f}`)));
    renderClips(clips.filter(Boolean));
  } else {
    renderClips([
      {titre:'Débat : L\'eau potable à Mamou', categorie:'Politique', duree:'2:45', date:'14 mars 2026', youtube_id:'', description:'Extrait de l\'émission Débat du Soir.', emoji:'💧', ordre:1},
      {titre:'Festival Pular 2026 : les artistes se confient', categorie:'Culture', duree:'3:12', date:'12 mars 2026', youtube_id:'', description:'Rencontre exclusive avec les artistes du festival.', emoji:'🎵', ordre:2},
      {titre:'Reportage : Le marché de Mamou en mutation', categorie:'Économie', duree:'1:58', date:'10 mars 2026', youtube_id:'', description:'Nos journalistes au cœur du marché central.', emoji:'📈', ordre:3},
      {titre:'Journal du Matin — Revue de presse', categorie:'Information', duree:'4:30', date:'8 mars 2026', youtube_id:'', description:'La revue de presse complète de la Moyenne Guinée.', emoji:'📰', ordre:4},
    ]);
  }

  showLoadingProgress(100);
  $('#footerYear').textContent = new Date().getFullYear();
  animateCounters();
  initNotifications();
  startProgrammeWatcher();

  // 3. Masquer le loading et révéler le site
  setTimeout(() => {
    hideLoading();
    requestAnimationFrame(() => setTimeout(initScrollReveal, 200));
  }, 400);
}


// ════════════════════════════════════════
//  CLIPS VIDÉO
// ════════════════════════════════════════
function renderClips(data) {
  const grid = document.getElementById('clipsGrid');
  if (!grid) return;
  const sorted = [...data].sort((a,b) => (a.ordre||0)-(b.ordre||0));
  grid.innerHTML = sorted.map((c,i) => `
    <div class="clip-card" onclick="openClipModal(${i})" data-idx="${i}">
      <div class="clip-thumb">
        <div class="clip-thumb-inner">
          <span class="clip-thumb-emoji">${c.emoji||'📹'}</span>
        </div>
        <div class="clip-play-btn">
          <div class="clip-play-icon">▶</div>
        </div>
        ${c.duree ? `<span class="clip-duree">${c.duree}</span>` : ''}
      </div>
      <div class="clip-body">
        <div class="clip-cat">${c.categorie||''}</div>
        <div class="clip-titre">${c.titre||c.title||''}</div>
        <div class="clip-desc">${c.description||''}</div>
        <div class="clip-date">${c.date||''}</div>
      </div>
    </div>`).join('');
  // Store data globally for modal
  window._clipsData = sorted;
}

// Modal clips
(function buildModal() {
  const modal = document.createElement('div');
  modal.className = 'clip-modal'; modal.id = 'clipModal';
  modal.innerHTML = `
    <div class="clip-modal-inner">
      <div class="clip-modal-video" id="clipModalVideo"></div>
      <div class="clip-modal-info">
        <div><div class="clip-modal-title" id="clipModalTitle"></div>
             <div class="clip-modal-meta"  id="clipModalMeta"></div></div>
        <button class="clip-modal-close" onclick="closeClipModal()">✕</button>
      </div>
    </div>`;
  modal.addEventListener('click', e => { if (e.target === modal) closeClipModal(); });
  document.body.appendChild(modal);
})();

function openClipModal(idx) {
  const data = window._clipsData;
  if (!data || !data[idx]) return;
  const clip = data[idx];
  const modal = document.getElementById('clipModal');
  const videoEl = document.getElementById('clipModalVideo');
  document.getElementById('clipModalTitle').textContent = clip.titre || clip.title || '';
  document.getElementById('clipModalMeta').textContent = (clip.categorie||'') + (clip.date ? ' · ' + clip.date : '') + (clip.duree ? ' · ' + clip.duree : '');
  if (clip.youtube_id && clip.youtube_id.trim()) {
    videoEl.innerHTML = `<iframe src="https://www.youtube.com/embed/${clip.youtube_id}?autoplay=1" allowfullscreen allow="autoplay; encrypted-media"></iframe>`;
  } else {
    videoEl.innerHTML = `
      <div class="clip-modal-placeholder">
        <span class="big-emoji">${clip.emoji||'📹'}</span>
        <p>${clip.description||'Clip vidéo — ajoutez l\'ID YouTube dans le CMS pour l\'activer.'}</p>
        <a href="https://www.youtube.com/channel/UCJIFBiOGN3o-gFMPqQhagPA" target="_blank" rel="noopener">Voir sur YouTube ▶</a>
      </div>`;
  }
  modal.classList.add('open');
  document.body.style.overflow = 'hidden';
}

function closeClipModal() {
  const modal = document.getElementById('clipModal');
  modal.classList.remove('open');
  document.getElementById('clipModalVideo').innerHTML = '';
  document.body.style.overflow = '';
}
document.addEventListener('keydown', e => { if (e.key === 'Escape') closeClipModal(); });

// ════════════════════════════════════════
//  NOTIFICATIONS PUSH (OneSignal)
// ════════════════════════════════════════
function initNotifications() {
  // Afficher le bandeau après 8 secondes si pas encore accepté/refusé
  const dismissed = localStorage.getItem('ffm_notif_dismissed');
  if (dismissed) return;

  setTimeout(() => {
    const banner = document.getElementById('notifBanner');
    if (banner) banner.style.display = 'flex';
  }, 8000);

  const btnYes = document.getElementById('btnNotifYes');
  const btnNo  = document.getElementById('btnNotifNo');

  if (btnYes) {
    btnYes.addEventListener('click', async () => {
      document.getElementById('notifBanner').style.display = 'none';
      localStorage.setItem('ffm_notif_dismissed', '1');
      // Déclencher la demande de permission OneSignal
      try {
        if (window.OneSignalDeferred) {
          window.OneSignalDeferred.push(async (OneSignal) => {
            await OneSignal.Notifications.requestPermission();
          });
        } else {
          // Fallback natif
          const perm = await Notification.requestPermission();
          if (perm === 'granted') showToastNotif('🔔 Notifications activées ! Vous serez alerté en direct.');
        }
      } catch(e) { console.log('Notifications non supportées'); }
    });
  }
  if (btnNo) {
    btnNo.addEventListener('click', () => {
      document.getElementById('notifBanner').style.display = 'none';
      localStorage.setItem('ffm_notif_dismissed', '1');
    });
  }
}

function showToastNotif(msg) {
  const t = document.createElement('div');
  t.style.cssText = 'position:fixed;bottom:5rem;right:1.5rem;z-index:9999;padding:.85rem 1.25rem;background:rgba(34,197,94,0.15);border:1px solid rgba(34,197,94,0.4);color:#22c55e;border-radius:12px;font-size:.85rem;font-weight:500;animation:slideIn .3s ease;max-width:280px';
  t.textContent = msg;
  document.body.appendChild(t);
  setTimeout(() => t.remove(), 4000);
}

// Expose globally for onclick
window.openClipModal = openClipModal;
window.closeClipModal = closeClipModal;
window.copyNum = copyNum;
window.selectAmount = selectAmount;

document.addEventListener('DOMContentLoaded', init);
document.addEventListener('DOMContentLoaded', animateGoalBar);

// ════════════════════════════════════════
//  DONS MOBILE MONEY
// ════════════════════════════════════════
let selectedAmount = '20000';

function selectAmount(el, amount) {
  selectedAmount = amount;
  document.querySelectorAll('.don-amount').forEach(d => d.classList.remove('active'));
  el.classList.add('active');
}

function copyNum(btn, num, label) {
  navigator.clipboard.writeText(num).catch(() => {
    const ta = document.createElement('textarea');
    ta.value = num; document.body.appendChild(ta); ta.select();
    document.execCommand('copy'); document.body.removeChild(ta);
  });
  btn.textContent = '✅ Copié !';
  btn.classList.add('copied');
  setTimeout(() => { btn.textContent = 'Copier'; btn.classList.remove('copied'); }, 2000);
}

// Bouton don WhatsApp
const btnDonWa = document.getElementById('btnDonWa');
if (btnDonWa) {
  btnDonWa.addEventListener('click', () => {
    const waBtn = document.getElementById('btnWa');
    const num = waBtn ? new URL(waBtn.href).pathname.slice(1) : '224629020259';
    const montant = selectedAmount
      ? parseInt(selectedAmount).toLocaleString('fr-FR') + ' GNF'
      : 'montant libre';
    const text = encodeURIComponent(
      `🎙️ Bonjour Fraternité FM !\n\nJe souhaite faire un don de ${montant} pour soutenir la radio.\n\nMon nom : …\n\n— Envoyé depuis FraterniteFM.com`
    );
    window.open(`https://wa.me/${num}?text=${text}`, '_blank');
  });
}

// Animation barre de progression des dons
function animateGoalBar() {
  const fill = document.getElementById('goalFill');
  if (!fill) return;
  const obs = new IntersectionObserver(entries => {
    entries.forEach(e => {
      if (e.isIntersecting) {
        setTimeout(() => {
          fill.style.width = fill.style.width || '35%';
        }, 300);
        obs.unobserve(e.target);
      }
    });
  }, { threshold: 0.3 });
  obs.observe(fill);
}

// ════════════════════════════════════════
//  FORMULAIRE SPONSORS
// ════════════════════════════════════════
const sponsorForm = document.getElementById('sponsorForm');
if (sponsorForm) {
  sponsorForm.addEventListener('submit', e => {
    e.preventDefault();
    const d = new FormData(e.target);
    const waBtn = document.getElementById('btnWa');
    const num = waBtn ? new URL(waBtn.href).pathname.slice(1) : '224629020259';
    const text = encodeURIComponent(
      `📋 Demande de partenariat — Fraternité FM\n\n` +
      `Entreprise : ${d.get('entreprise')}\n` +
      `Contact : ${d.get('contact')}\n` +
      `Téléphone : ${d.get('telephone')}\n` +
      `Package souhaité : ${d.get('pack')}\n` +
      (d.get('message') ? `\nMessage : ${d.get('message')}` : '') +
      `\n\n— Via FraterniteFM.com`
    );
    window.open(`https://wa.me/${num}?text=${text}`, '_blank');
    e.target.reset();
    const s = document.getElementById('sponsorSuccess');
    if (s) { s.style.display = 'block'; setTimeout(() => s.style.display = 'none', 6000); }
  });
}
