<!DOCTYPE html>
<html lang="zh-TW">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>2026 菩薩戒行前準備</title>

<style>
/* ===== 全站基礎 ===== */
body{
  margin:0;
  font-family:"Noto Serif TC", serif;
  background:linear-gradient(#2c1b0f,#4b2e1d);
  color:#333;
}

/* ===== 導覽列 ===== */
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

/* ===== 主容器 ===== */
.container{
  padding:20px;
  max-width:900px;
  margin:auto;
}

/* ===== 分頁卡片 ===== */
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

/* ===== 按鈕 ===== */
.mainBtn{
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

/* ===== 結果文字 ===== */
.result{
  text-align:center;
  margin-top:10px;
  font-weight:bold;
}

/* ===== PDF 顯示（GitHub Pages 穩定版） ===== */
.pdf-wrapper{
  margin-top:15px;
  width:100%;
  height:70vh;
  border:1px solid #c6a55a;
  overflow:hidden;
  background:#fffaf0;
}

.pdf-wrapper iframe{
  width:100%;
  height:100%;
  border:none;
}
</style>
</head>

<body>

<!-- ===== 導覽 ===== -->
<div class="nav">
  <button onclick="showPage(0)" class="active">準備清單</button>
  <button onclick="showPage(1)">四天作息</button>
  <button onclick="showPage(2)">生活規矩</button>
  <button onclick="showPage(3)">殿堂規矩</button>
  <button onclick="showPage(4)">齋堂規矩</button>
</div>

<div class="container">

<!-- ===== 準備清單 ===== -->
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

<!-- ===== 作息表 ===== -->
<div class="page">
  <h1>⏰ 四天作息表</h1>

  <button class="downloadBtn" onclick="downloadPDF()">⬇ 下載作息表 PDF</button>

  <div class="pdf-wrapper">
    <iframe src="作息表.pdf#view=FitH"></iframe>
  </div>
</div>

<!-- ===== 生活規矩 ===== -->
<div class="page">
  <h1>🙏 生活注意事項</h1>
  <ul>
    <li>輕聲行動，不打擾大眾</li>
    <li>寮房內保持安靜</li>
    <li>不可私自外出或會客</li>
    <li>一切作息以法器訊號為準</li>
    <li>不可私自更換床位</li>
  </ul>
</div>

<!-- ===== 殿堂規矩 ===== -->
<div class="page">
  <h1>🏯 殿堂注意事項</h1>
  <ul>
    <li>準時入殿，不得遲到</li>
    <li>名牌不得別於海青</li>
    <li>保持莊嚴肅靜</li>
    <li>不得交頭接耳</li>
    <li>一切依戒師指導</li>
  </ul>
</div>

<!-- ===== 齋堂規矩 ===== -->
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
/* ===== 簡易鐘聲 ===== */
function playBell(){
  let audioCtx=new(window.AudioContext||window.webkitAudioContext)();
  let osc=audioCtx.createOscillator();
  let gain=audioCtx.createGain();
  osc.connect(gain);
  gain.connect(audioCtx.destination);
  osc.type="sine";
  osc.frequency.setValueAtTime(600,audioCtx.currentTime);
  gain.gain.setValueAtTime(0.2,audioCtx.currentTime);
  osc.start();
  osc.stop(audioCtx.currentTime+0.4);
}

/* ===== 分頁切換 ===== */
function showPage(index){
  let pages=document.querySelectorAll(".page");
  let buttons=document.querySelectorAll(".nav button");
  pages.forEach(p=>p.classList.remove("active"));
  buttons.forEach(b=>b.classList.remove("active"));
  pages[index].classList.add("active");
  buttons[index].classList.add("active");
  playBell();
}

/* ===== 勾選檢查 ===== */
function checkComplete(){
  let boxes=document.querySelectorAll('input[type="checkbox"]');
  let checked=[...boxes].filter(b=>b.checked).length;
  document.getElementById("result").innerHTML=
    checked===boxes.length
    ? "🎉 準備完成！祝福圓滿受戒 🙏"
    : "尚有 "+(boxes.length-checked)+" 項未確認";
}

/* ===== PDF 下載 ===== */
function downloadPDF(){
  window.open("作息表.pdf","_blank");
}
</script>

</body>
</html>
