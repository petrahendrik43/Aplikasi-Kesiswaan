<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Mading Kesiswaan — SMP Negeri 71 Maluku Tengah</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Fredoka:wght@500;600;700&family=Caveat:wght@600;700&family=Plus+Jakarta+Sans:wght@400;500;600;700;800&display=swap" rel="stylesheet">
<style>
  :root{
    --paper:#FFF7EA;
    --paper-deep:#FCEFD8;
    --ink:#20303D;
    --ink-soft:#5A6B78;
    --coral:#FF6A4D;
    --coral-deep:#E4502F;
    --teal:#12938A;
    --teal-deep:#0B6E67;
    --gold:#FFC23C;
    --lilac:#8B6FE8;
    --line: rgba(32,48,61,0.12);
    --shadow: 0 10px 24px rgba(32,48,61,0.14);
  }
  *{box-sizing:border-box;}
  html{scroll-behavior:smooth;}
  body{
    margin:0;
    background:var(--paper);
    color:var(--ink);
    font-family:'Plus Jakarta Sans', sans-serif;
    background-image: radial-gradient(circle at 1px 1px, rgba(32,48,61,0.06) 1px, transparent 0);
    background-size: 22px 22px;
  }
  h1,h2,h3,.display{font-family:'Fredoka', sans-serif; font-weight:700; margin:0;}
  .hand{font-family:'Caveat', cursive; font-weight:700;}
  a{color:inherit; text-decoration:none;}
  .hidden{display:none !important;}
  .wrap{max-width:1120px; margin:0 auto; padding:0 24px;}
  .eyebrow{
    font-family:'Fredoka', sans-serif; font-size:13px; letter-spacing:.08em; text-transform:uppercase;
    color:var(--coral-deep); font-weight:600; display:inline-flex; align-items:center; gap:8px;
  }
  .eyebrow::before{content:""; width:8px; height:8px; border-radius:50%; background:var(--coral); display:inline-block;}

  /* ===== Navbar ===== */
  header{position:sticky; top:0; z-index:50; background:var(--ink); border-bottom:4px solid var(--gold);}
  .nav{display:flex; align-items:center; justify-content:space-between; padding:14px 24px; max-width:1120px; margin:0 auto;}
  .brand{display:flex; align-items:center; gap:10px;}
  .brand-badge{
    width:38px; height:38px; border-radius:10px; background:var(--coral); display:flex; align-items:center; justify-content:center;
    font-family:'Fredoka'; font-weight:700; color:#fff; font-size:18px; transform:rotate(-6deg); box-shadow: 0 4px 0 var(--coral-deep);
  }
  .brand-text{color:#fff; font-family:'Fredoka'; font-weight:600; font-size:16px; line-height:1.15;}
  .brand-text small{display:block; color:#B9C3CC; font-size:11px; font-weight:400; font-family:'Plus Jakarta Sans';}
  nav.links{display:flex; gap:22px; align-items:center;}
  nav.links a{color:#E8ECEF; font-size:14.5px; font-weight:600; padding:6px 2px;}
  nav.links a:hover{color:var(--gold);}
  .admin-link{font-family:'Fredoka'; font-size:13px !important; font-weight:600; color:var(--gold) !important; border:1.5px solid rgba(255,194,60,.5); padding:7px 14px; border-radius:9px;}
  #menu-btn{display:none; background:none; border:none; color:#fff; font-size:26px; cursor:pointer;}
  .mobile-menu{display:none; flex-direction:column; background:var(--ink); padding:0 24px 16px;}
  .mobile-menu a{color:#E8ECEF; padding:10px 0; border-top:1px solid rgba(255,255,255,.1); font-weight:600;}
  .mobile-menu.open{display:flex;}

  /* ===== Hero ===== */
  .hero{padding:72px 0 56px; position:relative; overflow:hidden;}
  .hero-grid{display:grid; grid-template-columns:1.15fr .85fr; gap:48px; align-items:center;}
  .hero h1{font-size:44px; line-height:1.12; margin:14px 0 18px; color:var(--ink);}
  .hero h1 span{color:var(--coral);}
  .hero p.lede{font-size:17px; color:var(--ink-soft); max-width:480px; margin-bottom:28px;}
  .cta-row{display:flex; gap:14px; flex-wrap:wrap;}
  .btn{font-family:'Fredoka'; font-weight:600; font-size:14.5px; padding:13px 22px; border-radius:12px; cursor:pointer; border:none; display:inline-flex; align-items:center; gap:8px;}
  .btn-primary{background:var(--coral); color:#fff; box-shadow:0 5px 0 var(--coral-deep);}
  .btn-primary:hover{transform:translateY(2px); box-shadow:0 3px 0 var(--coral-deep);}
  .btn-ghost{background:#fff; color:var(--ink); border:2px solid var(--ink); box-shadow:0 5px 0 var(--ink);}
  .btn-ghost:hover{transform:translateY(2px); box-shadow:0 3px 0 var(--ink);}

  .stat-pins{display:flex; gap:16px; margin-top:38px; flex-wrap:wrap;}
  .stat-pin{position:relative; background:#fff; border-radius:14px; padding:16px 18px 14px; box-shadow:var(--shadow); min-width:118px; transform:rotate(-2deg);}
  .stat-pin:nth-child(2){transform:rotate(2deg);}
  .stat-pin:nth-child(3){transform:rotate(-1.5deg);}
  .stat-pin .num{font-family:'Fredoka'; font-weight:700; font-size:26px; color:var(--teal-deep);}
  .stat-pin .lbl{font-size:12px; color:var(--ink-soft); font-weight:600;}

  .hero-board{position:relative; background:var(--paper-deep); border-radius:22px; padding:26px; box-shadow: inset 0 0 0 2px rgba(32,48,61,0.08); min-height:220px;}
  .note{background:#fff; border-radius:12px; padding:16px; box-shadow:var(--shadow); position:relative; margin-bottom:16px;}
  .note:last-child{margin-bottom:0;}
  .note.rot-l{transform:rotate(-3deg);}
  .note.rot-r{transform:rotate(2.5deg); margin-left:34px;}
  .note .hand{font-size:20px; color:var(--coral-deep);}
  .note p{margin:4px 0 0; font-size:13.5px; color:var(--ink-soft);}

  section{padding:64px 0;}
  .sec-head{max-width:640px; margin-bottom:40px;}
  .sec-head h2{font-size:32px; margin-top:10px;}
  .sec-head p{color:var(--ink-soft); font-size:15.5px; margin-top:10px;}

  /* ===== OSIS ===== */
  .osis-wrap{background:var(--ink); border-radius:24px; padding:44px; color:#fff; position:relative;}
  .osis-wrap .sec-head p, .osis-wrap .sec-head .eyebrow{color:#C7D0D7;}
  .osis-wrap .sec-head h2{color:#fff;}
  .org-chart{display:flex; flex-direction:column; align-items:center; gap:14px;}
  .org-row{display:flex; gap:16px; flex-wrap:wrap; justify-content:center;}
  .org-card{background:#28394A; border-radius:12px; padding:14px 20px; text-align:center; border:1px solid rgba(255,255,255,.08); min-width:150px;}
  .org-card.lead{background:var(--coral); min-width:200px;}
  .org-card .role{font-family:'Fredoka'; font-weight:600; font-size:13.5px; color:var(--gold);}
  .org-card.lead .role{color:#FFE3D9;}
  .org-card .name{font-size:13.5px; color:#E8ECEF; margin-top:2px;}
  .connector{width:2px; height:18px; background:rgba(255,255,255,.25);}

  .ekskul-grid{display:grid; grid-template-columns:repeat(4, 1fr); gap:18px; margin-top:8px;}
  .ekskul-card{background:#fff; border-radius:16px; padding:22px 18px; box-shadow:var(--shadow); text-align:center; transition:transform .18s ease;}
  .ekskul-card:hover{transform:translateY(-4px);}
  .ekskul-card .ico{width:52px; height:52px; border-radius:14px; display:flex; align-items:center; justify-content:center; margin:0 auto 12px; font-size:24px;}
  .ekskul-card h3{font-size:15px;}
  .ekskul-card p{font-size:12.5px; color:var(--ink-soft); margin-top:4px;}

  /* ===== Pengumuman ===== */
  .pengumuman-grid{display:grid; grid-template-columns:repeat(3,1fr); gap:26px 22px; margin-top:8px;}
  .pcard{background:#fff; border-radius:4px 4px 12px 12px; padding:20px 18px 22px; position:relative; box-shadow:var(--shadow); border-top:6px solid var(--coral);}
  .pcard:nth-child(3n+2){border-top-color:var(--teal);}
  .pcard:nth-child(3n){border-top-color:var(--lilac);}
  .pcard .tag{display:inline-block; font-size:11px; font-weight:700; padding:4px 10px; border-radius:999px; background:var(--paper-deep); color:var(--ink-soft); margin-bottom:10px;}
  .pcard .date{font-family:'Fredoka'; font-size:12.5px; color:var(--coral-deep); font-weight:600; position:absolute; top:18px; right:18px;}
  .pcard h3{font-size:16.5px; margin-top:2px; padding-right:70px;}
  .pcard p{font-size:13.5px; color:var(--ink-soft); margin-top:8px; line-height:1.5;}

  /* ===== Poin siswa ===== */
  .poin-panel{background:#fff; border-radius:22px; padding:32px; box-shadow:var(--shadow);}
  .poin-top{display:grid; grid-template-columns:1fr 1fr; gap:20px; margin-bottom:26px;}
  .poin-rule{border-radius:14px; padding:18px 20px; display:flex; gap:14px; align-items:flex-start;}
  .poin-rule.plus{background:#E8F7F2;}
  .poin-rule.minus{background:#FFEEEA;}
  .poin-rule .icn{font-size:22px;}
  .poin-rule h4{font-family:'Fredoka'; font-size:14.5px; margin-bottom:4px;}
  .poin-rule.plus h4{color:var(--teal-deep);}
  .poin-rule.minus h4{color:var(--coral-deep);}
  .poin-rule p{font-size:12.5px; color:var(--ink-soft); margin:0;}
  .badge-score{display:inline-flex; align-items:center; justify-content:center; min-width:44px; padding:4px 8px; border-radius:8px; font-weight:700; font-family:'Fredoka'; font-size:13px;}
  .badge-score.high{background:#E8F7F2; color:var(--teal-deep);}
  .badge-score.mid{background:#FFF3D9; color:#A5760E;}
  .badge-score.low{background:#FFEEEA; color:var(--coral-deep);}

  .login-card{max-width:420px; margin:0 auto; text-align:center; padding:10px 0 0;}
  .login-card .ico{font-size:38px; margin-bottom:8px;}
  .student-card{max-width:460px; margin:0 auto; padding:10px 0 0;}
  .student-card .top{display:flex; align-items:center; gap:16px; margin-bottom:20px;}
  .student-card .avatar{width:56px; height:56px; border-radius:14px; background:var(--paper-deep); display:flex; align-items:center; justify-content:center; font-size:26px; flex-shrink:0;}
  .student-card .stat-grid{display:grid; grid-template-columns:1fr 1fr; gap:14px; margin:20px 0;}
  .student-stat{background:var(--paper-deep); border-radius:12px; padding:16px; text-align:center;}
  .student-stat .num{font-family:'Fredoka'; font-size:24px; font-weight:700;}
  .student-stat .lbl{font-size:11.5px; color:var(--ink-soft); font-weight:600; margin-top:2px;}

  /* ===== Galeri ===== */
  .gal-grid{display:grid; grid-template-columns:repeat(4,1fr); gap:16px;}
  .gal-item{border-radius:16px; overflow:hidden; position:relative; aspect-ratio:1/1; display:flex; align-items:flex-end; padding:14px; color:#fff;}
  .gal-item span.cap{font-family:'Fredoka'; font-weight:600; font-size:13.5px; position:relative; z-index:2;}
  .gal-item::after{content:""; position:absolute; inset:0; background:linear-gradient(180deg, transparent 40%, rgba(0,0,0,.55)); z-index:1;}
  .gal-item .emoji{position:absolute; font-size:56px; opacity:.9; top:14px; left:14px; z-index:1; filter:drop-shadow(0 4px 8px rgba(0,0,0,.15));}

  /* ===== Footer ===== */
  footer{background:var(--ink); color:#E8ECEF; padding:52px 0 26px; margin-top:20px;}
  .foot-grid{display:grid; grid-template-columns:1.4fr 1fr 1fr; gap:36px; padding-bottom:34px; border-bottom:1px solid rgba(255,255,255,.1);}
  footer h4{font-family:'Fredoka'; font-size:14px; margin-bottom:14px; color:var(--gold);}
  footer p{font-size:13px; color:#B9C3CC; line-height:1.6;}
  footer ul{list-style:none; padding:0; margin:0; display:flex; flex-direction:column; gap:9px;}
  footer ul a{font-size:13.5px; color:#D6DCE1;}
  footer ul a:hover{color:var(--gold);}
  .foot-bottom{padding-top:20px; font-size:12.5px; color:#8493A0; display:flex; justify-content:space-between; flex-wrap:wrap; gap:10px;}

  /* ===== Modals ===== */
  .modal-overlay{position:fixed; inset:0; background:rgba(32,48,61,0.55); z-index:200; display:flex; align-items:center; justify-content:center; padding:20px;}
  .modal-box{background:#fff; border-radius:18px; padding:28px; width:100%; max-width:420px; box-shadow:0 20px 50px rgba(0,0,0,.25); max-height:88vh; overflow-y:auto; position:relative;}
  .modal-box h3{font-family:'Fredoka'; font-size:19px; margin-bottom:6px; padding-right:20px;}
  .modal-box .sub{font-size:13px; color:var(--ink-soft); margin-bottom:18px;}
  .modal-x{position:absolute; top:16px; right:18px; background:none; border:none; font-size:18px; cursor:pointer; color:var(--ink-soft);}
  .field{margin-bottom:14px;}
  .field label{display:block; font-size:12.5px; font-weight:700; margin-bottom:6px; color:var(--ink-soft); font-family:'Fredoka';}
  .field input, .field select, .field textarea{width:100%; padding:11px 13px; border-radius:10px; border:2px solid var(--line); font-family:'Plus Jakarta Sans'; font-size:14px; outline:none; background:#fff;}
  .field input:focus, .field select:focus, .field textarea:focus{border-color:var(--teal);}
  .field textarea{min-height:70px; resize:vertical;}
  .field-error{color:var(--coral-deep); font-size:12.5px; margin-top:8px; display:none;}
  .modal-actions{display:flex; justify-content:flex-end; gap:10px; margin-top:10px;}

  .toast{position:fixed; bottom:24px; left:50%; transform:translateX(-50%); background:var(--ink); color:#fff; padding:12px 20px; border-radius:10px; font-size:13.5px; z-index:300; box-shadow:var(--shadow); opacity:0; pointer-events:none; transition:opacity .25s ease, transform .25s ease;}
  .toast.show{opacity:1; transform:translateX(-50%) translateY(-6px);}

  /* ===== Admin Portal ===== */
  #adminPortal{min-height:100vh; background:var(--paper);}
  .admin-topbar{background:var(--ink); color:#fff; padding:16px 24px; display:flex; justify-content:space-between; align-items:center;}
  .admin-topbar .title{font-family:'Fredoka'; font-weight:600; display:flex; align-items:center; gap:10px; font-size:15px;}
  .admin-body{display:flex; min-height:calc(100vh - 62px);}
  .admin-sidebar{width:220px; background:#fff; border-right:1px solid var(--line); padding:20px 0; flex-shrink:0;}
  .admin-sidebar button{display:block; width:100%; text-align:left; padding:12px 24px; background:none; border:none; cursor:pointer; font-family:'Fredoka'; font-size:13.5px; color:var(--ink-soft); border-left:3px solid transparent;}
  .admin-sidebar button.active{color:var(--coral-deep); border-left-color:var(--coral); background:var(--paper-deep);}
  .admin-content{flex:1; padding:30px 32px; overflow-x:auto;}
  .admin-panel{display:none;}
  .admin-panel.active{display:block;}
  .admin-panel-head{display:flex; justify-content:space-between; align-items:center; margin-bottom:20px; gap:16px; flex-wrap:wrap;}
  .admin-panel-head h2{font-size:21px;}
  .admin-table-wrap{background:#fff; border-radius:14px; overflow:hidden; box-shadow:var(--shadow);}
  .admin-table-wrap table{width:100%; border-collapse:collapse; font-size:13.5px;}
  .admin-table-wrap thead th{text-align:left; font-family:'Fredoka'; font-size:12px; text-transform:uppercase; letter-spacing:.04em; color:var(--ink-soft); padding:12px 14px; border-bottom:2px solid var(--line);}
  .admin-table-wrap tbody td{padding:12px 14px; border-bottom:1px solid var(--line);}
  .admin-table-wrap tbody tr:hover{background:var(--paper-deep);}
  .row-actions{display:flex; gap:8px;}
  .row-actions button{border:none; padding:6px 10px; border-radius:7px; cursor:pointer; font-size:12px; font-weight:600;}
  .row-actions button.danger{background:#FFEEEA; color:var(--coral-deep);}
  .row-actions button.edit{background:#E3F5F2; color:var(--teal-deep);}

  #loadingOverlay{position:fixed; inset:0; background:var(--paper); z-index:500; display:flex; align-items:center; justify-content:center; font-family:'Fredoka'; color:var(--ink-soft); font-size:15px;}

  @media (max-width: 880px){
    nav.links{display:none;}
    #menu-btn{display:block;}
    .hero-grid{grid-template-columns:1fr;}
    .ekskul-grid{grid-template-columns:repeat(2,1fr);}
    .pengumuman-grid{grid-template-columns:1fr;}
    .poin-top{grid-template-columns:1fr;}
    .gal-grid{grid-template-columns:repeat(2,1fr);}
    .foot-grid{grid-template-columns:1fr; gap:24px;}
    .org-row{gap:10px;}
    .hero h1{font-size:32px;}
    .admin-body{flex-direction:column;}
    .admin-sidebar{width:100%; display:flex; overflow-x:auto; padding:8px;}
    .admin-sidebar button{white-space:nowrap; border-left:none; border-bottom:3px solid transparent;}
    .admin-sidebar button.active{border-left:none; border-bottom-color:var(--coral);}
  }

  @media (prefers-reduced-motion: reduce){
    html{scroll-behavior:auto;}
    *{transition:none !important;}
  }
</style>
</head>
<body>

<div id="loadingOverlay">Memuat data mading…</div>

<div id="site" class="hidden">

<header>
  <div class="nav">
    <div class="brand">
      <div class="brand-badge">K</div>
      <div class="brand-text">Mading Kesiswaan<small>SMP Negeri 71 Maluku Tengah</small></div>
    </div>
    <nav class="links">
      <a href="#profil">Profil</a>
      <a href="#pengumuman">Pengumuman</a>
      <a href="#poin">Poin Siswa</a>
      <a href="#galeri">Galeri</a>
      <a href="#kontak">Kontak</a>
      <a href="#" class="admin-link" onclick="openAdminLogin(); return false;">Portal Admin</a>
    </nav>
    <button id="menu-btn" aria-label="Buka menu">☰</button>
  </div>
  <div class="mobile-menu" id="mobile-menu">
    <a href="#profil">Profil</a>
    <a href="#pengumuman">Pengumuman</a>
    <a href="#poin">Poin Siswa</a>
    <a href="#galeri">Galeri</a>
    <a href="#kontak">Kontak</a>
    <a href="#" onclick="openAdminLogin(); return false;">Portal Admin</a>
  </div>
</header>

<!-- HERO -->
<section class="hero">
  <div class="wrap hero-grid">
    <div>
      <span class="eyebrow">Papan Kesiswaan Digital</span>
      <h1>Semua info OSIS, ekskul,<br>& kegiatan siswa <span>dalam satu mading.</span></h1>
      <p class="lede">Tempat resmi Bidang Kesiswaan untuk mengumumkan kegiatan, memperkenalkan pengurus OSIS &amp; ekskul, memantau poin siswa, dan mendokumentasikan momen-momen sekolah.</p>
      <div class="cta-row">
        <a href="#pengumuman" class="btn btn-primary">Lihat Pengumuman</a>
        <a href="#poin" class="btn btn-ghost">Cek Poin Siswa</a>
      </div>
      <div class="stat-pins">
        <div class="stat-pin"><div class="num" id="statEkskul">0</div><div class="lbl">Ekstrakurikuler</div></div>
        <div class="stat-pin"><div class="num" id="statOsis">0</div><div class="lbl">Pengurus OSIS</div></div>
        <div class="stat-pin"><div class="num">964</div><div class="lbl">Siswa Aktif</div></div>
      </div>
    </div>
    <div class="hero-board">
      <div id="heroNotes"></div>
    </div>
  </div>
</section>

<!-- PROFIL KESISWAAN -->
<section id="profil">
  <div class="wrap">
    <div class="osis-wrap">
      <div class="sec-head">
        <span class="eyebrow">Profil &amp; Struktur</span>
        <h2>Pengurus OSIS</h2>
        <p>Struktur inti pengurus OSIS yang menjalankan program kerja Bidang Kesiswaan sepanjang tahun ajaran.</p>
      </div>
      <div class="org-chart">
        <div class="org-card lead"><div class="role">Pembina OSIS</div><div class="name" id="osisPembinaName">-</div></div>
        <div class="connector"></div>
        <div class="org-card lead"><div class="role">Ketua OSIS</div><div class="name" id="osisKetuaName">-</div></div>
        <div class="connector"></div>
        <div class="org-row">
          <div class="org-card"><div class="role">Wakil Ketua</div><div class="name" id="osisWakilName">-</div></div>
          <div class="org-card"><div class="role">Sekretaris</div><div class="name" id="osisSekretarisName">-</div></div>
          <div class="org-card"><div class="role">Bendahara</div><div class="name" id="osisBendaharaName">-</div></div>
        </div>
        <div class="connector"></div>
        <div class="org-row" id="osisSeksiRow"></div>
      </div>
    </div>

    <div class="sec-head" style="margin-top:56px;">
      <span class="eyebrow">Ekstrakurikuler</span>
      <h2>Kembangkan Minat &amp; Bakat</h2>
      <p>Setiap siswa wajib mengikuti minimal satu ekskul. Berikut pilihan yang tersedia semester ini.</p>
    </div>
    <div class="ekskul-grid" id="ekskulGrid"></div>
  </div>
</section>

<!-- PENGUMUMAN -->
<section id="pengumuman">
  <div class="wrap">
    <div class="sec-head">
      <span class="eyebrow">Papan Pengumuman</span>
      <h2>Info &amp; Kegiatan Terbaru</h2>
      <p>Update seputar jadwal, lomba, dan kegiatan kesiswaan yang perlu diketahui seluruh siswa.</p>
    </div>
    <div class="pengumuman-grid" id="pengumumanGrid"></div>
  </div>
</section>

<!-- POIN SISWA -->
<section id="poin">
  <div class="wrap">
    <div class="sec-head">
      <span class="eyebrow">Presensi &amp; Poin Siswa</span>
      <h2>Pantau Poin Prestasi &amp; Pelanggaran</h2>
      <p>Sistem poin membantu memantau kedisiplinan sekaligus mengapresiasi prestasi siswa sepanjang semester.</p>
    </div>
    <div class="poin-panel">
      <div class="poin-top">
        <div class="poin-rule plus"><div class="icn">⭐</div><div><h4>Poin Prestasi</h4><p>Didapat dari lomba, kegiatan OSIS/ekskul aktif, dan kontribusi positif lain di sekolah.</p></div></div>
        <div class="poin-rule minus"><div class="icn">⚠️</div><div><h4>Poin Pelanggaran</h4><p>Dicatat dari keterlambatan, atribut tidak lengkap, hingga pelanggaran tata tertib lainnya.</p></div></div>
      </div>

      <div id="poinLoginPrompt" class="login-card">
        <div class="ico">🔐</div>
        <h3 style="font-family:'Fredoka'; font-size:18px;">Cek Poin Kamu</h3>
        <p style="color:var(--ink-soft); font-size:13.5px; margin:8px 0 20px;">Masuk dengan NISN dan password yang diberikan oleh admin Kesiswaan untuk melihat poin prestasi &amp; pelanggaranmu sendiri.</p>
        <button class="btn btn-primary" style="width:100%; justify-content:center;" onclick="openStudentLogin()">Masuk dengan NISN</button>
      </div>
      <div id="poinStudentWrap" class="hidden"></div>
    </div>
  </div>
</section>

<!-- GALERI -->
<section id="galeri">
  <div class="wrap">
    <div class="sec-head">
      <span class="eyebrow">Galeri Kegiatan</span>
      <h2>Momen &amp; Prestasi Siswa</h2>
      <p>Dokumentasi kegiatan kesiswaan sepanjang semester ini.</p>
    </div>
    <div class="gal-grid" id="galeriGrid"></div>
  </div>
</section>

<!-- FOOTER -->
<footer id="kontak">
  <div class="wrap">
    <div class="foot-grid">
      <div>
        <h4>Bidang Kesiswaan</h4>
        <p>SMP Negeri 71 Maluku Tengah<br>Jl. Legatala - Negeri Lesluru, Kec. Teon Nila Serua<br>Senin–Jumat, 07.00–15.30 WIB</p>
      </div>
      <div>
        <h4>Tautan Cepat</h4>
        <ul>
          <li><a href="#profil">Profil OSIS &amp; Ekskul</a></li>
          <li><a href="#pengumuman">Pengumuman</a></li>
          <li><a href="#poin">Poin Siswa</a></li>
          <li><a href="#galeri">Galeri</a></li>
          <li><a href="#" onclick="openAdminLogin(); return false;">Portal Admin</a></li>
        </ul>
      </div>
      <div>
        <h4>Kontak</h4>
        <ul>
          <li><a href="https://wa.me/6285137421546" target="_blank" rel="noopener" style="display:inline-flex;align-items:center;gap:6px;">💬 Chat WhatsApp Admin (0851-3742-1546)</a></li>
          <li>Ruang Kesiswaan — Gedung UKS SMPN 71 Malteng</li>
        </ul>
      </div>
    </div>
    <div class="foot-bottom">
      <span>© 2026 Bidang Kesiswaan — SMP Negeri 71 Maluku Tengah</span>
      <span>Dibuat untuk memudahkan info seputar OSIS, ekskul &amp; kegiatan siswa.</span>
    </div>
  </div>
</footer>

</div><!-- /#site -->

<!-- ===== ADMIN PORTAL ===== -->
<div id="adminPortal" class="hidden">
  <div class="admin-topbar">
    <div class="title">🛠️ Portal Admin Kesiswaan</div>
    <button class="btn btn-ghost" style="background:transparent;color:#fff;border-color:#fff;box-shadow:none;" onclick="exitAdmin()">← Kembali ke Website</button>
  </div>
  <div class="admin-body">
    <div class="admin-sidebar">
      <button id="navbtn-pengumuman" onclick="switchAdminPanel('pengumuman')">📣 Pengumuman</button>
      <button id="navbtn-osis" onclick="switchAdminPanel('osis')">🏛️ Struktur OSIS</button>
      <button id="navbtn-ekskul" onclick="switchAdminPanel('ekskul')">🎯 Ekskul</button>
      <button id="navbtn-siswa" onclick="switchAdminPanel('siswa')">🧑‍🎓 Siswa &amp; Poin</button>
      <button id="navbtn-galeri" onclick="switchAdminPanel('galeri')">🖼️ Galeri</button>
      <button id="navbtn-pengaturan" onclick="switchAdminPanel('pengaturan')">⚙️ Pengaturan</button>
    </div>
    <div class="admin-content">

      <div class="admin-panel" id="panel-pengumuman">
        <div class="admin-panel-head"><h2>Kelola Pengumuman</h2><button class="btn btn-primary" onclick="openFormModal('pengumuman')">+ Tambah</button></div>
        <div class="admin-table-wrap"><table><thead><tr><th>Tanggal</th><th>Kategori</th><th>Judul</th><th>Aksi</th></tr></thead><tbody id="adminPengumumanBody"></tbody></table></div>
      </div>

      <div class="admin-panel" id="panel-osis">
        <div class="admin-panel-head"><h2>Struktur OSIS</h2></div>
        <div class="admin-table-wrap" style="padding:24px;">
          <div class="field"><label>Pembina OSIS</label><input id="osisPembina"></div>
          <div style="display:grid; grid-template-columns:2fr 1fr; gap:12px;">
            <div class="field"><label>Ketua OSIS</label><input id="osisKetua"></div>
            <div class="field"><label>Kelas</label><input id="osisKetuaKelas"></div>
          </div>
          <div style="display:grid; grid-template-columns:2fr 1fr; gap:12px;">
            <div class="field"><label>Wakil Ketua</label><input id="osisWakil"></div>
            <div class="field"><label>Kelas</label><input id="osisWakilKelas"></div>
          </div>
          <div style="display:grid; grid-template-columns:2fr 1fr; gap:12px;">
            <div class="field"><label>Sekretaris</label><input id="osisSekretaris"></div>
            <div class="field"><label>Kelas</label><input id="osisSekretarisKelas"></div>
          </div>
          <div style="display:grid; grid-template-columns:2fr 1fr; gap:12px;">
            <div class="field"><label>Bendahara</label><input id="osisBendahara"></div>
            <div class="field"><label>Kelas</label><input id="osisBendaharaKelas"></div>
          </div>
          <p style="font-family:'Fredoka'; font-size:13px; color:var(--ink-soft); margin:18px 0 10px;">Seksi Bidang</p>
          <div id="osisSeksiInputs" style="display:grid; grid-template-columns:1fr 1fr; gap:12px;"></div>
          <button class="btn btn-primary" style="margin-top:14px;" onclick="saveOsisForm()">Simpan Struktur OSIS</button>
        </div>
      </div>

      <div class="admin-panel" id="panel-ekskul">
        <div class="admin-panel-head"><h2>Kelola Ekskul</h2><button class="btn btn-primary" onclick="openFormModal('ekskul')">+ Tambah</button></div>
        <div class="admin-table-wrap"><table><thead><tr><th>Emoji</th><th>Nama</th><th>Jadwal</th><th>Aksi</th></tr></thead><tbody id="adminEkskulBody"></tbody></table></div>
      </div>

      <div class="admin-panel" id="panel-siswa">
        <div class="admin-panel-head"><h2>Akun Siswa &amp; Poin</h2><button class="btn btn-primary" onclick="openFormModal('siswa')">+ Tambah Siswa</button></div>
        <p style="color:var(--ink-soft); font-size:13px; margin:-8px 0 16px;">Password di sini adalah password login siswa untuk mengecek poin masing-masing lewat NISN.</p>
        <div class="admin-table-wrap"><table><thead><tr><th>NISN</th><th>Nama</th><th>Kelas</th><th>Prestasi</th><th>Pelanggaran</th><th>Status</th><th>Aksi</th></tr></thead><tbody id="adminSiswaBody"></tbody></table></div>
      </div>

      <div class="admin-panel" id="panel-galeri">
        <div class="admin-panel-head"><h2>Kelola Galeri</h2><button class="btn btn-primary" onclick="openFormModal('galeri')">+ Tambah</button></div>
        <div class="admin-table-wrap"><table><thead><tr><th>Emoji</th><th>Judul</th><th>Warna</th><th>Aksi</th></tr></thead><tbody id="adminGaleriBody"></tbody></table></div>
      </div>

      <div class="admin-panel" id="panel-pengaturan">
        <div class="admin-panel-head"><h2>Pengaturan Admin</h2></div>
        <div class="admin-table-wrap" style="padding:24px; max-width:420px;">
          <div class="field"><label>Username Admin</label><input id="settingUser"></div>
          <div class="field"><label>Password Baru (kosongkan jika tidak diubah)</label><input type="password" id="settingPass"></div>
          <div class="field"><label>Konfirmasi Password Baru</label><input type="password" id="settingPassConfirm"></div>
          <div class="field-error" id="settingsError"></div>
          <button class="btn btn-primary" onclick="saveAdminSettings()">Simpan Pengaturan</button>
        </div>
      </div>

    </div>
  </div>
</div>

<!-- ===== MODALS ===== -->
<div class="modal-overlay hidden" id="studentLoginOverlay">
  <div class="modal-box">
    <button class="modal-x" onclick="closeStudentLogin()">✕</button>
    <h3>Masuk Cek Poin Siswa</h3>
    <p class="sub">Gunakan NISN &amp; password yang diberikan admin Kesiswaan.</p>
    <div class="field"><label>NISN</label><input id="loginNisn" placeholder="Contoh: 0081234561"></div>
    <div class="field"><label>Password</label><input type="password" id="loginPass"></div>
    <div class="field-error" id="studentLoginError">NISN atau password salah.</div>
    <div class="modal-actions">
      <button class="btn btn-ghost" onclick="closeStudentLogin()">Batal</button>
      <button class="btn btn-primary" onclick="studentLoginSubmit()">Masuk</button>
    </div>
  </div>
</div>

<div class="modal-overlay hidden" id="adminLoginOverlay">
  <div class="modal-box">
    <button class="modal-x" onclick="closeAdminLogin()">✕</button>
    <h3>Masuk Portal Admin</h3>
    <p class="sub">Khusus Bidang Kesiswaan untuk mengelola seluruh konten &amp; data poin siswa.</p>
    <div class="field"><label>Username</label><input id="adminUser"></div>
    <div class="field"><label>Password</label><input type="password" id="adminPass"></div>
    <div class="field-error" id="adminLoginError">Username atau password salah.</div>
    <div class="modal-actions">
      <button class="btn btn-ghost" onclick="closeAdminLogin()">Batal</button>
      <button class="btn btn-primary" onclick="adminLoginSubmit()">Masuk</button>
    </div>
  </div>
</div>

<div class="modal-overlay hidden" id="formModalOverlay">
  <div class="modal-box">
    <button class="modal-x" onclick="closeFormModal()">✕</button>
    <h3 id="formModalTitle">Tambah Data</h3>
    <div id="formModalFields"></div>
    <div class="field-error" id="formModalError"></div>
    <div class="modal-actions">
      <button class="btn btn-ghost" onclick="closeFormModal()">Batal</button>
      <button class="btn btn-primary" onclick="submitFormModal()">Simpan</button>
    </div>
  </div>
</div>

<div class="toast" id="toast"></div>

<script>
/* ============ DATA & STORAGE ============ */
const DEFAULTS = {
  pengumuman: [],
  ekskul: [
    {id:'e1', nama:'Bulu Tangkis', jadwal:'Selasa & Jumat', emoji:'🏸', warna:'coral'},
    {id:'e2', nama:'Seni Rupa', jadwal:'Rabu', emoji:'🎨', warna:'teal'},
    {id:'e3', nama:'Paduan Suara', jadwal:'Kamis', emoji:'📣', warna:'gold'},
    {id:'e4', nama:'Robotik', jadwal:'Sabtu', emoji:'🤖', warna:'lilac'},
    {id:'e5', nama:'Futsal', jadwal:'Senin & Kamis', emoji:'⚽', warna:'coral'},
    {id:'e6', nama:'Pramuka', jadwal:'Jumat', emoji:'🕵️', warna:'teal'},
    {id:'e7', nama:'Jurnalistik', jadwal:'Rabu', emoji:'📰', warna:'gold'},
    {id:'e8', nama:'Pencak Silat', jadwal:'Selasa', emoji:'🥋', warna:'lilac'}
  ],
  galeri: [
    {id:'g1', judul:'Juara Umum O2SN', emoji:'🏅', gradient:'coral'},
    {id:'g2', judul:'Pentas Seni Tahunan', emoji:'🎭', gradient:'teal'},
    {id:'g3', judul:'Upacara HUT Sekolah', emoji:'🚩', gradient:'lilac'},
    {id:'g4', judul:'Bakti Sosial', emoji:'🤝', gradient:'gold'},
    {id:'g5', judul:'Perkemahan Pramuka', emoji:'🏕️', gradient:'coral'},
    {id:'g6', judul:'Lomba Literasi', emoji:'📚', gradient:'teal'},
    {id:'g7', judul:'Ekskul Paduan Suara', emoji:'🎶', gradient:'lilac'},
    {id:'g8', judul:'Turnamen Antar Kelas', emoji:'🏸', gradient:'gold'}
  ],
  osis: {
    pembina:'',
    ketua:'', ketuaKelas:'',
    wakil:'', wakilKelas:'',
    sekretaris:'', sekretarisKelas:'',
    bendahara:'', bendaharaKelas:'',
    seksi:[
      {nama:'', jumlah:0},
      {nama:'', jumlah:0},
      {nama:'', jumlah:0},
      {nama:'', jumlah:0}
    ]
  },
  siswa: [],
  admin: {username:'admin', password:'admin123'}
};

const EKSKUL_COLORS = {coral:'#FFE9E3', teal:'#E3F5F2', gold:'#FFF3D9', lilac:'#ECE6FF'};
const GAL_GRADIENTS = {
  coral:'linear-gradient(160deg,#FF8A6A,#E4502F)',
  teal:'linear-gradient(160deg,#3FC1B7,#0B6E67)',
  lilac:'linear-gradient(160deg,#A18CFF,#6C4FD1)',
  gold:'linear-gradient(160deg,#FFCF6B,#E8A317)'
};
const WARNA_LABEL = {coral:'Merah Karang', teal:'Toska', gold:'Kuning Emas', lilac:'Ungu Lilac'};

const SCHEMAS = {
  pengumuman: [
    {key:'tanggal', label:'Tanggal', type:'text', placeholder:'contoh: 21 Jul'},
    {key:'tag', label:'Kategori', type:'text', placeholder:'contoh: Kegiatan'},
    {key:'judul', label:'Judul', type:'text'},
    {key:'deskripsi', label:'Deskripsi', type:'textarea'}
  ],
  ekskul: [
    {key:'nama', label:'Nama Ekskul', type:'text'},
    {key:'jadwal', label:'Jadwal', type:'text', placeholder:'contoh: Selasa & Jumat'},
    {key:'emoji', label:'Emoji Ikon', type:'text', placeholder:'contoh: 🏸'},
    {key:'warna', label:'Warna', type:'select', options:['coral','teal','gold','lilac']}
  ],
  galeri: [
    {key:'judul', label:'Judul', type:'text'},
    {key:'emoji', label:'Emoji', type:'text', placeholder:'contoh: 🏅'},
    {key:'gradient', label:'Warna', type:'select', options:['coral','teal','lilac','gold']}
  ],
  siswa: [
    {key:'nisn', label:'NISN', type:'text'},
    {key:'nama', label:'Nama Siswa', type:'text'},
    {key:'kelas', label:'Kelas', type:'text'},
    {key:'password', label:'Password Login', type:'text'},
    {key:'prestasi', label:'Poin Prestasi', type:'number', required:false},
    {key:'pelanggaran', label:'Poin Pelanggaran', type:'number', required:false}
  ]
};
const ENTITY_META = {
  pengumuman: {stateKey:'pengumuman', storageKey:'pengumuman-list', label:'Pengumuman'},
  ekskul: {stateKey:'ekskul', storageKey:'ekskul-list', label:'Ekskul'},
  galeri: {stateKey:'galeri', storageKey:'galeri-list', label:'Item Galeri'},
  siswa: {stateKey:'siswa', storageKey:'siswa-list', label:'Akun Siswa'}
};

let state = {pengumuman:[], ekskul:[], galeri:[], osis:{}, siswa:[], admin:{}};
let currentStudent = null;
let isAdmin = false;
let currentFormType = null;
let currentFormId = null;

function esc(str){
  const d = document.createElement('div');
  d.textContent = (str===undefined||str===null) ? '' : String(str);
  return d.innerHTML;
}
function uid(){ return 'i'+Date.now().toString(36)+Math.random().toString(36).slice(2,8); }

async function loadData(key, fallback){
  try{
    const res = await window.storage.get(key, true);
    if(res && res.value){ return JSON.parse(res.value); }
    await window.storage.set(key, JSON.stringify(fallback), true);
    return fallback;
  }catch(e){
    try{ await window.storage.set(key, JSON.stringify(fallback), true); }catch(e2){}
    return fallback;
  }
}
async function saveData(key, value){
  try{
    await window.storage.set(key, JSON.stringify(value), true);
    return true;
  }catch(e){
    showToast('Gagal menyimpan data. Coba lagi.');
    return false;
  }
}

/* ============ INIT ============ */
async function init(){
  state.pengumuman = await loadData('pengumuman-list', DEFAULTS.pengumuman);
  state.ekskul = await loadData('ekskul-list', DEFAULTS.ekskul);
  state.galeri = await loadData('galeri-list', DEFAULTS.galeri);
  state.osis = await loadData('osis-struktur', DEFAULTS.osis);
  state.siswa = await loadData('siswa-list', DEFAULTS.siswa);
  state.admin = await loadData('admin-akun', DEFAULTS.admin);

  renderAll();
  document.getElementById('loadingOverlay').classList.add('hidden');
  document.getElementById('site').classList.remove('hidden');
}
function renderAll(){
  renderPengumuman();
  renderHeroNotes();
  renderEkskul();
  renderOsisPublic();
  renderGaleri();
  renderStatPins();
  renderPoinSection();
}

/* ============ PUBLIC RENDER ============ */
function renderPengumuman(){
  const grid=document.getElementById('pengumumanGrid');
  grid.innerHTML = state.pengumuman.map(p=>`
    <div class="pcard">
      <span class="date">${esc(p.tanggal)}</span>
      <span class="tag">${esc(p.tag)}</span>
      <h3>${esc(p.judul)}</h3>
      <p>${esc(p.deskripsi)}</p>
    </div>`).join('') || '<p style="color:var(--ink-soft);">Belum ada pengumuman.</p>';
}
function renderHeroNotes(){
  const wrap=document.getElementById('heroNotes');
  const items=state.pengumuman.slice(0,3);
  wrap.innerHTML = items.map((p,i)=>{
    const rotClass = i%2===0?'rot-l':'rot-r';
    const desc = (p.deskripsi||'').length>60 ? p.deskripsi.slice(0,60)+'…' : (p.deskripsi||'');
    return `<div class="note ${rotClass}"><div class="hand">📌 ${esc(p.judul)}</div><p>${esc(desc)}</p></div>`;
  }).join('') || '<p style="color:var(--ink-soft);">Belum ada pengumuman.</p>';
}
function renderEkskul(){
  const grid=document.getElementById('ekskulGrid');
  grid.innerHTML = state.ekskul.map(e=>`
    <div class="ekskul-card">
      <div class="ico" style="background:${EKSKUL_COLORS[e.warna]||EKSKUL_COLORS.coral};">${esc(e.emoji)||'⭐'}</div>
      <h3>${esc(e.nama)}</h3><p>${esc(e.jadwal)}</p>
    </div>`).join('') || '<p style="color:var(--ink-soft);">Belum ada ekskul terdaftar.</p>';
}
function renderGaleri(){
  const grid=document.getElementById('galeriGrid');
  grid.innerHTML = state.galeri.map(g=>`
    <div class="gal-item" style="background:${GAL_GRADIENTS[g.gradient]||GAL_GRADIENTS.coral};">
      <span class="emoji">${esc(g.emoji)||'📷'}</span><span class="cap">${esc(g.judul)}</span>
    </div>`).join('') || '<p style="color:var(--ink-soft);">Belum ada galeri.</p>';
}
function renderOsisPublic(){
  const o=state.osis;
  document.getElementById('osisPembinaName').textContent = o.pembina || 'Belum diisi admin';
  document.getElementById('osisKetuaName').textContent = o.ketua ? (o.ketua + (o.ketuaKelas? ' — '+o.ketuaKelas : '')) : 'Belum diisi admin';
  document.getElementById('osisWakilName').textContent = o.wakil ? (o.wakil + (o.wakilKelas? ' — '+o.wakilKelas : '')) : 'Belum diisi admin';
  document.getElementById('osisSekretarisName').textContent = o.sekretaris ? (o.sekretaris + (o.sekretarisKelas? ' — '+o.sekretarisKelas : '')) : 'Belum diisi admin';
  document.getElementById('osisBendaharaName').textContent = o.bendahara ? (o.bendahara + (o.bendaharaKelas? ' — '+o.bendaharaKelas : '')) : 'Belum diisi admin';
  const seksiWrap=document.getElementById('osisSeksiRow');
  const seksiIsi = (o.seksi||[]).filter(s=>s.nama && s.nama.trim()!=='');
  seksiWrap.innerHTML = seksiIsi.length
    ? seksiIsi.map(s=>`<div class="org-card"><div class="role">${esc(s.nama)}</div><div class="name">${esc(s.jumlah)} anggota</div></div>`).join('')
    : '<p style="color:#B9C3CC; font-size:13px;">Data seksi bidang belum diisi admin.</p>';
}
function renderStatPins(){
  document.getElementById('statEkskul').textContent = state.ekskul.length;
  const seksiTotal = (state.osis.seksi||[]).reduce((a,s)=>a+(Number(s.jumlah)||0),0);
  document.getElementById('statOsis').textContent = 5 + seksiTotal;
}

/* ============ POIN SISWA (LOGIN) ============ */
function statusFor(prestasi, pelanggaran){
  const skor=(Number(prestasi)||0)-(Number(pelanggaran)||0);
  if(skor>=60) return {label:'Sangat Baik', cls:'high'};
  if(skor>=30) return {label:'Baik', cls:'high'};
  if(skor>=0) return {label:'Cukup', cls:'mid'};
  return {label:'Perlu Pembinaan', cls:'low'};
}
function renderPoinSection(){
  if(currentStudent){ renderStudentDashboard(); } else { showLoginPrompt(); }
}
function showLoginPrompt(){
  document.getElementById('poinStudentWrap').classList.add('hidden');
  document.getElementById('poinStudentWrap').innerHTML='';
  document.getElementById('poinLoginPrompt').classList.remove('hidden');
}
function renderStudentDashboard(){
  document.getElementById('poinLoginPrompt').classList.add('hidden');
  const wrap=document.getElementById('poinStudentWrap');
  wrap.classList.remove('hidden');
  const s=currentStudent;
  const st=statusFor(s.prestasi, s.pelanggaran);
  wrap.innerHTML = `
    <div class="student-card">
      <div class="top">
        <div class="avatar">🎓</div>
        <div>
          <h3 style="font-family:'Fredoka'; font-size:18px;">${esc(s.nama)}</h3>
          <p style="color:var(--ink-soft); font-size:13px; margin:2px 0 0;">Kelas ${esc(s.kelas)} · NISN ${esc(s.nisn)}</p>
        </div>
      </div>
      <div class="stat-grid">
        <div class="student-stat"><div class="num" style="color:var(--teal-deep);">+${Number(s.prestasi)||0}</div><div class="lbl">Poin Prestasi</div></div>
        <div class="student-stat"><div class="num" style="color:var(--coral-deep);">−${Number(s.pelanggaran)||0}</div><div class="lbl">Poin Pelanggaran</div></div>
      </div>
      <div style="text-align:center; margin-bottom:18px;">
        <span class="badge-score ${st.cls}" style="font-size:14px; padding:8px 16px;">${st.label}</span>
      </div>
      <button class="btn btn-ghost" style="width:100%; justify-content:center;" onclick="studentLogout()">Keluar</button>
    </div>`;
}
function studentLogout(){ currentStudent=null; showLoginPrompt(); }

function openStudentLogin(){
  document.getElementById('studentLoginError').style.display='none';
  document.getElementById('loginNisn').value='';
  document.getElementById('loginPass').value='';
  document.getElementById('studentLoginOverlay').classList.remove('hidden');
}
function closeStudentLogin(){ document.getElementById('studentLoginOverlay').classList.add('hidden'); }
function studentLoginSubmit(){
  const nisn=document.getElementById('loginNisn').value.trim();
  const pass=document.getElementById('loginPass').value;
  const found = state.siswa.find(s => String(s.nisn).trim()===nisn && s.password===pass);
  if(found){
    currentStudent=found;
    closeStudentLogin();
    renderStudentDashboard();
    showToast('Berhasil masuk. Selamat datang, '+found.nama+'!');
  } else {
    document.getElementById('studentLoginError').style.display='block';
  }
}

/* ============ ADMIN AUTH ============ */
function openAdminLogin(){
  if(isAdmin){ showAdminPortal(); return; }
  document.getElementById('adminLoginError').style.display='none';
  document.getElementById('adminUser').value='';
  document.getElementById('adminPass').value='';
  document.getElementById('adminLoginOverlay').classList.remove('hidden');
}
function closeAdminLogin(){ document.getElementById('adminLoginOverlay').classList.add('hidden'); }
function adminLoginSubmit(){
  const u=document.getElementById('adminUser').value.trim();
  const p=document.getElementById('adminPass').value;
  if(u===state.admin.username && p===state.admin.password){
    isAdmin=true;
    closeAdminLogin();
    showAdminPortal();
  } else {
    document.getElementById('adminLoginError').style.display='block';
  }
}
function showAdminPortal(){
  document.getElementById('site').classList.add('hidden');
  document.getElementById('adminPortal').classList.remove('hidden');
  window.scrollTo(0,0);
  renderAdminPengumuman(); renderAdminEkskul(); renderAdminGaleri(); renderAdminSiswa(); fillOsisForm();
  switchAdminPanel('pengumuman');
}
function exitAdmin(){
  isAdmin=false;
  document.getElementById('adminPortal').classList.add('hidden');
  document.getElementById('site').classList.remove('hidden');
}
function switchAdminPanel(name){
  document.querySelectorAll('.admin-panel').forEach(p=>p.classList.remove('active'));
  document.querySelectorAll('.admin-sidebar button').forEach(b=>b.classList.remove('active'));
  document.getElementById('panel-'+name).classList.add('active');
  document.getElementById('navbtn-'+name).classList.add('active');
}

/* ============ ADMIN: OSIS FORM ============ */
function fillOsisForm(){
  const o=state.osis;
  document.getElementById('osisPembina').value=o.pembina||'';
  document.getElementById('osisKetua').value=o.ketua||'';
  document.getElementById('osisKetuaKelas').value=o.ketuaKelas||'';
  document.getElementById('osisWakil').value=o.wakil||'';
  document.getElementById('osisWakilKelas').value=o.wakilKelas||'';
  document.getElementById('osisSekretaris').value=o.sekretaris||'';
  document.getElementById('osisSekretarisKelas').value=o.sekretarisKelas||'';
  document.getElementById('osisBendahara').value=o.bendahara||'';
  document.getElementById('osisBendaharaKelas').value=o.bendaharaKelas||'';
  const wrap=document.getElementById('osisSeksiInputs');
  wrap.innerHTML=(o.seksi||[]).map((s,i)=>`
    <div class="field"><label>Nama Seksi ${i+1}</label><input class="seksi-nama" value="${esc(s.nama)}"></div>
    <div class="field"><label>Jumlah Anggota</label><input type="number" class="seksi-jumlah" value="${Number(s.jumlah)||0}"></div>
  `).join('');
  document.getElementById('settingUser').value = state.admin.username||'';
}
async function saveOsisForm(){
  const namas=[...document.querySelectorAll('.seksi-nama')].map(i=>i.value.trim());
  const jumlahs=[...document.querySelectorAll('.seksi-jumlah')].map(i=>Number(i.value)||0);
  const seksi=namas.map((n,i)=>({nama:n, jumlah:jumlahs[i]}));
  state.osis = {
    pembina: document.getElementById('osisPembina').value.trim(),
    ketua: document.getElementById('osisKetua').value.trim(),
    ketuaKelas: document.getElementById('osisKetuaKelas').value.trim(),
    wakil: document.getElementById('osisWakil').value.trim(),
    wakilKelas: document.getElementById('osisWakilKelas').value.trim(),
    sekretaris: document.getElementById('osisSekretaris').value.trim(),
    sekretarisKelas: document.getElementById('osisSekretarisKelas').value.trim(),
    bendahara: document.getElementById('osisBendahara').value.trim(),
    bendaharaKelas: document.getElementById('osisBendaharaKelas').value.trim(),
    seksi
  };
  const ok = await saveData('osis-struktur', state.osis);
  if(ok){ renderOsisPublic(); renderStatPins(); showToast('Struktur OSIS disimpan.'); }
}

/* ============ ADMIN: GENERIC CRUD MODAL ============ */
function labelForOption(key,o){ return WARNA_LABEL[o] || o; }
function openFormModal(type, id){
  currentFormType=type; currentFormId=id||null;
  const meta=ENTITY_META[type]; const schema=SCHEMAS[type];
  document.getElementById('formModalTitle').textContent = (id?'Edit ':'Tambah ') + meta.label;
  const fieldsEl=document.getElementById('formModalFields');
  const item = id ? state[meta.stateKey].find(x=>x.id===id) : null;
  fieldsEl.innerHTML = schema.map(f=>{
    const val = item ? (item[f.key] ?? '') : '';
    let inputHtml='';
    if(f.type==='textarea'){
      inputHtml = `<textarea id="field-${f.key}" placeholder="${f.placeholder||''}">${esc(val)}</textarea>`;
    } else if(f.type==='select'){
      inputHtml = `<select id="field-${f.key}">${f.options.map(o=>`<option value="${o}" ${o===val?'selected':''}>${labelForOption(f.key,o)}</option>`).join('')}</select>`;
    } else {
      inputHtml = `<input type="${f.type==='number'?'number':'text'}" id="field-${f.key}" value="${esc(val)}" placeholder="${f.placeholder||''}">`;
    }
    return `<div class="field"><label>${f.label}</label>${inputHtml}</div>`;
  }).join('');
  document.getElementById('formModalError').style.display='none';
  document.getElementById('formModalOverlay').classList.remove('hidden');
}
function closeFormModal(){ document.getElementById('formModalOverlay').classList.add('hidden'); }
async function submitFormModal(){
  const meta=ENTITY_META[currentFormType]; const schema=SCHEMAS[currentFormType];
  const obj={};
  for(const f of schema){
    const el=document.getElementById('field-'+f.key);
    let v=el.value.trim();
    if(f.type==='number'){ v = v===''?0:Number(v); }
    if(f.required!==false && v===''){
      const err=document.getElementById('formModalError');
      err.textContent='Mohon lengkapi field: '+f.label;
      err.style.display='block';
      return;
    }
    obj[f.key]=v;
  }
  const arr=state[meta.stateKey];
  if(currentFormId){
    const idx=arr.findIndex(x=>x.id===currentFormId);
    if(idx>-1) arr[idx]={...arr[idx], ...obj};
  } else {
    obj.id=uid();
    arr.push(obj);
  }
  const ok = await saveData(meta.storageKey, arr);
  if(ok){
    closeFormModal();
    renderAllForType(currentFormType);
    showToast('Data berhasil disimpan.');
  }
}
async function deleteItem(type, id){
  if(!confirm('Hapus data ini?')) return;
  const meta=ENTITY_META[type];
  state[meta.stateKey] = state[meta.stateKey].filter(x=>x.id!==id);
  const ok = await saveData(meta.storageKey, state[meta.stateKey]);
  if(ok){ renderAllForType(type); showToast('Data dihapus.'); }
}
function renderAllForType(type){
  if(type==='pengumuman'){ renderPengumuman(); renderHeroNotes(); renderAdminPengumuman(); }
  if(type==='ekskul'){ renderEkskul(); renderStatPins(); renderAdminEkskul(); }
  if(type==='galeri'){ renderGaleri(); renderAdminGaleri(); }
  if(type==='siswa'){ renderAdminSiswa(); }
}
function emptyRow(cols){ return `<tr><td colspan="${cols}" style="text-align:center;color:var(--ink-soft);padding:24px;">Belum ada data.</td></tr>`; }

function renderAdminPengumuman(){
  const tbody=document.getElementById('adminPengumumanBody');
  tbody.innerHTML = state.pengumuman.map(p=>`
    <tr>
      <td>${esc(p.tanggal)}</td><td>${esc(p.tag)}</td><td>${esc(p.judul)}</td>
      <td class="row-actions">
        <button class="edit" onclick="openFormModal('pengumuman','${p.id}')">Edit</button>
        <button class="danger" onclick="deleteItem('pengumuman','${p.id}')">Hapus</button>
      </td>
    </tr>`).join('') || emptyRow(4);
}
function renderAdminEkskul(){
  const tbody=document.getElementById('adminEkskulBody');
  tbody.innerHTML = state.ekskul.map(e=>`
    <tr>
      <td>${esc(e.emoji)}</td><td>${esc(e.nama)}</td><td>${esc(e.jadwal)}</td>
      <td class="row-actions">
        <button class="edit" onclick="openFormModal('ekskul','${e.id}')">Edit</button>
        <button class="danger" onclick="deleteItem('ekskul','${e.id}')">Hapus</button>
      </td>
    </tr>`).join('') || emptyRow(4);
}
function renderAdminGaleri(){
  const tbody=document.getElementById('adminGaleriBody');
  tbody.innerHTML = state.galeri.map(g=>`
    <tr>
      <td>${esc(g.emoji)}</td><td>${esc(g.judul)}</td><td>${labelForOption('gradient', g.gradient)}</td>
      <td class="row-actions">
        <button class="edit" onclick="openFormModal('galeri','${g.id}')">Edit</button>
        <button class="danger" onclick="deleteItem('galeri','${g.id}')">Hapus</button>
      </td>
    </tr>`).join('') || emptyRow(4);
}
function renderAdminSiswa(){
  const tbody=document.getElementById('adminSiswaBody');
  tbody.innerHTML = state.siswa.map(s=>{
    const st=statusFor(s.prestasi, s.pelanggaran);
    return `<tr>
      <td>${esc(s.nisn)}</td><td>${esc(s.nama)}</td><td>${esc(s.kelas)}</td>
      <td>${Number(s.prestasi)||0}</td><td>${Number(s.pelanggaran)||0}</td>
      <td><span class="badge-score ${st.cls}">${st.label}</span></td>
      <td class="row-actions">
        <button class="edit" onclick="openFormModal('siswa','${s.id}')">Edit</button>
        <button class="danger" onclick="deleteItem('siswa','${s.id}')">Hapus</button>
      </td>
    </tr>`;
  }).join('') || emptyRow(7);
}

/* ============ ADMIN: SETTINGS ============ */
async function saveAdminSettings(){
  const newUser=document.getElementById('settingUser').value.trim();
  const newPass=document.getElementById('settingPass').value;
  const confirmPass=document.getElementById('settingPassConfirm').value;
  const err=document.getElementById('settingsError');
  err.style.display='none';
  if(!newUser){ err.textContent='Username tidak boleh kosong.'; err.style.display='block'; return; }
  if(newPass && newPass!==confirmPass){ err.textContent='Konfirmasi password tidak cocok.'; err.style.display='block'; return; }
  const updated = {username:newUser, password: newPass ? newPass : state.admin.password};
  const ok = await saveData('admin-akun', updated);
  if(ok){
    state.admin = updated;
    document.getElementById('settingPass').value='';
    document.getElementById('settingPassConfirm').value='';
    showToast('Pengaturan admin disimpan.');
  }
}

/* ============ TOAST ============ */
let toastTimer;
function showToast(msg){
  const t=document.getElementById('toast');
  t.textContent=msg;
  t.classList.add('show');
  clearTimeout(toastTimer);
  toastTimer=setTimeout(()=>t.classList.remove('show'), 2600);
}

/* ============ NAV (mobile menu) ============ */
document.addEventListener('DOMContentLoaded', () => {
  const menuBtn=document.getElementById('menu-btn');
  const mobileMenu=document.getElementById('mobile-menu');
  menuBtn.addEventListener('click', () => mobileMenu.classList.toggle('open'));
  mobileMenu.querySelectorAll('a').forEach(a => a.addEventListener('click', () => mobileMenu.classList.remove('open')));
  init();
});
</script>

</body>
</html>
