<!doctype html>
<html lang="de">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>5M PD-Tablet</title>
<style>
:root{
  --bg:#0b1220;
  --text:#e9eefc;
  --muted:#aab6da;
  --accent:#5eead4;
  --border:rgba(255,255,255,.08);
  --radius:22px;
  --shadow:0 18px 50px rgba(0,0,0,.45);
}
body{margin:0;font-family:ui-sans-serif,system-ui,sans-serif;background: radial-gradient(1200px 700px at 20% 10%, rgba(96,165,250,.22), transparent 55%),radial-gradient(900px 600px at 85% 35%, rgba(94,234,212,.20), transparent 50%),radial-gradient(900px 600px at 55% 95%, rgba(251,113,133,.14), transparent 45%),var(--bg);color:var(--text);min-height:100vh;display:flex;flex-direction:column;}
header{position:sticky;top:0;backdrop-filter:blur(14px);background:rgba(11,18,32,.55);border-bottom:1px solid var(--border);padding:18px;display:flex;align-items:center;gap:14px;justify-content:space-between;}
.logo{width:44px;height:44px;border-radius:16px;background: linear-gradient(135deg, rgba(94,234,212,.95), rgba(96,165,250,.95));display:grid;place-items:center;color:#06111f;font-weight:900;letter-spacing:.5px;}
header h1{margin:0;font-size:18px}
main{flex:1;display:flex;flex-direction:column;justify-content:center;align-items:center;gap:14px;padding:22px 18px;}
input{padding:12px;border-radius:14px;border:1px solid var(--border);background: rgba(0,0,0,.18);color: var(--text);outline:none;width:220px;margin-bottom:12px}
button{padding:12px 14px;border-radius:16px;border:0;cursor:pointer;font-weight:700;font-size:14px;color:#06111f;background: linear-gradient(135deg, rgba(94,234,212,.95), rgba(96,165,250,.95));margin-bottom:12px;width:240px;}
button:disabled{opacity:.5;cursor:not-allowed;}
</style>
</head>
<body>
<header>
  <div class="logo">5M</div>
  <h1>5M PD-Tablet</h1>
</header>
<main>
  <input id="username" placeholder="Benutzername">
  <input id="password" placeholder="Passwort" type="password">
  <button id="btnLogin">Einloggen</button>
  <div id="menu" style="display:none;flex-direction:column;align-items:center;gap:12px;margin-top:22px;">
    <button id="btnEinwohner" style="display:none;">Einwohner-Suche</button>
    <button id="btnFahrzeug" style="display:none;">Fahrzeug-Suche</button>
    <button id="btnLeitstelle" style="display:none;">Leitstelle</button>
    <button id="btnVerwaltung" style="display:none;">Verwaltung</button>
  </div>
</main>
<script>
const btnLogin = document.getElementById('btnLogin');
const menu = document.getElementById('menu');
const btnEinwohner = document.getElementById('btnEinwohner');
const btnFahrzeug = document.getElementById('btnFahrzeug');
const btnLeitstelle = document.getElementById('btnLeitstelle');
const btnVerwaltung = document.getElementById('btnVerwaltung');

btnLogin.addEventListener('click',()=>{
  const pw = document.getElementById('password').value.trim();
  menu.style.display='flex';
  btnEinwohner.style.display='none';
  btnFahrzeug.style.display='none';
  btnLeitstelle.style.display='none';
  btnVerwaltung.style.display='none';

  if(pw==='01'){ // PD
    btnEinwohner.style.display='block';
    btnFahrzeug.style.display='block';
    btnLeitstelle.style.display='block';
    btnVerwaltung.style.display='block';
  }else if(pw==='02'){ // FD
    btnEinwohner.style.display='block';
  }else if(pw==='03'){ // Ambulanz
    btnEinwohner.style.display='block';
    btnFahrzeug.style.display='block';
  }else{
    alert('Falsches Passwort');
    menu.style.display='none';
  }
});

btnEinwohner.addEventListener('click',()=>{
  window.open('https://2026createt.github.io/tablet-eiwohnersuche/', '_blank');
});
btnFahrzeug.addEventListener('click',()=>{
  window.open('https://2026createt.github.io/fahrzeugsuche-/', '_blank');
});
btnLeitstelle.addEventListener('click',()=>{alert('Leitstelle Funktion kommt später');});
btnVerwaltung.addEventListener('click',()=>{alert('Verwaltung Funktion kommt später');});
</script>
</body>
</html>
