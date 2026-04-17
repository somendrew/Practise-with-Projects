# Practise-with-Projects

<!DOCTYPE html>

<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Aesthetic Body Plan</title>
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #0a0a0a;
    --card: #111111;
    --card2: #161616;
    --accent: #c8f135;
    --accent2: #7fff6e;
    --text: #f0f0f0;
    --muted: #666;
    --border: #222;
  }
  * { margin: 0; padding: 0; box-sizing: border-box; }
  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'DM Sans', sans-serif;
    min-height: 100vh;
    padding: 24px 16px 60px;
  }

/* HEADER */
.header {
text-align: center;
padding: 40px 0 32px;
position: relative;
}
.header::before {
content: ‘’;
position: absolute;
top: 0; left: 50%; transform: translateX(-50%);
width: 1px; height: 40px;
background: linear-gradient(to bottom, transparent, var(–accent));
}
.header-tag {
font-size: 11px;
letter-spacing: 4px;
text-transform: uppercase;
color: var(–accent);
margin-bottom: 12px;
}
.header h1 {
font-family: ‘Bebas Neue’, sans-serif;
font-size: clamp(52px, 12vw, 88px);
line-height: 0.9;
letter-spacing: 2px;
color: var(–text);
}
.header h1 span { color: var(–accent); }
.header-sub {
margin-top: 16px;
font-size: 13px;
color: var(–muted);
letter-spacing: 1px;
}

/* STATS ROW */
.stats {
display: grid;
grid-template-columns: repeat(4, 1fr);
gap: 8px;
max-width: 560px;
margin: 28px auto 36px;
}
.stat {
background: var(–card);
border: 1px solid var(–border);
border-radius: 10px;
padding: 14px 10px;
text-align: center;
}
.stat-val {
font-family: ‘Bebas Neue’, sans-serif;
font-size: 26px;
color: var(–accent);
line-height: 1;
}
.stat-label {
font-size: 10px;
color: var(–muted);
text-transform: uppercase;
letter-spacing: 1px;
margin-top: 4px;
}

/* WEEK SCHEDULE STRIP */
.week-strip {
display: flex;
justify-content: center;
gap: 8px;
margin-bottom: 36px;
flex-wrap: wrap;
}
.day-pill {
padding: 8px 16px;
border-radius: 100px;
font-size: 12px;
font-weight: 500;
letter-spacing: 1px;
text-transform: uppercase;
border: 1px solid var(–border);
background: var(–card);
color: var(–muted);
}
.day-pill.active {
background: var(–accent);
color: #000;
border-color: var(–accent);
font-weight: 700;
}
.day-pill.off {
color: #333;
border-color: #1a1a1a;
}

/* FOCUS BADGES */
.section-label {
font-size: 11px;
letter-spacing: 3px;
text-transform: uppercase;
color: var(–accent);
text-align: center;
margin-bottom: 20px;
}

