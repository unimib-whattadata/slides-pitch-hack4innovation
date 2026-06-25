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

<!-- SLIDE 1: HERO -->
<div class="hero-bg">
  <div class="hero-blob hb-1"></div>
  <div class="hero-blob hb-2"></div>
  <div class="hero-blob hb-3"></div>
</div>

<div class="relative z-10 flex flex-col items-center justify-center h-full gap-6">
  <div class="hero-meta">
    <div class="hero-updated">Updated · June 25, 2026</div>
  </div>

  <h1 class="hero-title"><em>Hire<span>Light</span></em></h1>

  <p class="hero-desc">
    Identify top candidates at a glance.<br/>
    Faster screening, fairer decisions, less manual work.
  </p>

  <div class="hero-contact">
    <span>Contact</span>
    <span class="hero-contact-dot">·</span>
    <strong>info@whattadata.it</strong>
  </div>

</div>

<!--
"Good evening everyone. I'm Andrea, and today we're presenting **HireLight**: an AI intelligence layer that helps hiring teams screen CVs faster, more consistently, and with clearer evidence."
-->

---

<!-- SLIDE 2: THE PROBLEM -->
<div class="prob-bg"></div>

<div class="relative z-10 px-14 pt-0 pb-6 h-full flex flex-col">

  <div class="prob-header mb-1">
    <span class="prob-eyebrow">The problem</span>
    <h2 class="prob-title">CV screening is <em>broken</em></h2>
    <p class="prob-subtitle">Recruiters spend hours on repetitive screening while quality, consistency, and visibility stay hard to control.</p>
  </div>

  <div class="prob-grid flex-1">
    <div class="prob-item" v-click="1">
      <div class="prob-item-corner-icon pi-amber" aria-hidden="true">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.7" stroke-linecap="round" stroke-linejoin="round">
          <path d="M12 6v6l4 2" />
          <path d="M21 12a9 9 0 1 1-9-9" />
        </svg>
      </div>
      <div class="prob-item-num">01</div>
      <h3>Scattered manual workflows</h3>
      <p>Applications arrive from emails, portals, and forms, then get reviewed one by one. Volume rises faster than quality.</p>
    </div>
    <div class="prob-item" v-click="2">
      <div class="prob-item-corner-icon pi-rose" aria-hidden="true">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.7" stroke-linecap="round" stroke-linejoin="round">
          <path d="M12 3v18" />
          <path d="M3 7h18" />
          <path d="M4 7l3.5 5.5a2 2 0 0 0 1.69.93h5.62a2 2 0 0 0 1.69-.93L20 7" />
        </svg>
      </div>
      <div class="prob-item-num">02</div>
      <h3>Subjective shortlisting</h3>
      <p>No shared rubric means bias, inconsistent decisions, and strong candidates can be missed too early.</p>
    </div>
    <div class="prob-item" v-click="3">
      <div class="prob-item-corner-icon pi-indigo" aria-hidden="true">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.7" stroke-linecap="round" stroke-linejoin="round">
          <path d="M3 3v18h18" />
          <path d="M7 14.5v-3" />
          <path d="M12 14.5v-7" />
          <path d="M17 14.5v-5" />
        </svg>
      </div>
      <div class="prob-item-num">03</div>
      <h3>No performance visibility</h3>
      <p>Without structured data, teams cannot measure cycle time, funnel quality, or where decisions improve.</p>
    </div>
  </div>

  <div class="prob-stats-row">
    <div class="prob-stat prob-stat--amber" v-click="1">
      <div class="prob-stat-num">23h</div>
      <div class="prob-stat-label">spent each week on manual screening</div>
      <div class="prob-stat-source">Instant Impact Recruiting Report</div>
    </div>
    <div class="prob-divider" v-click="2"></div>
    <div class="prob-stat prob-stat--rose" v-click="2">
      <div class="prob-stat-num">40%</div>
      <div class="prob-stat-label">hiring-process inefficiency cited</div>
      <div class="prob-stat-source">PwC Annual Global CEO Survey</div>
    </div>
    <div class="prob-divider" v-click="3"></div>
    <div class="prob-stat prob-stat--violet" v-click="3">
      <div class="prob-stat-num">0 KPI</div>
      <div class="prob-stat-label">visibility for teams without structured data</div>
      <div class="prob-stat-source">Modern Measures of Talent Acquisition</div>
    </div>
  </div>

</div>

