<!doctype html>
<html lang="de">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>5M PD-Tablet</title>
  <style>
    :root{
      --bg:#0b1220;
      --card:#111a2e;
      --card2:#0f1730;
      --text:#e9eefc;
      --muted:#aab6da;
      --accent:#5eead4;
      --accent2:#60a5fa;
      --danger:#fb7185;
      --border:rgba(255,255,255,.08);
      --shadow: 0 18px 50px rgba(0,0,0,.45);
      --radius: 22px;
    }

    *{box-sizing:border-box}
    body{
      margin:0;
      font-family: ui-sans-serif, system-ui, -apple-system, Segoe UI, Roboto, Helvetica, Arial;
      background: radial-gradient(1200px 700px at 20% 10%, rgba(96,165,250,.22), transparent 55%),
                  radial-gradient(900px 600px at 85% 35%, rgba(94,234,212,.20), transparent 50%),
                  radial-gradient(900px 600px at 55% 95%, rgba(251,113,133,.14), transparent 45%),
                  var(--bg);
      color:var(--text);
      min-height:100vh;
      padding-bottom: 92px; /* Platz für Bottom Nav */
    }

    header{
      position: sticky;
      top: 0;
      z-index: 50;
      backdrop-filter: blur(14px);
      background: rgba(11,18,32,.55);
      border-bottom: 1px solid var(--border);
    }

    .wrap{max-width:1100px;margin:0 auto;padding:18px 18px;}

    .brand{
      display:flex;
      gap:14px;
      align-items:center;
      justify-content:space-between;
    }

    .brand-left{display:flex;gap:14px;align-items:center;}

    .logo{
      width:44px;height:44px;border-radius:16px;
      background: linear-gradient(135deg, rgba(94,234,212,.95), rgba(96,165,250,.95));
      box-shadow: 0 12px 30px rgba(0,0,0,.35);
      display:grid;place-items:center;
      color:#06111f;font-weight:900;
      letter-spacing:.5px;
    }

    .title h1{margin:0;font-size:18px;line-height:1.2}
    .title p{margin:3px 0 0 0;color:var(--muted);font-size:13px}

    .status-pill{
      display:flex;gap:8px;align-items:center;
      padding:8px 12px;border-radius:999px;
      border:1px solid var(--border);
      background: rgba(255,255,255,.04);
      font-size:13px;color:var(--muted);
    }

    .dot{width:9px;height:9px;border-radius:50%;background:var(--danger);box-shadow:0 0 0 4px rgba(251,113,133,.15)}
    .dot.ok{background:var(--accent);box-shadow:0 0 0 4px rgba(94,234,212,.12)}

    main{max-width:1100px;margin:0 auto;padding:22px 18px;}

    .hero{
      display:grid;
      grid-template-columns: 1.2fr .8fr;
      gap:18px;
      align-items:stretch;
    }

    @media (max-width: 860px){
      .hero{grid-template-columns:1fr;}
    }

    .card{
      border:1px solid var(--border);
      border-radius: var(--radius);
      background: linear-gradient(180deg, rgba(255,255,255,.05), rgba(255,255,255,.02));
      box-shadow: var(--shadow);
      overflow:hidden;
    }

    .card-inner{padding:18px;}

    .big-title{font-size:28px;margin:0 0 8px 0;letter-spacing:.2px}
    .subtitle{margin:0;color:var(--muted);line-height:1.6}

    .grid{
      display:grid;
      grid-template-columns: repeat(3, 1fr);
      gap:12px;
      margin-top:16px;
    }

    @media (max-width: 860px){
      .grid{grid-template-columns:1fr;}
    }

    .tile{
      padding:14px;
      border-radius:18px;
      border:1px solid var(--border);
      background: rgba(15,23,48,.55);
    }

    .tile h3{margin:0 0 6px 0;font-size:14px}
    .tile p{margin:0;color:var(--muted);font-size:13px;line-height:1.5}

    .login{
      background: linear-gradient(180deg, rgba(17,26,46,.75), rgba(15,23,48,.55));
    }

    .form-row{display:grid;gap:10px;margin-top:10px}

    label{font-size:12px;color:var(--muted)}

    input{
      width:100%;
      padding:12px 12px;
      border-radius:14px;
      border:1px solid var(--border);
      background: rgba(0,0,0,.18);
      color: var(--text);
      outline:none;
      font-size:14px;
    }

    input:focus{border-color: rgba(94,234,212,.55); box-shadow:0 0 0 4px rgba(94,234,212,.10)}

    .btn{
      width:100%;
      padding:12px 14px;
      border-radius:16px;
      border:0;
      cursor:pointer;
      font-weight:700;
      font-size:14px;
      color:#06111f;
      background: linear-gradient(135deg, rgba(94,234,212,.95), rgba(96,165,250,.95));
      box-shadow: 0 14px 40px rgba(0,0,0,.35);
    }

    .btn:active{transform: translateY(1px)}

    .hint{margin-top:10px;color:var(--muted);font-size:12px;line-height:1.6}

    .err{margin-top:10px;color: #fecdd3;font-size:12px;display:none}

    /* Bottom Nav */
    .bottom-nav{
      position: fixed;
      left: 0; right: 0; bottom: 0;
      z-index: 60;
      padding: 10px 12px;
      background: rgba(11,18,32,.65);
      border-top: 1px solid var(--border);
      backdrop-filter: blur(16px);
    }

    .nav-inner{
      max-width:1100px;
      margin:0 auto;
      display:flex;
      gap:10px;
      align-items:center;
      justify-content:space-between;
    }

    .nav-items{
      display:flex;
      gap:10px;
      align-items:center;
      flex-wrap:wrap;
    }

    .nav-btn{
      padding:10px 12px;
      border-radius: 16px;
      border: 1px solid var(--border);
      background: rgba(255,255,255,.04);
      color: var(--text);
      font-size: 13px;
      cursor:pointer;
      display:flex;
      align-items:center;
      gap:8px;
    }

    .nav-btn[disabled]{
      opacity:.35;
      cursor:not-allowed;
    }

    .nav-btn.primary{
      background: linear-gradient(135deg, rgba(94,234,212,.25), rgba(96,165,250,.18));
      border-color: rgba(94,234,212,.25);
    }

    .nav-right{
      display:flex; gap:10px; align-items:center;
    }

    .role{
      padding:10px 12px;
      border-radius:999px;
      border:1px solid var(--border);
      background: rgba(255,255,255,.04);
      font-size:13px;
      color: var(--muted);
      white-space:nowrap;
    }

    .role b{color:var(--text)}

    .ghost{
      padding:10px 12px;
      border-radius:16px;
      border:1px solid var(--border);
      background: transparent;
      color: var(--muted);
      cursor:pointer;
      font-size: 13px;
    }

    .ghost:hover{color:var(--text)}

    /* Page state */
    .page{
      display:none;
    }
    .page.active{display:block;}

    .page h2{margin:0 0 8px 0;font-size:18px}
    .page p{margin:0;color:var(--muted);line-height:1.6}

    .placeholder{
      margin-top:14px;
      border:1px dashed rgba(255,255,255,.14);
      border-radius: 18px;
      padding: 14px;
      background: rgba(0,0,0,.12);
      color: var(--muted);
      font-size: 13px;
    }

    .badge{
      display:inline-flex;
      align-items:center;
      gap:8px;
      padding: 6px 10px;
      border-radius: 999px;
      border: 1px solid var(--border);
      background: rgba(255,255,255,.04);
      font-size: 12px;
      color: var(--muted);
    }
  </style>
</head>
<body>
  <header>
    <div class="wrap">
      <div class="brand">
        <div class="brand-left">
          <div class="logo">5M</div>
          <div class="title">
            <h1>PD-Tablet • Einsatz & Verwaltung</h1>
            <p>Login-gesteuertes Menü für PD / FD / Ambulanz</p>
          </div>
        </div>
        <div class="status-pill" id="statusPill">
          <span class="dot" id="statusDot"></span>
          <span id="statusText">Nicht eingeloggt</span>
        </div>
      </div>
    </div>
  </header>

  <main>
    <!-- Start / Dashboard -->
    <section class="page active" id="page-dashboard">
      <div class="hero">
        <div class="card">
          <div class="card-inner">
            <h2 class="big-title">Willkommen im 5M PD-Tablet</h2>
            <p class="subtitle">
              Diese Basis-Webseite enthält: Login, Rollen (PD/FD/Ambulanz) und dynamische Menüs.
              Die Unterseiten/Links (z.B. Leitstelle, Einwohner-Suche etc.) können wir als nächstes einbauen.
            </p>

            <div class="grid">
              <div class="tile">
                <h3>🔐 Rollen-Login</h3>
                <p>Passwort 01 = PD • 02 = FD • 03 = Ambulanz</p>
              </div>
              <div class="tile">
                <h3>🧭 Tablet-Menü unten</h3>
                <p>Bottom Navigation wie auf einem Tablet – Menüs werden je nach Rolle freigeschaltet.</p>
              </div>
              <div class="tile">
                <h3>⚙️ Erweiterbar</h3>
                <p>Jeder Menüpunkt kann später auf eine eigene Seite / externen Link zeigen.</p>
              </div>
            </div>

            <div class="placeholder">
              <span class="badge">Hinweis</span>
              <div style="margin-top:10px">
                Du kannst dich unten über <b>Einloggen</b> anmelden.
              </div>
            </div>
          </div>
        </div>

        <div class="card login">
          <div class="card-inner">
            <h2 style="margin:0 0 6px 0; font-size:18px">Login</h2>
            <p class="subtitle" style="font-size:13px">
              Benutzername ist egal. Passwort bestimmt die Rolle.
            </p>

            <form id="loginForm" class="form-row" autocomplete="off">
              <div>
                <label for="username">Benutzername</label>
                <input id="username" name="username" placeholder="z.B. Max" />
              </div>
              <div>
                <label for="password">Passwort</label>
                <input id="password" name="password" placeholder="01 / 02 / 03" inputmode="numeric" />
              </div>
              <button class="btn" type="submit">Einloggen</button>
              <div class="err" id="loginError">Falsches Passwort. Erlaubt: 01, 02, 03.</div>
              <div class="hint">
                <b>01</b> = PD (alle Menüs) <br/>
                <b>02</b> = FD (nur Einwohner-Suche) <br/>
                <b>03</b> = Ambulanz (Einwohner-Suche + Fahrzeug-Suche)
              </div>
            </form>
          </div>
        </div>
      </div>
    </section>

    <!-- Pages (Platzhalter) -->
    <section class="page" id="page-einwohner">
      <div class="card"><div class="card-inner">
        <h2>Einwohner-Suche</h2>
        <p>Platzhalter. Hier kommt später die echte Suche / der Link rein.</p>
        <div class="placeholder">TODO: Suchmaske + Ergebnisliste / API-Anbindung</div>
      </div></div>
    </section>

    <section class="page" id="page-fahrzeug">
      <div class="card"><div class="card-inner">
        <h2>Fahrzeug-Suche</h2>
        <p>Platzhalter. Hier kommt später die echte Suche / der Link rein.</p>
        <div class="placeholder">TODO: Suchmaske + Fahrzeugdaten</div>
      </div></div>
    </section>

    <section class="page" id="page-leitstelle">
      <div class="card"><div class="card-inner">
        <h2>Leitstelle</h2>
        <p>Platzhalter. Nur für PD sichtbar.</p>
        <div class="placeholder">TODO: Leitstellen-Übersicht / Einsätze / Funkkanäle</div>
      </div></div>
    </section>

    <section class="page" id="page-verwaltung">
      <div class="card"><div class="card-inner">
        <h2>Verwaltung</h2>
        <p>Platzhalter. Nur für PD sichtbar.</p>
        <div class="placeholder">TODO: Akten, Berichte, Logs</div>
      </div></div>
    </section>

  </main>

  <nav class="bottom-nav" aria-label="Tablet Menü">
    <div class="nav-inner">
      <div class="nav-items">
        <button class="nav-btn primary" data-page="dashboard">🏠 Start</button>
        <button class="nav-btn" id="btnEinwohner" data-page="einwohner" disabled>👤 Einwohner-Suche</button>
        <button class="nav-btn" id="btnFahrzeug" data-page="fahrzeug" disabled>🚑 Fahrzeug-Suche</button>
        <button class="nav-btn" id="btnLeitstelle" data-page="leitstelle" disabled>📟 Leitstelle</button>
        <button class="nav-btn" id="btnVerwaltung" data-page="verwaltung" disabled>🗂️ Verwaltung</button>
      </div>

      <div class="nav-right">
        <div class="role" id="rolePill">Rolle: <b>—</b></div>
        <button class="ghost" id="btnLogout" disabled>Logout</button>
      </div>
    </div>
  </nav>

  <script>
    // Rollen / Rechte
    // PD: alles
    // FD: nur Einwohner
    // Ambulanz: Einwohner + Fahrzeug

    const state = {
      role: null, // 'PD' | 'FD' | 'AMB'
      username: ''
    };

    const pages = {
      dashboard: document.getElementById('page-dashboard'),
      einwohner: document.getElementById('page-einwohner'),
      fahrzeug: document.getElementById('page-fahrzeug'),
      leitstelle: document.getElementById('page-leitstelle'),
      verwaltung: document.getElementById('page-verwaltung'),
    };

    const statusDot = document.getElementById('statusDot');
    const statusText = document.getElementById('statusText');
    const rolePill = document.getElementById('rolePill');

    const btnEinwohner = document.getElementById('btnEinwohner');
    const btnFahrzeug = document.getElementById('btnFahrzeug');
    const btnLeitstelle = document.getElementById('btnLeitstelle');
    const btnVerwaltung = document.getElementById('btnVerwaltung');
    const btnLogout = document.getElementById('btnLogout');

    const loginForm = document.getElementById('loginForm');
    const loginError = document.getElementById('loginError');

    function setActivePage(key){
      Object.values(pages).forEach(p => p.classList.remove('active'));
      pages[key].classList.add('active');
      window.scrollTo({top:0, behavior:'smooth'});
    }

    function updateUI(){
      const loggedIn = !!state.role;

      // Status
      statusDot.classList.toggle('ok', loggedIn);
      statusText.textContent = loggedIn
        ? `Eingeloggt als ${state.role}`
        : 'Nicht eingeloggt';

      rolePill.innerHTML = loggedIn
        ? `Rolle: <b>${state.role}</b>`
        : 'Rolle: <b>—</b>';

      // Default alles sperren
      btnEinwohner.disabled = true;
      btnFahrzeug.disabled = true;
      btnLeitstelle.disabled = true;
      btnVerwaltung.disabled = true;

      // Rechte setzen
      if(state.role === 'PD'){
        btnEinwohner.disabled = false;
        btnFahrzeug.disabled = false;
        btnLeitstelle.disabled = false;
        btnVerwaltung.disabled = false;
      }
      if(state.role === 'FD'){
        btnEinwohner.disabled = false;
      }
      if(state.role === 'AMB'){
        btnEinwohner.disabled = false;
        btnFahrzeug.disabled = false;
      }

      btnLogout.disabled = !loggedIn;
    }

    function login(username, password){
      const pw = (password || '').trim();
      if(pw === '01') state.role = 'PD';
      else if(pw === '02') state.role = 'FD';
      else if(pw === '03') state.role = 'AMB';
      else return false;

      state.username = (username || '').trim();
      return true;
    }

    function logout(){
      state.role = null;
      state.username = '';
      updateUI();
      setActivePage('dashboard');
    }

    // Bottom Nav click
    document.querySelectorAll('[data-page]').forEach(btn => {
      btn.addEventListener('click', () => {
        const page = btn.getAttribute('data-page');
        if(btn.disabled) return;
        setActivePage(page);
      });
    });

    // Login submit
    loginForm.addEventListener('submit', (e) => {
      e.preventDefault();
      loginError.style.display = 'none';

      const username = document.getElementById('username').value;
      const password = document.getElementById('password').value;

      const ok = login(username, password);
      if(!ok){
        loginError.style.display = 'block';
        return;
      }

      updateUI();
      setActivePage('dashboard');

      // optional: Passwortfeld leeren
      document.getElementById('password').value = '';
    });

    btnLogout.addEventListener('click', logout);

    // Init
    updateUI();
  </script>
</body>
</html>