/* DAY CARDS */
.days-grid {
display: grid;
gap: 12px;
max-width: 680px;
margin: 0 auto 48px;
}
.day-card {
background: var(–card);
border: 1px solid var(–border);
border-radius: 16px;
overflow: hidden;
transition: border-color 0.2s;
}
.day-card:hover { border-color: #333; }

.day-header {
display: flex;
align-items: center;
justify-content: space-between;
padding: 18px 20px 14px;
cursor: pointer;
user-select: none;
}
.day-left { display: flex; align-items: center; gap: 14px; }
.day-num {
font-family: ‘Bebas Neue’, sans-serif;
font-size: 36px;
color: var(–accent);
line-height: 1;
min-width: 32px;
}
.day-info {}
.day-name {
font-size: 11px;
color: var(–muted);
text-transform: uppercase;
letter-spacing: 2px;
}
.day-focus {
font-family: ‘Bebas Neue’, sans-serif;
font-size: 22px;
letter-spacing: 1px;
line-height: 1.1;
margin-top: 2px;
}
.badge {
font-size: 10px;
font-weight: 600;
letter-spacing: 1px;
text-transform: uppercase;
padding: 4px 10px;
border-radius: 100px;
background: rgba(200,241,53,0.1);
color: var(–accent);
border: 1px solid rgba(200,241,53,0.2);
}
.badge.chest { background: rgba(99,179,237,0.1); color: #63b3ed; border-color: rgba(99,179,237,0.2); }
.badge.back { background: rgba(154,117,234,0.1); color: #9a75ea; border-color: rgba(154,117,234,0.2); }
.badge.legs { background: rgba(246,173,85,0.1); color: #f6ad55; border-color: rgba(246,173,85,0.2); }
.badge.shoulders { background: rgba(200,241,53,0.1); color: var(–accent); border-color: rgba(200,241,53,0.2); }
.badge.arms { background: rgba(252,129,129,0.1); color: #fc8181; border-color: rgba(252,129,129,0.2); }

.toggle-icon {
font-size: 18px;
color: var(–muted);
transition: transform 0.3s;
}
.day-card.open .toggle-icon { transform: rotate(180deg); }

.exercises {
display: none;
padding: 0 20px 20px;
}
.day-card.open .exercises { display: block; }

.divider { height: 1px; background: var(–border); margin-bottom: 16px; }

.ex-row {
display: grid;
grid-template-columns: 1fr auto;
align-items: start;
padding: 10px 0;
border-bottom: 1px solid #181818;
gap: 12px;
}
.ex-row:last-child { border-bottom: none; }
.ex-name {
font-size: 14px;
font-weight: 500;
color: var(–text);
}
.ex-note {
font-size: 11px;
color: var(–muted);
margin-top: 2px;
}
.ex-sets {
font-size: 12px;
font-weight: 600;
color: var(–accent);
white-space: nowrap;
text-align: right;
padding-top: 2px;
}

/* NUTRITION */
.section-block {
max-width: 680px;
margin: 0 auto 48px;
}
.nutrition-grid {
display: grid;
grid-template-columns: 1fr 1fr;
gap: 12px;
}
.nut-card {
background: var(–card);
border: 1px solid var(–border);
border-radius: 14px;
padding: 18px;
}
.nut-card.full { grid-column: 1 / -1; }
.nut-icon { font-size: 22px; margin-bottom: 8px; }
.nut-title {
font-size: 11px;
text-transform: uppercase;
letter-spacing: 2px;
color: var(–muted);
margin-bottom: 6px;
}
.nut-val {
font-family: ‘Bebas Neue’, sans-serif;
font-size: 28px;
color: var(–accent);
line-height: 1;
}
.nut-desc {
font-size: 12px;
color: var(–muted);
line-height: 1.6;
margin-top: 8px;
}

/* TIPS */
.tips-list {
display: grid;
gap: 10px;
}
.tip {
background: var(–card);
border: 1px solid var(–border);
border-left: 3px solid var(–accent);
border-radius: 0 12px 12px 0;
padding: 14px 16px;
font-size: 13px;
color: #ccc;
line-height: 1.6;
}
.tip strong { color: var(–text); }

/* FOOTER */
.footer {
text-align: center;
font-size: 11px;
color: #333;
letter-spacing: 2px;
text-transform: uppercase;
margin-top: 40px;
}
</style>

</head>
<body>

<div class="header">
  <div class="header-tag">Your Personal Program</div>
  <h1>AESTHETIC<br><span>BODY</span> PLAN</h1>
  <div class="header-sub">5 Days · Full Gym · 8–10 PM Sessions</div>
</div>

<div class="stats">
  <div class="stat"><div class="stat-val">69</div><div class="stat-label">kg</div></div>
  <div class="stat"><div class="stat-val">175</div><div class="stat-label">cm</div></div>
  <div class="stat"><div class="stat-val">5</div><div class="stat-label">days/wk</div></div>
  <div class="stat"><div class="stat-val">~60</div><div class="stat-label">min/day</div></div>
</div>

<div class="week-strip">
  <div class="day-pill active">Mon</div>
  <div class="day-pill off">Tue ✕</div>
  <div class="day-pill active">Wed</div>
  <div class="day-pill active">Thu</div>
  <div class="day-pill active">Fri</div>
  <div class="day-pill active">Sat</div>
  <div class="day-pill off">Sun ✕</div>
</div>

<div class="section-label">↓ Tap any day to expand ↓</div>

<div class="days-grid">

  <!-- MONDAY -->

  <div class="day-card" onclick="toggle(this)">
    <div class="day-header">
      <div class="day-left">
        <div class="day-num">01</div>
        <div class="day-info">
          <div class="day-name">Monday</div>
          <div class="day-focus">Chest + Triceps</div>
        </div>
      </div>
      <div style="display:flex;gap:8px;align-items:center">
        <div class="badge chest">Push</div>
        <div class="toggle-icon">▾</div>
      </div>
    </div>
    <div class="exercises">
      <div class="divider"></div>
      <div class="ex-row"><div><div class="ex-name">Flat Barbell Bench Press</div><div class="ex-note">Main chest builder — control the descent</div></div><div class="ex-sets">4 × 8–10</div></div>
      <div class="ex-row"><div><div class="ex-name">Incline Dumbbell Press</div><div class="ex-note">Upper chest emphasis — key for aesthetics</div></div><div class="ex-sets">3 × 10–12</div></div>
      <div class="ex-row"><div><div class="ex-name">Cable Chest Flyes</div><div class="ex-note">Stretch and squeeze — go slow</div></div><div class="ex-sets">3 × 12–15</div></div>
      <div class="ex-row"><div><div class="ex-name">Dips (weighted if possible)</div><div class="ex-note">Lean forward slightly for chest</div></div><div class="ex-sets">3 × 10–12</div></div>
      <div class="ex-row"><div><div class="ex-name">Tricep Rope Pushdown</div><div class="ex-note">Elbows pinned to sides</div></div><div class="ex-sets">3 × 12–15</div></div>
      <div class="ex-row"><div><div class="ex-name">Overhead Tricep Extension</div><div class="ex-note">Long head activation</div></div><div class="ex-sets">3 × 12</div></div>
      <div class="ex-row"><div><div class="ex-name">Hanging Leg Raises</div><div class="ex-note">Core finisher — squeeze at top</div></div><div class="ex-sets">3 × 15</div></div>
    </div>
  </div>

  <!-- WEDNESDAY -->

  <div class="day-card" onclick="toggle(this)">
    <div class="day-header">
      <div class="day-left">
        <div class="day-num">02</div>
        <div class="day-info">
          <div class="day-name">Wednesday</div>
          <div class="day-focus">Back + Biceps</div>
        </div>
      </div>
      <div style="display:flex;gap:8px;align-items:center">
        <div class="badge back">Pull</div>
        <div class="toggle-icon">▾</div>
      </div>
    </div>
    <div class="exercises">
      <div class="divider"></div>
      <div class="ex-row"><div><div class="ex-name">Pull-Ups / Lat Pulldown</div><div class="ex-note">Wide grip — builds the V-taper</div></div><div class="ex-sets">4 × 8–10</div></div>
      <div class="ex-row"><div><div class="ex-name">Barbell Bent-Over Row</div><div class="ex-note">Chest up, pull to lower chest</div></div><div class="ex-sets">4 × 8–10</div></div>
      <div class="ex-row"><div><div class="ex-name">Seated Cable Row</div><div class="ex-note">Squeeze shoulder blades at end</div></div><div class="ex-sets">3 × 12</div></div>
      <div class="ex-row"><div><div class="ex-name">Single-Arm Dumbbell Row</div><div class="ex-note">Full range of motion</div></div><div class="ex-sets">3 × 12</div></div>
      <div class="ex-row"><div><div class="ex-name">Barbell Curl</div><div class="ex-note">Strict form, no swinging</div></div><div class="ex-sets">3 × 10</div></div>
      <div class="ex-row"><div><div class="ex-name">Incline Dumbbell Curl</div><div class="ex-note">Full stretch at bottom</div></div><div class="ex-sets">3 × 12</div></div>
      <div class="ex-row"><div><div class="ex-name">Plank + Cable Crunches</div><div class="ex-note">2 rounds of each</div></div><div class="ex-sets">2 × 20</div></div>
    </div>
  </div>

  <!-- THURSDAY -->

  <div class="day-card" onclick="toggle(this)">
    <div class="day-header">
      <div class="day-left">
        <div class="day-num">03</div>
        <div class="day-info">
          <div class="day-name">Thursday</div>
          <div class="day-focus">Shoulders (Priority)</div>
        </div>
      </div>
      <div style="display:flex;gap:8px;align-items:center">
        <div class="badge shoulders">⭐ Focus</div>
        <div class="toggle-icon">▾</div>
      </div>
    </div>
    <div class="exercises">
      <div class="divider"></div>
      <div class="ex-row"><div><div class="ex-name">Seated Dumbbell Shoulder Press</div><div class="ex-note">Primary mass builder — controlled reps</div></div><div class="ex-sets">4 × 8–10</div></div>
      <div class="ex-row"><div><div class="ex-name">Lateral Raises</div><div class="ex-note">⭐ King of aesthetic shoulders — slight lean</div></div><div class="ex-sets">5 × 15–20</div></div>
      <div class="ex-row"><div><div class="ex-name">Cable Lateral Raise</div><div class="ex-note">Constant tension variation</div></div><div class="ex-sets">3 × 15</div></div>
      <div class="ex-row"><div><div class="ex-name">Face Pulls (cable)</div><div class="ex-note">Rear delt + rotator cuff health</div></div><div class="ex-sets">4 × 15</div></div>
      <div class="ex-row"><div><div class="ex-name">Rear Delt Fly (pec deck)</div><div class="ex-note">Full rear delt roundness</div></div><div class="ex-sets">3 × 15</div></div>
      <div class="ex-row"><div><div class="ex-name">Arnold Press</div><div class="ex-note">Hits all 3 delt heads</div></div><div class="ex-sets">3 × 10</div></div>
      <div class="ex-row"><div><div class="ex-name">Ab Circuit</div><div class="ex-note">Crunches + Reverse Crunches + Plank</div></div><div class="ex-sets">3 rounds</div></div>
    </div>
  </div>

  <!-- FRIDAY -->

  <div class="day-card" onclick="toggle(this)">
    <div class="day-header">
      <div class="day-left">
        <div class="day-num">04</div>
        <div class="day-info">
          <div class="day-name">Friday</div>
          <div class="day-focus">Legs + Glutes</div>
        </div>
      </div>
      <div style="display:flex;gap:8px;align-items:center">
        <div class="badge legs">Legs</div>
        <div class="toggle-icon">▾</div>
      </div>
    </div>
    <div class="exercises">
      <div class="divider"></div>
      <div class="ex-row"><div><div class="ex-name">Barbell Back Squat</div><div class="ex-note">Bread and butter — depth matters</div></div><div class="ex-sets">4 × 8</div></div>
      <div class="ex-row"><div><div class="ex-name">Romanian Deadlift</div><div class="ex-note">Hamstrings + glutes — slow eccentric</div></div><div class="ex-sets">4 × 10</div></div>
      <div class="ex-row"><div><div class="ex-name">Leg Press</div><div class="ex-note">High foot placement for glutes</div></div><div class="ex-sets">3 × 12</div></div>
      <div class="ex-row"><div><div class="ex-name">Walking Lunges</div><div class="ex-note">Good for symmetry and balance</div></div><div class="ex-sets">3 × 12/leg</div></div>
      <div class="ex-row"><div><div class="ex-name">Leg Curl (machine)</div><div class="ex-note">Isolate hamstrings</div></div><div class="ex-sets">3 × 12</div></div>
      <div class="ex-row"><div><div class="ex-name">Calf Raises (standing)</div><div class="ex-note">Slow — pause at top and bottom</div></div><div class="ex-sets">4 × 20</div></div>
    </div>
  </div>

  <!-- SATURDAY -->

  <div class="day-card" onclick="toggle(this)">
    <div class="day-header">
      <div class="day-left">
        <div class="day-num">05</div>
        <div class="day-info">
          <div class="day-name">Saturday</div>
          <div class="day-focus">Arms + Abs (Full)</div>
        </div>
      </div>
      <div style="display:flex;gap:8px;align-items:center">
        <div class="badge arms">Arms</div>
        <div class="toggle-icon">▾</div>
      </div>
    </div>
    <div class="exercises">
      <div class="divider"></div>
      <div class="ex-row"><div><div class="ex-name">EZ-Bar Curl</div><div class="ex-note">Wrist-friendly bicep builder</div></div><div class="ex-sets">4 × 10</div></div>
      <div class="ex-row"><div><div class="ex-name">Hammer Curl</div><div class="ex-note">Brachialis for arm thickness</div></div><div class="ex-sets">3 × 12</div></div>
      <div class="ex-row"><div><div class="ex-name">Concentration Curl</div><div class="ex-note">Peak contraction focus</div></div><div class="ex-sets">3 × 12</div></div>
      <div class="ex-row"><div><div class="ex-name">Close-Grip Bench Press</div><div class="ex-note">Tricep mass — key for arm size</div></div><div class="ex-sets">4 × 10</div></div>
      <div class="ex-row"><div><div class="ex-name">Skull Crushers</div><div class="ex-note">Full stretch on tricep long head</div></div><div class="ex-sets">3 × 12</div></div>
      <div class="ex-row"><div><div class="ex-name">Cable Crunch</div><div class="ex-note">Weighted — key for visible abs</div></div><div class="ex-sets">4 × 15–20</div></div>
      <div class="ex-row"><div><div class="ex-name">Hanging Leg Raises</div><div class="ex-note">Lower abs emphasis</div></div><div class="ex-sets">3 × 15</div></div>
      <div class="ex-row"><div><div class="ex-name">Russian Twists</div><div class="ex-note">Obliques for that carved look</div></div><div class="ex-sets">3 × 20</div></div>
    </div>
  </div>

</div>

<!-- NUTRITION -->

<div class="section-block">
  <div class="section-label">Nutrition at 69kg</div>
  <div class="nutrition-grid">
    <div class="nut-card">
      <div class="nut-icon">🔥</div>
      <div class="nut-title">Daily Calories</div>
      <div class="nut-val">2,300–2,500</div>
      <div class="nut-desc">Slight surplus on training days to build muscle while staying lean.</div>
    </div>
    <div class="nut-card">
      <div class="nut-icon">🥩</div>
      <div class="nut-title">Protein Target</div>
      <div class="nut-val">140–160g</div>
      <div class="nut-desc">~2g per kg bodyweight. Non-negotiable for muscle building.</div>
    </div>
    <div class="nut-card full">
      <div class="nut-icon">🕗</div>
      <div class="nut-title">Timing for 8–10pm training</div>
      <div class="nut-desc" style="font-size:13px">
        <strong style="color:var(--text)">Pre-workout (7–7:30pm):</strong> Medium meal — rice + chicken or oats + protein shake. Avoid heavy meals right before.<br><br>
        <strong style="color:var(--text)">Post-workout (10–10:30pm):</strong> Whey protein shake + banana or rice cakes. Keep it light so it doesn't disrupt sleep.<br><br>
        <strong style="color:var(--text)">Your 1.5 scoop shake:</strong> Great post-workout choice. Add a banana or 2 rice cakes to replenish glycogen.
      </div>
    </div>
  </div>
</div>

<!-- TIPS -->

<div class="section-block">
  <div class="section-label">Pro Tips for Corporate Athletes</div>
  <div class="tips-list">
    <div class="tip"><strong>Sleep is your #1 muscle builder.</strong> Since you train at 10pm, aim for 7–8 hours regardless. Wind down 30 min after training — no screens.</div>
    <div class="tip"><strong>Progressive overload every week.</strong> Add 1–2 reps or 2.5kg to your main lifts each week. This is what drives visible change over months.</div>
    <div class="tip"><strong>Abs are made in the kitchen.</strong> At your stats (69kg / 175cm) you likely need to lose a thin layer of fat to see abs — keep calories in check 5 days a week.</div>
    <div class="tip"><strong>Shoulders take time.</strong> Lateral raises are the single best move for that wide-shoulder look. Do them every session if possible — they recover fast.</div>
    <div class="tip"><strong>Corporate sitting = tight hips.</strong> Spend 5 min stretching hip flexors before leg day or squats will suffer. Cat-cow and couch stretch at your desk if possible.</div>
    <div class="tip"><strong>First 4 weeks:</strong> Focus on form and feel over weight. Your muscles remember — you'll come back faster than you think after the 6-month break.</div>
  </div>
</div>

<div class="footer">Built for your goals · Consistency beats perfection</div>

<script>
  function toggle(card) {
    card.classList.toggle('open');
  }
  // Open Monday by default
  document.querySelector('.day-card').classList.add('open');
</script>

</body>
</html>