<!DOCTYPE html>
<html lang="zh-TW">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>2026 菩薩戒行前準備</title>

<style>
body{
font-family:-apple-system,BlinkMacSystemFont,"Segoe UI";
background:linear-gradient(#f4f1e8,#e8dcc7);
margin:0;
}

.nav{
display:flex;
overflow-x:auto;
background:#8c6239;
}

.nav button{
flex:1;
padding:12px;
border:none;
background:#8c6239;
color:white;
font-size:14px;
}

.nav button.active{
background:#6d4c2f;
}

.container{
padding:20px;
max-width:700px;
margin:auto;
}

.page{
display:none;
background:white;
padding:25px;
border-radius:20px;
box-shadow:0 10px 30px rgba(0,0,0,.15);
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

.small{
font-size:13px;
color:#666;
margin-left:18px;
}

button.checkBtn{
margin-top:20px;
width:100%;
padding:14px;
border:none;
border-radius:12px;
background:#8c6239;
color:white;
}

.result{
text-align:center;
margin-top:10px;
font-weight:bold;
}

table{
width:100%;
border-collapse:collapse;
margin-top:10px;
}

table td, table th{
border:1px solid #ddd;
padding:8px;
font-size:14px;
}

table th{
background:#f0e6d6;
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
<h1>🧘 行前準備 CHECKLIST</h1>

<h2>📦 必備物品</h2>
<label><input type="checkbox"> 健保卡</label>
<label><input type="checkbox"> 海青</label>
<label><input type="checkbox"> 盥洗用品</label>
<label><input type="checkbox"> 茶杯</label>
<label><input type="checkbox"> 黑色襪子</label>
<label><input type="checkbox"> 室外拖鞋</label>
<label><input type="checkbox"> 睡袋或棉被</label>
<div class="small">※ 不提供寢具，請務必自備</div>

<h2>🚫 禁止攜帶</h2>
<label><input type="checkbox"> 個人電腦</label>
<label><input type="checkbox"> 食物</label>
<label><input type="checkbox"> 書籍雜誌</label>
<label><input type="checkbox"> 貴重物品</label>

<button class="checkBtn" onclick="checkComplete()">完成確認</button>
<div class="result" id="result"></div>
</div>

<!-- 作息表 -->
<div class="page">
<h1>⏰ 四天作息表</h1>

<table>
<tr><th>時間</th><th>內容</th></tr>
<tr><td>4:10</td><td>起板、叩鐘、擊鼓</td></tr>
<tr><td>5:00–6:40</td><td>早課、說戒</td></tr>
<tr><td>6:40–8:00</td><td>早齋、個人時間</td></tr>
<tr><td>8:10–12:00</td><td>演禮、說戒</td></tr>
<tr><td>12:00–13:45</td><td>午齋、午休</td></tr>
<tr><td>下午</td><td>演禮／誦戒／圓滿</td></tr>
<tr><td>17:00–18:00</td><td>藥石、盥洗</td></tr>
<tr><td>18:30–21:30</td><td>懺摩、說戒、授幽冥戒</td></tr>
<tr><td>21:30–22:00</td><td>擊鼓、叩鐘、安板</td></tr>
</table>

</div>

<!-- 生活規矩 -->
<div class="page">
<h1>🙏 生活注意事項</h1>
<ul>
<li>輕聲行動，避免打擾</li>
<li>寮房禁止說話</li>
<li>不得私自外出或會客</li>
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
function showPage(index){
let pages=document.querySelectorAll(".page");
let buttons=document.querySelectorAll(".nav button");

pages.forEach(p=>p.classList.remove("active"));
buttons.forEach(b=>b.classList.remove("active"));

pages[index].classList.add("active");
buttons[index].classList.add("active");
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
</script>

</body>
</html>
