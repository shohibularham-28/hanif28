<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Ulangan Bahasa Inggris — Narrative Text: Legend</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,500;0,600;0,700;1,500&family=Fraunces:opsz,wght@9..144,500;9..144,600;9..144,700&family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
  :root{
    --ink:#122019;
    --forest:#1c3a2e;
    --forest-deep:#0f2118;
    --parchment:#f4ecd8;
    --parchment-deep:#ecdfc0;
    --passage-bg:#e7d8b2;
    --passage-edge:#b98b3e;
    --card-bg:#fffcf3;
    --gold:#b8862f;
    --gold-bright:#d4a03f;
    --burgundy:#7a2b26;
    --burgundy-soft:#f4e3de;
    --ink-soft:#4a4030;
    --line:#d8c79a;
    --correct-hint:#3c6e4f;
  }
  *{box-sizing:border-box;}
  *, *::before, *::after{
    -webkit-user-select:none !important;
    -moz-user-select:none !important;
    -ms-user-select:none !important;
    user-select:none !important;
    -webkit-touch-callout:none !important;
    -webkit-tap-highlight-color:transparent;
  }
  body{
    margin:0;
    background:
      radial-gradient(circle at 15% 0%, rgba(184,134,47,0.10), transparent 45%),
      var(--parchment);
    font-family:'Fraunces', 'Cormorant Garamond', serif;
    color:var(--ink);
    padding-bottom:30px;
    min-height:100vh;
  }
  .wrap{max-width:760px;margin:0 auto;padding:0 14px;}

  /* HERO */
  .hero{
    background:
      radial-gradient(ellipse at top left, rgba(212,160,63,0.18), transparent 55%),
      linear-gradient(180deg, var(--forest) 0%, var(--forest-deep) 100%);
    color:var(--parchment);
    padding:22px 20px 20px;
    text-align:center;
    position:relative;
    overflow:hidden;
  }
  .hero::before, .hero::after{
    content:"";
    position:absolute;
    width:220px;height:220px;
    border:1px solid rgba(212,160,63,0.25);
    border-radius:50%;
    top:-90px; left:-70px;
  }
  .hero::after{
    top:auto; bottom:-110px; right:-80px; left:auto;
    width:260px; height:260px;
    border-color:rgba(212,160,63,0.15);
  }
  .eyebrow{
    font-family:'Inter',sans-serif;
    font-size:10px;
    letter-spacing:.26em;
    text-transform:uppercase;
    color:var(--gold-bright);
    font-weight:600;
    margin-bottom:6px;
    position:relative;
  }
  .hero h1{
    font-family:'Cormorant Garamond', serif;
    font-style:italic;
    font-weight:600;
    font-size:30px;
    margin:0 0 4px;
    letter-spacing:.01em;
    position:relative;
  }
  .hero .subtitle{
    font-family:'Inter',sans-serif;
    font-size:12px;
    letter-spacing:.16em;
    text-transform:uppercase;
    color:var(--gold-bright);
    position:relative;
  }
  .hero .rule{
    width:48px;height:2px;
    background:var(--gold-bright);
    margin:10px auto 12px;
    position:relative;
  }
  .instructions{
    font-family:'Inter',sans-serif;
    font-size:12px;
    line-height:1.55;
    color:#e4ddc8;
    max-width:560px;
    margin:0 auto;
    position:relative;
  }
  .instructions b{color:var(--gold-bright);font-weight:600;}

  /* progress / top bar */
  .progress-bar{
    position:sticky; top:0; z-index:20;
    background:var(--forest-deep);
    padding:9px 16px;
    display:flex; align-items:center; gap:10px;
    font-family:'Inter',sans-serif;
    border-bottom:2px solid var(--gold);
  }
  .progress-track{
    flex:1; height:6px; background:rgba(255,255,255,0.15);
    border-radius:4px; overflow:hidden;
  }
  .progress-fill{
    height:100%; width:0%;
    background:linear-gradient(90deg, var(--gold), var(--gold-bright));
    transition:width .3s ease;
  }
  .progress-label{
    color:var(--parchment); font-size:12px; font-weight:600; white-space:nowrap;
  }
  .grid-toggle-btn{
    flex:none;
    font-family:'Inter',sans-serif;
    font-size:11px; font-weight:700;
    background:rgba(255,255,255,0.10);
    color:var(--parchment);
    border:1px solid rgba(212,160,63,0.4);
    border-radius:14px;
    padding:5px 10px;
    cursor:pointer;
    white-space:nowrap;
  }
  .grid-toggle-btn:active{transform:scale(0.97);}

  /* CONNECTION PILL */
  .conn-pill{
    flex:none;
    display:flex; align-items:center; gap:5px;
    font-family:'Inter',sans-serif;
    font-size:10.5px; font-weight:700;
    padding:3px 9px;
    border-radius:12px;
    white-space:nowrap;
    background:rgba(255,255,255,0.08);
    color:#cfe8d6;
    transition:background .2s, color .2s;
  }
  .conn-pill .dot{
    width:7px;height:7px;border-radius:50%;
    background:#5fbf7d;
    flex:none;
  }
  .conn-pill.offline{
    background:rgba(122,43,38,0.25);
    color:#f4c9c2;
  }
  .conn-pill.offline .dot{background:#e0655a;}

  /* NAVIGATOR PANEL (grid of question numbers) */
  .nav-overlay{
    position:fixed; inset:0; background:rgba(15,33,24,0.55);
    z-index:40; display:none;
  }
  .nav-overlay.show{display:block;}
  .nav-panel{
    position:fixed; left:50%; top:50%; transform:translate(-50%,-50%);
    z-index:41;
    width:min(92vw, 480px);
    max-height:80vh;
    overflow-y:auto;
    background:var(--card-bg);
    border:2px solid var(--gold);
    border-radius:14px;
    padding:16px 16px 14px;
    box-shadow:0 10px 40px rgba(0,0,0,0.35);
  }
  .nav-panel h3{
    margin:0 0 4px;
    font-family:'Cormorant Garamond', serif;
    font-style:italic; font-weight:700;
    color:var(--forest-deep);
    font-size:19px;
  }
  .nav-panel .nav-sub{
    font-family:'Inter',sans-serif;
    font-size:11.5px;
    color:var(--ink-soft);
    margin:0 0 12px;
  }
  .nav-legend{
    display:flex; gap:14px; flex-wrap:wrap;
    font-family:'Inter',sans-serif;
    font-size:10.5px;
    color:var(--ink-soft);
    margin-bottom:12px;
  }
  .nav-legend span{display:inline-flex; align-items:center; gap:5px;}
  .nav-legend i{
    width:11px;height:11px;border-radius:4px;display:inline-block;
    border:1.5px solid var(--line);
  }
  .nav-legend i.done{background:var(--correct-hint);border-color:var(--correct-hint);}
  .nav-legend i.current{background:var(--gold-bright);border-color:var(--gold-bright);}
  .nav-grid{
    display:grid;
    grid-template-columns:repeat(6, 1fr);
    gap:8px;
  }
  .nav-cell{
    aspect-ratio:1;
    display:flex; align-items:center; justify-content:center;
    border-radius:8px;
    border:1.5px solid var(--line);
    background:#fffefb;
    font-family:'Inter',sans-serif;
    font-weight:700; font-size:13px;
    color:var(--ink-soft);
    cursor:pointer;
    position:relative;
  }
  .nav-cell.done{background:var(--correct-hint); border-color:var(--correct-hint); color:#fff;}
  .nav-cell.current{outline:2.5px solid var(--gold-bright); outline-offset:1px;}
  .nav-close{
    display:block; margin:14px auto 0;
    font-family:'Inter',sans-serif; font-size:12px; font-weight:700;
    background:none; border:1.5px solid var(--forest); color:var(--forest);
    padding:7px 20px; border-radius:16px; cursor:pointer;
  }

  /* PART / SECTION HEADER (per page) */
  .section-head{
    display:flex; align-items:center; gap:12px;
    margin:18px 0 12px;
  }
  .badge{
    flex:none;
    width:36px;height:36px;
    border-radius:50%;
    background:radial-gradient(circle at 32% 28%, var(--gold-bright), var(--gold) 70%);
    color:var(--forest-deep);
    display:flex; align-items:center; justify-content:center;
    font-family:'Cormorant Garamond',serif;
    font-weight:700; font-size:17px;
    box-shadow:0 2px 0 rgba(122,43,38,0.35), 0 3px 8px rgba(0,0,0,0.25);
    border:2px solid var(--parchment);
  }
  .section-titles h2{
    margin:0; font-size:18px; font-weight:700; color:var(--forest-deep);
    font-family:'Cormorant Garamond', serif;
  }
  .section-titles p{
    margin:1px 0 0; font-family:'Inter',sans-serif; font-size:11px;
    color:var(--ink-soft); letter-spacing:.02em;
  }
  .section-note{
    font-family:'Inter',sans-serif;
    font-size:11.5px; font-weight:600;
    background:var(--burgundy-soft);
    color:var(--burgundy);
    border:1px solid rgba(122,43,38,0.25);
    padding:6px 10px; border-radius:8px;
    margin-bottom:12px;
    display:inline-block;
  }

  /* PASSAGE (text/legend) BLOCK */
  .passage{
    background:var(--passage-bg);
    border:1px solid var(--passage-edge);
    border-left:5px solid var(--passage-edge);
    border-radius:9px;
    padding:12px 14px 14px;
    margin-bottom:12px;
    position:relative;
    box-shadow: 0 2px 6px rgba(90,60,20,0.12);
  }
  .passage::before{
    content:"❧";
    position:absolute;
    top:8px; right:12px;
    color:var(--gold);
    font-size:15px;
    opacity:.55;
  }
  .passage .ptitle{
    font-family:'Cormorant Garamond', serif;
    font-style:italic; font-weight:700;
    color:var(--burgundy);
    font-size:15px;
    margin:0 0 5px;
  }
  .passage p{
    font-family:'Inter', sans-serif;
    font-size:14.5px;
    line-height:1.55;
    color:#33291a;
    margin:0;
  }

  /* QUESTION CARD */
  .qcard{
    background:var(--card-bg);
    border:1px solid var(--line);
    border-radius:9px;
    padding:13px 14px 14px;
    margin-bottom:10px;
    box-shadow:0 1px 3px rgba(0,0,0,0.04);
    transition:box-shadow .2s, border-color .2s;
  }
  .qcard.answered{
    border-color:var(--correct-hint);
    box-shadow:0 0 0 1px rgba(60,110,79,0.25);
  }
  .qnum-row{
    display:flex; align-items:baseline; gap:9px;
    margin-bottom:10px;
  }
  .qnum{
    font-family:'Inter',sans-serif;
    font-weight:700; font-size:12px;
    color:#fff;
    background:var(--forest);
    padding:3px 10px;
    border-radius:14px;
    flex:none;
    display:inline-flex; align-items:center; gap:4px;
    transition:background .2s;
  }
  .qcard.answered .qnum{background:var(--correct-hint);}
  .qnum .check{display:none; font-size:10px;}
  .qcard.answered .qnum .check{display:inline;}
  .qtext{
    font-family:'Inter',sans-serif;
    font-size:14px; font-weight:500;
    color:var(--ink);
    line-height:1.4;
  }
  .options{display:flex; flex-direction:column; gap:7px;}
  .opt{
    display:flex; align-items:flex-start; gap:9px;
    padding:9px 10px;
    border:1.5px solid var(--line);
    border-radius:8px;
    background:#fffefb;
    cursor:pointer;
    font-family:'Inter',sans-serif;
    font-size:13px;
    line-height:1.4;
    transition:border-color .15s, background .15s, transform .1s;
  }
  .opt:hover{border-color:var(--gold);}
  .opt:active{transform:scale(0.995);}
  .opt.selected{
    border-color:var(--gold);
    background:linear-gradient(180deg, #fdf3de, #fbecc7);
    box-shadow:inset 0 0 0 1px var(--gold);
  }
  .opt-letter{
    flex:none;
    width:20px;height:20px;
    border-radius:50%;
    border:1.5px solid var(--ink-soft);
    display:flex; align-items:center; justify-content:center;
    font-size:11px; font-weight:700;
    color:var(--ink-soft);
    transition:background .15s, border-color .15s, color .15s;
  }
  .opt.selected .opt-letter{
    background:var(--gold); border-color:var(--gold); color:#fff;
  }
  .opt.multi.selected .opt-letter{border-radius:6px;}

  /* TRUE/FALSE */
  .tf-row{display:flex; gap:10px; margin-top:2px;}
  .tf-btn{
    flex:1;
    font-family:'Inter',sans-serif;
    font-weight:700; font-size:13px;
    letter-spacing:.03em;
    padding:10px 0;
    border-radius:18px;
    border:1.5px solid var(--line);
    background:#fffefb;
    cursor:pointer;
    color:var(--ink-soft);
    transition:all .15s;
  }
  .tf-btn.true.selected{background:var(--forest); border-color:var(--forest); color:#fff;}
  .tf-btn.false.selected{background:var(--burgundy); border-color:var(--burgundy); color:#fff;}

  .end-note{
    text-align:center;
    font-family:'Cormorant Garamond', serif;
    font-style:italic;
    color:var(--ink-soft);
    font-size:15px;
    margin:6px 0 6px;
  }

  .student-card{
    display:flex;
    gap:12px;
    background:var(--card-bg);
    border:1.5px solid var(--gold);
    border-radius:10px;
    padding:14px 16px;
    margin:18px 0 6px;
    box-shadow:0 2px 6px rgba(0,0,0,0.05);
    flex-wrap:wrap;
  }
  .student-field{flex:1; min-width:140px; display:flex; flex-direction:column; gap:4px;}
  .student-field label{
    font-family:'Inter',sans-serif;
    font-size:11px; font-weight:700;
    letter-spacing:.08em; text-transform:uppercase;
    color:var(--gold);
  }
  .student-field input{
    font-family:'Inter',sans-serif;
    font-size:14px;
    padding:8px 9px;
    border:1.5px solid var(--line);
    border-radius:7px;
    background:#fffefb;
    color:var(--ink);
    -webkit-user-select:text !important;
    -moz-user-select:text !important;
    user-select:text !important;
    width:100%;
  }
  .student-field input:focus{
    outline:none;
    border-color:var(--gold);
    box-shadow:0 0 0 2px rgba(184,134,47,0.2);
  }

  /* Explicit instruction banner shown on the cover page */
  .howto{
    background:var(--card-bg);
    border:1.5px dashed var(--gold);
    border-radius:10px;
    padding:14px 16px;
    margin:14px 0;
    font-family:'Inter',sans-serif;
    font-size:12.5px;
    line-height:1.65;
    color:var(--ink);
  }
  .howto b{color:var(--burgundy);}
  .howto ol{margin:6px 0 0; padding-left:18px;}
  .howto li{margin-bottom:4px;}

  .action-row{
    display:flex; justify-content:center; gap:10px;
    margin-top:16px; flex-wrap:wrap;
  }
  .btn{
    font-family:'Inter',sans-serif;
    font-size:14px; font-weight:700;
    padding:12px 26px;
    border-radius:22px;
    cursor:pointer;
    display:inline-flex; align-items:center; gap:8px;
    border:1.5px solid var(--gold);
  }
  .btn:disabled{opacity:.5; cursor:default;}
  .btn-primary{
    background:linear-gradient(180deg, var(--gold-bright), var(--gold));
    color:#2a1c05;
    box-shadow:0 3px 0 rgba(122,43,38,0.35);
  }
  .btn-primary:hover{filter:brightness(1.06);}
  .btn-primary:active{transform:translateY(1px); box-shadow:0 2px 0 rgba(122,43,38,0.35);}
  .btn-ghost{
    background:none;
    border:1.5px solid var(--forest);
    color:var(--forest);
  }
  .btn-ghost:hover{background:rgba(28,58,46,0.08);}
  .btn-submit{
    background:linear-gradient(180deg, var(--gold-bright), var(--gold));
    border:1.5px solid var(--gold);
    color:#2a1c05;
    box-shadow:0 3px 0 rgba(122,43,38,0.35);
  }
  .btn-reset{
    background:none;
    border:1.5px solid var(--burgundy);
    color:var(--burgundy);
    font-size:12px;
    padding:8px 16px;
  }
  .btn-reset:hover{background:var(--burgundy-soft);}

  /* Fixed bottom pager */
  .pager{
    position:sticky; bottom:0; z-index:15;
    background:var(--forest-deep);
    border-top:2px solid var(--gold);
    padding:9px 14px;
    display:flex; align-items:center; justify-content:space-between; gap:8px;
    margin-top:18px;
  }
  .pager-btn{
    font-family:'Inter',sans-serif;
    font-weight:700; font-size:13px;
    background:rgba(255,255,255,0.10);
    color:var(--parchment);
    border:1px solid rgba(212,160,63,0.4);
    border-radius:16px;
    padding:8px 16px;
    cursor:pointer;
    white-space:nowrap;
  }
  .pager-btn:disabled{opacity:.35; cursor:default;}
  .pager-mid{
    flex:1; text-align:center;
    font-family:'Inter',sans-serif;
    color:var(--gold-bright);
    font-size:12.5px; font-weight:700;
  }

  .submit-hint{
    text-align:center;
    font-family:'Inter',sans-serif;
    font-size:11px;
    color:var(--ink-soft);
    margin-top:10px;
    line-height:1.5;
  }

  .submit-status{
    display:none;
    align-items:center;
    justify-content:center;
    gap:9px;
    text-align:center;
    font-family:'Inter',sans-serif;
    font-size:13px;
    font-weight:600;
    margin-top:14px;
    padding:10px 14px;
    border-radius:10px;
    max-width:480px;
    margin-left:auto; margin-right:auto;
  }
  .submit-status.show{display:flex;}
  .submit-status .status-icon{
    flex:none;
    width:22px;height:22px;
    border-radius:50%;
    display:flex; align-items:center; justify-content:center;
    font-size:13px;
    font-weight:900;
    color:#fff;
  }
  .submit-status.ok{background:var(--burgundy-soft); color:var(--correct-hint); border:1px solid rgba(60,110,79,0.3);}
  .submit-status.ok .status-icon{background:var(--correct-hint);}
  .submit-status.warn{background:var(--burgundy-soft); color:var(--burgundy); border:1px solid rgba(122,43,38,0.3);}
  .submit-status.warn .status-icon{background:var(--burgundy);}
  .submit-status.pending{background:#f4ecd8; color:var(--ink-soft); border:1px solid var(--line);}
  .submit-status.pending .status-icon{background:var(--gold);}

  @media print{
    body *{display:none !important;}
  }
</style>
</head>
<body onselectstart="return false" oncontextmenu="return false" ondragstart="return false" oncopy="return false" oncut="return false">

<div class="progress-bar">
  <span class="progress-label" id="progLabel">0 / 30 answered</span>
  <div class="progress-track"><div class="progress-fill" id="progFill"></div></div>
  <button class="grid-toggle-btn" id="gridToggleBtn">☰ Soal</button>
  <span class="conn-pill" id="connPill"><span class="dot"></span><span id="connText">Online</span></span>
</div>

<div class="hero">
  <div class="eyebrow">Ulangan Bahasa Inggris</div>
  <h1>Narrative Text</h1>
  <div class="subtitle">— Legend —</div>
  <div class="rule"></div>
  <div class="instructions">
    <b>Part 1–3:</b> pilih satu jawaban benar (A–E). &nbsp;
    <b>Part 4:</b> pilih SEMUA jawaban yang benar. &nbsp;
    <b>Part 5:</b> tentukan True atau False. &nbsp;
    <br>Satu halaman = satu soal. Gunakan tombol <b>Sebelumnya / Berikutnya</b> di bawah, atau tekan <b>☰ Soal</b> untuk melompat langsung ke nomor tertentu.
    <br><b>Urutan soal dan urutan pilihan jawaban diacak</b> untuk setiap siswa.
  </div>
</div>

<div class="wrap" id="quiz">

  <!-- COVER PAGE -->
  <div class="page" data-page="cover">
    <div class="student-card">
      <div class="student-field">
        <label for="studentName">Nama</label>
        <input type="text" id="studentName" placeholder="Tulis nama lengkap">
      </div>
      <div class="student-field">
        <label for="studentClass">Kelas</label>
        <input type="text" id="studentClass" placeholder="Tulis kelas">
      </div>
    </div>

    <div class="howto">
      <b>Cara mengerjakan:</b>
      <ol>
        <li>Isi <b>Nama</b> dan <b>Kelas</b> di atas terlebih dahulu.</li>
        <li>Tekan <b>Mulai Mengerjakan</b> di bawah. Soal akan tampil satu per satu — kamu tidak perlu scroll untuk membaca teks bacaan.</li>
        <li>Pilih jawabanmu, lalu tekan <b>Berikutnya</b> untuk lanjut ke soal berikutnya (atau <b>Sebelumnya</b> untuk kembali).</li>
        <li>Tekan tombol <b>☰ Soal</b> di pojok kanan atas kapan saja untuk melihat peta seluruh soal — nomor yang sudah dijawab akan berwarna hijau.</li>
        <li>Setelah semua soal terjawab, tekan <b>✔ Submit Jawaban</b> di halaman terakhir.</li>
      </ol>
      <p style="margin:10px 0 0;"><b>Catatan:</b> urutan soal dan urutan pilihan jawaban (A, B, C, D, E) sudah diacak secara otomatis, jadi urutannya bisa berbeda antara satu siswa dengan siswa lain. Ini normal dan tidak memengaruhi jawaban yang benar.</p>
    </div>

    <div class="action-row">
      <button class="btn btn-primary" id="startBtn">Mulai Mengerjakan →</button>
    </div>
  </div>

  <div class="page-slot" id="pageSlot"></div>

  <div class="pager" id="pager" style="display:none;">
    <button class="pager-btn" id="prevBtn">← Sebelumnya</button>
    <span class="pager-mid" id="pagerMid">Soal 1 / 30</span>
    <button class="pager-btn" id="nextBtn">Berikutnya →</button>
  </div>

</div>

<!-- NAVIGATOR OVERLAY -->
<div class="nav-overlay" id="navOverlay"></div>
<div class="nav-panel" id="navPanel" style="display:none;">
  <h3>Peta Soal</h3>
  <p class="nav-sub">Tekan nomor untuk langsung menuju soal tersebut.</p>
  <div class="nav-legend">
    <span><i></i> Belum dijawab</span>
    <span><i class="done"></i> Sudah dijawab</span>
    <span><i class="current"></i> Sedang dibuka</span>
  </div>
  <div class="nav-grid" id="navGrid"></div>
  <button class="nav-close" id="navCloseBtn">Tutup</button>
</div>

<script>
  // ============ QUESTION DATA ============
  const QUESTIONS = [
    // ---------------- PART 1 ----------------
    {num:1, part:1, partTitle:"Identifying the Main Sentence", partDesc:"Pick the sentence that carries the paragraph's main idea",
     qtext:"Choose the sentence that would be the main sentence of the paragraph.", type:"single",
     options:[
       {l:"A", t:"The villagers carried baskets of rice to the temple every morning."},
       {l:"B", t:"The sacred spring was located behind an old temple."},
       {l:"C", t:"The villagers became worried when the sacred spring suddenly dried up."},
       {l:"D", t:"The priest placed white flowers beside the spring every afternoon."}
     ]},
    {num:2, part:1, qtext:"Choose the sentence that would be the main sentence of the paragraph.", type:"single",
     options:[
       {l:"A", t:"The fisherman's decision to return a magical pearl changed his life forever."},
       {l:"B", t:"The fisherman usually sailed before sunrise."},
       {l:"C", t:"He found the pearl inside a large shell near the northern shore."},
       {l:"D", t:"He brought the pearl to an old woman who lived near the harbor."}
     ]},
    {num:3, part:1, qtext:"Choose the sentence that would be the main sentence of the paragraph.", type:"single",
     options:[
       {l:"A", t:"Several birds flew above the trees as the girl entered the forest."},
       {l:"B", t:"Her grandmother had warned her about the forest many times."},
       {l:"C", t:"The girl carried a small lantern to light her way."},
       {l:"D", t:"A young girl discovered that the mysterious forest protected an ancient secret."}
     ]},
    {num:4, part:1, qtext:"Choose the sentence that would be the main sentence of the paragraph.", type:"single",
     options:[
       {l:"A", t:"Farmers planted rice and vegetables in the fertile valley."},
       {l:"B", t:"The king's selfish decision caused the fertile valley to lose its blessing."},
       {l:"C", t:"The king owned a large garden behind his palace."},
       {l:"D", t:"The villagers depended on the valley for their daily food."}
     ]},
    {num:5, part:1, qtext:"Choose the sentence that would be the main sentence of the paragraph.", type:"single",
     options:[
       {l:"A", t:"The warrior crossed three hills before reaching the hidden cave."},
       {l:"B", t:"He met an old woman beside a quiet waterfall."},
       {l:"C", t:"The warrior learned that true courage meant protecting others rather than seeking glory."},
       {l:"D", t:"The woman gave him a silver necklace before he continued his journey."}
     ]},

    // ---------------- PART 2 ----------------
    {num:6, part:2, partTitle:"Identifying the Main Idea", partDesc:"Read each legend and choose the best main idea",
     passageTitle:"Text 1 — The Legend of the Mountain Spring",
     passageText:"Long ago, a small village depended on a spring near a rocky hill. One year, the water began to disappear. A young girl named Lira followed strange footprints and found a wounded forest guardian near the spring. Instead of being afraid, she gave him food and medicine. After he recovered, the spring slowly returned to its former strength.",
     qtext:"What is the main idea of the text?", type:"single",
     options:[
       {l:"A", t:"A village became wealthy after discovering a hidden spring."},
       {l:"B", t:"A young girl helped a wounded guardian and restored the village's water source."},
       {l:"C", t:"Hunters protected a forest guardian from dangerous animals."},
       {l:"D", t:"The villagers learned how to survive without water."},
       {l:"E", t:"A forest guardian punished the people near the mountain."}
     ]},
    {num:7, part:2,
     passageTitle:"Text 2 — The Legend of the Silver Bird",
     passageText:"In an old coastal kingdom, people believed that a silver bird appeared before dangerous storms. One evening, a fisherman named Arven saw the bird flying low above the waves. He warned the villagers and asked them to move their boats. Some fishermen laughed at him, but a powerful storm struck several hours later. Because of Arven's warning, many boats and belongings were moved to safer places.",
     qtext:"What is the main idea of the text?", type:"single",
     options:[
       {l:"A", t:"A fisherman discovered a new island near the kingdom."},
       {l:"B", t:"A silver bird attacked fishermen near the coast."},
       {l:"C", t:"A fisherman trusted a mysterious warning and helped his community prepare for a storm."},
       {l:"D", t:"Older fishermen taught Arven how to predict storms."},
       {l:"E", t:"The coastal kingdom became famous for its silver birds."}
     ]},
    {num:8, part:2,
     passageTitle:"Text 3 — The Legend of the Sharing Bridge",
     passageText:"According to an old legend, a giant built a stone bridge to help travelers cross a deep ravine. He did not ask for gold in return. Instead, he asked travelers to leave a small piece of bread for anyone who might be hungry. After the giant disappeared, the villagers continued the tradition and taught it to their children.",
     qtext:"What is the main idea of the text?", type:"single",
     options:[
       {l:"A", t:"A giant destroyed a bridge after becoming angry with travelers."},
       {l:"B", t:"Travelers paid a giant with bread to cross a dangerous bridge."},
       {l:"C", t:"Villagers built a new road after the giant disappeared."},
       {l:"D", t:"A giant created a tradition of sharing food that continued after his disappearance."},
       {l:"E", t:"Travelers avoided the valley because they feared the giant."}
     ]},
    {num:9, part:2,
     passageTitle:"Text 4 — The Legend of the White Flower",
     passageText:"Many generations ago, a village stood beside a lake. The villagers often threw rubbish into the water until it became dark and muddy. An old farmer decided to clean the lake by himself. His actions inspired the villagers to help him. When the water became clear again, a strange white flower appeared on its surface, which the villagers believed was a sign of forgiveness.",
     qtext:"What is the main idea of the text?", type:"single",
     options:[
       {l:"A", t:"A mysterious flower destroyed a polluted lake."},
       {l:"B", t:"An old farmer inspired the villagers to restore a neglected lake."},
       {l:"C", t:"The villagers discovered valuable objects under the lake."},
       {l:"D", t:"A lake spirit forced the villagers to leave their homes."},
       {l:"E", t:"Farmers learned how to grow flowers in polluted water."}
     ]},
    {num:10, part:2,
     passageTitle:"Text 5 — The Legend of the Helpful Wolf",
     passageText:"A young royal messenger named Saren had to deliver an important letter through a dangerous forest. On the way, he found an injured wolf caught in a trap and freed it, even though this might delay his mission. Later, Saren became lost in the forest. The same wolf appeared and led him toward a familiar path. Saren eventually reached the castle and delivered the letter before sunrise.",
     qtext:"What is the main idea of the text?", type:"single",
     options:[
       {l:"A", t:"A wolf prevented a royal messenger from delivering an important letter."},
       {l:"B", t:"A messenger became lost because he entered a forbidden forest."},
       {l:"C", t:"A messenger's kindness to an injured wolf was later returned."},
       {l:"D", t:"A king ordered his messenger to capture a dangerous wolf."},
       {l:"E", t:"A hunter helped a messenger find his way through the forest."}
     ]},

    // ---------------- PART 3 ----------------
    {num:11, part:3, partTitle:"Textual & Inferential Information", partDesc:"Answer directly from the text, or read between the lines",
     passageTitle:"Text A — The Legend of the Whispering Bamboo",
     passageText:"Long ago, a farming village stood near a large bamboo forest. The villagers often heard soft whispers coming from the bamboo at night, but nobody knew where they came from. One evening, a farmer named Damar entered the forest after his youngest son failed to return home. Deep inside the forest, Damar found an old bamboo tree with a small opening in its trunk. From inside, he heard his son crying for help. The boy had fallen into a narrow hollow beneath the roots and could not climb out. Damar cut several bamboo poles and used them to help his son escape. After they returned home safely, the villagers began treating the bamboo forest with greater respect. They believed the forest had warned Damar by making the bamboo whisper.",
     qtext:"Why did Damar enter the bamboo forest?", type:"single",
     options:[
       {l:"A", t:"He wanted to collect bamboo for his house."},
       {l:"B", t:"He wanted to search for his missing son."},
       {l:"C", t:"He wanted to discover the source of the whispers."},
       {l:"D", t:"He wanted to hunt animals in the forest."},
       {l:"E", t:"He wanted to build a bridge across the forest."}
     ]},
    {num:12, part:3,
     passageTitle:"Text A — The Legend of the Whispering Bamboo",
     passageText:"Long ago, a farming village stood near a large bamboo forest. The villagers often heard soft whispers coming from the bamboo at night, but nobody knew where they came from. One evening, a farmer named Damar entered the forest after his youngest son failed to return home. Deep inside the forest, Damar found an old bamboo tree with a small opening in its trunk. From inside, he heard his son crying for help. The boy had fallen into a narrow hollow beneath the roots and could not climb out. Damar cut several bamboo poles and used them to help his son escape. After they returned home safely, the villagers began treating the bamboo forest with greater respect. They believed the forest had warned Damar by making the bamboo whisper.",
     qtext:"Where did Damar find his son?", type:"single",
     options:[
       {l:"A", t:"Beside a river near the forest."},
       {l:"B", t:"Inside an abandoned village house."},
       {l:"C", t:"Under the roots of an old bamboo tree."},
       {l:"D", t:"Behind a large rock outside the forest."},
       {l:"E", t:"Inside a small cave near the village."}
     ]},
    {num:13, part:3,
     passageTitle:"Text A — The Legend of the Whispering Bamboo",
     passageText:"Long ago, a farming village stood near a large bamboo forest. The villagers often heard soft whispers coming from the bamboo at night, but nobody knew where they came from. One evening, a farmer named Damar entered the forest after his youngest son failed to return home. Deep inside the forest, Damar found an old bamboo tree with a small opening in its trunk. From inside, he heard his son crying for help. The boy had fallen into a narrow hollow beneath the roots and could not climb out. Damar cut several bamboo poles and used them to help his son escape. After they returned home safely, the villagers began treating the bamboo forest with greater respect. They believed the forest had warned Damar by making the bamboo whisper.",
     qtext:"What did Damar use to help his son escape?", type:"single",
     options:[
       {l:"A", t:"A long piece of rope."},
       {l:"B", t:"A wooden ladder."},
       {l:"C", t:"Several bamboo poles."},
       {l:"D", t:"A fishing net."},
       {l:"E", t:"A metal chain."}
     ]},
    {num:14, part:3,
     passageTitle:"Text B — The Legend of the Moonlit Deer",
     passageText:"In a quiet kingdom surrounded by hills, a white deer appeared only during nights when the moon was full. According to an old story, the deer belonged to a guardian spirit who watched over travelers. One night, a young merchant named Tavin lost his way while returning from a distant market. He followed the white deer through a narrow valley until he reached a small village. The villagers welcomed him and gave him a place to rest. The next morning, Tavin discovered that the road he had originally planned to take had been destroyed by a landslide during the night. From that moment, Tavin believed that the mysterious deer had not appeared by accident.",
     qtext:"What can be inferred about the white deer?", type:"single",
     options:[
       {l:"A", t:"It probably helped travelers avoid danger."},
       {l:"B", t:"It usually lived inside the village."},
       {l:"C", t:"It was probably owned by Tavin."},
       {l:"D", t:"It appeared every night throughout the year."},
       {l:"E", t:"It wanted to lead travelers toward dangerous places."}
     ]},
    {num:15, part:3,
     passageTitle:"Text B — The Legend of the Moonlit Deer",
     passageText:"In a quiet kingdom surrounded by hills, a white deer appeared only during nights when the moon was full. According to an old story, the deer belonged to a guardian spirit who watched over travelers. One night, a young merchant named Tavin lost his way while returning from a distant market. He followed the white deer through a narrow valley until he reached a small village. The villagers welcomed him and gave him a place to rest. The next morning, Tavin discovered that the road he had originally planned to take had been destroyed by a landslide during the night. From that moment, Tavin believed that the mysterious deer had not appeared by accident.",
     qtext:"Why did Tavin believe the deer had appeared for a reason?", type:"single",
     options:[
       {l:"A", t:"The villagers told him that they owned the deer."},
       {l:"B", t:"The deer led him away from a road that was later destroyed."},
       {l:"C", t:"The deer followed him from the distant market."},
       {l:"D", t:"The deer warned him about the landslide directly."},
       {l:"E", t:"The deer brought him safely back to the kingdom."}
     ]},

    // ---------------- PART 4 ----------------
    {num:16, part:4, partTitle:"Multiple Choice, Multiple Answers", partDesc:"More than one option may be correct", partNote:"Choose ALL correct answers for each question.",
     passageTitle:"Text A — The Legend of the Singing Stone",
     passageText:"A long time ago, a village stood at the foot of a lonely mountain. Near the village was a large black stone. People believed that the stone could sing whenever someone in the village acted with honesty. One day, a poor woodcutter found a pouch of gold beside the road. Although he needed money, he brought the pouch to the village chief. That evening, the black stone produced a beautiful sound for the first time in many years. The villagers realized that the stone's song was a reminder that honesty could bring happiness to the whole community.",
     qtext:"Which statements are supported by the text?", type:"multi",
     options:[
       {l:"A", t:"The woodcutter found a pouch of gold."},
       {l:"B", t:"The woodcutter kept the gold for himself."},
       {l:"C", t:"The black stone was associated with honesty."},
       {l:"D", t:"The villagers had never heard the stone sing before."}
     ]},
    {num:17, part:4,
     passageTitle:"Text A — The Legend of the Singing Stone",
     passageText:"A long time ago, a village stood at the foot of a lonely mountain. Near the village was a large black stone. People believed that the stone could sing whenever someone in the village acted with honesty. One day, a poor woodcutter found a pouch of gold beside the road. Although he needed money, he brought the pouch to the village chief. That evening, the black stone produced a beautiful sound for the first time in many years. The villagers realized that the stone's song was a reminder that honesty could bring happiness to the whole community.",
     qtext:"What lessons can be learned from the legend?", type:"multi",
     options:[
       {l:"A", t:"Honesty can benefit more than one person."},
       {l:"B", t:"Wealth is always more important than honesty."},
       {l:"C", t:"A good action can inspire a community."},
       {l:"D", t:"People should keep valuable objects they find."}
     ]},
    {num:18, part:4,
     passageTitle:"Text A — The Legend of the Singing Stone",
     passageText:"A long time ago, a village stood at the foot of a lonely mountain. Near the village was a large black stone. People believed that the stone could sing whenever someone in the village acted with honesty. One day, a poor woodcutter found a pouch of gold beside the road. Although he needed money, he brought the pouch to the village chief. That evening, the black stone produced a beautiful sound for the first time in many years. The villagers realized that the stone's song was a reminder that honesty could bring happiness to the whole community.",
     qtext:"Which events happened in the story?", type:"multi",
     options:[
       {l:"A", t:"A woodcutter discovered gold beside a road."},
       {l:"B", t:"The woodcutter returned the gold to the village chief."},
       {l:"C", t:"The villagers destroyed the black stone."},
       {l:"D", t:"The stone produced a beautiful sound."}
     ]},
    {num:19, part:4,
     passageTitle:"Text B — The Legend of the Hidden Garden",
     passageText:"Behind a forgotten palace was a garden that could not be entered by ordinary people. According to the legend, the garden appeared only to someone who had helped another person without expecting a reward. A young servant named Mira once found an elderly traveler sitting beside a road. The traveler was tired and had no food, so Mira gave him her own lunch. She did not know that he was actually the guardian of the palace garden. The following morning, Mira discovered a beautiful garden behind the palace. The guardian explained that the garden appeared because Mira had shown kindness without asking for anything in return.",
     qtext:"Which statements are true according to the text?", type:"multi",
     options:[
       {l:"A", t:"Mira helped an elderly traveler."},
       {l:"B", t:"Mira gave the traveler her own lunch."},
       {l:"C", t:"Mira expected a valuable reward."},
       {l:"D", t:"The traveler was the guardian of the garden."}
     ]},
    {num:20, part:4,
     passageTitle:"Text B — The Legend of the Hidden Garden",
     passageText:"Behind a forgotten palace was a garden that could not be entered by ordinary people. According to the legend, the garden appeared only to someone who had helped another person without expecting a reward. A young servant named Mira once found an elderly traveler sitting beside a road. The traveler was tired and had no food, so Mira gave him her own lunch. She did not know that he was actually the guardian of the palace garden. The following morning, Mira discovered a beautiful garden behind the palace. The guardian explained that the garden appeared because Mira had shown kindness without asking for anything in return.",
     qtext:"Which ideas are implied by the legend?", type:"multi",
     options:[
       {l:"A", t:"Genuine kindness does not always require a reward."},
       {l:"B", t:"Mira's action demonstrated compassion."},
       {l:"C", t:"The garden appeared because Mira demanded to enter it."},
       {l:"D", t:"The traveler secretly tested Mira's character."}
     ]},

    // ---------------- PART 5 ----------------
    {num:21, part:5, partTitle:"True or False", partDesc:"Decide whether each statement matches the legend",
     passageTitle:"Text 1 — The Legend of the Blue Lantern",
     passageText:"Long ago, a village was surrounded by thick forests. At night, travelers often became lost because there were no lights along the narrow paths. A young woman named Elara made a blue lantern from an old glass bottle. Every evening, she placed it near the village entrance so travelers could find their way home. One stormy night, the lantern was blown away by strong wind. The villagers searched for it together and finally found it near a dangerous cliff. After that, they built a stronger shelter for the lantern and took turns protecting it.",
     qtext:"Elara made the blue lantern from an old glass bottle.", type:"tf"},
    {num:22, part:5,
     passageTitle:"Text 1 — The Legend of the Blue Lantern",
     passageText:"Long ago, a village was surrounded by thick forests. At night, travelers often became lost because there were no lights along the narrow paths. A young woman named Elara made a blue lantern from an old glass bottle. Every evening, she placed it near the village entrance so travelers could find their way home. One stormy night, the lantern was blown away by strong wind. The villagers searched for it together and finally found it near a dangerous cliff. After that, they built a stronger shelter for the lantern and took turns protecting it.",
     qtext:"The villagers ignored the lantern after it was blown away.", type:"tf"},
    {num:23, part:5,
     passageTitle:"Text 2 — The Legend of the Silent River",
     passageText:"A river once flowed through a peaceful farming village. The villagers believed that the river became silent whenever someone lied beside it. One afternoon, a merchant accused a farmer of stealing his horse. The farmer insisted that he was innocent. When both men stood beside the river, the water suddenly became completely quiet. The villagers investigated the matter and discovered that the merchant had actually lost his horse in another village. He later admitted that he had wrongly accused the farmer.",
     qtext:"The villagers believed that the river could become silent when someone lied.", type:"tf"},
    {num:24, part:5,
     passageTitle:"Text 2 — The Legend of the Silent River",
     passageText:"A river once flowed through a peaceful farming village. The villagers believed that the river became silent whenever someone lied beside it. One afternoon, a merchant accused a farmer of stealing his horse. The farmer insisted that he was innocent. When both men stood beside the river, the water suddenly became completely quiet. The villagers investigated the matter and discovered that the merchant had actually lost his horse in another village. He later admitted that he had wrongly accused the farmer.",
     qtext:"The investigation proved that the farmer had stolen the merchant's horse.", type:"tf"},
    {num:25, part:5,
     passageTitle:"Text 3 — The Legend of the Golden Seeds",
     passageText:"In an old farming village, a poor girl named Nara received three golden seeds from a mysterious traveler. The traveler told her to plant them only if she was willing to share the harvest with others. Nara planted the seeds beside her small house. A few weeks later, golden plants grew and produced enough grain to feed many families. Nara kept only what her family needed and distributed the rest among the villagers. The golden plants disappeared after the harvest, but the villagers remembered Nara's generosity for many years.",
     qtext:"Nara was instructed to share the harvest if she planted the seeds.", type:"tf"},
    {num:26, part:5,
     passageTitle:"Text 3 — The Legend of the Golden Seeds",
     passageText:"In an old farming village, a poor girl named Nara received three golden seeds from a mysterious traveler. The traveler told her to plant them only if she was willing to share the harvest with others. Nara planted the seeds beside her small house. A few weeks later, golden plants grew and produced enough grain to feed many families. Nara kept only what her family needed and distributed the rest among the villagers. The golden plants disappeared after the harvest, but the villagers remembered Nara's generosity for many years.",
     qtext:"Nara kept all the grain for her own family.", type:"tf"},
    {num:27, part:5,
     passageTitle:"Text 4 — The Legend of the Stone Fisherman",
     passageText:"According to an old coastal legend, a fisherman named Joran lived beside a quiet bay. He was famous for helping other fishermen during storms. One day, a terrible storm approached the village while several boats were still at sea. Joran went out to guide the boats back to shore. He managed to save everyone, but his own boat was destroyed by the waves. The next morning, the villagers found a strange stone shaped like a fisherman near the bay. They believed it represented Joran's courage and built a small monument beside it.",
     qtext:"Joran went to sea because he wanted to catch more fish before the storm.", type:"tf"},
    {num:28, part:5,
     passageTitle:"Text 4 — The Legend of the Stone Fisherman",
     passageText:"According to an old coastal legend, a fisherman named Joran lived beside a quiet bay. He was famous for helping other fishermen during storms. One day, a terrible storm approached the village while several boats were still at sea. Joran went out to guide the boats back to shore. He managed to save everyone, but his own boat was destroyed by the waves. The next morning, the villagers found a strange stone shaped like a fisherman near the bay. They believed it represented Joran's courage and built a small monument beside it.",
     qtext:"The villagers believed that the strange stone represented Joran's courage.", type:"tf"},
    {num:29, part:5,
     passageTitle:"Text 5 — The Legend of the Red Mountain",
     passageText:"Many years ago, a village stood beneath a mountain covered with red flowers. The villagers believed that the flowers protected the mountain from fire. One dry season, a careless traveler threw a burning piece of wood into the forest. A fire quickly spread toward the mountain. The villagers worked together to stop the flames and protect the flowers. After several days, the fire disappeared. According to the legend, the red flowers became brighter because they had witnessed the villagers' courage and cooperation.",
     qtext:"The villagers worked together to protect the mountain from the fire.", type:"tf"},
    {num:30, part:5,
     passageTitle:"Text 5 — The Legend of the Red Mountain",
     passageText:"Many years ago, a village stood beneath a mountain covered with red flowers. The villagers believed that the flowers protected the mountain from fire. One dry season, a careless traveler threw a burning piece of wood into the forest. A fire quickly spread toward the mountain. The villagers worked together to stop the flames and protect the flowers. After several days, the fire disappeared. According to the legend, the red flowers became brighter because they had witnessed the villagers' courage and cooperation.",
     qtext:"The fire was caused by a lightning strike during a storm.", type:"tf"}
  ];

  const PART_INFO = {
    1: {title:"Identifying the Main Sentence", desc:"Pick the sentence that carries the paragraph's main idea"},
    2: {title:"Identifying the Main Idea", desc:"Read each legend and choose the best main idea"},
    3: {title:"Textual & Inferential Information", desc:"Answer directly from the text, or read between the lines"},
    4: {title:"Multiple Choice, Multiple Answers", desc:"More than one option may be correct", note:"Choose ALL correct answers for each question."},
    5: {title:"True or False", desc:"Decide whether each statement matches the legend"}
  };

  const TOTAL = QUESTIONS.length;
  const answers = {}; // qnum -> answer string
  let currentIndex = -1; // -1 = cover page

  // ============ RANDOMIZATION ============
  // Fisher-Yates shuffle (returns a new array, does not mutate input)
  function shuffleArray(arr){
    const a = arr.slice();
    for(let i = a.length - 1; i > 0; i--){
      const j = Math.floor(Math.random() * (i + 1));
      [a[i], a[j]] = [a[j], a[i]];
    }
    return a;
  }

  // --- Randomize question order (persisted for this browser session/tab,
  //     so navigating back and forth doesn't reshuffle mid-attempt) ---
  const ORDER_KEY = 'quizOrder_narrativeLegend_v1';
  let orderOfNums;
  try{
    const saved = sessionStorage.getItem(ORDER_KEY);
    orderOfNums = saved ? JSON.parse(saved) : null;
  }catch(e){ orderOfNums = null; }
  if(!orderOfNums || orderOfNums.length !== TOTAL){
    // Shuffle WITHIN each part (1-5), then concatenate in part order.
    // This keeps each part's instructions together while still randomizing
    // which question a student sees first/last inside that part.
    const byPart = {};
    QUESTIONS.forEach(q=>{
      if(!byPart[q.part]) byPart[q.part] = [];
      byPart[q.part].push(q.num);
    });
    const partKeys = Object.keys(byPart).map(Number).sort((a,b)=>a-b);
    orderOfNums = [];
    partKeys.forEach(p=>{
      orderOfNums = orderOfNums.concat(shuffleArray(byPart[p]));
    });
    try{ sessionStorage.setItem(ORDER_KEY, JSON.stringify(orderOfNums)); }catch(e){}
  }
  const QMAP = {};
  QUESTIONS.forEach(q => { QMAP[q.num] = q; });
  const QUESTIONS_ORDERED = orderOfNums.map(n => QMAP[n]);

  // --- Randomize option order per question (identity letter stays attached
  //     to its own option text, so the submitted answer letter always
  //     matches the teacher's original answer key regardless of on-screen order) ---
  QUESTIONS_ORDERED.forEach(q=>{
    if(q.options){
      q.displayOptions = shuffleArray(q.options);
    }
  });

  const pageSlot = document.getElementById('pageSlot');
  const coverPage = document.querySelector('.page[data-page="cover"]');
  const pager = document.getElementById('pager');
  const pagerMid = document.getElementById('pagerMid');
  const prevBtn = document.getElementById('prevBtn');
  const nextBtn = document.getElementById('nextBtn');

  function esc(s){
    return s.replace(/&/g,'&amp;').replace(/</g,'&lt;').replace(/>/g,'&gt;');
  }

  function buildPage(q, displayNum){
    let html = '';
    const info = PART_INFO[q.part];
    html += '<div class="section-head"><div class="badge">'+q.part+'</div><div class="section-titles"><h2>'+esc(info.title)+'</h2><p>'+esc(info.desc)+'</p></div></div>';
    if(info.note){
      html += '<div class="section-note">'+esc(info.note)+'</div>';
    }

    if(q.passageText){
      html += '<div class="passage"><p class="ptitle">'+esc(q.passageTitle)+'</p><p>'+esc(q.passageText)+'</p></div>';
    }

    html += '<div class="qcard" data-q="'+q.num+'" data-type="'+q.type+'">';
    html += '<div class="qnum-row"><span class="qnum">Q'+displayNum+'<span class="check">✓</span></span></div>';
    html += '<div class="qtext" style="margin-bottom:10px;">'+esc(q.qtext)+'</div>';

    if(q.type === 'single' || q.type === 'multi'){
      html += '<div class="options">';
      (q.displayOptions || q.options).forEach(o=>{
        const cls = q.type === 'multi' ? 'opt multi' : 'opt';
        html += '<div class="'+cls+'" data-letter="'+o.l+'"><span class="opt-letter">'+o.l+'</span><span>'+esc(o.t)+'</span></div>';
      });
      html += '</div>';
    } else if(q.type === 'tf'){
      html += '<div class="tf-row"><button class="tf-btn true">TRUE</button><button class="tf-btn false">FALSE</button></div>';
    }
    html += '</div>';
    return html;
  }

  function buildEndPage(){
    return `
      <div class="end-note">❦ End of the tale — good luck. ❦</div>
      <div class="action-row">
        <button class="btn btn-submit" id="submitBtn">✔ Submit Jawaban</button>
        <button class="btn btn-reset" id="resetBtn">Clear all answers</button>
      </div>
      <div class="submit-hint">
        Pastikan Nama &amp; Kelas sudah diisi di halaman pertama, lalu tekan <b>Submit Jawaban</b>. Ringkasan jawaban akan langsung terkirim ke Google Form. Jika koneksi internet terputus, submit akan gagal — cek status di pojok kanan atas lalu tekan <b>Submit Jawaban</b> lagi.
      </div>
      <div class="submit-status" id="submitStatus"><span class="status-icon" id="statusIcon"></span><span id="statusText"></span></div>
    `;
  }

  function renderPage(index){
    currentIndex = index;
    coverPage.style.display = 'none';
    pager.style.display = 'flex';

    if(index >= TOTAL){
      // final / submit page
      pageSlot.innerHTML = buildEndPage();
      pagerMid.textContent = 'Halaman terakhir — Submit';
      prevBtn.disabled = false;
      nextBtn.disabled = true;
      attachEndPageEvents();
      window.scrollTo({top:0, behavior:'instant'});
      return;
    }

    const q = QUESTIONS_ORDERED[index];
    pageSlot.innerHTML = buildPage(q, index + 1);
    pagerMid.textContent = 'Soal ' + (index+1) + ' / ' + TOTAL;
    prevBtn.disabled = (index === 0) ? false : false; // prev always allowed (goes to cover on 0)
    nextBtn.disabled = false;
    restoreAnswerUI(q);
    attachQuestionEvents(q);
    window.scrollTo({top:0, behavior:'instant'});
  }

  function restoreAnswerUI(q){
    const card = document.querySelector('.qcard[data-q="'+q.num+'"]');
    const saved = answers[q.num];
    if(!saved) return;
    if(q.type === 'single'){
      const opt = card.querySelector('.opt[data-letter="'+saved+'"]');
      if(opt) opt.classList.add('selected');
    } else if(q.type === 'multi'){
      const letters = saved.split(',').map(s=>s.trim());
      letters.forEach(l=>{
        const opt = card.querySelector('.opt[data-letter="'+l+'"]');
        if(opt) opt.classList.add('selected');
      });
    } else if(q.type === 'tf'){
      const btn = card.querySelector('.tf-btn.' + (saved === 'TRUE' ? 'true' : 'false'));
      if(btn) btn.classList.add('selected');
    }
    card.classList.add('answered');
  }

  function attachQuestionEvents(q){
    const card = document.querySelector('.qcard[data-q="'+q.num+'"]');
    if(q.type === 'single'){
      card.querySelectorAll('.opt').forEach(opt=>{
        opt.addEventListener('click', ()=>{
          card.querySelectorAll('.opt').forEach(o=>o.classList.remove('selected'));
          opt.classList.add('selected');
          answers[q.num] = opt.dataset.letter;
          card.classList.add('answered');
          updateProgress();
          renderNavGrid();
        });
      });
    } else if(q.type === 'multi'){
      card.querySelectorAll('.opt').forEach(opt=>{
        opt.addEventListener('click', ()=>{
          opt.classList.toggle('selected');
          const sels = card.querySelectorAll('.opt.selected');
          if(sels.length){
            answers[q.num] = Array.from(sels).map(o=>o.dataset.letter).join(', ');
            card.classList.add('answered');
          } else {
            delete answers[q.num];
            card.classList.remove('answered');
          }
          updateProgress();
          renderNavGrid();
        });
      });
    } else if(q.type === 'tf'){
      card.querySelectorAll('.tf-btn').forEach(btn=>{
        btn.addEventListener('click', ()=>{
          card.querySelectorAll('.tf-btn').forEach(b=>b.classList.remove('selected'));
          btn.classList.add('selected');
          answers[q.num] = btn.classList.contains('true') ? 'TRUE' : 'FALSE';
          card.classList.add('answered');
          updateProgress();
          renderNavGrid();
        });
      });
    }
  }

  function updateProgress(){
    const count = Object.keys(answers).length;
    document.getElementById('progLabel').textContent = count + ' / ' + TOTAL + ' answered';
    document.getElementById('progFill').style.width = (count/TOTAL*100) + '%';
  }

  // ===== Navigation controls =====
  document.getElementById('startBtn').addEventListener('click', ()=>{
    renderPage(0);
  });

  prevBtn.addEventListener('click', ()=>{
    if(currentIndex <= 0){
      // back to cover
      currentIndex = -1;
      pageSlot.innerHTML = '';
      coverPage.style.display = 'block';
      pager.style.display = 'none';
      window.scrollTo({top:0, behavior:'instant'});
    } else {
      renderPage(currentIndex - 1);
    }
  });

  nextBtn.addEventListener('click', ()=>{
    if(currentIndex < TOTAL){
      renderPage(currentIndex + 1);
    }
  });

  // ===== Navigator grid panel =====
  const navOverlay = document.getElementById('navOverlay');
  const navPanel = document.getElementById('navPanel');
  const navGrid = document.getElementById('navGrid');

  function renderNavGrid(){
    navGrid.innerHTML = '';
    QUESTIONS_ORDERED.forEach((q, i)=>{
      const cell = document.createElement('div');
      cell.className = 'nav-cell';
      if(answers[q.num]) cell.classList.add('done');
      if(i === currentIndex) cell.classList.add('current');
      cell.textContent = i + 1;
      cell.addEventListener('click', ()=>{
        closeNav();
        renderPage(i);
      });
      navGrid.appendChild(cell);
    });
  }

  function openNav(){
    renderNavGrid();
    navOverlay.classList.add('show');
    navPanel.style.display = 'block';
  }
  function closeNav(){
    navOverlay.classList.remove('show');
    navPanel.style.display = 'none';
  }
  document.getElementById('gridToggleBtn').addEventListener('click', openNav);
  document.getElementById('navCloseBtn').addEventListener('click', closeNav);
  navOverlay.addEventListener('click', closeNav);

  // ===== Connection status pill =====
  const connPill = document.getElementById('connPill');
  const connText = document.getElementById('connText');
  function refreshConnPill(){
    const online = navigator.onLine;
    connPill.classList.toggle('offline', !online);
    connText.textContent = online ? 'Online' : 'Offline';
  }
  window.addEventListener('online', refreshConnPill);
  window.addEventListener('offline', refreshConnPill);
  refreshConnPill();

  async function hasRealConnection(){
    if(!navigator.onLine) return false;
    try{
      await fetch('https://www.gstatic.com/generate_204', { mode:'no-cors', cache:'no-store' });
      return true;
    }catch(e){
      return false;
    }
  }

  // ===== Answer summary + Google Form submission =====
  const GOOGLE_FORM_ID = '1FAIpQLSegeGmskBsfPe7C0aP6UBacnL2qFdMCYE2kut3DtbNS1AwR2w';
  const GOOGLE_FORM_ACTION = 'https://docs.google.com/forms/d/e/' + GOOGLE_FORM_ID + '/formResponse';
  const GOOGLE_FORM_ENTRY = 'entry.48174494';

  function collectAnswers(){
    const data = {};
    data.name = document.getElementById('studentName').value.trim();
    data.kelas = document.getElementById('studentClass').value.trim();
    QUESTIONS.forEach(q=>{
      data[q.num] = answers[q.num] || '-';
    });
    return data;
  }

  function buildSummaryText(){
    const data = collectAnswers();
    const lines = [];
    lines.push('Ulangan Bahasa Inggris — Narrative Text: Legend');
    lines.push('Nama: ' + (data.name || '-'));
    lines.push('Kelas: ' + (data.kelas || '-'));
    lines.push('');
    for(let i = 1; i <= TOTAL; i++){
      lines.push('Q' + i + ': ' + data[i]);
    }
    lines.push('');
    lines.push('(' + Object.keys(answers).length + '/' + TOTAL + ' soal terjawab)');
    return lines.join('\n');
  }

  function setStatus(kind, message){
    const statusEl = document.getElementById('submitStatus');
    const iconEl = document.getElementById('statusIcon');
    const textEl = document.getElementById('statusText');
    statusEl.className = 'submit-status show ' + kind;
    textEl.textContent = message;
    if(kind === 'ok'){ iconEl.textContent = '✓'; }
    else if(kind === 'warn'){ iconEl.textContent = '✕'; }
    else { iconEl.textContent = '…'; }
  }

  function attachEndPageEvents(){
    document.getElementById('submitBtn').addEventListener('click', submitAnswers);
    document.getElementById('resetBtn').addEventListener('click', ()=>{
      for(const k in answers) delete answers[k];
      updateProgress();
      renderPage(0);
    });
  }

  async function submitAnswers(){
    const btn = document.getElementById('submitBtn');
    const name = document.getElementById('studentName').value.trim();

    if(!name){
      setStatus('warn', 'Isi nama terlebih dahulu di halaman pertama sebelum submit.');
      return;
    }
    const answeredCount = Object.keys(answers).length;
    if(answeredCount < TOTAL){
      const proceed = confirm('Baru ' + answeredCount + ' dari ' + TOTAL + ' soal terjawab. Tetap submit?');
      if(!proceed) return;
    }

    btn.disabled = true;
    btn.textContent = 'Memeriksa koneksi…';
    setStatus('pending', 'Memeriksa koneksi internet…');

    const online = await hasRealConnection();
    if(!online){
      setStatus('warn', 'Gagal — tidak ada koneksi internet. Tekan Submit Jawaban lagi setelah tersambung.');
      btn.disabled = false;
      btn.textContent = '✔ Submit Jawaban';
      return;
    }

    btn.textContent = 'Mengirim…';
    const summary = buildSummaryText();

    try{
      const formData = new URLSearchParams();
      formData.append(GOOGLE_FORM_ENTRY, summary);

      await fetch(GOOGLE_FORM_ACTION, {
        method: 'POST',
        mode: 'no-cors',
        headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
        body: formData.toString()
      });

      setStatus('ok', 'Berhasil — jawaban kamu sudah terkirim.');
    }catch(err){
      setStatus('warn', 'Gagal mengirim — terjadi kesalahan. Tekan Submit Jawaban lagi.');
      btn.disabled = false;
      btn.textContent = '✔ Submit Jawaban';
      return;
    }

    btn.disabled = false;
    btn.textContent = '✔ Submit Jawaban';
  }

  // Prevent copying, right-click context menu, and text selection
  document.addEventListener('contextmenu', e => e.preventDefault());
  document.addEventListener('copy', e => e.preventDefault());
  document.addEventListener('cut', e => e.preventDefault());
  document.addEventListener('selectstart', e => e.preventDefault());
  document.addEventListener('dragstart', e => e.preventDefault());
  document.addEventListener('keydown', e => {
    if ((e.ctrlKey || e.metaKey) && ['c','x','a','p','s','u'].includes(e.key.toLowerCase())) {
      e.preventDefault();
    }
  });
</script>

</body>
</html>