<!--
Companies of every size face the same bottleneck: hiring is slow, fragmented, and difficult to measure.

Recruiters spend hours on repetitive screening, often without a shared rubric or reliable process data.
That creates three concrete problems: scattered manual workflows, subjective shortlisting, and no clear KPI visibility.

The data confirms the pain: recruiters can spend 23 hours a week on manual screening, and PwC reports major perceived inefficiency across hiring processes.
-->

---

<!-- SLIDE 3: THE SOLUTION — CONCEPT -->
<div class="sol-bg"></div>
<div class="relative z-10 px-14 pt-0 pb-6 h-full flex flex-col">

  <div class="prob-header mb-1">
    <span class="prob-eyebrow">The solution</span>
    <h2 class="prob-title">The <em>HireLight</em> Intelligence Layer</h2>
    <p class="prob-subtitle">Turning fragmented CVs into structured, explainable candidate signals in minutes.</p>
  </div>

  <div class="prob-grid flex-1">
    <div class="prob-item" v-click>
      <div class="prob-item-corner-icon pi-amber" aria-hidden="true">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
          <path d="M21 21L15.8033 15.8033M15.8033 15.8033C17.1605 14.4461 18 12.5711 18 10.5C18 6.35786 14.6421 3 10.5 3C6.35786 3 3 6.35786 3 10.5C3 14.6421 6.35786 18 10.5 18C12.5711 18 14.4461 17.1605 15.8033 15.8033Z"/>
        </svg>
      </div>
      <div class="prob-item-num">01</div>
      <h3>Structured Signal Extraction</h3>
      <p>Skills, experience, education, and context are transformed into comparable signals HR teams can act on.</p>
    </div>
    <div class="prob-item" v-click>
      <div class="prob-item-corner-icon pi-rose" aria-hidden="true">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
          <path d="M9 12.7498L11.25 14.9998L15 9.74985M12 2.71411C9.8495 4.75073 6.94563 5.99986 3.75 5.99986C3.69922 5.99986 3.64852 5.99955 3.59789 5.99892C3.2099 7.17903 3 8.43995 3 9.74991C3 15.3414 6.82432 20.0397 12 21.3719C17.1757 20.0397 21 15.3414 21 9.74991C21 8.43995 20.7901 7.17903 20.4021 5.99892C20.3515 5.99955 20.3008 5.99986 20.25 5.99986C17.0544 5.99986 14.1505 4.75073 12 2.71411Z"/>
        </svg>
      </div>
      <div class="prob-item-num">02</div>
      <h3>Bias-Aware Scoring</h3>
      <p>The scoring layer focuses on <strong>experience and education</strong>, reducing demographic noise and supporting AI Act-ready transparency.</p>
    </div>
    <div class="prob-item" v-click>
      <div class="prob-item-corner-icon pi-indigo" aria-hidden="true">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.7" stroke-linecap="round" stroke-linejoin="round">
          <path d="M13.5 4.5 7.5 14.25h4.5l-1.5 5.25 6-9.75H12l1.5-5.25Z" />
        </svg>
      </div>
      <div class="prob-item-num">03</div>
      <h3>Proactive Talent Matching</h3>
      <p>Unlike a passive ATS, HireLight surfaces fit, risk, and next actions as soon as a CV enters the pipeline.</p>
    </div>
  </div>

  <div class="prob-stats-row">
    <div class="prob-stat prob-stat--indigo" v-click="4">
      <div class="prob-stat-num">-75%</div>
      <div class="prob-stat-label">potential manual screening reduction</div>
      <div class="prob-stat-source">LinkedIn Future of Work Report (2023)</div>
    </div>
    <div class="prob-divider" v-click="4"></div>
    <div class="prob-stat prob-stat--emerald" v-click="4">
      <div class="prob-stat-num">100%</div>
      <div class="prob-stat-label">explainable by design</div>
      <div class="prob-stat-source">&nbsp;</div>
    </div>
    <div class="prob-divider" v-click="4"></div>
    <div class="prob-stat prob-stat--amber" v-click="4">
      <div class="prob-stat-num">Active</div>
      <div class="prob-stat-label">intelligence layer vs. ATS storage</div>
      <div class="prob-stat-source">&nbsp;</div>
    </div>
  </div>
</div>

