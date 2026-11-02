<!DOCTYPE html>
<html lang="zh-TW">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>今天吃什麼？隨機抽籤機</title>

    <!-- CSS 樣式區塊 -->
    <style>
        /* INS 風格色調與變數設定 */
        :root {
            --bg-color: #f7f7f8;
            --card-bg: #ffffff;
            --text-primary: #1a1a1a;
            --text-secondary: #757575;
            --border-color: #e5e5e7;
            --accent-black: #222222;
            --accent-gray: #f0f0f2;
            --shadow-sm: 0 4px 20px rgba(0, 0, 0, 0.04);
            --shadow-md: 0 12px 32px rgba(0, 0, 0, 0.08);
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, "PingFang TC", "Microsoft JhengHei", sans-serif;
            -webkit-font-smoothing: antialiased;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-primary);
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            padding: 24px;
        }

        /* 卡片主體 */
        .card {
            background-color: var(--card-bg);
            width: 100%;
            max-width: 420px;
            padding: 40px 32px;
            border-radius: 28px;
            box-shadow: var(--shadow-md);
            border: 1px solid var(--border-color);
            text-align: center;
            transition: all 0.3s ease;
        }

        /* 大標題 */
        .title {
            font-size: 1.75rem;
            font-weight: 600;
            letter-spacing: -0.02em;
            color: var(--text-primary);
            margin-bottom: 28px;
            min-height: 2.4em;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        /* 照片區域 */
        .image-container {
            width: 100%;
            height: 240px;
            margin-bottom: 28px;
            border-radius: 20px;
            overflow: hidden;
            background-color: var(--accent-gray);
            border: 1px solid var(--border-color);
        }

        .image-container img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            display: block;
        }

        /* 按鈕組 */
        .button-group {
            display: flex;
            flex-direction: column;
            gap: 12px;
        }

        .btn {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            padding: 16px 24px;
            font-size: 1rem;
            font-weight: 500;
            text-decoration: none;
            border-radius: 16px;
            border: none;
            cursor: pointer;
            transition: all 0.2s cubic-bezier(0.16, 1, 0.3, 1);
        }

        /* 主按鈕：點我抽籤 */
        .btn-primary {
            background-color: var(--accent-black);
            color: #ffffff;
            box-shadow: var(--shadow-sm);
        }

        .btn-primary:hover {
            background-color: #333333;
            transform: translateY(-1px);
        }

        .btn-primary:active {
            transform: translateY(1px);
        }

        /* 次按鈕：馬上出發 */
        .btn-secondary {
            background-color: var(--accent-gray);
            color: var(--text-primary);
            border: 1px solid var(--border-color);
        }

        .btn-secondary:hover {
            background-color: #e4e4e7;
            transform: translateY(-1px);
        }

        .btn-secondary:active {
            transform: translateY(1px);
        }

        /* 隱藏樣式 */
        .hidden {
            display: none !important;
        }

        /* 生動彈跳動畫 */
        .bounce-animation {
            animation: bounce 0.6s cubic-bezier(0.34, 1.56, 0.64, 1);
        }

        @keyframes bounce {
            0% {
                transform: scale(0.85);
                opacity: 0;
            }
            60% {
                transform: scale(1.05);
                opacity: 1;
            }
            100% {
                transform: scale(1);
            }
        }
    </style>
</head>
<body>

    <main class="card">
        <!-- 大標題 -->
        <h1 id="title" class="title">今天吃什麼？</h1>

        <!-- 美食照片區 -->
        <div id="image-container" class="image-container hidden">
            <img id="food-image" src="" alt="美食照片">
        </div>

        <!-- 按鈕區 -->
        <div class="button-group">
            <button id="draw-btn" class="btn btn-primary">點我抽籤</button>
            <a id="map-btn" class="btn btn-secondary hidden" href="#" target="_blank" rel="noopener">馬上出發 🗺️</a>
        </div>
    </main>

    <!-- JavaScript 邏輯區塊 -->
    <script>
        document.addEventListener('DOMContentLoaded', () => {
            const restaurants = [
                {
                    name: "楠梓烤肉",
                    image: "https://images.unsplash.com/photo-1555939594-58d7cb561ad1?auto=format&fit=crop&w=600&q=80",
                    mapUrl: "https://www.google.com/maps/search/?api=1&query=楠梓烤肉"
                },
                {
                    name: "冰塔",
                    image: "https://images.unsplash.com/photo-1563805042-7684c019e1cb?auto=format&fit=crop&w=600&q=80",
                    mapUrl: "https://www.google.com/maps/search/?api=1&query=冰塔"
                },
                {
                    name: "麥當勞",
                    image: "https://images.unsplash.com/photo-1561758033-d89a9ad46330?auto=format&fit=crop&w=600&q=80",
                    mapUrl: "https://www.google.com/maps/search/?api=1&query=麥當勞"
                },
                {
                    name: "卡布義大利麵",
                    image: "https://images.unsplash.com/photo-1551183053-bf91a1d81141?auto=format&fit=crop&w=600&q=80",
                    mapUrl: "https://www.google.com/maps/search/?api=1&query=卡布義大利麵"
                },
                {
                    name: "仁武丹丹漢堡",
                    image: "https://images.unsplash.com/photo-1625813506062-0aeb1d7a094b?auto=format&fit=crop&w=600&q=80",
                    mapUrl: "https://www.google.com/maps/search/?api=1&query=仁武丹丹漢堡"
                }
            ];

            const titleEl = document.getElementById('title');
            const drawBtn = document.getElementById('draw-btn');
            const mapBtn = document.getElementById('map-btn');
            const imageContainer = document.getElementById('image-container');
            const foodImage = document.getElementById('food-image');

            drawBtn.addEventListener('click', () => {
                const randomIndex = Math.floor(Math.random() * restaurants.length);
                const selected = restaurants[randomIndex];

                // 重置動畫效果
                titleEl.classList.remove('bounce-animation');
                imageContainer.classList.remove('bounce-animation');
                
                void titleEl.offsetWidth; // 觸發瀏覽器重繪

                // 更新內容與連結
                titleEl.innerText = `今天就吃：${selected.name}！`;
                foodImage.src = selected.image;
                foodImage.alt = selected.name;
                mapBtn.href = selected.mapUrl;

                // 顯示照片與按鈕
                imageContainer.classList.remove('hidden');
                mapBtn.classList.remove('hidden');

                // 套用彈跳動畫
                titleEl.classList.add('bounce-animation');
                imageContainer.classList.add('bounce-animation');
            });
        });
    </script>
</body>
</html>
