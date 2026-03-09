import { useState, useEffect, useRef } from "react";

const API_KEY_PLACEHOLDER = "";

// ── Palette & Tokens ──────────────────────────────────────────────────────────
const HABITS_DEFAULT = [
  { id: 1, name: "Morning run", icon: "🏃", color: "#FF6B35", streak: 12, category: "body" },
  { id: 2, name: "Read 30 min", icon: "📖", color: "#4ECDC4", streak: 7, category: "mind" },
  { id: 3, name: "Meditate", icon: "🧘", color: "#A78BFA", streak: 21, category: "mind" },
  { id: 4, name: "No sugar", icon: "🥦", color: "#34D399", streak: 5, category: "body" },
  { id: 5, name: "Journal", icon: "✍️", color: "#FBBF24", streak: 3, category: "soul" },
  { id: 6, name: "Cold shower", icon: "🚿", color: "#60A5FA", streak: 9, category: "body" },
];

const DAYS = ["M", "T", "W", "T", "F", "S", "S"];
const QUOTES = [
  "Small steps, compounded daily, move mountains.",
  "Discipline is choosing between what you want now and what you want most.",
  "We are what we repeatedly do.",
  "Your future is created by what you do today, not tomorrow.",
  "The secret of your future is hidden in your daily routine.",
];

function generateWeekData() {
  return DAYS.map((_, i) => ({
    day: DAYS[i],
    done: Math.random() > 0.25,
  }));
}

