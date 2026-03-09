<!DOCTYPE html>
<html lang="zh-TW">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>2026 菩薩戒行前準備</title>

<style>
/* ===== 全站基礎設定 ===== */
* {
  box-sizing: border-box; /* 防止 Padding 撐開寬度 */
}

body {
  margin: 0;
  padding: 0;
  font-family: "Noto Serif TC", serif;
  background: #2c1b0f; /* 深色背景 */
  background-attachment: fixed;
  color: #333;
  line-height: 1.6;
}

/* ===== 核心包覆層：確保導覽列與內容同寬 ===== */
.main-wrapper {
  max-width: 800px; /* 寬度設定，可根據需求調整 (建議 800-900) */
  margin: 0 auto;   /* 置中 */
  width: 100%;      /* 手機版自動滿版 */
  padding: 0 10px;  /* 側邊留白防止手機版貼邊 */
}

/* ===== 導覽列優化 ===== */
.nav {
  display: flex;
  background: #3a2416;
  border-bottom: 3px solid #c6a55a;
  border-radius: 15px 15px 0 0; /* 上方圓角 */
  overflow: hidden; /* 確保圓角生效 */
  margin-top: 20px;
}

.nav button {
  flex: 1;
  padding: 15px 5px;
  border: none;
  background: transparent;
  color: #e6d3a3;
  font-size: 15px;
  cursor: pointer;
  transition: all 0.3s ease;
  white-space: nowrap; /* 防止文字換行 */
}

.nav button.active {
  background: #5a3a22;
  color: #ffd700;
  font-weight: bold;
  box-shadow: inset 0 -4px 0 #c6a55a;
}

.nav button:hover {
  background: #4a3426;
}

/* ===== 主內容容器 ===== */
.container {
  width: 100%;
}

/* ===== 分頁卡片優化 ===== */
.page {
  display: none;
  background: #fffaf0;
  padding: 30px;
  border-radius: 0 0 15px 15px; /* 下方圓角 */
  box-shadow: 0 10px 40px rgba(0,0,0,0.5);
  min-height: 60vh;
}

.page.active {
  display: block;
  animation: fadeIn 0.4s ease-out;
}

@keyframes fadeIn {
  from { opacity: 0; transform: translateY(10px); }
  to { opacity: 1; transform: translateY(0); }
}

h1 {
  text-align: center;
  color: #8c6239;
  margin-top: 0;
  font-size: 1.6rem;
}

h2 {
  color: #6d4c2f;
  margin-top: 25px;
  border-left: 4px solid #c6a55a;
  padding-left: 10px;
}

label {
  display: block;
  margin: 12px 0;
  padding: 8px;
  background: rgba(140, 98, 57, 0.05);
  border-radius: 5px;
  cursor: pointer;
}

/* ===== 按鈕與工具 ===== */
.mainBtn {
  margin-top: 30px;
  width: 100%;
  padding: 16px;
  border: none;
  border-radius: 10px;
  background: #8c6239;
  color: white;
  font-size: 16px;
  font-weight: bold;
  cursor: pointer;
  transition: background 0.3s;
}

.mainBtn:hover {
  background: #6d4c2f;
}

.downloadBtn {
  margin-bottom: 15px;
  width: 100%;
  padding: 12px;
  border: 1px solid #c6a55a;
  border-radius: 8px;
  background: #fff;
  color: #3a2416;
  font-weight: bold;
  cursor: pointer;
}

/* ===== PDF 區域優化 ===== */
.pdf-wrapper {
  margin-top: 10px;
  width: 100%;
  height: 60vh;
  border: 2px solid #e6d3a3;
  border-radius: 8px;
  overflow: hidden;
  background: #eee;
}

.pdf-wrapper iframe {
  width: 100%;
  height: 100%;
  border: none;
}

/* ===== 列表樣式 ===== */
ul {
  padding-left: 20px;
}

li {
  margin-bottom: 10px;
}

.result {
  text-align: center;
  margin-top: 15px;
  font-size: 1.1rem;
  color: #8c6239;
}

/* 手機版微調 */
@media (max-width: 600px) {
  .nav button {
    font-size: 13px;
    padding: 12px 2px;
  }
  .page {
    padding: 20px;
  }
}
</style>
</head>

<body>

<div class="main-wrapper">
  <div class="nav">
    <button onclick="showPage(0)" class="active">準備清單</button>
    <button onclick="showPage(1)">四天作息</button>
    <button onclick="showPage(2)">生活規矩</button>
    <button onclick="showPage(3)">殿堂規矩</button>
    <button onclick="showPage(4)">齋堂規矩</button>
  </div>

  <div class="container">
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

    <div class="page">
      <h1>⏰ 四天作息表</h1>
      <button class="downloadBtn" onclick="downloadPDF()">⬇ 下載/另開視窗查看 PDF</button>
      <div class="pdf-wrapper">
        <iframe src="作息表.pdf#view=FitH"></iframe>
      </div>
    </div>

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
  
  <p style="text-align:center; color:#e6d3a3; font-size:12px; margin:20px 0;">© 2026 菩薩戒行持手冊</p>
</div>

<script>
function playBell(){
  try {
    let audioCtx=new(window.AudioContext||window.webkitAudioContext)();
    let osc=audioCtx.createOscillator();
    let gain=audioCtx.createGain();
    osc.connect(gain);
    gain.connect(audioCtx.destination);
    osc.type="sine";
    osc.frequency.setValueAtTime(600,audioCtx.currentTime);
    gain.gain.setValueAtTime(0.1,audioCtx.currentTime);
    gain.gain.exponentialRampToValueAtTime(0.0001, audioCtx.currentTime + 0.5);
    osc.start();
    osc.stop(audioCtx.currentTime+0.5);
  } catch(e) { console.log("Audio play failed"); }
}

function showPage(index){
  let pages=document.querySelectorAll(".page");
  let buttons=document.querySelectorAll(".nav button");
  pages.forEach(p=>p.classList.remove("active"));
  buttons.forEach(b=>b.classList.remove("active"));
  pages[index].classList.add("active");
  buttons[index].classList.add("active");
  playBell();
  window.scrollTo({top: 0, behavior: 'smooth'});
}

function checkComplete(){
  let boxes=document.querySelectorAll('input[type="checkbox"]');
  let checked=[...boxes].filter(b=>b.checked).length;
  let res = document.getElementById("result");
  if(checked===boxes.length) {
    res.innerHTML = "🎉 準備完成！祝福圓滿受戒 🙏";
    res.style.color = "#2d5a27";
  } else {
    res.innerHTML = "尚有 "+(boxes.length-checked)+" 項未確認";
    res.style.color = "#8c6239";
  }
}

function downloadPDF(){
  window.open("作息表.pdf","_blank");
}
</script>

</body>
</html>
