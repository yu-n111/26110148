<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <link rel="stylesheet" href="./style.css">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pen</title>
  </head>
  <body>

    <script src="./script.js"></script>
  </body>
</html>
<!DOCTYPE html>
<html lang="zh-TW">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>今天吃什麼？ | 隨機抽籤機</title>
  
  <!-- 載入 CSS 樣式表 -->
  <link rel="stylesheet" href="style.css">
  
  <!-- Google 字體 -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+TC:wght@400;500;700&display=swap" rel="stylesheet">
  
  <!-- 載入 JavaScript (加上 defer 確保頁面載入後執行) -->
  <script src="script.js" defer></script>
</head>
<body>

  <div class="card">
    <span class="badge">FOOD DECIDER</span>
    
    <!-- 大標題／抽籤結果顯示區 -->
    <h1 id="food-title" class="title">今天吃什麼？</h1>
    
    <!-- 圖片顯示區 -->
    <div class="image-wrapper">
      <img id="food-image" src="https://images.unsplash.com/photo-1504674900247-0877df9cc836?q=80&w=800&auto=format&fit=crop" alt="食物圖片">
    </div>

    <!-- 按鈕區 -->
    <div class="button-group">
      <button id="draw-btn" class="btn btn-primary">點我抽籤</button>
      <a id="map-link" href="#" target="_blank" class="btn btn-secondary disabled">馬上出發 ➔</a>
    </div>
  </div>

</body>
</html>
html {
  height: 100%;
  background: 50% 50% no-repeat
    url('data:image/svg+xml,<svg viewBox="-20 -5 60 40" width="140" xmlns="http://www.w3.org/2000/svg" opacity="0.2"><path d="M1 8l11-7 11 7v8l-11 7-11-7zm0 0l11 8 11-8m0 8L12 8 1 16M12 1v7m0 8v7" fill="none" stroke="currentColor" stroke-linejoin="round" stroke-width="2"/><text x="-12" y="32" font-size="5" font-family="monospace" fill="currentColor">Built on CodePen</text></svg>');
}
/* 全域重設與INS風極簡設定 */
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  font-family: 'Noto Sans TC', sans-serif;
}

body {
  background-color: #f7f7f8;
  color: #333333;
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  padding: 20px;
}

/* INS 風格卡片容器 */
.card {
  background: #ffffff;
  width: 100%;
  max-width: 420px;
  border-radius: 24px;
  padding: 32px 24px;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.05);
  border: 1px solid #eaeaea;
  text-align: center;
}

/* 小標籤 */
.badge {
  display: inline-block;
  font-size: 0.75rem;
  font-weight: 700;
  letter-spacing: 2px;
  color: #8e8e93;
  background-color: #f2f2f7;
  padding: 4px 12px;
  border-radius: 20px;
  margin-bottom: 16px;
}

/* 主標題 */
.title {
  font-size: 1.8rem;
  font-weight: 700;
  color: #1c1c1e;
  margin-bottom: 24px;
  min-height: 2.4rem;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: transform 0.2s ease;
}

/* 生動彈跳動畫類別 (由 JS 動態新增) */
.bounce-pop {
  animation: bouncePop 0.6s cubic-bezier(0.175, 0.885, 0.32, 1.275);
}

@keyframes bouncePop {
  0% {
    opacity: 0.3;
    transform: scale(0.7);
  }
  50% {
    transform: scale(1.15);
  }
  100% {
    opacity: 1;
    transform: scale(1);
  }
}

/* 圖片外框與圖片 */
.image-wrapper {
  width: 100%;
  height: 220px;
  border-radius: 16px;
  overflow: hidden;
  background-color: #f2f2f7;
  margin-bottom: 28px;
  border: 1px solid #f0f0f0;
}

.image-wrapper img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: opacity 0.3s ease;
}

/* 按鈕群組 */
.button-group {
  display: flex;
  flex-direction: column;
  gap: 12px;
}

