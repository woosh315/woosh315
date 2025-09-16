<!DOCTYPE html>
<html lang="en" data-theme="auto">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Junsu Kim — Homepage</title>
  <meta name="description" content="Junsu Kim — KAIST EE undergraduate. Computer Vision / 3D Vision, multi-view reconstruction, Gaussian Splatting." />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap" rel="stylesheet">

  <style>
    :root{
      --bg:#ffffff;--text:#111827;--muted:#6b7280;--card:#f8fafc;--accent:#2563eb;--border:#e5e7eb;
    }
    [data-theme="dark"]{
      --bg:#0b0f17;--text:#e5e7eb;--muted:#94a3b8;--card:#0f1520;--accent:#60a5fa;--border:#1f2937;
    }

    *{box-sizing:border-box}
    html,body{margin:0;padding:0;font-family:'Inter',system-ui,-apple-system,Segoe UI,Roboto,sans-serif;background:var(--bg);color:var(--text)}
    a{color:var(--accent);text-decoration:none}
    img{max-width:100%;display:block}

    .container{max-width:980px;margin:0 auto;padding:20px 16px}

    /* --- NAV --- */
    nav{position:sticky;top:0;background:var(--bg);border-bottom:1px solid var(--border);z-index:10}
    .nav-row{display:flex;align-items:center;justify-content:space-between;gap:12px}
    .nav-links a{margin-left:16px;color:var(--muted)}
    .nav-toggle{display:none}
    .toggle{border:none;background:transparent;color:var(--muted);cursor:pointer}

    /* --- HERO --- */
    .hero{display:grid;grid-template-columns:1.6fr .8fr;gap:18px;padding:36px 0}
    .hero h1{font-size:32px;margin:0 0 6px}
    .hero p{color:var(--muted);margin:6px 0 18px}
    .row{display:flex;gap:10px;flex-wrap:wrap}
    .btn{display:inline-block;padding:10px 14px;border-radius:10px;border:1px solid var(--border);background:var(--card)}
    .btn.primary{background:var(--accent);color:#fff;border-color:var(--accent)}
    .pfp{
      width:160px;height:160px;border-radius:50%;
      object-fit:cover;object-position:50% 35%;
      border:1px solid var(--border);background:#fff;
    }

    /* --- SECTIONS / CARDS --- */
    section{padding:22px 0;border-top:1px solid var(--border)}
    h2{margin:0 0 14px}
    .card{background:var(--card);border:1px solid var(--border);border-radius:14px;padding:16px}
    .card.accent{border-left:4px solid var(--accent);padding-left:14px}
    .muted{color:var(--muted)}
    .tag{font-size:12px;padding:2px 8px;border:1px solid var(--border);border-radius:999px;color:var(--muted)}


    /* --- Stacked list --- */
    .stack{display:grid;gap:18px}
    .section-subtitle{margin:0 0 6px;font-size:18px}
    ul.tight{margin:6px 0 0;padding-left:18px}
    ul.tight li{margin:4px 0}

    /* --- Education cards --- */
    .edu-list{display:grid;gap:18px}
    .edu-item{
      display:grid;grid-template-columns:88px 1fr;gap:18px;align-items:start;
      background:var(--card);border:1px solid var(--border);border-radius:14px;padding:16px
    }
    .edu-logo{
      width:72px;height:72px;border-radius:50%;
      object-fit:contain;background:#fff;border:1px solid var(--border);padding:8px
    }
    .edu-title{font-size:20px;font-weight:700}
    .edu-meta{display:flex;justify-content:space-between;color:var(--muted);margin:4px 0 6px}


	/* --- Honors: key / value two-column list --- */
	/* --- Honors 제목 좀 더 크게 --- */
	.section-subtitle{
	  font-size:20px;      /* 기존 18px → 20px */
	  font-weight:600;
	  margin-bottom:10px;
	}

	/* --- 공용: 좌측 항목 / 우측 기간(two-column) 리스트 --- */
	ul.kv{                 /* ← 이 줄이 현재 빠져 있어서 불릿이 보일 수 있음 */
	  list-style:none;
	  margin:0;
	  padding-left:0;
	}

	ul.kv li{
	  display:grid;
	  grid-template-columns: 1fr auto;  /* 왼쪽 내용, 오른쪽 기간 */
	  align-items:baseline;
	  gap:16px;
	  margin:6px 0;        /* Honors/Activities 둘 다 간격 타이트하게 */
	}

	ul.kv .k{ line-height:1.35; }
	ul.kv .v{
	  color:var(--muted);
	  white-space:nowrap;  /* 기간 줄바꿈 방지 */
	  text-align:right;    /* 더 깔끔한 우측 정렬 */
	}

	/* Honors의 설명 줄 붙여주기 */
	ul.kv .sub{
	  grid-column:1 / -1;  /* 전체 폭 사용 */
	  color:var(--muted);
	  font-style:italic;
	  margin-left:0.75rem;
	  margin-top:0;        /* 위 간격 제거 */
	  font-size:14px;
	  line-height:1.4;
	}

	/* Activities는 간격을 더 촘촘하게 */
	ul.kv.activities li{ margin:4px 0; }

	/* 모바일에서 한 줄로 비좁을 때 자동으로 세로 스택 */
	@media (max-width:480px){
	  ul.kv li{ grid-template-columns:1fr; gap:6px; }
	  ul.kv .v{ justify-self:start; margin-left:0.75rem; text-align:left; }
	}
	














    /* --- Footer --- */
    .foot{padding:28px 0;color:var(--muted);text-align:center;border-top:1px solid var(--border);margin-top:24px}

    /* ====== Responsive ====== */
    @media (max-width:760px){
      .nav-toggle{display:inline-flex}
      .nav-links{
        display:none;position:absolute;right:16px;top:56px;
        background:var(--bg);border:1px solid var(--border);
        border-radius:12px;padding:10px;width:min(88vw,320px);
        box-shadow:0 8px 24px rgba(0,0,0,.15)
      }
      .nav-links.open{display:block}

      .hero{grid-template-columns:1fr;gap:14px;padding:24px 0}
      .row{flex-direction:column;align-items:stretch}
      .btn{width:100%;text-align:center}
      .pfp{width:120px;height:120px;margin-top:8px}

      .edu-item{grid-template-columns:64px 1fr;padding:14px}
      .edu-meta{gap:6px}
/* 모바일에서 드롭다운 메뉴 항목을 세로로 꽉 차게 */
.nav-links a,
.nav-links .toggle{
  display:block;
  width:100%;
  text-align:left;
  margin:6px 0 0 0;       /* 위에 여백만 살짝 */
  padding:10px 12px;
  border-radius:8px;
}

/* 데스크탑 기본 margin-left를 모바일에선 제거 */
.nav-links a{ margin-left:0; }

/* 호버 시 살짝 배경 */
.nav-links a:hover{ background:var(--card); }
    }
    @media (max-width:480px){
      h1{font-size:clamp(22px, 5vw, 28px)}
      h2{font-size:clamp(18px, 4.2vw, 22px)}
      .pfp{width:96px;height:96px}
      .edu-item{grid-template-columns:1fr}
      .edu-logo{width:56px;height:56px;margin-bottom:6px}
      .edu-meta{flex-direction:column}
    }
  </style>
</head>
<body>
  <!-- ===== NAV ===== -->
  <nav>
    <div class="container nav-row">
      <div><strong>Junsu Kim</strong></div>

      <!-- 모바일 토글 버튼 -->
      <button id="navToggle" class="toggle nav-toggle" aria-expanded="false" aria-controls="navMenu">☰ Menu</button>

      <!-- 메뉴 -->
      <div id="navMenu" class="nav-links">
        <a href="#education">Education</a>
        <a href="#honors">Honors & Activities</a>
        <a href="#publications">Publications</a>
        <a href="#projects">Projects</a>
        <a href="#experience">Experience</a>
        <a href="/cv/" target="_blank">CV</a>
        <button id="themeBtn" class="toggle" aria-label="Toggle theme">🌙 Dark</button>
      </div>
    </div>
  </nav>

  <!-- ===== HERO ===== -->
  <header class="container hero">
    <div>
      <h1>Hi, I'm Junsu 👋</h1>
      <p>Undergraduate @ KAIST (EE). Interests in <b>Computer Vision</b> & <b>3D Vision</b>,
         multi-view reconstruction, and 3D Gaussian Splatting.</p>
      <div class="row">
        <a class="btn primary" href="/cv/" target="_blank">📄 CV</a>
        <a class="btn" href="mailto:sam9732@kaist.ac.kr">✉️ sam9732@kaist.ac.kr</a>
        <a class="btn" href="https://github.com/JJUNOS0926" target="_blank">🐙 GitHub</a>
      </div>
    </div>
    <div style="display:flex;justify-content:center;align-items:flex-start">
      <!-- 프로필 사진: 프로젝트/사용자 페이지 모두 안전하도록 상대경로 사용 -->
      <img src="images/profile.jpg?v=2" alt="Junsu Kim" class="pfp">
    </div>
  </header>

  <main class="container">
    <!-- ===== EDUCATION ===== -->
    <section id="education">
      <h2>Education</h2>
      <div class="edu-list">
        <article class="edu-item">
          <img class="edu-logo" src="images/edu/kaist_logo.png?v=2" alt="KAIST logo">
          <div>
            <div class="edu-meta">
              <div class="edu-title">Korea Advanced Institute of Science & Technology (KAIST)</div>
              <div class="muted">Daejeon, South Korea</div>
            </div>
            <ul class="tight">
              <li>B.S. in Electrical Engineering</li>
              <li>Mar 2021 – <i>Expected Aug 2027</i></li>
              <li>GPA: 4.10/4.3 (Major 4.20/4.3)</li>
            </ul>
          </div>
        </article>
      </div>
    </section>

    <!-- ===== HONORS & ACTIVITIES ===== -->
    <section id="honors">
      <h2>Honors & Activities</h2>
      <div class="stack">
	<div class="card accent">
	  <h3 class="section-subtitle">Honors</h3>
	  <ul class="kv">
	    <li>
	      <span class="k">KAIST <strong>Presidential Fellowship</strong> (15th)</span>
	      <span class="v">Feb 2025 – Present</span>
	    </li>

	    <li class="with-sub">
	      <span class="k">KAIST EE, <strong>Dean’s List Award</strong></span>
	      <span class="v">Spring 2024</span>
	      <span class="sub">Awarded to the top 3% of all EE students</span>
	    </li>

	    <li class="with-sub">
	      <span class="k">KAIST, <strong>Freshman Dean’s List Award</strong></span>
	      <span class="v">Fall 2021</span>
	      <span class="sub">Awarded to the top 3% of all freshman students</span>
	    </li>

	    <li>
	      <span class="k">Woon Hae <strong>Scholarship</strong> (12nd)</span>
	      <span class="v">Feb 2025 – Dec 2025</span>
	    </li>
	  </ul>
	</div>

	<div class="card">
	  <h3 class="section-subtitle">Activities</h3>
	  <ul class="kv activities">
	    <li>
	      <span class="k">YEHS (Young Engineers Honor Society)</span>
	      <span class="v">Jan 2025 – Present</span>
	    </li>
	    <li>
	      <span class="k">Include (KAIST AI Studying Club)</span>
	      <span class="v">Sep 2024 – Present</span>
	    </li>
	    <li>
	      <span class="k">SilverLining (KAIST International Volunteer Club)</span>
	      <span class="v">Mar 2025 – Present</span>
	    </li>
	  </ul>
	</div>

        <div class="card">
          <h3 class="section-subtitle">Skills</h3>
          <p class="muted">C/C++, Python, PyTorch</p>
        </div>
      </div>
    </section>

    <!-- ===== PUBLICATIONS ===== -->
    <section id="publications">
      <h2>Publications</h2>
      <div class="card">
        <p class="muted">— (Add here when available)</p>
      </div>
    </section>

    <!-- ===== PROJECTS ===== -->
    <section id="projects">
      <h2>Projects</h2>
      <div class="stack">
        <div class="card">
          <strong>Multi-view Scene Reconstruction</strong>
          <p class="muted">Integrating Gaussian Splatting with transformer-based depth (VGGT / NoPoSplat).</p>
          <div class="row"><span class="tag">3D Vision</span><a href="#" class="muted">repo ↗</a></div>
        </div>
        <div class="card">
          <strong>Few-shot / Anomaly Detection Baselines</strong>
          <p class="muted">Implemented object detection baselines (RCNN–YOLO, ViT) for VICLAB.</p>
          <div class="row"><span class="tag">Detection</span><a href="#" class="muted">notes ↗</a></div>
        </div>
        <div class="card">
          <strong>Talking Head Synthesis</strong>
          <p class="muted">GANs + 3DMM + neural renderers (MLILAB paper study).</p>
          <div class="row"><span class="tag">GenAI</span><a href="#" class="muted">demo ↗</a></div>
        </div>
      </div>
    </section>

    <!-- ===== EXPERIENCE ===== -->
    <section id="experience">
      <h2>Experience</h2>
      <div class="stack">
        <div class="card">
          <div class="row"><strong>CVLAB, KAIST</strong><span class="muted">Jun 2025 – Present</span></div>
          <p class="muted">Research Intern (Advisor: Prof. Seungryong Kim, KAIST AI)</p>
          <ul class="tight">
            <li>3D Vision: multi-view reconstruction, 3D Gaussian Splatting</li>
          </ul>
        </div>
        <div class="card">
          <div class="row"><strong>VICLAB, KAIST</strong><span class="muted">Dec 2024 – Jun 2025</span></div>
          <p class="muted">Research Intern (Advisor: Prof. Mun Churl Kim, KAIST EE)</p>
          <ul class="tight">
            <li>Reviewed RCNN–YOLO, ViT and implemented few-shot/anomaly detection baselines</li>
          </ul>
        </div>
      </div>
    </section>
  </main>

  <div class="foot">© 2025 Junsu Kim · <a href="mailto:sam9732@kaist.ac.kr">Contact</a></div>

  <script>
    // === Theme toggle (light/dark/auto saved) ===
    const applyTheme = t=>{
      const root=document.documentElement;
      if(t==='auto'){ root.setAttribute('data-theme', matchMedia('(prefers-color-scheme:dark)').matches?'dark':'light');}
      else { root.setAttribute('data-theme', t); }
    };
    const saved=localStorage.getItem('theme')||'auto';
    document.documentElement.setAttribute('data-theme', saved==='auto'
      ? (matchMedia('(prefers-color-scheme:dark)').matches?'dark':'light')
      : saved);
    window.addEventListener('DOMContentLoaded',()=>{
      const btn=document.getElementById('themeBtn');
      if(btn){
        const refreshLabel=()=>btn.textContent=(document.documentElement.getAttribute('data-theme')==='dark')?'☀️ Light':'🌙 Dark';
        btn.onclick=()=>{
          const cur=document.documentElement.getAttribute('data-theme');
          const next= cur==='light' ? 'dark' : 'light';
          localStorage.setItem('theme', next);applyTheme(next);refreshLabel();
        };
        refreshLabel();
      }
    });

// === Mobile nav toggle ===
(function(){
  const navBtn  = document.getElementById('navToggle');
  const navMenu = document.getElementById('navMenu');
  if (!navBtn || !navMenu) return;

  // 토글 버튼
  navBtn.addEventListener('click', () => {
    const opened = navMenu.classList.toggle('open');
    navBtn.setAttribute('aria-expanded', opened ? 'true' : 'false');
  });

  // 메뉴 바깥 클릭시 닫기
  document.addEventListener('click', (e) => {
    if (!navMenu.classList.contains('open')) return;
    const inside = navMenu.contains(e.target) || navBtn.contains(e.target);
    if (!inside) {
      navMenu.classList.remove('open');
      navBtn.setAttribute('aria-expanded', 'false'); // 추가
    }
  });

  // 메뉴 항목 클릭 시 자동 닫기 (여기가 반드시 IIFE 안쪽이어야 함)
  navMenu.querySelectorAll('a, .toggle').forEach((el) => {
    el.addEventListener('click', () => {
      navMenu.classList.remove('open');
      navBtn.setAttribute('aria-expanded', 'false');
    });
  });
})();
</script>
</body>
</html>
