---
theme: default
background: ""
class: text-center
highlighter: shiki
lineNumbers: false
info: |
  ## Hack4Innovation Bicocca
  Automated pipeline for AI-powered CV evaluation
drawings:
  persist: false
transition: slide-left
title: Hack4Innovation Bicocca — HireLight
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

/* ─── V-CLICK GLOBAL ANIMATION ─── */
.slidev-vclick-target {
  transition: opacity 0.5s cubic-bezier(.22,1,.36,1), transform 0.5s cubic-bezier(.22,1,.36,1) !important;
}
.slidev-vclick-hidden {
  opacity: 0 !important;
  transform: translateY(14px) !important;
  pointer-events: none;
}

/* ─── PIPELINE PREVIEW ─── */
.pipeline-preview {
  position: absolute;
  inset: 0;
  z-index: 20;
  display: flex;
  align-items: center;
  justify-content: center;
  background: #fff;
}

.pipeline-preview-img {
  max-width: 92%;
  max-height: 88%;
  object-fit: contain;
  border-radius: 12px;
  box-shadow: 0 8px 40px rgba(0,0,0,0.12);
}

.pip-preview-enter-active {
  transition: opacity 0.45s cubic-bezier(.22,1,.36,1), transform 0.45s cubic-bezier(.22,1,.36,1);
}
.pip-preview-leave-active {
  transition: opacity 0.4s cubic-bezier(.22,1,.36,1), transform 0.4s cubic-bezier(.22,1,.36,1);
}
.pip-preview-enter-from {
  opacity: 0;
  transform: scale(0.92);
}
.pip-preview-leave-to {
  opacity: 0;
  transform: scale(1.04);
}

