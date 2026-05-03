<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Undangan Pernikahan</title>
<link href="https://fonts.googleapis.com/css2?family=Great+Vibes&family=Playfair+Display:wght@500;700&display=swap" rel="stylesheet">
<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: 'Segoe UI', sans-serif;
    overflow-x: hidden;
}

/* COVER */
#cover {
    height: 100vh;
    background: linear-gradient(rgba(0,0,0,0.5), rgba(0,0,0,0.5)),
                url('s.jpeg') center/cover no-repeat;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
    padding: 40px 20px;
    color: white;
}

.top-text {
    text-align: center;
}

.top-text h1 {
    font-size: 32px;
    color: #ff4d6d;
}

/* CARD */
.card {
    background: rgba(255,255,255,0.95);
    padding: 20px;
    border-radius: 20px;
    text-align: center;
    width: 95%;
    max-width: 350px;
    color: black;
}

/* BUTTON */
button {
    margin-top: 15px;
    background: #8b0000;
    color: white;
    border: none;
    padding: 12px;
    border-radius: 12px;
    width: 100%;
}

/* CONTENT */
#content {
    display: none;
    padding: 20px;

    background: 
        linear-gradient(rgba(255,255,255,0.85), rgba(255,255,255,0.9)),
        url('bunga.jpg') center/cover no-repeat;

    min-height: 100vh;
}

/* SECTION */
.section {
    text-align: center;
    margin: 30px 0;
}

/* MEMPELAI */
.mempelai {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 20px;
}

.box {
    background: white;
    padding: 15px;
    border-radius: 20px;
    width: 95%;
    max-width: 320px;
    text-align: center;
    box-shadow: 0 5px 15px rgba(0,0,0,0.1);
}

/* FOTO RESPONSIVE */
.box img{
    width: 140px;
    height: 140px;
    border-radius: 50%;
    object-fit: cover;
    object-position: center top; /* fokus ke wajah */
    border: 4px solid #ff4d6d;
}

/* DATE BOX */
.date-box {
    background: rgba(255,255,255,0.95);
    padding: 20px;
    border-radius: 25px;
    text-align: center;
    margin: 20px 0;
    box-shadow: 0 10px 25px rgba(0,0,0,0.15);
}

.title {
    font-family: cursive;
    color: #8b0000;
    margin-bottom: 20px;
}

/* GRID */
.time-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 15px;
}

/* BULAT */
.circle {
    width: 55px;
    height: 55px;
    border: 2px solid black;
    border-radius: 50%;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 16px;
    margin: auto;
}

/* CARD2 */
.card2 {
    background: white;
    padding: 15px;
    border-radius: 20px;
    margin-bottom: 15px;
    text-align: center;
}

/* INPUT */
input, textarea {
    width: 95%;
    padding: 10px;
    margin: 5px;
    border-radius: 10px;
    border: 1px solid #ccc;
}

/* RESPONSIVE */
@media (max-width: 480px) {
    .top-text h1 {
        font-size: 26px;
    }

    .circle {
        width: 50px;
        height: 50px;
        font-size: 14px;
    }

    button {
        font-size: 14px;
    }
}

/* KOTAK KATA-KATA (LEBIH SOLID) */
.quote-box {
    background: white; /* ini bikin kolom jelas */
    padding: 20px;
    border-radius: 20px;
    text-align: center;
    margin: 20px 0;
    box-shadow: 0 8px 20px rgba(0,0,0,0.15);
}

/* TEKS */
.quote-box p {
    font-style: italic;
    font-size: 15px;
    color: #333;
    line-height: 1.6;
    margin-bottom: 10px;
}

.quote-box h4 {
    color: #8b0000;
    font-weight: normal;
}

/* GALERI GRID */
/* GANTI CSS GALERI LAMA JADI INI */

.gallery{
    display:grid;
    grid-template-columns:repeat(2,1fr);
    gap:14px;
    margin-bottom:20px;
}

