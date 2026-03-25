---
theme: default
background: ""
class: text-center
highlighter: shiki
lineNumbers: false
info: |
  ## Hack4Innovation Bicocca
  Pipeline automatizzata per la valutazione CV con AI
drawings:
  persist: false
transition: slide-left
title: Hack4Innovation Bicocca — Whattadata
---

<style>
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800;900&display=swap');

:root {
  --bg: #f8fafc;
  --card: #ffffff;
  --sidebar: #0f172a;
  --indigo: #4f46e5;
  --indigo-light: #e0e7ff;
  --slate-900: #0f172a;
  --slate-700: #334155;
  --slate-500: #64748b;
  --slate-300: #cbd5e1;
  --slate-100: #f1f5f9;
  --emerald: #10b981;
  --amber: #f59e0b;
  --red: #ef4444;
  --blue: #3b82f6;
}

.slidev-layout {
  font-family: 'Inter', sans-serif !important;
}

/* ─── HERO ─── */
.hero-bg {
  position: absolute;
  inset: 0;
  background: var(--sidebar);
  overflow: hidden;
}

.hero-bg::before {
  content: '';
  position: absolute;
  width: 500px;
  height: 500px;
  background: radial-gradient(circle, rgba(79,70,229,0.18) 0%, transparent 70%);
  top: -80px;
  right: -80px;
}

.hero-bg::after {
  content: '';
  position: absolute;
  width: 400px;
  height: 400px;
  background: radial-gradient(circle, rgba(16,185,129,0.10) 0%, transparent 70%);
  bottom: -120px;
  left: -40px;
}

@keyframes fade-in {
  from { opacity: 0; transform: translateY(16px); }
  to { opacity: 1; transform: translateY(0); }
}

.hero-title {
  font-size: 3.2rem;
  font-weight: 800;
  letter-spacing: -0.03em;
  line-height: 1.1;
  color: #ffffff;
  animation: fade-in 0.8s ease-out;
}

.hero-title span {
  color: var(--indigo);
  background: none;
  -webkit-text-fill-color: #818cf8;
}

.hero-subtitle {
  font-size: 0.8rem;
  font-weight: 600;
  color: var(--slate-500);
  letter-spacing: 0.18em;
  text-transform: uppercase;
  animation: fade-in 0.8s ease-out 0.2s both;
}

.hero-desc {
  font-size: 1.05rem;
  color: rgba(255,255,255,0.55);
  max-width: 520px;
  text-align: center;
  line-height: 1.6;
  animation: fade-in 0.8s ease-out 0.35s both;
}

.hero-badge {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 10px 24px;
  border-radius: 12px;
  background: var(--indigo);
  color: #fff;
  font-weight: 600;
  font-size: 0.85rem;
  animation: fade-in 0.8s ease-out 0.55s both;
  cursor: pointer;
  transition: all 0.2s ease;
}

.hero-badge:hover {
  background: #4338ca;
  transform: translateY(-2px);
  box-shadow: 0 8px 24px rgba(79,70,229,0.35);
}

/* ─── SHARED ─── */
.light-slide {
  position: absolute;
  inset: 0;
  background: var(--bg);
}

.dark-slide {
  position: absolute;
  inset: 0;
  background: var(--sidebar);
}

.slide-label {
  font-size: 0.7rem;
  font-weight: 700;
  letter-spacing: 0.2em;
  text-transform: uppercase;
  color: var(--indigo);
  display: inline-flex;
  align-items: center;
  gap: 6px;
}

.slide-label::before {
  content: '';
  width: 18px;
  height: 2px;
  background: var(--indigo);
  border-radius: 2px;
}

.slide-title {
  font-size: 2rem;
  font-weight: 800;
  letter-spacing: -0.02em;
  color: var(--slate-900);
  margin-top: 4px;
}

.slide-title-white {
  font-size: 2rem;
  font-weight: 800;
  letter-spacing: -0.02em;
  color: #fff;
  margin-top: 4px;
}

/* ─── PROBLEM CARDS (LIGHT) ─── */
.problem-card {
  background: var(--card);
  border: 1px solid #e2e8f0;
  border-radius: 14px;
  padding: 14px 16px;
  transition: all 0.25s ease;
  position: relative;
}

.problem-card:hover {
  transform: translateY(-3px);
  box-shadow: 0 8px 24px rgba(0,0,0,0.06);
  border-color: var(--indigo);
}

.problem-icon {
  width: 34px;
  height: 34px;
  border-radius: 10px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1rem;
  flex-shrink: 0;
}

.problem-card h3 {
  font-size: 0.88rem;
  font-weight: 700;
  color: var(--slate-900);
  margin: 0;
}

