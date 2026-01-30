<!doctype html>
<html lang="de">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Einwohner-Suche • 5M PD-Tablet</title>
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
body{
  margin:0;
  font-family:ui-sans-serif,system-ui,sans-serif;
  background: radial-gradient(1200px 700px at 20% 10%, rgba(96,165,250,.22), transparent 55%),
              radial-gradient(900px 600px at 85% 35%, rgba(94,234,212,.20), transparent 50%),
              radial-gradient(900px 600px at 55% 95%, rgba(251,113,133,.14), transparent 45%),
              var(--bg);
  color:var(--text);
  min-height:100vh;
  padding-bottom:22px;
}
header{position:sticky;top:0;backdrop-filter:blur(14px);background:rgba(11,18,32,.55);border-bottom:1px solid var(--border);padding:18px;display:flex;align-items:center;gap:14px;}
.logo{width:44px;height:44px;border-radius:16px;background: linear-gradient(135deg, rgba(94,234,212,.95), rgba(96,165,250,.95));display:grid;place-items:center;color:#06111f;font-weight:900;letter-spacing:.5px;}
header h1{margin:0;font-size:18px}
main{max-width:1100px;margin:0 auto;padding:22px 18px;}
.card{border:1px solid var(--border);border-radius: var(--radius);background: linear-gradient(180deg, rgba(255,255,255,.05), rgba(255,255,255,.02));box-shadow: var(--shadow);overflow:hidden;}
.card-inner{padding:18px;}
.grid{display:grid;grid-template-columns:1fr 1fr;gap:14px;align-items:start;}
@media(max-width:980px){.grid{grid-template-columns:1fr}}
.big-title{font-size:24px;margin:0 0 8px 0}
.subtitle{margin:0;color:var(--muted);font-size:13px}
input, textarea, select{width:100%;padding:12px;border-radius:14px;border:1px solid var(--border);background: rgba(0,0,0,.18);color: var(--text);outline:none;margin-bottom:8px}
textarea{min-height:110px;resize:vertical}
.btn{padding:12px 14px;border-radius:16px;border:0;cursor:pointer;font-weight:700;font-size:14px;color:#06111f;background: linear-gradient(135deg, rgba(94,234,212,.95), rgba(96,165,250,.95));margin-bottom:8px;}
.btn.secondary{background: rgba(255,255,255,.05);border:1px solid var(--border);color: var(--text);}
.btn.danger{background: rgba(251,113,133,.16);border:1px solid rgba(251,113,133,.35);color: #fecdd3;}
.btn:active{transform: translateY(1px)}
.toolbar{display:flex;gap:10px;flex-wrap:wrap;margin-top:12px}
.list{margin-top:12px;display:grid;gap:10px;}
.person{padding:12px;border-radius:18px;border:1px solid var(--border);background: rgba(15,23,48,.55);cursor:pointer;display:flex;justify-content:space-between;gap:12px;align-items:flex-start;}
.p-name{margin:0;font-size:14px}
.p-meta{margin:6px 0 0 0;color:var(--muted);font-size:12px;line-height:1.5}
.pill{padding:6px 10px;border-radius:999px;border:1px solid var(--border);background: rgba(255,255,255,.04);font-size:12px;color:var(--muted);white-space:nowrap;}
.pill.ok{border-color: rgba(52,211,153,.35); background: rgba(52,211,153,.10); color:#bbf7d0}
.pill.warn{border-color: rgba(251,191,36,.35); background: rgba(251,191,36,.10); color:#fde68a}
.modal-backdrop{position:fixed;inset:0;z-index:100;background: rgba(0,0,0,.55);backdrop-filter: blur(10px);display:none;padding: 18px;}
.modal{max-width: 980px;margin: 0 auto;border:1px solid var(--border);border-radius: 26px;background: rgba(17,26,46,.92);box-shadow: var(--shadow);overflow:hidden;}
.modal-head{padding: 14px 16px;border-bottom:1px solid var(--border);display:flex;justify-content:space-between;align-items:center;gap:10px}
.modal-head h3{margin:0;font-size:16px}
.close{border:1px solid var(--border);background: rgba(255,255,255,.04);color: var(--text);border-radius: 14px;padding: 8px 10px;cursor:pointer;}
.modal-body{padding:16px}
.tabs{display:flex;gap:10px;flex-wrap:wrap;margin-bottom:12px}
.tab{padding:10px 12px;border-radius: 16px;border: 1px solid var(--border);background: rgba(255,255,255,.04);color: var(--text);font-size: 13px;cursor:pointer;}
.tab.active{border-color: rgba(94,234,212,.35); background: rgba(94,234,212,.12)}
.tabpage{display:none}.tabpage.active{display:block}
.entry{border:1px solid var(--border);background: rgba(0,0,0,.12);border-radius: 18px;padding: 12px;margin-top:10px;}
.entry h4{margin:0 0 6px 0;font-size:13px}
.entry p{margin:0;color:var(--muted);font-size:12px;line-height:1.5}
.small{font-size:12px;color:var(--muted)}
</style>
</head>
<body>
<header>
  <div class="logo">5M</div>
  <h1>Einwohner-Suche • 5M PD-Tablet</h1>
</header>
<main>
  <div class="grid">
    <section class="card">
      <div class="card-inner">
        <h2 class="big-title">Einwohner hinzufügen</h2>
        <p class="subtitle">Trage alle Daten ein</p>
        <form id="addForm" class="form">
          <input id="firstName" placeholder="Vorname" required />
          <input id="lastName" placeholder="Nachname" required />
          <input id="phone" placeholder="Telefon" />
          <input id="job" placeholder="Beruf" />
          <input id="address" placeholder="Adresse" />
          <input id="dob" type="date" />
          <select id="status">
            <option value="unauffällig">Unauffällig</option>
            <option value="auffällig">Auffällig</option>
          </select>
          <div class="toolbar">
            <button class="btn" type="submit">Speichern</button>
            <button class="btn secondary" type="button" id="btnReset">Alles löschen</button>
          </div>
        </form>
      </div>
    </section>
    <section class="card">
      <div class="card-inner">
        <h2 class="big-title">Einwohnerliste</h2>
        <input id="search" placeholder="Suche nach Name, Telefon, Adresse, Beruf…" />
        <div class="list" id="list"></div>
      </div>
    </section>
  </div>
</main>
<div class="modal-backdrop" id="modalBackdrop">
  <div class="modal">
    <div class="modal-head">
      <h3 id="modalTitle">Einwohner</h3>
      <button class="close" id="btnClose">✕</button>
    </div>
    <div class="modal-body">
      <div class="tabs">
        <button class="tab active" data-tab="details">Details</button>
        <button class="tab" data-tab="notes">Notizen</button>
        <button class="tab" data-tab="record">Strafakte</button>
      </div>
      <div class="tabpage active" id="tab-details"><p id="detailsText"></p></div>
      <div class="tabpage" id="tab-notes">
        <textarea id="noteText" placeholder="Neue Notiz..."></textarea>
        <button class="btn" id="btnAddNote">Notiz speichern</button>
        <div id="notesList"></div>
      </div>
      <div class="tabpage" id="tab-record">
        <textarea id="recordText" placeholder="Neue Strafakte..."></textarea>
        <button class="btn" id="btnAddRecord">Strafakte speichern</button>
        <div id="recordList"></div>
      </div>
    </div>
  </div>
</div>
<script>
const STORAGE_KEY='pdtablet_einwohner_v3';
const el=id=>document.getElementById(id);
let residents=JSON.parse(localStorage.getItem(STORAGE_KEY)||'[]');
let activeId=null;

function save(){localStorage.setItem(STORAGE_KEY,JSON.stringify(residents));}
function uid(){return Date.now().toString(16)+Math.random().toString(16).slice(2);}
function clearForm(){['firstName','lastName','phone','job','address','dob'].forEach(id=>el(id).value='');el('status').value='unauffällig';}

function fmtResident(r){return {name:`${r.firstName} ${r.lastName}`.trim(),meta:[r.phone?r.phone:'',r.address?r.address:'',r.job?r.job:''].filter(Boolean).join(' • ')}};
function matches(r,q){if(!q)return true;const s=q.toLowerCase();return [r.firstName,r.lastName,r.phone,r.address,r.job].filter(Boolean).join(' ').toLowerCase().includes(s);}

function render(){
  const q=el('search').value.trim();
  const filtered=residents.filter(r=>matches(r,q));
  el('list').innerHTML='';
  filtered.sort((a,b)=>a.lastName.localeCompare(b.lastName)).forEach(r=>{
    const div=document.createElement('div');
    div.className='person';
    div.addEventListener('click',()=>openResident(r.id));
    const {name,meta}=fmtResident(r);
    div.innerHTML=`<div><h3 class='p-name'>${name||'Unbekannt'}</h3><p class='p-meta'>${meta||'—'}</p></div><div><div class='pill ${r.status==='auffällig'?'warn':'ok'}'>${r.status==='auffällig'?'Auffällig':'Unauffällig'}</div></div>`;
    el('list').appendChild(div);
  });
}

el('addForm').addEventListener('submit',e=>{
  e.preventDefault();
  const r={id:uid(),firstName:el('firstName').value.trim(),lastName:el('lastName').value.trim(),phone:el('phone').value.trim(),job:el('job').value.trim(),address:el('address').value.trim(),dob:el('dob').value,status:el('status').value,notes:[],record:[]};
  residents.push(r);save();clearForm();render();
});
el('btnReset').addEventListener('click',()=>{if(confirm('ALLE Einwohner löschen?')){residents=[];save();render();}});
el('search').addEventListener('input',render);

// Modal & Tabs
function openResident(id){
  activeId=id;
  const r=residents.find(x=>x.id===id);
  if(!r)return;
  el('modalTitle').textContent=`${r.firstName} ${r.lastName}`;
  el('detailsText').textContent=`Telefon: ${r.phone||'-'}\nAdresse: ${r.address||'-'}\nBeruf: ${r.job||'-'}\nGeburtsdatum: ${r.dob||'-'}\nStatus: ${r.status}`;
  renderNotes(r);renderRecord(r);
  setTab('details');
  el('modalBackdrop').style.display='block';
}
function closeModal(){el('modalBackdrop').style.display='none';activeId=null;el('noteText').value='';el('recordText').value='';}
el('btnClose').addEventListener('click',closeModal);
el('modalBackdrop').addEventListener('click',e=>{if(e.target===el('modalBackdrop'))closeModal();});
function setTab(k){document.querySelectorAll('.tab').forEach(t=>t.classList.toggle('active',t.dataset.tab===k));document.querySelectorAll('.tabpage').forEach(p=>p.classList.remove('active'));el('tab-'+k).classList.add('active');}
document.querySelectorAll('.tab').forEach(btn=>btn.addEventListener('click',()=>setTab(btn.dataset.tab)));

function renderNotes(r){const nl=el('notesList');nl.innerHTML='';(r.notes||[]).slice().sort((a,b)=>b.ts-a.ts).forEach(n=>{const d=document.createElement('div');d.className='entry';const dt=new Date(n.ts);d.innerHTML=`<h4>Notiz • ${dt.toLocaleString()}</h4><p>${escapeHtml(n.t)}</p>`;nl.appendChild(d);});if(!r.notes||r.notes.length===0)nl.innerHTML='<div class="entry"><p>Keine Notizen</p></div>';}
function renderRecord(r){const rl=el('recordList');rl.innerHTML='';(r.record||[]).slice().sort((a,b)=>b.ts-a.ts).forEach(n=>{const d=document.createElement('div');d.className='entry';const dt=new Date(n.ts);d.innerHTML=`<h4>Strafakte • ${dt.toLocaleString()}</h4><p>${escapeHtml(n.t)}</p>`;rl.appendChild(d);});if(!r.record||r.record.length===0)rl.innerHTML='<div class="entry"><p>Keine Strafakte</p></div>';}
el('btnAddNote').addEventListener('click',()=>{if(!activeId)return;const r=residents.find(x=>x.id===activeId);if(!r)return;const t=el('noteText').value.trim();if(!t)return;r.notes=r.notes||[];r.notes.push({t,ts:Date.now()});save();el('noteText').value='';renderNotes(r);render();});
el('btnAddRecord').addEventListener('click',()=>{if(!activeId)return;const r=residents.find(x=>x.id===activeId);if(!r)return;const t=el('recordText').value.trim();if(!t)return;r.record=r.record||[];r.record.push({t,ts:Date.now()});save();el('recordText').value='';renderRecord(r);render();});
function escapeHtml(str){return(str||'').replaceAll('&','&amp;').replaceAll('<','&lt;').replaceAll('>','&gt;').replaceAll('"','&quot;').replaceAll("'",'&#039;').replaceAll('\n','<br/>');}
render();
</script>
</body>
</html>