.gallery img{
    width:100%;
    height:220px;
    object-fit:contain;   /* biar foto full keliatan */
    object-position:center;
    background:#fff;
    border-radius:20px;
    padding:8px;
    cursor:pointer;
    transition:0.4s;
    box-shadow:0 8px 20px rgba(0,0,0,0.08);
}

.gallery img:hover{
    transform:scale(1.03);
}

/* HP */
@media(max-width:480px){
.gallery{
    grid-template-columns:1fr;
}

.gallery img{
    height:240px;
}
}

/* MODAL (ZOOM) */
#modal {
    display: none;
    position: fixed;
    z-index: 999;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    background: rgba(0,0,0,0.8);
    justify-content: center;
    align-items: center;
}

#modal img {
    width: 90%;
    max-width: 400px;
    border-radius: 20px;
}

/* BUTTON MUSIK */
.music-btn {
    position: fixed;
    bottom: 20px;
    right: 20px;
    background: #8b0000;
    color: white;
    font-size: 20px;
    width: 50px;
    height: 50px;
    border-radius: 50%;
    display: flex;
    justify-content: center;
    align-items: center;
    cursor: pointer;
    box-shadow: 0 5px 15px rgba(0,0,0,0.3);
    z-index: 999;
}

/* ANIMASI PUTAR */
.music-btn.playing {
    animation: putar 3s linear infinite;
}

@keyframes putar {
    from { transform: rotate(0deg); }
    to { transform: rotate(360deg); }
}

/* LOKASI */
.lokasi-box{
    background: rgba(255,255,255,0.95);
    padding: 25px;
    border-radius: 25px;
    text-align:center;
    margin:20px 0;
}

.lokasi-title{
    font-family:cursive;
    color:#8b0000;
    font-size:38px;
    margin-bottom:15px;
}

.lokasi-nama{
    font-size:42px;
    margin-top:18px;
    margin-bottom:10px;
}

.lokasi-alamat{
    font-size:18px;
    line-height:1.8;
    color:#333;
    margin-bottom:20px;
}

.lokasi-btn{
    background:#8b0000;
    color:white;
    border:none;
    padding:14px 28px;
    border-radius:30px;
    font-size:18px;
}

/* HADIAH */
.hadiah-box{
    background: rgba(255,255,255,0.92);
    padding: 25px 20px;
    border-radius: 25px;
    text-align:center;
    margin:20px 0;
}

.hadiah-title{
    font-family:cursive;
    color:#8b0000;
    font-size:34px;
    margin-bottom:15px;
}

.hadiah-text{
    color:#333;
    font-size:15px;
    line-height:1.8;
    margin-bottom:20px;
}

.hadiah-btn-wrap{
    display:flex;
    gap:10px;
    justify-content:center;
}

.hadiah-btn{
    background:#8b0000;
    color:white;
    border:none;
    padding:12px 18px;
    border-radius:30px;
    width:auto;
    min-width:120px;
    font-size:14px;
}

/* REKENING */
.rekening-box{
    background:#fff;
    border:2px solid #8b0000;
    border-radius:18px;
    padding:15px;
    margin-bottom:12px;
    color:#333;
    line-height:1.7;
}
/* ACARA */
.acara-box{
    padding:25px 20px;
    border-radius:25px;
    text-align:center;
}

.acara-title{
    font-family:cursive;
    font-size:34px;
    color:#8c1d2c;
    margin-bottom:18px;
}

.acara-item{
    display:flex;
    align-items:center;
    gap:10px;
    background:#fff;
    padding:12px;
    border-radius:15px;
    margin-bottom:10px;
    border:1px solid #f0d6d9;
}

.acara-item span{
    font-size:22px;
}

.acara-item p{
    margin:0;
    font-size:16px;
    color:#4b3a34;
}

.acara-btn{
    margin-top:15px;
    background:#8c1d2c;
    color:#fff;
    border:none;
    padding:12px;
    border-radius:30px;
}

