import React from 'react';

// Final — Lively dark-themed Quants Research & Analytics single-file React component
// - Tailwind CSS assumed available in the project
// - Small interactive touches: hover lifts, subtle motion, gradient accents
// - Replaces newsletter with a prominent LinkedIn button linking to your profile (update LINKEDIN_URL)
// - Replace /images/... placeholders with your real screenshots or code images

const LINKEDIN_URL = 'https://www.linkedin.com/in/ibrahimkiria/'; // <-- update to your exact LinkedIn URL

export default function QuantsLanding() {
  const projects = [
    {
      id: 'p-nasi',
      title: 'Optimal Portfolio — NASI (Sharpe SIM)',
      summary:
        "Constructed an optimal portfolio for Nairobi All Share Index using Sharpe's Single Index Model. Includes backtest and factor attribution.",
      tags: ['portfolio', 'backtest', 'Python'],
      img: '/images/code-sample-nasi.png'
    },
    {
      id: 'p-hmm',
      title: 'Regime-based Rotation (HMM)',
      summary:
        'Implemented VIX regime detection using HMM and designed ETF rotation strategies with performance metrics and drawdown analysis.',
      tags: ['HMM', 'strategy', 'risk'],
      img: '/images/code-sample-hmm.png'
    },
    {
      id: 'p-svr',
      title: 'Macro-driven Forecasts (SVR + XGBoost)',
      summary: 'Feature engineered macro indicators and trained hybrid models for short-term return forecasting.',
      tags: ['forecasting', 'ml'],
      img: '/images/code-sample-ml.png'
    },
  ];

  return (
    <div className="min-h-screen bg-gradient-to-b from-slate-950 via-slate-900 to-slate-900 text-slate-100 antialiased">
      {/* NAV */}
      <header className="sticky top-0 z-50 bg-slate-900/80 backdrop-blur border-b border-slate-800">
        <div className="max-w-6xl mx-auto px-6 py-4 flex items-center justify-between">
          <div className="flex items-center gap-3">
            <div className="rounded-lg bg-gradient-to-r from-indigo-500 to-sky-400 text-white p-2 font-semibold shadow-md transform hover:scale-105 transition">QR</div>
            <div>
              <h1 className="text-lg font-semibold">Quants Research & Analytics</h1>
              <p className="text-xs text-slate-400">Research · Strategy · Risk · Data</p>
            </div>
          </div>

          <nav className="hidden md:flex items-center gap-6 text-sm">
            <a className="hover:text-sky-300 transition" href="#research">Research</a>
            <a className="hover:text-sky-300 transition" href="#projects">Projects</a>
            <a className="hover:text-sky-300 transition" href="#team">Team</a>
            <a className="hover:text-sky-300 transition" href="#contact">Contact</a>
            <a
              href={LINKEDIN_URL}
              target="_blank"
              rel="noreferrer"
              className="ml-3 inline-flex items-center gap-2 rounded-md bg-gradient-to-r from-blue-600 to-blue-500 text-white px-4 py-2 text-sm font-semibold shadow hover:scale-[1.02] transform transition"
            >
              <svg xmlns="http://www.w3.org/2000/svg" className="h-4 w-4" viewBox="0 0 24 24" fill="currentColor"><path d="M19 0h-14c-2.76 0-5 2.24-5 5v14c0 2.76 2.24 5 5 5h14c2.76 0 5-2.24 5-5v-14c0-2.76-2.24-5-5-5zm-11.75 20h-2.5v-9h2.5v9zm-1.25-10.2c-.8 0-1.45-.65-1.45-1.45s.65-1.45 1.45-1.45c.8 0 1.45.65 1.45 1.45s-.65 1.45-1.45 1.45zm13 10.2h-2.5v-4.5c0-1.07-.02-2.45-1.5-2.45-1.5 0-1.73 1.17-1.73 2.38v4.57h-2.5v-9h2.4v1.23h.03c.33-.62 1.13-1.27 2.33-1.27 2.49 0 2.95 1.64 2.95 3.77v5.27z"/></svg>
              Connect
            </a>
          </nav>

          <div className="md:hidden">
            <a href={LINKEDIN_URL} target="_blank" rel="noreferrer" className="inline-flex items-center gap-2 rounded-md bg-blue-600 text-white px-3 py-2 text-sm font-semibold shadow">LinkedIn</a>
          </div>
        </div>
      </header>

      {/* HERO */}
      <main className="max-w-6xl mx-auto px-6 py-16">
        <section className="grid md:grid-cols-2 gap-8 items-center">
          <div>
            <h2 className="text-4xl md:text-5xl font-extrabold leading-tight text-white">Quantitative research that moves markets —
              <span className="bg-clip-text text-transparent bg-gradient-to-r from-sky-300 to-indigo-400"> actionable & reproducible</span>
            </h2>

            <p className="mt-4 text-slate-300 max-w-xl text-lg">We build tested, production-ready strategies and reproducible research — from regime detection to portfolio optimization — using Python & R.</p>

            <div className="mt-6 flex gap-3">
              <a href="#projects" className="inline-flex items-center gap-3 rounded-full bg-indigo-600 px-5 py-3 font-semibold shadow-lg hover:translate-y-[-3px] transform transition">View Projects</a>
              <a href="#contact" className="inline-flex items-center gap-3 rounded-full border border-slate-700 px-5 py-3 text-slate-200 hover:bg-slate-800 transition">Work with us</a>
            </div>

            <div className="mt-8 grid grid-cols-3 gap-4 text-sm">
              <StatCard label="Backtests" value="120+" />
              <StatCard label="Models" value="35" />
              <StatCard label="Datasets" value="18" />
            </div>

            <div className="mt-8 flex items-center gap-3 text-sm text-slate-400">
              <div className="p-2 bg-slate-800 rounded">📁</div>
              <div>
                <div className="text-xs">Featured</div>
                <div className="text-slate-200 font-medium">Regime-based Rotation (HMM) — Read the walkthrough</div>
              </div>
            </div>
          </div>

          {/* Right: chart + animated sparkline */}
          <div>
            <div className="bg-gradient-to-b from-slate-800 to-slate-850 rounded-xl p-5 shadow-lg border border-slate-700">
              <div className="flex items-start justify-between">
                <div>
                  <div className="text-xs text-slate-400">Equity Curve (example)</div>
                  <div className="mt-2 text-white font-bold text-2xl">+10.4% CAGR</div>
                </div>
                <div className="text-sm text-slate-300">Sharpe 1.45</div>
              </div>

              <div className="mt-4 h-48 flex items-center justify-center">
                {/* Replace with Recharts or your chart component */}
                <svg width="100%" height="100%" viewBox="0 0 600 200" preserveAspectRatio="none" className="rounded">
                  <defs>
                    <linearGradient id="g1" x1="0" x2="1">
                      <stop offset="0%" stopColor="#38bdf8" stopOpacity="0.7" />
                      <stop offset="100%" stopColor="#6366f1" stopOpacity="0.7" />
                    </linearGradient>
                  </defs>
                  <path d="M0 140 C80 100 160 120 240 90 C320 60 400 80 480 40 C560 0 600 20 600 20" fill="none" stroke="url(#g1)" strokeWidth="3" strokeLinecap="round" strokeLinejoin="round" />
                </svg>
              </div>

              <div className="mt-4 grid grid-cols-3 text-center text-slate-200">
                <div>
                  <div className="text-xs text-slate-400">Max DD</div>
                  <div className="font-bold">-8.2%</div>
                </div>
                <div>
                  <div className="text-xs text-slate-400">Win Rate</div>
                  <div className="font-bold">63%</div>
                </div>
                <div>
                  <div className="text-xs text-slate-400">Trades</div>
                  <div className="font-bold">420</div>
                </div>
              </div>
            </div>
          </div>
        </section>

        {/* RESEARCH */}
        <section id="research" className="mt-14">
          <h3 className="text-2xl font-semibold text-white">Recent Research</h3>
          <div className="mt-6 grid md:grid-cols-3 gap-6">
            <ResearchCard title="VIX Regimes & Rotation" date="Oct 2025">Hidden Markov Models to identify volatility regimes and tailor ETF exposure.</ResearchCard>
            <ResearchCard title="NASI Portfolio — SIM" date="Aug 2025">Sharpe Single Index Model applied to Nairobi All Share Index for optimal weights.</ResearchCard>
            <ResearchCard title="Macro Feature Selection" date="Jul 2025">Feature engineering for macro-driven forecasts using LASSO and tree-based importance.</ResearchCard>
          </div>
        </section>

        {/* PROJECTS */}
        <section id="projects" className="mt-14">
          <h3 className="text-2xl font-semibold text-white">Projects</h3>
          <div className="mt-6 grid md:grid-cols-3 gap-6">
            {projects.map((p) => (
              <div key={p.id} className="bg-slate-800 p-4 rounded-lg shadow hover:shadow-xl transform hover:-translate-y-2 transition duration-300">
                <div className="flex items-start justify-between gap-4">
                  <div className="flex-1">
                    <h4 className="font-semibold text-white">{p.title}</h4>
                    <p className="text-sm text-slate-300 mt-2">{p.summary}</p>
                    <div className="mt-4 flex flex-wrap gap-2">
                      {p.tags.map((t) => (
                        <span key={t} className="text-xs bg-slate-700 px-2 py-1 rounded text-slate-200">{t}</span>
                      ))}
                    </div>
                  </div>
                  <img src={p.img} alt={`${p.id}-code`} className="w-28 h-20 object-cover rounded ml-4 hidden md:block" />
                </div>

                <div className="mt-4 flex items-center justify-between">
                  <a href="#" className="text-sky-300 text-sm">Read</a>
                  <button className="text-sm rounded px-3 py-1 border border-slate-600 text-slate-200">Code</button>
                </div>
              </div>
            ))}
          </div>
        </section>

        {/* TEAM / OVERVIEW */}
        <section id="team" className="mt-14 grid md:grid-cols-2 gap-6 items-start">
          <div className="bg-slate-800 p-6 rounded-lg shadow">
            <h3 className="text-lg font-semibold text-white">Overview</h3>
            <p className="mt-3 text-slate-300">📊 <strong>About Quant Research & Analytics</strong></p>
            <p className="mt-2 text-slate-300 text-sm">At Quant Research & Analytics, we specialize in quantitative research, financial modeling, stochastic modeling, and data-driven analysis using Python and R. Our work bridges finance, economics, health, climate finance, statistics, and data science — delivering insights that empower smarter, evidence-based decisions.</p>

            <p className="mt-3 text-slate-300 text-sm">We collaborate with students, researchers and professionals through hands-on projects, mentorship and applied analytics — transforming complex data into clear, actionable strategies that drive measurable growth and sustainability.</p>

            <div className="mt-4 text-sm text-slate-300">
              <div>⚙️ Advanced Quantitative Research. Delivered as Actionable Strategy Reports.</div>
              <div className="mt-2">📈 From Data to Insight — Advancing Growth through Quantitative, Statistical, and Evidence-Based Research.</div>

              <ul className="mt-3 space-y-1 text-slate-300">
                <li><strong>Industry:</strong> Research Services</li>
                <li><strong>Company size:</strong> 2-10 employees</li>
                <li><strong>Founded:</strong> 2024</li>
                <li><strong>Location:</strong> Nairobi, KE</li>
                <li><strong>Specialties:</strong> Quantitative Research, Financial Modeling, Data Analytics, Machine Learning, Risk Management, Econometrics</li>
              </ul>
            </div>
          </div>

          <div className="bg-slate-800 p-6 rounded-lg shadow" id="contact">
            <h3 className="text-lg font-semibold text-white">Get in touch</h3>
            <p className="mt-3 text-slate-300">Want a collaboration, a research license, or full-stack strategy delivery? Connect on LinkedIn or drop your message below.</p>

            <div className="mt-4 flex flex-col gap-3">
              <a href={LINKEDIN_URL} target="_blank" rel="noreferrer" className="inline-flex items-center gap-3 rounded-full bg-blue-600 px-4 py-3 font-semibold shadow hover:scale-[1.02] transform transition">
                <svg xmlns="http://www.w3.org/2000/svg" className="h-5 w-5" viewBox="0 0 24 24" fill="currentColor"><path d="M19 0h-14c-2.76 0-5 2.24-5 5v14c0 2.76 2.24 5 5 5h14c2.76 0 5-2.24 5-5v-14c0-2.76-2.24-5-5-5zm-11.75 20h-2.5v-9h2.5v9zm-1.25-10.2c-.8 0-1.45-.65-1.45-1.45s.65-1.45 1.45-1.45c.8 0 1.45.65 1.45 1.45s-.65 1.45-1.45 1.45zm13 10.2h-2.5v-4.5c0-1.07-.02-2.45-1.5-2.45-1.5 0-1.73 1.17-1.73 2.38v4.57h-2.5v-9h2.4v1.23h.03c.33-.62 1.13-1.27 2.33-1.27 2.49 0 2.95 1.64 2.95 3.77v5.27z"/></svg>
                Connect on LinkedIn
              </a>

              <form className="mt-2 grid gap-3">
                <input className="bg-slate-700 border border-slate-600 rounded px-3 py-2 text-slate-100" placeholder="Your name (optional)" />
                <input className="bg-slate-700 border border-slate-600 rounded px-3 py-2 text-slate-100" placeholder="Your email" />
                <textarea className="bg-slate-700 border border-slate-600 rounded px-3 py-2 text-slate-100" rows={4} placeholder="Message"></textarea>
                <div className="flex justify-end">
                  <button type="button" className="bg-indigo-600 text-white px-4 py-2 rounded">Send</button>
                </div>
              </form>
            </div>
          </div>
        </section>

        {/* FOOTER */}
        <footer className="mt-16 py-8 text-sm text-slate-400">
          <div className="max-w-6xl mx-auto px-6 flex flex-col md:flex-row items-center justify-between gap-4">
            <div>© {new Date().getFullYear()} Quants Research & Analytics — Built by Ibrahim</div>
            <div className="flex gap-4">
              <a className="text-slate-300 hover:text-white transition" href="#">Privacy</a>
              <a className="text-slate-300 hover:text-white transition" href="#">Terms</a>
              <a className="text-slate-300 hover:text-white transition" href="#">GitHub</a>
            </div>
          </div>
        </footer>
      </main>
    </div>
  );
}

// ----------------------
// Small presentational components
// ----------------------

function StatCard({ label, value }) {
  return (
    <div className="bg-slate-800 p-4 rounded-lg shadow flex flex-col items-start">
      <div className="text-xs text-slate-400">{label}</div>
      <div className="mt-2 text-white font-bold text-lg animate-fade-in">{value}</div>
    </div>
  );
}

function ResearchCard({ children, title, date }) {
  return (
    <article className="bg-slate-800 p-4 rounded-lg shadow hover:scale-[1.02] transform transition">
      <div className="flex items-start justify-between">
        <div>
          <h4 className="font-semibold text-white">{title}</h4>
          <p className="text-sm text-slate-300 mt-2">{children}</p>
        </div>
        <div className="text-xs text-slate-400">{date}</div>
      </div>
    </article>
  );
}
