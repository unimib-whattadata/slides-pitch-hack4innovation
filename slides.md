---
theme: default
background: ''
class: text-center
highlighter: shiki
lineNumbers: false
info: |
  ## Hack4Innovation Bicocca
  Pitch Deck for Automated CV Evaluation Pipeline
drawings:
  persist: false
transition: slide-left
title: Hack4Innovation Bicocca - Team Pitch
---

<style>
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800;900&display=swap');

:root {
  --purple-primary: #7c3aed;
  --purple-light: #a78bfa;
  --cyan-accent: #22d3ee;
  --pink-accent: #f472b6;
  --gradient-start: #0f0c29;
  --gradient-mid: #302b63;
  --gradient-end: #24243e;
}

.slidev-layout {
  font-family: 'Inter', sans-serif !important;
}

/* ─── TITLE SLIDE ─── */
.hero-bg {
  position: absolute;
  inset: 0;
  background: linear-gradient(135deg, #0f0c29 0%, #302b63 50%, #24243e 100%);
  overflow: hidden;
}

.hero-bg::before {
  content: '';
  position: absolute;
  width: 600px;
  height: 600px;
  background: radial-gradient(circle, rgba(124,58,237,0.35) 0%, transparent 70%);
  top: -100px;
  right: -100px;
  animation: pulse-glow 4s ease-in-out infinite;
}

.hero-bg::after {
  content: '';
  position: absolute;
  width: 500px;
  height: 500px;
  background: radial-gradient(circle, rgba(34,211,238,0.2) 0%, transparent 70%);
  bottom: -150px;
  left: -50px;
  animation: pulse-glow 5s ease-in-out infinite reverse;
}

@keyframes pulse-glow {
  0%, 100% { transform: scale(1); opacity: 0.7; }
  50% { transform: scale(1.15); opacity: 1; }
}

@keyframes float-up {
  0% { transform: translateY(30px); opacity: 0; }
  100% { transform: translateY(0); opacity: 1; }
}

@keyframes shimmer {
  0% { background-position: -200% center; }
  100% { background-position: 200% center; }
}

.hero-title {
  font-size: 3.6rem;
  font-weight: 900;
  letter-spacing: -0.03em;
  line-height: 1.1;
  background: linear-gradient(135deg, #fff 0%, #a78bfa 50%, #22d3ee 100%);
  background-size: 200% auto;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  animation: shimmer 4s linear infinite, float-up 1s ease-out;
}

.hero-subtitle {
  font-size: 1.15rem;
  font-weight: 400;
  color: rgba(255,255,255,0.6);
  letter-spacing: 0.15em;
  text-transform: uppercase;
  animation: float-up 1s ease-out 0.3s both;
}

.hero-badge {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 10px 24px;
  border-radius: 100px;
  background: rgba(124,58,237,0.2);
  border: 1px solid rgba(124,58,237,0.4);
  backdrop-filter: blur(12px);
  color: #a78bfa;
  font-weight: 600;
  font-size: 0.9rem;
  animation: float-up 1s ease-out 0.6s both;
  transition: all 0.3s ease;
}

.hero-badge:hover {
  background: rgba(124,58,237,0.35);
  transform: translateY(-2px);
  box-shadow: 0 8px 30px rgba(124,58,237,0.3);
}

/* ─── SHARED STYLES ─── */
.dark-slide {
  position: absolute;
  inset: 0;
  background: linear-gradient(135deg, #0f0c29 0%, #1a1640 50%, #24243e 100%);
}

.slide-title {
  font-size: 2.2rem;
  font-weight: 800;
  letter-spacing: -0.02em;
  background: linear-gradient(135deg, #fff, #a78bfa);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.slide-label {
  font-size: 0.75rem;
  font-weight: 600;
  letter-spacing: 0.2em;
  text-transform: uppercase;
  color: #7c3aed;
}

/* ─── PROBLEM CARDS ─── */
.problem-card {
  background: rgba(255,255,255,0.04);
  border: 1px solid rgba(255,255,255,0.08);
  border-radius: 16px;
  padding: 16px;
  backdrop-filter: blur(10px);
  transition: all 0.35s cubic-bezier(0.4, 0, 0.2, 1);
  position: relative;
  overflow: hidden;
}

.problem-card::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 2px;
  background: linear-gradient(90deg, transparent, #f472b6, transparent);
  opacity: 0;
  transition: opacity 0.35s ease;
}

.problem-card:hover {
  background: rgba(255,255,255,0.08);
  transform: translateY(-4px);
  border-color: rgba(244,114,182,0.3);
  box-shadow: 0 12px 40px rgba(0,0,0,0.3);
}

.problem-card:hover::before {
  opacity: 1;
}

.problem-icon {
  width: 38px;
  height: 38px;
  border-radius: 10px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.2rem;
  background: rgba(244,114,182,0.15);
  flex-shrink: 0;
}

.problem-card h3 {
  font-size: 0.95rem;
  font-weight: 700;
  color: #fff;
  margin: 0;
}

.problem-card p {
  font-size: 0.75rem;
  color: rgba(255,255,255,0.5);
  line-height: 1.5;
}

/* ─── SOLUTION PIPELINE ─── */
.pipeline-step {
  display: flex;
  align-items: center;
  gap: 14px;
  padding: 11px 16px;
  border-radius: 14px;
  background: rgba(255,255,255,0.03);
  border: 1px solid rgba(255,255,255,0.06);
  transition: all 0.3s ease;
}

.pipeline-step:hover {
  background: rgba(124,58,237,0.1);
  border-color: rgba(124,58,237,0.3);
  transform: translateX(6px);
}

.step-number {
  width: 36px;
  height: 36px;
  border-radius: 10px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 0.8rem;
  font-weight: 800;
  color: #fff;
  flex-shrink: 0;
}

.step-content h4 {
  font-size: 0.85rem;
  font-weight: 700;
  color: #fff;
  margin: 0 0 1px 0;
}

.step-content p {
  font-size: 0.7rem;
  color: rgba(255,255,255,0.45);
  margin: 0;
  line-height: 1.3;
}

/* ─── TECH STACK CARD ─── */
.tech-stack-card {
  display: flex;
  align-items: center;
  gap: 24px;
  padding: 12px 24px;
  background: rgba(255,255,255,0.04);
  border: 1px solid rgba(255,255,255,0.1);
  border-radius: 16px;
  width: fit-content;
  margin: 12px 0 24px 0;
}

.tech-logo {
  height: 64px;
  width: 64px;
  object-fit: contain;
  border-radius: 8px;
}

/* ─── VALUE METRIC ─── */
.value-card {
  text-align: center;
  padding: 24px 16px;
  border-radius: 20px;
  background: rgba(255,255,255,0.04);
  border: 1px solid rgba(255,255,255,0.08);
  transition: all 0.35s cubic-bezier(0.4, 0, 0.2, 1);
}

.value-card:hover {
  transform: translateY(-6px);
  background: rgba(255,255,255,0.08);
  box-shadow: 0 20px 50px rgba(0,0,0,0.4);
}

.value-number {
  font-size: 2.8rem;
  font-weight: 900;
  letter-spacing: -0.04em;
  line-height: 1;
  margin-bottom: 6px;
}

.value-label {
  font-size: 0.8rem;
  font-weight: 600;
  color: #fff;
  margin-bottom: 4px;
}

.value-desc {
  font-size: 0.65rem;
  color: rgba(255,255,255,0.4);
  line-height: 1.4;
}

/* ─── FUTURE CARDS ─── */
.future-card {
  padding: 16px;
  border-radius: 16px;
  background: rgba(255,255,255,0.04);
  border: 1px solid rgba(255,255,255,0.08);
  transition: all 0.35s cubic-bezier(0.4, 0, 0.2, 1);
  position: relative;
  overflow: hidden;
}

.future-card::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  height: 2px;
  background: linear-gradient(90deg, transparent, var(--card-accent, #7c3aed), transparent);
  opacity: 0;
  transition: opacity 0.35s ease;
}

.future-card:hover {
  transform: translateY(-4px);
  background: rgba(255,255,255,0.07);
  box-shadow: 0 16px 40px rgba(0,0,0,0.3);
}

.future-card:hover::after {
  opacity: 1;
}

.future-icon {
  width: 40px;
  height: 40px;
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.2rem;
  background: rgba(255,255,255,0.04);
  flex-shrink: 0;
}

.future-card h3 {
  font-size: 0.95rem;
  font-weight: 700;
  color: #fff;
  margin: 0;
}

.future-card p {
  font-size: 0.7rem;
  color: rgba(255,255,255,0.45);
  line-height: 1.5;
}

/* ─── THANK YOU SLIDE ─── */
.thankyou-bg {
  position: absolute;
  inset: 0;
  background: linear-gradient(135deg, #0f0c29 0%, #302b63 50%, #24243e 100%);
  overflow: hidden;
}

.thankyou-bg::before {
  content: '';
  position: absolute;
  width: 700px;
  height: 700px;
  background: radial-gradient(circle, rgba(124,58,237,0.25) 0%, transparent 70%);
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  animation: pulse-glow 4s ease-in-out infinite;
}

.thankyou-title {
  font-size: 4rem;
  font-weight: 900;
  letter-spacing: -0.03em;
  background: linear-gradient(135deg, #fff, #a78bfa, #22d3ee);
  background-size: 200% auto;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  animation: shimmer 4s linear infinite;
}

.contact-pill {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 8px 20px;
  border-radius: 100px;
  background: rgba(255,255,255,0.06);
  border: 1px solid rgba(255,255,255,0.12);
  color: rgba(255,255,255,0.7);
  font-size: 0.8rem;
  transition: all 0.3s ease;
}

.contact-pill:hover {
  background: rgba(124,58,237,0.2);
  border-color: rgba(124,58,237,0.4);
  color: #a78bfa;
}

/* ─── TECH BADGE ─── */
.tech-badge {
  display: inline-flex;
  align-items: center;
  gap: 6px;
  padding: 6px 14px;
  border-radius: 8px;
  font-size: 0.7rem;
  font-weight: 600;
  background: rgba(255,255,255,0.06);
  border: 1px solid rgba(255,255,255,0.1);
  color: rgba(255,255,255,0.7);
}

/* ─── SLIDE NUMBERS / PROGRESS ─── */
.slidev-page-number {
  color: rgba(255,255,255,0.3) !important;
}
</style>

<!-- SLIDE 1: HERO -->
<div class="hero-bg"></div>

<div class="relative z-10 flex flex-col items-center justify-center h-full gap-6">
  <div class="hero-subtitle">Hack4Innovation Bicocca · 27 March 2026</div>
  
  <h1 class="hero-title">AI Talent<br/>Acquisition Assistant</h1>
  
  <p style="color: rgba(255,255,255,0.45); font-size: 1.05rem; max-width: 500px; text-align: center; animation: float-up 1s ease-out 0.45s both;">
    Automating candidate evaluation with intelligent workflows
  </p>

  <span class="hero-badge" @click="$slidev.nav.next" style="cursor:pointer;">
    Discover Our Pipeline →
  </span>
</div>

---

<!-- SLIDE 2: THE PROBLEM -->
<div class="dark-slide"></div>

<div class="relative z-10 px-14 py-8 h-full flex flex-col">
  <div class="mb-4">
    <span class="slide-label">The challenge</span>
    <h2 class="slide-title mt-1">The Hiring Bottleneck</h2>
  </div>

  <div class="grid grid-cols-2 gap-4 flex-1">
    <div class="problem-card">
      <div class="flex items-center gap-3 mb-2">
        <div class="problem-icon">⏱️</div>
        <h3>Too Slow</h3>
      </div>
      <p>HR teams spend countless hours on manual screening, creating bottlenecks that let top talent slip away.</p>
    </div>
    <div class="problem-card">
      <div class="flex items-center gap-3 mb-2">
        <div class="problem-icon">⚖️</div>
        <h3>Inconsistent</h3>
      </div>
      <p>Different recruiters apply different criteria to the same CV — leading to biased, subjective outcomes.</p>
    </div>
    <div class="problem-card">
      <div class="flex items-center gap-3 mb-2">
        <div class="problem-icon">🧩</div>
        <h3>Unstructured Data</h3>
      </div>
      <p>Modern candidates showcase skills via portfolios that don't fit the standard CV format.</p>
    </div>
    <div class="problem-card">
      <div class="flex items-center gap-3 mb-2">
        <div class="problem-icon">🧠</div>
        <h3>Decision Fatigue</h3>
      </div>
      <p>Manual role classification and experience matching is error-prone at scale.</p>
    </div>
  </div>
</div>

---

<!-- SLIDE 3: THE SOLUTION -->
<div class="dark-slide"></div>

<div class="relative z-10 px-14 py-8 h-full flex flex-col">
  <div class="mb-1">
    <span class="slide-label">Our approach</span>
    <h2 class="slide-title mt-1">The Automated Pipeline</h2>
    <div class="tech-stack-card">
      <img src="./img/n8n.png" class="tech-logo" title="n8n" />
      <img src="./img/oai.png" class="tech-logo" title="OpenAI" />
      <img src="./img/sheets.png" class="tech-logo" title="Google Sheets" />
      <img src="./img/slack.png" class="tech-logo" title="Slack" />
    </div>
  </div>

  <div class="grid grid-cols-2 gap-4 flex-1">
    <div class="pipeline-step">
      <div class="step-number" style="background: linear-gradient(135deg, #7c3aed, #6d28d9);">01</div>
      <div class="step-content">
        <h4>Email Ingestion</h4>
        <p>Automatically fetches incoming applicant emails from Gmail</p>
      </div>
    </div>
    <div class="pipeline-step">
      <div class="step-number" style="background: linear-gradient(135deg, #8b5cf6, #7c3aed);">02</div>
      <div class="step-content">
        <h4>Cloud Organization</h4>
        <p>Extracts & categorizes CVs and Portfolios into Google Drive</p>
      </div>
    </div>
    <div class="pipeline-step">
      <div class="step-number" style="background: linear-gradient(135deg, #a78bfa, #8b5cf6);">03</div>
      <div class="step-content">
        <h4>AI Parsing & Extraction</h4>
        <p>Extracts Name, Phone, Email, LinkedIn via structured AI output</p>
      </div>
    </div>
    <div class="pipeline-step">
      <div class="step-number" style="background: linear-gradient(135deg, #c4b5fd, #a78bfa);">04</div>
      <div class="step-content">
        <h4>Scoring & Grading</h4>
        <p>Evaluates across 7 metrics - then grades, updates Sheets & pings Slack</p>
      </div>
    </div>
  </div>
</div>

---

<!-- SLIDE 4: VALUE GENERATED -->
<div class="dark-slide"></div>

<div class="relative z-10 px-14 py-8 h-full flex flex-col">
  <div class="mb-4">
    <span class="slide-label">Impact</span>
    <h2 class="slide-title mt-1">The Value We Create</h2>
  </div>

  <div class="grid grid-cols-4 gap-4 flex-1 items-start">
    <div class="value-card">
      <div class="value-number" style="background: linear-gradient(135deg, #22d3ee, #06b6d4); -webkit-background-clip: text; -webkit-text-fill-color: transparent;">10×</div>
      <div class="value-label">Faster</div>
      <div class="value-desc">Instant evaluation within minutes of application</div>
    </div>
    <div class="value-card">
      <div class="value-number" style="background: linear-gradient(135deg, #a78bfa, #7c3aed); -webkit-background-clip: text; -webkit-text-fill-color: transparent;">💎</div>
      <div class="value-label">Hidden Gems</div>
      <div class="value-desc">Infers true roles from actual experience, not titles</div>
    </div>
    <div class="value-card">
      <div class="value-number" style="background: linear-gradient(135deg, #34d399, #10b981); -webkit-background-clip: text; -webkit-text-fill-color: transparent;">100%</div>
      <div class="value-label">Consistent</div>
      <div class="value-desc">Every candidate scored with the same rigorous criteria</div>
    </div>
    <div class="value-card">
      <div class="value-number" style="background: linear-gradient(135deg, #f472b6, #ec4899); -webkit-background-clip: text; -webkit-text-fill-color: transparent;">🙋</div>
      <div class="value-label">Human Focus</div>
      <div class="value-desc">HR shifts from admin to high-value interviews</div>
    </div>
  </div>

  <div style="text-align: center; margin-top: 20px;">
    <img src="https://media.giphy.com/media/8p5mXt9wKFTs4/giphy.gif" style="height: 120px; margin: 0 auto 12px; border-radius: 12px; box-shadow: 0 10px 40px rgba(124,58,237,0.3); border: 1px solid rgba(255,255,255,0.1);" />
    <br/>
    <span style="display: inline-block; padding: 10px 28px; border-radius: 12px; background: rgba(124,58,237,0.12); border: 1px solid rgba(124,58,237,0.25); color: #a78bfa; font-size: 0.8rem; font-weight: 600;">
      From administrative bottleneck to strategic advantage
    </span>
  </div>
</div>

---

<!-- SLIDE 5: FUTURE DEVELOPMENTS -->
<div class="dark-slide"></div>

<div class="relative z-10 px-14 py-8 h-full flex flex-col">
  <div class="mb-4">
    <span class="slide-label">What's next</span>
    <h2 class="slide-title mt-1">Future Developments</h2>
  </div>

  <div class="grid grid-cols-2 gap-4 flex-1">
    <div class="future-card" style="--card-accent: #22d3ee;">
      <div class="flex items-center gap-3 mb-2">
        <div class="future-icon" style="background: rgba(34,211,238,0.12);">🤖</div>
        <h3>Conversational Screening</h3>
      </div>
      <p>AI voice/chat agent for a quick 5-minute cultural fit pre-screen before human interviews.</p>
    </div>
    <div class="future-card" style="--card-accent: #a78bfa;">
      <div class="flex items-center gap-3 mb-2">
        <div class="future-icon" style="background: rgba(167,139,250,0.12);">📅</div>
        <h3>Auto-Scheduling</h3>
      </div>
      <p>Calendly integration to auto-invite top-scoring candidates to the next round.</p>
    </div>
    <div class="future-card" style="--card-accent: #34d399;">
      <div class="flex items-center gap-3 mb-2">
        <div class="future-icon" style="background: rgba(52,211,153,0.12);">📊</div>
        <h3>ATS Integration</h3>
      </div>
      <p>Push qualified candidates directly into enterprise ATS platforms.</p>
    </div>
    <div class="future-card" style="--card-accent: #f472b6;">
      <div class="flex items-center gap-3 mb-2">
        <div class="future-icon" style="background: rgba(244,114,182,0.12);">🏢</div>
        <h3>Role-Specific Rubrics</h3>
      </div>
      <p>Dynamically adjust evaluation criteria based on the specific job pathway.</p>
    </div>
  </div>
</div>

---

<!-- SLIDE 6: THANK YOU -->
<div class="thankyou-bg"></div>

<div class="relative z-10 flex flex-col items-center justify-center h-full gap-8">
  <h1 class="thankyou-title">Thank You</h1>
  
  <p style="color: rgba(255,255,255,0.5); font-size: 1.1rem; font-weight: 400;">
    Any questions?
  </p>

  <div class="flex gap-3">
    <span class="contact-pill">📍 Bicocca Pavilion</span>
    <span class="contact-pill">📅 27 March 2026</span>
    <span class="contact-pill">🏆 Hack4Innovation</span>
  </div>
</div>