/* EFEK BUNGA JATUH */
.falling-flowers{
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    pointer-events: none;
    overflow: hidden;
    z-index: 9999;
}

.flower{
    position: absolute;
    top: -50px;
    font-size: 20px;
    animation: fall linear infinite;
    opacity: 0.8;
}

@keyframes fall{
    0%{
        transform: translateY(-50px) rotate(0deg);
        opacity: 0;
    }
    10%{
        opacity: 0.9;
    }
    100%{
        transform: translateY(110vh) rotate(360deg);
        opacity: 0;
    }
}
.wedding-title{
    font-family: 'Georgia', serif;
    font-size: 42px;
    font-weight: bold;
    text-align: center;
    color: #8b0000;
    letter-spacing: 2px;
    position: relative;
    margin-bottom: 20px;
    text-shadow: 2px 2px 8px rgba(0,0,0,0.15);
}

/* Garis hias kiri kanan */
.wedding-title::before,
.wedding-title::after{
    content: "";
    position: absolute;
    top: 50%;
    width: 60px;
    height: 2px;
    background: #d4af37;
}

.wedding-title::before{
    left: -70px;
}

.wedding-title::after{
    right: -70px;
}

/* UCAPAN */
.card2 h3{
    font-family:'Playfair Display', serif;
    font-size:28px;
    color:#8b0000;
    margin-bottom:15px;
}

/* INPUT / TEXTAREA */
.card2 input,
.card2 textarea{
    font-family:'Segoe UI', sans-serif;
    font-size:15px;
    color:#333;
    border:1px solid #e5d3d8;
    background:#fff;
}

.card2 textarea{
    min-height:100px;
    resize:none;
}

/* PENUTUP */
.penutup-title{
    font-family:'Playfair Display', serif;
    font-size:34px;
    color:#8b0000;
    margin-bottom:15px;
}

.penutup-text{
    font-family:'Segoe UI', sans-serif;
    font-size:16px;
    line-height:1.8;
    color:#4b3a34;
    margin-bottom:20px;
}

.penutup-nama{
    font-family:'Great Vibes', cursive;
    font-size:36px;
    color:#c2185b;
    font-weight:normal;
}

.wedding-title{
    font-family:'Great Vibes', cursive;
    font-size:52px;
    font-weight:normal;
    color:#8b0000;
    text-align:center;
    margin-bottom:10px;
}

.section-title{
    font-family:'Playfair Display', serif;
    font-size:36px;
    font-weight:700;
    color:#8b0000;
    text-align:center;
    margin-bottom:15px;
    letter-spacing:1px;
    text-shadow:0 2px 10px rgba(0,0,0,0.08);
}

