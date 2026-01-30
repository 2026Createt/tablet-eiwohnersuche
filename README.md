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

    main{max-width:1100px;margin:0 auto;padding:22px 18px;}

    .card{
      border:1px solid var(--border);
      border-radius: var(--radius);
      background: linear-gradient(180deg, rgba(255,255,255,.05), rgba(255,255,255,.02));
      box-shadow: var(--shadow);
      overflow:hidden;
    }

    .card-inner{padding:18px;}

    .grid{
      display:grid;
      grid-template-columns: 1fr 1fr;
      gap:14px;
      align-items:start;
    }

    @media (max-width: 980px){
      .grid{grid-template-columns:1fr;}
    }

    .big-title{font-size:24px;margin:0 0 8px 0;letter-spacing:.2px}
    .subtitle{margin:0;color:var(--muted);line-height:1.6;font-size:13px}

    label{font-size:12px;color:var(--muted)}

    input, textarea, select{
      width:100%;
      padding:12px 12px;
      border-radius:14px;
      border:1px solid var(--border);
      background: rgba(0,0,0,.18);
      color: var(--text);
      outline:none;
      font-size:14px;
    }

    textarea{min-height:110px;resize:vertical}

    input:focus, textarea:focus, select:focus{
      border-color: rgba(94,234,212,.55);
      box-shadow:0 0 0 4px rgba(94,234,212,.10)
    }

    .form{
      display:grid;
      gap:10px;
      margin-top:12px;
    }

    .row2{display:grid;grid-template-columns:1fr 1fr;gap:10px}
    @media (max-width: 520px){.row2{grid-template-columns:1fr}}

    .btn{
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

    .btn.secondary{
      background: rgba(255,255,255,.05);
      border:1px solid var(--border);
      color: var(--text);
      box-shadow:none;
    }

    .btn.danger{
      background: rgba(251,113,133,.16);
      border:1px solid rgba(251,113,133,.35);
      color: #fecdd3;
      box-shadow:none;
    }

    .btn:active{transform: translateY(1px)}

    .toolbar{display:flex;gap:10px;flex-wrap:wrap;margin-top:12px}

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

    .search{
      display:flex;gap:10px;align-items:center;
      margin-top:12px;
    }

    .search input{flex:1}

    .list{
      margin-top:12px;
      display:grid;
      gap:10px;
    }

    .person{
      padding:12px;
      border-radius:18px;
      border:1px solid var(--border);
      background: rgba(15,23,48,.55);
      cursor:pointer;
      display:flex;
      justify-content:space-between;
      gap:12px;
      align-items:flex-start;
    }

    .person:hover{border-color: rgba(94,234,212,.25)}

    .p-name{margin:0;font-size:14px}
    .p-meta{margin:6px 0 0 0;color:var(--muted);font-size:12px;line-height:1.5}

    .pill{
      padding:6px 10px;
      border-radius:999px;
      border:1px solid var(--border);
      background: rgba(255,255,255,.04);
      font-size:12px;
      color:var(--muted);
      white-space:nowrap;
    }

    .pill.ok{border-color: rgba(52,211,153,.35); background: rgba(52,211,153,.10); color:#bbf7d0}
    .pill.warn{border-color: rgba(251,191,36,.35); background: rgba(251,191,36,.10); color:#fde68a}

    /* Modal */
    .modal-backdrop{
      position:fixed; inset:0; z-index:100;
      background: rgba(0,0,0,.55);
      backdrop-filter: blur(10px);
      display:none;
      padding: 18px;
    }

    .modal{
      max-width: 980px;
      margin: 0 auto;
      border:1px solid var(--border);
      border-radius: 26px;
      background: rgba(17,26,46,.92);
      box-shadow: var(--shadow);
      overflow:hidden;
    }

    .modal-head{
      padding: 14px 16px;
      border-bottom:1px solid var(--border);
      display:flex;
      justify-content:space-between;
      align-items:center;
      gap:10px;
    }

    .modal-head h3{margin:0;font-size:16px}

    .close{
      border:1px solid var(--border);
      background: rgba(255,255,255,.04);
      color: var(--text);
      border-radius: 14px;
      padding: 8px 10px;
      cursor:pointer;
    }

    .modal-body{padding:16px}

    .tabs{display:flex;gap:10px;flex-wrap:wrap;margin-bottom:12px}
    .tab{
      padding:10px 12px;
      border-radius: 16px;
      border: 1px solid var(--border);
      background: rgba(255,255,255,.04);
      color: var(--text);
      font-size: 13px;
      cursor:pointer;
    }
    .tab.active{border-color: rgba(94,234,212,.35); background: rgba(94,234,212,.12)}

    .tabpage{display:none}
    .tabpage.active{display:block}

    .entry{
      border:1px solid var(--border);
      background: rgba(0,0,0,.12);
      border-radius: 18px;
      padding: 12px;
      margin-top:10px;
    }

    .entry h4{margin:0 0 6px 0;font-size:13px}
    .entry p{margin:0;color:var(--muted);font-size:12px;line-height:1.5}

    .small{font-size:12px;color:var(--muted)}

  </style>
</head>
<body>
  <header>
    <div class="wrap">
      <div class="brand">
        <div class="brand-left">
          <div class="logo">5M</div>
          <div class="title">
            <h1>Einwohner-Suche • Einwohner hinzufügen</h1>
            <p>5M PD-Tablet – Datenverwaltung (lokal gespeichert)</p>
          </div>
        </div>
        <div class="badge" id="countBadge">0 Einwohner</div>
      </div>
    </div>
  </header>

  <main>
    <div class="grid">
      <!-- Formular -->
      <section class="card">
        <div class="card-inner">
          <h2 class="big-title">Einwohner hinzufügen</h2>
          <p class="subtitle">Trage Daten ein und speichere den Einwohner. Danach erscheint er rechts in der Liste.</p>

          <form id="addForm" class="form" autocomplete="off">
            <div class="row2">
              <div>
                <label>Vorname</label>
                <input id="firstName" placeholder="z.B. Max" required />
              </div>
              <div>
                <label>Nachname</label>
                <input id="lastName" placeholder="z.B. Mustermann" required />
              </div>
            </div>

            <div class="row2">
              <div>
                <label>Telefonnummer</label>
                <input id="phone" placeholder="z.B. 0176 123456" />
              </div>
              <div>
                <label>Beruf</label>
                <input id="job" placeholder="z.B. Mechaniker" />
              </div>
            </div>

            <div>
              <label>Adresse</label>
              <input id="address" placeholder="z.B. Grove Street 12" />
            </div>

            <div class="row2">
              <div>
                <label>Geburtsdatum</label>
                <input id="dob" type="date" />
              </div>
              <div>
                <label>Status</label>
                <select id="status">
                  <option value="unauffällig">Unauffällig</option>
                  <option value="auffällig">Auffällig</option>
                </select>
              </div>
            </div>

            <div class="toolbar">
              <button class="btn" type="submit">Einwohner speichern</button>
              <button class="btn secondary" type="button" id="btnDemo">Demo-Einwohner</button>
              <button class="btn danger" type="button" id="btnReset">Alles löschen</button>
            </div>

            <div class="small">Hinweis: Speicherung erfolgt lokal im Browser (localStorage). Später kann man das an eine Datenbank/API anbinden.</div>
          </form>
        </div>
      </section>

      <!-- Liste / Suche -->
      <section class="card">
        <div class="card-inner">
          <h2 class="big-title">Einwohner</h2>
          <p class="subtitle">Suche und klicke einen Einwohner an, um Details, Notizen & Strafakte zu bearbeiten.</p>

          <div class="search">
            <input id="search" placeholder="Suche nach Name, Telefon, Adresse, Beruf…" />
            <span class="badge" id="resultBadge">0 Treffer</span>
          </div>

          <div class="list" id="list"></div>
        </div>
      </section>
    </div>
  </main>

  <!-- Modal: Einwohner Details -->
  <div class="modal-backdrop" id="modalBackdrop">
    <div class="modal" role="dialog" aria-modal="true">
      <div class="modal-head">
        <div>
          <h3 id="modalTitle">Einwohner</h3>
          <div class="small" id="modalSub">—</div>
        </div>
        <button class="close" id="btnClose">Schließen ✕</button>
      </div>

      <div class="modal-body">
        <div class="tabs">
          <button class="tab active" data-tab="details">Details</button>
          <button class="tab" data-tab="notes">Notizen</button>
          <button class="tab" data-tab="record">Strafakte</button>
        </div>

        <div class="tabpage active" id="tab-details">
          <div class="entry">
            <h4>Personendaten</h4>
            <p id="detailsText">—</p>
          </div>
          <div class="toolbar" style="margin-top:12px">
            <button class="btn danger" id="btnDelete">Einwohner löschen</button>
          </div>
        </div>

        <div class="tabpage" id="tab-notes">
          <label>Notiz hinzufügen</label>
          <textarea id="noteText" placeholder="z.B. Aussage, Beobachtung, Hinweis…"></textarea>
          <div class="toolbar">
            <button class="btn" id="btnAddNote">Notiz speichern</button>
          </div>
          <div id="notesList"></div>
        </div>

        <div class="tabpage" id="tab-record">
          <label>Strafakte hinzufügen</label>
          <textarea id="recordText" placeholder="z.B. Tatbestand, Datum, Aktenzeichen…"></textarea>
          <div class="toolbar">
            <button class="btn" id="btnAddRecord">Strafakte speichern</button>
          </div>
          <div id="recordList"></div>
        </div>
      </div>
    </div>
  </div>

  <script>
    // --- Datenmodell (lokal) ---
    // Einwohner: { id, firstName, lastName, phone, job, address, dob, status, notes:[], record:[] }

    const STORAGE_KEY = 'pdtablet_einwohner_v1';

    const el = (id) => document.getElementById(id);

    const addForm = el('addForm');
    const listEl = el('list');
    const searchEl = el('search');
    const countBadge = el('countBadge');
    const resultBadge = el('resultBadge');

    const modalBackdrop = el('modalBackdrop');
    const modalTitle = el('modalTitle');
    const modalSub = el('modalSub');
    const detailsText = el('detailsText');

    const notesList = el('notesList');
    const recordList = el('recordList');

    let residents = loadResidents();
    let activeId = null;

    function uid(){
      return Math.random().toString(16).slice(2) + Date.now().toString(16);
    }

    function loadResidents(){
      try{
        const raw = localStorage.getItem(STORAGE_KEY);
        return raw ? JSON.parse(raw) : [];
      }catch{
        return [];
      }
    }

    function saveResidents(){
      localStorage.setItem(STORAGE_KEY, JSON.stringify(residents));
    }

    function fmtResident(r){
      const name = `${r.firstName} ${r.lastName}`.trim();
      const parts = [];
      if(r.phone) parts.push(`☎ ${r.phone}`);
      if(r.address) parts.push(`📍 ${r.address}`);
      if(r.job) parts.push(`💼 ${r.job}`);
      if(r.dob) parts.push(`🎂 ${r.dob}`);
      return { name, meta: parts.join(' • ') };
    }

    function matches(r, q){
      if(!q) return true;
      const s = q.toLowerCase();
      return [r.firstName, r.lastName, r.phone, r.address, r.job]
        .filter(Boolean)
        .join(' ')
        .toLowerCase()
        .includes(s);
    }

    function render(){
      const q = searchEl.value.trim();
      const filtered = residents.filter(r => matches(r, q));

      countBadge.textContent = `${residents.length} Einwohner`;
      resultBadge.textContent = `${filtered.length} Treffer`;

      listEl.innerHTML = '';
      filtered
        .sort((a,b) => (a.lastName+a.firstName).localeCompare(b.lastName+b.firstName))
        .forEach(r => {
          const {name, meta} = fmtResident(r);

          const div = document.createElement('div');
          div.className = 'person';
          div.addEventListener('click', () => openResident(r.id));

          const left = document.createElement('div');
          const h = document.createElement('h3');
          h.className = 'p-name';
          h.textContent = name || 'Unbekannt';

          const p = document.createElement('p');
          p.className = 'p-meta';
          p.textContent = meta || '—';

          left.appendChild(h);
          left.appendChild(p);

          const right = document.createElement('div');
          const pill = document.createElement('div');
          pill.className = 'pill ' + (r.status === 'auffällig' ? 'warn' : 'ok');
          pill.textContent = r.status === 'auffällig' ? 'Auffällig' : 'Unauffällig';

          right.appendChild(pill);

          div.appendChild(left);
          div.appendChild(right);

          listEl.appendChild(div);
        });
    }

    function clearForm(){
      ['firstName','lastName','phone','job','address','dob'].forEach(id => el(id).value = '');
      el('status').value = 'unauffällig';
    }

    addForm.addEventListener('submit', (e) => {
      e.preventDefault();

      const resident = {
        id: uid(),
        firstName: el('firstName').value.trim(),
        lastName: el('lastName').value.trim(),
        phone: el('phone').value.trim(),
        job: el('job').value.trim(),
        address: el('address').value.trim(),
        dob: el('dob').value,
        status: el('status').value,
        notes: [],
        record: []
      };

      residents.push(resident);
      saveResidents();
      clearForm();
      render();
    });

    el('btnDemo').addEventListener('click', () => {
      const demo = [
        {
          id: uid(),
          firstName: 'Max',
          lastName: 'Mustermann',
          phone: '0176 123456',
          job: 'Mechaniker',
          address: 'Grove Street 12',
          dob: '1997-05-21',
          status: 'unauffällig',
          notes: [{ t: 'Unauffällig bei Kontrolle.', ts: Date.now() }],
          record: []
        },
        {
          id: uid(),
          firstName: 'Lena',
          lastName: 'Klein',
          phone: '0151 777888',
          job: 'Sanitäterin',
          address: 'Vinewood Blvd 3',
          dob: '2000-11-02',
          status: 'auffällig',
          notes: [],
          record: [{ t: 'Sachbeschädigung – 12/2025', ts: Date.now() }]
        }
      ];

      residents = demo.concat(residents);
      saveResidents();
      render();
    });

    el('btnReset').addEventListener('click', () => {
      if(!confirm('Wirklich ALLE Einwohner löschen?')) return;
      residents = [];
      saveResidents();
      render();
    });

    searchEl.addEventListener('input', render);

    // --- Modal / Details ---
    function openResident(id){
      activeId = id;
      const r = residents.find(x => x.id === id);
      if(!r) return;

      const {name, meta} = fmtResident(r);
      modalTitle.textContent = name;
      modalSub.textContent = meta || '—';

      detailsText.textContent =
        `Name: ${r.firstName} ${r.lastName}` +
        (r.phone ? `
Telefon: ${r.phone}` : '') +
        (r.address ? `
Adresse: ${r.address}` : '') +
        (r.job ? `
Beruf: ${r.job}` : '') +
        (r.dob ? `
Geburtsdatum: ${r.dob}` : '') +
        `
Status: ${r.status}`;

      renderNotes(r);
      renderRecord(r);

      // Default Tab
      setTab('details');

      modalBackdrop.style.display = 'block';
    }

    function closeModal(){
      modalBackdrop.style.display = 'none';
      activeId = null;
      el('noteText').value = '';
      el('recordText').value = '';
    }

    el('btnClose').addEventListener('click', closeModal);
    modalBackdrop.addEventListener('click', (e) => {
      if(e.target === modalBackdrop) closeModal();
    });

    // Tabs
    document.querySelectorAll('.tab').forEach(btn => {
      btn.addEventListener('click', () => setTab(btn.dataset.tab));
    });

    function setTab(key){
      document.querySelectorAll('.tab').forEach(t => t.classList.toggle('active', t.dataset.tab === key));
      document.querySelectorAll('.tabpage').forEach(p => p.classList.remove('active'));
      el('tab-' + key).classList.add('active');
    }

    // Notizen
    function renderNotes(r){
      notesList.innerHTML = '';
      const arr = (r.notes || []).slice().sort((a,b)=>b.ts-a.ts);
      if(arr.length === 0){
        notesList.innerHTML = '<div class="entry"><p>Keine Notizen vorhanden.</p></div>';
        return;
      }
      arr.forEach(n => {
        const div = document.createElement('div');
        div.className = 'entry';
        const dt = new Date(n.ts);
        div.innerHTML = `<h4>Notiz • ${dt.toLocaleString()}</h4><p>${escapeHtml(n.t)}</p>`;
        notesList.appendChild(div);
      });
    }

    el('btnAddNote').addEventListener('click', () => {
      if(!activeId) return;
      const r = residents.find(x => x.id === activeId);
      if(!r) return;
      const text = el('noteText').value.trim();
      if(!text) return;
      r.notes = r.notes || [];
      r.notes.push({ t: text, ts: Date.now() });
      saveResidents();
      el('noteText').value = '';
      renderNotes(r);
      render();
    });

    // Strafakte
    function renderRecord(r){
      recordList.innerHTML = '';
      const arr = (r.record || []).slice().sort((a,b)=>b.ts-a.ts);
      if(arr.length === 0){
        recordList.innerHTML = '<div class="entry"><p>Keine Strafakte vorhanden.</p></div>';
        return;
      }
      arr.forEach(n => {
        const div = document.createElement('div');
        div.className = 'entry';
        const dt = new Date(n.ts);
        div.innerHTML = `<h4>Strafakte • ${dt.toLocaleString()}</h4><p>${escapeHtml(n.t)}</p>`;
        recordList.appendChild(div);
      });
    }

    el('btnAddRecord').addEventListener('click', () => {
      if(!activeId) return;
      const r = residents.find(x => x.id === activeId);
      if(!r) return;
      const text = el('recordText').value.trim();
      if(!text) return;
      r.record = r.record || [];
      r.record.push({ t: text, ts: Date.now() });
      saveResidents();
      el('recordText').value = '';
      renderRecord(r);
      render();
    });

    // Löschen
    el('btnDelete').addEventListener('click', () => {
      if(!activeId) return;
      const r = residents.find(x => x.id === activeId);
      if(!r) return;
      if(!confirm(`Einwohner wirklich löschen? (${r.firstName} ${r.lastName})`)) return;
      residents = residents.filter(x => x.id !== activeId);
      saveResidents();
      closeModal();
      render();
    });

    function escapeHtml(str){
      return (str || '')
        .replaceAll('&', '&amp;')
        .replaceAll('<', '&lt;')
        .replaceAll('>', '&gt;')
        .replaceAll('"', '&quot;')
        .replaceAll("'", '&#039;')
        .replaceAll('
', '<br/>');
    }

    // Init
    render();
  </script>
</body>
</html>
