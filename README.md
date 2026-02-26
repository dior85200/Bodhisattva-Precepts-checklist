<!DOCTYPE html>
<html lang="zh-TW">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>2026 菩薩戒行前準備</title>

<style>
body{
margin:0;
font-family: "Noto Serif TC", serif;
background:linear-gradient(#2c1b0f,#4b2e1d);
color:#333;
}

.nav{
display:flex;
background:#3a2416;
border-bottom:2px solid #c6a55a;
}

.nav button{
flex:1;
padding:14px;
border:none;
background:#3a2416;
color:#e6d3a3;
font-size:14px;
}

.nav button.active{
background:#5a3a22;
color:#ffd700;
}

.container{
padding:20px;
max-width:800px;
margin:auto;
}

.page{
display:none;
background:#fffaf0;
padding:25px;
border-radius:15px;
box-shadow:0 8px 30px rgba(0,0,0,.4);
}

.page.active{
display:block;
}

h1{
text-align:center;
color:#8c6239;
}

h2{
color:#6d4c2f;
margin-top:20px;
}

label{
display:block;
margin:6px 0;
}

button.mainBtn{
margin-top:20px;
width:100%;
padding:14px;
border:none;
border-radius:10px;
background:#8c6239;
color:white;
font-size:15px;
}

.downloadBtn{
margin-top:15px;
width:100%;
padding:12px;
border:none;
border-radius:8px;
background:#c6a55a;
color:#3a2416;
font-weight:bold;
}

.result{
text-align:center;
margin-top:10px;
font-weight:bold;
}

.pdf-container{
margin-top:15px;
height:70vh;
border:1px solid #c6a55a;
}
</style>
</head>

<body>

<div class="nav">
<button onclick="showPage(0)" class="active">準備清單</button>
<button onclick="showPage(1)">四天作息</button>
<button onclick="showPage(2)">生活規矩</button>
<button onclick="showPage(3)">殿堂規矩</button>
<button onclick="showPage(4)">齋堂規矩</button>
</div>

<div class="container">

<!-- 準備清單 -->
<div class="page active">
<h1>🧘 菩薩戒行前準備</h1>

<h2>📦 必備物品</h2>
<label><input type="checkbox"> 健保卡</label>
<label><input type="checkbox"> 海青</label>
<label><input type="checkbox"> 盥洗用品</label>
<label><input type="checkbox"> 茶杯</label>
<label><input type="checkbox"> 黑色襪子</label>
<label><input type="checkbox"> 室外拖鞋</label>
<label><input type="checkbox"> 睡袋或棉被</label>

<h2>🚫 禁止攜帶</h2>
<label><input type="checkbox"> 個人電腦</label>
<label><input type="checkbox"> 食物</label>
<label><input type="checkbox"> 書籍雜誌</label>
<label><input type="checkbox"> 貴重物品</label>

<button class="mainBtn" onclick="checkComplete()">完成確認</button>
<div class="result" id="result"></div>
</div>

<!-- 作息頁（嵌入PDF） -->
<div class="page">
<h1>⏰ 四天作息表</h1>

<button class="downloadBtn" onclick="downloadPDF()">⬇ 下載作息表 PDF</button>

<div class="pdf-container">
<iframe src="作息表.pdf" width="100%" height="100%"></iframe>
</div>
</div>

<!-- 生活規矩 -->
<div class="page">
<h1>🙏 生活注意事項</h1>
<ul>
<li>輕聲行動，不打擾大眾</li>
<li>寮房禁止說話</li>
<li>不可私自外出會客</li>
<li>作息以法器訊號為準</li>
<li>不可私自更換床位</li>
</ul>
</div>

<!-- 殿堂規矩 -->
<div class="page">
<h1>🏯 殿堂注意事項</h1>
<ul>
<li>不得遲到</li>
<li>名牌別掛海青</li>
<li>保持莊嚴肅靜</li>
<li>不得交頭接耳</li>
<li>服從戒師指導</li>
</ul>
</div>

<!-- 齋堂規矩 -->
<div class="page">
<h1>🍚 齋堂注意事項</h1>
<ul>
<li>合掌念佛入堂</li>
<li>依序入座</li>
<li>用齋不出聲</li>
<li>食畢默念佛號</li>
</ul>
</div>

</div>

<script>

// 法器音效（簡易鐘聲）
function playBell(){
let audioCtx = new (window.AudioContext || window.webkitAudioContext)();
let oscillator = audioCtx.createOscillator();
let gainNode = audioCtx.createGain();

oscillator.connect(gainNode);
gainNode.connect(audioCtx.destination);

oscillator.type = "sine";
oscillator.frequency.setValueAtTime(600, audioCtx.currentTime);
gainNode.gain.setValueAtTime(0.2, audioCtx.currentTime);

oscillator.start();
oscillator.stop(audioCtx.currentTime + 0.5);
}

function showPage(index){
let pages=document.querySelectorAll(".page");
let buttons=document.querySelectorAll(".nav button");

pages.forEach(p=>p.classList.remove("active"));
buttons.forEach(b=>b.classList.remove("active"));

pages[index].classList.add("active");
buttons[index].classList.add("active");

playBell();
}

function checkComplete(){
let checkboxes=document.querySelectorAll('input[type="checkbox"]');
let total=checkboxes.length;
let checked=0;

checkboxes.forEach(box=>{
if(box.checked){checked++;}
});

if(checked===total){
document.getElementById("result").innerHTML="🎉 準備完成！祝福圓滿受戒 🙏";
}else{
document.getElementById("result").innerHTML="尚有 "+(total-checked)+" 項未確認";
}
}

function downloadPDF(){
window.open("作息表.pdf","_blank");
}

</script>

</body>
</html>