.btn {
  display: inline-block;
  width: 100%;
  padding: 14px 0;
  border-radius: 12px;
  font-size: 1rem;
  font-weight: 500;
  text-decoration: none;
  border: none;
  cursor: pointer;
  transition: all 0.2s ease;
}

/* 主按鈕：點我抽籤 */
.btn-primary {
  background-color: #1c1c1e;
  color: #ffffff;
}

.btn-primary:hover {
  background-color: #3a3a3c;
  transform: translateY(-2px);
}

.btn-primary:active {
  transform: translateY(0);
}

/* 次要按鈕：馬上出發 */
.btn-secondary {
  background-color: #f2f2f7;
  color: #1c1c1e;
  border: 1px solid #e5e5ea;
}

.btn-secondary:hover {
  background-color: #e5e5ea;
}

/* 按鈕停用狀態 */
.btn-secondary.disabled {
  opacity: 0.4;
  pointer-events: none;
  cursor: not-allowed;
}
// 包裹在 DOMContentLoaded 事件中，確保網頁元件都載入完畢才執行邏輯，防止 null 錯誤
document.addEventListener('DOMContentLoaded', () => {

  // 1. 食物清單資料庫 (包含名稱、對應照片、Google 地圖搜尋關鍵字)
  const foodList = [
    {
      name: "楠梓烤肉",
      image: "https://i.postimg.cc/bvpKryJD/IMG-1371.jpg",
      query: "楠梓烤肉"
    },
    {
      name: "冰塔",
      image: "https://i.postimg.cc/nVNVzmtM/IMG-7423.jpg",
      query: "冰塔"
    },
    {
      name: "麥當勞",
      image: "https://i.postimg.cc/C1NM5rSg/IMG-1370.jpg",
      query: "麥當勞"
    },
    {
      name: "卡布義大利麵",
      image: "https://i.postimg.cc/W3bLWNLC/IMG-1363.jpg",
      query: "卡布義大利麵"
    },
    {
      name: "仁武丹丹",
      image: "https://i.postimg.cc/8PqGpgWx/IMG-1364.jpg",
      query: "仁武丹丹漢堡"
    }
  ];

  // 2. 取得 DOM 元素
  const foodTitle = document.getElementById('food-title');
  const foodImage = document.getElementById('food-image');
  const drawBtn = document.getElementById('draw-btn');
  const mapLink = document.getElementById('map-link');

  let isRolling = false; // 防止重複點擊的狀態鎖

  // 3. 點擊抽籤按鈕事件
  drawBtn.addEventListener('click', () => {
    if (isRolling) return;
    isRolling = true;

    // 移除舊的動畫類別，方便重新觸發
    foodTitle.classList.remove('bounce-pop');

    let counter = 0;
    const totalFlips = 15; // 滾動切換次數
    const speed = 80;      // 每次切換間隔 (毫秒)

    // 隨機快速切換名稱效果
    const timer = setInterval(() => {
      const randomIndex = Math.floor(Math.random() * foodList.length);
      foodTitle.innerText = foodList[randomIndex].name;
      counter++;

      // 滾動結束，決定最終結果
      if (counter >= totalFlips) {
        clearInterval(timer);

        // 挑選最終結果
        const finalIndex = Math.floor(Math.random() * foodList.length);
        const selectedFood = foodList[finalIndex];

        // 更新標題與動畫
        foodTitle.innerText = selectedFood.name;
        foodTitle.classList.add('bounce-pop');

        // 更新圖片
        foodImage.style.opacity = '0.5';
        setTimeout(() => {
          foodImage.src = selectedFood.image;
          foodImage.style.opacity = '1';
        }, 150);

        // 更新 Google Maps 導航連結並解除按鈕停用狀態
        const mapUrl = `https://www.google.com/maps/search/?api=1&query=${encodeURIComponent(selectedFood.query)}`;
        mapLink.href = mapUrl;
        mapLink.classList.remove('disabled');

        isRolling = false;
      }
    }, speed);
  });

});
