# Siklus-komputer
Siklus komputer 
<!doctype html>
<html lang="id">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Siklus Instruksi Kerja Komputer</title>
  <style>
    :root{--bg:#0f172a;--card:#0b1220;--accent:#7dd3fc;--muted:#94a3b8;--glass:rgba(255,255,255,0.03)}
    html,body{height:100%;margin:0;font-family:Inter,ui-sans-serif,system-ui,Segoe UI,Roboto,-apple-system,'Noto Sans',"Helvetica Neue",Arial}
    body{background:linear-gradient(180deg,#07162a 0%,#021024 100%);color:#e6eef8;display:flex;align-items:center;justify-content:center;padding:24px}
    .wrap{max-width:900px;width:100%}
    header{display:flex;align-items:center;gap:16px;margin-bottom:18px}
    .logo{width:64px;height:64px;border-radius:12px;background:linear-gradient(135deg,var(--accent),#60a5fa);display:flex;align-items:center;justify-content:center;box-shadow:0 6px 18px rgba(2,6,23,0.6)}
    .logo svg{width:36px;height:36px}
    h1{font-size:1.5rem;margin:0}
    p.lead{color:var(--muted);margin-top:6px}
    .card{background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));border-radius:12px;padding:18px;margin-bottom:14px;box-shadow:0 6px 20px rgba(2,6,23,0.6)}
    .stages{display:grid;grid-template-columns:repeat(auto-fit,minmax(200px,1fr));gap:12px;margin-top:12px}
    .stage{background:var(--glass);padding:12px;border-radius:10px}
    .stage h3{margin:0 0 6px 0}
    .diagram{display:flex;gap:12px;align-items:center;justify-content:center;margin-top:12px}
    .ascii{font-family:monospace;background:#001427;padding:12px;border-radius:8px;color:#cfeffd}
    code{white-space:pre-wrap}
    footer{color:var(--muted);font-size:0.9rem;margin-top:8px}
    .btn{display:inline-block;padding:8px 12px;border-radius:8px;background:linear-gradient(90deg,#0ea5e9,#60a5fa);color:#021024;font-weight:600;text-decoration:none}
    /* responsive */
    @media (max-width:520px){h1{font-size:1.2rem}}
  </style>
</head>
<body>
  <main class="wrap">
    <header>
      <div class="logo" aria-hidden>
        <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M3 12h18" stroke="#021024" stroke-width="1.2" stroke-linecap="round" stroke-linejoin="round"/><path d="M12 3v18" stroke="#021024" stroke-width="1.2" stroke-linecap="round" stroke-linejoin="round"/></svg>
      </div>
      <div>
        <h1>Siklus Instruksi Kerja Komputer</h1>
        <p class="lead">Penjelasan singkat tentang bagaimana CPU mengeksekusi satu instruksi — fetch, decode, execute, store.</p>
      </div>
    </header>

    <section class="card">
      <h2>Pengertian</h2>
      <p> <strong>Siklus instruksi</strong> adalah rangkaian langkah yang dilakukan CPU untuk mengeksekusi satu instruksi dari program. Setiap instruksi (mis. penjumlahan, pemindahan data) melalui serangkaian fase sehingga hasilnya dapat disimpan dan program berlanjut.</p>
    </section>

    <section class="card">
      <h2>Tahapan Utama</h2>
      <div class="stages">
        <div class="stage">
          <h3>1. Fetch (Mengambil)</h3>
          <p>CPU mengambil instruksi dari memori utama menggunakan alamat yang disimpan di <strong>Program Counter (PC)</strong>. Setelah diambil, PC biasanya ditambah untuk menunjuk instruksi berikutnya.</p>
        </div>
        <div class="stage">
          <h3>2. Decode (Mendekode)</h3>
          <p>Control Unit menerjemahkan instruksi untuk menentukan operasi yang harus dilakukan dan operand yang dipakai (register, alamat memori, immediate).</p>
        </div>
        <div class="stage">
          <h3>3. Execute (Menjalankan)</h3>
          <p>ALU atau unit lain menjalankan operasi (aritmetika, logika, akses memori, cabang, dll.).</p>
        </div>
        <div class="stage">
          <h3>4. Store (Menyimpan)</h3>
          <p>Hasil eksekusi disimpan kembali ke register atau memori. Siklus selesai, CPU kembali ke tahap Fetch untuk instruksi selanjutnya.</p>
        </div>
      </div>

      <div class="diagram" aria-hidden>
        <div class="ascii">
<code>+--------+   +--------+   +---------+   +-------+
| Fetch  | ->| Decode | ->| Execute | ->| Store |
+--------+   +--------+   +---------+   +-------+
      ^                                   |
      |-----------------------------------|
</code>
        </div>
      </div>

    </section>

    <section class="card">
      <h2>Catatan & Visual</h2>
      <p>Proses ini berulang sangat cepat (jutaan hingga miliaran siklus per detik tergantung frekuensi CPU). Arsitektur modern menambahkan fitur seperti pipeline, cache, dan superscalar untuk meningkatkan throughput instruksi.</p>
      <p class="muted">Butuh diagram SVG detail atau versi printable? Klik tombol di bawah untuk menyalin HTML ini ke clipboard.</p>
      <p><a class="btn" id="copyBtn">Salin HTML ke clipboard</a></p>
    </section>

    <footer>Ditulis otomatis — jika ingin, saya bisa tambahkan diagram pipeline, contoh assembly, atau versi terjemahan bahasa Inggris.</footer>
  </main>

  <script>
    document.getElementById('copyBtn').addEventListener('click', async function(){
      try{
        await navigator.clipboard.writeText(document.documentElement.outerHTML);
        this.textContent = 'Tersalin!';
        setTimeout(()=> this.textContent = 'Salin HTML ke clipboard',1500);
      }catch(e){
        alert('Tidak dapat menyalin otomatis — silakan seleksi dan salin manual.');
      }
    });
  </script>
</body>
</html>