<!--
"Our solution is an **Intelligence Layer**.
1. We go beyond keywords by turning every CV into structured signals: skills, experience, education, and context.
2. The scoring layer is bias-aware: it focuses on experience and education, reducing demographic noise and supporting explainability.
3. While traditional ATS platforms store candidates, HireLight actively recommends next steps.
The potential impact is clear: AI-assisted screening can reduce manual effort dramatically while giving HR teams a stronger evidence base."
-->

---

<!-- SLIDE 4: TECHNICAL STACK -->
<div class="sol-bg"></div>
<div class="relative z-10 px-14 py-2 h-full flex flex-col justify-between">
  <div class="prob-header mb-1">
    <span class="prob-eyebrow">Architecture</span>
    <h2 class="prob-title">The <em>Engine</em> Under the Hood</h2>
    <p class="prob-subtitle subtitle--tight">A modular, cloud-native pipeline designed for scale, privacy, and adaptation.</p>
  </div>
  
  <div class="flex-1 flex items-center justify-center p-2">
     <!-- Placeholder for a simple architecture diagram or icon set -->
     <div class="grid grid-cols-3 gap-6 w-full max-w-5xl">
        <div class="output-card-dark p-4 flex flex-col items-center gap-3 text-center" v-click>
           <div class="prob-stat-num metric--lg metric--indigo">28+</div>
           <div class="arch-card-title">Orchestration Steps</div>
           <p class="arch-card-desc">Parse attachments, normalize CV data, score candidates, and trigger the next action automatically.</p>
        </div>
        <div class="output-card-dark p-4 flex flex-col items-center gap-3 text-center" v-click>
           <div class="prob-stat-num metric--lg metric--amber">Hybrid</div>
           <div class="arch-card-title">Multi-Channel Intake</div>
           <p class="arch-card-desc">Start with email, then extend to <strong>LinkedIn, Indeed, career pages, and HR portals</strong> through APIs.</p>
        </div>
        <div class="output-card-dark p-4 flex flex-col items-center gap-3 text-center" v-click>
           <div class="prob-stat-num metric--lg metric--emerald">Jury</div>
           <div class="arch-card-title">Model-Agnostic Intelligence</div>
           <p class="arch-card-desc">Use <strong>local LLMs</strong>, OpenAI APIs, or a <strong>model jury</strong> to balance privacy, cost, and reliability.</p>
        </div>
     </div>
  </div>

  <div class="prob-stats-row tech-row justify-center gap-12">
    <div class="prob-stat" v-click="3">
      <img class="tech-icon" src="./img/n8n.png" alt="n8n" />
      <div class="prob-stat-label">Automation</div>
    </div>
    <div class="prob-stat" v-click="3">
      <img class="tech-icon" src="./img/oai.png" alt="OpenAI" />
      <div class="prob-stat-label">AI Scoring</div>
    </div>
    <div class="prob-stat" v-click="3">
      <img class="tech-icon" src="./img/supabase.png" alt="Supabase" />
      <div class="prob-stat-label">Candidate Data</div>
    </div>
    <div class="prob-stat" v-click="3">
      <img class="tech-icon" src="./img/nextjs.png" alt="Next.js" />
      <div class="prob-stat-label">Hiring UI</div>
    </div>
  </div>
</div>

<!--
"For the technical jury: HireLight is modular and channel-agnostic.
It starts with email ingestion, but the same architecture can connect to LinkedIn, Indeed, career pages, or internal HR portals.
The intelligence layer is model-agnostic: we can use OpenAI APIs, local LLMs for privacy-sensitive contexts, or a model jury when reliability matters most."
-->

---

