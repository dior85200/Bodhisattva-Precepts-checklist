<!DOCTYPE html>
<html lang="zh-TW">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>菩薩戒行前準備 CHECKLIST</title>

<style>
body{
font-family:-apple-system,BlinkMacSystemFont,"Segoe UI";
background:linear-gradient(#f4f1e8,#e8dcc7);
margin:0;
padding:20px;
}

.container{
max-width:500px;
margin:auto;
background:white;
padding:25px;
border-radius:20px;
box-shadow:0 10px 30px rgba(0,0,0,.15);
}

h1{
text-align:center;
color:#8c6239;
}

h2{
color:#6d4c2f;
margin-top:25px;
}

label{
display:block;
margin:8px 0;
font-size:16px;
}

button{
margin-top:20px;
width:100%;
padding:14px;
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
color:#4caf50;
}
</style>
</head>

<body>

<div class="container">

<h1>🧘 菩薩戒行前準備 CHECKLIST</h1>

<h2>📦 攜帶物品</h2>
<label><input type="checkbox"> 健保卡</label>
<label><input type="checkbox"> 海青</label>
<label><input type="checkbox"> 盥洗用品</label>
<label><input type="checkbox"> 茶杯</label>
<label><input type="checkbox"> 黑色襪子</label>
<label><input type="checkbox"> 室外拖鞋</label>
<label><input type="checkbox"> 睡袋或棉被</label>

<h2>👜 建議攜帶</h2>
<label><input type="checkbox"> 口罩</label>
<label><input type="checkbox"> 生理用品</label>
<label><input type="checkbox"> 自用藥品</label>
<label><input type="checkbox"> 耳塞或眼罩</label>

<h2>🚫 禁止攜帶</h2>
<label><input type="checkbox"> 個人電腦</label>
<label><input type="checkbox"> 食物</label>
<label><input type="checkbox"> 書籍雜誌</label>
<label><input type="checkbox"> 貴重物品</label>

<h2>⏰ 作息提醒</h2>
<label><input type="checkbox"> 4:10 起板</label>
<label><input type="checkbox"> 依照法器訊號作息</label>
<label><input type="checkbox"> 21:30 安板</label>

<h2>🙏 戒壇規矩</h2>
<label><input type="checkbox"> 戒期間禁語</label>
<label><input type="checkbox"> 不可私自換床位</label>
<label><input type="checkbox"> 保持整潔</label>
<label><input type="checkbox"> 尊重戒師指導</label>

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
document.getElementById("result").innerHTML="🎉 準備圓滿！可以安心受戒 🙏";
}else{
document.getElementById("result").innerHTML="還有 "+(total-checked)+" 項尚未確認喔！";
}
}
</script>

</body>
</html>
