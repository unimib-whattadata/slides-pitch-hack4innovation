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
  -webkit-text-fill-color: #4f46e5;
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
  transition: all 0.35s cubic-bezier(.22,1,.36,1);
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
  transition: all 0.35s cubic-bezier(.22,1,.36,1);
}

.contact-pill:hover {
  background: rgba(79,70,229,0.15);
  border-color: rgba(79,70,229,0.3);
  color: #818cf8;
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
<div class="prob-bg"></div>

<div class="relative z-10 px-14 py-6 h-full flex flex-col">

  <div class="prob-header mb-3">
    <span class="prob-eyebrow">Il problema</span>
    <h2 class="prob-title">Lo screening CV è <em>rotto</em></h2>
    <p class="prob-subtitle">I recruiter perdono ore ogni settimana su task ripetitivi, soggettivi, non misurabili.</p>
  </div>

  <div class="prob-grid flex-1">
    <div class="prob-item" v-click>
      <div class="prob-item-num">01</div>
      <div class="prob-icon-wrap pi-amber">⏱️</div>
      <h3>Gestione manuale e isolata</h3>
      <p>CV via email gestiti uno per uno, senza automazione. Il tempo cresce, la qualità no.</p>
    </div>
    <div class="prob-item" v-click>
      <div class="prob-item-num">02</div>
      <div class="prob-icon-wrap pi-rose">⚖️</div>
      <h3>Valutazioni soggettive</h3>
      <p>Nessuno standard condiviso: bias e inconsistenza nelle decisioni, candidati validi esclusi per errore.</p>
    </div>
    <div class="prob-item" v-click>
      <div class="prob-item-num">03</div>
      <div class="prob-icon-wrap pi-indigo">📊</div>
      <h3>Zero visibilità KPI</h3>
      <p>Nessun dato, nessun tracciamento. Senza metriche il processo non si misura — e non migliora.</p>
    </div>
  </div>

  <div class="prob-stats-row">
    <div class="prob-stat" v-click>
      <div class="prob-stat-num" style="color: #fbbf24;">23h</div>
      <div class="prob-stat-label" style="color: rgba(251,191,36,0.7);">settimana dedicata allo screening manuale</div>
      <div class="prob-stat-source">Instant Impact Recruiting Report</div>
    </div>
    <div class="prob-divider"></div>
    <div class="prob-stat" v-click>
      <div class="prob-stat-num" style="color: #f87171;">40%</div>
      <div class="prob-stat-label" style="color: rgba(248,113,113,0.7);">di inefficienza percepita nel processo di hiring</div>
      <div class="prob-stat-source">PwC Annual Global CEO Survey</div>
    </div>
    <div class="prob-divider"></div>
    <div class="prob-stat" v-click>
      <div class="prob-stat-num" style="color: #a78bfa;">0 KPI</div>
      <div class="prob-stat-label" style="color: rgba(167,139,250,0.7);">visibilità sui dati per il 30% delle aziende</div>
      <div class="prob-stat-source">Modern Measures of Talent Acquisition</div>
    </div>
  </div>

</div>

---

<!-- SLIDE 3: LA SOLUZIONE — PIPELINE -->
<div class="sol-bg"></div>
<div class="relative z-10 px-14 py-6 h-full flex flex-col">
  <div class="prob-header mb-3">
    <span class="prob-eyebrow">La soluzione</span>
    <h2 class="prob-title">Pipeline <em>automatizzata</em> end-to-end</h2>
    <p class="prob-subtitle">Da email a candidate scoring in pochi minuti, zero intervento manuale.</p>
  </div>
  <div class="prob-grid flex-1">
    <div class="prob-item" v-click>
      <div class="prob-item-num">01</div>
      <div class="prob-icon-wrap pi-amber">📧</div>
      <h3>Ingestion Email</h3>
      <p>Gmail trigger ogni 4h — scarica email con allegati non lette e le instrada nella pipeline.</p>
    </div>
    <div class="prob-item" v-click>
      <div class="prob-item-num">02</div>
      <div class="prob-icon-wrap pi-rose">📂</div>
      <h3>Smart File Routing</h3>
      <p>Classificazione automatica → CV, Portfolio, Altro su Google Drive.</p>
    </div>
    <div class="prob-item" v-click>
      <div class="prob-item-num">03</div>
      <div class="prob-icon-wrap pi-indigo">🤖</div>
      <h3>AI Extraction + Scoring</h3>
      <p>GPT-5 estrae dati e valuta il CV su metriche personalizzate dall'azienda.</p>
    </div>
  </div>
  <div class="prob-stats-row">
    <div class="prob-stat" v-click="4">
      <div class="prob-stat-num" style="color:#818cf8;">28</div>
      <div class="prob-stat-label" style="color:rgba(129,140,248,0.7);">nodi n8n</div>
    </div>
    <div class="prob-divider" v-click="5"></div>
    <div class="prob-stat" v-click="5">
      <img src="./img/n8n.png" style="height:30px;width:30px;object-fit:contain;margin:0 auto 6px;display:block;" />
      <div class="prob-stat-label">n8n</div>
    </div>
    <div class="prob-divider" v-click="5"></div>
    <div class="prob-stat" v-click="5">
      <img src="./img/oai.png" style="height:30px;width:30px;object-fit:contain;margin:0 auto 6px;display:block;" />
      <div class="prob-stat-label">OpenAI</div>
    </div>
    <div class="prob-divider" v-click="5"></div>
    <div class="prob-stat" v-click="5">
      <img src="./img/sheets.png" style="height:30px;width:30px;object-fit:contain;margin:0 auto 6px;display:block;" />
      <div class="prob-stat-label">Google Sheets</div>
    </div>
    <div class="prob-divider" v-click="5"></div>
    <div class="prob-stat" v-click="5">
      <img src="./img/slack.png" style="height:30px;width:30px;object-fit:contain;margin:0 auto 6px;display:block;" />
      <div class="prob-stat-label">Slack</div>
    </div>
    <div class="prob-divider" v-click="5"></div>
    <div class="prob-stat" v-click="5">
      <img src="./img/nextjs.png" style="height:30px;width:30px;object-fit:contain;margin:0 auto 6px;display:block;" />
      <div class="prob-stat-label">Next.js</div>
    </div>
  </div>
</div>

---
clicks: 3
---

<!-- SLIDE 4: OUTPUT — DASHBOARD + EXCEL -->
<div class="sol-bg"></div>
<div class="relative z-10 px-14 pt-0 pb-4 h-full flex flex-col">
  <div class="prob-header mb-8">
    <span class="prob-eyebrow">Output concreti</span>
    <h2 class="prob-title"><em>Dashboard</em> & <em style="color:#34d399;">Report</em> strutturato</h2>
  </div>
  <div class="relative flex-1">
    <div :style="{ opacity: ($clicks === 0 || $clicks === 2) ? 1 : 0, pointerEvents: ($clicks === 0 || $clicks === 2) ? 'auto' : 'none', transition: 'opacity 0.4s ease' }" style="position:absolute;inset:0;display:grid;grid-template-columns:1fr 1fr;gap:24px;align-items:start;">
      <div class="output-card-dark" style="box-shadow: 0 8px 32px rgba(79,70,229,0.12), 0 0 0 1px rgba(79,70,229,0.2);">
        <div class="flex items-center gap-4 mb-5">
          <div class="output-icon" style="background:rgba(79,70,229,0.15);border:1px solid rgba(79,70,229,0.3);width:48px;height:48px;border-radius:14px;font-size:1.4rem;">📊</div>
          <div>
            <h3 style="color:#818cf8;">Dashboard interattiva</h3>
            <p>Next.js + Supabase + Tailwind</p>
          </div>
        </div>
        <div style="display:flex;flex-direction:column;gap:10px;">
          <div class="output-item-row"><span class="output-item-dot" style="background:#818cf8;"></span><span class="output-item-label"><strong>KPI cards</strong> — totale candidati, nuovi oggi, tasso assunzione</span></div>
          <div class="output-item-row"><span class="output-item-dot" style="background:#818cf8;"></span><span class="output-item-label"><strong>Grafici pipeline</strong> — distribuzione per stato</span></div>
          <div class="output-item-row"><span class="output-item-dot" style="background:#818cf8;"></span><span class="output-item-label"><strong>Tabella candidati</strong> — ricerca, filtri, dettaglio</span></div>
          <div class="output-item-row"><span class="output-item-dot" style="background:#818cf8;"></span><span class="output-item-label"><strong>Filtri temporali</strong> — oggi, 7gg, 30gg, tutti</span></div>
          <div class="output-item-row"><span class="output-item-dot" style="background:#818cf8;"></span><span class="output-item-label"><strong>Pipeline Kanban</strong> — gestione visuale degli stati</span></div>
        </div>
      </div>
      <div class="output-card-dark" style="box-shadow: 0 8px 32px rgba(16,185,129,0.12), 0 0 0 1px rgba(16,185,129,0.2);">
        <div class="flex items-center gap-4 mb-5">
          <div class="output-icon" style="background:rgba(16,185,129,0.15);border:1px solid rgba(16,185,129,0.3);width:48px;height:48px;border-radius:14px;font-size:1.4rem;">📋</div>
          <div>
            <h3 style="color:#34d399;">Report Excel Strutturato</h3>
            <p>Google Sheets automation</p>
          </div>
        </div>
        <div style="display:flex;flex-direction:column;gap:10px;">
          <div class="output-item-row"><span class="output-item-dot" style="background:#34d399;"></span><span class="output-item-label"><strong>Candidato</strong> — Mario Rossi</span></div>
          <div class="output-item-row"><span class="output-item-dot" style="background:#34d399;"></span><span class="output-item-label"><strong>Score</strong> — Idoneo (58/70)</span></div>
          <div class="output-item-row"><span class="output-item-dot" style="background:#34d399;"></span><span class="output-item-label"><strong>Ruolo dedotto</strong> — Content Creator</span></div>
          <div class="output-item-row"><span class="output-item-dot" style="background:#34d399;"></span><span class="output-item-label"><strong>Email / Tel / LinkedIn</strong> — ✅ Estratti auto</span></div>
          <div class="output-item-row"><span class="output-item-dot" style="background:#34d399;"></span><span class="output-item-label"><strong>CV / Portfolio</strong> — 🔗 Link Google Drive</span></div>
        </div>
      </div>
    </div>
    <div :style="{ opacity: $clicks === 1 ? 1 : 0, pointerEvents: $clicks === 1 ? 'auto' : 'none', transition: 'opacity 0.4s ease' }" style="position:absolute;inset:0;display:flex;gap:24px;">
      <div class="output-card-dark" style="box-shadow: 0 8px 32px rgba(79,70,229,0.12), 0 0 0 1px rgba(79,70,229,0.2);flex:1;align-self:start;">
        <div class="flex items-center gap-4 mb-5">
          <div class="output-icon" style="background:rgba(79,70,229,0.15);border:1px solid rgba(79,70,229,0.3);width:48px;height:48px;border-radius:14px;font-size:1.4rem;">📊</div>
          <div>
            <h3 style="color:#818cf8;">Dashboard interattiva</h3>
            <p>Visualizzazione dati in tempo reale</p>
          </div>
        </div>
        <div style="display:flex;flex-direction:column;gap:8px;">
          <div class="output-item-row"><span class="output-item-dot" style="background:#818cf8;"></span><span class="output-item-label"><strong>KPI cards</strong> — totale candidati, nuovi oggi, tasso assunzione</span></div>
          <div class="output-item-row"><span class="output-item-dot" style="background:#818cf8;"></span><span class="output-item-label"><strong>Grafici pipeline</strong> — distribuzione per stato</span></div>
          <div class="output-item-row"><span class="output-item-dot" style="background:#818cf8;"></span><span class="output-item-label"><strong>Tabella candidati</strong> — ricerca, filtri, dettaglio</span></div>
          <div class="output-item-row"><span class="output-item-dot" style="background:#818cf8;"></span><span class="output-item-label"><strong>Filtri temporali</strong> — oggi, 7gg, 30gg, tutti</span></div>
          <div class="output-item-row"><span class="output-item-dot" style="background:#818cf8;"></span><span class="output-item-label"><strong>Pipeline Kanban</strong> — gestione visuale degli stati</span></div>
        </div>
      </div>
      <div style="flex:1.4;display:flex;align-items:center;justify-content:center;">
        <img src="./img/dashboard.png" style="width:100%;height:100%;object-fit:contain;border-radius:16px;box-shadow: 0 12px 48px rgba(0,0,0,0.4);" />
      </div>
    </div>
    <div :style="{ opacity: $clicks === 3 ? 1 : 0, pointerEvents: $clicks === 3 ? 'auto' : 'none', transition: 'opacity 0.4s ease' }" style="position:absolute;inset:0;display:flex;gap:24px;">
      <div class="output-card-dark" style="box-shadow: 0 8px 32px rgba(16,185,129,0.12), 0 0 0 1px rgba(16,185,129,0.2);flex:1;align-self:start;">
        <div class="flex items-center gap-4 mb-5">
          <div class="output-icon" style="background:rgba(16,185,129,0.15);border:1px solid rgba(16,185,129,0.3);width:48px;height:48px;border-radius:14px;font-size:1.4rem;">📋</div>
          <div>
            <h3 style="color:#34d399;">Report Strutturato</h3>
            <p>Database excel-like automatizzato</p>
          </div>
        </div>
        <div style="display:flex;flex-direction:column;gap:8px;">
          <div class="output-item-row"><span class="output-item-dot" style="background:#34d399;"></span><span class="output-item-label"><strong>Candidato</strong> — Mario Rossi</span></div>
          <div class="output-item-row"><span class="output-item-dot" style="background:#34d399;"></span><span class="output-item-label"><strong>Score</strong> — Idoneo (58/70)</span></div>
          <div class="output-item-row"><span class="output-item-dot" style="background:#34d399;"></span><span class="output-item-label"><strong>Ruolo dedotto</strong> — Content Creator</span></div>
          <div class="output-item-row"><span class="output-item-dot" style="background:#34d399;"></span><span class="output-item-label"><strong>Email / Tel / LinkedIn</strong> — ✅ Estratti auto</span></div>
          <div class="output-item-row"><span class="output-item-dot" style="background:#34d399;"></span><span class="output-item-label"><strong>CV / Portfolio</strong> — 🔗 Link Google Drive</span></div>
        </div>
      </div>
      <div style="flex:1.4;display:flex;align-items:center;justify-content:center;">
        <img src="./img/sheets2.png" style="width:100%;height:100%;object-fit:contain;border-radius:16px;box-shadow: 0 12px 48px rgba(0,0,0,0.4);" />
      </div>
    </div>
  </div>
</div>

---

<!-- SLIDE 5: VALORE GENERATO -->
<div class="sol-bg" transition="slide-up"></div>

<div class="relative z-10 px-14 pt-2 pb-8 h-full flex flex-col">
  <div class="prob-header mb-4">
    <span class="prob-eyebrow">Impatto</span>
    <h2 class="prob-title">Il <em>valore</em> che creiamo</h2>
    <p class="prob-subtitle">Efficienza operativa, standardizzazione e modularità senza compromessi.</p>
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

<!-- SLIDE 6: BUSINESS MODEL & POSIZIONAMENTO -->
<div class="sol-bg" transition="slide-up"></div>
<div class="relative z-10 px-14 pt-2 pb-8 h-full flex flex-col">
  <div class="prob-header mb-8">
    <span class="prob-eyebrow">Strategia</span>
    <h2 class="prob-title">Business <em style="color:#818cf8; text-shadow: 0 0 20px rgba(129,140,248,0.6);">Model</em> & <em style="color:#818cf8; text-shadow: 0 0 20px rgba(129,140,248,0.6);">Posizionamento</em></h2>
    <p class="prob-subtitle">Come scaliamo il valore nel mercato HR Tech.</p>
  </div>
  <div v-click class="hidden"></div>
  <div v-click class="hidden"></div>
  <div v-click class="hidden"></div>
  <div class="flex gap-10 flex-1 items-start transition-all duration-500">
    <div class="output-card-dark transition-all duration-700 ease-in-out" :style="{ flex: $clicks === 1 ? '1 0 100%' : ($clicks === 3 ? '0 0 0%' : '1 0 50%'), opacity: $clicks === 3 ? 0 : 1, pointerEvents: $clicks === 3 ? 'none' : 'auto', transform: $clicks === 3 ? 'translateX(-40px)' : 'none', padding: $clicks === 3 ? '0' : '24px', borderWidth: $clicks === 3 ? '0' : '1px' }" style="box-shadow: 0 8px 32px rgba(79,70,229,0.15), 0 0 0 1px rgba(79,70,229,0.25);">
      <div class="flex items-center gap-5 mb-6 whitespace-nowrap">
        <div class="output-icon" style="background:rgba(79,70,229,0.2);border:1px solid rgba(79,70,229,0.4);width:52px;height:52px;border-radius:14px;font-size:1.5rem;">💰</div>
        <div>
          <h3 style="color:#818cf8; font-size: 1.2rem;">Business Model</h3>
          <p style="opacity: 0.6;">SaaS & Performance based</p>
        </div>
      </div>
      <div v-if="$clicks !== 1" style="display:flex;flex-direction:column;gap:12px;">
        <div class="output-item-row"><span class="output-item-dot" style="background:#818cf8;"></span><span class="output-item-label"><strong>Abbonamento SaaS</strong> — Tiered pricing mensile per volumi</span></div>
        <div class="output-item-row"><span class="output-item-dot" style="background:#818cf8;"></span><span class="output-item-label"><strong>Pay-per-Credit</strong> — Flessibilità per picchi stagionali</span></div>
        <div class="output-item-row"><span class="output-item-dot" style="background:#818cf8;"></span><span class="output-item-label"><strong>Enterprise API</strong> — One-time fee per setup custom</span></div>
      </div>
      <div v-else class="grid grid-cols-3 gap-4 animate-fade-in">
        <div class="expanded-item">
          <div class="expanded-icon">📈</div>
          <h4 class="expanded-title">SaaS Tiered</h4>
          <p class="expanded-desc">Pricing mensile scalabile basato sui volumi gestiti.</p>
        </div>
        <div class="expanded-item">
          <div class="expanded-icon">💳</div>
          <h4 class="expanded-title">Pay-per-Credit</h4>
          <p class="expanded-desc">Massima flessibilità per gestire picchi senza costi fissi.</p>
        </div>
        <div class="expanded-item">
          <div class="expanded-icon">🔌</div>
          <h4 class="expanded-title">Enterprise API</h4>
          <p class="expanded-desc">Integrazione profonda e setup custom per workflow complessi.</p>
        </div>
      </div>
    </div>
    <div class="output-card-dark transition-all duration-700 ease-in-out" :style="{ flex: $clicks === 3 ? '1 0 100%' : ($clicks === 1 ? '0 0 0%' : '1 0 50%'), opacity: $clicks === 1 ? 0 : 1, pointerEvents: $clicks === 1 ? 'none' : 'auto', transform: $clicks === 1 ? 'translateX(40px)' : 'none', padding: $clicks === 1 ? '0' : '24px', borderWidth: $clicks === 1 ? '0' : '1px' }" style="box-shadow: 0 8px 32px rgba(16,185,129,0.15), 0 0 0 1px rgba(16,185,129,0.25);">
      <div class="flex items-center gap-5 mb-6 whitespace-nowrap">
        <div class="output-icon" style="background:rgba(16,185,129,0.2);border:1px solid rgba(16,185,129,0.4);width:52px;height:52px;border-radius:14px;font-size:1.5rem;">🎯</div>
        <div>
          <h3 style="color:#34d399; font-size: 1.2rem;">Posizionamento</h3>
          <p style="opacity: 0.6;">Strategicità & Integrazione</p>
        </div>
      </div>
      <div v-if="$clicks !== 3" style="display:flex;flex-direction:column;gap:12px;">
        <div class="output-item-row"><span class="output-item-dot" style="background:#34d399;"></span><span class="output-item-label"><strong>Target</strong> — HR Dept mid-large enterprise (Tech/Finance)</span></div>
        <div class="output-item-row"><span class="output-item-dot" style="background:#34d399;"></span><span class="output-item-label"><strong>Differenziatore</strong> — No-code & AI vs Legacy Systems</span></div>
        <div class="output-item-row"><span class="output-item-dot" style="background:#34d399;"></span><span class="output-item-label"><strong>Valore</strong> — Velocità 10x e scoring standardizzato</span></div>
      </div>
      <div v-else class="grid grid-cols-3 gap-4 animate-fade-in">
        <div class="expanded-item">
          <div class="expanded-icon">🏢</div>
          <h4 class="expanded-title">Mid-Large Ent</h4>
          <p class="expanded-desc">Soluzione per dipartimenti HR in settori Tech e Finance.</p>
        </div>
        <div class="expanded-item">
          <div class="expanded-icon">🚀</div>
          <h4 class="expanded-title">No-code & AI</h4>
          <p class="expanded-desc">La velocità dell'AI unita alla semplicità del no-code.</p>
        </div>
        <div class="expanded-item">
          <div class="expanded-icon">⚡</div>
          <h4 class="expanded-title">Valore 10x</h4>
          <p class="expanded-desc">Screening più veloce e scoring oggettivo su ogni candidato.</p>
        </div>
      </div>
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