.problem-card p {
  font-size: 0.72rem;
  color: var(--slate-500);
  line-height: 1.45;
  margin-top: 4px;
}

/* ─── STAT BANNER ─── */
.stat-banner {
  display: flex;
  gap: 10px;
  margin-top: 8px;
}

.stat-item {
  background: var(--card);
  border: 1px solid #e2e8f0;
  border-radius: 10px;
  padding: 10px 16px;
  text-align: center;
  flex: 1;
}

.stat-item .num {
  font-size: 1.3rem;
  font-weight: 800;
  color: var(--slate-900);
}

.stat-item .lbl {
  font-size: 0.62rem;
  color: var(--slate-500);
  margin-top: 1px;
}

/* ─── PIPELINE STEPS ─── */
.pipeline-step {
  display: flex;
  align-items: center;
  gap: 14px;
  padding: 14px 18px;
  border-radius: 14px;
  background: var(--card);
  border: 1px solid #e2e8f0;
  transition: all 0.25s ease;
}

.pipeline-step:hover {
  border-color: var(--indigo);
  transform: translateX(4px);
  box-shadow: 0 4px 16px rgba(0,0,0,0.04);
}

.step-number {
  width: 38px;
  height: 38px;
  border-radius: 10px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 0.8rem;
  font-weight: 800;
  color: #fff;
  flex-shrink: 0;
  background: var(--indigo);
}

.step-content h4 {
  font-size: 0.88rem;
  font-weight: 700;
  color: var(--slate-900);
  margin: 0 0 2px 0;
}

.step-content p {
  font-size: 0.72rem;
  color: var(--slate-500);
  margin: 0;
  line-height: 1.35;
}

/* ─── TECH STACK ─── */
.tech-stack-card {
  display: flex;
  align-items: center;
  gap: 20px;
  padding: 10px 20px;
  background: var(--card);
  border: 1px solid #e2e8f0;
  border-radius: 14px;
  width: fit-content;
  margin: 10px 0 16px 0;
}

.tech-logo {
  height: 44px;
  width: 44px;
  object-fit: contain;
  border-radius: 8px;
}

/* ─── OUTPUT CARDS ─── */
.output-card {
  background: var(--card);
  border: 1px solid #e2e8f0;
  border-radius: 16px;
  padding: 20px;
  transition: all 0.25s ease;
}

.output-card:hover {
  transform: translateY(-3px);
  box-shadow: 0 8px 24px rgba(0,0,0,0.06);
}

.output-card h3 {
  font-size: 1rem;
  font-weight: 700;
  color: var(--slate-900);
  margin: 0 0 6px 0;
}

.output-card p {
  font-size: 0.75rem;
  color: var(--slate-500);
  line-height: 1.55;
}

.output-icon {
  width: 42px;
  height: 42px;
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.2rem;
  flex-shrink: 0;
}

/* ─── VALUE CARDS ─── */
.value-card {
  text-align: center;
  padding: 24px 16px;
  border-radius: 16px;
  background: rgba(255,255,255,0.06);
  border: 1px solid rgba(255,255,255,0.08);
  transition: all 0.25s ease;
}

.value-card:hover {
  transform: translateY(-4px);
  background: rgba(255,255,255,0.10);
  box-shadow: 0 12px 32px rgba(0,0,0,0.3);
}

.value-number {
  font-size: 2.6rem;
  font-weight: 900;
  letter-spacing: -0.04em;
  line-height: 1;
  margin-bottom: 8px;
  color: #818cf8;
}

.value-label {
  font-size: 0.85rem;
  font-weight: 700;
  color: #fff;
  margin-bottom: 4px;
}

.value-desc {
  font-size: 0.68rem;
  color: rgba(255,255,255,0.45);
  line-height: 1.45;
}

/* ─── FUTURE CARDS ─── */
.future-card {
  padding: 18px;
  border-radius: 16px;
  background: rgba(255,255,255,0.05);
  border: 1px solid rgba(255,255,255,0.08);
  transition: all 0.25s ease;
}

.future-card:hover {
  transform: translateY(-3px);
  background: rgba(255,255,255,0.09);
  box-shadow: 0 12px 32px rgba(0,0,0,0.25);
}

.future-icon {
  width: 40px;
  height: 40px;
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.15rem;
  flex-shrink: 0;
}

.future-card h3 {
  font-size: 0.95rem;
  font-weight: 700;
  color: #fff;
  margin: 0;
}

.future-card p {
  font-size: 0.72rem;
  color: rgba(255,255,255,0.45);
  line-height: 1.5;
}