// ── Inline styles (no Tailwind compiler needed) ───────────────────────────────
const css = `
  @import url('https://fonts.googleapis.com/css2?family=Bebas+Neue&family=DM+Sans:ital,wght@0,300;0,400;0,500;0,600;1,300&display=swap');

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --bg: #0a0a0f;
    --surface: #111118;
    --surface2: #1a1a24;
    --border: rgba(255,255,255,0.06);
    --text: #f0eff8;
    --muted: #6b6a7e;
    --accent: #FF6B35;
    --accent2: #A78BFA;
    --green: #34D399;
    --radius: 18px;
    --font-display: 'Bebas Neue', cursive;
    --font-body: 'DM Sans', sans-serif;
  }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: var(--font-body);
    min-height: 100vh;
    overflow-x: hidden;
  }

  .app {
    max-width: 1100px;
    margin: 0 auto;
    padding: 32px 24px 80px;
  }

  /* ── Header ── */
  .header {
    display: flex;
    align-items: flex-end;
    justify-content: space-between;
    margin-bottom: 40px;
    gap: 16px;
    flex-wrap: wrap;
  }
  .logo {
    font-family: var(--font-display);
    font-size: 52px;
    letter-spacing: 3px;
    line-height: 1;
    background: linear-gradient(135deg, #FF6B35 0%, #A78BFA 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }
  .logo-sub {
    font-size: 13px;
    color: var(--muted);
    letter-spacing: 2px;
    text-transform: uppercase;
    margin-top: 4px;
  }
  .date-pill {
    background: var(--surface2);
    border: 1px solid var(--border);
    border-radius: 100px;
    padding: 8px 20px;
    font-size: 13px;
    color: var(--muted);
    font-weight: 500;
  }

  /* ── Grid ── */
  .grid {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    gap: 16px;
  }
  @media (max-width: 800px) {
    .grid { grid-template-columns: 1fr; }
    .span2 { grid-column: span 1 !important; }
  }
  .span2 { grid-column: span 2; }

  /* ── Card ── */
  .card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: var(--radius);
    padding: 24px;
    position: relative;
    overflow: hidden;
    transition: border-color 0.2s;
  }
  .card:hover { border-color: rgba(255,255,255,0.12); }
  .card-label {
    font-size: 11px;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 12px;
    font-weight: 600;
  }

  /* ── Stat cards ── */
  .stat-cards {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 12px;
    margin-bottom: 16px;
  }
  @media (max-width: 800px) { .stat-cards { grid-template-columns: 1fr; } }
  .stat-card {
    background: var(--surface2);
    border: 1px solid var(--border);
    border-radius: 14px;
    padding: 18px 20px;
  }
  .stat-val {
    font-family: var(--font-display);
    font-size: 42px;
    letter-spacing: 1px;
    line-height: 1;
  }
  .stat-label { font-size: 12px; color: var(--muted); margin-top: 4px; font-weight: 500; }

  /* ── Habit list ── */
  .habit-row {
    display: flex;
    align-items: center;
    gap: 14px;
    padding: 14px 0;
    border-bottom: 1px solid var(--border);
    cursor: pointer;
    transition: opacity 0.15s;
  }
  .habit-row:last-child { border-bottom: none; }
  .habit-row:hover { opacity: 0.85; }
  .habit-icon {
    width: 40px; height: 40px;
    border-radius: 12px;
    display: flex; align-items: center; justify-content: center;
    font-size: 20px;
    flex-shrink: 0;
  }
  .habit-name { font-weight: 500; font-size: 15px; flex: 1; }
  .habit-streak {
    font-family: var(--font-display);
    font-size: 22px;
    letter-spacing: 1px;
  }
  .habit-streak-label { font-size: 10px; color: var(--muted); text-transform: uppercase; letter-spacing: 1px; }
  .week-dots { display: flex; gap: 4px; }
  .dot {
    width: 22px; height: 22px;
    border-radius: 6px;
    display: flex; align-items: center; justify-content: center;
    font-size: 9px;
    font-weight: 600;
    color: var(--muted);
  }
  .dot.done { color: #fff; }
  .check-btn {
    width: 32px; height: 32px;
    border-radius: 50%;
    border: 2px solid var(--border);
    background: transparent;
    cursor: pointer;
    display: flex; align-items: center; justify-content: center;
    font-size: 14px;
    transition: all 0.2s;
    flex-shrink: 0;
  }
  .check-btn.checked { border-color: var(--green); background: var(--green); }
  .check-btn:hover { transform: scale(1.1); }

  /* ── Ring ── */
  .ring-wrap { display: flex; align-items: center; justify-content: center; flex-direction: column; gap: 8px; padding: 8px 0; }
  .ring-label { font-size: 13px; color: var(--muted); }
  .ring-pct { font-family: var(--font-display); font-size: 36px; text-align: center; }

  /* ── AI Coach ── */
  .ai-box {
    background: var(--surface2);
    border: 1px solid var(--border);
    border-radius: 14px;
    padding: 18px;
    margin-top: 12px;
    min-height: 80px;
    font-size: 14px;
    line-height: 1.65;
    color: var(--text);
  }
  .ai-loading { color: var(--muted); font-style: italic; }
  .ai-btn {
    margin-top: 12px;
    background: linear-gradient(135deg, #FF6B35, #A78BFA);
    border: none;
    border-radius: 100px;
    padding: 10px 24px;
    color: #fff;
    font-family: var(--font-body);
    font-weight: 600;
    font-size: 13px;
    cursor: pointer;
    letter-spacing: 0.5px;
    transition: opacity 0.2s, transform 0.15s;
  }
  .ai-btn:hover { opacity: 0.88; transform: translateY(-1px); }
  .ai-btn:disabled { opacity: 0.4; cursor: not-allowed; transform: none; }

  /* ── Add habit ── */
  .add-row {
    display: flex; gap: 8px; margin-top: 16px;
  }
  .add-input {
    flex: 1;
    background: var(--surface2);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 10px 16px;
    color: var(--text);
    font-family: var(--font-body);
    font-size: 14px;
    outline: none;
    transition: border-color 0.2s;
  }
  .add-input:focus { border-color: var(--accent2); }
  .add-btn {
    background: var(--surface2);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 10px 16px;
    color: var(--text);
    font-size: 20px;
    cursor: pointer;
    transition: background 0.2s;
  }
  .add-btn:hover { background: var(--surface); }

  /* ── Quote ── */
  .quote {
    font-size: 15px;
    line-height: 1.7;
    font-style: italic;
    color: var(--muted);
    text-align: center;
    padding: 4px 0 8px;
  }
  .quote-mark { font-size: 40px; line-height: 0.5; color: var(--accent); display: block; margin-bottom: 10px; font-style: normal; }

  /* ── Heatmap ── */
  .heatmap { display: flex; gap: 3px; flex-wrap: wrap; margin-top: 8px; }
  .hcell {
    width: 14px; height: 14px;
    border-radius: 3px;
    background: var(--surface2);
    transition: background 0.3s;
  }

  /* ── Glow effects ── */
  .glow-orange::after {
    content: '';
    position: absolute;
    top: -60px; right: -60px;
    width: 180px; height: 180px;
    background: radial-gradient(circle, rgba(255,107,53,0.12) 0%, transparent 70%);
    pointer-events: none;
  }
  .glow-purple::after {
    content: '';
    position: absolute;
    bottom: -60px; left: -60px;
    width: 180px; height: 180px;
    background: radial-gradient(circle, rgba(167,139,250,0.10) 0%, transparent 70%);
    pointer-events: none;
  }

  /* ── Nav Tabs ── */
  .tabs { display: flex; gap: 6px; margin-bottom: 24px; }
  .tab {
    background: transparent;
    border: 1px solid var(--border);
    border-radius: 100px;
    padding: 7px 18px;
    color: var(--muted);
    font-family: var(--font-body);
    font-size: 13px;
    font-weight: 500;
    cursor: pointer;
    transition: all 0.2s;
  }
  .tab.active {
    background: var(--surface2);
    border-color: rgba(255,255,255,0.15);
    color: var(--text);
  }

  /* ── Scrollbar ── */
  ::-webkit-scrollbar { width: 4px; }
  ::-webkit-scrollbar-track { background: transparent; }
  ::-webkit-scrollbar-thumb { background: var(--surface2); border-radius: 4px; }
`;

