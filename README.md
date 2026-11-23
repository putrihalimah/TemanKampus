<!doctype html>
<html lang="id">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>Teman Kampus</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Bricolage+Grotesque:wght@400;600;800&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #eef7ff;
    --cd: #ffffff;
    --tx: #0e2a47;
    --mu: #5f7a96;
    --pr: #1a8fe3;
    --pt: #ffffff;
    --sf: #dcefff;
    --ac: #ffc845;
    --bd: #d3e6f8;
    --wr: #c8432b;
    --ok: #1b9a6c;
    box-sizing: border-box;
    padding-top: env(safe-area-inset-top, 0px);
    padding-bottom: env(safe-area-inset-bottom, 0px);
  }
  @media (prefers-color-scheme: dark) {
    :root:not([data-theme="light"]) {
      --bg: #0a1628;
      --cd: #12243d;
      --tx: #e8f1fb;
      --mu: #93a9c4;
      --pr: #5cb8ff;
      --pt: #06182b;
      --sf: #1b3556;
      --bd: #23405f;
      --wr: #ff8a75;
      --ok: #4cd6a0;
    }
  }
  :root[data-theme="dark"] {
    --bg: #0a1628;
    --cd: #12243d;
    --tx: #e8f1fb;
    --mu: #93a9c4;
    --pr: #5cb8ff;
    --pt: #06182b;
    --sf: #1b3556;
    --bd: #23405f;
    --wr: #ff8a75;
    --ok: #4cd6a0;
  }

  html { scroll-padding-top: env(safe-area-inset-top, 0px); }
  * { box-sizing: border-box; }
  body {
    margin: 0;
    background: var(--bg);
    color: var(--tx);
    font: 15px/1.5 "Bricolage Grotesque", system-ui, sans-serif;
    overflow-x: hidden;
  }

  h1, h2, h3, p { margin: 0 0 .4rem; }
  h1 { font-size: 1.6rem; font-weight: 800; line-height: 1.15; }
  h2 { font-size: 1.05rem; font-weight: 800; }
  h3 { font-size: 1rem; font-weight: 600; }
  a { color: var(--pr); font-weight: 600; cursor: pointer; text-decoration: none; }
  a:hover { text-decoration: underline; }

  button, input, select, textarea { font: inherit; color: inherit; }
  input, select, textarea {
    width: 100%;
    padding: .6rem .75rem;
    border: 1.5px solid var(--bd);
    border-radius: 10px;
    background: var(--cd);
    margin: .2rem 0 .7rem;
  }
  input[type=checkbox], input[type=file] { width: auto; margin: 0; }
  label { font-weight: 600; font-size: .86rem; }
  :focus-visible { outline: 3px solid var(--ac); outline-offset: 2px; }

  .btn {
    background: var(--pr);
    color: var(--pt);
    border: 0;
    border-radius: 10px;
    padding: .55rem 1.1rem;
    font-weight: 700;
    cursor: pointer;
    transition: opacity .15s, transform .1s;
    display: inline-flex;
    align-items: center;
    justify-content: center;
    gap: .35rem;
  }
  .btn:hover:not(:disabled) { opacity: .92; }
  .btn:active:not(:disabled) { transform: scale(.98); }
  .btn:disabled { opacity: .6; cursor: not-allowed; }
  .btn.g { background: var(--sf); color: var(--tx); }
  .btn.s { padding: .32rem .75rem; font-size: .84rem; }
  .btn.w { width: 100%; }

  .card {
    background: var(--cd);
    border: 1px solid var(--bd);
    border-radius: 14px;
    padding: 1rem;
    margin-bottom: .8rem;
  }
  .mu { color: var(--mu); font-size: .86rem; }
  .row { display: flex; gap: .6rem; align-items: center; flex-wrap: wrap; }
  .sp { justify-content: space-between; }
  .grow { flex: 1; min-width: 110px; }

  .tag {
    background: var(--sf);
    border-radius: 6px;
    padding: .08rem .52rem;
    font-size: .76rem;
    font-weight: 600;
    display: inline-block;
  }
  .tag.w { background: var(--ac); color: #3a2a00; }
  .tag.ok { background: var(--ok); color: #fff; }
  .err { color: var(--wr); font-weight: 600; min-height: 1.3em; font-size: .88rem; }

  .av {
    border-radius: 50%;
    object-fit: cover;
    display: inline-grid;
    place-items: center;
    background: var(--pr);
    color: var(--pt);
    font-weight: 800;
    flex: none;
  }

  /* Auth Layout - Teks & Ilustrasi terpisah rapi tanpa tumpang tindih */
  .auth { display: grid; grid-template-columns: 1.15fr 1fr; min-height: 100vh; }
  .art {
    position: relative;
    background: linear-gradient(180deg, #3aa8f5 0%, #8cd0ff 55%, #d5eeff 100%);
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    overflow: hidden;
  }
  .art-head {
    position: relative;
    z-index: 2;
    padding: 2.2rem 2.2rem 1rem;
    color: #072d52;
  }
  .art-head h1 {
    font-size: 2.25rem;
    max-width: 13em;
    margin-top: .8rem;
    letter-spacing: -.02em;
  }
  .art-sub {
    font-size: 1rem;
    font-weight: 600;
    color: #0e4478;
    margin-top: .35rem;
    max-width: 24em;
  }
  .art-scene {
    position: relative;
    width: 100%;
    height: 320px;
    flex-shrink: 0;
  }
  .art-scene svg {
    position: absolute;
    inset: 0;
    width: 100%;
    height: 100%;
    display: block;
  }
  .brand-lockup {
    display: inline-flex;
    align-items: center;
    gap: .65rem;
    font-weight: 800;
    font-size: 1.25rem;
    letter-spacing: -.01em;
  }
  .brand-lockup span { color: var(--pr); }
  .art-head .brand-lockup { color: #072d52; font-size: 1.35rem; }
  .art-head .brand-lockup span { color: #0b5ea8; }

  .form { padding: 2rem 1.5rem; max-width: 470px; width: 100%; margin: auto; }
  .seg { display: flex; gap: .3rem; margin-bottom: 1rem; border-bottom: 2px solid var(--bd); }
  .seg button {
    flex: 1;
    border: 0;
    background: none;
    padding: .5rem;
    font-weight: 700;
    cursor: pointer;
    color: var(--mu);
    border-bottom: 3px solid transparent;
    margin-bottom: -2px;
  }
  .seg .on { color: var(--pr); border-color: var(--pr); }

  /* Main App Layout */
  .app { display: grid; grid-template-columns: 215px 1fr; min-height: 100vh; }
  .logo { font-weight: 800; font-size: 1.15rem; padding: .2rem .5rem 1rem; display: flex; align-items: center; gap: .6rem; }
  .logo span { color: var(--pr); }
  .mob-brand { display: none; align-items: center; gap: .45rem; font-weight: 800; font-size: 1rem; flex-shrink: 0; }

  nav {
    background: var(--cd);
    border-right: 1px solid var(--bd);
    padding: 1rem .7rem;
    position: sticky;
    top: 0;
    height: 100vh;
    overflow: auto;
    display: flex;
    flex-direction: column;
  }
  nav button {
    display: flex;
    gap: .55rem;
    align-items: center;
    width: 100%;
    text-align: left;
    background: none;
    border: 0;
    padding: .55rem .7rem;
    border-radius: 10px;
    cursor: pointer;
    font-weight: 600;
    color: var(--mu);
  }
  nav button.on { background: var(--sf); color: var(--pr); }

  .live-badge {
    margin-top: auto;
    padding: .55rem .7rem;
    font-size: .78rem;
    color: var(--ok);
    font-weight: 700;
    display: flex;
    align-items: center;
    gap: .45rem;
  }
  .live-badge .dot {
    width: 8px;
    height: 8px;
    border-radius: 50%;
    background: var(--ok);
    display: inline-block;
    animation: pulse 2s infinite;
  }
  @keyframes pulse { 0%, 100% { opacity: 1; } 50% { opacity: .35; } }

  .top {
    display: flex;
    gap: .6rem;
    align-items: center;
    padding: .8rem 1.2rem;
    position: sticky;
    top: 0;
    background: var(--bg);
    z-index: 5;
  }
  .top input { margin: 0; }
  .top select { width: auto; margin: 0; }
  main { padding: 0 1.2rem 2rem; max-width: 880px; }
  .grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: .8rem; }

  /* Weather & Sky Banner */
  .sky {
    position: relative;
    border-radius: 18px;
    overflow: hidden;
    min-height: 150px;
    margin-bottom: 1rem;
    color: #0b3a66;
    padding: 1.2rem;
  }
  .sky svg { position: absolute; right: 0; top: 0; height: 100%; width: 60%; max-width: 340px; }
  .sky .sk { position: relative; max-width: 60%; }
  .sky.s0 { background: linear-gradient(160deg, #4fb8ff, #cdeaff); }
  .sky.s1 { background: linear-gradient(160deg, #8fa9bf, #d3dde6); }
  .sky.s2 { background: linear-gradient(160deg, #4d6379, #8a9eb0); color: #fff; }
  .sky.s3 { background: linear-gradient(160deg, #4fb8ff, #e6f6ff); }
  .rn line { animation: fall .9s linear infinite; }
  @keyframes fall { from { transform: translateY(-12px); opacity: 0; } 30% { opacity: 1; } to { transform: translateY(14px); opacity: 0; } }
  @media (prefers-reduced-motion: reduce) { .rn line { animation: none; } }

  /* Study Streak & Pomodoro Widget */
  .streak-card {
    background: linear-gradient(135deg, var(--cd) 0%, var(--sf) 100%);
    border: 1.5px solid var(--bd);
  }
  .streak-days {
    display: flex;
    gap: .35rem;
    margin: .65rem 0;
  }
  .s-day {
    flex: 1;
    text-align: center;
    padding: .4rem .2rem;
    border-radius: 9px;
    background: var(--cd);
    border: 1px solid var(--bd);
    font-size: .75rem;
    font-weight: 700;
    color: var(--mu);
  }
  .s-day.on {
    background: var(--ac);
    color: #3a2a00;
    border-color: #e5ad24;
  }
  .s-day.today {
    outline: 2px solid var(--pr);
  }
  .pomo-pill {
    display: inline-flex;
    align-items: center;
    gap: .4rem;
    background: var(--cd);
    border: 1px solid var(--bd);
    border-radius: 9px;
    padding: .3rem .65rem;
    font-weight: 800;
    font-variant-numeric: tabular-nums;
  }

  /* Post Media & Social Interactions */
  .post-media {
    margin: .5rem 0;
    border-radius: 12px;
    overflow: hidden;
    border: 1px solid var(--bd);
    background: #000;
    max-height: 360px;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .post-media img {
    width: 100%;
    max-height: 360px;
    object-fit: cover;
    display: block;
    background: var(--sf);
  }
  .post-media video, .post-media iframe {
    width: 100%;
    height: 270px;
    border: 0;
    display: block;
  }
  .repost-banner {
    font-size: .78rem;
    font-weight: 700;
    color: var(--mu);
    display: flex;
    align-items: center;
    gap: .35rem;
    margin-bottom: .45rem;
    padding-bottom: .35rem;
    border-bottom: 1px dashed var(--bd);
  }
  .repost-quote {
    border: 1px solid var(--bd);
    background: var(--bg);
    border-radius: 10px;
    padding: .7rem;
    margin: .4rem 0;
  }
  .act-bar {
    display: flex;
    gap: .35rem;
    flex-wrap: wrap;
    margin-top: .55rem;
    padding-top: .5rem;
    border-top: 1px solid var(--bd);
  }
  .act-btn {
    background: transparent;
    border: 1px solid transparent;
    border-radius: 8px;
    padding: .32rem .65rem;
    font-size: .82rem;
    font-weight: 700;
    color: var(--mu);
    cursor: pointer;
    display: inline-flex;
    align-items: center;
    gap: .3rem;
    transition: background .15s, color .15s;
  }
  .act-btn:hover { background: var(--sf); color: var(--tx); }
  .act-btn.liked { color: var(--wr); background: rgba(200, 67, 43, 0.1); }
  .act-btn.reposted { color: var(--ok); background: rgba(27, 154, 108, 0.12); }

  .cmt-box {
    margin-top: .6rem;
    padding-top: .6rem;
    border-top: 1px solid var(--bd);
  }
  .cmt-item {
    background: var(--bg);
    border-radius: 9px;
    padding: .45rem .65rem;
    margin-bottom: .4rem;
    font-size: .88rem;
  }
  .media-prev {
    position: relative;
    margin: .5rem 0;
    border-radius: 10px;
    overflow: hidden;
    border: 1.5px solid var(--bd);
    background: var(--bg);
    padding: .45rem;
  }
  .media-prev img, .media-prev video {
    max-height: 180px;
    border-radius: 8px;
    display: block;
    margin: auto;
  }

  .done { text-decoration: line-through; color: var(--mu); }
  .tabs { display: flex; gap: .4rem; overflow-x: auto; margin-bottom: .8rem; padding-bottom: .2rem; }
  .tabs .btn { white-space: nowrap; }
  .empty { text-align: center; color: var(--mu); padding: 1.5rem 1rem; }

  /* Toast & Loader */
  .toast {
    position: fixed;
    bottom: 80px;
    left: 50%;
    transform: translateX(-50%);
    background: var(--tx);
    color: var(--cd);
    padding: .6rem 1.15rem;
    border-radius: 99px;
    font-weight: 700;
    font-size: .88rem;
    z-index: 100;
    box-shadow: 0 6px 20px rgba(0, 0, 0, .2);
    animation: fadeIn .2s ease;
    text-align: center;
    max-width: 90vw;
  }
  @keyframes fadeIn { from { opacity: 0; transform: translate(-50%, 10px); } to { opacity: 1; transform: translate(-50%, 0); } }

  .loader-wrap {
    display: grid;
    place-items: center;
    min-height: 100vh;
    text-align: center;
    padding: 1rem;
  }
  .spinner {
    width: 38px;
    height: 38px;
    border: 4px solid var(--bd);
    border-top-color: var(--pr);
    border-radius: 50%;
    animation: spin .8s linear infinite;
    margin: 0 auto .8rem;
  }
  @keyframes spin { to { transform: rotate(360deg); } }

  @media (max-width: 760px) {
    .auth { display: block; }
    .art-head { padding: 1.4rem 1.2rem .5rem; }
    .art-head h1 { font-size: 1.45rem; }
    .art-sub { font-size: .88rem; }
    .art-scene { height: 185px; }
    .app { display: block; }
    .top { padding: .6rem; }
    .mob-brand { display: inline-flex; }
    main { padding: 0 .8rem 6rem; }
    .sky .sk { max-width: 72%; }
    nav {
      position: fixed;
      top: auto;
      bottom: 0;
      left: 0;
      right: 0;
      height: auto;
      z-index: 9;
      flex-direction: row;
      padding: .3rem .3rem calc(.3rem + env(safe-area-inset-bottom, 0px));
      border-right: 0;
      border-top: 1px solid var(--bd);
      overflow-x: auto;
    }
    nav .logo, nav .live-badge { display: none; }
    nav button {
      flex-direction: column;
      align-items: center;
      gap: 0;
      font-size: .68rem;
      padding: .35rem .6rem;
      width: auto;
      white-space: nowrap;
    }
  }
</style>
</head>
<body>
<div id="root">
  <div class="loader-wrap">
    <div>
      <div class="spinner"></div>
      <div style="font-weight:700">Menghubungkan ke Teman Kampus...</div>
    </div>
  </div>
</div>

<script type="module">
  import { initializeApp } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-app.js";
  import { getAuth, signInAnonymously, signInWithCustomToken, onAuthStateChanged } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-auth.js";
  import { getFirestore, doc, getDoc, addDoc, setDoc, updateDoc, deleteDoc, onSnapshot, collection } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-firestore.js";

  // Inisialisasi Firebase
  const appId = typeof __app_id !== 'undefined' ? __app_id : 'teman-kampus-app';
  const firebaseConfig = JSON.parse(__firebase_config);
  const app = initializeApp(firebaseConfig);
  const auth = getAuth(app);
  const db = getFirestore(app);

  // Utilitas DOM & Keamanan XSS
  const $ = s => document.querySelector(s);
  const h = s => String(s ?? "").replace(/[&<>"]/g, c => ({ "&": "&amp;", "<": "&lt;", ">": "&gt;", '"': "&quot;" }[c]));
  const uid = () => Math.random().toString(36).slice(2, 9);

  // Toast Notification
  window.showToast = (msg) => {
    const existing = document.querySelector('.toast');
    if (existing) existing.remove();
    const el = document.createElement('div');
    el.className = 'toast';
    el.textContent = msg;
    document.body.appendChild(el);
    setTimeout(() => el.remove(), 2800);
  };

  // Kamus Bahasa (Indonesia & English)
  const T = {
    id: {
      home: "Beranda", sched: "Jadwal", todo: "Tugas", notes: "Catatan", opp: "Peluang", forum: "Forum", fr: "Teman", ipk: "IPK", prof: "Profil", post: "Pasang info", out: "Keluar", sr: "Cari peluang, forum, teman…",
      add: "Tambah", del: "Hapus", save: "Simpan", saved: "Disimpan", open: "Buka tautan", back: "Kembali", all: "Semua", send: "Kirim", g1: "Pagi", g2: "Siang", g3: "Sore", g4: "Malam",
      w0: "Cerah. Semua tugas aman.", w1: "Mendung. {n} tugas lewat deadline.", w2: "Hujan. {n} tugas lewat deadline. Kerjakan satu dulu.", w3: "Pelangi! Semua tugas selesai.",
      today: "Kuliah hari ini", due: "Tugas terdekat",
      e1: "Tidak ada kelas.", e2: "Tidak ada tugas.", e3: "Belum ada catatan.", e4: "Belum ada info.", e5: "Tidak ditemukan.", e6: "Belum ada update. Jadilah yang pertama berbagi!",
      st: "Lagi apa di kampus hari ini?", share: "Bagikan",
      course: "Mata kuliah", room: "Ruang", task: "Tugas", title: "Judul", body: "Isi", nts: "Hanya kamu yang bisa baca.", opps: "Peluang",
      fq: "Topik atau pertanyaan", fb: "Detail", mk: "Buat topik", rep: "balasan", wr: "Balas…",
      people: "Mahasiswa", study: "Belajar bareng", reqs: "Permintaan teman", nb: "Buat grup belajar", tg: "Target", jur: "Jurusan", join: "Gabung", leave: "Keluar grup", members: "anggota", mats: "Materi", mtt: "Judul", mtu: "Tautan",
      fadd: "Tambah teman", fsent: "Terkirim", facc: "Terima", ffr: "Berteman", friends: "teman",
      ps: "Pasang info", cat: "Kategori", dl: "Batas daftar", req: "Syarat", lk: "Tautan", pub: "Terbitkan", mine: "Info saya",
      nm: "Nama", cp: "Kampus", sm: "Semester", bio: "Bio", lg: "Bahasa", tm: "Tema Tampilan", tm0: "Otomatis (Sistem)", tm1: "Terang", tm2: "Gelap",
      pw: "Ganti sandi", pw0: "Sandi lama", pw1: "Sandi baru", da: "Hapus akun", da2: "Yakin? Klik lagi", ok: "Tersimpan", photo: "Ganti foto",
      priv: "Jadwal, tugas, dan catatan hanya terlihat olehmu.", pubn: "Profil ini terlihat oleh mahasiswa lain.", edit: "Edit profil",
      fy: "Untukmu", ipkt: "IPK kumulatif", ip: "IP", sks: "SKS", edit2: "Ubah", hi: "Prioritas", rem: "Pengingat", msg: "Pesan", mw: "Tulis pesan…", nomsg: "Belum ada pesan.",
      prv: "Profil hanya terlihat teman", prg: "Progres target", item: "Langkah baru", closed: "ditutup", td0: "hari ini", dleft: " hari lagi", ver: "Terverifikasi", unv: "Belum diverifikasi", smp: "Contoh",
      "Beasiswa Pemerintah": "Beasiswa Pemerintah", "Beasiswa Swasta": "Beasiswa Swasta", Lomba: "Lomba", Magang: "Magang", Volunteer: "Volunteer", Lainnya: "Lainnya",
      hh: "Kuliah, tugas, dan teman. Satu tempat.", li: "Masuk", rs: "Mahasiswa", rp: "Pemberi info", idn: "Email / no. telepon", pwd: "Sandi (min. 6)", sch2: "Asal kampus",
      ot: "Jenis lembaga", on: "Nama lembaga", pic: "Penanggung jawab", web: "Situs resmi", ds: "Deskripsi singkat", auth: "Saya berwenang mewakili lembaga ini",
      ot1: "Instansi pemerintah", ot2: "Yayasan / perusahaan beasiswa", ot3: "Penyelenggara lomba", ot4: "Perusahaan magang", ot5: "Kampus / organisasi / lainnya", pnote: "Akun pemberi info ditinjau dulu.",
      live: "Terhubung Cloud Real-time", shareLink: "Bagikan tautan aplikasi ini agar teman kampusmu bisa bergabung bersama!",
      authSub: "Atur jadwal kuliah, kejar deadline tugas, bangun streak belajar, dan terhubung dengan mahasiswa lain.",
      addImg: "Foto", addVid: "Video", vidUrlPh: "Tempel URL video (YouTube / .mp4) atau pilih file…",
      like: "Suka", comment: "Komentar", repost: "Repost", shareAct: "Bagikan",
      repostedBy: "Diposting ulang oleh", cmtPh: "Tulis komentar…", copied: "Teks & tautan postingan tersalin!",
      repostedToast: "Berhasil diposting ulang ke beranda!",
      streakTitle: "Streak Belajar", streakDays: "hari berturut-turut", streakBest: "Rekor terbaik",
      checkinBtn: "Check-in Belajar Hari Ini", checkedIn: "Sudah Belajar Hari Ini",
      checkinToast: "Mantap! Streak belajarmu bertambah 🔥",
      focusTimer: "Timer Fokus", startFocus: "Mulai 25m", pauseFocus: "Jeda", resetFocus: "Reset",
      daysShort: ["Min", "Sen", "Sel", "Rab", "Kam", "Jum", "Sab"]
    },
    en: {
      home: "Home", sched: "Schedule", todo: "Tasks", notes: "Notes", opp: "Opportunities", forum: "Forum", fr: "Friends", ipk: "GPA", prof: "Profile", post: "Post info", out: "Log out", sr: "Search opportunities, forum, people…",
      add: "Add", del: "Delete", save: "Save", saved: "Saved", open: "Open link", back: "Back", all: "All", send: "Send", g1: "Morning", g2: "Afternoon", g3: "Evening", g4: "Night",
      w0: "Clear skies. All tasks on track.", w1: "Cloudy. {n} overdue task(s).", w2: "Raining. {n} overdue tasks. Finish one first.", w3: "Rainbow! All tasks done.",
      today: "Classes today", due: "Next due",
      e1: "No classes.", e2: "No tasks.", e3: "No notes yet.", e4: "Nothing here yet.", e5: "Nothing found.", e6: "No updates yet. Be the first to share!",
      st: "What are you up to on campus today?", share: "Post",
      course: "Course", room: "Room", task: "Task", title: "Title", body: "Note", nts: "Only you can read these.", opps: "Opportunities",
      fq: "Topic or question", fb: "Details", mk: "Start topic", rep: "replies", wr: "Reply…",
      people: "Students", study: "Study together", reqs: "Friend requests", nb: "Start a study group", tg: "Goal", jur: "Major", join: "Join", leave: "Leave group", members: "members", mats: "Materials", mtt: "Title", mtu: "Link",
      fadd: "Add friend", fsent: "Sent", facc: "Accept", ffr: "Friends", friends: "friends",
      ps: "Post info", cat: "Category", dl: "Deadline", req: "Requirements", lk: "Link", pub: "Publish", mine: "My posts",
      nm: "Name", cp: "Campus", sm: "Semester", bio: "Bio", lg: "Language", tm: "Theme", tm0: "Auto (System)", tm1: "Light", tm2: "Dark",
      pw: "Change password", pw0: "Current password", pw1: "New password", da: "Delete account", da2: "Sure? Click again", ok: "Saved", photo: "Change photo",
      priv: "Your schedule, tasks, and notes are visible only to you.", pubn: "Other students can see this profile.", edit: "Edit profile",
      fy: "For you", ipkt: "Cumulative GPA", ip: "GPA", sks: "Credits", edit2: "Edit", hi: "Priority", rem: "Reminders", msg: "Message", mw: "Write a message…", nomsg: "No messages yet.",
      prv: "Profile visible to friends only", prg: "Goal progress", item: "New step", closed: "closed", td0: "today", dleft: " days left", ver: "Verified", unv: "Not verified", smp: "Sample",
      "Beasiswa Pemerintah": "Gov. scholarship", "Beasiswa Swasta": "Private scholarship", Lomba: "Contest", Magang: "Internship", Volunteer: "Volunteer", Lainnya: "Other",
      hh: "Classes, tasks, and friends. One place.", li: "Log in", rs: "Student", rp: "Info provider", idn: "Email / phone", pwd: "Password (min. 6)", sch2: "Campus",
      ot: "Organization type", on: "Organization name", pic: "Contact person", web: "Official website", ds: "Short description", auth: "I am authorized to represent this organization",
      ot1: "Government agency", ot2: "Foundation / scholarship company", ot3: "Contest organizer", ot4: "Internship company", ot5: "Campus / organization / other", pnote: "Provider accounts are reviewed first.",
      live: "Cloud Real-time Connected", shareLink: "Share this app link with your campus friends to connect together!",
      authSub: "Manage class schedules, beat deadlines, build your study streak, and connect with campus peers.",
      addImg: "Photo", addVid: "Video", vidUrlPh: "Paste video URL (YouTube / .mp4) or pick a file…",
      like: "Like", comment: "Comment", repost: "Repost", shareAct: "Share",
      repostedBy: "Reposted by", cmtPh: "Write a comment…", copied: "Post text & link copied!",
      repostedToast: "Reposted to your feed!",
      streakTitle: "Study Streak", streakDays: "day streak", streakBest: "Best streak",
      checkinBtn: "Check-in Study Today", checkedIn: "Studied Today",
      checkinToast: "Awesome! Study streak updated 🔥",
      focusTimer: "Focus Timer", startFocus: "Start 25m", pauseFocus: "Pause", resetFocus: "Reset",
      daysShort: ["Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat"]
    }
  };

  let LG = "id";
  let THEME = "auto";
  const t = k => T[LG]?.[k] ?? T.id[k] ?? k;

  const CATS = ["Beasiswa Pemerintah", "Beasiswa Swasta", "Lomba", "Magang", "Volunteer", "Lainnya"];
  const DAYS = {
    id: ["Minggu", "Senin", "Selasa", "Rabu", "Kamis", "Jumat", "Sabtu"],
    en: ["Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"]
  };

  const DEFAULT_OPPS = [
    { id: "o1", cat: "Beasiswa Pemerintah", title: "Beasiswa Unggulan", org: "Kemdikbudristek", deadline: "2027-01-31", req: "IPK min. 3,00; aktif kuliah", link: "https://example.com", by: "seed", sample: 1 },
    { id: "o2", cat: "Beasiswa Swasta", title: "Beasiswa Prestasi Mahasiswa Teknik", org: "Yayasan Contoh", deadline: "2026-12-20", req: "Semester 3-6, esai 500 kata", link: "https://example.com", by: "seed", sample: 1 },
    { id: "o3", cat: "Lomba", title: "Lomba Desain Energi Terbarukan", org: "BEM Fakultas Teknik", deadline: "2026-12-05", req: "Tim 2-3 orang, proposal 10 halaman", link: "https://example.com", by: "seed", sample: 1 },
    { id: "o4", cat: "Magang", title: "Magang Teknisi Kelistrikan", org: "PT Contoh Energi", deadline: "2027-02-10", req: "Semester 5+, CV dan transkrip", link: "https://example.com", by: "seed", sample: 1 },
    { id: "o6", cat: "Volunteer", title: "Relawan Mengajar Anak Pesisir", org: "Komunitas Contoh", deadline: "2027-01-15", req: "Semua jurusan, komitmen 2 bulan, akhir pekan", link: "https://example.com", by: "seed", sample: 1 },
    { id: "o5", cat: "Lainnya", title: "Workshop Mikrokontroler", org: "Himpunan Elektro", deadline: "2026-12-12", req: "Terbuka untuk semua jurusan", link: "https://example.com", by: "seed", sample: 1 }
  ];

  const DEFAULT_THREADS = [
    { id: "t1", t: "Cara bagi waktu kuliah dan organisasi?", body: "Tugas dan rapat sering datang bareng. Kalian gimana?", name: "Contoh", campus: "Contoh", replies: [] }
  ];

  const DEFAULT_GROUPS = [
    { id: "g1", mk: "Kalkulus", jur: "Teknik Elektro", target: "Tuntas Bab Integral sebelum UAS", name: "Contoh", members: [], mats: [], goals: [] }
  ];

  // State Aplikasi (Sinkronisasi Firestore Real-time)
  let D = {
    users: [],
    posts: [],
    opps: [...DEFAULT_OPPS],
    threads: [...DEFAULT_THREADS],
    groups: [...DEFAULT_GROUPS],
    msgs: []
  };

  let myPrivateData = {
    sched: [],
    todos: [],
    notes: [],
    saved: [],
    ipk: [],
    streakLogs: []
  };

  let S = null; // ID akun aktif
  let V = "home", PV = "home", TAB = "all", OT = null, Q = "", MODE = "login", DEL = 0, FT = "people", UID = null, EID = null, CID = null;
  let unsubPrivate = null;
  let openComments = {};
  let draftMedia = { type: null, src: "" };
  let showVidInput = false;

  // State Timer Pomodoro 25 Menit
  let pomoSec = 25 * 60;
  let pomoRunning = false;
  let pomoInterval = null;

  const me = () => D.users.find(u => u.id === S);
  const U = id => D.users.find(x => x.id === id);

  // Helper Path Firestore (Aturan Wajib: /artifacts/{appId}/public/data/{col} & /artifacts/{appId}/users/{uid}/{col})
  const pubCol = name => collection(db, 'artifacts', appId, 'public', 'data', name);
  const pubDoc = (name, id) => doc(db, 'artifacts', appId, 'public', 'data', name, id);
  const privDoc = () => doc(db, 'artifacts', appId, 'users', auth.currentUser.uid, 'profile', 'private_data');

  // Seed data awal jika database masih kosong
  async function ensureSeedData() {
    if (!auth.currentUser) return;
    try {
      const seedRef = doc(db, 'artifacts', appId, 'public', 'data', 'meta', 'seeded');
      const snap = await getDoc(seedRef);
      if (!snap.exists()) {
        await setDoc(seedRef, { done: true, ts: new Date().toISOString() });
        for (const o of DEFAULT_OPPS) {
          await setDoc(pubDoc('opps', o.id), o);
        }
        for (const th of DEFAULT_THREADS) {
          await setDoc(pubDoc('threads', th.id), th);
        }
        for (const gr of DEFAULT_GROUPS) {
          await setDoc(pubDoc('groups', gr.id), gr);
        }
      }
    } catch (e) {
      console.error("Seed check error:", e);
    }
  }

  // Listener Data Publik Real-time
  function initPublicListeners() {
    if (!auth.currentUser) return;

    onSnapshot(pubCol('users'), snap => {
      D.users = snap.docs.map(d => ({ id: d.id, ...d.data() }));
      render();
    }, err => console.error("Users listener error:", err));

    onSnapshot(pubCol('posts'), snap => {
      D.posts = snap.docs
        .map(d => ({ id: d.id, ...d.data() }))
        .sort((a, b) => (b.ts || "").localeCompare(a.ts || ""));
      render();
    }, err => console.error("Posts listener error:", err));

    onSnapshot(pubCol('opps'), snap => {
      if (!snap.empty) {
        D.opps = snap.docs.map(d => ({ id: d.id, ...d.data() }));
        render();
      }
    }, err => console.error("Opps listener error:", err));

    onSnapshot(pubCol('threads'), snap => {
      if (!snap.empty) {
        D.threads = snap.docs
          .map(d => ({ id: d.id, ...d.data() }))
          .sort((a, b) => (b.ts || "").localeCompare(a.ts || ""));
        render();
      }
    }, err => console.error("Threads listener error:", err));

    onSnapshot(pubCol('groups'), snap => {
      if (!snap.empty) {
        D.groups = snap.docs.map(d => ({ id: d.id, ...d.data() }));
        render();
      }
    }, err => console.error("Groups listener error:", err));

    onSnapshot(pubCol('msgs'), snap => {
      D.msgs = snap.docs
        .map(d => ({ id: d.id, ...d.data() }))
        .sort((a, b) => (a.ts || "").localeCompare(b.ts || ""));
      render();
    }, err => console.error("Msgs listener error:", err));
  }

  // Listener Data Pribadi (Jadwal, Tugas, Catatan, IPK, Simpanan, Streak)
  function attachPrivateListener() {
    if (!auth.currentUser) return;
    if (unsubPrivate) unsubPrivate();
    unsubPrivate = onSnapshot(privDoc(), snap => {
      if (snap.exists()) {
        const data = snap.data();
        myPrivateData = {
          sched: data.sched || [],
          todos: data.todos || [],
          notes: data.notes || [],
          saved: data.saved || [],
          ipk: data.ipk || [],
          streakLogs: data.streakLogs || []
        };
      } else {
        myPrivateData = { sched: [], todos: [], notes: [], saved: [], ipk: [], streakLogs: [] };
      }
      render();
    }, err => console.error("Private data listener error:", err));
  }

  async function savePrivateData(updater) {
    if (!auth.currentUser) return;
    updater(myPrivateData);
    render();
    try {
      await setDoc(privDoc(), myPrivateData, { merge: true });
    } catch (e) {
      console.error("Error saving private data:", e);
    }
  }

  // Autentikasi Firebase Awal
  async function bootstrapAuth() {
    try {
      if (typeof __initial_auth_token !== 'undefined' && __initial_auth_token) {
        await signInWithCustomToken(auth, __initial_auth_token);
      } else {
        await signInAnonymously(auth);
      }
    } catch (e) {
      console.error("Auth failed:", e);
    }
  }

  onAuthStateChanged(auth, async (user) => {
    if (user) {
      await ensureSeedData();
      initPublicListeners();
      attachPrivateListener();
      try {
        const sessSnap = await getDoc(doc(db, 'artifacts', appId, 'users', user.uid, 'profile', 'session'));
        if (sessSnap.exists() && sessSnap.data().activeProfileId) {
          S = sessSnap.data().activeProfileId;
          if (sessSnap.data().lang) LG = sessSnap.data().lang;
          if (sessSnap.data().theme) applyTheme(sessSnap.data().theme, false);
        }
      } catch (e) {}
      render();
    }
  });

  // Helper Kriptografi & Validasi
  async function sha(s) {
    try {
      const b = await crypto.subtle.digest("SHA-256", new TextEncoder().encode("tk:" + s));
      return [...new Uint8Array(b)].map(x => x.toString(16).padStart(2, "0")).join("");
    } catch (e) {
      return btoa(s);
    }
  }

  const normId = v => {
    v = v.trim().toLowerCase();
    if (/^\S+@\S+\.\S+$/.test(v)) return v;
    const p = v.replace(/[\s-]/g, "");
    return /^\+?\d{9,15}$/.test(p) ? p : null;
  };

  const val = i => ($("#" + i)?.value || "").trim();
  const er = m => { const el = $("#err"); if (el) el.textContent = m; };

  // Logo Mahasiswa Minimalis + Monogram TK
  const tkLogo = (size = 34) => `<svg width="${size}" height="${size}" viewBox="0 0 48 48" fill="none" aria-hidden="true" style="flex-shrink:0">
    <rect width="48" height="48" rx="13" fill="#1a8fe3"/>
    <path d="M24 9L8 16.5L24 24L40 16.5L24 9Z" fill="#ffc845"/>
    <path d="M36 18.5V25.5C36 27.5 30.6 30 24 30C17.4 30 12 27.5 12 25.5V18.5" stroke="#ffffff" stroke-width="2.4" stroke-linecap="round" stroke-linejoin="round"/>
    <path d="M40 16.5V24.5" stroke="#ffc845" stroke-width="2.4" stroke-linecap="round"/>
    <circle cx="40" cy="25.5" r="1.8" fill="#ffc845"/>
    <text x="24" y="41.5" text-anchor="middle" fill="#ffffff" font-family="Bricolage Grotesque, system-ui, sans-serif" font-weight="800" font-size="12.5" letter-spacing="0.5">TK</text>
  </svg>`;

  const av = (u, s = 40) => u?.photo
    ? `<img class="av" src="${u.photo}" width="${s}" height="${s}" alt="">`
    : `<span class="av" style="width:${s}px;height:${s}px;font-size:${s * .42}px">${h((u?.name || "?")[0].toUpperCase())}</span>`;

  const langSel = () => `<select aria-label="${t("lg")}" onchange="window.setLg(this.value)">
    <option value="id" ${LG == "id" ? "selected" : ""}>Indonesia</option>
    <option value="en" ${LG == "en" ? "selected" : ""}>English</option>
  </select>`;

  window.setLg = async v => {
    LG = v;
    render();
    if (auth.currentUser) {
      await setDoc(doc(db, 'artifacts', appId, 'users', auth.currentUser.uid, 'profile', 'session'), { lang: v }, { merge: true });
    }
  };

  window.applyTheme = async (valTheme, persist = true) => {
    THEME = valTheme;
    if (valTheme === "auto") document.documentElement.removeAttribute("data-theme");
    else document.documentElement.setAttribute("data-theme", valTheme);
    if (persist && auth.currentUser) {
      await setDoc(doc(db, 'artifacts', appId, 'users', auth.currentUser.uid, 'profile', 'session'), { theme: valTheme }, { merge: true });
    }
  };

  // Ilustrasi SVG Langit, Cuaca & Kampus
  const cloud = (x, y, s, c = "#fff") => `<g fill="${c}" transform="translate(${x} ${y}) scale(${s})"><ellipse cx="40" cy="30" rx="30" ry="16"/><ellipse cx="62" cy="22" rx="22" ry="16"/><ellipse cx="22" cy="24" rx="16" ry="12"/></g>`;
  const SKY = [
    `<svg viewBox="0 0 300 150" aria-hidden="true"><circle cx="210" cy="55" r="30" fill="#ffc845"/><g stroke="#ffc845" stroke-width="5" stroke-linecap="round">${[0, 45, 90, 135, 180, 225, 270, 315].map(a => `<line x1="${210 + 42 * Math.cos(a * Math.PI / 180)}" y1="${55 + 42 * Math.sin(a * Math.PI / 180)}" x2="${210 + 54 * Math.cos(a * Math.PI / 180)}" y2="${55 + 54 * Math.sin(a * Math.PI / 180)}"/>`).join("")}</g>${cloud(90, 85, .9)}${cloud(205, 100, .6)}</svg>`,
    `<svg viewBox="0 0 300 150" aria-hidden="true"><circle cx="230" cy="40" r="22" fill="#ffe08a" opacity=".7"/>${cloud(120, 30, 1.2, "#f4f7fa")}${cloud(190, 75, .9, "#dfe7ee")}${cloud(60, 85, .8, "#e9eef3")}</svg>`,
    `<svg viewBox="0 0 300 150" aria-hidden="true">${cloud(130, 10, 1.3, "#6d8195")}${cloud(60, 35, .9, "#7c8fa2")}<g class="rn" stroke="#bfe0ff" stroke-width="3" stroke-linecap="round">${Array.from({ length: 14 }, (_, i) => `<line x1="${70 + i * 14}" y1="${85 + (i % 3) * 14}" x2="${66 + i * 14}" y2="${97 + (i % 3) * 14}" style="animation-delay:${(i % 5) * .18}s"/>`).join("")}</g></svg>`,
    `<svg viewBox="0 0 300 150" aria-hidden="true">${["#e4572e", "#ffc845", "#2fa98c", "#1a8fe3", "#7a5af8"].map((c, i) => `<path d="M${60 + i * 9} 140A${90 - i * 9} ${90 - i * 9} 0 0 1 ${240 - i * 9} 140" fill="none" stroke="${c}" stroke-width="8"/>`).join("")}${cloud(30, 95, .7)}${cloud(200, 100, .7)}</svg>`
  ];

  const campusArt = `<svg viewBox="0 0 600 320" preserveAspectRatio="xMidYMax slice" aria-hidden="true">
    <circle cx="515" cy="52" r="30" fill="#ffc845"/>
    ${cloud(45, 28, 1.15)}${cloud(320, 62, .9)}${cloud(445, 105, .75)}
    <g>
      <rect x="150" y="125" width="300" height="125" fill="#f6ead6"/>
      <polygon points="135,127 300,62 465,127" fill="#c9503a"/>
      <rect x="270" y="30" width="60" height="95" fill="#f6ead6"/>
      <polygon points="262,32 300,2 338,32" fill="#c9503a"/>
      <circle cx="300" cy="60" r="13" fill="#fff" stroke="#8a6a4a" stroke-width="3"/>
      ${[175, 215, 255, 345, 385, 425].map(x => `<rect x="${x}" y="145" width="14" height="105" fill="#fff" opacity=".9"/>`).join("")}
      <rect x="278" y="180" width="44" height="70" fill="#6b4a33" rx="4"/>
    </g>
    <rect y="250" width="600" height="70" fill="#6cc27a"/>
    <path d="M270 250 L330 250 L420 320 L180 320Z" fill="#e8d8b9"/>
    <g>
      <rect x="56" y="205" width="12" height="50" fill="#7a5233"/><circle cx="62" cy="192" r="34" fill="#3f9d55"/>
      <rect x="532" y="210" width="12" height="45" fill="#7a5233"/><circle cx="538" cy="196" r="30" fill="#3f9d55"/>
    </g>
    <g>
      <circle cx="215" cy="268" r="11" fill="#f1c9a5"/><rect x="204" y="279" width="22" height="34" rx="7" fill="#1a8fe3"/><rect x="225" y="281" width="9" height="23" rx="4" fill="#ffc845"/>
      <circle cx="260" cy="274" r="10" fill="#d9a67f"/><rect x="250" y="284" width="20" height="31" rx="7" fill="#e4572e"/><rect x="240" y="285" width="9" height="21" rx="4" fill="#2d5a8a"/>
      <circle cx="400" cy="270" r="11" fill="#e8b996"/><rect x="389" y="281" width="22" height="34" rx="7" fill="#2fa98c"/><rect x="380" y="283" width="9" height="23" rx="4" fill="#ffc845"/>
    </g>
  </svg>`;

  // Tampilan Autentikasi (Masuk / Daftar Mahasiswa / Daftar Pemberi Info)
  window.setAuthMode = m => { MODE = m; authView(); };

  function authView() {
    const M = MODE, P = M === "regP", R = M !== "login";
    const f = (i, l, x = "") => `<label>${l}<input id="${i}" ${x}></label>`;
    $("#root").innerHTML = `<div class="auth">
      <div class="art">
        <div class="art-head">
          <div class="brand-lockup">${tkLogo(38)}<div>Teman <span>Kampus</span></div></div>
          <h1>${t("hh")}</h1>
          <p class="art-sub">${t("authSub")}</p>
        </div>
        <div class="art-scene">${campusArt}</div>
      </div>
      <div class="form">
        <div class="row sp" style="margin-bottom:1rem">
          <h2 style="margin:0">${t(R ? "rs" : "li")}${P ? " / " + t("rp") : ""}</h2>
          ${langSel()}
        </div>
        <div class="seg">
          <button class="${M == "login" ? "on" : ""}" onclick="window.setAuthMode('login')">${t("li")}</button>
          <button class="${M == "regS" ? "on" : ""}" onclick="window.setAuthMode('regS')">${t("rs")}</button>
          <button class="${P ? "on" : ""}" onclick="window.setAuthMode('regP')">${t("rp")}</button>
        </div>
        <div id="err" class="err" role="alert"></div>
        ${M === "regS" ? f("nm", t("nm")) + f("cp", t("sch2")) + f("jr", t("jur")) + f("sm", t("sm"), 'type="number" min="1" max="14"') : ""}
        ${P ? `<label>${t("ot")}<select id="ot">${[1, 2, 3, 4, 5].map(i => `<option value="${i}">${t("ot" + i)}</option>`).join("")}</select></label>
          ${f("on", t("on"))}${f("pic", t("pic"))}${f("web", t("web"), 'placeholder="https://"')}
          <label>${t("ds")}<textarea id="ds" rows="2"></textarea></label>` : ""}
        ${f("idn", t("idn"), 'autocomplete="username"')}
        ${f("pw", t("pwd"), 'type="password"')}
        ${P ? `<label class="row" style="margin-bottom:.6rem"><input type="checkbox" id="au"> ${t("auth")}</label><p class="mu">${t("pnote")}</p>` : ""}
        <button class="btn w" id="authBtn" onclick="${R ? `window.doReg('${M}')` : "window.doLogin()"}">${t(R ? (P ? "rp" : "rs") : "li")}</button>
        <p class="mu" style="margin-top:1rem">🌐 ${t("shareLink")}</p>
      </div>
    </div>`;
  }

  window.doReg = async m => {
    if (!auth.currentUser) return er("Sedang menghubungkan ke server...");
    const P = m === "regP", id = normId(val("idn")), pw = $("#pw").value, nm = P ? val("pic") : val("nm");
    if (!nm) return er("Isi nama dulu.");
    if (!id) return er("Email atau nomor telepon belum valid.");
    if (pw.length < 6) return er("Sandi minimal 6 karakter.");
    if (D.users.some(u => u.id_ == id)) return er("Email atau nomor ini sudah terdaftar.");

    const newId = uid();
    const u = {
      id_: id,
      pw: await sha(pw),
      role: P ? "provider" : "student",
      name: nm,
      fr: [],
      rq: [],
      sq: [],
      createdAt: new Date().toISOString()
    };

    if (P) {
      u.org = val("on");
      u.otype = $("#ot").value;
      u.web = val("web");
      u.desc = val("ds");
      u.verified = false;
      if (!u.org || !/^https?:\/\//.test(u.web)) return er("Isi nama lembaga dan situs resmi (diawali https://).");
      if (!$("#au").checked) return er("Centang pernyataan kewenangan dulu.");
    } else {
      u.campus = val("cp");
      u.jur = val("jr");
      u.sem = val("sm");
      if (!u.campus || !u.sem) return er("Isi kampus dan semester.");
    }

    const btn = $("#authBtn");
    if (btn) btn.disabled = true;

    try {
      await setDoc(pubDoc('users', newId), u);
      S = newId;
      await setDoc(doc(db, 'artifacts', appId, 'users', auth.currentUser.uid, 'profile', 'session'), { activeProfileId: S }, { merge: true });
      V = P ? "post" : "home";
      render();
    } catch (e) {
      er("Gagal mendaftar. Coba lagi.");
      if (btn) btn.disabled = false;
    }
  };

  window.doLogin = async () => {
    if (!auth.currentUser) return er("Sedang menghubungkan ke server...");
    const id = normId(val("idn"));
    const u = D.users.find(x => x.id_ === id);
    if (!u || u.pw !== await sha($("#pw").value)) return er("Email/nomor atau sandi belum cocok.");
    S = u.id;
    await setDoc(doc(db, 'artifacts', appId, 'users', auth.currentUser.uid, 'profile', 'session'), { activeProfileId: S }, { merge: true });
    V = u.role === "student" ? "home" : "post";
    render();
  };

  window.out = async () => {
    S = null;
    MODE = "login";
    if (auth.currentUser) {
      await setDoc(doc(db, 'artifacts', appId, 'users', auth.currentUser.uid, 'profile', 'session'), { activeProfileId: null }, { merge: true });
    }
    render();
  };

  // Navigasi & Render Utama
  const NAV = {
    student: [["home", "🏠"], ["sched", "🗓️"], ["todo", "✅"], ["notes", "📒"], ["opp", "🎯"], ["forum", "💬"], ["fr", "🤝"], ["ipk", "📊"], ["prof", "🙂"]],
    provider: [["post", "📣"], ["opp", "🎯"], ["prof", "🙂"]]
  };

  function render() {
    const u = me();
    if (!u) return authView();
    $("#root").innerHTML = `<div class="app">
      <nav>
        <div class="logo">${tkLogo(32)}<div>Teman <span>Kampus</span></div></div>
        ${NAV[u.role].map(([k, e]) => `<button class="${V === k ? "on" : ""}" onclick="window.go('${k}')">
          <span>${e}</span>${t(k)}${k === "fr" && u.rq?.length ? ` <span class="tag w">${u.rq.length}</span>` : ""}
        </button>`).join("")}
        <button onclick="window.out()"><span>👋</span>${t("out")}</button>
        <div class="live-badge"><span class="dot"></span>${t("live")}</div>
      </nav>
      <div>
        <div class="top">
          <div class="mob-brand">${tkLogo(28)}<span>TK</span></div>
          <input id="gq" type="search" placeholder="${t("sr")}" value="${h(Q)}" oninput="window.gs(this.value)" aria-label="${t("sr")}">
          ${langSel()}
          <a onclick="window.go('prof')" aria-label="${t("prof")}">${av(u, 34)}</a>
        </div>
        <main id="m">${V === "search" ? VIEWS.search(u) : VIEWS[V](u)}</main>
      </div>
    </div>`;
  }

  window.gs = v => {
    Q = v;
    if (v.trim() && V !== "search") {
      PV = V;
      V = "search";
      render();
      const i = $("#gq");
      i.focus();
      i.setSelectionRange(v.length, v.length);
    } else if (!v.trim() && V === "search") {
      V = PV;
      render();
    } else if (V === "search") {
      $("#m").innerHTML = VIEWS.search(me());
    }
  };

  window.go = k => { V = k; OT = null; Q = ""; DEL = 0; UID = null; EID = null; render(); };
  window.seeU = id => { UID = id; V = "user"; Q = ""; render(); };
  window.setTab = c => { TAB = c; render(); };
  window.setFT = c => { FT = c; render(); };
  window.openThread = id => { OT = id; Q = ""; V = "forum"; render(); };

  // Helper Tanggal & Cuaca
  const days = d => Math.ceil((new Date(d) - new Date(new Date().toDateString())) / 864e5);
  const dl = d => { const n = days(d); return n < 0 ? t("closed") : n === 0 ? t("td0") : n + t("dleft"); };
  const fd = d => new Date(d).toLocaleDateString(LG === "id" ? "id-ID" : "en-GB", { day: "numeric", month: "short", year: "numeric" });
  const empty = k => `<div class="card empty">${t(k)}</div>`;
  const head = (a, b) => `<h1>${t(a)}</h1>${b ? `<p class="mu" style="margin-bottom:.9rem">${t(b)}</p>` : `<div style="height:.7rem"></div>`}`;
  const od = () => myPrivateData.todos.filter(x => !x.done && x.due && days(x.due) < 0).length;

  // Perhitungan Streak Belajar Harian
  const localDateStr = (d = new Date()) => {
    const y = d.getFullYear();
    const m = String(d.getMonth() + 1).padStart(2, "0");
    const day = String(d.getDate()).padStart(2, "0");
    return `${y}-${m}-${day}`;
  };

  function calcStreak(logs = []) {
    const set = new Set(logs);
    const today = new Date();
    const todayStr = localDateStr(today);
    const yest = new Date(today);
    yest.setDate(yest.getDate() - 1);
    const yestStr = localDateStr(yest);

    let current = 0;
    let cursor = set.has(todayStr) ? new Date(today) : (set.has(yestStr) ? new Date(yest) : null);
    if (cursor) {
      while (set.has(localDateStr(cursor))) {
        current++;
        cursor.setDate(cursor.getDate() - 1);
      }
    }

    const sorted = [...set].sort();
    let best = 0, run = 0, prevTime = null;
    for (const ds of sorted) {
      const tm = new Date(ds + "T00:00:00").getTime();
      if (prevTime !== null && Math.round((tm - prevTime) / 864e5) === 1) run++;
      else run = 1;
      if (run > best) best = run;
      prevTime = tm;
    }

    const dow = today.getDay();
    const diffToMon = dow === 0 ? -6 : 1 - dow;
    const monday = new Date(today);
    monday.setDate(today.getDate() + diffToMon);
    const week = Array.from({ length: 7 }, (_, i) => {
      const d = new Date(monday);
      d.setDate(monday.getDate() + i);
      const ds = localDateStr(d);
      return {
        label: t("daysShort")[d.getDay()],
        done: set.has(ds),
        isToday: ds === todayStr
      };
    });

    return { current, best, studiedToday: set.has(todayStr), week };
  }

  function streakWidget() {
    const st = calcStreak(myPrivateData.streakLogs || []);
    const mins = String(Math.floor(pomoSec / 60)).padStart(2, "0");
    const secs = String(pomoSec % 60).padStart(2, "0");
    return `<div class="card streak-card">
      <div class="row sp">
        <div>
          <h2 style="margin:0">🔥 ${t("streakTitle")}: <span style="color:var(--pr);font-size:1.25rem">${st.current}</span> ${t("streakDays")}</h2>
          <div class="mu">${t("streakBest")}: <b>${st.best}</b> ${t("streakDays")}</div>
        </div>
        <button class="btn ${st.studiedToday ? "g" : ""} s" onclick="window.checkInStudy()" ${st.studiedToday ? "disabled" : ""}>
          ${st.studiedToday ? "✓ " + t("checkedIn") : "🔥 " + t("checkinBtn")}
        </button>
      </div>
      <div class="streak-days">
        ${st.week.map(d => `<div class="s-day ${d.done ? "on" : ""} ${d.isToday ? "today" : ""}">${d.label}<br>${d.done ? "🔥" : "·"}</div>`).join("")}
      </div>
      <div class="row sp" style="margin-top:.5rem;padding-top:.5rem;border-top:1px solid var(--bd)">
        <span class="mu">⏱️ ${t("focusTimer")}</span>
        <div class="row">
          <span class="pomo-pill" id="pomoDisplay">${mins}:${secs}</span>
          <button class="btn g s" onclick="window.togglePomo()">${pomoRunning ? t("pauseFocus") : t("startFocus")}</button>
          <button class="btn g s" onclick="window.resetPomo()">${t("resetFocus")}</button>
        </div>
      </div>
    </div>`;
  }

  function sky(u, hi) {
    const n = od();
    const todos = myPrivateData.todos;
    const s = todos.length && todos.every(x => x.done) ? 3 : n === 0 ? 0 : n < 3 ? 1 : 2;
    const hr = new Date().getHours();
    const greet = hr < 11 ? 1 : hr < 15 ? 2 : hr < 18 ? 3 : 4;
    return `<div class="sky s${s}">${SKY[s]}<div class="sk">
      ${hi ? `<h1>${t("g" + greet)}, ${h(u.name.split(" ")[0])}</h1>` : ""}
      <p style="font-weight:600;margin-top:.3rem">${t("w" + s).replace("{n}", n)}</p>
    </div></div>`;
  }

  // Komponen Kartu Konten
  function oppCard(o, u) {
    const sv = myPrivateData.saved?.includes(o.id);
    const vt = o.sample ? `<span class="tag">${t("smp")}</span>` : o.ver ? `<span class="tag ok">✓ ${t("ver")}</span>` : `<span class="tag">${t("unv")}</span>`;
    return `<div class="card">
      <div class="row sp"><div class="row"><span class="tag">${t(o.cat)}</span>${vt}</div><span class="tag w">${dl(o.deadline)}</span></div>
      <h3 style="margin-top:.5rem">${h(o.title)}</h3>
      <div class="mu">${h(o.org)} · ${fd(o.deadline)}</div>
      <p style="margin-top:.2rem">${h(o.req)}</p>
      <div class="row">
        <a href="${h(o.link)}" target="_blank" rel="noopener">${t("open")}</a>
        ${u.role === "student" ? `<button class="btn g s" onclick="window.sav('${o.id}')">${sv ? "★ " + t("saved") : "☆ " + t("save")}</button>` : ""}
        ${o.by === u.id ? `<button class="btn g s" onclick="window.delO('${o.id}')">${t("del")}</button>` : ""}
      </div>
    </div>`;
  }

  const nl = (id, n) => id && U(id) ? `<a onclick="window.seeU('${id}')">${h(n)}</a>` : h(n);

  const forumCard = x => `<div class="card">
    <h3><a onclick="window.openThread('${x.id}')">${h(x.t)}</a></h3>
    <div class="mu">${nl(x.uid, x.name)} · ${h(x.campus)} · ${(x.replies || []).length} ${t("rep")}</div>
  </div>`;

  const gp = g => {
    const a = g.goals || [], n = a.filter(x => x.d).length;
    return `<progress value="${n}" max="${a.length || 1}" style="width:100%"></progress>` +
      a.map((x, i) => `<label class="row"><input type="checkbox" ${x.d ? "checked" : ""} onchange="window.gt('${g.id}',${i})"> <span class="${x.d ? "done" : ""}">${h(x.t)}</span></label>`).join("") +
      `<div class="row"><input class="grow" id="gi${g.id}" placeholder="${t("item")}" style="margin:0"><button class="btn s" onclick="window.ga('${g.id}')">${t("add")}</button></div>`;
  };

  const groupCard = (g, u) => {
    const j = (g.members || []).includes(u.id);
    return `<div class="card">
      <div class="row sp"><h3>${h(g.mk)}</h3><span class="tag">${h(g.jur)}</span></div>
      <p>${h(g.target)}</p>
      <div class="mu">${nl(g.uid, g.name)} · ${(g.members || []).length} ${t("members")}</div>
      <button class="btn ${j ? "g" : ""} s" style="margin-top:.5rem" onclick="window.jn('${g.id}')">${j ? t("leave") : t("join")}</button>
      ${j ? `<div style="margin-top:.7rem"><b>${t("prg")}</b>${gp(g)}</div>
      <div style="margin-top:.7rem"><b>${t("mats")}</b>
        ${(g.mats || []).map(m => `<div><a href="${h(m.url)}" target="_blank" rel="noopener">${h(m.t)}</a> <span class="mu">${h(m.by)}</span></div>`).join("")}
        <div class="row" style="margin-top:.4rem">
          <input class="grow" id="mt${g.id}" placeholder="${t("mtt")}" style="margin:0">
          <input class="grow" id="mu${g.id}" placeholder="${t("mtu")}" style="margin:0">
          <button class="btn s" onclick="window.mat('${g.id}')">${t("share")}</button>
        </div>
      </div>` : ""}
    </div>`;
  };

  const renderMedia = media => {
    if (!media || !media.src) return "";
    if (media.type === "image") {
      return `<div class="post-media"><img src="${h(media.src)}" alt="Lampiran foto" loading="lazy"></div>`;
    }
    if (media.type === "video") {
      const yt = media.src.match(/(?:youtu\.be\/|youtube\.com\/(?:watch\?v=|embed\/|shorts\/))([\w-]{11})/);
      if (yt) {
        return `<div class="post-media"><iframe src="https://www.youtube.com/embed/${yt[1]}" allowfullscreen loading="lazy"></iframe></div>`;
      }
      return `<div class="post-media"><video src="${h(media.src)}" controls playsinline preload="metadata"></video></div>`;
    }
    return "";
  };

  const postCard = p => {
    const a = U(p.uid);
    if (!a) return "";
    const isLiked = (p.lk || []).includes(S);
    const isReposted = (p.reposts || []).includes(S);
    const cmts = p.comments || [];
    const cmtOpen = !!openComments[p.id];

    return `<div class="card">
      ${p.repostOf ? `<div class="repost-banner">🔁 ${t("repostedBy")} <a onclick="window.seeU('${a.id}')">${h(a.name)}</a> · ${fd(p.ts)}</div>` : ""}
      <div class="row" style="align-items:flex-start;flex-wrap:nowrap">
        <a onclick="window.seeU('${a.id}')">${av(a, 40)}</a>
        <div class="grow" style="min-width:0">
          <div class="row sp">
            <div><a onclick="window.seeU('${a.id}')"><b>${h(a.name)}</b></a> <span class="mu">· ${fd(p.ts)}</span></div>
            ${p.uid === S ? `<button class="btn g s" onclick="window.delPost('${p.id}')" title="${t("del")}">✕</button>` : ""}
          </div>
          ${p.txt ? `<div style="margin:.3rem 0;white-space:pre-wrap;word-break:break-word">${h(p.txt)}</div>` : ""}
          ${renderMedia(p.media)}
          ${p.repostOf ? `<div class="repost-quote">
            <div class="mu" style="margin-bottom:.25rem"><b>${h(p.repostOf.authorName)}</b></div>
            ${p.repostOf.txt ? `<div style="white-space:pre-wrap;font-size:.92rem">${h(p.repostOf.txt)}</div>` : ""}
            ${renderMedia(p.repostOf.media)}
          </div>` : ""}
          <div class="act-bar">
            <button class="act-btn ${isLiked ? "liked" : ""}" onclick="window.lk('${p.id}')">
              ${isLiked ? "♥" : "♡"} ${t("like")} ${(p.lk || []).length ? `(${p.lk.length})` : ""}
            </button>
            <button class="act-btn" onclick="window.toggleCmt('${p.id}')">
              💬 ${t("comment")} ${cmts.length ? `(${cmts.length})` : ""}
            </button>
            <button class="act-btn ${isReposted ? "reposted" : ""}" onclick="window.repost('${p.id}')">
              🔁 ${t("repost")} ${(p.reposts || []).length ? `(${p.reposts.length})` : ""}
            </button>
            <button class="act-btn" onclick="window.sharePost('${p.id}')">
              📤 ${t("shareAct")}
            </button>
          </div>
          ${cmtOpen ? `<div class="cmt-box">
            ${cmts.map(c => `<div class="cmt-item">
              <div class="row sp"><b>${nl(c.uid, c.name)}</b><span class="mu" style="font-size:.75rem">${c.ts ? fd(c.ts) : ""}</span></div>
              <div style="margin-top:.15rem;white-space:pre-wrap">${h(c.txt)}</div>
            </div>`).join("")}
            <div class="row" style="margin-top:.4rem">
              <input class="grow" id="ci_${p.id}" placeholder="${t("cmtPh")}" style="margin:0" onkeydown="if(event.key==='Enter')window.addCmt('${p.id}')">
              <button class="btn s" onclick="window.addCmt('${p.id}')">${t("send")}</button>
            </div>
          </div>` : ""}
        </div>
      </div>
    </div>`;
  };

  function fbtn(me_, o) {
    if (me_.id === o.id) return "";
    const a = me_.fr?.includes(o.id), s = me_.sq?.includes(o.id), r = me_.rq?.includes(o.id);
    return a
      ? `<button class="btn s" onclick="window.chat('${o.id}')">${t("msg")}</button> <button class="btn g s" onclick="window.unF('${o.id}')">✓ ${t("ffr")}</button>`
      : s
        ? `<button class="btn g s" disabled>${t("fsent")}</button>`
        : r
          ? `<button class="btn s" onclick="window.accF('${o.id}')">${t("facc")}</button>`
          : `<button class="btn s" onclick="window.reqF('${o.id}')">${t("fadd")}</button>`;
  }

  const info = o => o.role === "student" ? `${h(o.campus)}${o.jur ? " · " + h(o.jur) : ""} · ${t("sm")} ${h(o.sem)}` : h(o.org);
  const F = (i, l, x = "") => `<label>${l}<input id="${i}" ${x}></label>`;

  // Halaman-halaman Utama (VIEWS)
  const VIEWS = {
    home(u) {
      const n = new Date().getDay();
      const cl = myPrivateData.sched.filter(s => s.day == n).sort((a, b) => a.time.localeCompare(b.time));
      const tp = myPrivateData.todos.filter(x => !x.done).sort((a, b) => (a.due || "9").localeCompare(b.due || "9")).slice(0, 4);
      const rd = [
        ...myPrivateData.todos.filter(x => !x.done && x.due && days(x.due) >= 0 && days(x.due) <= 2).map(x => x.t + " · " + dl(x.due)),
        ...D.opps.filter(o => myPrivateData.saved?.includes(o.id) && days(o.deadline) >= 0 && days(o.deadline) <= 3).map(o => o.title + " · " + dl(o.deadline))
      ];
      return sky(u, 1) +
        streakWidget() +
        (rd.length ? `<div class="card" style="border-color:var(--ac)"><h2>⏰ ${t("rem")}</h2>${rd.map(x => `<div>${h(x)}</div>`).join("")}</div>` : "") +
        `<div class="grid">
          <div class="card"><h2>${t("today")}</h2>${cl.map(s => `<div><b>${h(s.time)}</b> ${h(s.mk)} <span class="mu">${h(s.room)}</span></div>`).join("") || `<p class="mu">${t("e1")}</p>`}</div>
          <div class="card"><h2>${t("due")}</h2>${tp.map(x => `<div>${h(x.t)} <span class="mu">${x.due ? fd(x.due) : ""}</span></div>`).join("") || `<p class="mu">${t("e2")}</p>`}</div>
        </div>
        <div class="card">
          <div class="row" style="flex-wrap:nowrap;align-items:flex-start">
            ${av(u, 38)}
            <textarea class="grow" id="sp" rows="2" placeholder="${t("st")}" style="margin:0;resize:vertical"></textarea>
          </div>
          ${draftMedia.src ? `<div class="media-prev">
            ${draftMedia.type === "image" ? `<img src="${h(draftMedia.src)}" alt="Preview">` : `<video src="${h(draftMedia.src)}" controls></video>`}
            <button class="btn g s" style="margin-top:.4rem" onclick="window.clearDraftMedia()">✕ ${t("del")}</button>
          </div>` : ""}
          ${showVidInput ? `<div class="row" style="margin-top:.5rem">
            <input class="grow" id="vidUrl" placeholder="${t("vidUrlPh")}" value="${draftMedia.type === "video" ? h(draftMedia.src) : ""}" oninput="window.setVidUrl(this.value)" style="margin:0">
          </div>` : ""}
          <div class="row sp" style="margin-top:.6rem">
            <div class="row">
              <label class="btn g s" style="cursor:pointer">🖼️ ${t("addImg")}<input type="file" accept="image/*" hidden onchange="window.pickPostImg(event)"></label>
              <label class="btn g s" style="cursor:pointer">🎬 ${t("addVid")}<input type="file" accept="video/*" hidden onchange="window.pickPostVid(event)"></label>
              <button class="btn g s" type="button" onclick="window.toggleVidUrl()">🔗 URL Video</button>
            </div>
            <button class="btn" onclick="window.addP()">${t("share")}</button>
          </div>
        </div>
        ${D.posts.map(postCard).join("") || empty("e6")}`;
    },
    sched(u) {
      const D_ = DAYS[LG];
      const sc = myPrivateData.sched;
      return head("sched") + `<div class="card"><div class="row">
        <select id="sd" style="width:auto;margin:0">${D_.slice(1).map((d, i) => `<option value="${i + 1}">${d}</option>`).join("")}</select>
        <input id="st" type="time" style="width:auto;margin:0">
        <input class="grow" id="sm" placeholder="${t("course")}" style="margin:0">
        <input id="sr" placeholder="${t("room")}" style="width:100px;margin:0">
        <button class="btn" onclick="window.addS()">${t("add")}</button>
      </div></div>` +
      (sc.length ? D_.slice(1).map((d, i) => {
        const l = sc.filter(s => s.day == i + 1).sort((a, b) => a.time.localeCompare(b.time));
        return l.length ? `<div class="card"><h3>${d}</h3>${l.map(s => `<div class="row sp"><span><b>${h(s.time)}</b> ${h(s.mk)} <span class="mu">${h(s.room)}</span></span><button class="btn g s" onclick="window.delPriv('sched','${s.id}')">${t("del")}</button></div>`).join("")}</div>` : "";
      }).join("") : empty("e1"));
    },
    todo(u) {
      const todos = myPrivateData.todos;
      const ET = todos.find(x => x.id === EID);
      return sky(u, 0) + `<div class="card"><div class="row">
        <input class="grow" id="tt" placeholder="${t("task")}" value="${h(ET?.t)}" style="margin:0">
        <input id="td" type="date" value="${ET?.due || ""}" style="width:auto;margin:0">
        <label class="row"><input type="checkbox" id="th" ${ET?.hi ? "checked" : ""}> ${t("hi")}</label>
        <button class="btn" onclick="window.addT()">${ET ? t("save") : t("add")}</button>
      </div></div>` +
      (todos.map(x => `<div class="card row sp">
        <label class="row"><input type="checkbox" ${x.done ? "checked" : ""} onchange="window.tgTodo('${x.id}')"><span class="${x.done ? "done" : ""}">${x.hi ? "❗ " : ""}${h(x.t)}</span> <span class="${!x.done && x.due && days(x.due) < 0 ? "tag w" : "mu"}">${x.due ? fd(x.due) : ""}</span></label>
        <span class="row"><button class="btn g s" onclick="window.edT('${x.id}')">${t("edit2")}</button><button class="btn g s" onclick="window.delPriv('todos','${x.id}')">${t("del")}</button></span>
      </div>`).join("") || empty("e2"));
    },
    notes(u) {
      const notes = myPrivateData.notes;
      const EN = notes.find(x => x.id === EID);
      return head("notes", "nts") + `<div class="card">
        <input id="nt" value="${h(EN?.t)}" placeholder="${t("title")}">
        <textarea id="nb" rows="3" placeholder="${t("body")}">${h(EN?.body)}</textarea>
        <button class="btn" onclick="window.addN()">${t("save")}</button>
      </div>` +
      (notes.map(n => `<div class="card"><div class="row sp"><h3>${h(n.t)}</h3><span class="row"><button class="btn g s" onclick="window.edT('${n.id}')">${t("edit2")}</button><button class="btn g s" onclick="window.delPriv('notes','${n.id}')">${t("del")}</button></span></div><div style="white-space:pre-wrap">${h(n.body)}</div></div>`).join("") || empty("e3"));
    },
    opp(u) {
      const k = (u.jur || "").toLowerCase().split(/\s+/).filter(w => w.length > 3);
      const l = D.opps.filter(o => TAB === "sv"
        ? myPrivateData.saved?.includes(o.id)
        : days(o.deadline) >= 0 && (TAB === "all" || o.cat === TAB || (TAB === "fy" && (!k.length || /semua jurusan/i.test(o.req) || k.some(w => (o.title + o.org + o.req).toLowerCase().includes(w)))))
      ).sort((a, b) => a.deadline.localeCompare(b.deadline));
      return head("opps") + `<div class="tabs">${["all", "fy", ...CATS, "sv"].map(c => `<button class="btn ${TAB === c ? "" : "g"} s" onclick="window.setTab('${c}')">${c === "all" ? t("all") : c === "sv" ? "★ " + t("saved") : c === "fy" ? "✦ " + t("fy") : t(c)}</button>`).join("")}</div>${l.map(o => oppCard(o, u)).join("") || empty("e4")}`;
    },
    post(u) {
      const m = D.opps.filter(o => o.by === u.id);
      return head("ps") + `<div class="card"><div id="err" class="err"></div>
        <label>${t("cat")}<select id="pc">${CATS.map(c => `<option value="${c}">${t(c)}</option>`).join("")}</select></label>
        ${F("pt", t("title"))}${F("pd", t("dl"), 'type="date"')}
        <label>${t("req")}<textarea id="pq" rows="3"></textarea></label>
        ${F("pl", t("lk"), 'placeholder="https://"')}
        <button class="btn" onclick="window.addO()">${t("pub")}</button>
      </div><h2>${t("mine")}</h2>${m.map(o => oppCard(o, u)).join("") || empty("e4")}`;
    },
    forum(u) {
      if (OT) {
        const x = D.threads.find(y => y.id === OT);
        if (!x) { OT = null; return VIEWS.forum(u); }
        return `<button class="btn g s" onclick="window.openThread(null)">← ${t("back")}</button>
          <div class="card" style="margin-top:.8rem"><h2>${h(x.t)}</h2><div class="mu">${nl(x.uid, x.name)} · ${h(x.campus)}</div><p>${h(x.body)}</p></div>
          ${(x.replies || []).map(r => `<div class="card"><b>${nl(r.uid, r.name)}</b> <span class="mu">${h(r.campus)}</span><div>${h(r.txt)}</div></div>`).join("")}
          <div class="card"><textarea id="rp" rows="3" placeholder="${t("wr")}"></textarea><button class="btn" onclick="window.rep('${x.id}')">${t("send")}</button></div>`;
      }
      return head("forum") + `<div class="card">
        <input id="ft" placeholder="${t("fq")}">
        <textarea id="fb" rows="2" placeholder="${t("fb")}"></textarea>
        <button class="btn" onclick="window.addF()">${t("mk")}</button>
      </div>${D.threads.map(forumCard).join("")}`;
    },
    fr(u) {
      const ps = D.users.filter(x => x.role === "student" && x.id !== u.id);
      const rq = ps.filter(x => (u.rq || []).includes(x.id));
      return head("fr") + `<div class="tabs">${["people", "study"].map(c => `<button class="btn ${FT === c ? "" : "g"} s" onclick="window.setFT('${c}')">${t(c)}</button>`).join("")}</div>` +
        (FT === "people"
          ? (rq.length ? `<h2>${t("reqs")}</h2>` + rq.map(o => `<div class="card row sp"><a class="row" onclick="window.seeU('${o.id}')">${av(o, 38)}<span>${h(o.name)}</span></a>${fbtn(u, o)}</div>`).join("") : "") +
            (ps.map(o => `<div class="card row sp"><a class="row" onclick="window.seeU('${o.id}')">${av(o, 42)}<span><b>${h(o.name)}</b><br><span class="mu">${info(o)}</span></span></a>${fbtn(u, o)}</div>`).join("") || empty("e5"))
          : `<div class="card"><h3>${t("nb")}</h3><div class="grid"><input id="gm" placeholder="${t("course")}"><input id="gj" placeholder="${t("jur")}"></div><input id="gt" placeholder="${t("tg")}"><button class="btn" onclick="window.addG()">${t("add")}</button></div>${D.groups.map(g => groupCard(g, u)).join("")}`);
    },
    user(u) {
      const o = U(UID);
      if (!o) return empty("e5");
      const lock = o.priv && !(u.fr || []).includes(o.id);
      return `<button class="btn g s" onclick="window.go('fr')">← ${t("back")}</button>
        <div class="card row" style="margin-top:.8rem;flex-wrap:nowrap">${av(o, 84)}
          <div class="grow">
            <h1>${h(o.name)}</h1>
            <div class="mu">${info(o)}</div>
            <p>${lock ? "" : h(o.bio || o.desc || "")}</p>
            <div class="row"><span class="tag">${(o.fr || []).length} ${t("friends")}</span>${fbtn(u, o)}</div>
          </div>
        </div>${lock ? "" : D.posts.filter(p => p.uid === o.id).map(postCard).join("")}`;
    },
    ipk(u) {
      const L_ = myPrivateData.ipk || [];
      const P = { A: 4, B: 3, C: 2, D: 1, E: 0 };
      const cal = a => {
        const s = a.reduce((x, y) => x + +y.sks, 0);
        return s ? (a.reduce((x, y) => x + +y.sks * P[y.gr], 0) / s).toFixed(2) : "–";
      };
      const ss = [...new Set(L_.map(x => x.sm))].sort((a, b) => a - b);
      return head("ipk") + `<div class="card"><div class="row">
        <input class="grow" id="ik" placeholder="${t("course")}" style="margin:0">
        <input id="is" type="number" min="1" max="6" placeholder="${t("sks")}" style="width:80px;margin:0">
        <select id="ig" style="width:auto;margin:0">${Object.keys(P).map(k => `<option>${k}</option>`).join("")}</select>
        <input id="im" type="number" min="1" max="14" value="${u.sem || 1}" style="width:80px;margin:0" aria-label="${t("sm")}">
        <button class="btn" onclick="window.addI()">${t("add")}</button>
      </div></div>
      <div class="card"><h2>${t("ipkt")}: ${cal(L_)}</h2>
        ${ss.map(s => {
          const a = L_.filter(x => x.sm == s);
          return `<h3 style="margin-top:.7rem">${t("sm")} ${s} · ${t("ip")} ${cal(a)}</h3>` +
            a.map(x => `<div class="row sp"><span>${h(x.mk)} <span class="mu">${x.sks} ${t("sks")} · ${x.gr}</span></span><button class="btn g s" onclick="window.delI('${x.id}')">${t("del")}</button></div>`).join("");
        }).join("")}
      </div>`;
    },
    chat(u) {
      const o = U(CID);
      if (!o || !(u.fr || []).includes(o.id)) return empty("e5");
      const m = D.msgs.filter(x => (x.f === u.id && x.to === o.id) || (x.f === o.id && x.to === u.id));
      return `<button class="btn g s" onclick="window.go('fr')">← ${t("back")}</button>
        <h2 style="margin:.8rem 0">${h(o.name)}</h2>
        ${m.map(x => `<div class="card" style="max-width:80%;${x.f === u.id ? "margin-left:auto;background:var(--sf)" : ""}">${h(x.txt)}<div class="mu">${new Date(x.ts).toLocaleTimeString([], { hour: "2-digit", minute: "2-digit" })}</div></div>`).join("") || empty("nomsg")}
        <div class="row"><input class="grow" id="mg" placeholder="${t("mw")}" style="margin:0" onkeydown="if(event.key==='Enter')window.sendM()"><button class="btn" onclick="window.sendM()">${t("send")}</button></div>`;
    },
    search(u) {
      const q = Q.trim().toLowerCase(), m = s => s.toLowerCase().includes(q);
      const o = D.opps.filter(x => m(x.title + x.org + x.cat + x.req));
      const f = D.threads.filter(x => m(x.t + x.body));
      const g = D.groups.filter(x => m(x.mk + x.jur + x.target));
      const p = D.users.filter(x => x.role === "student" && x.id !== u.id && m(x.name + x.campus + (x.jur || "")));
      return `<h1 style="margin:.5rem 0 .8rem">“${h(Q)}”</h1>` +
        (o.length + f.length + g.length + p.length
          ? (p.length ? `<h2>${t("people")}</h2>` + p.map(x => `<div class="card row sp"><a class="row" onclick="window.seeU('${x.id}')">${av(x, 38)}<span>${h(x.name)}<br><span class="mu">${info(x)}</span></span></a>${fbtn(u, x)}</div>`).join("") : "") +
            (o.length ? `<h2>${t("opp")}</h2>` + o.map(x => oppCard(x, u)).join("") : "") +
            (f.length ? `<h2>${t("forum")}</h2>` + f.map(forumCard).join("") : "") +
            (g.length ? `<h2>${t("study")}</h2>` + g.map(x => groupCard(x, u)).join("") : "")
          : empty("e5"));
    },
    prof(u) {
      const S_ = u.role === "student";
      return `<div class="card row" style="flex-wrap:nowrap;margin-top:.5rem">${av(u, 84)}
          <div class="grow"><h1>${h(u.name)}</h1><div class="mu">${info(u)}</div>
          <div class="row" style="margin-top:.4rem"><span class="tag">${(u.fr || []).length} ${t("friends")}</span>
          <label class="btn g s" style="cursor:pointer">${t("photo")}<input type="file" accept="image/*" hidden onchange="window.pho(event)"></label></div></div>
        </div>
        <p class="mu">${S_ ? t("priv") + " " : ""}${t("pubn")}</p>
        <div class="card"><h2>${t("edit")}</h2><div id="ms" class="err" style="color:var(--ok)"></div>
          ${F("pn", t("nm"), `value="${h(u.name)}"`)}
          ${S_ ? F("pcp", t("cp"), `value="${h(u.campus)}"`) + F("pj", t("jur"), `value="${h(u.jur || "")}"`) + F("ps", t("sm"), `type="number" value="${h(u.sem)}"`) : F("po", t("on"), `value="${h(u.org)}"`) + F("pw_", t("web"), `value="${h(u.web || "")}"`)}
          <label>${t("bio")}<textarea id="pb" rows="2">${h((S_ ? u.bio : u.desc) || "")}</textarea></label>
          <label class="row" style="margin-bottom:.7rem"><input type="checkbox" id="pv" ${u.priv ? "checked" : ""}> ${t("prv")}</label>
          <button class="btn" onclick="window.saveP()">${t("save")}</button>
        </div>
        <div class="card"><h2>${t("lg")}</h2>${langSel()}
          <h2 style="margin-top:.8rem">${t("tm")}</h2>
          <select onchange="window.applyTheme(this.value)">
            <option value="auto" ${THEME === "auto" ? "selected" : ""}>${t("tm0")}</option>
            <option value="light" ${THEME === "light" ? "selected" : ""}>${t("tm1")}</option>
            <option value="dark" ${THEME === "dark" ? "selected" : ""}>${t("tm2")}</option>
          </select>
        </div>
        <div class="card"><h2>${t("pw")}</h2>${F("o0", t("pw0"), 'type="password"')}${F("n0", t("pw1"), 'type="password"')}<button class="btn g" onclick="window.chPw()">${t("save")}</button><div id="pm" class="err"></div></div>
        <div class="card"><button class="btn g" onclick="window.delA()">${DEL ? t("da2") : t("da")}</button></div>`;
    }
  };

  // Aksi Profil & Akun
  window.pho = e => {
    const f = e.target.files[0];
    if (!f) return;
    const r = new FileReader();
    r.onload = () => {
      const i = new Image();
      i.onload = async () => {
        const c = document.createElement("canvas");
        c.width = c.height = 160;
        const s = Math.min(i.width, i.height);
        c.getContext("2d").drawImage(i, (i.width - s) / 2, (i.height - s) / 2, s, s, 0, 0, 160, 160);
        await updateDoc(pubDoc('users', S), { photo: c.toDataURL("image/jpeg", .8) });
        showToast(t("ok"));
      };
      i.src = r.result;
    };
    r.readAsDataURL(f);
  };

  window.saveP = async () => {
    const u = me();
    const upd = { name: val("pn") || u.name, priv: $("#pv").checked };
    if (u.role === "student") {
      upd.campus = val("pcp") || u.campus;
      upd.jur = val("pj");
      upd.sem = val("ps") || u.sem;
      upd.bio = val("pb");
    } else {
      upd.org = val("po") || u.org;
      upd.web = val("pw_");
      upd.desc = val("pb");
    }
    await updateDoc(pubDoc('users', S), upd);
    const ms = $("#ms");
    if (ms) ms.textContent = "✓ " + t("ok");
  };

  window.chPw = async () => {
    const u = me(), n = $("#n0").value;
    if (u.pw !== await sha($("#o0").value)) return $("#pm").textContent = "Sandi lama salah.";
    if (n.length < 6) return $("#pm").textContent = "Minimal 6 karakter.";
    await updateDoc(pubDoc('users', S), { pw: await sha(n) });
    showToast(t("ok"));
  };

  window.delA = async () => {
    if (!DEL) { DEL = 1; return render(); }
    await deleteDoc(pubDoc('users', S));
    DEL = 0;
    window.out();
  };

  // Aksi Pertemanan & Chat Real-time
  const rm = (a, x) => (a || []).filter(y => y !== x);
  window.reqF = async id => {
    const m = me(), o = U(id);
    await updateDoc(pubDoc('users', m.id), { sq: [...rm(m.sq, id), id] });
    await updateDoc(pubDoc('users', id), { rq: [...rm(o.rq, m.id), m.id] });
  };
  window.accF = async id => {
    const m = me(), o = U(id);
    await updateDoc(pubDoc('users', m.id), { rq: rm(m.rq, id), fr: [...rm(m.fr, id), id] });
    await updateDoc(pubDoc('users', id), { sq: rm(o.sq, m.id), fr: [...rm(o.fr, m.id), m.id] });
  };
  window.unF = async id => {
    const m = me(), o = U(id);
    await updateDoc(pubDoc('users', m.id), { fr: rm(m.fr, id) });
    await updateDoc(pubDoc('users', id), { fr: rm(o.fr, m.id) });
  };
  window.chat = id => { CID = id; V = "chat"; Q = ""; render(); };
  window.sendM = async () => {
    const x = val("mg");
    if (!x) return;
    $("#mg").value = "";
    await addDoc(pubCol('msgs'), { f: S, to: CID, txt: x, ts: new Date().toISOString() });
  };

  // Aksi Streak Belajar & Timer Fokus
  window.checkInStudy = () => {
    const todayStr = localDateStr();
    if ((myPrivateData.streakLogs || []).includes(todayStr)) return;
    savePrivateData(d => {
      d.streakLogs = [...new Set([...(d.streakLogs || []), todayStr])];
    });
    showToast(t("checkinToast"));
  };

  window.togglePomo = () => {
    if (pomoRunning) {
      pomoRunning = false;
      clearInterval(pomoInterval);
      render();
      return;
    }
    pomoRunning = true;
    render();
    pomoInterval = setInterval(() => {
      if (pomoSec > 0) {
        pomoSec--;
        const el = $("#pomoDisplay");
        if (el) {
          el.textContent = `${String(Math.floor(pomoSec / 60)).padStart(2, "0")}:${String(pomoSec % 60).padStart(2, "0")}`;
        }
      } else {
        clearInterval(pomoInterval);
        pomoRunning = false;
        pomoSec = 25 * 60;
        window.checkInStudy();
        render();
      }
    }, 1000);
  };

  window.resetPomo = () => {
    clearInterval(pomoInterval);
    pomoRunning = false;
    pomoSec = 25 * 60;
    render();
  };

  // Aksi Postingan Sosial (Teks, Foto, Video, Like, Komentar, Repost, Share)
  window.pickPostImg = e => {
    const f = e.target.files[0];
    if (!f) return;
    const r = new FileReader();
    r.onload = () => {
      const i = new Image();
      i.onload = () => {
        const maxW = 720;
        const scale = Math.min(1, maxW / i.width);
        const c = document.createElement("canvas");
        c.width = Math.round(i.width * scale);
        c.height = Math.round(i.height * scale);
        c.getContext("2d").drawImage(i, 0, 0, c.width, c.height);
        draftMedia = { type: "image", src: c.toDataURL("image/jpeg", 0.72) };
        showVidInput = false;
        render();
      };
      i.src = r.result;
    };
    r.readAsDataURL(f);
  };

  window.pickPostVid = e => {
    const f = e.target.files[0];
    if (!f) return;
    if (f.size > 700 * 1024) {
      showToast("Ukuran file video maks 700KB, atau gunakan tautan YouTube/MP4.");
      showVidInput = true;
      render();
      return;
    }
    const r = new FileReader();
    r.onload = () => {
      draftMedia = { type: "video", src: r.result };
      showVidInput = false;
      render();
    };
    r.readAsDataURL(f);
  };

  window.toggleVidUrl = () => {
    showVidInput = !showVidInput;
    render();
  };

  window.setVidUrl = v => {
    v = v.trim();
    if (v) draftMedia = { type: "video", src: v };
    else draftMedia = { type: null, src: "" };
  };

  window.clearDraftMedia = () => {
    draftMedia = { type: null, src: "" };
    showVidInput = false;
    render();
  };

  window.addP = async () => {
    const x = val("sp");
    const hasMedia = draftMedia && draftMedia.src;
    if (!x && !hasMedia) return;
    const payload = {
      uid: S,
      txt: x,
      lk: [],
      comments: [],
      reposts: [],
      ts: new Date().toISOString()
    };
    if (hasMedia) payload.media = { ...draftMedia };
    $("#sp").value = "";
    draftMedia = { type: null, src: "" };
    showVidInput = false;
    await addDoc(pubCol('posts'), payload);
  };

  window.delPost = async id => {
    await deleteDoc(pubDoc('posts', id));
  };

  window.lk = async id => {
    const p = D.posts.find(x => x.id === id);
    if (!p) return;
    const lkArr = [...(p.lk || [])];
    const i = lkArr.indexOf(S);
    i < 0 ? lkArr.push(S) : lkArr.splice(i, 1);
    await updateDoc(pubDoc('posts', id), { lk: lkArr });
  };

  window.toggleCmt = id => {
    openComments[id] = !openComments[id];
    render();
  };

  window.addCmt = async id => {
    const inp = $("#ci_" + id);
    const txt = (inp?.value || "").trim();
    if (!txt) return;
    const p = D.posts.find(x => x.id === id);
    if (!p) return;
    inp.value = "";
    const u = me();
    const comments = [...(p.comments || []), {
      uid: u.id,
      name: u.name,
      txt,
      ts: new Date().toISOString()
    }];
    await updateDoc(pubDoc('posts', id), { comments });
  };

  window.repost = async id => {
    const p = D.posts.find(x => x.id === id);
    if (!p) return;
    const origAuthor = U(p.uid);
    const repostsArr = [...(p.reposts || [])];
    if (!repostsArr.includes(S)) {
      repostsArr.push(S);
      await updateDoc(pubDoc('posts', id), { reposts: repostsArr });
    }
    const quoteSource = p.repostOf ? p.repostOf : {
      authorId: p.uid,
      authorName: origAuthor?.name || "Mahasiswa",
      txt: p.txt || "",
      media: p.media || null
    };
    await addDoc(pubCol('posts'), {
      uid: S,
      txt: "",
      repostOf: quoteSource,
      lk: [],
      comments: [],
      reposts: [],
      ts: new Date().toISOString()
    });
    showToast(t("repostedToast"));
  };

  window.sharePost = id => {
    const p = D.posts.find(x => x.id === id);
    if (!p) return;
    const author = U(p.uid)?.name || "Teman Kampus";
    const bodyText = p.repostOf ? p.repostOf.txt : p.txt;
    const shareStr = `[Teman Kampus - ${author}]\n${bodyText || "(Postingan Media)"}\n${window.location.href}`;
    const ta = document.createElement("textarea");
    ta.value = shareStr;
    ta.style.position = "fixed";
    ta.style.opacity = "0";
    document.body.appendChild(ta);
    ta.select();
    try {
      document.execCommand("copy");
      showToast(t("copied"));
    } catch (e) {
      showToast(t("copied"));
    }
    ta.remove();
  };

  // Aksi Akademik Pribadi (Jadwal, Tugas, Catatan, IPK, Simpan Peluang)
  window.addS = () => {
    const mk = val("sm"), tm = val("st");
    if (!mk || !tm) return;
    savePrivateData(d => d.sched.push({ id: uid(), day: $("#sd").value, time: tm, mk, room: val("sr") }));
  };

  window.addT = () => {
    const x = val("tt");
    if (!x) return;
    const hi = $("#th").checked;
    savePrivateData(d => {
      const e = d.todos.find(y => y.id === EID);
      if (e) Object.assign(e, { t: x, due: val("td"), hi });
      else d.todos.push({ id: uid(), t: x, due: val("td"), done: false, hi });
      EID = null;
    });
  };

  window.edT = id => { EID = id; render(); };
  window.tgTodo = id => savePrivateData(d => {
    const x = d.todos.find(y => y.id === id);
    if (x) {
      x.done = !x.done;
      if (x.done) {
        const todayStr = localDateStr();
        d.streakLogs = [...new Set([...(d.streakLogs || []), todayStr])];
      }
    }
  });
  window.delPriv = (k, id) => savePrivateData(d => { d[k] = d[k].filter(x => x.id !== id); });

  window.addN = () => {
    const x = val("nt");
    if (!x) return;
    savePrivateData(d => {
      const e = d.notes.find(y => y.id === EID);
      if (e) Object.assign(e, { t: x, body: val("nb") });
      else d.notes.unshift({ id: uid(), t: x, body: val("nb") });
      EID = null;
    });
  };

  window.sav = id => savePrivateData(d => {
    d.saved = d.saved || [];
    const i = d.saved.indexOf(id);
    i < 0 ? d.saved.push(id) : d.saved.splice(i, 1);
  });

  window.addI = () => {
    const mk = val("ik"), s = +val("is");
    if (!mk || !s) return;
    const u = me();
    savePrivateData(d => (d.ipk = d.ipk || []).push({ id: uid(), mk, sks: s, gr: $("#ig").value, sm: val("im") || u.sem }));
  };
  window.delI = id => savePrivateData(d => { d.ipk = (d.ipk || []).filter(x => x.id !== id); });

  // Aksi Peluang, Forum & Grup Belajar Real-time
  window.addO = async () => {
    const x = val("pt"), d = val("pd"), l = val("pl");
    if (!x || !d || !/^https?:\/\//.test(l)) return er("Isi judul, batas daftar, dan tautan (diawali https://).");
    const u = me();
    await addDoc(pubCol('opps'), {
      cat: $("#pc").value,
      title: x,
      org: u.org,
      deadline: d,
      req: val("pq"),
      link: l,
      by: u.id,
      ver: !!u.verified
    });
    $("#pt").value = ""; $("#pq").value = ""; $("#pl").value = "";
    showToast(t("ok"));
  };
  window.delO = async id => { await deleteDoc(pubDoc('opps', id)); };

  const pub = u => ({ uid: u.id, name: u.name, campus: u.campus || u.org || "" });
  window.addF = async () => {
    const x = val("ft");
    if (!x) return;
    const u = me();
    await addDoc(pubCol('threads'), { t: x, body: val("fb"), ...pub(u), replies: [], ts: new Date().toISOString() });
    $("#ft").value = ""; $("#fb").value = "";
  };
  window.rep = async id => {
    const x = val("rp");
    if (!x) return;
    const th = D.threads.find(y => y.id === id);
    const u = me();
    await updateDoc(pubDoc('threads', id), { replies: [...(th.replies || []), { ...pub(u), txt: x }] });
    $("#rp").value = "";
  };

  window.addG = async () => {
    const mk = val("gm"), x = val("gt");
    if (!mk || !x) return;
    const u = me();
    await addDoc(pubCol('groups'), {
      uid: u.id,
      mk,
      jur: val("gj") || "Lintas jurusan",
      target: x,
      name: u.name,
      members: [u.id],
      mats: [],
      goals: []
    });
    $("#gm").value = ""; $("#gj").value = ""; $("#gt").value = "";
  };
  window.jn = async id => {
    const g = D.groups.find(x => x.id === id);
    const mems = [...(g.members || [])];
    const i = mems.indexOf(S);
    i < 0 ? mems.push(S) : mems.splice(i, 1);
    await updateDoc(pubDoc('groups', id), { members: mems });
  };
  window.gt = async (id, i) => {
    const g = D.groups.find(y => y.id === id);
    const goals = [...(g.goals || [])];
    goals[i] = { ...goals[i], d: !goals[i].d };
    await updateDoc(pubDoc('groups', id), { goals });
  };
  window.ga = async id => {
    const x = val("gi" + id);
    if (!x) return;
    const g = D.groups.find(y => y.id === id);
    await updateDoc(pubDoc('groups', id), { goals: [...(g.goals || []), { t: x, d: 0 }] });
  };
  window.mat = async id => {
    const x = val("mt" + id), url = val("mu" + id);
    if (!x || !/^https?:\/\//.test(url)) return;
    const g = D.groups.find(y => y.id === id);
    const u = me();
    await updateDoc(pubDoc('groups', id), { mats: [...(g.mats || []), { t: x, url, by: u.name }] });
  };

  // Jalankan koneksi awal
  bootstrapAuth();
</script>
</body>
</html>