<!-- SLIDE 5: MARKET LANDSCAPE -->
<div class="sol-bg" transition="slide-up"></div>
<div class="relative z-10 px-14 py-2 h-full flex flex-col">
  <div class="prob-header mb-1">
    <span class="prob-eyebrow">Market</span>
    <h2 class="prob-title">Competitive <em>Landscape</em></h2>
    <p class="prob-subtitle subtitle--sm">Where HireLight fits between legacy HR systems and enterprise talent-intelligence suites.</p>
  </div>

  <div class="comp-table-wrap" v-click>
    <table class="comp-table comp-table--compact">
      <thead>
        <tr>
          <th>Platform</th>
          <th>Category</th>
          <th>Key Strength</th>
          <th>Ideal Org. Size</th>
        </tr>
      </thead>
      <tbody>
        <tr class="comp-row--highlight">
          <td><strong class="text-strong">HireLight</strong></td>
          <td><span class="comp-tag comp-tag--active">Active Intelligence</span></td>
          <td>Explainable scoring & SME compliance</td>
          <td><strong>10 - 5,000+</strong></td>
        </tr>
        <tr>
          <td><strong>Eightfold AI</strong></td>
          <td><span class="comp-tag">Talent Intelligence</span></td>
          <td>Predictive AI for workforce planning</td>
          <td>5,000+</td>
        </tr>
        <tr>
          <td><strong>HiredScore</strong></td>
          <td><span class="comp-tag">AI Screening</span></td>
          <td>ATS overlay and auditable AI</td>
          <td>500+</td>
        </tr>
        <tr>
          <td><strong>Juicebox AI</strong></td>
          <td><span class="comp-tag">AI Sourcing</span></td>
          <td>Natural-language talent sourcing</td>
          <td>10 - 500+</td>
        </tr>
        <tr>
          <td><strong>HiBob / Personio</strong></td>
          <td><span class="comp-tag">Mid-Market HRIS</span></td>
          <td>Integrated HR analytics and GDPR focus</td>
          <td>50 - 1,000</td>
        </tr>
      </tbody>
    </table>
  </div>

  <div class="flex gap-2 mt-4" v-click>
    <div class="flex-1 feat-card feat-card--compact feat-card--indigo">
      <h4>Model Jury</h4>
      <p>Consensus scoring reduces hallucinations and single-model bias.</p>
    </div>
    <div class="flex-1 feat-card feat-card--compact feat-card--emerald">
      <h4>Bias-Aware Core</h4>
      <p>Risky demographic signals are filtered before scoring.</p>
    </div>
    <div class="flex-1 feat-card feat-card--compact feat-card--amber">
      <h4>SME-Ready Compliance</h4>
      <p>AI Act transparency without enterprise-only pricing.</p>
    </div>
  </div>
</div>

<!--
"The market is split between legacy HR systems and enterprise-grade talent intelligence platforms.
HireLight's position is different: we bring explainable, AI-assisted screening to the mid-market.
Instead of making compliance an enterprise-only feature, we make it accessible to SMEs.

Our edge has three parts:
1. A **model jury** for more reliable scoring.
2. A **bias-aware core** that filters risky demographic signals before evaluation.
3. An **active intelligence layer** that turns passive CV storage into decision-ready talent data."
-->

---

<!-- SLIDE 6: BUSINESS MODEL & STRATEGY -->
<div class="sol-bg" transition="slide-up"></div>
<div class="relative z-10 px-14 pt-1 pb-4 h-full flex flex-col">
  <div class="prob-header mb-1">
    <span class="prob-eyebrow">Sustainability & Growth</span>
    <h2 class="prob-title"><em>Business</em> Model</h2>
    <p class="prob-subtitle subtitle--xs">An accessible pricing model built for adoption, compliance, and scale.</p>
  </div>

  <div class="flex-1 flex flex-col items-center justify-center gap-2">
    <!-- TARGET MARKET POSITIONING -->
    <div class="grid grid-cols-2 gap-3 w-full max-w-4xl" v-click>
       <div class="output-card-dark card-accent-indigo p-3">
          <div class="business-kicker text-indigo-300">Distinctive Positioning</div>
          <h3 class="text-[0.9rem]">The Compliance Democratizer</h3>
          <p class="text-[0.62rem] opacity-70">Enterprise-grade transparency for SMEs, without enterprise-grade cost or complexity.</p>
       </div>
       <div class="output-card-dark card-accent-emerald p-3">
          <div class="business-kicker text-emerald-300">Scalability Moat</div>
          <h3 class="text-[0.9rem]">Lean, Modular Delivery</h3>
          <p class="text-[0.62rem] opacity-70">Low-overhead automation and API layers keep deployment fast and customization practical.</p>
       </div>
    </div>
    <!-- PRICING TIERS -->
    <div class="output-card-dark w-full max-w-4xl p-3" v-click>
      <div class="text-center mb-2">
        <span class="pricing-badge">SME-ready pricing</span>
      </div>
      <div class="grid grid-cols-3 gap-3">
        <div class="tier-card">
          <div class="tier-title">Starter</div>
          <div class="tier-price">Free to €99/mo</div>
          <div class="tier-divider"></div>
          <p>Up to 100 CVs/mo.<br/>Explainable scoring.</p>
        </div>
        <div class="tier-card tier-card--highlight">
          <div class="tier-title">Growth (Mid)</div>
          <div class="tier-price tier-price--highlight">€299/mo</div>
          <div class="tier-divider"></div>
          <p>Up to 1,000 CVs/mo.<br/>Model-jury scoring.</p>
        </div>
        <div class="tier-card tier-card--amber">
          <div class="tier-title">Enterprise</div>
          <div class="tier-price">Custom volume</div>
          <div class="tier-divider"></div>
          <p>Unlimited volumes.<br/>Local LLM or on-prem.</p>
        </div>
      </div>
    </div>
  </div>
