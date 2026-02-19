
<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>درس ۱۲ فارسی ششم – دوستی (ارسال نتیجه برای معلم در شاد)</title>
<link href="https://fonts.googleapis.com/css2?family=Vazirmatn:wght@300;400;500;600;700;900&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #0F1B2D;
    --surface: #162235;
    --border: rgba(255,213,120,0.18);
    --gold: #FFD578;
    --gold2: #E8B84B;
    --green: #4ADE80;
    --red: #F87171;
    --blue: #60A5FA;
    --purple: #C084FC;
    --text: #EAE4D4;
    --muted: rgba(234,228,212,0.45);
  }

  *, *::before, *::after { margin:0; padding:0; box-sizing:border-box; }

  body {
    font-family: 'Vazirmatn', sans-serif;
    background: var(--bg);
    color: var(--text);
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* Stars bg */
  body::before {
    content:'';
    position:fixed;
    inset:0;
    background:
      radial-gradient(ellipse at 15% 30%, rgba(96,165,250,0.06) 0%, transparent 60%),
      radial-gradient(ellipse at 85% 70%, rgba(192,132,252,0.07) 0%, transparent 60%),
      url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='400' height='400'%3E%3Ccircle cx='50' cy='80' r='1' fill='%23FFD578' opacity='.3'/%3E%3Ccircle cx='150' cy='200' r='1.2' fill='%23FFD578' opacity='.25'/%3E%3Ccircle cx='300' cy='50' r='0.8' fill='white' opacity='.2'/%3E%3Ccircle cx='350' cy='300' r='1' fill='white' opacity='.15'/%3E%3Ccircle cx='80' cy='350' r='1.3' fill='%23FFD578' opacity='.2'/%3E%3Ccircle cx='250' cy='150' r='0.9' fill='white' opacity='.18'/%3E%3C/svg%3E");
    pointer-events:none;
    z-index:0;
  }

  .wrap {
    position:relative; z-index:1;
    max-width:860px;
    margin:0 auto;
    padding:18px 16px 60px;
  }

  /* ── HEADER ── */
  header {
    text-align:center;
    padding:36px 0 28px;
  }
  .badge {
    display:inline-block;
    background:rgba(255,213,120,0.12);
    border:1px solid rgba(255,213,120,0.3);
    color:var(--gold);
    font-size:.75rem;
    font-weight:600;
    letter-spacing:3px;
    padding:5px 18px;
    border-radius:30px;
    margin-bottom:14px;
  }
  header h1 {
    font-size:clamp(1.9rem,5vw,3rem);
    font-weight:900;
    background:linear-gradient(140deg,#FFE08A,var(--gold),#C28A00);
    -webkit-background-clip:text; -webkit-text-fill-color:transparent; background-clip:text;
    line-height:1.2;
    margin-bottom:6px;
  }
  header .subtitle { color:var(--muted); font-size:.85rem; }

  /* ── SCOREBAR ── */
  .scorebar {
    display:flex; justify-content:space-between; align-items:center;
    background:rgba(255,213,120,0.06);
    border:1px solid var(--border);
    border-radius:16px;
    padding:12px 22px;
    margin-bottom:22px;
    gap:10px;
  }
  .si { text-align:center; }
  .si-label { font-size:.65rem; color:var(--gold); letter-spacing:1px; opacity:.7; }
  .si-val { font-size:1.5rem; font-weight:900; color:var(--gold); }

  /* ── SECTIONS ── */
  .sec { display:none; animation:fadeUp .4s ease; }
  .sec.active { display:block; }
  @keyframes fadeUp {
    from{opacity:0;transform:translateY(18px)}
    to{opacity:1;transform:translateY(0)}
  }

  /* ── MENU ── */
  .menu-grid {
    display:grid;
    grid-template-columns:1fr 1fr;
    gap:14px;
  }
  .mcard {
    background:linear-gradient(145deg,rgba(22,34,53,0.9),rgba(15,27,45,0.9));
    border:1px solid var(--border);
    border-radius:20px;
    padding:26px 18px;
    cursor:pointer;
    text-align:center;
    transition:all .3s;
    position:relative; overflow:hidden;
  }
  .mcard::after {
    content:'';position:absolute;inset:0;
    background:linear-gradient(135deg,rgba(255,213,120,0.08),transparent);
    opacity:0;transition:opacity .3s;
  }
  .mcard:hover::after { opacity:1; }
  .mcard:hover { border-color:var(--gold2); transform:translateY(-4px); box-shadow:0 12px 36px rgba(255,213,120,0.12); }
  .mcard .ico { font-size:2.6rem; margin-bottom:10px; }
  .mcard h3 { font-size:1rem; font-weight:700; color:var(--gold); margin-bottom:5px; }
  .mcard p { font-size:.76rem; color:var(--muted); line-height:1.6; }

  /* ── COMMON ── */
  .back-btn {
    background:transparent;
    border:1px solid var(--border);
    color:var(--gold2);
    padding:7px 18px;
    border-radius:30px;
    cursor:pointer;
    font-family:'Vazirmatn',sans-serif;
    font-size:.82rem;
    margin-bottom:18px;
    transition:all .2s;
  }
  .back-btn:hover { background:rgba(255,213,120,0.08); }

  .sec-title {
    font-size:1.2rem; font-weight:700;
    color:var(--gold);
    margin-bottom:18px;
    padding-bottom:10px;
    border-bottom:1px solid var(--border);
    display:flex; align-items:center; gap:8px;
  }

  /* ── QUIZ ── */
  .prog-bar { display:flex; gap:5px; margin-bottom:20px; }
  .pdot { flex:1; height:4px; border-radius:2px; background:rgba(255,213,120,0.1); transition:background .3s; }
  .pdot.done { background:var(--gold2); }
  .pdot.cur  { background:var(--gold); animation:blink 1.2s ease infinite; }
  @keyframes blink { 0%,100%{opacity:1}50%{opacity:.4} }

  .qcard {
    background:rgba(22,34,53,0.9);
    border:1px solid var(--border);
    border-radius:18px;
    padding:24px;
    margin-bottom:14px;
  }
  .qnum { font-size:.7rem; color:var(--gold); letter-spacing:2px; margin-bottom:10px; }
  .qtext { font-size:1.08rem; font-weight:600; line-height:1.7; }

  .opts { display:grid; gap:9px; margin-top:18px; }
  .obtn {
    background:rgba(234,228,212,0.03);
    border:1px solid rgba(255,213,120,0.18);
    color:var(--text);
    padding:13px 18px;
    border-radius:11px;
    cursor:pointer;
    font-family:'Vazirmatn',sans-serif;
    font-size:.93rem;
    text-align:right;
    transition:all .22s;
    line-height:1.5;
  }
  .obtn:not(.locked):hover { background:rgba(255,213,120,0.08); border-color:var(--gold2); }
  .obtn.correct { background:rgba(74,222,128,0.12); border-color:var(--green); color:#86EFAC; }
  .obtn.wrong   { background:rgba(248,113,113,0.12); border-color:var(--red); color:#FCA5A5; }

  .fb {
    padding:13px 18px; border-radius:11px;
    font-size:.87rem; line-height:1.65;
    margin-top:10px; display:none;
  }
  .fb.ok  { display:block; background:rgba(74,222,128,0.08); border:1px solid rgba(74,222,128,0.25); color:#86EFAC; }
  .fb.err { display:block; background:rgba(248,113,113,0.08); border:1px solid rgba(248,113,113,0.25); color:#FCA5A5; }

  .nbtn {
    display:none; width:100%;
    background:linear-gradient(135deg,var(--gold2),#9A6800);
    border:none; color:#0F1B2D;
    padding:13px; border-radius:11px;
    cursor:pointer; font-family:'Vazirmatn',sans-serif;
    font-size:.97rem; font-weight:700;
    margin-top:10px; transition:opacity .2s;
  }
  .nbtn:hover { opacity:.88; }

  /* ── VOCAB MATCH ── */
  .vocab-grid { display:grid; grid-template-columns:1fr 1fr; gap:11px; }
  .vcol-title { text-align:center; color:var(--gold); font-size:.75rem; font-weight:600; letter-spacing:1px; margin-bottom:8px; }
  .vitem {
    background:rgba(22,34,53,0.9);
    border:2px solid rgba(255,213,120,0.18);
    border-radius:11px;
    padding:11px 14px;
    cursor:pointer;
    font-size:.88rem;
    text-align:center;
    transition:all .22s;
    min-height:50px;
    display:flex; align-items:center; justify-content:center;
    line-height:1.4;
  }
  .vitem:hover { border-color:var(--gold2); background:rgba(255,213,120,0.07); }
  .vitem.sel   { border-color:var(--gold); background:rgba(255,213,120,0.14); color:var(--gold); }
  .vitem.mat   { border-color:var(--green); background:rgba(74,222,128,0.09); color:#86EFAC; cursor:default; }
  .vitem.shake { border-color:var(--red); background:rgba(248,113,113,0.1); animation:shake .35s ease; }
  @keyframes shake { 0%,100%{transform:translateX(0)}25%{transform:translateX(-6px)}75%{transform:translateX(6px)} }

  .match-info { text-align:center; color:var(--gold2); font-size:.88rem; margin:14px 0; min-height:22px; }

  /* ── FILL BLANKS ── */
  .fcard {
    background:rgba(22,34,53,0.9);
    border:1px solid var(--border);
    border-radius:16px;
    padding:22px;
    margin-bottom:13px;
  }
  .fsentence { font-size:1.05rem; font-weight:500; line-height:2.5; }
  .finput {
    display:inline-block;
    border:none; border-bottom:2px solid var(--gold2);
    background:transparent;
    color:var(--gold);
    font-family:'Vazirmatn',sans-serif;
    font-size:.98rem;
    width:120px; text-align:center;
    outline:none; padding:2px 6px;
    margin:0 4px;
    transition:border-color .2s;
  }
  .finput:focus { border-color:var(--gold); }
  .finput.ok  { border-color:var(--green); color:#86EFAC; }
  .finput.err { border-color:var(--red);   color:#FCA5A5; }

  /* ── TRUE/FALSE ── */
  .tf-card {
    background:rgba(22,34,53,0.9);
    border:1px solid var(--border);
    border-radius:16px;
    padding:20px 22px;
    margin-bottom:12px;
    display:flex; gap:14px; align-items:flex-start;
  }
  .tf-text { flex:1; font-size:.95rem; line-height:1.7; }
  .tf-btns { display:flex; gap:8px; flex-shrink:0; }
  .tf-btn {
    padding:8px 16px;
    border-radius:10px;
    border:1px solid;
    font-family:'Vazirmatn',sans-serif;
    font-size:.85rem;
    font-weight:600;
    cursor:pointer;
    transition:all .22s;
  }
  .tf-true  { border-color:rgba(74,222,128,0.35); background:rgba(74,222,128,0.07); color:#86EFAC; }
  .tf-false { border-color:rgba(248,113,113,0.35); background:rgba(248,113,113,0.07); color:#FCA5A5; }
  .tf-true:hover  { background:rgba(74,222,128,0.18); }
  .tf-false:hover { background:rgba(248,113,113,0.18); }
  .tf-btn.correct { background:rgba(74,222,128,0.25); border-color:var(--green); }
  .tf-btn.wrong   { background:rgba(248,113,113,0.25); border-color:var(--red); }
  .tf-btn:disabled { cursor:default; }
  .tf-icon { font-size:1.5rem; flex-shrink:0; margin-top:2px; }

  /* ── RESULT ── */
  .result-box { text-align:center; padding:40px 20px; }
  .rbig { font-size:5rem; margin-bottom:14px; }
  .result-box h2 {
    font-size:2rem; font-weight:900;
    background:linear-gradient(135deg,var(--gold),var(--gold2));
    -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;
    margin-bottom:8px;
  }
  .result-box p { color:var(--muted); font-size:1rem; margin-bottom:28px; }
  .ragain {
    background:linear-gradient(135deg,var(--gold2),#8B6000);
    border:none; color:#0F1B2D;
    padding:13px 38px; border-radius:30px;
    cursor:pointer; font-family:'Vazirmatn',sans-serif;
    font-size:.97rem; font-weight:700;
    transition:transform .2s;
  }
  .ragain:hover { transform:scale(1.05); }

  .check-btn {
    background:linear-gradient(135deg,#1E3A5F,#162235);
    border:1px solid rgba(96,165,250,0.35);
    color:var(--blue);
    padding:11px 28px; border-radius:11px;
    cursor:pointer; font-family:'Vazirmatn',sans-serif;
    font-size:.92rem; font-weight:600;
    margin-top:14px; transition:all .2s;
  }
  .check-btn:hover { background:rgba(96,165,250,0.1); }

  .mono {
    background:rgba(255,213,120,0.04);
    border:1px dashed rgba(255,213,120,0.25);
    border-radius:12px;
    padding:12px 14px;
    white-space:pre-wrap;
    line-height:1.9;
    font-size:.92rem;
    color:var(--text);
  }

  @media(max-width:560px){
    .menu-grid,.vocab-grid{ grid-template-columns:1fr; }
    .tf-card { flex-direction:column; }
  }
</style>
</head>
<body>
<div class="wrap">

  <header>
    <div class="badge">فارسی · پایه ششم · درس ۱۲</div>
    <h1>🤝 دوستی</h1>
    <p class="subtitle">برگرفته از قابوس‌نامه · نوشتهٔ عنصرالمعالی</p>
  </header>

  <!-- Score bar -->
  <div class="scorebar">
    <div class="si"><div class="si-label">امتیاز</div><div class="si-val" id="totalScore">۰</div></div>
    <div class="si"><div class="si-label">بازی</div><div class="si-val" id="curGame">—</div></div>
    <div class="si"><div class="si-label">ستاره</div><div class="si-val" id="stars">☆</div></div>
  </div>

  <!-- ═══ STUDENT INFO (اول بازی) ═══ -->
  <div class="sec active" id="sec-student" style="margin-bottom:14px;">
    <div class="qcard" style="margin-bottom:0;">
      <div class="qtext" style="margin-bottom:14px;">👤 اطلاعات دانش‌آموز</div>

      <div style="display:grid;gap:10px;">
        <input id="stuName" class="obtn" style="text-align:right" placeholder="نام و نام خانوادگی" />
        <input id="stuClass" class="obtn" style="text-align:right" placeholder="کلاس (مثلاً ۶/۲)" />
        <button class="nbtn" style="display:block" onclick="saveStudent()">شروع بازی ▶</button>
      </div>

      <div id="stuWarn" class="fb err" style="display:none;margin-top:10px;">لطفاً نام و کلاس را وارد کن.</div>
      <div style="margin-top:10px;color:var(--muted);font-size:.78rem;line-height:1.7;">
        بعد از بازی، نتیجه را با دکمه «کپی نتیجه» بردار و در شاد برای معلم ارسال کن.
      </div>
    </div>
  </div>

  <!-- ═══ MENU ═══ -->
  <div class="sec" id="sec-menu">
    <div class="menu-grid">
      <div class="mcard" onclick="startQuiz()">
        <div class="ico">❓</div>
        <h3>آزمون درک و دریافت</h3>
        <p>۱۰ سوال از محتوای درس دوستی</p>
      </div>
      <div class="mcard" onclick="startVocab()">
        <div class="ico">📚</div>
        <h3>معنی واژگان</h3>
        <p>کلمات مهم درس را با معنی جور کن</p>
      </div>
      <div class="mcard" onclick="startFill()">
        <div class="ico">✏️</div>
        <h3>جاهای خالی</h3>
        <p>جمله‌های ناقص را کامل کن</p>
      </div>
      <div class="mcard" onclick="startTF()">
        <div class="ico">✔️</div>
        <h3>درست یا نادرست</h3>
        <p>گزاره‌ها را بررسی کن</p>
      </div>

      <div class="mcard" onclick="openFinal()">
        <div class="ico">📌</div>
        <h3>نتیجه نهایی</h3>
        <p>کپی نتیجه برای ارسال در شاد</p>
      </div>
      <div class="mcard" onclick="resetAll()">
        <div class="ico">🔄</div>
        <h3>شروع دوباره</h3>
        <p>امتیاز و نتیجه‌ها صفر می‌شود</p>
      </div>
    </div>
  </div>

  <!-- ═══ QUIZ ═══ -->
  <div class="sec" id="sec-quiz">
    <button class="back-btn" onclick="home()">→ بازگشت</button>
    <div class="sec-title">❓ آزمون درک و دریافت</div>
    <div class="prog-bar" id="qprog"></div>
    <div id="qbody"></div>
  </div>

  <!-- ═══ VOCAB ═══ -->
  <div class="sec" id="sec-vocab">
    <button class="back-btn" onclick="home()">→ بازگشت</button>
    <div class="sec-title">📚 معنی واژگان</div>
    <div class="match-info" id="vocabInfo">روی یک واژه کلیک کن، سپس معنی آن را انتخاب کن</div>
    <div class="vocab-grid">
      <div>
        <div class="vcol-title">📝 معنی</div>
        <div id="vdesc" style="display:grid;gap:9px;"></div>
      </div>
      <div>
        <div class="vcol-title">🔤 واژه</div>
        <div id="vword" style="display:grid;gap:9px;"></div>
      </div>
    </div>
    <div style="text-align:center;margin-top:18px;">
      <button class="check-btn" onclick="startVocab()">🔄 دوباره</button>
    </div>
  </div>

  <!-- ═══ FILL ═══ -->
  <div class="sec" id="sec-fill">
    <button class="back-btn" onclick="home()">→ بازگشت</button>
    <div class="sec-title">✏️ جاهای خالی را پر کن</div>
    <div id="fillbody"></div>
    <button class="check-btn" onclick="checkFill()">✅ بررسی</button>
    <div id="fillFB" style="margin-top:12px;"></div>
  </div>

  <!-- ═══ TRUE/FALSE ═══ -->
  <div class="sec" id="sec-tf">
    <button class="back-btn" onclick="home()">→ بازگشت</button>
    <div class="sec-title">✔️ درست یا نادرست</div>
    <div id="tfbody"></div>
    <div id="tfScore" style="text-align:center;margin-top:16px;color:var(--gold);font-size:.9rem;min-height:22px;"></div>
  </div>

  <!-- ═══ FINAL RESULT ═══ -->
  <div class="sec" id="sec-final">
    <button class="back-btn" onclick="home()">→ بازگشت</button>
    <div class="sec-title">📌 نتیجه نهایی</div>

    <div class="qcard">
      <div class="qtext" style="margin-bottom:10px;">متن نتیجه را کپی کن و در شاد برای معلم ارسال کن:</div>
      <div class="mono" id="finalText"></div>

      <button class="nbtn" style="display:block;margin-top:12px" onclick="copyResult()">📋 کپی نتیجه برای ارسال در شاد</button>
      <button class="check-btn" onclick="resetAll()">🔄 شروع دوباره</button>

      <div id="copyOk" class="fb ok" style="display:none;margin-top:12px;">✅ کپی شد! برو شاد و برای معلم ارسال کن.</div>
    </div>
  </div>

</div><!-- /wrap -->

<script>
/* ========= Helpers ========= */
const fa = n => String(n).replace(/\d/g, d => '۰۱۲۳۴۵۶۷۸۹'[d]);

// نرمال‌سازی فارسی برای مقایسه جواب‌ها (فاصله/نیم‌فاصله/ي/ی/ك/ک/اعراب/علائم)
function normalizeFa(str){
  return String(str ?? '')
    .trim()
    .replace(/[يى]/g, 'ی')
    .replace(/ك/g, 'ک')
    .replace(/ۀ/g, 'ه')
    .replace(/ة/g, 'ه')
    .replace(/[ًٌٍَُِّْٔ]/g, '')   // اعراب و علامت‌ها
    .replace(/[“”"']/g, '')
    .replace(/[،,:؛;.!?؟]/g, '')
    .replace(/\u200c/g, ' ')      // نیم‌فاصله → فاصله
    .replace(/\s+/g, ' ')         // فاصله‌های اضافه
    .toLowerCase();
}

/* ========= Global State ========= */
let score = 0;

let student = { name: '', cls: '' };

let quizStats = { correct: 0, total: 0 };
let vocabStats = { matched: 0, total: 0 };
let fillStats  = { correct: 0, total: 0 };
let tfStats    = { correct: 0, total: 0 };

function upScore(){
  document.getElementById('totalScore').textContent = fa(score);
  document.getElementById('stars').textContent =
    score >= 100 ? '⭐⭐⭐' : score >= 50 ? '⭐⭐' : score >= 15 ? '⭐' : '☆';
}

function show(id){
  document.querySelectorAll('.sec').forEach(s => s.classList.remove('active'));
  document.getElementById(id).classList.add('active');
  window.scrollTo(0,0);
}

function home(){
  show('sec-menu');
  document.getElementById('curGame').textContent = '—';
}

function setCur(n){
  document.getElementById('curGame').textContent = n;
}

/* ========= Student ========= */
function saveStudent(){
  const name = (document.getElementById('stuName').value || '').trim();
  const cls  = (document.getElementById('stuClass').value || '').trim();
  const warn = document.getElementById('stuWarn');

  if(!name || !cls){
    warn.style.display = 'block';
    return;
  }
  warn.style.display = 'none';

  student.name = name;
  student.cls = cls;

  show('sec-menu');
}

function openFinal(){
  const now = new Date();
  const txt =
`نام: ${student.name || '—'}
کلاس: ${student.cls || '—'}
تاریخ: ${now.toLocaleDateString('fa-IR')}

امتیاز کل: ${fa(score)}

آزمون: ${fa(quizStats.correct)} از ${fa(quizStats.total)}
واژگان: ${fa(vocabStats.matched)} از ${fa(vocabStats.total)}
جاهای خالی: ${fa(fillStats.correct)} از ${fa(fillStats.total)}
درست/نادرست: ${fa(tfStats.correct)} از ${fa(tfStats.total)}

✅ لطفاً همین متن را برای معلم در شاد ارسال کنید.`;

  document.getElementById('finalText').textContent = txt;
  document.getElementById('copyOk').style.display = 'none';
  show('sec-final');
  setCur('نتیجه');
}

async function copyResult(){
  const t = document.getElementById('finalText').textContent;
  try{
    await navigator.clipboard.writeText(t);
    document.getElementById('copyOk').style.display = 'block';
  }catch(e){
    alert('کپی خودکار ممکن نشد. روی متن نگه دار و گزینه Copy را بزن.');
  }
}

function resetAll(){
  score = 0;
  upScore();

  quizStats = { correct: 0, total: 0 };
  vocabStats = { matched: 0, total: 0 };
  fillStats  = { correct: 0, total: 0 };
  tfStats    = { correct: 0, total: 0 };

  student = { name: '', cls: '' };
  const n = document.getElementById('stuName');
  const c = document.getElementById('stuClass');
  if(n) n.value = '';
  if(c) c.value = '';
  document.getElementById('stuWarn').style.display = 'none';
  document.getElementById('copyOk').style.display = 'none';

  show('sec-student');
  setCur('—');
}

/* ========= QUIZ ========= */
const questions = [
  { q:'به عقیدهٔ عنصرالمعالی، وقتی دوست تازه‌ای پیدا کردی، با دوستان قدیمی چه باید کرد؟', opts:['آن‌ها را فراموش کنی','آن‌ها را نگه داری و دوستی را حفظ کنی','با آن‌ها قطع رابطه کنی','فقط با دوستان ثروتمند بمانی'], ans:1, fb:'عنصرالمعالی می‌گوید دوستان قدیمی را فراموش نکن و دوستی با آن‌ها را حفظ کن.' },
  { q:'چگونه می‌توان از یک «نیم‌دوست» یک «دوست یکدل» ساخت؟', opts:['با پول دادن به او','با پرهیز از او','با نیکویی و مهربانی در هر پیش‌آمد','با رقابت با او'], ans:2, fb:'نویسنده می‌گوید با نیکویی و مهربانی در هر پیش‌آمد نیک و بد می‌توان نیم‌دوست را یکدل کرد.' },
  { q:'نویسندهٔ کتاب قابوس‌نامه کیست؟', opts:['سعدی','حافظ','عنصرالمعالی','فردوسی'], ans:2, fb:'قابوس‌نامه نوشتهٔ عنصرالمعالی است که برای فرزندش نوشته شد.' },
  { q:'قابوس‌نامه برای چه کسی نوشته شده است؟', opts:['برای شاهان','برای فرزند نویسنده','برای مردم عادی','برای سربازان'], ans:1, fb:'عنصرالمعالی این کتاب را به عنوان اندرزنامه برای فرزندش قیکاووس نوشت.' },
  { q:'در داستان «یک قطرهٔ عسل»، شکارچی چگونه به وجود عسل پی برد؟', opts:['به تصادف عسل را دید','زنبورها را دنبال کرد و قطره‌های عسل از شکاف سنگ را دید','آواز زنبورها را شنید','سگش عسل را پیدا کرد'], ans:1, fb:'شکارچی دید زنبورها اطراف یک سنگ پرواز می‌کنند و قطرات عسل از شکاف آن می‌ریزد.' },
  { q:'در داستان «یک قطرهٔ عسل»، اولین دعوا از کجا شروع شد؟', opts:['بر سر زمین','بر سر اختلاف ماهیفروش و روغن‌فروش بر سر قطرهٔ عسل و مگس','بر سر آب','بر سر شکار'], ans:1, fb:'یک قطره عسل روی ماهی افتاد، مگسی آمد، سگ ماهیفروش مگس را خورد و دعوای بزرگی آغاز شد.' },
  { q:'پیام اصلی داستان «یک قطرهٔ عسل» چیست؟', opts:['عسل خوراکی ارزشمند است','دشمنی و نزاع از کوچک‌ترین بی‌توجهی آغاز می‌شود','شکار حیوانات ممنوع است','باید همیشه دوست خوب داشت'], ans:1, fb:'داستان نشان می‌دهد دعواهای بزرگ از کوچک‌ترین اتفاق‌ها شروع می‌شوند و باید از دشمنی پرهیز کرد.' },
  { q:'در درس، کدام ویژگی برای انتخاب دوست خوب توصیه نشده؟', opts:['راستگویی','امانت‌داری','ثروت زیاد','درستکاری'], ans:2, fb:'نویسنده ثروت را ملاک دوستی نمی‌داند؛ ایمان، راستگویی و امانت‌داری مهم است.' },
  { q:'واژهٔ «نیم‌دوست» در درس به چه معناست؟', opts:['نیمی از دوستان','کسی که دوستی ناقص و کمرنگ دارد','دشمن پنهان','دوست مشترک'], ans:1, fb:'نیم‌دوست کسی است که دوستی با او ابتدایی و کمرنگ است اما می‌توان آن را تقویت کرد.' },
  { q:'چه رفتاری باعث می‌شود نیم‌دوست در دوستی صمیمی‌تر شود؟', opts:['بی‌توجهی به او','هدیه دادن','مهربانی و همراهی در سختی و شادی','پیوسته از او انتقاد کردن'], ans:2, fb:'عنصرالمعالی می‌گوید با مهربانی و همراهی در هر حال، نیم‌دوست را یکدل خواهی کرد.' },
];

let qIdx=0, qScore=0, qAnswered=false;

function startQuiz(){
  qIdx=0; qScore=0;
  quizStats.total = questions.length;
  quizStats.correct = 0;

  show('sec-quiz'); setCur('آزمون');
  renderQ();
}

function renderProg(){
  document.getElementById('qprog').innerHTML = questions.map((_,i)=>
    `<div class="pdot ${i<qIdx?'done':i===qIdx?'cur':''}"></div>`
  ).join('');
}

function renderQ(){
  if(qIdx>=questions.length){ showQResult(); return; }
  qAnswered=false; renderProg();
  const q=questions[qIdx];
  document.getElementById('qbody').innerHTML=`
    <div class="qcard">
      <div class="qnum">سوال ${fa(qIdx+1)} از ${fa(questions.length)}</div>
      <div class="qtext">${q.q}</div>
    </div>
    <div class="opts">
      ${q.opts.map((o,i)=>`<button class="obtn" onclick="ansQ(${i})">${o}</button>`).join('')}
    </div>
    <div class="fb" id="qfb"></div>
    <button class="nbtn" id="qnext" onclick="nextQ()">سوال بعدی ←</button>`;
}

function ansQ(i){
  if(qAnswered) return;
  qAnswered=true;

  const q=questions[qIdx];
  document.querySelectorAll('.obtn').forEach(b=>{ b.classList.add('locked'); b.style.cursor='default'; });

  const btns=document.querySelectorAll('.obtn');
  const fb=document.getElementById('qfb');

  if(i===q.ans){
    btns[i].classList.add('correct');
    fb.className='fb ok';
    fb.textContent='✅ آفرین! '+q.fb;
    qScore++; quizStats.correct++;
    score+=5; upScore();
  } else {
    btns[i].classList.add('wrong');
    btns[q.ans].classList.add('correct');
    fb.className='fb err';
    fb.textContent='❌ اشتباه! '+q.fb;
  }
  document.getElementById('qnext').style.display='block';
}

function nextQ(){ qIdx++; renderQ(); }

function showQResult(){
  const p=Math.round(qScore/questions.length*100);
  const e=p>=80?'🏆':p>=60?'🎉':p>=40?'👍':'📚';
  document.getElementById('qbody').innerHTML=`
    <div class="result-box">
      <div class="rbig">${e}</div>
      <h2>نتیجه آزمون</h2>
      <p>${fa(qScore)} از ${fa(questions.length)} صحیح · ${fa(p)}٪</p>
      <button class="ragain" onclick="startQuiz()">🔄 دوباره</button>
      <div style="margin-top:12px;">
        <button class="check-btn" onclick="openFinal()">📌 مشاهده نتیجه نهایی</button>
      </div>
    </div>`;
}

/* ========= VOCAB MATCH (Fix کامل) ========= */
const vocabData = [
  { word:'نیم‌دوست', meaning:'کسی که دوستی ابتدایی و کمرنگ دارد' },
  { word:'یکدل', meaning:'صمیمی و باوفا' },
  { word:'اندرز', meaning:'نصیحت و رهنمود' },
  { word:'مقصر', meaning:'گناهکار، کسی که تقصیر دارد' },
  { word:'مباد', meaning:'مبادا، نشود' },
  { word:'گوهر', meaning:'ذات، سرشت اصلی' },
];

let vSelType=null, vSelVal=null, vSelIdx=null, vDone=0;

function startVocab(){
  vSelType=null; vSelVal=null; vSelIdx=null; vDone=0;

  vocabStats.total = vocabData.length;
  vocabStats.matched = 0;

  show('sec-vocab'); setCur('واژگان');

  const sw=[...vocabData].sort(()=>Math.random()-.5);
  const sm=[...vocabData].sort(()=>Math.random()-.5);

  document.getElementById('vword').innerHTML = sw.map((v,i)=>
    `<div class="vitem" id="vw-${i}" data-v="${v.word}" onclick="pickV('w','${v.word}',${i})">${v.word}</div>`
  ).join('');

  document.getElementById('vdesc').innerHTML = sm.map((v,i)=>
    `<div class="vitem" id="vm-${i}" data-v="${v.word}" onclick="pickV('m','${v.word}',${i})">${v.meaning}</div>`
  ).join('');

  document.getElementById('vocabInfo').textContent='روی یک واژه کلیک کن، سپس معنی آن را انتخاب کن';
}

function pickV(type, val, idx){
  const el = document.getElementById(type==='w' ? `vw-${idx}` : `vm-${idx}`);
  if(!el || el.classList.contains('mat')) return;

  if(vSelType===null){
    vSelType=type; vSelVal=val; vSelIdx=idx;
    el.classList.add('sel');
    document.getElementById('vocabInfo').textContent='حالا جفتش را پیدا کن';
    return;
  }

  const prev = document.getElementById(vSelType==='w' ? `vw-${vSelIdx}` : `vm-${vSelIdx}`);
  if(!prev){ vSelType=null; vSelVal=null; vSelIdx=null; return; }

  if(vSelType===type){
    prev.classList.remove('sel');
    vSelType=type; vSelVal=val; vSelIdx=idx;
    el.classList.add('sel');
    return;
  }

  prev.classList.remove('sel');

  if(vSelVal===val){
    prev.classList.add('mat'); el.classList.add('mat'); vDone++;
    vocabStats.matched = vDone;

    score += 4; upScore();
    document.getElementById('vocabInfo').textContent =
      (vDone===vocabData.length) ? '🎉 همه را درست جور کردی!' : `✅ درست! ${fa(vocabData.length-vDone)} جفت مانده`;
  } else {
    prev.classList.add('shake'); el.classList.add('shake');
    document.getElementById('vocabInfo').textContent='❌ اشتباه! دوباره امتحان کن';
    setTimeout(()=>{ prev.classList.remove('shake'); el.classList.remove('shake'); }, 400);
  }

  vSelType=null; vSelVal=null; vSelIdx=null;
}

/* ========= FILL BLANKS ========= */
const fills = [
  { pre:'قابوس‌نامه نوشتهٔ', blank:'عنصرالمعالی/عنصر المعالی', post:'است.' },
  { pre:'با کسانی که دوستی', blank:'مختصر', post:'داری با نیکویی رفتار کن.' },
  { pre:'دوستان قدیمی را', blank:'فراموش', post:'نکن و رابطه‌ات را با آن‌ها قطع نکن.' },
  { pre:'هر پیش‌آمد نیک و بد، مهربانی کن تا نیم‌دوست', blank:'یکدل', post:'شود.' },
  { pre:'داستان یک قطرهٔ عسل نشان می‌دهد که دشمنی از', blank:'کوچک‌ترین/کوچکترین', post:'چیز آغاز می‌شود.' },
  { pre:'درس دوازدهم فارسی ششم موضوع', blank:'دوستی', post:'دارد.' },
];

function startFill(){
  fillStats.total = fills.length;
  fillStats.correct = 0;

  show('sec-fill'); setCur('جاخالی');

  document.getElementById('fillbody').innerHTML = fills.map((f,i)=>`
    <div class="fcard">
      <div class="fsentence">${f.pre}
        <input class="finput" id="fi-${i}" placeholder="؟" autocomplete="off" inputmode="text">
        ${f.post}
      </div>
    </div>
  `).join('');

  document.getElementById('fillFB').innerHTML='';
}

function isFillCorrect(userValue, answer){
  const accepted = String(answer).split('/').map(a => normalizeFa(a));
  const u = normalizeFa(userValue);
  return accepted.some(a => a === u);
}

function checkFill(){
  let ok=0;
  fills.forEach((f,i)=>{
    const inp=document.getElementById(`fi-${i}`);
    const v=inp.value;
    if(isFillCorrect(v, f.blank)){
      inp.classList.remove('err'); inp.classList.add('ok'); ok++;
    } else {
      inp.classList.remove('ok'); inp.classList.add('err');
      inp.placeholder = f.blank.split('/')[0];
    }
  });

  fillStats.correct = ok;

  score += ok * 3;
  upScore();

  document.getElementById('fillFB').innerHTML = `
    <div class="fb ${ok===fills.length?'ok':'err'}" style="display:block">
      ${ok===fills.length ? '✅ عالی! همه درست!' : `✏️ ${fa(ok)} از ${fa(fills.length)} درست. موارد قرمز را اصلاح کن.`}
    </div>
    <div style="text-align:center;margin-top:10px;">
      <button class="check-btn" onclick="openFinal()">📌 مشاهده نتیجه نهایی</button>
    </div>`;
}

/* ========= TRUE / FALSE ========= */
const tfData = [
  { s:'عنصرالمعالی می‌گوید دوستان قدیمی را به خاطر دوستان جدید فراموش کن.', ans:false, exp:'اشتباه! او می‌گوید دوستان قدیمی را حفظ کن.' },
  { s:'قابوس‌نامه یک کتاب اندرزی است که نویسنده برای فرزندش نوشت.', ans:true, exp:'درست! این کتاب اندرزنامه‌ای برای فرزند نویسنده است.' },
  { s:'در داستان یک قطرهٔ عسل، یک قطره عسل باعث آغاز درگیری بزرگی شد.', ans:true, exp:'درست! دعوا از یک قطرهٔ عسل و مگس شروع شد.' },
  { s:'نویسنده معتقد است ثروت مهم‌ترین معیار انتخاب دوست است.', ans:false, exp:'اشتباه! ایمان، راستگویی و امانت‌داری مهم‌تر از ثروت است.' },
  { s:'می‌توان با نیکویی و مهربانی، نیم‌دوست را به دوست یکدل تبدیل کرد.', ans:true, exp:'درست! این توصیهٔ اصلی عنصرالمعالی در این درس است.' },
  { s:'درس دوازدهم فارسی ششم موضوع وطن‌دوستی دارد.', ans:false, exp:'اشتباه! موضوع این درس دوستی است.' },
];

let tfCorrect=0;

function startTF(){
  tfCorrect=0;
  tfStats.total = tfData.length;
  tfStats.correct = 0;

  show('sec-tf'); setCur('درست/نادرست');

  document.getElementById('tfbody').innerHTML = tfData.map((t,i)=>`
    <div class="tf-card" id="tfc-${i}">
      <div class="tf-icon" id="tfi-${i}">❔</div>
      <div class="tf-text">${t.s}</div>
      <div class="tf-btns">
        <button class="tf-btn tf-true"  id="tft-${i}" onclick="answerTF(${i},true)">درست</button>
        <button class="tf-btn tf-false" id="tff-${i}" onclick="answerTF(${i},false)">نادرست</button>
      </div>
    </div>
  `).join('');

  document.getElementById('tfScore').textContent='';
}

function answerTF(i, ans){
  const t=tfData[i];
  const btnT=document.getElementById(`tft-${i}`);
  const btnF=document.getElementById(`tff-${i}`);
  const ico=document.getElementById(`tfi-${i}`);

  btnT.disabled=true; btnF.disabled=true;

  if(ans===t.ans){
    (ans?btnT:btnF).classList.add('correct');
    ico.textContent='✅';
    tfCorrect++; tfStats.correct = tfCorrect;
    score+=4; upScore();
  } else {
    (ans?btnT:btnF).classList.add('wrong');
    (t.ans?btnT:btnF).classList.add('correct');
    ico.textContent='❌';
  }

  const card=document.getElementById(`tfc-${i}`);
  const expEl=document.createElement('div');
  expEl.style.cssText='margin-top:8px;font-size:.78rem;color:var(--muted);line-height:1.5;';
  expEl.textContent=t.exp;
  card.appendChild(expEl);

  const allDone = tfData.every((_,j)=>document.getElementById(`tft-${j}`).disabled);
  if(allDone){
    document.getElementById('tfScore').textContent=`نتیجه: ${fa(tfCorrect)} از ${fa(tfData.length)} درست 🎯`;
    const box = document.createElement('div');
    box.style.cssText='text-align:center;margin-top:10px;';
    box.innerHTML = `<button class="check-btn" onclick="openFinal()">📌 مشاهده نتیجه نهایی</button>`;
    document.getElementById('tfbody').appendChild(box);
  }
}

/* init */
upScore();
</script>
</body>
</html>
```0
