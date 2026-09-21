<!doctype html>
<html lang="th">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>สมุดเพื่อน</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Mali:wght@500;700&family=Sarabun:wght@400;500;700&display=swap" rel="stylesheet">
<style>
  :root {
    --paper: #F3F7FD;
    --rule: #CBD9EE;
    --margin: #F2A0B5;
    --ink: #1B2350;
    --ink-soft: #4B5683;
    --card: #FFFFFF;
    --card-edge: #D9E3F3;
    --field: #FFFFFF;
    --accent: #D42E5E;
    --accent-ink: #FFFFFF;
    --marker: #FFE27A;
    --focus: #2B6BE0;
    --danger: #B3261E;
    --mx: 22px;
    box-sizing: border-box;
    padding-top: env(safe-area-inset-top, 0px);
    padding-bottom: env(safe-area-inset-bottom, 0px);
  }
  @media (prefers-color-scheme: dark) {
    :root:not([data-theme="light"]) {
      --paper: #151A33; --rule: #232B4F; --margin: #7A3A55; --ink: #EEF1FF; --ink-soft: #A9B2DC;
      --card: #1E2447; --card-edge: #2E376A; --field: #171C3A; --accent: #FF7096; --accent-ink: #2A0B18;
      --marker: #6B5A12; --focus: #8DB4FF; --danger: #FF8A80;
    }
  }
  :root[data-theme="dark"] {
    --paper: #151A33; --rule: #232B4F; --margin: #7A3A55; --ink: #EEF1FF; --ink-soft: #A9B2DC;
    --card: #1E2447; --card-edge: #2E376A; --field: #171C3A; --accent: #FF7096; --accent-ink: #2A0B18;
    --marker: #6B5A12; --focus: #8DB4FF; --danger: #FF8A80;
  }
  html { scroll-padding-top: env(safe-area-inset-top, 0px); }
  *, *::before, *::after { box-sizing: inherit; }
  @media (min-width: 720px) { :root { --mx: 56px; } }

  body {
    margin: 0;
    font-family: "Sarabun", "Noto Sans Thai", system-ui, sans-serif;
    font-size: 16px;
    line-height: 1.6;
    color: var(--ink);
    background-color: var(--paper);
    background-image:
      linear-gradient(to right, transparent var(--mx), var(--margin) var(--mx), var(--margin) calc(var(--mx) + 2px), transparent calc(var(--mx) + 2px)),
      repeating-linear-gradient(to bottom, transparent 0, transparent 31px, var(--rule) 31px, var(--rule) 32px);
    min-height: 100vh;
  }
  h1, h2, h3, .hand { font-family: "Mali", "Sarabun", system-ui, sans-serif; }
  button, input, select, textarea { font: inherit; color: inherit; }
  [hidden] { display: none !important; }
  :focus-visible { outline: 3px solid var(--focus); outline-offset: 2px; }

  .wrap { max-width: 1200px; margin: 0 auto; padding: 32px 16px 96px calc(var(--mx) + 18px); }

  /* header */
  .title {
    font-size: clamp(2.6rem, 9vw, 4.6rem);
    line-height: 1.25;
    margin: 0;
    font-weight: 700;
    display: inline;
    background-image: linear-gradient(transparent 58%, var(--marker) 58%, var(--marker) 92%, transparent 92%);
    padding: 0 .2em;
    margin-left: -.2em;
  }
  .sub { margin: 14px 0 0; color: var(--ink-soft); max-width: 46ch; }

  /* toolbar */
  .bar {
    position: sticky; top: env(safe-area-inset-top, 0px); z-index: 5;
    display: flex; flex-wrap: wrap; gap: 10px; align-items: center;
    margin: 26px -8px 0; padding: 12px 8px;
    background: color-mix(in srgb, var(--paper) 92%, transparent);
    backdrop-filter: blur(6px);
  }
  .search { flex: 1 1 220px; position: relative; }
  .search input { width: 100%; padding: 10px 14px 10px 40px; }
  .search svg { position: absolute; left: 13px; top: 50%; transform: translateY(-50%); color: var(--ink-soft); pointer-events: none; }
  input[type=text], input[type=search], input[type=date], input[type=tel], select, textarea {
    background: var(--field); border: 1.5px solid var(--card-edge); border-radius: 8px; padding: 9px 12px; min-height: 44px;
  }
  textarea { width: 100%; resize: vertical; min-height: 84px; }
  .btn {
    display: inline-flex; align-items: center; justify-content: center; gap: 8px;
    min-height: 44px; padding: 0 18px; border-radius: 8px; border: 1.5px solid var(--ink); background: transparent;
    cursor: pointer; font-weight: 500;
  }
  .btn:hover { background: color-mix(in srgb, var(--ink) 8%, transparent); }
  .btn.primary { background: var(--accent); border-color: var(--accent); color: var(--accent-ink); font-weight: 700; }
  .btn.primary:hover { filter: brightness(1.07); }
  .btn.danger { border-color: var(--danger); color: var(--danger); }
  .btn[disabled] { opacity: .6; cursor: wait; }

  /* chips */
  .chips { display: flex; flex-wrap: wrap; gap: 8px; margin: 10px 0 4px; }
  .chip {
    border: 1.5px solid var(--card-edge); background: var(--card); border-radius: 999px; padding: 4px 14px; min-height: 36px; cursor: pointer;
  }
  .chip[aria-pressed="true"] { background: var(--ink); color: var(--paper); border-color: var(--ink); }
  .chip small { opacity: .7; margin-left: 4px; }

  /* notices */
  .note {
    margin: 14px 0 0; padding: 10px 14px; border-radius: 8px; background: var(--card); border: 1.5px dashed var(--card-edge);
    display: flex; flex-wrap: wrap; gap: 8px 14px; align-items: center; justify-content: space-between;
  }
  .note p { margin: 0; }
  .bday { margin-top: 18px; }
  .bday h2 { font-size: 1.15rem; margin: 0 0 8px; }
  .bday ul { list-style: none; margin: 0; padding: 0; display: flex; flex-wrap: wrap; gap: 8px; }
  .bday li button {
    display: inline-flex; gap: 8px; align-items: center; background: var(--card); border: 1.5px solid var(--card-edge);
    border-radius: 8px; padding: 6px 12px; cursor: pointer; min-height: 40px;
  }
  .bday b { font-family: "Mali", sans-serif; }

  /* cards */
  .grid { display: grid; gap: 30px 20px; grid-template-columns: repeat(auto-fill, minmax(240px, 1fr)); margin-top: 26px; padding: 0; list-style: none; }
  .card {
    position: relative; display: block; width: 100%; text-align: left; cursor: pointer;
    background: var(--card); border: 1.5px solid var(--card-edge); border-radius: 6px;
    padding: 34px 16px 16px; box-shadow: 0 3px 0 var(--card-edge);
  }
  .card:hover { transform: translateY(-2px); box-shadow: 0 5px 0 var(--card-edge); }
  .tape {
    position: absolute; top: -12px; left: 14px; padding: 2px 14px; font-size: .85rem; color: #1B2350; font-weight: 500;
    transform: rotate(-2deg); max-width: calc(100% - 28px); white-space: nowrap; overflow: hidden; text-overflow: ellipsis;
    box-shadow: 0 1px 0 rgba(0,0,0,.08);
  }
  .card .top { display: flex; gap: 14px; align-items: center; }
  .avatar {
    flex: none; width: 68px; height: 68px; border-radius: 50%; display: grid; place-items: center; overflow: hidden;
    font-family: "Mali", sans-serif; font-weight: 700; font-size: 1.9rem; color: #1B2350; border: 2px solid var(--card-edge);
  }
  .avatar img { width: 100%; height: 100%; object-fit: cover; display: block; }
  .avatar.lg { width: 92px; height: 92px; font-size: 2.6rem; }
  .card .nick { font-family: "Mali", sans-serif; font-weight: 700; font-size: 1.4rem; line-height: 1.3; display: block; overflow-wrap: anywhere; }
  .card .full { color: var(--ink-soft); font-size: .92rem; display: block; overflow-wrap: anywhere; }
  .card .meta { display: block; margin-top: 12px; font-size: .92rem; color: var(--ink-soft); }
  .tags { display: flex; flex-wrap: wrap; gap: 6px; margin-top: 10px; }
  .tag { background: color-mix(in srgb, var(--ink) 9%, transparent); border-radius: 4px; padding: 0 8px; font-size: .84rem; }

  .empty { margin: 40px 0; padding: 28px; text-align: center; background: var(--card); border: 1.5px dashed var(--card-edge); border-radius: 8px; }
  .empty h2 { margin: 0 0 6px; font-size: 1.3rem; }
  .empty p { margin: 0 0 16px; color: var(--ink-soft); }

  /* dialog */
  dialog {
    width: min(600px, calc(100% - 24px)); max-height: 92dvh; padding: 0; border: 1.5px solid var(--ink); border-radius: 10px;
    background: var(--card); color: var(--ink); overflow: auto;
  }
  dialog::backdrop { background: rgba(10, 14, 40, .55); }
  .dlg { padding: 24px 22px 22px; }
  .dlg-head { display: flex; gap: 16px; align-items: center; margin-bottom: 8px; }
  .dlg-head h2 { margin: 0; font-size: 1.7rem; line-height: 1.3; overflow-wrap: anywhere; }
  .dlg-head p { margin: 0; color: var(--ink-soft); overflow-wrap: anywhere; }
  .pill { display: inline-block; margin-top: 6px; padding: 0 12px; border-radius: 4px; color: #1B2350; font-size: .88rem; font-weight: 500; }
  dl { margin: 18px 0 0; display: grid; grid-template-columns: minmax(96px, 30%) 1fr; gap: 10px 14px; }
  dt { color: var(--ink-soft); }
  dd { margin: 0; overflow-wrap: anywhere; white-space: pre-line; }
  dd a { color: var(--focus); }
  .actions { display: flex; flex-wrap: wrap; gap: 10px; margin-top: 22px; justify-content: flex-end; }
  .actions .grow { margin-right: auto; }

  .form { display: grid; grid-template-columns: 1fr 1fr; gap: 14px; }
  .form .full { grid-column: 1 / -1; }
  .form label { display: block; font-weight: 500; margin-bottom: 4px; }
  .form input[type=text], .form input[type=date], .form input[type=tel] { width: 100%; }
  .hint { font-size: .86rem; color: var(--ink-soft); margin: 4px 0 0; }
  .err { color: var(--danger); font-weight: 500; margin: 0; }
  .photo-row { display: flex; gap: 16px; align-items: center; }
  @media (max-width: 520px) { .form { grid-template-columns: 1fr; } dl { grid-template-columns: 1fr; gap: 0; } dt { margin-top: 10px; } }

  .toast {
    position: fixed; left: 50%; bottom: calc(24px + env(safe-area-inset-bottom, 0px)); transform: translateX(-50%);
    background: var(--ink); color: var(--paper); padding: 10px 20px; border-radius: 8px; z-index: 50; font-weight: 500;
  }
  @media (prefers-reduced-motion: no-preference) {
    .card { transition: transform .15s ease, box-shadow .15s ease; }
  }
</style>
</head>
<body>
<div class="wrap" id="app"></div>

<script type="application/json" id="data">{"friends":[
{"id":"f_demo1","sample":true,"nick":"ต้น","full":"ธนพล ใจดี","group":"เพื่อนมหาวิทยาลัย","bday":"1999-10-03","place":"คณะวิศวกรรมศาสตร์","town":"นครราชสีมา","hobbies":"เล่นเกม, ถ่ายรูป, กาแฟ","phone":"","line":"ton.demo","ig":"","met":"เจอกันวันปฐมนิเทศ นั่งติดกันแล้วชวนคุยเรื่องเกมจนสนิท","note":"ชอบขอยืมชาร์จเจอร์ แต่ใจดีมาก","photo":"","created":1}
,{"id":"f_demo2","sample":true,"nick":"แพร","full":"แพรวา สุขสันต์","group":"เพื่อนมัธยม","bday":"2000-01-15","place":"ทำงานที่บริษัทออกแบบ","town":"เชียงใหม่","hobbies":"วาดรูป, ปั่นจักรยาน","phone":"","line":"","ig":"prae.demo","met":"อยู่ห้องเดียวกันตั้งแต่ ม.1","note":"เป็นคนที่โทรหาได้ทุกเวลา","photo":"","created":2}
,{"id":"f_demo3","sample":true,"nick":"ก้อง","full":"ก้องภพ รักเรียน","group":"เพื่อนที่ทำงาน","bday":"","place":"ฝ่ายการตลาด","town":"ขอนแก่น","hobbies":"วิ่ง, ทำอาหาร","phone":"","line":"","ig":"","met":"เข้าทำงานพร้อมกัน","note":"","photo":"","created":3}
]}</script>

<script>
(function () {
  const $ = (s, r = document) => r.querySelector(s);
  const esc = s => String(s ?? '').replace(/[&<>"']/g, c => ({ '&': '&amp;', '<': '&lt;', '>': '&gt;', '"': '&quot;', "'": '&#39;' }[c]));

  let state;
  try { state = JSON.parse($('#data').textContent); } catch (e) { state = { friends: [] }; }
  const KEY = 'friends-book-v1';
  try { const saved = JSON.parse(localStorage.getItem(KEY) || 'null'); if (saved && Array.isArray(saved.friends)) state = saved; } catch (e) {}
  if (!Array.isArray(state.friends)) state.friends = [];

  const ui = { q: '', group: '', sort: 'name', readOnly: false, notice: '' };
  let artifact = null;
  let draftPhoto = '';

  const TAPES = ['#FFB3C7', '#FFE27A', '#A8ECD3', '#B5D3FF', '#D2C2F5', '#FFCFA1'];
  const DEFAULT_GROUP = 'เพื่อนทั่วไป';
  const groupOf = f => (f.group || '').trim() || DEFAULT_GROUP;
  function tapeColor(g) {
    let h = 0;
    for (const ch of g) h = (h * 31 + ch.codePointAt(0)) >>> 0;
    return TAPES[h % TAPES.length];
  }
  function initial(name) {
    const chars = Array.from((name || '?').replace(/^[เแโใไ]+/, ''));
    return (chars[0] || '?').toUpperCase();
  }
  function avatar(f, lg) {
    const bg = tapeColor(groupOf(f));
    return `<span class="avatar${lg ? ' lg' : ''}" style="background:${bg}">${f.photo ? `<img src="${esc(f.photo)}" alt="">` : esc(initial(f.nick))}</span>`;
  }
  function daysUntil(iso) {
    if (!iso) return null;
    const [, m, d] = iso.split('-').map(Number);
    const now = new Date();
    const t0 = new Date(now.getFullYear(), now.getMonth(), now.getDate());
    let n = new Date(now.getFullYear(), m - 1, d);
    if (n < t0) n = new Date(now.getFullYear() + 1, m - 1, d);
    return Math.round((n - t0) / 864e5);
  }
  function fmtBday(iso) {
    if (!iso) return '';
    const [y, m, d] = iso.split('-').map(Number);
    return new Date(y, m - 1, d).toLocaleDateString('th-TH', { day: 'numeric', month: 'long' });
  }
  const tagsOf = f => (f.hobbies || '').split(/[,،、]/).map(s => s.trim()).filter(Boolean);

  /* ---------- shell ---------- */
  function buildShell() {
    $('#app').innerHTML = `
      <header>
        <h1 class="title">สมุดเพื่อน</h1>
        <p class="sub">รวมประวัติของเพื่อนๆ ไว้ในที่เดียว ทั้งชื่อเล่น วันเกิด งานอดิเรก และเรื่องที่อยากจำ</p>
      </header>
      <div class="bar" role="search">
        <div class="search">
          <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" aria-hidden="true"><circle cx="11" cy="11" r="7"/><path d="M20 20l-3.5-3.5"/></svg>
          <input type="search" id="q" placeholder="ค้นหาชื่อ กลุ่ม หรืองานอดิเรก" aria-label="ค้นหาเพื่อน">
        </div>
        <select id="sort" aria-label="เรียงลำดับ">
          <option value="name">เรียงตามชื่อเล่น</option>
          <option value="new">เพิ่มล่าสุด</option>
          <option value="bday">วันเกิดใกล้ถึง</option>
        </select>
        <button class="btn primary" id="add" type="button">+ เพิ่มเพื่อน</button>
        <button class="btn" id="export" type="button">สำรองข้อมูล</button>
        <button class="btn" id="import" type="button">นำเข้า</button>
        <input type="file" id="imp" accept="application/json" hidden>
      </div>
      <div id="chips" class="chips" role="group" aria-label="กรองตามกลุ่ม"></div>
      <div id="notes"></div>
      <div id="bdays"></div>
      <div id="list"></div>
      <dialog id="dlg" aria-labelledby="dlg-title"></dialog>`;

    $('#q').addEventListener('input', e => { ui.q = e.target.value; renderList(); });
    $('#sort').addEventListener('change', e => { ui.sort = e.target.value; renderList(); });
    $('#add').addEventListener('click', () => openForm());
    $('#export').addEventListener('click', exportData);
    $('#import').addEventListener('click', () => $('#imp').click());
    $('#imp').addEventListener('change', importData);
    $('#dlg').addEventListener('click', e => { if (e.target === e.currentTarget) e.currentTarget.close(); });
  }

  /* ---------- lists ---------- */
  function visible() {
    const q = ui.q.trim().toLowerCase();
    let arr = state.friends.filter(f => {
      if (ui.group && groupOf(f) !== ui.group) return false;
      if (!q) return true;
      return [f.nick, f.full, groupOf(f), f.hobbies, f.place, f.town].join(' ').toLowerCase().includes(q);
    });
    if (ui.sort === 'name') arr.sort((a, b) => a.nick.localeCompare(b.nick, 'th'));
    else if (ui.sort === 'new') arr.sort((a, b) => (b.created || 0) - (a.created || 0));
    else arr.sort((a, b) => (daysUntil(a.bday) ?? 9999) - (daysUntil(b.bday) ?? 9999));
    return arr;
  }

  function renderAll() { renderChips(); renderNotes(); renderBdays(); renderList(); applyMode(); }

  function applyMode() { const b = $('#add'); if (b) b.hidden = ui.readOnly; }

  function renderChips() {
    const counts = {};
    state.friends.forEach(f => { const g = groupOf(f); counts[g] = (counts[g] || 0) + 1; });
    const names = Object.keys(counts).sort((a, b) => a.localeCompare(b, 'th'));
    if (ui.group && !counts[ui.group]) ui.group = '';
    const chip = (label, val, n) => `<button type="button" class="chip" data-g="${esc(val)}" aria-pressed="${ui.group === val}">${esc(label)}<small>${n}</small></button>`;
    $('#chips').innerHTML = state.friends.length ? chip('ทั้งหมด', '', state.friends.length) + names.map(n => chip(n, n, counts[n])).join('') : '';
    $('#chips').querySelectorAll('.chip').forEach(b => b.addEventListener('click', () => { ui.group = b.dataset.g; renderChips(); renderList(); }));
  }

  function renderNotes() {
    const hasSample = state.friends.some(f => f.sample);
    let html = '';
    if (ui.notice) html += `<div class="note" role="status"><p>${esc(ui.notice)}</p></div>`;
    if (hasSample && !ui.readOnly) {
      html += `<div class="note"><p>เพื่อนสามคนแรกเป็นข้อมูลตัวอย่าง ลบทิ้งเมื่อพร้อมเริ่มของจริงได้เลย</p><button type="button" class="btn" id="clear-sample">ลบข้อมูลตัวอย่าง</button></div>`;
    }
    $('#notes').innerHTML = html;
    const cs = $('#clear-sample');
    if (cs) cs.addEventListener('click', async () => {
      cs.disabled = true;
      await commit({ ...state, friends: state.friends.filter(f => !f.sample) }, 'ลบข้อมูลตัวอย่างแล้ว');
      cs.disabled = false;
    });
  }

  function renderBdays() {
    const soon = state.friends
      .map(f => ({ f, d: daysUntil(f.bday) }))
      .filter(x => x.d !== null && x.d <= 30)
      .sort((a, b) => a.d - b.d);
    if (!soon.length) { $('#bdays').innerHTML = ''; return; }
    $('#bdays').innerHTML = `<section class="bday" aria-labelledby="bd-h"><h2 id="bd-h">วันเกิดเพื่อนที่กำลังจะมาถึง</h2><ul>${soon.map(({ f, d }) =>
      `<li><button type="button" data-id="${esc(f.id)}"><b>${esc(f.nick)}</b><span>${d === 0 ? 'วันนี้!' : d === 1 ? 'พรุ่งนี้' : 'อีก ' + d + ' วัน'} (${esc(fmtBday(f.bday))})</span></button></li>`).join('')}</ul></section>`;
    $('#bdays').querySelectorAll('button').forEach(b => b.addEventListener('click', () => openDetail(b.dataset.id)));
  }

  function renderList() {
    const arr = visible();
    const box = $('#list');
    if (!state.friends.length) {
      box.innerHTML = `<div class="empty"><h2>สมุดเล่มนี้ยังว่างอยู่</h2><p>เริ่มจากเพื่อนคนแรกที่นึกออกได้เลย</p>${ui.readOnly ? '' : '<button class="btn primary" type="button" id="empty-add">+ เพิ่มเพื่อน</button>'}</div>`;
      const b = $('#empty-add'); if (b) b.addEventListener('click', () => openForm());
      return;
    }
    if (!arr.length) {
      box.innerHTML = `<div class="empty"><h2>ไม่พบเพื่อนที่ตรงกัน</h2><p>ลองเปลี่ยนคำค้นหา หรือเลือกกลุ่ม “ทั้งหมด”</p></div>`;
      return;
    }
    box.innerHTML = `<ul class="grid">${arr.map(f => {
      const g = groupOf(f);
      const tags = tagsOf(f).slice(0, 3);
      return `<li><button type="button" class="card" data-id="${esc(f.id)}">
        <span class="tape" style="background:${tapeColor(g)}">${esc(g)}</span>
        <span class="top">${avatar(f)}<span><span class="nick">${esc(f.nick)}</span>${f.full ? `<span class="full">${esc(f.full)}</span>` : ''}</span></span>
        ${f.place ? `<span class="meta">${esc(f.place)}</span>` : ''}
        ${f.bday ? `<span class="meta">วันเกิด ${esc(fmtBday(f.bday))}</span>` : ''}
        ${tags.length ? `<span class="tags">${tags.map(t => `<span class="tag">${esc(t)}</span>`).join('')}</span>` : ''}
      </button></li>`;
    }).join('')}</ul>`;
    box.querySelectorAll('.card').forEach(b => b.addEventListener('click', () => openDetail(b.dataset.id)));
  }

  /* ---------- detail ---------- */
  function row(label, val) { return val ? `<dt>${label}</dt><dd>${val}</dd>` : ''; }

  function openDetail(id) {
    const f = state.friends.find(x => x.id === id);
    if (!f) return;
    const g = groupOf(f);
    const ig = (f.ig || '').replace(/^@/, '').replace(/[^A-Za-z0-9._]/g, '');
    const tel = (f.phone || '').replace(/[^0-9+]/g, '');
    const dlg = $('#dlg');
    dlg.innerHTML = `<div class="dlg">
      <div class="dlg-head">${avatar(f, true)}<div>
        <h2 id="dlg-title">${esc(f.nick)}</h2>
        ${f.full ? `<p>${esc(f.full)}</p>` : ''}
        <span class="pill" style="background:${tapeColor(g)}">${esc(g)}</span>
      </div></div>
      <dl>
        ${row('วันเกิด', esc(fmtBday(f.bday)))}
        ${row('เรียน/ทำงานที่', esc(f.place))}
        ${row('บ้านเกิด', esc(f.town))}
        ${row('งานอดิเรก', esc(tagsOf(f).join(', ')))}
        ${row('เบอร์โทร', tel ? `<a href="tel:${esc(tel)}">${esc(f.phone)}</a>` : '')}
        ${row('LINE', esc(f.line))}
        ${row('Instagram', ig ? `<a href="https://instagram.com/${esc(ig)}" target="_blank" rel="noopener noreferrer">@${esc(ig)}</a>` : '')}
        ${row('รู้จักกันตอนไหน', esc(f.met))}
        ${row('เรื่องที่อยากจำ', esc(f.note))}
      </dl>
      <div class="actions">
        ${ui.readOnly ? '' : '<button class="btn danger grow" type="button" id="del">ลบ</button><button class="btn" type="button" id="edit">แก้ไข</button>'}
        <button class="btn primary" type="button" id="close">ปิด</button>
      </div></div>`;
    $('#close', dlg).addEventListener('click', () => dlg.close());
    const edit = $('#edit', dlg);
    if (edit) edit.addEventListener('click', () => openForm(id));
    const del = $('#del', dlg);
    if (del) del.addEventListener('click', () => {
      if (del.dataset.armed !== '1') { del.dataset.armed = '1'; del.textContent = 'ยืนยันลบ ' + f.nick; return; }
      del.disabled = true;
      commit({ ...state, friends: state.friends.filter(x => x.id !== id) }, 'ลบแล้ว').then(ok => { if (!ok) del.disabled = false; });
    });
    if (!dlg.open) dlg.showModal();
  }

  /* ---------- form ---------- */
  function openForm(id) {
    if (ui.readOnly) return;
    const f = id ? state.friends.find(x => x.id === id) : null;
    const v = k => esc(f ? f[k] : '');
    draftPhoto = f ? f.photo || '' : '';
    const groups = [...new Set(['เพื่อนมัธยม', 'เพื่อนมหาวิทยาลัย', 'เพื่อนที่ทำงาน', 'เพื่อนบ้าน', ...state.friends.map(groupOf)])];
    const dlg = $('#dlg');
    dlg.innerHTML = `<form class="dlg" id="form" novalidate>
      <h2 id="dlg-title" style="margin:0 0 16px;font-size:1.5rem">${f ? 'แก้ไขข้อมูลเพื่อน' : 'เพิ่มเพื่อนใหม่'}</h2>
      <div class="form">
        <div class="full photo-row">
          <span id="ph-prev"></span>
          <div>
            <label for="photo" style="margin:0">รูปโปรไฟล์ (ไม่บังคับ)</label>
            <input type="file" id="photo" accept="image/*">
            <button type="button" class="btn" id="ph-clear" style="min-height:36px;margin-top:6px" hidden>เอารูปออก</button>
          </div>
        </div>
        <div><label for="nick">ชื่อเล่น *</label><input type="text" id="nick" name="nick" value="${v('nick')}" maxlength="40" autocomplete="off" required></div>
        <div><label for="full">ชื่อ-นามสกุล</label><input type="text" id="full" name="full" value="${v('full')}" maxlength="80" autocomplete="off"></div>
        <div><label for="group">กลุ่มเพื่อน</label><input type="text" id="group" name="group" list="glist" value="${v('group')}" maxlength="40" placeholder="เช่น เพื่อนมัธยม" autocomplete="off"><datalist id="glist">${groups.map(g => `<option value="${esc(g)}">`).join('')}</datalist></div>
        <div><label for="bday">วันเกิด</label><input type="date" id="bday" name="bday" value="${v('bday')}"></div>
        <div><label for="place">เรียน/ทำงานที่</label><input type="text" id="place" name="place" value="${v('place')}" maxlength="80" autocomplete="off"></div>
        <div><label for="town">บ้านเกิด</label><input type="text" id="town" name="town" value="${v('town')}" maxlength="60" autocomplete="off"></div>
        <div class="full"><label for="hobbies">งานอดิเรก</label><input type="text" id="hobbies" name="hobbies" value="${v('hobbies')}" maxlength="120" placeholder="คั่นด้วยเครื่องหมายจุลภาค เช่น เล่นเกม, วาดรูป" autocomplete="off"></div>
        <div><label for="phone">เบอร์โทร</label><input type="tel" id="phone" name="phone" value="${v('phone')}" maxlength="20" autocomplete="off"></div>
        <div><label for="line">LINE ID</label><input type="text" id="line" name="line" value="${v('line')}" maxlength="40" autocomplete="off"></div>
        <div class="full"><label for="ig">Instagram</label><input type="text" id="ig" name="ig" value="${v('ig')}" maxlength="40" placeholder="ชื่อผู้ใช้ ไม่ต้องใส่ลิงก์" autocomplete="off">
          <p class="hint">เบอร์โทร LINE และ Instagram จะมองเห็นได้ทุกคนที่มีลิงก์หน้านี้ ใส่เท่าที่เพื่อนยินยอมเท่านั้น</p></div>
        <div class="full"><label for="met">รู้จักกันตอนไหน</label><textarea id="met" name="met" maxlength="400">${v('met')}</textarea></div>
        <div class="full"><label for="note">เรื่องที่อยากจำเกี่ยวกับเพื่อนคนนี้</label><textarea id="note" name="note" maxlength="600">${v('note')}</textarea></div>
        <p class="err full" id="err" role="alert" hidden></p>
      </div>
      <div class="actions"><button class="btn" type="button" id="cancel">ยกเลิก</button><button class="btn primary" type="submit" id="save">บันทึก</button></div>
    </form>`;

    const prev = () => {
      $('#ph-prev', dlg).innerHTML = avatar({ nick: $('#nick', dlg).value || (f && f.nick) || '?', group: $('#group', dlg).value, photo: draftPhoto }, true);
      $('#ph-clear', dlg).hidden = !draftPhoto;
    };
    prev();
    $('#nick', dlg).addEventListener('input', prev);
    $('#group', dlg).addEventListener('input', prev);
    $('#ph-clear', dlg).addEventListener('click', () => { draftPhoto = ''; $('#photo', dlg).value = ''; prev(); });
    $('#photo', dlg).addEventListener('change', async e => {
      const file = e.target.files[0]; if (!file) return;
      try { draftPhoto = await shrink(file); prev(); }
      catch (err) { showErr('อ่านรูปนี้ไม่ได้ ลองเลือกไฟล์ JPG หรือ PNG'); }
    });
    $('#cancel', dlg).addEventListener('click', () => (f ? openDetail(f.id) : dlg.close()));
    const showErr = m => { const el = $('#err', dlg); el.textContent = m; el.hidden = !m; };

    $('#form', dlg).addEventListener('submit', async e => {
      e.preventDefault();
      const d = Object.fromEntries(new FormData(e.currentTarget));
      const nick = (d.nick || '').trim();
      if (!nick) { showErr('กรอกชื่อเล่นก่อนบันทึก'); $('#nick', dlg).focus(); return; }
      const rec = {
        id: f ? f.id : 'f_' + Date.now().toString(36) + Math.random().toString(36).slice(2, 6),
        nick, full: (d.full || '').trim(), group: (d.group || '').trim(), bday: d.bday || '',
        place: (d.place || '').trim(), town: (d.town || '').trim(), hobbies: (d.hobbies || '').trim(),
        phone: (d.phone || '').trim(), line: (d.line || '').trim(), ig: (d.ig || '').trim(),
        met: (d.met || '').trim(), note: (d.note || '').trim(), photo: draftPhoto,
        created: f ? f.created : Date.now()
      };
      const friends = f ? state.friends.map(x => (x.id === f.id ? rec : x)) : [...state.friends, rec];
      const btn = $('#save', dlg); btn.disabled = true; btn.textContent = 'กำลังบันทึก…';
      const ok = await commit({ ...state, friends }, f ? 'บันทึกการแก้ไขแล้ว' : 'เพิ่มเพื่อนแล้ว');
      if (!ok) { btn.disabled = false; btn.textContent = 'บันทึก'; if (ui.readOnly) dlg.close(); else showErr('บันทึกไม่สำเร็จ ลองอีกครั้ง'); }
    });
    if (!dlg.open) dlg.showModal();
    setTimeout(() => $('#nick', dlg) && $('#nick', dlg).focus(), 0);
  }

  function shrink(file) {
    return new Promise((res, rej) => {
      const fr = new FileReader();
      fr.onerror = rej;
      fr.onload = () => {
        const img = new Image();
        img.onerror = rej;
        img.onload = () => {
          const S = 240, c = document.createElement('canvas'); c.width = c.height = S;
          const m = Math.min(img.width, img.height), sx = (img.width - m) / 2, sy = (img.height - m) / 2;
          c.getContext('2d').drawImage(img, sx, sy, m, m, 0, 0, S, S);
          res(c.toDataURL('image/jpeg', 0.75));
        };
        img.src = fr.result;
      };
      fr.readAsDataURL(file);
    });
  }

  /* ---------- saving (in this browser + JSON backup) ---------- */
  async function commit(next, flash) {
    state = next;
    try { localStorage.setItem(KEY, JSON.stringify(state)); }
    catch (e) { alert('บันทึกในเบราว์เซอร์ไม่ได้ ลองกด "สำรองข้อมูล" เก็บไว้เป็นไฟล์'); }
    const dlg = $('#dlg'); if (dlg.open) dlg.close();
    renderAll();
    toast(flash);
    return true;
  }

  function exportData() {
    const blob = new Blob([JSON.stringify(state, null, 2)], { type: 'application/json' });
    const a = document.createElement('a');
    a.href = URL.createObjectURL(blob); a.download = 'friends-book-backup.json';
    document.body.appendChild(a); a.click(); a.remove();
    setTimeout(() => URL.revokeObjectURL(a.href), 1000);
  }

  function importData(e) {
    const file = e.target.files[0]; e.target.value = '';
    if (!file) return;
    const fr = new FileReader();
    fr.onload = () => {
      try {
        const d = JSON.parse(fr.result);
        if (!d || !Array.isArray(d.friends)) throw new Error('bad');
        const str = v => (typeof v === 'string' ? v : '');
        const friends = d.friends.filter(f => f && str(f.nick).trim()).map((f, i) => ({
          id: str(f.id) || 'f_' + Date.now().toString(36) + i, sample: !!f.sample,
          nick: str(f.nick), full: str(f.full), group: str(f.group), bday: str(f.bday), place: str(f.place), town: str(f.town),
          hobbies: str(f.hobbies), phone: str(f.phone), line: str(f.line), ig: str(f.ig), met: str(f.met), note: str(f.note),
          photo: str(f.photo).startsWith('data:image/') ? f.photo : '', created: Number(f.created) || Date.now()
        }));
        if (confirm('นำเข้าเพื่อน ' + friends.length + ' คน? ข้อมูลปัจจุบันจะถูกแทนที่')) commit({ friends }, 'นำเข้าแล้ว');
      } catch (err) { alert('ไฟล์นี้ไม่ใช่ไฟล์สำรองของสมุดเพื่อน'); }
    };
    fr.readAsText(file);
  }

  function setReadOnly() {}

  function toast(msg) {
    const t = document.createElement('div'); t.className = 'toast'; t.setAttribute('role', 'status'); t.textContent = msg;
    document.body.appendChild(t); setTimeout(() => t.remove(), 2600);
  }

  /* ---------- start ---------- */
  buildShell();
  renderAll();
  try { const m = sessionStorage.getItem('flash'); if (m) { sessionStorage.removeItem('flash'); toast(m); } } catch (e) {}

})();
</script>
</body>
</html>