/* ─── THANK YOU ─── */
.thankyou-bg {
  position: absolute;
  inset: 0;
  background: var(--sidebar);
  overflow: hidden;
}

.thankyou-bg::before {
  content: '';
  position: absolute;
  width: 600px;
  height: 600px;
  background: radial-gradient(circle, rgba(79,70,229,0.12) 0%, transparent 70%);
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

.thankyou-title {
  font-size: 3.6rem;
  font-weight: 900;
  letter-spacing: -0.03em;
  color: #ffffff;
}

.thankyou-title span {
  color: #818cf8;
}

.contact-pill {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 8px 18px;
  border-radius: 10px;
  background: rgba(255,255,255,0.06);
  border: 1px solid rgba(255,255,255,0.1);
  color: rgba(255,255,255,0.65);
  font-size: 0.8rem;
  font-weight: 500;
  transition: all 0.2s ease;
}

.contact-pill:hover {
  background: rgba(79,70,229,0.15);
  border-color: rgba(79,70,229,0.3);
  color: #818cf8;
}

/* ─── OTHER ─── */
.feature-tag {
  display: inline-flex;
  align-items: center;
  gap: 4px;
  padding: 4px 10px;
  border-radius: 6px;
  font-size: 0.65rem;
  font-weight: 600;
  background: var(--indigo-light);
  color: var(--indigo);
}

.slidev-page-number {
  color: var(--slate-300) !important;
}
</style>

<!-- SLIDE 1: HERO -->
<div class="hero-bg"></div>

<div class="relative z-10 flex flex-col items-center justify-center h-full gap-6">
  <div class="hero-subtitle">Hack4Innovation Bicocca · 27 Marzo 2026</div>

  <h1 class="hero-title">Pipeline AI per<br/>la <span>Talent Acquisition</span></h1>

  <p class="hero-desc">
    Da email a candidate scoring in pochi minuti.<br/>
    Zero intervento manuale, dati strutturati, decisioni data-driven.
  </p>

<span class="hero-badge" @click="$slidev.nav.next">
Scopri la Pipeline →
</span>

</div>

---

<!-- SLIDE 2: IL PROBLEMA -->
<div class="light-slide" transition="slide-up"></div>

<div class="relative z-10 px-14 py-6 h-full flex flex-col">
  <div class="mb-2">
    <span class="slide-label">Il problema</span>
    <h2 class="slide-title" style="font-size: 1.8rem;">Lo screening CV è un collo di bottiglia</h2>
  </div>
  <div class="grid grid-cols-2 gap-3 flex-1">
    <div class="problem-card" v-click>
      <div class="flex items-center gap-3 mb-1">
        <div class="problem-icon" style="background: #fef3c7;">⏱️</div>
        <h3>Gestione manuale e isolata</h3>
      </div>
      <p>I recruiter devono gestire singoli allegati email e task ripetitivi, sottraendo tempo ad attività ad alto valore (colloqui).</p>
    </div>
    <div class="problem-card" v-click>
      <div class="flex items-center gap-3 mb-1">
        <div class="problem-icon" style="background: #fce7f3;">⚖️</div>
        <h3>Valutazioni soggettive</h3>
      </div>
      <p>La mancanza di standard e i bias cognitivi portano a criticità nella qualità delle decisioni e allo scarto di candidati validi.</p>
    </div>
    <div class="problem-card" v-click>
      <div class="flex items-center gap-3 mb-1">
        <div class="problem-icon" style="background: #e0e7ff;">💎</div>
        <h3>Perdita di talenti validi</h3>
      </div>
      <p>L'incapacità di processare dati disomogenei e i lunghi tempi di risposta portano a scartare o perdere i migliori profili già presenti nel database.</p>
    </div>
    <div class="problem-card" v-click>
      <div class="flex items-center gap-3 mb-1">
        <div class="problem-icon" style="background: #d1fae5;">📊</div>
        <h3>Inefficienza operativa</h3>
      </div>
      <p>Passaggi manuali tra tool diversi aumentano il rischio di errori e impediscono di tracciare KPI reali del processo.</p>
    </div>
  </div>
  <div class="stat-banner">
    <div class="stat-item">
      <div class="num" style="color: var(--indigo);">23h</div>
      <div class="lbl">Tempo revisione / settimana</div>
    </div>
    <div class="stat-item">
      <div class="num" style="color: var(--amber);">40%</div>
      <div class="lbl">CV non valutati in tempo</div>
    </div>
    <div class="stat-item">
      <div class="num" style="color: var(--red);">0</div>
      <div class="lbl">KPI tracciati real-time</div>
    </div>
  </div>
</div>

---

<!-- SLIDE 3: LA SOLUZIONE — PIPELINE -->
<div class="light-slide" transition="slide-up"></div>

<div class="relative z-10 px-14 py-8 h-full flex flex-col">
  <div class="mb-1">
    <span class="slide-label">La soluzione</span>
    <h2 class="slide-title">Pipeline automatizzata end-to-end</h2>
    <div class="tech-stack-card">
      <img src="./img/n8n.png" class="tech-logo" title="n8n" />
      <img src="./img/oai.png" class="tech-logo" title="OpenAI GPT-5" />
      <img src="./img/sheets.png" class="tech-logo" title="Google Sheets" />
      <img src="./img/slack.png" class="tech-logo" title="Slack" />
    </div>
  </div>

  <div class="grid grid-cols-2 gap-4 flex-1">
    <div class="pipeline-step" v-click>
      <div class="step-number">01</div>
      <div class="step-content">
        <h4>Ingestion Email</h4>
        <p>Gmail trigger automatico ogni 4h — scarica email con allegati non lette</p>
      </div>
    </div>
    <div class="pipeline-step" v-click>
      <div class="step-number" style="background: #7c3aed;">02</div>
      <div class="step-content">
        <h4>Smart File Routing</h4>
        <p>Classificazione automatica allegati → CV, Portfolio, Altro su Google Drive</p>
      </div>
    </div>
    <div class="pipeline-step" v-click>
      <div class="step-number" style="background: #0ea5e9;">03</div>
      <div class="step-content">
        <h4>AI Extraction + Scoring</h4>
        <p>GPT-5 estrae dati anagrafici e valuta il CV su metriche fornite dall'azienda tramite prompt.</p>
      </div>
    </div>
    <div class="pipeline-step" v-click>
      <div class="step-number" style="background: var(--emerald);">04</div>
      <div class="step-content">
        <h4>Output strutturato</h4>
        <p>Popolamento automatico Google Sheets + notifica Slack + email al candidato</p>
      </div>
    </div>
  </div>

</div>

---

<!-- SLIDE 4: OUTPUT — DASHBOARD + EXCEL -->
<div class="light-slide" transition="slide-up"></div>

<div class="relative z-10 px-14 py-8 h-full flex flex-col">
  <div class="mb-3">
    <span class="slide-label">Output concreti</span>
    <h2 class="slide-title">Dashboard & Report strutturato</h2>
  </div>

  <div class="grid grid-cols-2 gap-5 flex-1">
    <div class="output-card" style="border-left: 3px solid var(--indigo);" v-click>
      <div class="flex items-center gap-3 mb-2">
        <div class="output-icon" style="background: #e0e7ff;">📊</div>
        <h3>Dashboard interattiva</h3>
      </div>
      <p>Dashboard custom in Next.js connessa a Supabase, con:</p>
      <ul style="font-size: 0.75rem; color: var(--slate-500); margin-top: 8px; padding-left: 16px; line-height: 1.7;">
        <li><strong style="color: var(--slate-900);">KPI cards</strong> — totale candidati, nuovi oggi, tasso assunzione</li>
        <li><strong style="color: var(--slate-900);">Grafici pipeline</strong> — distribuzione per stato</li>
        <li><strong style="color: var(--slate-900);">Tabella candidati</strong> — ricerca, filtri, dettaglio</li>
        <li><strong style="color: var(--slate-900);">Filtri temporali</strong> — oggi, 7gg, 30gg, tutti</li>
        <li><strong style="color: var(--slate-900);">Pipeline Kanban</strong> — gestione visuale degli stati</li>
      </ul>
    </div>
    <div class="output-card" style="border-left: 3px solid var(--emerald);" v-click>
      <div class="flex items-center gap-3 mb-2">
        <div class="output-icon" style="background: #d1fae5;">📋</div>
        <h3>Google Sheets strutturato</h3>
      </div>
      <p>Ogni candidato viene registrato automaticamente:</p>
      <ul style="font-size: 0.72rem; color: var(--slate-500); margin-top: 8px; padding-left: 16px; line-height: 1.7;">
        <li><strong style="color: var(--slate-900);">Candidato</strong> — Mario Rossi</li>
        <li><strong style="color: var(--emerald);">Score</strong> — Idoneo (58/70)</li>
        <li><strong style="color: var(--slate-900);">Ruolo dedotto</strong> — Content Creator</li>
        <li><strong style="color: var(--slate-900);">Email / Tel / LinkedIn</strong> — ✅ Estratti auto</li>
        <li><strong style="color: var(--indigo);">CV / Portfolio</strong> — 🔗 Link Google Drive</li>
        <li><strong style="color: var(--slate-900);">Link Mail</strong> — 🔗 Link diretto Gmail</li>
      </ul>
    </div>
  </div>

  <div style="text-align: center; margin-top: 14px;">
    <span style="display: inline-block; padding: 8px 22px; border-radius: 10px; background: #e0e7ff; color: var(--indigo); font-size: 0.78rem; font-weight: 600;">
      🎯 Demo live della dashboard disponibile
    </span>
  </div>
</div>

---

<!-- SLIDE 5: VALORE GENERATO -->
<div class="dark-slide" transition="slide-up"></div>

<div class="relative z-10 px-14 py-8 h-full flex flex-col">
  <div class="mb-4">
    <span class="slide-label" style="color: #818cf8;">Impatto</span>
    <h2 class="slide-title-white">Il valore che creiamo</h2>
  </div>

  <div class="grid grid-cols-2 gap-5 flex-1 items-start">
    <div class="value-card" v-click>
      <div class="value-number" style="color: #34d399;">10×</div>
      <div class="value-label">Efficienza</div>
      <div class="value-desc">Automazione completa del workflow dallo screening iniziale alla notifica finale.</div>
    </div>
    <div class="value-card" v-click>
      <div class="value-number" style="color: #818cf8;">100%</div>
      <div class="value-label">Standard</div>
      <div class="value-desc">Valutazione basata su parametri oggettivi e certificati per ogni lotto di dati.</div>
    </div>
    <div class="value-card" v-click>
      <div class="value-number" style="color: #fbbf24;">0€</div>
      <div class="value-label">Manutenzione</div>
      <div class="value-desc">Architettura cloud e no-code che azzera i costi fissi di gestione server.</div>
    </div>
    <div class="value-card" v-click>
      <div class="value-number" style="color: #f87171;">100%</div>
      <div class="value-label">Modulare</div>
      <div class="value-desc">Workflow agnostico: scegli lo stack tecnologico (ATS, CRM, HRIS) più adatto.</div>
    </div>
  </div>

</div>

---

<!-- SLIDE 6: SVILUPPI FUTURI -->
<div class="dark-slide" transition="slide-up"></div>

<div class="relative z-10 px-14 py-8 h-full flex flex-col">
  <div class="mb-4">
    <span class="slide-label" style="color: #818cf8;">Prossimi passi</span>
    <h2 class="slide-title-white">Sviluppi futuri</h2>
  </div>

  <div class="grid grid-cols-2 gap-4 flex-1">
    <div class="future-card" v-click>
      <div class="flex items-center gap-3 mb-2">
        <div class="future-icon" style="background: rgba(129,140,248,0.15);">📈</div>
        <h3>Analisi Predittiva</h3>
      </div>
      <p>Algoritmi AI per identificare i "top performers" basandosi sui successi storici del team e della cultura aziendale.</p>
    </div>
    <div class="future-card" v-click>
      <div class="flex items-center gap-3 mb-2">
        <div class="future-icon" style="background: rgba(52,211,153,0.15);">📅</div>
        <h3>Auto-scheduling</h3>
      </div>
      <p>Integrazione Calendly per invitare automaticamente i candidati top-score al colloquio tecnico successivo.</p>
    </div>
    <div class="future-card" v-click>
      <div class="flex items-center gap-3 mb-2">
        <div class="future-icon" style="background: rgba(251,191,36,0.15);">🌐</div>
        <h3>Multi-Source Intelligence</h3>
      </div>
      <p>Arricchimento profili incrociando dati GitHub, LinkedIn e Portfolio per una visione a 360° del candidato.</p>
    </div>
    <div class="future-card" v-click>
      <div class="flex items-center gap-3 mb-2">
        <div class="future-icon" style="background: rgba(56,189,248,0.15);">🧪</div>
        <h3>Smart Interview Co-pilot</h3>
      </div>
      <p>Generazione automatica di domande tecniche mirate basate sui "gap" o punti di forza rilevati nel CV.</p>
    </div>
  </div>
</div>

---

<!-- SLIDE 7: GRAZIE -->
<div class="thankyou-bg"></div>

<div class="relative z-10 flex flex-col items-center justify-center h-full gap-8">
  <h1 class="thankyou-title">Grazie<span>.</span></h1>

  <p style="color: rgba(255,255,255,0.5); font-size: 1.1rem; font-weight: 400;">
    Domande?
  </p>

  <div class="flex gap-3">
    <span class="contact-pill">📍 Bicocca</span>
    <span class="contact-pill">📅 27 Marzo 2026</span>
    <span class="contact-pill">🏆 Hack4Innovation</span>
  </div>
</div>
