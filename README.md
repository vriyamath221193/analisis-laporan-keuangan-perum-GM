<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Dashboard Keuangan — Paguyuban Griya Mulya</title>
<style>
:root{--navy:#103b70;--blue:#1769aa;--sky:#eaf5fc;--ink:#172b43;--muted:#66788c;--line:#d9e5ef;--green:#167447;--red:#b8323b;--gold:#f4c542;--white:#fff;--shadow:0 8px 24px #163c6412}
*{box-sizing:border-box}body{margin:0;background:#f2f6fa;color:var(--ink);font:15px/1.5 Inter,system-ui,-apple-system,Segoe UI,Arial,sans-serif}
header{background:linear-gradient(115deg,#0d376b,#1476b9);color:white;padding:26px max(20px,calc((100% - 1220px)/2));position:relative;overflow:hidden}
header:after{content:"";position:absolute;width:360px;height:360px;border:1px solid #ffffff24;border-radius:50%;right:-80px;top:-220px;box-shadow:0 0 0 35px #ffffff0c,0 0 0 75px #ffffff09}
.eyebrow{font-size:12px;letter-spacing:1.7px;text-transform:uppercase;opacity:.8;font-weight:700}h1{font-size:clamp(23px,4vw,36px);line-height:1.13;margin:6px 0}.subtitle{opacity:.86}.headrow{display:flex;justify-content:space-between;align-items:center;gap:20px;position:relative;z-index:1}.period{background:#ffffff18;border:1px solid #ffffff40;border-radius:12px;padding:10px 14px;white-space:nowrap}
main{max-width:1220px;margin:22px auto;padding:0 18px 40px}.toolbar{display:flex;justify-content:space-between;align-items:center;gap:12px;flex-wrap:wrap;margin-bottom:16px}.toolbar .filters{display:flex;gap:8px;flex-wrap:wrap}select,button,input{font:inherit;border:1px solid var(--line);border-radius:10px;padding:9px 12px;background:white;color:var(--ink)}button{cursor:pointer;font-weight:650}button.primary{background:var(--navy);color:white;border-color:var(--navy)}button:hover{filter:brightness(.96)}.muted{color:var(--muted);font-size:13px}
.grid{display:grid;gap:15px}.kpis{grid-template-columns:repeat(4,minmax(0,1fr));margin-bottom:15px}.card{background:white;border:1px solid var(--line);border-radius:16px;box-shadow:var(--shadow);padding:17px;min-width:0}.kpi-label{font-size:13px;color:var(--muted);font-weight:650}.kpi-value{font-size:clamp(20px,2.4vw,29px);font-weight:800;letter-spacing:-.6px;margin:7px 0 2px}.kpi-foot{font-size:12px;color:var(--muted)}.kpi-icon{float:right;font-size:22px;background:var(--sky);padding:5px 9px;border-radius:10px}.blue{color:var(--blue)}.green{color:var(--green)}.red{color:var(--red)}
.two{grid-template-columns:1.25fr 1fr;margin-bottom:15px}.section-title{font-size:17px;font-weight:800;margin:0 0 12px;display:flex;justify-content:space-between;align-items:center;gap:10px}.chart-wrap{height:280px;position:relative}canvas{width:100%;height:100%;display:block}.legend{display:flex;gap:15px;flex-wrap:wrap;font-size:12px;color:var(--muted);margin-top:8px}.dot{display:inline-block;width:9px;height:9px;border-radius:50%;margin-right:5px}
.breakdown{display:grid;gap:13px}.barline{display:grid;grid-template-columns:92px 1fr auto;gap:10px;align-items:center;font-size:13px}.track{height:10px;background:#edf2f7;border-radius:20px;overflow:hidden}.fill{height:100%;border-radius:20px;background:linear-gradient(90deg,#1676bb,#48b5db)}.insight{background:#fff9e6;border:1px solid #f2df9c;padding:12px 14px;border-radius:12px;font-size:13px;margin-top:15px}
.table-wrap{overflow:auto}table{width:100%;border-collapse:collapse;min-width:610px;font-size:13px}th,td{text-align:right;padding:11px 10px;border-bottom:1px solid #e7edf3;white-space:nowrap}th:first-child,td:first-child{text-align:left}thead th{background:#f1f6fb;color:#42576d;font-weight:750}tfoot td{font-weight:800;background:#f7fafc}.bottom{grid-template-columns:1.1fr .9fr;margin-top:15px}.funds{display:grid;grid-template-columns:repeat(3,1fr);gap:10px}.fund{border-radius:13px;padding:13px;background:#eff8ff;border:1px solid #d7eaf8}.fund:nth-child(2){background:#f0f8ed;border-color:#d8ead0}.fund:nth-child(3){background:#fff5e9;border-color:#f3dfc5}.fund strong{display:block;font-size:19px;margin:5px 0}.fund small{color:var(--muted)}.activity{display:flex;justify-content:space-between;gap:12px;padding:10px 0;border-bottom:1px solid #edf1f5;font-size:13px}.activity:last-child{border:0}
footer{text-align:center;color:#8291a1;font-size:12px;padding:20px}
.modal{display:none;position:fixed;inset:0;background:#071b31a6;z-index:5;align-items:center;justify-content:center;padding:16px}.modal.show{display:flex}.modalbox{background:white;border-radius:16px;padding:22px;width:min(440px,100%);box-shadow:0 20px 60px #0003}.formgrid{display:grid;gap:10px}.formgrid label{font-size:13px;font-weight:700}.formgrid input,.formgrid select{width:100%;margin-top:4px}.modalactions{display:flex;justify-content:flex-end;gap:8px;margin-top:15px}
@media(max-width:850px){.kpis{grid-template-columns:repeat(2,1fr)}.two,.bottom{grid-template-columns:1fr}.headrow{align-items:flex-start;flex-direction:column}.period{white-space:normal}}
@media(max-width:520px){main{padding:0 11px}.kpis{gap:9px}.card{padding:13px}.kpi-value{font-size:19px}.funds{grid-template-columns:1fr}.barline{grid-template-columns:75px 1fr auto;font-size:12px}.chart-wrap{height:230px}}
</style>
</head>
<body>
<header><div class="headrow"><div><div class="eyebrow">Laporan transparansi keuangan warga</div><h1>Paguyuban Bapak-Bapak<br>Perumahan Griya Mulya</h1><div class="subtitle">Dashboard Analisis Laporan Keuangan</div></div><div class="period">📅 Periode: Juli – 9 November 2026</div></div></header>
<main>
<div class="toolbar"><div><strong>Ringkasan posisi keuangan</strong><div class="muted">Data berdasarkan infografik yang diberikan</div></div><div class="filters"><select id="monthFilter" aria-label="Filter bulan"><option value="all">Semua periode</option><option value="0">Juli</option><option value="1">Agustus</option><option value="2">September</option><option value="3">Oktober</option><option value="4">November</option></select><button id="addBtn" class="primary">＋ Tambah transaksi</button><button id="resetBtn">Reset data</button></div></div>
<section class="grid kpis">
 <div class="card"><span class="kpi-icon">💰</span><div class="kpi-label">Total saldo keuangan</div><div class="kpi-value" id="balance">Rp11.468.733</div><div class="kpi-foot">Posisi per 9 November 2026</div></div>
 <div class="card"><span class="kpi-icon">📥</span><div class="kpi-label">Total pemasukan</div><div class="kpi-value blue" id="income">Rp9.780.000</div><div class="kpi-foot">Juli – November 2026</div></div>
 <div class="card"><span class="kpi-icon">📤</span><div class="kpi-label">Total pengeluaran</div><div class="kpi-value" id="expense">Rp10.860.767</div><div class="kpi-foot">Juli – November 2026</div></div>
 <div class="card"><span class="kpi-icon">⚖️</span><div class="kpi-label">Surplus / defisit</div><div class="kpi-value red" id="net">-Rp1.080.767</div><div class="kpi-foot">Pemasukan dikurangi pengeluaran</div></div>
</section>
<section class="grid two">
 <div class="card"><h2 class="section-title">📈 Tren saldo keuangan <span class="muted">dalam juta rupiah</span></h2><div class="chart-wrap"><canvas id="trend"></canvas></div><div class="legend"><span><i class="dot" style="background:#1769aa"></i>Saldo akhir bulan</span></div></div>
 <div class="card"><h2 class="section-title">📊 Komposisi saldo per kas</h2><div class="breakdown" id="breakdown"></div><div class="insight">💡 Kas Air merupakan komponen terbesar, sekitar 90,57% dari total saldo. Pengeluaran listrik yang tercatat pada infografik: <b>Rp2.780.767</b>.</div></div>
</section>
<section class="card"><h2 class="section-title">Rekap pemasukan & pengeluaran bulanan <span class="muted">Rupiah (IDR)</span></h2><div class="table-wrap"><table><thead><tr><th>Periode</th><th>Pemasukan</th><th>Pengeluaran</th><th>Surplus / Defisit*</th></tr></thead><tbody id="monthRows"></tbody><tfoot id="totals"></tfoot></table></div><div class="muted" style="margin-top:9px">*Surplus/defisit dihitung otomatis dari pemasukan dikurangi pengeluaran.</div></section>
<section class="grid bottom">
 <div class="card"><h2 class="section-title">🏦 Rincian saldo per kas</h2><div class="funds">
  <div class="fund"><b>💧 Kas Air</b><strong>Rp10.386.733</strong><small>90,57% dari saldo</small></div>
  <div class="fund"><b>👥 Kas Bapak-Bapak (RT)</b><strong>Rp298.000</strong><small>2,60% dari saldo</small></div>
  <div class="fund"><b>🇮🇩 Kas 17 Agustusan</b><strong>Rp784.000</strong><small>6,83% dari saldo</small></div>
 </div></div>
 <div class="card"><h2 class="section-title">📝 Catatan keuangan</h2><div class="activity"><span>Saldo kas air masih di atas Rp10 juta</span><b class="green">Positif</b></div><div class="activity"><span>Kas RT relatif kecil</span><b>Perhatian</b></div><div class="activity"><span>Kas 17 Agustusan tetap positif</span><b class="green">Positif</b></div><div class="activity"><span>Pengeluaran listrik tercatat</span><b>Rp2.780.767</b></div></div>
</section>
<footer>Transparan • Akuntabel • Demi Kebersamaan<br>Dashboard interaktif — angka dapat diperbarui melalui fitur tambah transaksi.</footer>
</main>
<div class="modal" id="modal"><div class="modalbox"><h2 style="margin:0 0 14px">Tambah transaksi</h2><form id="txForm" class="formgrid"><label>Nama transaksi<input id="desc" required placeholder="Contoh: Iuran warga"></label><label>Bulan<select id="txMonth"><option>Juli</option><option>Agustus</option><option>September</option><option>Oktober</option><option>November</option></select></label><label>Jenis transaksi<select id="txType"><option value="in">Pemasukan</option><option value="out">Pengeluaran</option></select></label><label>Nominal (Rp)<input id="amount" type="number" min="1" required placeholder="Contoh: 150000"></label><div class="modalactions"><button type="button" id="cancelBtn">Batal</button><button class="primary" type="submit">Simpan transaksi</button></div></form></div></div>
<script>
const base=[
 {m:'Juli',in:1980000,out:2697710},{m:'Agustus',in:2160000,out:3147854},
 {m:'September',in:1760000,out:1381522},{m:'Oktober',in:2360000,out:2959447},
 {m:'November',in:1520000,out:674234}
];
let data=base.map(x=>({...x})), selected='all';
const fmt=n=>'Rp'+Math.abs(Math.round(n)).toLocaleString('id-ID');
const signed=n=>(n<0?'-':'')+fmt(n);
const $=id=>document.getElementById(id);
function sums(rows){return rows.reduce((a,x)=>({in:a.in+x.in,out:a.out+x.out}),{in:0,out:0})}
function render(){
 const rows=selected==='all'?data:[data[+selected]], s=sums(rows), net=s.in-s.out;
 $('income').textContent=fmt(s.in);$('expense').textContent=fmt(s.out);$('net').textContent=signed(net);
 $('net').className='kpi-value '+(net>=0?'green':'red');
 $('balance').textContent=fmt(11468733);
 $('monthRows').innerHTML=rows.map(x=>{let n=x.in-x.out;return `<tr><td>${x.m} 2026</td><td>${fmt(x.in)}</td><td>${fmt(x.out)}</td><td class="${n>=0?'green':'red'}">${signed(n)}</td></tr>`}).join('');
 $('totals').innerHTML=`<tr><td>Total</td><td>${fmt(s.in)}</td><td>${fmt(s.out)}</td><td class="${net>=0?'green':'red'}">${signed(net)}</td></tr>`;
 const funds=[['Kas Air',10386733],['Kas RT',298000],['Kas 17-an',784000]], total=funds.reduce((a,x)=>a+x[1],0);
 $('breakdown').innerHTML=funds.map(([n,v])=>`<div class="barline"><b>${n}</b><div class="track"><div class="fill" style="width:${v/total*100}%"></div></div><span>${(v/total*100).toFixed(2)}%</span></div><div class="muted" style="margin-top:-10px;margin-left:102px">${fmt(v)}</div>`).join('');
 drawChart();
}
function drawChart(){
 const c=$('trend'),ctx=c.getContext('2d'),w=c.clientWidth,h=c.clientHeight,dpr=window.devicePixelRatio||1;c.width=w*dpr;c.height=h*dpr;ctx.scale(dpr,dpr);ctx.clearRect(0,0,w,h);
 const vals=[10.967,10.844,11.222,11.093,11.469],labels=['Juli','Agustus','September','Oktober','November'];
 const pad={l:43,r:15,t:20,b:38},min=10,max=12,xx=i=>pad.l+i*(w-pad.l-pad.r)/4,yy=v=>pad.t+(max-v)/(max-min)*(h-pad.t-pad.b);
 ctx.font='11px system-ui';ctx.strokeStyle='#e6edf4';ctx.fillStyle='#728196';ctx.lineWidth=1;
 for(let v=10;v<=12.001;v+=.5){let y=yy(v);ctx.beginPath();ctx.moveTo(pad.l,y);ctx.lineTo(w-pad.r,y);ctx.stroke();ctx.fillText(v.toFixed(1).replace('.',','),5,y+4)}
 ctx.strokeStyle='#1769aa';ctx.lineWidth=3;ctx.beginPath();vals.forEach((v,i)=>i?ctx.lineTo(xx(i),yy(v)):ctx.moveTo(xx(i),yy(v)));ctx.stroke();
 vals.forEach((v,i)=>{ctx.fillStyle='#1769aa';ctx.beginPath();ctx.arc(xx(i),yy(v),5,0,Math.PI*2);ctx.fill();ctx.fillStyle='#20364e';ctx.font='bold 11px system-ui';ctx.textAlign='center';ctx.fillText(v.toFixed(3).replace('.',','),xx(i),yy(v)-12);ctx.font='11px system-ui';ctx.fillText(labels[i],xx(i),h-18)});
}
$('monthFilter').addEventListener('change',e=>{selected=e.target.value;render()});
$('addBtn').onclick=()=>$('modal').classList.add('show');$('cancelBtn').onclick=()=>$('modal').classList.remove('show');
$('txForm').onsubmit=e=>{e.preventDefault();let m=$('txMonth').value,idx=data.findIndex(x=>x.m===m),v=Number($('amount').value);if(idx>=0)data[idx][$('txType').value==='in'?'in':'out']+=v;$('modal').classList.remove('show');e.target.reset();render()};
$('resetBtn').onclick=()=>{data=base.map(x=>({...x}));selected='all';$('monthFilter').value='all';render()};
window.addEventListener('resize',drawChart);render();
</script>
</body></html>