</div>

<!--
"Our business model is built around adoption.
Many AI hiring platforms are priced and packaged for large enterprises, while SMEs still face the same manual bottleneck.

HireLight is the compliance democratizer: it offers transparent, AI-assisted screening without enterprise-level cost or setup.
Because the architecture is modular, using n8n and scalable API layers, we can deploy quickly and keep customization practical.

The pricing mirrors that path:
1. **Starter** for early adoption and smaller volumes.
2. **Growth** for teams that need model-jury reliability at scale.
3. **Enterprise** for local LLMs, on-prem options, and higher-volume requirements.

This makes the solution commercially sustainable and accessible to the segment that needs it most."
-->

---

<!-- SLIDE 7: THE TEAM & ROLES -->
<div class="sol-bg" transition="slide-up"></div>

<div class="relative z-10 px-14 pt-0 pb-2 h-full flex flex-col -mt-2">
  <div class="prob-header mb-1">
    <span class="prob-eyebrow">The Team</span>
    <h2 class="prob-title">Who <em>we are</em></h2>
    <p class="prob-subtitle">A cross-functional team spanning product, AI, engineering, research, and design.</p>
  </div>

  <div class="team-grid">
    <div class="team-item">
      <div class="team-img-wrap">
        <img src="./img/af.png" alt="Andrea Feliziani" />
      </div>
      <div class="team-text">
        <h3 class="team-name">Andrea Feliziani</h3>
        <p class="team-role">UI/UX Designer & Frontend Developer</p>
      </div>
    </div>
    <div class="team-item">
      <div class="team-img-wrap">
        <img src="./img/mc.png" alt="Marco Cremaschi" />
      </div>
      <div class="team-text">
        <h3 class="team-name">Marco Cremaschi</h3>
        <p class="team-role">Researcher</p>
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
        <p class="team-role">Backend Developer & AI Specialist</p>
      </div>
    </div>
    <div class="team-collaboration-label">
      <span>In collaborazione con</span>
    </div>
    <div class="team-item">
      <div class="team-img-wrap">
        <img src="./img/ag.png" alt="Azizbek Gulomov" />
      </div>
      <div class="team-text">
        <h3 class="team-name">Azizbek Gulomov</h3>
        <p class="team-role">Backend Designer</p>
      </div>
    </div>
    <div class="team-item">
      <div class="team-img-wrap">
        <img src="./img/lj.png" alt="Labhanshiv Jayant" />
      </div>
      <div class="team-text">
        <h3 class="team-name">Labhanshiv Jayant</h3>
        <p class="team-role">Researcher</p>
      </div>
    </div>
    <div class="team-item">
      <div class="team-img-wrap">
        <img src="./img/sa.png" alt="Siraj Ahmed" />
      </div>
      <div class="team-text">
        <h3 class="team-name">Siraj Ahmed</h3>
        <p class="team-role">Frontend Designer</p>
      </div>
    </div>
  </div>
</div>

<!--
To build HireLight, we combined product design, AI, backend engineering, frontend development, and research.
That mix is important: the challenge is not only technical, but also ethical, operational, and user-facing.

Thank you.
-->

---

<!-- SLIDE 8: THANK YOU -->
<div class="thankyou-bg">
  <div class="thankyou-blob"></div>
</div>

<div class="relative z-10 flex flex-col items-center justify-center h-full text-center px-10 gap-8">
  <div class="thankyou-logo-wrap">
    <img class="thankyou-logo-img" src="./img/whattadata.png" alt="WhattaData logo" />
  </div>

  <div v-click class="mb-2">
    <h1 class="thankyou-title"><span>Thank</span><span>you.</span></h1>
  </div>

  <a class="thankyou-site-link" href="https://whattadata.it" target="_blank" rel="noopener noreferrer">
    <span>Sito</span>
    whattadata.it
  </a>

</div>
