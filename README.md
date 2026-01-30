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
  --text:#e9eefc;
  --muted:#aab6da;
  --accent:#5eead4;
  --border:rgba(255,255,255,.08);
  --radius:22px;
  --shadow:0 18px 50px rgba(0,0,0,.45);
}
*{box-sizing:border-box}
body{
  margin:0;
  font-family:ui-sans-serif,system-ui,sans-serif;
  background: radial-gradient(1200px 700px at 20% 10%, rgba(96,165,250,.22), transparent 55%),
              radial-gradient(900px 600px at 85% 35%, rgba(94,234,212,.20), transparent 50%),
              radial-gradient(900px 600px at 55% 95%, rgba(251,113,133,.14), transparent 45%),
              var(--bg);
  color:var(--text);
  min-height:100vh;
  display:flex;
  flex-direction:column;
}
header{
  position:sticky;top:0;
  backdrop-filter:blur(14px);
  background:rgba(11,18,32,.55);
  border-bottom:1px solid var(--border);
  padding:18px;
  display:flex;
  align-items:center;
  gap:14px;
}
.logo{
  width:44px;height:44px;
  border-radius:16px;
  background: linear-gradient(135deg, rgba(94,234,212,.95), rgba(96,165,250,.95));
  display:grid;place-items:center;
  font-weight:900;color:#06111f;
  font-size:18px;
}
header h1{margin:0;font-size:18px;letter-spacing:.2px}
main{
  flex:1;
  display:flex;
  flex-direction:column;
  align-items:center;
  justify-content:center;
  padding:20px;
}
input{
  padding:12px;
  border-radius:12px;
  border:1px solid var(--border);
  background:rgba(0,0,0,.18);
  color:var(--text);
  margin-bottom:12px;
  width:220px;
}
button{
  padding:12px 20px;
  border:none;
  border-radius:16px;
  background:var(--accent);
  color:#06111f;
  font-weight:700;
  cursor:pointer;
  margin-bottom:12px;
  width:240px;
}
button:disabled{opacity:.5;cursor:not-allowed}
nav{
  position:fixed;
  bottom:0;
  width:100%;
  display:flex;
  justify-content:center;
  gap:12px;
  padding:12px;
  background:rgba(11,18,32,.55);
  border-top:1px solid var(--border);
}
</style>
</head>
<body>
<header>
  <div class="logo">5M</div>
  <h1>5M PD-Tablet • Hauptseite</h1>
</header>
<main>
  <input id="username" placeholder="Benutzername" />
  <input id="password" type="password" placeholder="Passwort" />
  <button id="loginBtn">Einloggen</button>
  <p id="msg" style="color:#fb7185"></p>
</main>
<nav id="menu" style="display:none">
  <button id="btnEinwohner">Einwohner-Suche</button>
  <button id="btnFahrzeug" style="display:none">Fahrzeug-Suche</button>
  <button id="btnLeitstelle" style="display:none">Leitstelle</button>
  <button id="btnVerwaltung" style="display:none">Verwaltung</button>
</nav>
<script>
const loginBtn = document.getElementById('loginBtn');
const msg = document.getElementById('msg');
const menu = document.getElementById('menu');
const btnEinwohner = document.getElementById('btnEinwohner');
const btnFahrzeug = document.getElementById('btnFahrzeug');
const btnLeitstelle = document.getElementById('btnLeitstelle');
const btnVerwaltung = document.getElementById('btnVerwaltung');
loginBtn.addEventListener('click',()=>{
  const pw = document.getElementById('password').value;
  msg.textContent='';
  menu.style.display='none';
  btnFahrzeug.style.display='none';
  btnLeitstelle.style.display='none';
  btnVerwaltung.style.display='none';
  if(pw==='01'){
    menu.style.display='flex';
    btnEinwohner.style.display='inline-block';
    btnFahrzeug.style.display='inline-block';
    btnLeitstelle.style.display='inline-block';
    btnVerwaltung.style.display='inline-block';
  } else if(pw==='02'){
    menu.style.display='flex';
    btnEinwohner.style.display='inline-block';
  } else if(pw==='03'){
    menu.style.display='flex';
    btnEinwohner.style.display='inline-block';
    btnFahrzeug.style.display='inline-block';
  } else {
    msg.textContent='Falsches Passwort';
  }
});
btnEinwohner.addEventListener('click',()=>{
  window.open('https://2026createt.github.io/tablet-eiwohnersuche/','_blank');
});
</script>
</body>
</html>