.nama-love{
    font-family:'Great Vibes', cursive;
    font-size:34px;
    font-weight:normal;
    color:#c2185b;
    text-align:center;
    margin-bottom:12px;
}
.nama-cover{
    font-family:'Great Vibes', cursive;
    font-size:64px;
    font-weight:normal;
    color: #ffffff;
    text-align:center;
    line-height:1.2;
    text-shadow:0 4px 15px rgba(0,0,0,0.25);
}
.penutup-box{
    background:linear-gradient(180deg,#ffffff,#fff8fa);
    padding:35px 25px;
    border-radius:28px;
    text-align:center;
    box-shadow:0 12px 30px rgba(0,0,0,0.08);
    border:1px solid #f4dce2;
    margin-top:30px;
}

.penutup-ornamen{
    font-size:22px;
    color:#d4af37;
    margin-bottom:12px;
}

.penutup-title{
    font-family:'Playfair Display', serif;
    font-size:34px;
    color:#8b0000;
    margin-bottom:15px;
}

.penutup-text{
    font-size:15px;
    line-height:1.9;
    color:#555;
    margin-bottom:15px;
}

.penutup-sub{
    font-style:italic;
    color:#c2185b;
    font-size:15px;
    margin-bottom:20px;
}

.penutup-divider{
    width:70px;
    height:2px;
    background:#d4af37;
    margin:20px auto;
    border-radius:10px;
}

.penutup-nama{
    font-family:'Great Vibes', cursive;
    font-size:42px;
    color:#8b0000;
    font-weight:normal;
}
.fade-up{
    opacity:0;
    transform:translateY(40px);
    transition:all .8s ease;
}

.fade-up.show{
    opacity:1;
    transform:translateY(0);
}
.top-text{
    animation:floatHero 4s ease-in-out infinite;
}

#cover button{
    background: linear-gradient(135deg,#c1121f,#8b0000);
    color: white;
    font-weight: bold;
    font-size: 16px;
    padding: 14px;
    border-radius: 14px;
    border: none;
    width: 100%;
    position: relative;
    z-index: 2;
    animation: pulse 2s infinite;
    box-shadow: 0 8px 20px rgba(139,0,0,.35);
}

@keyframes pulse{
    0%{
        box-shadow:
            0 0 0 0 rgba(193,18,31,.55),
            0 8px 20px rgba(139,0,0,.35);
    }
    70%{
        box-shadow:
            0 0 0 18px rgba(193,18,31,0),
            0 8px 20px rgba(139,0,0,.35);
    }
    100%{
        box-shadow:
            0 0 0 0 rgba(193,18,31,0),
            0 8px 20px rgba(139,0,0,.35);
    }
}
content{
    background: url('111.jpg') center no-repeat;
    background-size: 800px auto;
}
<style>
/* CSS kamu yang lama ... */

/* TARUH DI SINI */
.card,
.card2,
.box,
.quote-box,
.date-box,
.lokasi-box,
.hadiah-box,
.penutup-box,
.acara-box,
.rekening-box{
    transition: all .35s ease;
    cursor: pointer;
}

.card:hover,
.card2:hover,
.box:hover,
.quote-box:hover,
.date-box:hover,
.lokasi-box:hover,
.hadiah-box:hover,
.penutup-box:hover,
.acara-box:hover,
.rekening-box:hover{
    transform: translateY(-6px) scale(1.02);
    box-shadow: 0 15px 30px rgba(139,0,0,.15);
}

.card:active,
.card2:active,
.box:active,
.quote-box:active,
.date-box:active,
.lokasi-box:active,
.hadiah-box:active,
.penutup-box:active,
.acara-box:active,
.rekening-box:active{
    transform: scale(0.98);
}
.reveal{
    opacity: 0;
    transform: translateY(40px);
    transition: all .8s ease;
}

.reveal.show{
    opacity: 1;
    transform: translateY(0);
}
</style>




</head>

<body>
<div class="falling-flowers"></div>
<link href="https://fonts.googleapis.com/css2?family=Great+Vibes&family=Playfair+Display:wght@600;700&display=swap" rel="stylesheet">
<!-- COVER -->
<div id="cover">
    <div class="top-text">
<h2 class="wedding-title">A Journey of Love Begins</h2>
<h1 class="nama-cover">Davi & Saniah</h1>    </div>

    <div class="card">
        <p>Kepada Yth.</p>
        <p>Bapak/Ibu/Saudara/i</p>
        <p id="namaTamu">Tamu Undangan</p>

        <button onclick="bukaUndangan()">Open Invitation</button>
    </div>
</div>

<!-- CONTENT -->
<div id="content">

    <!-- KATA KATA -->
    <div class="section">
<h2 class="section-title">The Wedding Of</h2>    </div>
        <div class="quote-box">
<h5 class="nama-love">Davi & Saniah</h5>        <p>
            "Dan di antara tanda-tanda kebesaran-Nya, 
            Dia menciptakan pasangan hidup agar kamu menemukan ketenangan di dalamnya, 
            serta menjadikan cinta dan kasih sayang di antara kalian."
        </p>
        <h4>QS. Ar-Rum: 21</h4>
    </div>

    <div class="mempelai">

        <div class="box">
            <img src="davi.jpeg">
            <h3>Davi</h3>
            <p>Putra dari</p>
            <p>Bapak Uus Lustiawan & Ibu Nunung Nurhayati</p>
        </div>
         <div class="box">
            <img src="sani.jpeg">
            <h3>Saniah</h3>
            <p>Putri dari</p>
            <p>Bapak Aris & Ibu Kelly Aprilla</p>
        </div>
    </div>

    <!-- GALERI -->
    <div class="section">
    </div>

    <div class="gallery">

        <img src="1.jpeg" onclick="openModal(this)">
        <img src="2.jpeg" onclick="openModal(this)">
        <img src="3.jpeg" onclick="openModal(this)">
        <img src="4.jpeg" onclick="openModal(this)">

    </div>

    <!-- MODAL ZOOM -->
    <div id="modal" onclick="closeModal()">
        <img id="modal-img">
    </div>

    <!-- MASUKKAN DI BAWAH BAGIAN ACARA -->

    <!-- LOKASI -->
   <!-- LOKASI STYLE ELEGAN -->
    <div class="card2 lokasi-box">

        <h2 class="lokasi-title">Lokasi Acara</h2>

      <iframe
        src="https://www.google.com/maps?q=Bitung+Sari+Ciawi+Bogor&output=embed"
        width="100%"
        height="220"
        style="border:3px solid #8b0000; border-radius:18px;"
        allowfullscreen=""
        loading="lazy">
        </iframe>

        <!-- TOMBOL LINK ASLI -->
        <a href="https://maps.app.goo.gl/Na9yKscP5cigKwJb9" target="_blank">
            <button class="lokasi-btn">Buka Google Maps</button>
        </a>


        <p class="lokasi-alamat">
            Jl. Mayjen He Sukma<br>
            Ds. Bitung Sari Kp. Bitung Ratna rt01/02 Kec. Ciawi Kab. Bogor<br>
            Jawa Barat 16720
        </p>


    </div>
    <!-- HADIAH -->
   
    <!-- HADIAH PERNIKAHAN -->
<!-- GANTI BAGIAN HADIAH LAMA DENGAN INI -->
<div class="card2 hadiah-box">

    <h2 class="hadiah-title">Hadiah Pernikahan</h2>

    <p class="hadiah-text">
        Doa dan Restu Anda sangat berarti bagi kami.<br>
        Namun, jika memberi adalah cara Anda<br>
        mengungkapkan kasih sayang, kami akan<br>
        menerimanya dengan senang hati, karena itu<br>
        akan menambah kebahagiaan kami.
    </p>

    <div class="rekening-box">
        <p><b>BCA</b></p>
        <p>6821846801</p>
        <p>a.n Davi</p>
    </div>

    <div class="rekening-box">
        <p><b>BCA</b></p>
        <p>6821989393</p>
        <p>a.n Saniah</p>
    </div>

</div>

   
    <!-- COUNTDOWN -->
    <div class="date-box">
        <h2 class="title">Date</h2>

        <div class="time-grid">
            <div>
                <div class="circle" id="day">00</div>
                <p>Day</p>
            </div>
            <div>
                <div class="circle" id="hour">00</div>
                <p>Hour</p>
            </div>
            <div>
                <div class="circle" id="minute">00</div>
                <p>Minute</p>
            </div>
            <div>
                <div class="circle" id="second">00</div>
                <p>Second</p>
            </div>
        </div>

        <button>Save the Date</button>
    </div>

    <!-- ACARA -->
   <!-- GANTI BAGIAN ACARA LAMA DENGAN INI -->

    <div class="card2 acara-box">

        <h2 class="acara-title">Save The Date</h2>

        <div class="acara-item">
            <span>📅</span>
            <p>Minggu, 31 Mei 2026</p>
        </div>

        <div class="acara-item">
            <span>⏰</span>
            <p>09.00 WIB - Selesai</p>
        </div>

        <div class="acara-item">
            <span>📍</span>
            <p>Kp. Bitung Ratna Rt01/02 (samping RA-ALIF)</p>
        </div>

        <button class="acara-btn">Kami Menanti Kehadiran Anda</button>

    </div>

    <!-- UCAPAN -->
    <div class="card2">
        <h3>💌 Ucapan</h3>
        <input type="text" placeholder="Nama">
        <textarea placeholder="Tulis ucapan..."></textarea>
        <button>Kirim</button>
    </div>

    <!-- TAMBAHKAN DI PALING BAWAH SEBELUM </div> CONTENT -->

  <div class="card2 penutup-box">

    <div class="penutup-ornamen">❀ ✦ ❀</div>

    <h2 class="penutup-title">Terima Kasih</h2>

    <p class="penutup-text">
        Merupakan suatu kehormatan dan kebahagiaan bagi kami
        apabila Bapak/Ibu/Saudara/i berkenan hadir untuk
        memberikan doa restu pada hari bahagia kami.
    </p>

    <p class="penutup-sub">
        Kehadiran dan doa Anda adalah hadiah terindah bagi kami ✨
    </p>

    <div class="penutup-divider"></div>

    <h3 class="penutup-nama">Davi & Saniah</h3>

</div>

    <!-- AUDIO -->
    <audio id="musik" loop>
        <source src="tiara.mp3" type="audio/mpeg">
    </audio>

    <!-- BUTTON MUSIK -->
    <div class="music-btn" onclick="toggleMusic()">
        ▶️
    </div>

</div>

<script>
// OPEN
let isPlaying = false;

function bukaUndangan() {
    document.getElementById("cover").style.display = "none";
    document.getElementById("content").style.display = "block";

    const musik = document.getElementById("musik");

    musik.play().then(() => {
        isPlaying = true;
        document.querySelector(".music-btn").innerHTML = "⏸️";
        document.querySelector(".music-btn").classList.add("playing");
    }).catch(() => {
        console.log("Autoplay gagal");
    });
}

// NAMA TAMU
const params = new URLSearchParams(window.location.search);
const nama = params.get("nama");
if (nama) document.getElementById("namaTamu").innerText = nama;

// COUNTDOWN
const targetDate = new Date("2026-05-31T09:00:00").getTime();

setInterval(() => {
    const now = new Date().getTime();
    const diff = targetDate - now;

    const d = Math.floor(diff / (1000*60*60*24));
    const h = Math.floor((diff % (1000*60*60*24)) / (1000*60*60));
    const m = Math.floor((diff % (1000*60*60)) / (1000*60));
    const s = Math.floor((diff % (1000*60)) / 1000);

    document.getElementById("day").innerText = d;
    document.getElementById("hour").innerText = h;
    document.getElementById("minute").innerText = m;
    document.getElementById("second").innerText = s;

}, 1000);

// OPEN FOTO
function openModal(img) {
    document.getElementById("modal").style.display = "flex";
    document.getElementById("modal-img").src = img.src;
}

// CLOSE FOTO
function closeModal() {
    document.getElementById("modal").style.display = "none";
}


// EFEK BUNGA JATUH
const flowerContainer = document.querySelector(".falling-flowers");

function createFlower() {
    const flower = document.createElement("div");
    flower.classList.add("flower");

    const flowers = ["🌸", "🌺", "💮", "🌷"];
    flower.innerHTML = flowers[Math.floor(Math.random() * flowers.length)];

    flower.style.left = Math.random() * 100 + "vw";
    flower.style.fontSize = (Math.random() * 15 + 15) + "px";
    flower.style.animationDuration = (Math.random() * 5 + 5) + "s";
    flower.style.opacity = Math.random();

    flowerContainer.appendChild(flower);

    setTimeout(() => {
        flower.remove();
    }, 10000);
}

setInterval(createFlower, 400);

</script>


</body>
</html>
