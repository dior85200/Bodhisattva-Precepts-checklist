<!DOCTYPE html>
<html lang="zh-TW">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>2026 菩薩戒行前準備 CHECKLIST</title>

<style>
body{
font-family:-apple-system,BlinkMacSystemFont,"Segoe UI";
background:linear-gradient(#f4f1e8,#e8dcc7);
margin:0;
padding:20px;
}

.container{
max-width:600px;
margin:auto;
background:white;
padding:30px;
border-radius:20px;
box-shadow:0 10px 30px rgba(0,0,0,.15);
}

h1{
text-align:center;
color:#8c6239;
font-size:26px;
margin-bottom:5px;
}

.subtitle{
text-align:center;
font-size:14px;
color:#777;
margin-bottom:20px;
}

.section{
margin-top:25px;
padding-top:15px;
border-top:1px solid #eee;
}

h2{
color:#6d4c2f;
font-size:20px;
margin-bottom:10px;
}

.small-note{
font-size:13px;
color:#888;
margin-bottom:10px;
}

label{
display:block;
margin:6px 0;
font-size:16px;
}

.small{
font-size:13px;
color:#666;
margin-left:22px;
margin-top:-4px;
margin-bottom:6px;
}

button{
margin-top:25px;
width:100%;
padding:15px;
border:none;
border-radius:12px;
background:#8c6239;
color:white;
font-size:16px;
}

.result{
margin-top:15px;
text-align:center;
font-weight:bold;
font-size:18px;
}
</style>
</head>

<body>

<div class="container">

<h1>🧘 2026 菩薩戒行前準備</h1>
<div class="subtitle">請逐項確認，圓滿受戒 🙏</div>

<!-- 攜帶物品 -->
<div class="section">
<h2>📦 必備攜帶物品</h2>
<div class="small-note">報到時需準備齊全</div>

<label><input type="checkbox"> 健保卡</label>
<label><input type="checkbox"> 海青</label>
<label><input type="checkbox"> 盥洗用品</label>
<label><input type="checkbox"> 茶杯</label>
<label><input type="checkbox"> 黑色襪子</label>
<label><input type="checkbox"> 室外拖鞋（衛浴專用）</label>
<label><input type="checkbox"> 睡袋或棉被</label>
<div class="small">※ 不提供寢具，請務必自備</div>
<div class="small">※ 請勿使用塑膠袋裝物品（環保與安靜）</div>
</div>

<!-- 建議攜帶 -->
<div class="section">
<h2>👜 評估攜帶</h2>
<label><input type="checkbox"> 口罩</label>
<label><input type="checkbox"> 生理用品</label>
<label><input type="checkbox"> 自用藥品</label>
<label><input type="checkbox"> 耳塞</label>
<label><input type="checkbox"> 眼罩</label>
</div>

<!-- 禁止攜帶 -->
<div class="section">
<h2>🚫 禁止攜帶</h2>
<div class="small-note">違規物品請勿帶入戒壇</div>
<label><input type="checkbox"> 個人電腦</label>
<label><input type="checkbox"> 食物</label>
<label><input type="checkbox"> 書籍雜誌</label>
<label><input type="checkbox"> 貴重物品</label>
</div>

<!-- 作息提醒 -->
<div class="section">
<h2>⏰ 作息提醒</h2>
<label><input type="checkbox"> 4:10 起板</label>
<label><input type="checkbox"> 依照法器訊號作息</label>
<label><input type="checkbox"> 準時集合、不遲到</label>
<label><input type="checkbox"> 21:30 安板</label>
</div>

<!-- 戒壇規矩 -->
<div class="section">
<h2>🙏 戒壇規矩</h2>
<label><input type="checkbox"> 戒期間絕對禁語</label>
<label><input type="checkbox"> 不可私自換床位</label>
<label><input type="checkbox"> 不可私自外出</label>
<label><input type="checkbox"> 保持寮房整潔</label>
<label><input type="checkbox"> 尊重戒師與護戒法師指導</label>
</div>

<button onclick="checkComplete()">完成確認</button>

<div class="result" id="result"></div>

</div>

<script>
function checkComplete(){
let checkboxes = document.querySelectorAll('input[type="checkbox"]');
let total = checkboxes.length;
let checked = 0;

checkboxes.forEach(box=>{
if(box.checked){checked++;}
});

if(checked === total){
document.getElementById("result").innerHTML="🎉 所有項目確認完成！祝福圓滿受戒 🙏";
document.getElementById("result").style.color="#4caf50";
}else{
document.getElementById("result").innerHTML="尚有 "+(total-checked)+" 項未確認";
document.getElementById("result").style.color="#d84315";
}
}
</script>

</body>
</html>