/* ─── HERO ─── */
.hero-bg {
  position: absolute;
  inset: 0;
  background: linear-gradient(-45deg, #080d1a, #0f172a, #080d1a, #111827);
  background-size: 400% 400%;
  animation: gradient-flow 15s ease infinite;
  overflow: hidden;
}

@keyframes gradient-flow {
  0% { background-position: 0% 50%; }
  50% { background-position: 100% 50%; }
  100% { background-position: 0% 50%; }
}

.hero-bg::before {
  content: '';
  position: absolute;
  inset: 0;
  background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noiseFilter'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.65' numOctaves='3' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='noiseFilter'/%3E%3C/svg%3E");
  opacity: 0.04;
  pointer-events: none;
  z-index: 1;
}

.hero-blob {
  position: absolute;
  border-radius: 50%;
  filter: blur(80px);
  z-index: 0;
  pointer-events: none;
  opacity: 0.35;
  will-change: transform;
}

.hb-1 {
  width: 650px; height: 650px;
  background: radial-gradient(circle, #4f46e5 0%, transparent 75%);
  top: -240px; right: -120px;
  animation: orbit1 12s linear infinite;
}

.hb-2 {
  width: 550px; height: 550px;
  background: radial-gradient(circle, #10b981 0%, transparent 75%);
  bottom: -180px; left: -120px;
  animation: orbit2 15s linear infinite;
}

.hb-3 {
  width: 500px; height: 500px;
  background: radial-gradient(circle, #818cf8 0%, transparent 75%);
  top: 40%; left: 55%;
  animation: orbit3 10s linear infinite;
}

@keyframes orbit1 {
  from { transform: rotate(0deg) translate(40px) rotate(0deg); }
  to { transform: rotate(360deg) translate(40px) rotate(-360deg); }
}

@keyframes orbit2 {
  from { transform: rotate(0deg) translate(60px) rotate(0deg); }
  to { transform: rotate(-360deg) translate(60px) rotate(360deg); }
}

@keyframes orbit3 {
  from { transform: rotate(0deg) translate(30px) rotate(0deg); }
  to { transform: rotate(360deg) translate(30px) rotate(-360deg); }
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

.hero-title em {
  font-style: normal;
  position: relative;
  display: inline-block;
}

.hero-title em::after {
  content: '';
  position: absolute;
  left: 0;
  bottom: 2px;
  width: 100%;
  height: 3px;
  background: linear-gradient(90deg, #ffffff, rgba(255,255,255,0));
  border-radius: 2px;
  transform-origin: left;
  animation: prob-line-grow 0.8s cubic-bezier(.22,1,.36,1) 0.4s both;
}

.hero-title span {
  background: linear-gradient(120deg, #4f46e5, #818cf8, #4f46e5);
  background-size: 200% auto;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  animation: shine 3s linear infinite;
}

@keyframes shine {
  to { background-position: 200% center; }
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
  transition: all 0.35s cubic-bezier(.22,1,.36,1);
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
  transition: all 0.35s cubic-bezier(.22,1,.36,1);
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

.nodes-badge {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 10px 18px;
  height: 64px;
  box-sizing: border-box;
  align-self: stretch;
  background: var(--card);
  border: 1px solid #e2e8f0;
  border-radius: 14px;
  line-height: 1;
}

.nodes-num {
  font-size: 1.3rem;
  font-weight: 900;
  color: var(--indigo);
  letter-spacing: -0.03em;
}

.nodes-label {
  font-size: 0.6rem;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 0.12em;
  color: var(--slate-500);
  margin-top: 2px;
}

.tech-stack-card-dark {
  display: flex;
  align-items: center;
  gap: 16px;
  padding: 10px 18px;
  background: rgba(255,255,255,0.05);
  border: 1px solid rgba(255,255,255,0.08);
  border-radius: 14px;
}

.nodes-badge-dark {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 10px 18px;
  align-self: stretch;
  background: rgba(255,255,255,0.05);
  border: 1px solid rgba(255,255,255,0.08);
  border-radius: 14px;
  line-height: 1;
}

.pipeline-step-dark {
  display: flex;
  align-items: center;
  gap: 14px;
  padding: 12px 16px;
  border-radius: 14px;
  background: rgba(255,255,255,0.04);
  border: 1px solid rgba(255,255,255,0.07);
  transition: all 0.35s cubic-bezier(.22,1,.36,1);
}

.pipeline-step-dark:hover {
  background: rgba(255,255,255,0.08);
  transform: translateX(4px);
}

.pipeline-step-dark .step-content h4 {
  font-size: 0.88rem;
  font-weight: 700;
  color: #fff;
  margin: 0 0 2px 0;
}

.pipeline-step-dark .step-content p {
  font-size: 0.72rem;
  color: rgba(255,255,255,0.50);
  margin: 0;
  line-height: 1.35;
}

.sol-img-wrap {
  width: 44%;
  flex-shrink: 0;
  display: flex;
  align-items: center;
  justify-content: center;
  background: rgba(255,255,255,0.03);
  border-radius: 16px;
  border: 1px solid rgba(255,255,255,0.07);
  overflow: hidden;
  padding: 12px;
}

.sol-img {
  width: 100%;
  height: 100%;
  object-fit: contain;
  border-radius: 10px;
}

/* ─── SOLUTION SLIDE ─── */
.sol-bg {
  position: absolute;
  inset: 0;
  background: #080d1a;
  overflow: hidden;
}
.sol-bg::before {
  content: '';
  position: absolute;
  width: 600px;
  height: 600px;
  background: radial-gradient(circle, rgba(79,70,229,0.08) 0%, transparent 60%);
  top: -120px;
  right: -100px;
  pointer-events: none;
}
.sol-bg::after {
  content: '';
  position: absolute;
  width: 500px;
  height: 500px;
  background: radial-gradient(circle, rgba(16,185,129,0.06) 0%, transparent 60%);
  bottom: -80px;
  left: -60px;
  pointer-events: none;
}
.sol-stack-row {
  display: flex;
  align-items: center;
  gap: 8px;
}
.sol-logo {
  width: 28px;
  height: 28px;
  object-fit: contain;
  border-radius: 8px;
  opacity: 0.9;
  padding: 5px;
  background: rgba(255,255,255,0.06);
  border: 1px solid rgba(255,255,255,0.10);
  box-sizing: content-box;
}
.sol-nodes-chip {
  display: flex;
  align-items: baseline;
  gap: 4px;
  padding: 5px 10px;
  background: rgba(79,70,229,0.15);
  border: 1px solid rgba(79,70,229,0.3);
  border-radius: 8px;
  margin-left: 4px;
  box-sizing: content-box;
}
.sol-nodes-num {
  font-size: 0.9rem;
  font-weight: 900;
  color: #818cf8;
  letter-spacing: -0.02em;
}
.sol-nodes-label {
  font-size: 0.55rem;
  font-weight: 600;
  color: rgba(255,255,255,0.4);
  text-transform: uppercase;
  letter-spacing: 0.1em;
}
.sol-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 14px;
  flex: 1;
  align-items: stretch;
}
.sol-card {
  padding: 22px 20px;
  border-radius: 18px;
  background: rgba(255,255,255,0.05);
  backdrop-filter: blur(16px);
  -webkit-backdrop-filter: blur(16px);
  border: 1px solid rgba(255,255,255,0.08);
  display: flex;
  flex-direction: column;
  gap: 8px;
  transition: all 0.35s cubic-bezier(.22,1,.36,1);
  cursor: default;
  position: relative;
  overflow: hidden;
}
.sol-card::before {
  content: '';
  position: absolute;
  top: 0; left: 0; right: 0;
  height: 1px;
  background: linear-gradient(90deg, transparent, rgba(255,255,255,0.2), transparent);
}
.sol-card:nth-child(1) { box-shadow: 0 0 0 1px rgba(79,70,229,0.2), 0 8px 32px rgba(79,70,229,0.08); }
.sol-card:nth-child(2) { box-shadow: 0 0 0 1px rgba(124,58,237,0.2), 0 8px 32px rgba(124,58,237,0.08); }
.sol-card:nth-child(3) { box-shadow: 0 0 0 1px rgba(14,165,233,0.2), 0 8px 32px rgba(14,165,233,0.08); }
.sol-card:nth-child(4) { box-shadow: 0 0 0 1px rgba(16,185,129,0.2), 0 8px 32px rgba(16,185,129,0.08); }
.sol-card:nth-child(1):hover { background: rgba(79,70,229,0.08); box-shadow: 0 0 0 1px rgba(79,70,229,0.4), 0 16px 48px rgba(79,70,229,0.16); transform: translateY(-3px); }
.sol-card:nth-child(2):hover { background: rgba(124,58,237,0.08); box-shadow: 0 0 0 1px rgba(124,58,237,0.4), 0 16px 48px rgba(124,58,237,0.16); transform: translateY(-3px); }
.sol-card:nth-child(3):hover { background: rgba(14,165,233,0.08); box-shadow: 0 0 0 1px rgba(14,165,233,0.4), 0 16px 48px rgba(14,165,233,0.16); transform: translateY(-3px); }
.sol-card:nth-child(4):hover { background: rgba(16,185,129,0.08); box-shadow: 0 0 0 1px rgba(16,185,129,0.4), 0 16px 48px rgba(16,185,129,0.16); transform: translateY(-3px); }
.sol-card-num {
  font-size: 1.4rem;
  font-weight: 900;
  letter-spacing: -0.04em;
  line-height: 1;
}
.sol-card-title {
  font-size: 0.88rem;
  font-weight: 700;
  color: #fff;
  margin: 0;
  line-height: 1.2;
}
.sol-card-desc {
  font-size: 0.70rem;
  color: rgba(255,255,255,0.55);
  line-height: 1.5;
  margin: 0;
  flex: 1;
}
/* ─── OUTPUT CARDS ─── */
.output-card {
  background: var(--card);
  border: 1px solid #e2e8f0;
  border-radius: 16px;
  padding: 20px;
  transition: all 0.35s cubic-bezier(.22,1,.36,1);
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
  transition: all 0.35s cubic-bezier(.22,1,.36,1);
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
  animation: prob-num-glow 3s ease-in-out infinite;
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
  transition: all 0.35s cubic-bezier(.22,1,.36,1);
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
/* ─── THANK YOU ─── */
.thankyou-bg {
  position: absolute;
  inset: 0;
  background: #080d1a;
  overflow: hidden;
}

.thankyou-bg::before,
.thankyou-bg::after,
.thankyou-blob {
  content: '';
  position: absolute;
  filter: blur(80px);
  opacity: 0.15;
  border-radius: 50%;
  animation: float-blob 20s infinite alternate ease-in-out;
}

.thankyou-bg::before {
  width: 500px; height: 500px;
  background: radial-gradient(circle, #4f46e5 0%, transparent 70%);
  top: -100px; left: -100px;
  animation-duration: 25s;
}

.thankyou-bg::after {
  width: 600px; height: 600px;
  background: radial-gradient(circle, #34d399 0%, transparent 70%);
  bottom: -150px; right: -150px;
  animation-duration: 30s;
  animation-delay: -5s;
}

.thankyou-blob {
  width: 400px; height: 400px;
  background: radial-gradient(circle, #818cf8 0%, transparent 70%);
  top: 40%; left: 50%;
  animation-duration: 22s;
  animation-delay: -10s;
}

@keyframes float-blob {
  from { transform: translate(0, 0) scale(1); }
  to { transform: translate(100px, 40px) scale(1.1); }
}

.thankyou-title {
  font-size: 5.5rem;
  font-weight: 900;
  letter-spacing: -0.04em;
  line-height: 1;
  background: linear-gradient(135deg, #fff 30%, #818cf8 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  filter: drop-shadow(0 0 30px rgba(129,140,248,0.3));
}

.thankyou-subtitle {
  font-size: 1.2rem;
  color: rgba(255,255,255,0.5);
  font-weight: 400;
  letter-spacing: 0.05em;
  margin-top: -10px;
}

.contact-pill {
  display: inline-flex;
  align-items: center;
  gap: 10px;
  padding: 10px 22px;
  border-radius: 14px;
  background: rgba(255,255,255,0.04);
  backdrop-filter: blur(20px);
  -webkit-backdrop-filter: blur(20px);
  border: 1px solid rgba(255,255,255,0.08);
  color: rgba(255,255,255,0.7);
  font-size: 0.85rem;
  font-weight: 600;
  transition: all 0.4s cubic-bezier(.22,1,.36,1);
}

.contact-pill:hover {
  background: rgba(255,255,255,0.1);
  border-color: rgba(129,140,248,0.4);
  color: #fff;
  transform: translateY(-4px);
  box-shadow: 0 10px 25px rgba(0,0,0,0.2), 0 0 15px rgba(129,140,248,0.2);
}

/* ─── PROBLEM SLIDE REDESIGN ─── */
.prob-bg {
  position: absolute;
  inset: 0;
  background: #080d1a;
  overflow: hidden;
}

.prob-bg::before {
  content: '';
  position: absolute;
  width: 700px;
  height: 700px;
  background: radial-gradient(circle, rgba(239,68,68,0.07) 0%, transparent 60%);
  top: -180px;
  right: -120px;
  pointer-events: none;
}

.prob-bg::after {
  content: '';
  position: absolute;
  width: 500px;
  height: 500px;
  background: radial-gradient(circle, rgba(79,70,229,0.07) 0%, transparent 60%);
  bottom: -100px;
  left: -80px;
  pointer-events: none;
}

@keyframes shimmer-rotto {
  0%, 100% { text-shadow: 0 0 8px rgba(79,70,229,0.4); }
  50%       { text-shadow: 0 0 20px rgba(79,70,229,0.9), 0 0 40px rgba(79,70,229,0.4); }
}

@keyframes prob-fade-up {
  from { opacity: 0; transform: translateY(28px); }
  to   { opacity: 1; transform: translateY(0); }
}

@keyframes prob-line-grow {
  from { transform: scaleX(0); }
  to   { transform: scaleX(1); }
}

@keyframes prob-num-glow {
  0%, 100% { text-shadow: 0 0 20px currentColor; }
  50%       { text-shadow: 0 0 40px currentColor, 0 0 80px currentColor; }
}

/* ─── EXPANDED CARD GRID ─── */
.expanded-item {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  gap: 4px;
  padding: 12px;
  border-radius: 16px;
  background: rgba(255,255,255,0.03);
  border: 1px solid rgba(255,255,255,0.06);
  transition: all 0.3s ease;
}
.expanded-item:hover {
  background: rgba(255,255,255,0.06);
  transform: translateY(-4px);
}
.expanded-icon {
  font-size: 1.5rem;
  margin-bottom: 2px;
}
.expanded-title {
  font-size: 0.85rem;
  font-weight: 800;
  color: #fff;
  margin: 0;
}
.expanded-desc {
  font-size: 0.65rem;
  color: rgba(255,255,255,0.5);
  line-height: 1.4;
  margin: 0;
}
@keyframes fade-in {
  from { opacity: 0; transform: translateY(10px); }
  to { opacity: 1; transform: translateY(0); }
}
.animate-fade-in {
  animation: fade-in 0.5s ease-out both;
}

.prob-header {
  animation: prob-fade-up 0.7s cubic-bezier(.22,1,.36,1) both;
}

.prob-eyebrow {
  font-size: 0.65rem;
  font-weight: 700;
  letter-spacing: 0.22em;
  text-transform: uppercase;
  color: #4f46e5;
  display: inline-flex;
  align-items: center;
  gap: 8px;
}

.prob-eyebrow::before {
  content: '';
  width: 20px;
  height: 2px;
  background: #4f46e5;
  border-radius: 2px;
}

.prob-title {
  font-size: 2.6rem;
  font-weight: 900;
  color: #fff;
  letter-spacing: -0.035em;
  margin-top: 6px;
  line-height: 1.05;
}

.prob-title em {
  font-style: normal;
  position: relative;
  color: #4f46e5;
  animation: shimmer-rotto 4s ease-in-out infinite;
}

.prob-title em::after {
  content: '';
  position: absolute;
  left: 0;
  bottom: 2px;
  width: 100%;
  height: 3px;
  background: linear-gradient(90deg, #ffffff, rgba(255,255,255,0));
  border-radius: 2px;
  transform-origin: left;
  animation: prob-line-grow 0.8s cubic-bezier(.22,1,.36,1) 0.4s both;
}

.prob-subtitle {
  font-size: 0.88rem;
  color: rgba(255,255,255,0.62);
  margin-top: 8px;
  font-weight: 400;
}

.prob-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 14px;
  flex: 1;
  align-items: stretch;
}

.prob-item {
  padding: 22px 20px;
  border-radius: 18px;
  background: rgba(255,255,255,0.06);
  backdrop-filter: blur(16px);
  -webkit-backdrop-filter: blur(16px);
  border: 1px solid rgba(255,255,255,0.10);
  display: flex;
  flex-direction: column;
  gap: 12px;
  transition: all 0.35s cubic-bezier(.22,1,.36,1);
  cursor: default;
  position: relative;
  overflow: hidden;
}

.prob-item::before {
  content: '';
  position: absolute;
  top: 0; left: 0; right: 0;
  height: 1px;
  background: linear-gradient(90deg, transparent, rgba(255,255,255,0.25), transparent);
}

.prob-item:nth-child(1) {
  box-shadow: 0 0 0 1px rgba(251,191,36,0.18), 0 8px 32px rgba(251,191,36,0.08);
}
.prob-item:nth-child(2) {
  box-shadow: 0 0 0 1px rgba(248,113,113,0.18), 0 8px 32px rgba(248,113,113,0.08);
}
.prob-item:nth-child(3) {
  box-shadow: 0 0 0 1px rgba(129,140,248,0.18), 0 8px 32px rgba(129,140,248,0.08);
}

.prob-item:nth-child(1):hover {
  background: rgba(251,191,36,0.07);
  box-shadow: 0 0 0 1px rgba(251,191,36,0.40), 0 16px 48px rgba(251,191,36,0.18);
  transform: translateY(-5px);
}
.prob-item:nth-child(2):hover {
  background: rgba(248,113,113,0.07);
  box-shadow: 0 0 0 1px rgba(248,113,113,0.40), 0 16px 48px rgba(248,113,113,0.18);
  transform: translateY(-5px);
}
.prob-item:nth-child(3):hover {
  background: rgba(129,140,248,0.07);
  box-shadow: 0 0 0 1px rgba(129,140,248,0.40), 0 16px 48px rgba(129,140,248,0.18);
  transform: translateY(-5px);
}

.prob-item-num {
  font-size: 0.6rem;
  font-weight: 800;
  letter-spacing: 0.15em;
  color: rgba(255,255,255,0.22);
  text-transform: uppercase;
}

.prob-icon-wrap {
  width: 48px;
  height: 48px;
  border-radius: 14px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.4rem;
  flex-shrink: 0;
}

.pi-amber  { background: rgba(251,191,36,0.15);  border: 1px solid rgba(251,191,36,0.30); box-shadow: 0 0 16px rgba(251,191,36,0.12); }
.pi-rose   { background: rgba(248,113,113,0.15); border: 1px solid rgba(248,113,113,0.30); box-shadow: 0 0 16px rgba(248,113,113,0.12); }
.pi-indigo { background: rgba(167,139,250,0.15); border: 1px solid rgba(167,139,250,0.30); box-shadow: 0 0 16px rgba(167,139,250,0.12); }

.prob-item h3 {
  font-size: 0.95rem;
  font-weight: 700;
  color: #fff;
  margin: 0;
  line-height: 1.3;
}

.prob-item p {
  font-size: 0.73rem;
  color: rgba(255,255,255,0.62);
  line-height: 1.65;
  margin: 0;
  flex: 1;
}

.prob-stats-row {
  display: flex;
  align-items: flex-start;
  margin-top: 10px;
  padding-top: 10px;
  border-top: 1px solid rgba(255,255,255,0.06);
  gap: 0;
}

.prob-stat {
  flex: 1;
  text-align: center;
  padding: 8px 0;
}

.prob-stat-num {
  font-size: 2rem;
  font-weight: 900;
  letter-spacing: -0.04em;
  line-height: 1;
  animation: prob-num-glow 3s ease-in-out infinite;
}

.prob-stat-label {
  font-size: 0.65rem;
  color: rgba(255,255,255,0.50);
  margin-top: 5px;
  font-weight: 500;
  letter-spacing: 0.02em;
}

.prob-stat-source {
  font-size: 0.52rem;
  color: rgba(255,255,255,0.22);
  margin-top: 4px;
  font-style: italic;
  letter-spacing: 0.01em;
}

.prob-divider {
  width: 1px;
  height: 60px;
  background: rgba(255,255,255,0.08);
  flex-shrink: 0;
  margin-top: 8px;
}

/* ─── OUTPUT CARD DARK — PREMIUM ─── */
.output-card-dark {
  background: linear-gradient(135deg, rgba(255,255,255,0.07) 0%, rgba(255,255,255,0.02) 100%);
  border: 1px solid rgba(255,255,255,0.08);
  border-radius: 18px;
  padding: 24px;
  backdrop-filter: blur(20px);
  -webkit-backdrop-filter: blur(20px);
  transition: all 0.4s cubic-bezier(.22,1,.36,1);
  position: relative;
  overflow: hidden;
}
.output-card-dark::before {
  content: '';
  position: absolute;
  top: 0; left: 0; right: 0;
  height: 1px;
  background: linear-gradient(90deg, transparent, rgba(255,255,255,0.15), transparent);
}
.output-card-dark:hover {
  transform: translateY(-5px);
  background: linear-gradient(135deg, rgba(255,255,255,0.1) 0%, rgba(255,255,255,0.04) 100%);
}
.output-card-dark h3 {
  font-size: 1.05rem;
  font-weight: 700;
  color: #fff;
  margin: 0;
  letter-spacing: -0.01em;
}
.output-card-dark p {
  font-size: 0.75rem;
  color: rgba(255,255,255,0.5);
  line-height: 1.55;
  margin-top: 4px;
}

.output-item-row {
  display: flex;
  align-items: center;
  gap: 10px;
  padding: 10px 14px;
  border-radius: 12px;
  background: rgba(255,255,255,0.03);
  border: 1px solid rgba(255,255,255,0.04);
  font-size: 0.75rem;
  transition: all 0.2s ease;
}
.output-item-row:hover {
  background: rgba(255,255,255,0.07);
  transform: translateX(4px);
}
.output-item-dot {
  width: 6px;
  height: 6px;
  border-radius: 50%;
  flex-shrink: 0;
}
.output-item-label {
  color: rgba(255,255,255,0.55);
  flex: 1;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}
.output-item-label strong {
  color: #fff;
  font-weight: 700;
}

/* ─── TEAM SLIDE ─── */
.team-grid {
  display: grid;
  grid-template-columns: repeat(12, minmax(0, 1fr));
  gap: 6px;
  width: 100%;
  max-width: 920px;
  margin: -10px auto 0;
  align-content: start;
}

.team-item {
  grid-column: span 3;
  min-height: 110px;
  background:
    linear-gradient(180deg, rgba(15, 23, 42, 0.78) 0%, rgba(15, 23, 42, 0.56) 100%);
  backdrop-filter: blur(12px);
  -webkit-backdrop-filter: blur(12px);
  border: 1px solid rgba(148, 163, 184, 0.14);
  border-radius: 14px;
  padding: 8px 8px 7px;
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  justify-content: flex-start;
  gap: 5px;
  transition: all 0.4s cubic-bezier(.22,1,.36,1);
  position: relative;
  overflow: hidden;
  box-shadow: 0 12px 24px rgba(15, 23, 42, 0.2);
}

.team-item--wide {
  grid-column: span 3;
  min-height: 110px;
}

.team-item::before {
  content: '';
  position: absolute;
  inset: 0;
  background:
    radial-gradient(circle at top, rgba(129, 140, 248, 0.16), transparent 52%);
  pointer-events: none;
}

.team-item::after {
  content: '';
  position: absolute;
  inset: 0 auto auto 0;
  width: 100%;
  height: 2px;
  background: linear-gradient(90deg, #818cf8 0%, #34d399 100%);
  opacity: 0.85;
}

.team-item:hover {
  border-color: rgba(129, 140, 248, 0.4);
  transform: translateY(-5px);
  box-shadow: 0 24px 44px rgba(15, 23, 42, 0.3), 0 0 16px rgba(129, 140, 248, 0.1);
}

.team-img-wrap {
  width: 38px;
  height: 38px;
  flex-shrink: 0;
  border-radius: 50%;
  padding: 1.5px;
  background: linear-gradient(135deg, #818cf8, #34d399);
  box-shadow: 0 7px 14px rgba(15, 23, 42, 0.2);
}

.team-img-wrap img {
  width: 100%;
  height: 100%;
  border-radius: 50%;
  object-fit: cover;
  border: 2px solid #0f172a;
}

.team-text {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  gap: 3px;
  flex: 1;
  width: 100%;
}

.team-name {
  font-size: 0.54rem;
  font-weight: 800;
  color: #fff;
  letter-spacing: -0.01em;
  line-height: 1.05;
  min-height: 1.9em;
  display: flex;
  align-items: flex-end;
  justify-content: center;
}

.team-role {
  font-size: 0.38rem;
  color: rgba(255, 255, 255, 0.66);
  line-height: 1.18;
  font-weight: 600;
  letter-spacing: 0.02em;
  max-width: 16ch;
  margin: 0 auto;
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
<div class="hero-bg">
  <div class="hero-blob hb-1"></div>
  <div class="hero-blob hb-2"></div>
  <div class="hero-blob hb-3"></div>
</div>

<div class="relative z-10 flex flex-col items-center justify-center h-full gap-6">
  <div class="hero-subtitle">Hack4Innovation Bicocca · March 27, 2026</div>

  <h1 class="hero-title"><em>Hire<span>Light</span></em></h1>

  <p class="hero-desc">
    Spot top talent at first glance.<br/>
    Faster screening, clearer decisions, zero manual drag.
  </p>

</div>

<!--
"Good evening everyone, my name is Andrea and today we will present **HireLight**, our AI solution to make hiring faster and smarter.
-->

---

<!-- SLIDE 2: THE PROBLEM -->
<div class="prob-bg"></div>

<div class="relative z-10 px-14 pt-0 pb-6 h-full flex flex-col">

  <div class="prob-header mb-1">
    <span class="prob-eyebrow">The problem</span>
    <h2 class="prob-title">CV screening is <em>broken</em></h2>
    <p class="prob-subtitle">Recruiters lose hours every week on repetitive, subjective, unmeasurable tasks.</p>
  </div>

  <div class="prob-grid flex-1">
    <div class="prob-item" v-click="1">
      <div class="prob-item-num">01</div>
      <div class="prob-icon-wrap pi-amber">⏱️</div>
      <h3>Manual and isolated management</h3>
      <p>CVs via email handled one by one, with no automation. Time grows, quality doesn't.</p>
    </div>
    <div class="prob-item" v-click="2">
      <div class="prob-item-num">02</div>
      <div class="prob-icon-wrap pi-rose">⚖️</div>
      <h3>Subjective evaluations</h3>
      <p>No shared standard: bias and inconsistency in decisions, valid candidates excluded by mistake.</p>
    </div>
    <div class="prob-item" v-click="3">
      <div class="prob-item-num">03</div>
      <div class="prob-icon-wrap pi-indigo">📊</div>
      <h3>Zero KPI visibility</h3>
      <p>No data, no tracking. Without metrics the process cannot be measured — and cannot improve.</p>
    </div>
  </div>

  <div class="prob-stats-row">
    <div class="prob-stat" v-click="1">
      <div class="prob-stat-num" style="color: #fbbf24;">23h</div>
      <div class="prob-stat-label" style="color: rgba(251,191,36,0.7);">per week spent on manual screening</div>
      <div class="prob-stat-source">Instant Impact Recruiting Report</div>
    </div>
    <div class="prob-divider" v-click="2"></div>
    <div class="prob-stat" v-click="2">
      <div class="prob-stat-num" style="color: #f87171;">40%</div>
      <div class="prob-stat-label" style="color: rgba(248,113,113,0.7);">perceived inefficiency in the hiring process</div>
      <div class="prob-stat-source">PwC Annual Global CEO Survey</div>
    </div>
    <div class="prob-divider" v-click="3"></div>
    <div class="prob-stat" v-click="3">
      <div class="prob-stat-num" style="color: #a78bfa;">0 KPI</div>
      <div class="prob-stat-label" style="color: rgba(167,139,250,0.7);">data visibility for 30% of companies</div>
      <div class="prob-stat-source">Modern Measures of Talent Acquisition</div>
    </div>
  </div>

</div>

<!--
In fact Small and big companies have the same big problem: **hairing is slow.**

Recruiters lose hours every week on repetitive and  sabjektive tasks.
This can be a problem because it can lead to manual and isolated management,
sabjektive evaluation,
and ziro  KPI visibility.

 Just think that in a PwC report  the hairing prosess is considered inefficency in 40% of cases.
-->

---

<!-- SLIDE 3: THE SOLUTION — CONCEPT -->
<div class="sol-bg"></div>
<div class="relative z-10 px-14 py-2 h-full flex flex-col justify-between">
  <div class="prob-header mb-0 text-center">
    <span class="prob-eyebrow">The solution</span>
    <h2 class="prob-title">The <em>HireLight</em> Intelligence Layer</h2>
    <p class="prob-subtitle" style="margin-top:2px;">Transforming data into informed decisions, ethically and instantly.</p>
  </div>
  <div class="prob-grid flex-1" style="gap:10px; margin-top:10px;">
    <div class="prob-item" v-click style="padding: 14px 16px; gap: 8px;">
      <div class="prob-item-num">01</div>
      <div class="prob-icon-wrap pi-amber" style="width:36px; height:36px; font-size:1.1rem;">🧩</div>
      <h3>Multi-Feature Extraction</h3>
      <p style="font-size:0.7rem; line-height:1.4;">Hard skills, soft skills, and experiences are extracted to provide HR teams with deep, structured insights for <strong>informed decisions</strong>.</p>
    </div>
    <div class="prob-item" v-click style="padding: 14px 16px; gap: 8px;">
      <div class="prob-item-num">02</div>
      <div class="prob-icon-wrap pi-rose" style="width:36px; height:36px; font-size:1.1rem;">⚖️</div>
      <h3>AI Act Compliant Scoring</h3>
      <p style="font-size:0.7rem; line-height:1.4;">Ethical meritocracy: the scoring model has access <strong>only to Experience and Education</strong> sections to ensure objective, bias-free evaluations.</p>
    </div>
    <div class="prob-item" v-click style="padding: 14px 16px; gap: 8px;">
      <div class="prob-item-num">03</div>
      <div class="prob-icon-wrap pi-indigo" style="width:36px; height:36px; font-size:1.1rem;">⚡</div>
      <h3>Active Intelligence</h3>
      <p style="font-size:0.7rem; line-height:1.4;">Unlike <strong>Traditional ATS</strong> (passive storage), HireLight proactively identifies talent and calculates fit in real-time.</p>
    </div>
  </div>
  <div class="prob-stats-row" style="margin-top:2px; padding-top:4px;">
    <div class="prob-stat" v-click="4">
      <div class="prob-stat-num" style="color:#818cf8;">-75%</div>
      <div class="prob-stat-label" style="color:rgba(129,140,248,0.7);">Manual Screening Effort</div>
      <div class="prob-stat-source">LinkedIn Future of Work Report (2023)</div>
    </div>
    <div class="prob-divider" v-click="4"></div>
    <div class="prob-stat" v-click="4">
      <div class="prob-stat-num" style="color:#34d399;">100%</div>
      <div class="prob-stat-label" style="color:rgba(52,211,153,0.7);">AI Act Transparency</div>
    </div>
    <div class="prob-divider" v-click="4"></div>
    <div class="prob-stat" v-click="4">
      <div class="prob-stat-num" style="color:#fbbf24;">AI-Powered</div>
      <div class="prob-stat-label" style="color:rgba(251,191,36,0.7);">Vs Traditional ATS Silos</div>
    </div>
  </div>
</div>

<!--
"Our solution is an **Intelligence Layer**.
1. We go beyond simple keywords: we extract multiple features—from hard skills to growth potential—so you can make **informed decisions**.
2. Ethics is at our core. We are **AI Act compliant**: our scoring model only looks at work experience and education to guarantee a bias-free, merit-based process.
3. While traditional ATS are passive silos, HireLight is **active intelligence**.
And the impact is real: according to LinkedIn, AI can reduce manual screening effort by 75%."
-->

---

<!-- SLIDE 4: TECHNICAL STACK -->
<div class="sol-bg"></div>
<div class="relative z-10 px-14 py-2 h-full flex flex-col justify-between">
  <div class="prob-header mb-1">
    <span class="prob-eyebrow">Architecture</span>
    <h2 class="prob-title">The <em>Engine</em> Under the Hood</h2>
    <p class="prob-subtitle" style="margin-top:2px;">A robust, modular, and cloud-native pipeline built for scale.</p>
  </div>
  
  <div class="flex-1 flex items-center justify-center p-2">
     <!-- Placeholder for a simple architecture diagram or icon set -->
     <div class="grid grid-cols-3 gap-6 w-full max-w-5xl">
        <div class="output-card-dark p-4 flex flex-col items-center gap-3 text-center" v-click>
           <div class="prob-stat-num" style="color:#818cf8; font-size:1.8rem;">28+</div>
           <div class="text-[0.85rem] font-bold">Interconnected Nodes</div>
           <p class="text-[0.65rem] opacity-70 leading-relaxed">Parsing attachments, extracting multi-dimensional data, and orchestrating the candidate lifecycle.</p>
        </div>
        <div class="output-card-dark p-4 flex flex-col items-center gap-3 text-center" v-click>
           <div class="prob-stat-num" style="color:#fbbf24; font-size:1.8rem;">Hybrid</div>
           <div class="text-[0.85rem] font-bold">Data Ingestion</div>
           <p class="text-[0.65rem] opacity-70 leading-relaxed">Not only emails: native API integration with <strong>LinkedIn, Indeed, and corporate HR portals</strong>.</p>
        </div>
        <div class="output-card-dark p-4 flex flex-col items-center gap-3 text-center" v-click>
           <div class="prob-stat-num" style="color:#34d399; font-size:1.8rem;">Jury</div>
           <div class="text-[0.85rem] font-bold">Model Intelligence</div>
           <p class="text-[0.65rem] opacity-70 leading-relaxed">Supports <strong>Local LLMs</strong>, OpenAI APIs, or a <strong>Majority-Voting Jury</strong> of multiple models for unmatched reliability.</p>
        </div>
     </div>
  </div>

  <div class="prob-stats-row justify-center gap-12" style="margin-top:2px; padding-top:4px;">
    <div class="prob-stat" v-click="3">
      <img src="./img/n8n.png" style="height:35px;width:35px;object-fit:contain;margin:0 auto 6px;display:block;" />
      <div class="prob-stat-label">Automation</div>
    </div>
    <div class="prob-stat" v-click="3">
      <img src="./img/oai.png" style="height:35px;width:35px;object-fit:contain;margin:0 auto 6px;display:block;" />
      <div class="prob-stat-label">Intelligence</div>
    </div>
    <div class="prob-stat" v-click="3">
      <img src="./img/supabase.png" style="height:35px;width:35px;object-fit:contain;margin:0 auto 6px;display:block;" />
      <div class="prob-stat-label">Database</div>
    </div>
    <div class="prob-stat" v-click="3">
      <img src="./img/nextjs.png" style="height:35px;width:35px;object-fit:contain;margin:0 auto 6px;display:block;" />
      <div class="prob-stat-label">Interface</div>
    </div>
  </div>
</div>

<!--
"For the technical jury: the engine is modular and channel-agnostic. While we process emails out-of-the-box, the architecture supports direct API integration with 3rd-party portals. Finally, our Intelligence layer is model-agnostic: we can deploy local LLMs for privacy, or use a 'Jury of Models' with majority voting to guarantee objective and reliable scoring."
-->

---

<!-- SLIDE 5: GENERATED VALUE -->
<div class="sol-bg" transition="slide-up"></div>

<div class="relative z-10 px-14 pt-0 pb-2 h-full flex flex-col -mt-2">
  <div class="prob-header mb-1">
    <span class="prob-eyebrow">Impact</span>
    <h2 class="prob-title">The <em>value</em> we create</h2>
    <p class="prob-subtitle">Operational efficiency, standardization, and modularity without compromise.</p>
  </div>

  <div class="grid grid-cols-2 gap-5 flex-1 items-start">
    <div class="value-card" v-click>
      <div class="value-number" style="color: #34d399;">10×</div>
      <div class="value-label">Efficiency</div>
      <div class="value-desc">Full workflow automation from initial screening to final notification.</div>
    </div>
    <div class="value-card" v-click>
      <div class="value-number" style="color: #818cf8;">100%</div>
      <div class="value-label">Standard</div>
      <div class="value-desc">Evaluation based on objective and certified parameters for every data batch.</div>
    </div>
    <div class="value-card" v-click>
      <div class="value-number" style="color: #fbbf24;">0€</div>
      <div class="value-label">Maintenance</div>
      <div class="value-desc">Cloud and no-code architecture that eliminates fixed server management costs.</div>
    </div>
    <div class="value-card" v-click>
      <div class="value-number" style="color: #f87171;">100%</div>
      <div class="value-label">Modular</div>
      <div class="value-desc">Agnostic workflow: choose the technology stack (ATS, CRM, HRIS) that fits best.</div>
    </div>
  </div>
</div>

<!--
In this slide, we show the value of our pipeline.”


“ In fact The whole hairing  prosess is automated, from screening to final notification.”

“All candidates are evaluated using the same objective criteria.


” Thanks to cloud and no-code tools, there are no server costs to manage.”


and finally “Any tools can be used depending on the needs. The process is completely modular and can be adapted to your needs.
-->

---

<!-- SLIDE 6: BUSINESS MODEL & STRATEGY -->
<div class="sol-bg" transition="slide-up"></div>
<div class="relative z-10 px-14 pt-2 pb-8 h-full flex flex-col">
  <div class="prob-header mb-12">
    <span class="prob-eyebrow">Strategy</span>
    <h2 class="prob-title"><em>Business</em> Model</h2>
    <p class="prob-subtitle">How we scale value in the HR Tech market.</p>
  </div>
  <div class="flex-1 flex items-center justify-center">
    <div class="output-card-dark w-full max-w-4xl p-10" style="box-shadow: 0 8px 32px rgba(79,70,229,0.15), 0 0 0 1px rgba(79,70,229,0.25);">
      <div class="grid grid-cols-3 gap-8">
        <div v-click class="flex flex-col items-center text-center gap-4 group cursor-default">
          <div class="output-icon group-hover:scale-110 group-hover:shadow-[0_0_20px_rgba(129,140,248,0.4)] transition-all duration-300" style="background:rgba(79,70,229,0.2);border:1px solid rgba(79,70,229,0.4);width:60px;height:60px;border-radius:16px;font-size:1.8rem;">💰</div>
          <div>
            <h3 style="color:#818cf8; font-size: 1.1rem; margin-bottom: 4px;">SaaS Subscription</h3>
            <p style="opacity: 0.6; font-size: 0.82rem; line-height: 1.4;">Flexible monthly pricing based on managed volumes.</p>
          </div>
        </div>
        <div v-click class="flex flex-col items-center text-center gap-4 border-l border-r border-white/10 px-6 group cursor-default">
          <div class="output-icon group-hover:scale-110 group-hover:shadow-[0_0_20px_rgba(52,211,153,0.4)] transition-all duration-300" style="background:rgba(16,185,129,0.2);border:1px solid rgba(16,185,129,0.4);width:60px;height:60px;border-radius:16px;font-size:1.8rem;">🎯</div>
          <div>
            <h3 style="color:#34d399; font-size: 1.1rem; margin-bottom: 4px;">Universal</h3>
            <p style="opacity: 0.6; font-size: 0.82rem; line-height: 1.4;">Startup, SMB or enterprise: it works for everyone.</p>
          </div>
        </div>
        <div v-click class="flex flex-col items-center text-center gap-4 group cursor-default">
          <div class="output-icon group-hover:scale-110 group-hover:shadow-[0_0_20px_rgba(251,191,36,0.4)] transition-all duration-300" style="background:rgba(251,191,36,0.2);border:1px solid rgba(251,191,36,0.4);width:60px;height:60px;border-radius:16px;font-size:1.8rem;">🚀</div>
          <div>
            <h3 style="color:#fbbf24; font-size: 1.1rem; margin-bottom: 4px;">Scalable Automation</h3>
            <p style="opacity: 0.6; font-size: 0.82rem; line-height: 1.4;">Grows with you: from 10 to 10,000 applications with no changes.</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>

<!--
"Our business plan is simple.
We offer a **monthly subscription**. Companies pay a small fee based on how many CVs they process.


It’s perfect for any size of company, from the largest to the smallest

And it grows with you, no matter how many applications you have, the resalt doesn’t change.

It’s a 'ready-to-go' system: you connect your email, and it starts working. No complicated setup needed."
-->

---

<!-- SLIDE 7: THE TEAM & ROLES -->
<div class="sol-bg" transition="slide-up"></div>

<div class="relative z-10 px-14 pt-0 pb-2 h-full flex flex-col -mt-2">
  <div class="prob-header mb-1">
    <span class="prob-eyebrow">The Team</span>
    <h2 class="prob-title">Who <em>we are</em></h2>
    <p class="prob-subtitle">Complementary skills for an innovative solution.</p>
  </div>

  <div class="team-grid">
    <div class="team-item">
      <div class="team-img-wrap">
        <img src="./img/af.png" alt="Andrea Feliziani" />
      </div>
      <div class="team-text">
        <h3 class="team-name">Andrea Feliziani</h3>
        <p class="team-role">UI/UX Designer & Front-end Developer</p>
      </div>
    </div>
    <div class="team-item">
      <div class="team-img-wrap">
        <img src="./img/mc.png" alt="Marco Cremaschi" />
      </div>
      <div class="team-text">
        <h3 class="team-name">Marco Cremaschi</h3>
        <p class="team-role">Unimib Professor & Researcher</p>
      </div>
    </div>
    <div class="team-item">
      <div class="team-img-wrap">
        <img src="./img/dv.png" alt="Davide Vanoncini" />
      </div>
      <div class="team-text">
        <h3 class="team-name">Davide Vanoncini</h3>
        <p class="team-role">Full-stack Developer & AI Specialist</p>
      </div>
    </div>
    <div class="team-item">
      <div class="team-img-wrap">
        <img src="./img/dc.png" alt="David Chieregato" />
      </div>
      <div class="team-text">
        <h3 class="team-name">David Chieregato</h3>
        <p class="team-role">Back-end Developer & AI Specialist</p>
      </div>
    </div>
    <div class="team-item team-item--wide">
      <div class="team-img-wrap">
        <img src="./img/ag.png" alt="Azizbek Gulomov" />
      </div>
      <div class="team-text">
        <h3 class="team-name">Azizbek Gulomov</h3>
        <p class="team-role">Front-end Designer</p>
      </div>
    </div>
    <div class="team-item team-item--wide">
      <div class="team-img-wrap">
        <img src="./img/lj.png" alt="Labhanshiv Jayan" />
      </div>
      <div class="team-text">
        <h3 class="team-name">Labhanshiv Jayan</h3>
        <p class="team-role">Researcher</p>
      </div>
    </div>
    <div class="team-item team-item--wide">
      <div class="team-img-wrap">
        <img src="./img/sa.png" alt="Siraj Ahmed" />
      </div>
      <div class="team-text">
        <h3 class="team-name">Siraj Ahmed</h3>
        <p class="team-role">Front-end Designer</p>
      </div>
    </div>
  </div>
</div>

<!--
in conclusion our team is made up of Andrea, Marco, Fabio, David, Azizbek, Labhanshiv, and Siraj.

we're done, thank you very much
-->

---

<!-- SLIDE 8: THANK YOU -->
<div class="thankyou-bg">
  <div class="thankyou-blob"></div>
</div>

<div class="relative z-10 flex flex-col items-center justify-center h-full text-center px-10">
  <div v-click class="mb-2">
    <h1 class="thankyou-title">Thank you<span>.</span></h1>
    <p class="thankyou-subtitle">Questions?</p>
  </div>

  <div v-click class="flex flex-wrap justify-center gap-4 mt-16">
    <span class="contact-pill shadow-xl">📍 Bicocca</span>
    <span class="contact-pill shadow-xl">📅 March 27, 2026</span>
    <span class="contact-pill shadow-xl">🏆 @Hack4Innovation</span>
  </div>
</div>
