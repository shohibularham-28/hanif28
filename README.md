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
    padding-bottom:60px;
  }
  .wrap{max-width:760px;margin:0 auto;padding:0 14px;}

  /* HERO */
  .hero{
    background:
      radial-gradient(ellipse at top left, rgba(212,160,63,0.18), transparent 55%),
      linear-gradient(180deg, var(--forest) 0%, var(--forest-deep) 100%);
    color:var(--parchment);
    padding:24px 20px 22px;
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
    font-size:32px;
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
    max-width:520px;
    margin:0 auto;
    position:relative;
  }
  .instructions b{color:var(--gold-bright);font-weight:600;}

  /* progress */
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

  /* SECTION HEADER */
  .section{margin-top:22px;}
  .section-head{
    display:flex; align-items:center; gap:12px;
    margin:0 0 12px;
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
    background:
      linear-gradient(180deg, var(--passage-bg), var(--passage-deep, var(--passage-bg)));
    border:1px solid var(--passage-edge);
    border-left:5px solid var(--passage-edge);
    border-radius:9px;
    padding:12px 14px 14px;
    margin-bottom:10px;
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
    font-family:'Cormorant Garamond', serif;
    font-size:14.5px;
    line-height:1.42;
    color:#33291a;
    margin:0;
  }

  /* QUESTION CARD */
  .qcard{
    background:var(--card-bg);
    border:1px solid var(--line);
    border-radius:9px;
    padding:11px 12px 11px;
    margin-bottom:10px;
    box-shadow:0 1px 3px rgba(0,0,0,0.04);
  }
  .qnum-row{
    display:flex; align-items:baseline; gap:7px;
    margin-bottom:7px;
  }
  .qnum{
    font-family:'Inter',sans-serif;
    font-weight:700; font-size:11px;
    color:#fff;
    background:var(--forest);
    padding:2px 8px;
    border-radius:14px;
    flex:none;
  }
  .qtext{
    font-family:'Inter',sans-serif;
    font-size:13px; font-weight:500;
    color:var(--ink);
    line-height:1.35;
  }
  .options{display:flex; flex-direction:column; gap:6px;}
  .opt{
    display:flex; align-items:flex-start; gap:8px;
    padding:7px 9px;
    border:1.5px solid var(--line);
    border-radius:7px;
    background:#fffefb;
    cursor:pointer;
    font-family:'Inter',sans-serif;
    font-size:12.5px;
    line-height:1.35;
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
    width:19px;height:19px;
    border-radius:50%;
    border:1.5px solid var(--ink-soft);
    display:flex; align-items:center; justify-content:center;
    font-size:10.5px; font-weight:700;
    color:var(--ink-soft);
  }
  .opt.selected .opt-letter{
    background:var(--gold); border-color:var(--gold); color:#fff;
  }
  .opt.multi.selected .opt-letter{border-radius:6px;}

  /* TRUE/FALSE */
  .tf-row{display:flex; gap:8px; margin-top:1px;}
  .tf-btn{
    flex:1;
    font-family:'Inter',sans-serif;
    font-weight:700; font-size:12px;
    letter-spacing:.03em;
    padding:7px 0;
    border-radius:18px;
    border:1.5px solid var(--line);
    background:#fffefb;
    cursor:pointer;
    color:var(--ink-soft);
    transition:all .15s;
  }
  .tf-btn.true.selected{background:var(--forest); border-color:var(--forest); color:#fff;}
  .tf-btn.false.selected{background:var(--burgundy); border-color:var(--burgundy); color:#fff;}

  .passage-group{
    scroll-margin-top:60px;
  }
  .divider{
    display:flex; align-items:center; gap:12px;
    margin:20px 0 4px;
    color:var(--gold);
  }
  .divider::before, .divider::after{
    content:""; flex:1; height:1px; background:var(--line);
  }

  .end-note{
    text-align:center;
    font-family:'Cormorant Garamond', serif;
    font-style:italic;
    color:var(--ink-soft);
    font-size:15px;
    margin:24px 0 6px;
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
  }
  .student-field{flex:1; display:flex; flex-direction:column; gap:4px;}
  .student-field label{
    font-family:'Inter',sans-serif;
    font-size:11px; font-weight:700;
    letter-spacing:.08em; text-transform:uppercase;
    color:var(--gold);
  }
  .student-field input{
    font-family:'Inter',sans-serif;
    font-size:14px;
    padding:7px 9px;
    border:1.5px solid var(--line);
    border-radius:7px;
    background:#fffefb;
    color:var(--ink);
    -webkit-user-select:text !important;
    -moz-user-select:text !important;
    user-select:text !important;
  }
  .student-field input:focus{
    outline:none;
    border-color:var(--gold);
    box-shadow:0 0 0 2px rgba(184,134,47,0.2);
  }

  .action-row{
    display:flex; justify-content:center; gap:10px;
    margin-top:20px; flex-wrap:wrap;
  }
  .submit-btn{
    font-family:'Inter',sans-serif;
    font-size:14px; font-weight:700;
    background:linear-gradient(180deg, var(--gold-bright), var(--gold));
    border:1.5px solid var(--gold);
    color:#2a1c05;
    padding:12px 30px;
    border-radius:22px;
    cursor:pointer;
    display:inline-flex; align-items:center; gap:8px;
    box-shadow:0 3px 0 rgba(122,43,38,0.35);
  }
  .submit-btn:hover{filter:brightness(1.06);}
  .submit-btn:active{transform:translateY(1px); box-shadow:0 2px 0 rgba(122,43,38,0.35);}
  .submit-btn:disabled{opacity:.6; cursor:default;}

  .submit-hint{
    text-align:center;
    font-family:'Inter',sans-serif;
    font-size:11px;
    color:var(--ink-soft);
    margin-top:8px;
    line-height:1.5;
  }

  .submit-status{
    text-align:center;
    font-family:'Inter',sans-serif;
    font-size:13px;
    font-weight:600;
    margin-top:12px;
    display:none;
  }
  .submit-status.show{display:block;}
  .submit-status.ok{color:var(--correct-hint);}
  .submit-status.warn{color:var(--burgundy);}

  .reset-wrap{text-align:center; margin-top:18px;}
  .reset-btn{
    font-family:'Inter',sans-serif;
    font-size:12px; font-weight:600;
    background:none;
    border:1.5px solid var(--burgundy);
    color:var(--burgundy);
    padding:7px 16px;
    border-radius:18px;
    cursor:pointer;
  }
  .reset-btn:hover{background:var(--burgundy-soft);}

  @media print{
    .progress-bar, .submit-btn, .doc-btn, .reset-btn, .submit-hint, .action-row{display:none !important;}
    body{background:#fff !important;}
    .hero{background:var(--forest-deep) !important; -webkit-print-color-adjust:exact; print-color-adjust:exact;}
    .passage{background:var(--passage-bg) !important; -webkit-print-color-adjust:exact; print-color-adjust:exact; break-inside:avoid;}
    .qcard{break-inside:avoid; box-shadow:none;}
    .opt.selected{-webkit-print-color-adjust:exact; print-color-adjust:exact;}
    .tf-btn.selected{-webkit-print-color-adjust:exact; print-color-adjust:exact;}
    .student-card{-webkit-print-color-adjust:exact; print-color-adjust:exact; break-inside:avoid;}
    .section{break-inside:avoid-page;}
  }
</style>
</head>
<body onselectstart="return false" oncontextmenu="return false" ondragstart="return false" oncopy="return false" oncut="return false">

<div class="progress-bar">
  <span class="progress-label" id="progLabel">0 / 30 answered</span>
  <div class="progress-track"><div class="progress-fill" id="progFill"></div></div>
</div>

<div class="hero">
  <div class="eyebrow">Ulangan Bahasa Inggris</div>
  <h1>Narrative Text</h1>
  <div class="subtitle">— Legend —</div>
  <div class="rule"></div>
  <div class="instructions">
    <b>Part 1–3:</b> choose one correct answer (A–E). &nbsp;
    <b>Part 4:</b> choose all correct answers. &nbsp;
    <b>Part 5:</b> decide True or False.
  </div>
</div>

<div class="wrap" id="quiz">

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

  <!-- PART 1 -->
  <div class="section">
    <div class="section-head">
      <div class="badge">1</div>
      <div class="section-titles">
        <h2>Identifying the Main Sentence</h2>
        <p>Pick the sentence that carries the paragraph's main idea</p>
      </div>
    </div>

    <div class="qcard" data-q="1" data-type="single">
      <div class="qnum-row"><span class="qnum">Q1</span><span class="qtext">Choose the sentence that would be the main sentence of the paragraph.</span></div>
      <div class="options">
        <div class="opt" data-letter="A"><span class="opt-letter">A</span><span>The villagers carried baskets of rice to the temple every morning.</span></div>
        <div class="opt" data-letter="B"><span class="opt-letter">B</span><span>The sacred spring was located behind an old temple.</span></div>
        <div class="opt" data-letter="C"><span class="opt-letter">C</span><span>The villagers became worried when the sacred spring suddenly dried up.</span></div>
        <div class="opt" data-letter="D"><span class="opt-letter">D</span><span>The priest placed white flowers beside the spring every afternoon.</span></div>
      </div>
    </div>

    <div class="qcard" data-q="2" data-type="single">
      <div class="qnum-row"><span class="qnum">Q2</span><span class="qtext">Choose the sentence that would be the main sentence of the paragraph.</span></div>
      <div class="options">
        <div class="opt" data-letter="A"><span class="opt-letter">A</span><span>The fisherman's decision to return a magical pearl changed his life forever.</span></div>
        <div class="opt" data-letter="B"><span class="opt-letter">B</span><span>The fisherman usually sailed before sunrise.</span></div>
        <div class="opt" data-letter="C"><span class="opt-letter">C</span><span>He found the pearl inside a large shell near the northern shore.</span></div>
        <div class="opt" data-letter="D"><span class="opt-letter">D</span><span>He brought the pearl to an old woman who lived near the harbor.</span></div>
      </div>
    </div>

    <div class="qcard" data-q="3" data-type="single">
      <div class="qnum-row"><span class="qnum">Q3</span><span class="qtext">Choose the sentence that would be the main sentence of the paragraph.</span></div>
      <div class="options">
        <div class="opt" data-letter="A"><span class="opt-letter">A</span><span>Several birds flew above the trees as the girl entered the forest.</span></div>
        <div class="opt" data-letter="B"><span class="opt-letter">B</span><span>Her grandmother had warned her about the forest many times.</span></div>
        <div class="opt" data-letter="C"><span class="opt-letter">C</span><span>The girl carried a small lantern to light her way.</span></div>
        <div class="opt" data-letter="D"><span class="opt-letter">D</span><span>A young girl discovered that the mysterious forest protected an ancient secret.</span></div>
      </div>
    </div>

    <div class="qcard" data-q="4" data-type="single">
      <div class="qnum-row"><span class="qnum">Q4</span><span class="qtext">Choose the sentence that would be the main sentence of the paragraph.</span></div>
      <div class="options">
        <div class="opt" data-letter="A"><span class="opt-letter">A</span><span>Farmers planted rice and vegetables in the fertile valley.</span></div>
        <div class="opt" data-letter="B"><span class="opt-letter">B</span><span>The king's selfish decision caused the fertile valley to lose its blessing.</span></div>
        <div class="opt" data-letter="C"><span class="opt-letter">C</span><span>The king owned a large garden behind his palace.</span></div>
        <div class="opt" data-letter="D"><span class="opt-letter">D</span><span>The villagers depended on the valley for their daily food.</span></div>
      </div>
    </div>

    <div class="qcard" data-q="5" data-type="single">
      <div class="qnum-row"><span class="qnum">Q5</span><span class="qtext">Choose the sentence that would be the main sentence of the paragraph.</span></div>
      <div class="options">
        <div class="opt" data-letter="A"><span class="opt-letter">A</span><span>The warrior crossed three hills before reaching the hidden cave.</span></div>
        <div class="opt" data-letter="B"><span class="opt-letter">B</span><span>He met an old woman beside a quiet waterfall.</span></div>
        <div class="opt" data-letter="C"><span class="opt-letter">C</span><span>The warrior learned that true courage meant protecting others rather than seeking glory.</span></div>
        <div class="opt" data-letter="D"><span class="opt-letter">D</span><span>The woman gave him a silver necklace before he continued his journey.</span></div>
      </div>
    </div>
  </div>

  <div class="divider">❦</div>

  <!-- PART 2 -->
  <div class="section">
    <div class="section-head">
      <div class="badge">2</div>
      <div class="section-titles">
        <h2>Identifying the Main Idea</h2>
        <p>Read each legend and choose the best main idea</p>
      </div>
    </div>

    <div class="passage">
      <p class="ptitle">Text 1 — The Legend of the Mountain Spring</p>
      <p>Long ago, a small village depended on a spring near a rocky hill. One year, the water began to disappear. A young girl named Lira followed strange footprints and found a wounded forest guardian near the spring. Instead of being afraid, she gave him food and medicine. After he recovered, the spring slowly returned to its former strength.</p>
    </div>
    <div class="qcard" data-q="6" data-type="single">
      <div class="qnum-row"><span class="qnum">Q6</span><span class="qtext">What is the main idea of the text?</span></div>
      <div class="options">
        <div class="opt" data-letter="A"><span class="opt-letter">A</span><span>A village became wealthy after discovering a hidden spring.</span></div>
        <div class="opt" data-letter="B"><span class="opt-letter">B</span><span>A young girl helped a wounded guardian and restored the village's water source.</span></div>
        <div class="opt" data-letter="C"><span class="opt-letter">C</span><span>Hunters protected a forest guardian from dangerous animals.</span></div>
        <div class="opt" data-letter="D"><span class="opt-letter">D</span><span>The villagers learned how to survive without water.</span></div>
        <div class="opt" data-letter="E"><span class="opt-letter">E</span><span>A forest guardian punished the people near the mountain.</span></div>
      </div>
    </div>

    <div class="passage">
      <p class="ptitle">Text 2 — The Legend of the Silver Bird</p>
      <p>In an old coastal kingdom, people believed that a silver bird appeared before dangerous storms. One evening, a fisherman named Arven saw the bird flying low above the waves. He warned the villagers and asked them to move their boats. Some fishermen laughed at him, but a powerful storm struck several hours later. Because of Arven's warning, many boats and belongings were moved to safer places.</p>
    </div>
    <div class="qcard" data-q="7" data-type="single">
      <div class="qnum-row"><span class="qnum">Q7</span><span class="qtext">What is the main idea of the text?</span></div>
      <div class="options">
        <div class="opt" data-letter="A"><span class="opt-letter">A</span><span>A fisherman discovered a new island near the kingdom.</span></div>
        <div class="opt" data-letter="B"><span class="opt-letter">B</span><span>A silver bird attacked fishermen near the coast.</span></div>
        <div class="opt" data-letter="C"><span class="opt-letter">C</span><span>A fisherman trusted a mysterious warning and helped his community prepare for a storm.</span></div>
        <div class="opt" data-letter="D"><span class="opt-letter">D</span><span>Older fishermen taught Arven how to predict storms.</span></div>
        <div class="opt" data-letter="E"><span class="opt-letter">E</span><span>The coastal kingdom became famous for its silver birds.</span></div>
      </div>
    </div>

    <div class="passage">
      <p class="ptitle">Text 3 — The Legend of the Sharing Bridge</p>
      <p>According to an old legend, a giant built a stone bridge to help travelers cross a deep ravine. He did not ask for gold in return. Instead, he asked travelers to leave a small piece of bread for anyone who might be hungry. After the giant disappeared, the villagers continued the tradition and taught it to their children.</p>
    </div>
    <div class="qcard" data-q="8" data-type="single">
      <div class="qnum-row"><span class="qnum">Q8</span><span class="qtext">What is the main idea of the text?</span></div>
      <div class="options">
        <div class="opt" data-letter="A"><span class="opt-letter">A</span><span>A giant destroyed a bridge after becoming angry with travelers.</span></div>
        <div class="opt" data-letter="B"><span class="opt-letter">B</span><span>Travelers paid a giant with bread to cross a dangerous bridge.</span></div>
        <div class="opt" data-letter="C"><span class="opt-letter">C</span><span>Villagers built a new road after the giant disappeared.</span></div>
        <div class="opt" data-letter="D"><span class="opt-letter">D</span><span>A giant created a tradition of sharing food that continued after his disappearance.</span></div>
        <div class="opt" data-letter="E"><span class="opt-letter">E</span><span>Travelers avoided the valley because they feared the giant.</span></div>
      </div>
    </div>

    <div class="passage">
      <p class="ptitle">Text 4 — The Legend of the White Flower</p>
      <p>Many generations ago, a village stood beside a lake. The villagers often threw rubbish into the water until it became dark and muddy. An old farmer decided to clean the lake by himself. His actions inspired the villagers to help him. When the water became clear again, a strange white flower appeared on its surface, which the villagers believed was a sign of forgiveness.</p>
    </div>
    <div class="qcard" data-q="9" data-type="single">
      <div class="qnum-row"><span class="qnum">Q9</span><span class="qtext">What is the main idea of the text?</span></div>
      <div class="options">
        <div class="opt" data-letter="A"><span class="opt-letter">A</span><span>A mysterious flower destroyed a polluted lake.</span></div>
        <div class="opt" data-letter="B"><span class="opt-letter">B</span><span>An old farmer inspired the villagers to restore a neglected lake.</span></div>
        <div class="opt" data-letter="C"><span class="opt-letter">C</span><span>The villagers discovered valuable objects under the lake.</span></div>
        <div class="opt" data-letter="D"><span class="opt-letter">D</span><span>A lake spirit forced the villagers to leave their homes.</span></div>
        <div class="opt" data-letter="E"><span class="opt-letter">E</span><span>Farmers learned how to grow flowers in polluted water.</span></div>
      </div>
    </div>

    <div class="passage">
      <p class="ptitle">Text 5 — The Legend of the Helpful Wolf</p>
      <p>A young royal messenger named Saren had to deliver an important letter through a dangerous forest. On the way, he found an injured wolf caught in a trap and freed it, even though this might delay his mission. Later, Saren became lost in the forest. The same wolf appeared and led him toward a familiar path. Saren eventually reached the castle and delivered the letter before sunrise.</p>
    </div>
    <div class="qcard" data-q="10" data-type="single">
      <div class="qnum-row"><span class="qnum">Q10</span><span class="qtext">What is the main idea of the text?</span></div>
      <div class="options">
        <div class="opt" data-letter="A"><span class="opt-letter">A</span><span>A wolf prevented a royal messenger from delivering an important letter.</span></div>
        <div class="opt" data-letter="B"><span class="opt-letter">B</span><span>A messenger became lost because he entered a forbidden forest.</span></div>
        <div class="opt" data-letter="C"><span class="opt-letter">C</span><span>A messenger's kindness to an injured wolf was later returned.</span></div>
        <div class="opt" data-letter="D"><span class="opt-letter">D</span><span>A king ordered his messenger to capture a dangerous wolf.</span></div>
        <div class="opt" data-letter="E"><span class="opt-letter">E</span><span>A hunter helped a messenger find his way through the forest.</span></div>
      </div>
    </div>
  </div>

  <div class="divider">❦</div>

  <!-- PART 3 -->
  <div class="section">
    <div class="section-head">
      <div class="badge">3</div>
      <div class="section-titles">
        <h2>Textual &amp; Inferential Information</h2>
        <p>Answer directly from the text, or read between the lines</p>
      </div>
    </div>

    <div class="passage">
      <p class="ptitle">Text A — The Legend of the Whispering Bamboo</p>
      <p>Long ago, a farming village stood near a large bamboo forest. The villagers often heard soft whispers coming from the bamboo at night, but nobody knew where they came from. One evening, a farmer named Damar entered the forest after his youngest son failed to return home. Deep inside the forest, Damar found an old bamboo tree with a small opening in its trunk. From inside, he heard his son crying for help. The boy had fallen into a narrow hollow beneath the roots and could not climb out. Damar cut several bamboo poles and used them to help his son escape. After they returned home safely, the villagers began treating the bamboo forest with greater respect. They believed the forest had warned Damar by making the bamboo whisper.</p>
    </div>
    <div class="qcard" data-q="11" data-type="single">
      <div class="qnum-row"><span class="qnum">Q11</span><span class="qtext">Why did Damar enter the bamboo forest?</span></div>
      <div class="options">
        <div class="opt" data-letter="A"><span class="opt-letter">A</span><span>He wanted to collect bamboo for his house.</span></div>
        <div class="opt" data-letter="B"><span class="opt-letter">B</span><span>He wanted to search for his missing son.</span></div>
        <div class="opt" data-letter="C"><span class="opt-letter">C</span><span>He wanted to discover the source of the whispers.</span></div>
        <div class="opt" data-letter="D"><span class="opt-letter">D</span><span>He wanted to hunt animals in the forest.</span></div>
        <div class="opt" data-letter="E"><span class="opt-letter">E</span><span>He wanted to build a bridge across the forest.</span></div>
      </div>
    </div>
    <div class="qcard" data-q="12" data-type="single">
      <div class="qnum-row"><span class="qnum">Q12</span><span class="qtext">Where did Damar find his son?</span></div>
      <div class="options">
        <div class="opt" data-letter="A"><span class="opt-letter">A</span><span>Beside a river near the forest.</span></div>
        <div class="opt" data-letter="B"><span class="opt-letter">B</span><span>Inside an abandoned village house.</span></div>
        <div class="opt" data-letter="C"><span class="opt-letter">C</span><span>Under the roots of an old bamboo tree.</span></div>
        <div class="opt" data-letter="D"><span class="opt-letter">D</span><span>Behind a large rock outside the forest.</span></div>
        <div class="opt" data-letter="E"><span class="opt-letter">E</span><span>Inside a small cave near the village.</span></div>
      </div>
    </div>
    <div class="qcard" data-q="13" data-type="single">
      <div class="qnum-row"><span class="qnum">Q13</span><span class="qtext">What did Damar use to help his son escape?</span></div>
      <div class="options">
        <div class="opt" data-letter="A"><span class="opt-letter">A</span><span>A long piece of rope.</span></div>
        <div class="opt" data-letter="B"><span class="opt-letter">B</span><span>A wooden ladder.</span></div>
        <div class="opt" data-letter="C"><span class="opt-letter">C</span><span>Several bamboo poles.</span></div>
        <div class="opt" data-letter="D"><span class="opt-letter">D</span><span>A fishing net.</span></div>
        <div class="opt" data-letter="E"><span class="opt-letter">E</span><span>A metal chain.</span></div>
      </div>
    </div>

    <div class="passage">
      <p class="ptitle">Text B — The Legend of the Moonlit Deer</p>
      <p>In a quiet kingdom surrounded by hills, a white deer appeared only during nights when the moon was full. According to an old story, the deer belonged to a guardian spirit who watched over travelers. One night, a young merchant named Tavin lost his way while returning from a distant market. He followed the white deer through a narrow valley until he reached a small village. The villagers welcomed him and gave him a place to rest. The next morning, Tavin discovered that the road he had originally planned to take had been destroyed by a landslide during the night. From that moment, Tavin believed that the mysterious deer had not appeared by accident.</p>
    </div>
    <div class="qcard" data-q="14" data-type="single">
      <div class="qnum-row"><span class="qnum">Q14</span><span class="qtext">What can be inferred about the white deer?</span></div>
      <div class="options">
        <div class="opt" data-letter="A"><span class="opt-letter">A</span><span>It probably helped travelers avoid danger.</span></div>
        <div class="opt" data-letter="B"><span class="opt-letter">B</span><span>It usually lived inside the village.</span></div>
        <div class="opt" data-letter="C"><span class="opt-letter">C</span><span>It was probably owned by Tavin.</span></div>
        <div class="opt" data-letter="D"><span class="opt-letter">D</span><span>It appeared every night throughout the year.</span></div>
        <div class="opt" data-letter="E"><span class="opt-letter">E</span><span>It wanted to lead travelers toward dangerous places.</span></div>
      </div>
    </div>
    <div class="qcard" data-q="15" data-type="single">
      <div class="qnum-row"><span class="qnum">Q15</span><span class="qtext">Why did Tavin believe the deer had appeared for a reason?</span></div>
      <div class="options">
        <div class="opt" data-letter="A"><span class="opt-letter">A</span><span>The villagers told him that they owned the deer.</span></div>
        <div class="opt" data-letter="B"><span class="opt-letter">B</span><span>The deer led him away from a road that was later destroyed.</span></div>
        <div class="opt" data-letter="C"><span class="opt-letter">C</span><span>The deer followed him from the distant market.</span></div>
        <div class="opt" data-letter="D"><span class="opt-letter">D</span><span>The deer warned him about the landslide directly.</span></div>
        <div class="opt" data-letter="E"><span class="opt-letter">E</span><span>The deer brought him safely back to the kingdom.</span></div>
      </div>
    </div>
  </div>

  <div class="divider">❦</div>

  <!-- PART 4 -->
  <div class="section">
    <div class="section-head">
      <div class="badge">4</div>
      <div class="section-titles">
        <h2>Multiple Choice, Multiple Answers</h2>
        <p>More than one option may be correct</p>
      </div>
    </div>
    <div class="section-note">Choose ALL correct answers for each question.</div>

    <div class="passage">
      <p class="ptitle">Text A — The Legend of the Singing Stone</p>
      <p>A long time ago, a village stood at the foot of a lonely mountain. Near the village was a large black stone. People believed that the stone could sing whenever someone in the village acted with honesty. One day, a poor woodcutter found a pouch of gold beside the road. Although he needed money, he brought the pouch to the village chief. That evening, the black stone produced a beautiful sound for the first time in many years. The villagers realized that the stone's song was a reminder that honesty could bring happiness to the whole community.</p>
    </div>
    <div class="qcard" data-q="16" data-type="multi">
      <div class="qnum-row"><span class="qnum">Q16</span><span class="qtext">Which statements are supported by the text?</span></div>
      <div class="options">
        <div class="opt multi" data-letter="A"><span class="opt-letter">A</span><span>The woodcutter found a pouch of gold.</span></div>
        <div class="opt multi" data-letter="B"><span class="opt-letter">B</span><span>The woodcutter kept the gold for himself.</span></div>
        <div class="opt multi" data-letter="C"><span class="opt-letter">C</span><span>The black stone was associated with honesty.</span></div>
        <div class="opt multi" data-letter="D"><span class="opt-letter">D</span><span>The villagers had never heard the stone sing before.</span></div>
      </div>
    </div>
    <div class="qcard" data-q="17" data-type="multi">
      <div class="qnum-row"><span class="qnum">Q17</span><span class="qtext">What lessons can be learned from the legend?</span></div>
      <div class="options">
        <div class="opt multi" data-letter="A"><span class="opt-letter">A</span><span>Honesty can benefit more than one person.</span></div>
        <div class="opt multi" data-letter="B"><span class="opt-letter">B</span><span>Wealth is always more important than honesty.</span></div>
        <div class="opt multi" data-letter="C"><span class="opt-letter">C</span><span>A good action can inspire a community.</span></div>
        <div class="opt multi" data-letter="D"><span class="opt-letter">D</span><span>People should keep valuable objects they find.</span></div>
      </div>
    </div>
    <div class="qcard" data-q="18" data-type="multi">
      <div class="qnum-row"><span class="qnum">Q18</span><span class="qtext">Which events happened in the story?</span></div>
      <div class="options">
        <div class="opt multi" data-letter="A"><span class="opt-letter">A</span><span>A woodcutter discovered gold beside a road.</span></div>
        <div class="opt multi" data-letter="B"><span class="opt-letter">B</span><span>The woodcutter returned the gold to the village chief.</span></div>
        <div class="opt multi" data-letter="C"><span class="opt-letter">C</span><span>The villagers destroyed the black stone.</span></div>
        <div class="opt multi" data-letter="D"><span class="opt-letter">D</span><span>The stone produced a beautiful sound.</span></div>
      </div>
    </div>

    <div class="passage">
      <p class="ptitle">Text B — The Legend of the Hidden Garden</p>
      <p>Behind a forgotten palace was a garden that could not be entered by ordinary people. According to the legend, the garden appeared only to someone who had helped another person without expecting a reward. A young servant named Mira once found an elderly traveler sitting beside a road. The traveler was tired and had no food, so Mira gave him her own lunch. She did not know that he was actually the guardian of the palace garden. The following morning, Mira discovered a beautiful garden behind the palace. The guardian explained that the garden appeared because Mira had shown kindness without asking for anything in return.</p>
    </div>
    <div class="qcard" data-q="19" data-type="multi">
      <div class="qnum-row"><span class="qnum">Q19</span><span class="qtext">Which statements are true according to the text?</span></div>
      <div class="options">
        <div class="opt multi" data-letter="A"><span class="opt-letter">A</span><span>Mira helped an elderly traveler.</span></div>
        <div class="opt multi" data-letter="B"><span class="opt-letter">B</span><span>Mira gave the traveler her own lunch.</span></div>
        <div class="opt multi" data-letter="C"><span class="opt-letter">C</span><span>Mira expected a valuable reward.</span></div>
        <div class="opt multi" data-letter="D"><span class="opt-letter">D</span><span>The traveler was the guardian of the garden.</span></div>
      </div>
    </div>
    <div class="qcard" data-q="20" data-type="multi">
      <div class="qnum-row"><span class="qnum">Q20</span><span class="qtext">Which ideas are implied by the legend?</span></div>
      <div class="options">
        <div class="opt multi" data-letter="A"><span class="opt-letter">A</span><span>Genuine kindness does not always require a reward.</span></div>
        <div class="opt multi" data-letter="B"><span class="opt-letter">B</span><span>Mira's action demonstrated compassion.</span></div>
        <div class="opt multi" data-letter="C"><span class="opt-letter">C</span><span>The garden appeared because Mira demanded to enter it.</span></div>
        <div class="opt multi" data-letter="D"><span class="opt-letter">D</span><span>The traveler secretly tested Mira's character.</span></div>
      </div>
    </div>
  </div>

  <div class="divider">❦</div>

  <!-- PART 5 -->
  <div class="section">
    <div class="section-head">
      <div class="badge">5</div>
      <div class="section-titles">
        <h2>True or False</h2>
        <p>Decide whether each statement matches the legend</p>
      </div>
    </div>

    <div class="passage">
      <p class="ptitle">Text 1 — The Legend of the Blue Lantern</p>
      <p>Long ago, a village was surrounded by thick forests. At night, travelers often became lost because there were no lights along the narrow paths. A young woman named Elara made a blue lantern from an old glass bottle. Every evening, she placed it near the village entrance so travelers could find their way home. One stormy night, the lantern was blown away by strong wind. The villagers searched for it together and finally found it near a dangerous cliff. After that, they built a stronger shelter for the lantern and took turns protecting it.</p>
    </div>
    <div class="qcard" data-q="21" data-type="tf">
      <div class="qnum-row"><span class="qnum">Q21</span><span class="qtext">Elara made the blue lantern from an old glass bottle.</span></div>
      <div class="tf-row"><button class="tf-btn true">TRUE</button><button class="tf-btn false">FALSE</button></div>
    </div>
    <div class="qcard" data-q="22" data-type="tf">
      <div class="qnum-row"><span class="qnum">Q22</span><span class="qtext">The villagers ignored the lantern after it was blown away.</span></div>
      <div class="tf-row"><button class="tf-btn true">TRUE</button><button class="tf-btn false">FALSE</button></div>
    </div>

    <div class="passage">
      <p class="ptitle">Text 2 — The Legend of the Silent River</p>
      <p>A river once flowed through a peaceful farming village. The villagers believed that the river became silent whenever someone lied beside it. One afternoon, a merchant accused a farmer of stealing his horse. The farmer insisted that he was innocent. When both men stood beside the river, the water suddenly became completely quiet. The villagers investigated the matter and discovered that the merchant had actually lost his horse in another village. He later admitted that he had wrongly accused the farmer.</p>
    </div>
    <div class="qcard" data-q="23" data-type="tf">
      <div class="qnum-row"><span class="qnum">Q23</span><span class="qtext">The villagers believed that the river could become silent when someone lied.</span></div>
      <div class="tf-row"><button class="tf-btn true">TRUE</button><button class="tf-btn false">FALSE</button></div>
    </div>
    <div class="qcard" data-q="24" data-type="tf">
      <div class="qnum-row"><span class="qnum">Q24</span><span class="qtext">The investigation proved that the farmer had stolen the merchant's horse.</span></div>
      <div class="tf-row"><button class="tf-btn true">TRUE</button><button class="tf-btn false">FALSE</button></div>
    </div>

    <div class="passage">
      <p class="ptitle">Text 3 — The Legend of the Golden Seeds</p>
      <p>In an old farming village, a poor girl named Nara received three golden seeds from a mysterious traveler. The traveler told her to plant them only if she was willing to share the harvest with others. Nara planted the seeds beside her small house. A few weeks later, golden plants grew and produced enough grain to feed many families. Nara kept only what her family needed and distributed the rest among the villagers. The golden plants disappeared after the harvest, but the villagers remembered Nara's generosity for many years.</p>
    </div>
    <div class="qcard" data-q="25" data-type="tf">
      <div class="qnum-row"><span class="qnum">Q25</span><span class="qtext">Nara was instructed to share the harvest if she planted the seeds.</span></div>
      <div class="tf-row"><button class="tf-btn true">TRUE</button><button class="tf-btn false">FALSE</button></div>
    </div>
    <div class="qcard" data-q="26" data-type="tf">
      <div class="qnum-row"><span class="qnum">Q26</span><span class="qtext">Nara kept all the grain for her own family.</span></div>
      <div class="tf-row"><button class="tf-btn true">TRUE</button><button class="tf-btn false">FALSE</button></div>
    </div>

    <div class="passage">
      <p class="ptitle">Text 4 — The Legend of the Stone Fisherman</p>
      <p>According to an old coastal legend, a fisherman named Joran lived beside a quiet bay. He was famous for helping other fishermen during storms. One day, a terrible storm approached the village while several boats were still at sea. Joran went out to guide the boats back to shore. He managed to save everyone, but his own boat was destroyed by the waves. The next morning, the villagers found a strange stone shaped like a fisherman near the bay. They believed it represented Joran's courage and built a small monument beside it.</p>
    </div>
    <div class="qcard" data-q="27" data-type="tf">
      <div class="qnum-row"><span class="qnum">Q27</span><span class="qtext">Joran went to sea because he wanted to catch more fish before the storm.</span></div>
      <div class="tf-row"><button class="tf-btn true">TRUE</button><button class="tf-btn false">FALSE</button></div>
    </div>
    <div class="qcard" data-q="28" data-type="tf">
      <div class="qnum-row"><span class="qnum">Q28</span><span class="qtext">The villagers believed that the strange stone represented Joran's courage.</span></div>
      <div class="tf-row"><button class="tf-btn true">TRUE</button><button class="tf-btn false">FALSE</button></div>
    </div>

    <div class="passage">
      <p class="ptitle">Text 5 — The Legend of the Red Mountain</p>
      <p>Many years ago, a village stood beneath a mountain covered with red flowers. The villagers believed that the flowers protected the mountain from fire. One dry season, a careless traveler threw a burning piece of wood into the forest. A fire quickly spread toward the mountain. The villagers worked together to stop the flames and protect the flowers. After several days, the fire disappeared. According to the legend, the red flowers became brighter because they had witnessed the villagers' courage and cooperation.</p>
    </div>
    <div class="qcard" data-q="29" data-type="tf">
      <div class="qnum-row"><span class="qnum">Q29</span><span class="qtext">The villagers worked together to protect the mountain from the fire.</span></div>
      <div class="tf-row"><button class="tf-btn true">TRUE</button><button class="tf-btn false">FALSE</button></div>
    </div>
    <div class="qcard" data-q="30" data-type="tf">
      <div class="qnum-row"><span class="qnum">Q30</span><span class="qtext">The fire was caused by a lightning strike during a storm.</span></div>
      <div class="tf-row"><button class="tf-btn true">TRUE</button><button class="tf-btn false">FALSE</button></div>
    </div>
  </div>

  <div class="end-note">❦ End of the tale — good luck. ❦</div>
  <div class="action-row">
    <button class="submit-btn" id="submitBtn">✔ Submit Jawaban</button>
    <button class="reset-btn" id="resetBtn">Clear all answers</button>
  </div>
  <div class="submit-hint">
    Isi Nama &amp; Kelas dulu, lalu tekan <b>Submit Jawaban</b>. Ringkasan jawaban akan otomatis terkirim ke Google Form.
  </div>
  <div class="submit-status" id="submitStatus"></div>

</div>

<!-- Hidden iframe target so the Google Form POST doesn't navigate away from the quiz -->
<iframe name="hidden_gform_target" id="hidden_gform_target" style="display:none;"></iframe>

<script>
  const TOTAL = 30;
  const answered = new Set();

  function updateProgress(){
    document.getElementById('progLabel').textContent = answered.size + ' / ' + TOTAL + ' answered';
    document.getElementById('progFill').style.width = (answered.size/TOTAL*100) + '%';
  }

  document.querySelectorAll('.qcard').forEach(card=>{
    const qid = card.dataset.q;
    const type = card.dataset.type;

    if(type === 'single'){
      card.querySelectorAll('.opt').forEach(opt=>{
        opt.addEventListener('click', ()=>{
          card.querySelectorAll('.opt').forEach(o=>o.classList.remove('selected'));
          opt.classList.add('selected');
          answered.add(qid);
          updateProgress();
        });
      });
    } else if(type === 'multi'){
      card.querySelectorAll('.opt').forEach(opt=>{
        opt.addEventListener('click', ()=>{
          opt.classList.toggle('selected');
          const anySelected = card.querySelector('.opt.selected');
          if(anySelected) answered.add(qid); else answered.delete(qid);
          updateProgress();
        });
      });
    } else if(type === 'tf'){
      card.querySelectorAll('.tf-btn').forEach(btn=>{
        btn.addEventListener('click', ()=>{
          card.querySelectorAll('.tf-btn').forEach(b=>b.classList.remove('selected'));
          btn.classList.add('selected');
          answered.add(qid);
          updateProgress();
        });
      });
    }
  });

  document.getElementById('resetBtn').addEventListener('click', ()=>{
    document.querySelectorAll('.opt.selected, .tf-btn.selected').forEach(el=>el.classList.remove('selected'));
    answered.clear();
    updateProgress();
  });

  // ===== Answer summary + Google Form submission =====
  const GOOGLE_FORM_ACTION = 'https://docs.google.com/forms/d/e/1FAIpQLSegeGmskBsfPe7C0aP6UBacnL2qFdMCYE2kut3DtbNS1AwR2w/formResponse';
  const GOOGLE_FORM_ENTRY_ID = 'entry.48174494'; // "jawaban" field

  function collectAnswers(){
    const data = {};
    data.name = document.getElementById('studentName').value.trim();
    data.kelas = document.getElementById('studentClass').value.trim();

    document.querySelectorAll('.qcard').forEach(card=>{
      const qid = card.dataset.q;
      const type = card.dataset.type;
      let answerStr = '-';

      if(type === 'single'){
        const sel = card.querySelector('.opt.selected');
        if(sel) answerStr = sel.dataset.letter;
      } else if(type === 'multi'){
        const sels = card.querySelectorAll('.opt.selected');
        if(sels.length) answerStr = Array.from(sels).map(o=>o.dataset.letter).join(', ');
      } else if(type === 'tf'){
        const sel = card.querySelector('.tf-btn.selected');
        if(sel) answerStr = sel.classList.contains('true') ? 'TRUE' : 'FALSE';
      }
      data[qid] = answerStr;
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
    lines.push('(' + answered.size + '/' + TOTAL + ' soal terjawab)');
    return lines.join('\n');
  }

  function submitToGoogleForm(summaryText){
    return new Promise((resolve)=>{
      const form = document.createElement('form');
      form.action = GOOGLE_FORM_ACTION;
      form.method = 'POST';
      form.target = 'hidden_gform_target';
      form.style.display = 'none';

      const input = document.createElement('input');
      input.type = 'hidden';
      input.name = GOOGLE_FORM_ENTRY_ID;
      input.value = summaryText;
      form.appendChild(input);

      document.body.appendChild(form);

      const iframe = document.getElementById('hidden_gform_target');
      const onLoad = () => {
        iframe.removeEventListener('load', onLoad);
        document.body.removeChild(form);
        resolve(true);
      };
      iframe.addEventListener('load', onLoad);

      form.submit();

      // Fallback in case the iframe load event doesn't fire
      setTimeout(()=>{
        if(document.body.contains(form)){
          iframe.removeEventListener('load', onLoad);
          document.body.removeChild(form);
          resolve(true);
        }
      }, 4000);
    });
  }

  async function submitAnswers(){
    const statusEl = document.getElementById('submitStatus');
    const btn = document.getElementById('submitBtn');
    const name = document.getElementById('studentName').value.trim();

    if(!name){
      statusEl.textContent = 'Isi nama terlebih dahulu sebelum submit.';
      statusEl.className = 'submit-status show warn';
      return;
    }
    if(answered.size < TOTAL){
      const proceed = confirm('Baru ' + answered.size + ' dari ' + TOTAL + ' soal terjawab. Tetap submit?');
      if(!proceed) return;
    }

    btn.disabled = true;
    btn.textContent = 'Mengirim…';

    const summary = buildSummaryText();

    try{
      await submitToGoogleForm(summary);
      statusEl.textContent = '✔ Jawaban berhasil dikirim ke Google Form. Terima kasih!';
      statusEl.className = 'submit-status show ok';
    }catch(e){
      statusEl.textContent = 'Terjadi kesalahan saat mengirim. Coba tekan Submit lagi.';
      statusEl.className = 'submit-status show warn';
    }

    btn.disabled = false;
    btn.textContent = '✔ Submit Jawaban';
  }

  document.getElementById('submitBtn').addEventListener('click', submitAnswers);

  // Prevent copying, right-click context menu, and text selection
  document.addEventListener('contextmenu', e => e.preventDefault());
  document.addEventListener('copy', e => e.preventDefault());
  document.addEventListener('cut', e => e.preventDefault());
  document.addEventListener('selectstart', e => e.preventDefault());
  document.addEventListener('dragstart', e => e.preventDefault());
  document.addEventListener('keydown', e => {
    // Block common copy/select/print/save shortcuts
    if ((e.ctrlKey || e.metaKey) && ['c','x','a','p','s','u'].includes(e.key.toLowerCase())) {
      e.preventDefault();
    }
  });
</script>

</body>
</html>