// ── Ring SVG ──────────────────────────────────────────────────────────────────
function Ring({ pct, color, size = 120, stroke = 10 }) {
  const r = (size - stroke) / 2;
  const circ = 2 * Math.PI * r;
  const offset = circ - (pct / 100) * circ;
  return (
    <svg width={size} height={size} style={{ transform: "rotate(-90deg)" }}>
      <circle cx={size / 2} cy={size / 2} r={r} fill="none" stroke="#1a1a24" strokeWidth={stroke} />
      <circle
        cx={size / 2} cy={size / 2} r={r} fill="none"
        stroke={color} strokeWidth={stroke}
        strokeDasharray={circ} strokeDashoffset={offset}
        strokeLinecap="round"
        style={{ transition: "stroke-dashoffset 1s cubic-bezier(.4,0,.2,1)" }}
      />
    </svg>
  );
}

// ── Heatmap (52 weeks) ────────────────────────────────────────────────────────
function Heatmap() {
  const cells = Array.from({ length: 52 * 7 }, (_, i) => ({
    active: Math.random() > 0.45,
    intensity: Math.floor(Math.random() * 4),
  }));
  const colors = ["#1a1a24", "#2d3a2e", "#34D399aa", "#34D399"];
  return (
    <div className="heatmap">
      {cells.map((c, i) => (
        <div key={i} className="hcell" style={{ background: c.active ? colors[c.intensity] : colors[0] }} />
      ))}
    </div>
  );
}

