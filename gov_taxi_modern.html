<!doctype html>
<html lang="th">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>GovTaxi — Modern Prototype</title>
  <!-- Google Font -->
  <link href="https://fonts.googleapis.com/css2?family=Prompt:wght@300;400;600;700&display=swap" rel="stylesheet">
  <!-- Leaflet -->
  <link rel="stylesheet" href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css" crossorigin=""/>
  <!-- Lucide icons -->
  <script src="https://unpkg.com/lucide/dist/lucide.min.js"></script>
  <style>
    :root{
      --bg:#f4f8fb; --card:#ffffff; --muted:#6b8895; --accent:#0ea5a4; --accent-2:#0b6fa8; --danger:#f43f5e; --glass: rgba(255,255,255,0.65);
      --radius:14px; --glass-blur:8px; --shadow: 0 8px 24px rgba(11,47,68,0.08);
      font-family: 'Prompt', 'Noto Sans Thai', sans-serif; color:#0b2b3a;
    }
    *{box-sizing:border-box}
    html,body{height:100%;margin:0;background:linear-gradient(180deg,#f7fbfd,var(--bg));}
    .app{max-width:1200px;margin:22px auto;padding:18px}

    header{display:flex;align-items:center;justify-content:space-between;gap:12px}
    .brand{display:flex;gap:12px;align-items:center}
    .logo{width:56px;height:56px;border-radius:12px;background:linear-gradient(135deg,var(--accent-2),var(--accent));display:flex;align-items:center;justify-content:center;color:white;font-weight:800;font-size:18px;box-shadow:var(--shadow)}
    h1{margin:0;font-size:18px}
    .sub{color:var(--muted);font-size:13px}

    .controls{display:flex;gap:10px;align-items:center}
    .btn{background:var(--accent);color:white;padding:10px 14px;border-radius:10px;border:0;font-weight:700;cursor:pointer;box-shadow:0 6px 18px rgba(14,122,120,0.12)}
    .btn.ghost{background:transparent;color:var(--accent-2);border:1px solid rgba(11,111,120,0.08)}

    .layout{display:grid;grid-template-columns:1fr 360px;gap:18px;margin-top:18px}
    .card{background:var(--card);border-radius:var(--radius);padding:14px;box-shadow:var(--shadow)}

    #map{height:520px;border-radius:12px;overflow:hidden}

    .search-row{display:grid;grid-template-columns:1fr 1fr;gap:10px}
    input,select,textarea{width:100%;padding:12px;border-radius:10px;border:1px solid #e6f0f4;background:transparent;font-size:14px}

    .status-log{height:120px;overflow:auto;padding:10px;border-radius:10px;background:linear-gradient(180deg,#f6fbff,#fff);border:1px solid #eaf6fb}

    .driver-item{display:flex;gap:12px;align-items:center;padding:10px;border-radius:12px;border:1px solid #f1f6f8;margin-bottom:8px}
    .avatar{width:56px;height:56px;border-radius:12px;background:linear-gradient(135deg,var(--accent),var(--accent-2));display:flex;align-items:center;justify-content:center;color:white;font-weight:800}
    .small{font-size:13px;color:var(--muted)}

    .assigned-footer{position:fixed;left:50%;transform:translateX(-50%);bottom:22px;width:min(1000px,calc(100% - 48px));display:flex;align-items:center;justify-content:space-between;gap:12px;padding:12px;border-radius:14px;background:linear-gradient(180deg,rgba(255,255,255,0.96),rgba(255,255,255,0.92));box-shadow:0 16px 40px rgba(6,46,60,0.12);border:1px solid #eef6fb}

    .eta-bar{height:8px;border-radius:999px;background:#eef8f7;overflow:hidden}
    .eta-fill{height:100%;width:0%;background:linear-gradient(90deg,var(--accent),var(--accent-2));transition:width 1s linear}

    .toast{position:fixed;right:22px;top:22px;background:#0b6fa8;color:white;padding:10px 14px;border-radius:10px;box-shadow:0 8px 24px rgba(11,47,68,0.12);display:flex;gap:10px;align-items:center}

    .history-list{max-height:220px;overflow:auto}

    /* responsive */
    @media (max-width:1000px){.layout{grid-template-columns:1fr} #map{height:380px} .assigned-footer{left:12px;transform:none;width:calc(100% - 24px)}}
  </style>
</head>
<body>
  <div class="app">
    <header>
      <div class="brand">
        <div class="logo">GT</div>
        <div>
          <h1>GovTaxi — Modern Prototype</h1>
          <div class="sub">ระบบจำลองเรียกแท็กซี่ — Modern UX / Interactive Demo</div>
        </div>
      </div>

      <div class="controls">
        <button id="toggleTheme" class="btn ghost">🌙 Dark</button>
        <button id="openHistory" class="btn ghost">📜 ประวัติ</button>
        <button id="newCall" class="btn">เรียกแท็กซี่</button>
      </div>
    </header>

    <div class="layout">
      <main>
        <div class="card">
          <div style="display:flex;gap:12px;align-items:center;justify-content:space-between">
            <div>
              <div class="small">ตำแหน่งขึ้น</div>
              <div style="margin-top:6px" class="search-row">
                <input id="pickup" placeholder="เช่น BTS สยาม" value="BTS สยาม">
                <input id="dest" placeholder="เช่น สนามบินสุวรรณภูมิ" value="สนามบินสุวรรณภูมิ">
              </div>
            </div>
            <div style="width:240px">
              <div class="small">จำนวนผู้โดยสาร</div>
              <select id="pax" style="margin-top:6px"><option>1</option><option>2</option><option>3</option><option>4</option></select>
              <div style="margin-top:10px;display:flex;gap:8px">
                <button id="callBtn" class="btn" style="flex:1">🔍 เริ่มค้นหา</button>
                <button id="quickBtn" class="btn ghost">⚡️ Quick</button>
              </div>
            </div>
          </div>

          <div style="display:flex;gap:12px;margin-top:14px;align-items:flex-start">
            <div style="flex:1">
              <div id="map" class="card"></div>

              <div style="display:flex;gap:8px;margin-top:12px;align-items:center">
                <div class="pill" style="font-weight:700;color:var(--accent-2)">Prototype</div>
                <div class="small">โทน: Modern — Interactive demo</div>
              </div>
            </div>

            <aside style="width:340px">
              <div class="card">
                <h3 style="margin:0 0 8px 0">สถานะการค้นหา</h3>
                <div id="log" class="status-log">ระบบพร้อมใช้งาน</div>
                <div style="margin-top:10px;display:flex;gap:8px">
                  <div style="flex:1"><div class="small">การเรียกทั้งหมด</div><div id="statCalls" style="font-weight:800">0</div></div>
                  <div style="flex:1"><div class="small">สำเร็จ</div><div id="statSuccess" style="font-weight:800">0</div></div>
                </div>
              </div>

              <div class="card" style="margin-top:12px">
                <h3 style="margin:0 0 8px 0">ไดรเวอร์ใกล้เคียง (จำลอง)</h3>
                <div id="driversList" class="history-list" style="margin-top:6px"></div>
              </div>

              <div class="card" style="margin-top:12px">
                <h3 style="margin:0 0 8px 0">ให้คะแนน / ข้อเสนอแนะ</h3>
                <div id="ratingArea" class="small">หลังใช้งานจะมีพื้นที่ให้ให้คะแนนอัตโนมัติ</div>
              </div>
            </aside>
          </div>
        </div>

        <div class="card" style="margin-top:14px">
          <h3 style="margin:0 0 8px 0">เกี่ยวกับ GovTaxi (Modern)</h3>
          <p class="small" style="margin:0">เวอร์ชันต้นแบบนี้ออกแบบมาเพื่อสาธิตแนวทาง UX ที่ทันสมัย: การจับคู่อัจฉริยะ, ระบบสำรอง, การให้รางวัล และการบันทึกประวัติการปฏิเสธ</p>
        </div>
      </main>

      <!-- right column summary -->
      <div>
        <div class="card">
          <h3 style="margin:0 0 8px 0">แดชบอร์ดสรุป</h3>
          <div style="display:flex;gap:8px;margin-top:8px">
            <div style="flex:1"><div class="small">ปฏิเสธ</div><div id="statReject" style="font-weight:800">0</div></div>
            <div style="flex:1"><div class="small">เวลาเฉลี่ยจับคู่</div><div id="statAvg" style="font-weight:800">-</div></div>
          </div>

          <hr style="margin:12px 0;border:none;border-top:1px solid #eef6fa" />
          <h4 style="margin:0 0 8px 0">ประวัติการเรียก (Local)</h4>
          <div id="history" class="history-list small" style="margin-top:6px"></div>

          <div style="margin-top:12px;display:flex;gap:8px">
            <button id="clearHistory" class="btn ghost" style="flex:1">ล้างประวัติ</button>
            <button id="exportHistory" class="btn" style="flex:1">ส่งออก JSON</button>
          </div>
        </div>

        <div class="card" style="margin-top:12px">
          <h3 style="margin:0 0 8px 0">เอกสารอ้างอิง</h3>
          <div class="small">ต้นแบบนี้ใช้ Leaflet (OSM) ในการแสดงตำแหน่ง และ LocalStorage สำหรับบันทึกประวัติ</div>
        </div>
      </div>
    </div>

    <!-- assigned footer (hidden until assigned) -->
    <div id="assignedFooter" class="assigned-footer" style="display:none">
      <div style="display:flex;gap:12px;align-items:center">
        <div class="avatar" id="drvAvatar">A</div>
        <div>
          <div id="drvTitle" style="font-weight:800">คนขับ: -</div>
          <div id="drvSub" class="small">รถ - • ทะเบียน -</div>
        </div>
      </div>
      <div style="flex:1">
        <div class="small">สถานะการเดินทาง</div>
        <div class="eta-bar" style="margin-top:8px"><div id="etaFill" class="eta-fill"></div></div>
      </div>
      <div style="display:flex;gap:8px;align-items:center">
        <button id="contactDriver" class="btn ghost">📞 ติดต่อ</button>
        <button id="cancelBtn" class="btn" style="background:var(--danger)">ยกเลิก</button>
      </div>
    </div>

    <!-- toast container -->
    <div id="toastRoot" style="position:fixed;right:22px;top:22px;z-index:9999"></div>

  </div>

  <!-- Leaflet JS -->
  <script src="https://unpkg.com/leaflet@1.9.4/dist/leaflet.js" crossorigin=""></script>
  <script>
    // --- mock drivers ---
    const mockDrivers = [
      {id:1,name:'สมชาย',car:'Toyota Altis',plate:'กข 1234',loc:[13.746,100.534],rating:4.8,acceptProb:0.6},
      {id:2,name:'ประวิทย์',car:'Honda City',plate:'ขว 5678',loc:[13.751,100.538],rating:4.6,acceptProb:0.5},
      {id:3,name:'หญิงใจ',car:'Mitsubishi Mirage',plate:'กค 9012',loc:[13.744,100.535],rating:4.9,acceptProb:0.8},
      {id:4,name:'ณรงค์',car:'Toyota Vios',plate:'งข 2233',loc:[13.752,100.540],rating:4.4,acceptProb:0.45},
      {id:5,name:'เจษฎา',car:'Nissan Almera',plate:'จล 3344',loc:[13.740,100.530],rating:4.2,acceptProb:0.35}
    ];

    // stats
    let stats = {calls:0,success:0,reject:0,totalMatchTime:0};

    // init map
    const map = L.map('map').setView([13.746,100.537],14);
    L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png',{maxZoom:19,attribution:'© OpenStreetMap'}).addTo(map);
    const drvMarkers = [];
    mockDrivers.forEach(d=>{ const m=L.marker(d.loc).addTo(map).bindPopup(`<strong>${d.name}</strong><br>${d.car} • ${d.plate}`); drvMarkers.push(m); });

    // UI refs
    const log = document.getElementById('log');
    const driversList = document.getElementById('driversList');
    const callBtn = document.getElementById('callBtn');
    const statCalls = document.getElementById('statCalls');
    const statSuccess = document.getElementById('statSuccess');
    const statReject = document.getElementById('statReject');
    const statAvg = document.getElementById('statAvg');
    const assignedFooter = document.getElementById('assignedFooter');
    const drvAvatar = document.getElementById('drvAvatar');
    const drvTitle = document.getElementById('drvTitle');
    const drvSub = document.getElementById('drvSub');
    const etaFill = document.getElementById('etaFill');
    const toastRoot = document.getElementById('toastRoot');

    // render drivers
    function renderDrivers(){
      driversList.innerHTML='';
      mockDrivers.forEach(d=>{
        const div=document.createElement('div');div.className='driver-item';
        div.innerHTML = `<div class='avatar'>${d.name.charAt(0)}</div><div style='flex:1'><div style='font-weight:800'>${d.name}</div><div class='small'>${d.car} • ${d.plate}</div><div class='small'>Rating ${d.rating} • Accept ${Math.round(d.acceptProb*100)}%</div></div>`;
        driversList.appendChild(div);
      });
    }
    renderDrivers();

    function appendLog(txt){ const time=new Date().toLocaleTimeString('th-TH'); log.innerHTML=`<div>[${time}] ${txt}</div>` + log.innerHTML; }

    // toast helper
    function toast(msg,timeout=3500){ const t=document.createElement('div'); t.className='toast'; t.innerHTML=`<div style='font-weight:700;margin-right:8px'>GovTaxi</div><div>${msg}</div>`; toastRoot.appendChild(t); setTimeout(()=>{ t.style.opacity=0; setTimeout(()=>t.remove(),400); }, timeout); }

    // wait util
    function wait(ms){ return new Promise(res=>setTimeout(res,ms)); }

    // history localstorage
    function saveHistory(entry){ const h=JSON.parse(localStorage.getItem('gov_history')||'[]'); h.unshift(entry); localStorage.setItem('gov_history',JSON.stringify(h)); renderHistory(); }
    function renderHistory(){ const h=JSON.parse(localStorage.getItem('gov_history')||'[]'); const el=document.getElementById('history'); el.innerHTML=''; if(!h.length){ el.innerHTML='<div class="small">ยังไม่มีประวัติ</div>'; return; } h.slice(0,20).forEach(it=>{ const d=document.createElement('div'); d.className='small'; d.style.padding='8px 0'; d.innerHTML=`<div style="font-weight:700">${it.pickup} → ${it.dest}</div><div class='small'>${it.time} — ${it.status}</div>`; el.appendChild(d);} ); }
    renderHistory();

    // main matching flow (modern with animation + ETA bar)
    callBtn.addEventListener('click', async ()=>{
      const pickup=document.getElementById('pickup').value; const dest=document.getElementById('dest').value; const pax=document.getElementById('pax').value;
      stats.calls++; statCalls.textContent=stats.calls; appendLog(`เริ่มค้นหา ${pickup} → ${dest} (${pax} pax)`); toast('เริ่มค้นหาแท็กซี่...');

      // simple ranking by acceptProb + randomness
      const start=performance.now();
      let drivers = mockDrivers.map(d=>({...d,score:d.acceptProb + Math.random()*0.25})).sort((a,b)=>b.score-a.score);
      // show pulsing markers for each try
      let assigned=null;
      for(let i=0;i<drivers.length;i++){
        const d=drivers[i]; appendLog(`ส่งคำขอไปยัง ${d.name}`); toast(`ส่งคำขอไปยัง ${d.name}`);
        // animate marker (fly to driver)
        map.flyTo(d.loc,15,{duration:0.8});
        await wait(900 + Math.random()*600);
        const r=Math.random();
        if(r < d.acceptProb){ assigned=d; appendLog(`${d.name} ยอมรับคำขอ`); stats.success++; statSuccess.textContent=stats.success; toast(`${d.name} ยอมรับคำขอ`); break; }
        else{ appendLog(`${d.name} ปฏิเสธ`); stats.reject++; statReject.textContent=stats.reject; // boost others
          drivers.forEach((x,idx)=>{ if(idx>i) x.acceptProb = Math.min(0.98, x.acceptProb + 0.06); }); }
      }
      const end=performance.now(); const elapsed=Math.round((end-start)/1000); stats.totalMatchTime+=elapsed; statAvg.textContent=(stats.totalMatchTime / Math.max(1,stats.calls)).toFixed(1)+'s';

      if(assigned){ showAssigned(assigned); saveHistory({pickup,dest,pax,status:'assigned to '+assigned.name,time:new Date().toLocaleString('th-TH')}); }
      else{ appendLog('ไม่พบคนขับ — แนะนำขยับตำแหน่งขึ้น/ลง'); toast('ขออภัย: ไม่พบคนขับในบริเวณนี้'); saveHistory({pickup,dest,pax,status:'no driver',time:new Date().toLocaleString('th-TH')}); }
    });

    // show assigned UI
    let etaTimer=null;
    function showAssigned(d){ assignedFooter.style.display='flex'; drvAvatar.textContent=d.name.charAt(0); drvTitle.textContent=`คนขับ: ${d.name}`; drvSub.textContent=`${d.car} • ทะเบียน ${d.plate}`;
      // animate ETA fill (3-10 min convert to percent)
      const etaMin = Math.floor(3 + Math.random()*8); let secs=etaMin*60; etaFill.style.width='0%'; clearInterval(etaTimer);
      const total=secs; etaTimer=setInterval(()=>{ secs -= 5; const pct = Math.max(0,Math.round(((total-secs)/total)*100)); etaFill.style.width = pct+'%'; if(secs<=0){ clearInterval(etaTimer); etaFill.style.width='100%'; appendLog('คนขับมาถึง'); toast('คนขับมาถึงแล้ว'); document.getElementById('ratingArea').innerHTML='ขอบคุณ! โปรดให้คะแนน'; } },5000);

      // contact / cancel
      document.getElementById('contactDriver').onclick = ()=>{ alert(`(Prototype) โทรหา ${d.name} — เบอร์ 0x-xxx-xxxx`); };
      document.getElementById('cancelBtn').onclick = ()=>{ assignedFooter.style.display='none'; appendLog('ผู้โดยสารยกเลิกการเรียก'); toast('ยกเลิกการเรียก'); saveHistory({pickup:document.getElementById('pickup').value,dest:document.getElementById('dest').value,pax:document.getElementById('pax').value,status:'cancelled',time:new Date().toLocaleString('th-TH')}); };
      window.currentAssigned = d;
    }

    // quick actions
    document.getElementById('newCall').addEventListener('click', ()=>{ document.getElementById('pickup').focus(); });
    document.getElementById('quickBtn').addEventListener('click', ()=>{ document.getElementById('pickup').value='หน้าอาคารรัฐ'; document.getElementById('dest').value='ศูนย์ราชการ'; callBtn.click(); });

    // history controls
    document.getElementById('openHistory').addEventListener('click', ()=>{ const h=JSON.parse(localStorage.getItem('gov_history')||'[]'); if(!h.length) return toast('ยังไม่มีประวัติ'); const first=h[0]; alert('ประวัติล่าสุด:\n'+first.pickup+' → '+first.dest+'\n'+first.time+'\n'+first.status); });
    document.getElementById('clearHistory').addEventListener('click', ()=>{ if(confirm('ลบประวัติทั้งหมด?')){ localStorage.removeItem('gov_history'); renderHistory(); toast('ล้างประวัติเรียบร้อย'); } });
    document.getElementById('exportHistory').addEventListener('click', ()=>{ const h=localStorage.getItem('gov_history')||'[]'; const blob=new Blob([h],{type:'application/json'}); const url=URL.createObjectURL(blob); const a=document.createElement('a'); a.href=url; a.download='govtaxi_history.json'; a.click(); URL.revokeObjectURL(url); toast('ดาวน์โหลด JSON ประวัติแล้ว'); });

    // theme toggle
    const toggleTheme=document.getElementById('toggleTheme'); let dark=false;
    toggleTheme.addEventListener('click', ()=>{ dark=!dark; if(dark){ document.documentElement.style.setProperty('--bg','#0b1216'); document.documentElement.style.setProperty('--card','#061016'); document.documentElement.style.setProperty('--muted','#90a8b3'); document.documentElement.style.setProperty('--accent','#06b6d4'); document.body.style.background='linear-gradient(180deg,#061016,#07121a)'; toggleTheme.textContent='☀️ Light'; } else { document.documentElement.style.removeProperty('--bg'); document.documentElement.style.removeProperty('--card'); document.documentElement.style.removeProperty('--muted'); document.documentElement.style.removeProperty('--accent'); document.body.style.background='linear-gradient(180deg,#f7fbfd,var(--bg))'; toggleTheme.textContent='🌙 Dark'; } });

    // init
    appendLog('พร้อมใช้งาน — Modern prototype loaded');
    toast('ระบบพร้อมใช้งาน');
  </script>
</body>
</html>
