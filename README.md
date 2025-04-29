
<html lang="zh-Hant">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>美麗媽的秘製食譜</title>
  <!-- 引入手寫感字體 -->
<link href="https://fonts.googleapis.com/css2?family=Caveat&display=swap" rel="stylesheet">
 
  <style>
    h1:first-of-type {
  display: none;
}

    /* 整體頁面設定 */
    body {
      font-family: 'Patrick Hand', '微軟正黑體', sans-serif;
      background:rgb(241, 233, 252); /* 淡紫灰背景 */
      margin: 0;
      padding: 20px;
      color: #333;
    }

    /* 主標題設定 */
    h1 {
      text-align: center;
      color:rgb(130, 98, 169); /* 灰紫色 */
      background-color:rgb(230, 223, 251); /* 很淡的紫色背景 */
      padding: 20px;
      border-radius: 12px;
      margin-bottom: 30px;
      font-size: 36px;
    }

    /* 搜尋框設定 */
    #searchInput {
      display: block;
      margin: 0 auto 20px auto;
      padding: 10px 20px;
      font-size: 16px;
      border: 2px solid #c8e6c9;
      border-radius: 50px;
      width: 80%;
      max-width: 400px;
    }

    /* 按鈕區塊 */
    .buttons {
      text-align: center;
      margin-bottom: 20px;
    }

    /* 按鈕樣式設定 */
    .buttons button {
      background:rgb(152, 246, 236); /* 藍綠色（比之前更柔和） */
      border: none;
      padding: 12px 20px;
      margin: 5px;
      font-size: 16px;
      cursor: pointer;
      border-radius: 50px;
      transition: background 0.3s;
      color: #333;
      font-family: 'Patrick Hand', '微軟正黑體', sans-serif;
    }

    /* 按鈕懸停效果 */
    .buttons button:hover {
      background:rgb(118, 222, 211); /* 深一點點藍綠 */
    }

    /* 食譜卡片樣式 */
    .recipe {
      background: #ffffff; /* 白色卡片 */
      border: 3px solid #e0d7f3;(225, 213, 249); /* 柔紫色邊框 */
      border-radius: 12px;
      padding: 20px;
      margin: 15px auto;
      max-width: 600px;
      box-shadow: 2px 2px 10px rgba(0,0,0,0.05);
    }

    /* 卡片內的標題 */
    .recipe h2 {
      margin-top: 0;
      color: #a480cf;
      font-family: 'Patrick Hand', '微軟正黑體', sans-serif;
    }

    /* 小標題 (食材、步驟) */
    .section-title {
      font-weight: bold;
      margin-top: 15px;
      color: #6a4c93; /* 深紫色 */
      font-size: 18px;
    }

    /* 頁尾版權 */
    footer {
      text-align: center;
      margin-top: 40px;
      font-size: 14px;
      color: #999;
      font-family: 'Patrick Hand', '微軟正黑體', sans-serif;
    }
  </style>
</head>

<body>

<h1>美麗媽的秘製食譜</h1>

<!-- 搜尋欄 -->
<input type="text" id="searchInput" placeholder="搜尋食譜..." onkeyup="searchRecipes()">

<!-- 分類按鈕 -->
<div class="buttons">
  <button onclick="filterRecipes('全部')">全部</button>
  <button onclick="filterRecipes('家常菜')">家常菜</button>
  <button onclick="filterRecipes('甜點')">甜點</button>
  <button onclick="filterRecipes('麵包／早餐')">麵包／早餐</button>
  <button onclick="filterRecipes('鹹的')">鹹的</button>
  <button onclick="filterRecipes('肉類')">肉類</button>
  <button onclick="filterRecipes('其他')">其他</button>
</div>

<!-- 食譜卡片們 -->
<div id="recipes">
  <div class="recipe" data-category="家常菜 肉類">
    <h2>香煎雞腿排</h2>
    <div class="section-title">食材：</div>
    <ul>
      <li>去骨雞腿排 2片</li>
      <li>鹽 少許</li>
      <li>黑胡椒 少許</li>
      <li>橄欖油 1大匙</li>
    </ul>
    <div class="section-title">步驟：</div>
    <ol>
      <li>雞腿排用鹽和黑胡椒均勻醃10分鐘。</li>
      <li>平底鍋加熱，放入橄欖油。</li>
      <li>雞皮朝下小火煎至金黃，再翻面煎熟即可。</li>
    </ol>
  </div>

  <div class="recipe" data-category="甜點 其他">
    <h2>蜂蜜檸檬果凍</h2>
    <div class="section-title">食材：</div>
    <ul>
      <li>檸檬汁 50ml</li>
      <li>蜂蜜 3大匙</li>
      <li>吉利丁粉 10g</li>
      <li>水 300ml</li>
    </ul>
    <div class="section-title">步驟：</div>
    <ol>
      <li>將水加熱至溫暖，加入吉利丁粉攪拌溶解。</li>
      <li>拌入蜂蜜與檸檬汁。</li>
      <li>倒入模具中，冷藏4小時至凝固。</li>
    </ol>
  </div>

  <div class="recipe" data-category="麵包／早餐 甜點">
    <h2>鬆餅</h2>
    <div class="section-title">食材：</div>
    <ul>
      <li>低筋麵粉 200g</li>
      <li>牛奶 150ml</li>
      <li>蛋 1顆</li>
      <li>砂糖 2大匙</li>
      <li>泡打粉 1小匙</li>
    </ul>
    <div class="section-title">步驟：</div>
    <ol>
      <li>將所有材料攪拌均勻成麵糊。</li>
      <li>平底鍋加熱後，小火煎至兩面金黃。</li>
      <li>可依喜好搭配果醬或蜂蜜食用。</li>
    </ol>
  </div>
</div>

<!-- 版權 -->
<footer>
  Copyright © 2025 美麗媽
</footer>

<!-- JavaScript 部分 -->
<script>
function filterRecipes(category) {
  var recipes = document.getElementsByClassName('recipe');
  for (var i = 0; i < recipes.length; i++) {
    if (category === '全部') {
      recipes[i].style.display = 'block';
    } else {
      if (recipes[i].getAttribute('data-category').includes(category)) {
        recipes[i].style.display = 'block';
      } else {
        recipes[i].style.display = 'none';
      }
    }
  }
}

function searchRecipes() {
  var input = document.getElementById('searchInput').value.toLowerCase();
  var recipes = document.getElementsByClassName('recipe');
  for (var i = 0; i < recipes.length; i++) {
    var text = recipes[i].innerText.toLowerCase();
    if (text.includes(input)) {
      recipes[i].style.display = 'block';
    } else {
      recipes[i].style.display = 'none';
    }
  }
}
</script>

</body>
</html>

      