// ── Main App ──────────────────────────────────────────────────────────────────
export default function MomentumApp() {
  const [habits, setHabits] = useState(() =>
    HABITS_DEFAULT.map(h => ({ ...h, weekData: generateWeekData(), checkedToday: Math.random() > 0.5 }))
  );
  const [newHabit, setNewHabit] = useState("");
  const [activeTab, setActiveTab] = useState("today");
  const [aiMessage, setAiMessage] = useState("");
  const [aiLoading, setAiLoading] = useState(false);
  const [quote] = useState(QUOTES[Math.floor(Math.random() * QUOTES.length)]);
  const today = new Date().toLocaleDateString("en-US", { weekday: "long", month: "long", day: "numeric" });

  const doneCount = habits.filter(h => h.checkedToday).length;
  const pct = Math.round((doneCount / habits.length) * 100);
  const longestStreak = Math.max(...habits.map(h => h.streak));
  const totalDone = habits.reduce((a, h) => a + h.weekData.filter(d => d.done).length, 0);

  function toggleHabit(id) {
    setHabits(prev =>
      prev.map(h =>
        h.id === id
          ? { ...h, checkedToday: !h.checkedToday, streak: !h.checkedToday ? h.streak + 1 : Math.max(0, h.streak - 1) }
          : h
      )
    );
  }

  function addHabit() {
    if (!newHabit.trim()) return;
    const icons = ["⚡","🎯","💪","🌿","🔥","✨","🎵","🧩"];
    const colors = ["#FF6B35","#4ECDC4","#A78BFA","#34D399","#FBBF24","#60A5FA","#F472B6","#FB923C"];
    const idx = habits.length % icons.length;
    setHabits(prev => [...prev, {
      id: Date.now(), name: newHabit.trim(),
      icon: icons[idx], color: colors[idx],
      streak: 0, category: "mind",
      weekData: generateWeekData(), checkedToday: false,
    }]);
    setNewHabit("");
  }

  async function getAICoach() {
    setAiLoading(true);
    setAiMessage("");
    const summary = habits.map(h => `${h.name}: ${h.streak}-day streak, ${h.checkedToday ? "done today" : "not done today"}`).join("; ");
    try {
      const res = await fetch("https://api.anthropic.com/v1/messages", {
        method: "POST",
        headers: { "Content-Type": "application/json" },
        body: JSON.stringify({
          model: "claude-sonnet-4-20250514",
          max_tokens: 1000,
          system: "You are an elite personal coach named Momentum. Be warm, direct, and motivating. Give a short (3-4 sentence) personalized coaching insight based on the user's habit data. Be specific, reference their actual habits and streaks. End with one powerful action tip for today. No bullet points — flowing prose only.",
          messages: [{ role: "user", content: `My habit data today: ${summary}. Overall completion: ${pct}%. Give me a personalized coaching message.` }],
        }),
      });
      const data = await res.json();
      const text = data.content?.map(b => b.text || "").join("") || "Keep going — every rep counts.";
      setAiMessage(text);
    } catch {
      setAiMessage("You're building something real here. Stay consistent — the compound effect is silently working in your favor. Focus on your longest streak today and protect it at all costs.");
    }
    setAiLoading(false);
  }

  return (
    <>
      <style>{css}</style>
      <div className="app">
        {/* Header */}
        <div className="header">
          <div>
            <div className="logo">MOMENTUM</div>
            <div className="logo-sub">Your daily habit engine</div>
          </div>
          <div className="date-pill">{today}</div>
        </div>

        {/* Tabs */}
        <div className="tabs">
          {["today", "progress", "coach"].map(t => (
            <button key={t} className={`tab ${activeTab === t ? "active" : ""}`} onClick={() => setActiveTab(t)}>
              {t.charAt(0).toUpperCase() + t.slice(1)}
            </button>
          ))}
        </div>

        {/* ── TODAY TAB ── */}
        {activeTab === "today" && (
          <>
            {/* Stat Cards */}
            <div className="stat-cards">
              <div className="stat-card">
                <div className="stat-val" style={{ color: "#FF6B35" }}>{doneCount}/{habits.length}</div>
                <div className="stat-label">Done today</div>
              </div>
              <div className="stat-card">
                <div className="stat-val" style={{ color: "#A78BFA" }}>{longestStreak}</div>
                <div className="stat-label">Longest streak</div>
              </div>
              <div className="stat-card">
                <div className="stat-val" style={{ color: "#34D399" }}>{pct}%</div>
                <div className="stat-label">Completion rate</div>
              </div>
            </div>

            <div className="grid">
              {/* Habits */}
              <div className="card span2 glow-orange">
                <div className="card-label">Today's Habits</div>
                {habits.map(h => (
                  <div key={h.id} className="habit-row" onClick={() => toggleHabit(h.id)}>
                    <div className="habit-icon" style={{ background: h.color + "22" }}>{h.icon}</div>
                    <div style={{ flex: 1 }}>
                      <div className="habit-name" style={{ textDecoration: h.checkedToday ? "line-through" : "none", color: h.checkedToday ? "var(--muted)" : "var(--text)" }}>
                        {h.name}
                      </div>
                      <div className="week-dots" style={{ marginTop: 6 }}>
                        {h.weekData.map((d, i) => (
                          <div key={i} className={`dot ${d.done ? "done" : ""}`} style={{ background: d.done ? h.color : "var(--surface2)" }}>
                            {DAYS[i]}
                          </div>
                        ))}
                      </div>
                    </div>
                    <div style={{ textAlign: "right" }}>
                      <div className="habit-streak" style={{ color: h.color }}>{h.streak}</div>
                      <div className="habit-streak-label">day streak</div>
                    </div>
                    <button className={`check-btn ${h.checkedToday ? "checked" : ""}`} onClick={e => { e.stopPropagation(); toggleHabit(h.id); }}>
                      {h.checkedToday ? "✓" : ""}
                    </button>
                  </div>
                ))}
                {/* Add habit */}
                <div className="add-row">
                  <input
                    className="add-input"
                    placeholder="Add a new habit..."
                    value={newHabit}
                    onChange={e => setNewHabit(e.target.value)}
                    onKeyDown={e => e.key === "Enter" && addHabit()}
                  />
                  <button className="add-btn" onClick={addHabit}>+</button>
                </div>
              </div>

              {/* Ring + Quote */}
              <div className="card glow-purple" style={{ display: "flex", flexDirection: "column", justifyContent: "space-between" }}>
                <div className="card-label">Daily Ring</div>
                <div className="ring-wrap">
                  <div style={{ position: "relative", display: "inline-flex", alignItems: "center", justifyContent: "center" }}>
                    <Ring pct={pct} color={pct >= 80 ? "#34D399" : pct >= 50 ? "#FBBF24" : "#FF6B35"} size={130} stroke={12} />
                    <div style={{ position: "absolute", textAlign: "center" }}>
                      <div className="ring-pct">{pct}%</div>
                    </div>
                  </div>
                  <div className="ring-label">{doneCount} of {habits.length} complete</div>
                </div>
                <div className="quote">
                  <span className="quote-mark">"</span>
                  {quote}
                </div>
              </div>
            </div>
          </>
        )}

        {/* ── PROGRESS TAB ── */}
        {activeTab === "progress" && (
          <div className="grid">
            <div className="card span2">
              <div className="card-label">Year in Pixels</div>
              <div style={{ fontSize: 12, color: "var(--muted)", marginBottom: 10 }}>Every square is a day. Green = habits completed.</div>
              <Heatmap />
            </div>
            <div className="card">
              <div className="card-label">This Week</div>
              {habits.map(h => (
                <div key={h.id} style={{ marginBottom: 14 }}>
                  <div style={{ display: "flex", justifyContent: "space-between", fontSize: 13, marginBottom: 4 }}>
                    <span>{h.icon} {h.name}</span>
                    <span style={{ color: h.color, fontWeight: 600 }}>{h.weekData.filter(d => d.done).length}/7</span>
                  </div>
                  <div style={{ height: 6, background: "var(--surface2)", borderRadius: 3, overflow: "hidden" }}>
                    <div style={{ height: "100%", width: `${(h.weekData.filter(d => d.done).length / 7) * 100}%`, background: h.color, borderRadius: 3, transition: "width 1s" }} />
                  </div>
                </div>
              ))}
            </div>
            <div className="card" style={{ gridColumn: "1 / -1" }}>
              <div className="card-label">Streak Leaderboard</div>
              <div style={{ display: "flex", gap: 12, flexWrap: "wrap", marginTop: 8 }}>
                {[...habits].sort((a, b) => b.streak - a.streak).map((h, i) => (
                  <div key={h.id} style={{ background: "var(--surface2)", border: "1px solid var(--border)", borderRadius: 14, padding: "14px 20px", minWidth: 120 }}>
                    <div style={{ fontSize: 11, color: "var(--muted)", marginBottom: 4 }}>#{i + 1}</div>
                    <div style={{ fontSize: 22 }}>{h.icon}</div>
                    <div style={{ fontSize: 13, fontWeight: 500, marginTop: 4 }}>{h.name}</div>
                    <div style={{ fontFamily: "var(--font-display)", fontSize: 30, color: h.color }}>{h.streak}</div>
                    <div style={{ fontSize: 10, color: "var(--muted)", textTransform: "uppercase", letterSpacing: 1 }}>days</div>
                  </div>
                ))}
              </div>
            </div>
          </div>
        )}

        {/* ── COACH TAB ── */}
        {activeTab === "coach" && (
          <div className="grid">
            <div className="card span2 glow-purple">
              <div className="card-label">🤖 AI Coach — Powered by Claude</div>
              <p style={{ fontSize: 14, color: "var(--muted)", lineHeight: 1.6, marginBottom: 12 }}>
                Your personal AI coach analyzes your streaks, completion patterns, and daily data to give you a tailored motivational briefing. Hit the button for your daily insight.
              </p>
              <button className="ai-btn" onClick={getAICoach} disabled={aiLoading}>
                {aiLoading ? "Analyzing your data..." : "✦ Get My Daily Coaching"}
              </button>
              {(aiMessage || aiLoading) && (
                <div className="ai-box">
                  {aiLoading
                    ? <span className="ai-loading">Claude is reviewing your habits...</span>
                    : aiMessage}
                </div>
              )}
            </div>
            <div className="card">
              <div className="card-label">Your Stats Summary</div>
              <div style={{ display: "flex", flexDirection: "column", gap: 14, marginTop: 4 }}>
                {[
                  { label: "Total habits tracked", val: habits.length, color: "#FF6B35" },
                  { label: "Checked off today", val: doneCount, color: "#34D399" },
                  { label: "Longest current streak", val: `${longestStreak}d`, color: "#A78BFA" },
                  { label: "Weekly completions", val: totalDone, color: "#FBBF24" },
                  { label: "Today's completion", val: `${pct}%`, color: "#60A5FA" },
                ].map(s => (
                  <div key={s.label} style={{ display: "flex", justifyContent: "space-between", alignItems: "center" }}>
                    <span style={{ fontSize: 13, color: "var(--muted)" }}>{s.label}</span>
                    <span style={{ fontFamily: "var(--font-display)", fontSize: 22, color: s.color }}>{s.val}</span>
                  </div>
                ))}
              </div>
            </div>
            <div className="card" style={{ gridColumn: "1 / -1", background: "linear-gradient(135deg, #0f0e1a, #1a1025)" }}>
              <div className="card-label">💡 Momentum Insights</div>
              <div style={{ display: "grid", gridTemplateColumns: "repeat(auto-fit, minmax(220px, 1fr))", gap: 12, marginTop: 8 }}>
                {[
                  { icon: "🔥", title: "Habit Stacking", tip: "Link your habits together. When you finish your run, immediately meditate. The sequence builds faster than isolated habits." },
                  { icon: "🕐", title: "Time Anchoring", tip: "Tie each habit to a fixed time or event — morning coffee, end of work — and it becomes automatic within 3 weeks." },
                  { icon: "📊", title: "The 2-Day Rule", tip: "Never skip twice in a row. Missing once is an accident. Missing twice is a new habit — a bad one." },
                  { icon: "🏆", title: "Identity-Based Habits", tip: "Don't say 'I want to run.' Say 'I am a runner.' Identity precedes behavior. Act as who you want to become." },
                ].map(tip => (
                  <div key={tip.title} style={{ background: "var(--surface2)", border: "1px solid var(--border)", borderRadius: 14, padding: 16 }}>
                    <div style={{ fontSize: 22, marginBottom: 6 }}>{tip.icon}</div>
                    <div style={{ fontWeight: 600, fontSize: 14, marginBottom: 6 }}>{tip.title}</div>
                    <div style={{ fontSize: 13, color: "var(--muted)", lineHeight: 1.6 }}>{tip.tip}</div>
                  </div>
                ))}
              </div>
            </div>
          </div>
        )}
      </div>
    </>
  );
}
