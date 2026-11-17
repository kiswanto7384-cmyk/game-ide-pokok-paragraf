<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Generator Soal SMA</title>
<script>window.MathJax={tex:{inlineMath:[['\\(','\\)']]},svg:{fontCache:'global'}};</script>
<script defer src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/3.2.2/es5/tex-svg.js"></script>
<style>
:root{--bg:#eef2f1;--card:#fff;--tx:#1b2b2b;--mut:#5d6f6f;--line:#cfdad9;--ac:#0f5c5c;--acx:#fff}
@media (prefers-color-scheme:dark){:root{--bg:#121b1b;--card:#1b2727;--tx:#e4eeee;--mut:#98adad;--line:#2f4141;--ac:#5fc4c0;--acx:#0b1a1a}}
*{box-sizing:border-box}
body{margin:0;background:var(--bg);color:var(--tx);font:15px/1.5 system-ui,-apple-system,"Segoe UI",Roboto,sans-serif}
.wrap{max-width:1100px;margin:0 auto;padding:16px;display:grid;gap:16px;grid-template-columns:340px 1fr;align-items:start}
@media(max-width:820px){.wrap{grid-template-columns:1fr}}
.panel{background:var(--card);border:1px solid var(--line);border-radius:10px;padding:16px}
h1{font-size:19px;margin:0 0 2px}
.sub{color:var(--mut);margin:0 0 12px;font-size:13px}
label{display:block;font-size:13px;color:var(--mut);margin:10px 0 3px}
input,select{width:100%;padding:8px;border:1px solid var(--line);border-radius:6px;background:var(--bg);color:var(--tx);font:inherit}
.g2{display:grid;grid-template-columns:1fr 1fr;gap:8px}
.g5{display:grid;grid-template-columns:repeat(5,1fr);gap:6px}
.g5 label{font-size:11px;margin-top:4px}
button{font:inherit;padding:9px 12px;border-radius:6px;border:1px solid var(--ac);background:var(--ac);color:var(--acx);cursor:pointer}
button.alt{background:transparent;color:var(--ac)}
button:focus-visible,input:focus-visible,select:focus-visible,summary:focus-visible{outline:2px solid var(--ac);outline-offset:2px}
.row{display:flex;gap:8px;margin-top:14px;flex-wrap:wrap}
.row button{flex:1}
details{margin-top:12px;border-top:1px solid var(--line);padding-top:8px}
summary{cursor:pointer;color:var(--mut);font-size:13px}
#status{margin:10px 0 0;min-height:20px;font-size:13px;color:var(--mut)}
.empty{color:var(--mut);text-align:center;padding:40px 10px}
.paper{background:#fff;color:#000;border:1px solid var(--line);border-radius:4px;padding:28px 32px;font-family:"Times New Roman",Georgia,serif;font-size:13pt;line-height:1.45;overflow-x:auto}
.paper h3{font-size:13pt;margin:18px 0 6px}
.kop{text-align:center;border-bottom:2px solid #000;padding-bottom:8px;margin-bottom:8px}
.idn{font-size:11pt;margin-bottom:10px}
.q{display:flex;gap:8px;margin:0 0 12px;page-break-inside:avoid}
.no{min-width:24px}
.main{flex:1}
.main p{margin:0 0 4px;white-space:pre-line}
.st{font-style:italic}
.fig{width:34%;max-width:240px;flex:none}
.fig svg{width:100%;height:auto}
.op{list-style:none;margin:2px 0 0;padding:0}
.op li{display:flex;gap:6px}
.bs{border-collapse:collapse;margin-top:4px;font-size:12pt}
.bs td,.bs th{border:1px solid #000;padding:2px 8px}
.kunci{page-break-before:always}
.kunci p{margin:0 0 5px;white-space:pre-line;font-size:12pt}
body.nokey .kunci{display:none}
@media print{body{background:#fff}.panel,.noprint{display:none!important}.wrap{display:block;padding:0}.paper{border:0;padding:0}}
</style>
</head>
<body>
<div class="wrap">
  <section class="panel noprint">
    <h1>Generator Soal SMA</h1>
    <p class="sub">Isi topik, pilih jenis soal, lalu buat.</p>

    <label for="school">Nama sekolah</label>
    <input id="school" placeholder="SMA Negeri ...">
    <div class="g2">
      <div><label for="kelas">Kelas</label>
        <select id="kelas"><option>10</option><option>11</option><option>12</option></select></div>
      <div><label for="ujian">Jenis ujian</label>
        <select id="ujian"><option value="Ulangan Harian">UH</option><option value="Penilaian Tengah Semester">PTS</option><option value="Penilaian Akhir Semester">PAS</option></select></div>
    </div>
    <label for="mapel">Mata pelajaran</label>
    <input id="mapel" list="mapelList" placeholder="Matematika">
    <datalist id="mapelList"><option>Matematika</option><option>Fisika</option><option>Kimia</option><option>Biologi</option><option>Ekonomi</option><option>Geografi</option><option>Sosiologi</option><option>Sejarah</option><option>Bahasa Indonesia</option><option>Bahasa Inggris</option><option>Informatika</option></datalist>
    <label for="topik">Topik / bab</label>
    <input id="topik" placeholder="Contoh: Fungsi kuadrat">
    <div class="g2">
      <div><label for="tingkat">Tingkat soal</label>
        <select id="tingkat"><option>Campuran (mudah sampai HOTS)</option><option>Mudah</option><option>Sedang</option><option>HOTS</option></select></div>
      <div><label for="opsiN">Opsi pilihan ganda</label>
        <select id="opsiN"><option value="5">A-E</option><option value="4">A-D</option></select></div>
    </div>

    <label>Jumlah soal per jenis</label>
    <div class="g5">
      <div><label for="n_pg">PG</label><input id="n_pg" type="number" min="0" max="30" value="10"></div>
      <div><label for="n_pgk">PG kompleks</label><input id="n_pgk" type="number" min="0" max="15" value="0"></div>
      <div><label for="n_bs">Benar-salah</label><input id="n_bs" type="number" min="0" max="15" value="0"></div>
      <div><label for="n_is">Isian</label><input id="n_is" type="number" min="0" max="20" value="0"></div>
      <div><label for="n_es">Esai</label><input id="n_es" type="number" min="0" max="10" value="0"></div>
    </div>

    <div class="row"><button id="go">Buat soal</button></div>
    <div class="row">
      <button class="alt" id="pdf">Cetak / PDF</button>
      <button class="alt" id="doc">Unduh Word</button>
    </div>
    <label style="display:flex;gap:6px;align-items:center;margin-top:10px"><input id="showKey" type="checkbox" checked style="width:auto"> Sertakan kunci dan pembahasan</label>
    <p id="status" role="status"></p>

    <details>
      <summary>Pengaturan AI</summary>
      <label for="key">API key</label>
      <input id="key" type="password" autocomplete="off" placeholder="Tempel API key Anda">
      <label for="model">Model</label>
      <input id="model" placeholder="llama-3.3-70b-versatile">
      <label for="ep">Alamat API</label>
      <input id="ep" placeholder="https://api.groq.com/openai/v1/chat/completions">
      <p class="sub" style="margin-top:6px">Disimpan hanya di browser ini, tidak dikirim ke repo.</p>
    </details>
  </section>

  <section>
    <div id="paper" class="paper"><div class="empty">Soal akan tampil di sini.</div></div>
  </section>
</div>

<script>
const $=s=>document.querySelector(s);
const LS={get(k){try{return localStorage.getItem(k)||''}catch(x){return ''}},set(k,v){try{localStorage.setItem(k,v)}catch(x){}}};
const e=x=>String(x==null?'':x).replace(/&/g,'&amp;').replace(/</g,'&lt;').replace(/>/g,'&gt;');
const st=t=>{$('#status').textContent=t};
const T={
 pg:{label:'Pilihan Ganda',sc:'{"stimulus":"","pertanyaan":"","opsi":[],"kunci":"A","pembahasan":"","gambar_svg":""}'},
 pgk:{label:'Pilihan Ganda Kompleks (pilih semua jawaban yang benar)',sc:'{"stimulus":"","pertanyaan":"","opsi":[],"kunci":["A","C"],"pembahasan":"","gambar_svg":""}'},
 bs:{label:'Benar-Salah',sc:'{"stimulus":"","pertanyaan":"","pernyataan":[{"teks":"","benar":true}],"pembahasan":"","gambar_svg":""}'},
 is:{label:'Isian Singkat',sc:'{"stimulus":"","pertanyaan":"","jawaban":"","pembahasan":"","gambar_svg":""}'},
 es:{label:'Esai',sc:'{"stimulus":"","pertanyaan":"","pedoman":"","skor":5,"gambar_svg":""}'}
};
const SYS='Anda guru SMA berpengalaman di Indonesia yang menyusun soal sesuai Kurikulum Merdeka. Balas HANYA dengan JSON array yang valid, tanpa teks lain dan tanpa markdown. Tulis rumus dalam LaTeX dengan pembatas \\\\( dan \\\\), dan tulis setiap backslash LaTeX DUA kali di dalam JSON (contoh: \\\\(\\\\frac{1}{2}\\\\)). Jangan pakai tanda dolar.';

['school','key','model','ep'].forEach(id=>{$('#'+id).value=LS.get(id);$('#'+id).addEventListener('input',()=>LS.set(id,$('#'+id).value.trim()))});

async function ask(prompt){
  const r=await fetch(LS.get('ep')||'https://api.groq.com/openai/v1/chat/completions',{method:'POST',
    headers:{'Content-Type':'application/json','Authorization':'Bearer '+LS.get('key')},
    body:JSON.stringify({model:LS.get('model')||'llama-3.3-70b-versatile',temperature:0.6,messages:[{role:'system',content:SYS},{role:'user',content:prompt}]})});
  if(!r.ok) throw new Error('API menolak permintaan (kode '+r.status+'). Periksa API key dan model.');
  const j=await r.json();
  return j.choices[0].message.content;
}
function parse(t){
  const a=t.indexOf('['),b=t.lastIndexOf(']');
  if(a<0||b<0) throw new Error('Jawaban AI bukan JSON. Coba buat lagi.');
  let s=t.slice(a,b+1),arr;
  try{arr=JSON.parse(s)}catch(x){arr=JSON.parse(s.replace(/\\(?!["\\\/bfnrtu])/g,'\\\\'))}
  return JSON.parse(JSON.stringify(arr),(k,v)=>typeof v==='string'?v.replace(/\f/g,'\\f').replace(/\x08/g,'\\b').replace(/\r/g,'\\r').replace(/\t/g,'\\t'):v);
}
function fig(q){
  const s=(q.gambar_svg||'').trim();
  return s.indexOf('<svg')===0?'<div class="fig">'+s.replace(/<script[\s\S]*?<\/script>/gi,'').replace(/\son\w+="[^"]*"/gi,'')+'</div>':'';
}
function soalHtml(q,k,N,no){
  let m=(q.stimulus?'<p class="st">'+e(q.stimulus)+'</p>':'')+'<p>'+e(q.pertanyaan)+'</p>';
  if(k==='pg'||k==='pgk') m+='<ul class="op">'+(q.opsi||[]).slice(0,N).map((o,i)=>'<li><span>'+'ABCDE'[i]+'.</span><span>'+e(o)+'</span></li>').join('')+'</ul>';
  if(k==='bs') m+='<table class="bs"><tr><th>Pernyataan</th><th>Benar</th><th>Salah</th></tr>'+(q.pernyataan||[]).map(p=>'<tr><td>'+e(p.teks)+'</td><td>☐</td><td>☐</td></tr>').join('')+'</table>';
  if(k==='is') m+='<p>Jawaban: ........................................</p>';
  if(k==='es') m+='<p>(Skor '+e(q.skor||5)+')</p>';
  return '<div class="q"><div class="no">'+no+'.</div><div class="main">'+m+'</div>'+fig(q)+'</div>';
}
function kunciHtml(q,k,no){
  const a={pg:q.kunci,pgk:[].concat(q.kunci||[]).join(', '),bs:(q.pernyataan||[]).map(p=>p.benar?'B':'S').join(', '),is:q.jawaban,es:q.pedoman}[k];
  return '<p><b>'+no+'.</b> '+e(a)+(q.pembahasan?' — '+e(q.pembahasan):'')+'</p>';
}
const state={soal:'',kunci:''};

async function gen(){
  if(!LS.get('key')){st('Isi API key di Pengaturan AI dulu.');$('details').open=true;return}
  const mapel=$('#mapel').value.trim(),topik=$('#topik').value.trim();
  if(!mapel||!topik){st('Isi mata pelajaran dan topik/bab dulu.');return}
  const kelas=$('#kelas').value,ujian=$('#ujian').value,tingkat=$('#tingkat').value,N=+$('#opsiN').value;
  let no=0,sec=0,soal='',kunci='';
  $('#go').disabled=true;
  for(const k of Object.keys(T)){
    const n=+$('#n_'+k).value||0; if(!n) continue;
    st('Membuat soal '+T[k].label+'...');
    const p='Buat '+n+' soal '+T[k].label+' mata pelajaran '+mapel+' kelas '+kelas+' SMA dengan topik/bab: '+topik+'. Jenis ujian: '+ujian+'. Tingkat: '+tingkat+'. '
      +((k==='pg'||k==='pgk')?'Jumlah opsi tepat '+N+' (A sampai '+'ABCDE'[N-1]+'), sebar kunci jawaban merata. ':'')
      +'Stimulus (teks, data, atau tabel singkat) boleh diisi bila membantu. Isi gambar_svg hanya bila gambar benar-benar membantu (grafik, diagram, bangun); buat SVG sederhana dengan viewBox, garis hitam di latar putih, teks seminimal mungkin; selain itu isi string kosong. Format tiap objek: '+T[k].sc;
    try{
      const arr=parse(await ask(p));
      const h='<h3>'+String.fromCharCode(65+sec)+'. '+T[k].label+'</h3>';
      soal+=h;kunci+=h;sec++;
      arr.forEach(q=>{no++;soal+=soalHtml(q,k,N,no);kunci+=kunciHtml(q,k,no)});
    }catch(err){st('Gagal pada '+T[k].label+': '+err.message);$('#go').disabled=false;return}
  }
  $('#go').disabled=false;
  if(!no){st('Isi jumlah soal minimal satu jenis.');return}
  const kop='<div class="kop"><b>'+e($('#school').value||'Nama Sekolah')+'</b><br>'+e(ujian)+' '+e(mapel)+' — Kelas '+kelas+'<br>Topik: '+e(topik)+'</div><div class="idn">Nama: ................................ Kelas: ........ No. Absen: ........</div>';
  state.soal=kop+soal;state.kunci='<div class="kunci"><h3>Kunci Jawaban dan Pembahasan</h3>'+kunci+'</div>';
  $('#paper').innerHTML=state.soal+state.kunci;
  if(window.MathJax&&MathJax.typesetPromise) MathJax.typesetPromise([$('#paper')]);
  st(no+' soal selesai dibuat.');
}
function dlWord(){
  if(!state.soal){st('Buat soal dulu.');return}
  const body=(state.soal+($('#showKey').checked?state.kunci:'')).replace(/<svg[\s\S]*?<\/svg>/g,'');
  const html='<html xmlns:o="urn:schemas-microsoft-com:office:office" xmlns:w="urn:schemas-microsoft-com:office:word"><head><meta charset="utf-8"><style>body{font-family:"Times New Roman";font-size:12pt}.kop{text-align:center}.bs td,.bs th{border:1px solid #000;padding:2px 8px}.op{list-style:none;padding-left:20px}.no{display:inline}</style></head><body>'+body+'</body></html>';
  const a=document.createElement('a');
  a.href=URL.createObjectURL(new Blob(['\ufeff',html],{type:'application/msword'}));
  a.download='soal-'+($('#mapel').value||'sma').replace(/\s+/g,'-')+'.doc';
  a.click();setTimeout(()=>URL.revokeObjectURL(a.href),1000);
}
$('#showKey').addEventListener('change',()=>document.body.classList.toggle('nokey',!$('#showKey').checked));
$('#go').addEventListener('click',gen);
$('#pdf').addEventListener('click',()=>{state.soal?window.print():st('Buat soal dulu.')});
$('#doc').addEventListener('click',dlWord);
</script>
</body>
</html>
