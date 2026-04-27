<!DOCTYPE html>
<html lang="zh-TW" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Akari | Vtuber Illustration Portfolio</title>
    <!-- 引入字體：Inter 用於乾淨的 UI 結構，Playfair Display 提升標題的設計師高級感 -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600&family=Playfair+Display:ital,wght@0,500;0,700;1,500&display=swap" rel="stylesheet">
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        // 定義全站標準色與字體規範
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        deepblue: '#0e3e62',
                        gold: '#cfad77',
                    },
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                        serif: ['Playfair Display', 'serif'],
                    }
                }
            }
        }
    </script>
    <style>
        /* 自定義滾動條以配合極簡風格 */
        ::-webkit-scrollbar { width: 8px; }
        ::-webkit-scrollbar-track { background: #f1f1f1; }
        ::-webkit-scrollbar-thumb { background: #cfad77; border-radius: 4px; }
        ::-webkit-scrollbar-thumb:hover { background: #b89865; }
    </style>
</head>
<body class="bg-white text-deepblue font-sans antialiased selection:bg-gold selection:text-white">

    <!-- 導覽列 (Header) -->
    <nav class="w-full flex justify-between items-center py-6 px-6 lg:px-12 max-w-[1440px] mx-auto bg-white">
        <!-- 替換為指定的 LOGO -->
        <div class="flex items-center">
            <img src="https://i.ibb.co/ymmBdSJJ/LOGO-V3-04.png" alt="Akari Logo" class="h-6 md:h-8 object-contain">
        </div>
        <!-- 桌面端導覽列 -->
        <div class="hidden md:flex gap-10 text-sm uppercase tracking-widest font-medium">
            <a href="#" class="hover:text-gold transition-colors duration-300">Home</a>
            <a href="#portfolio" class="hover:text-gold transition-colors duration-300">Portfolio</a>
            <a href="mailto:opulcytec.design02@gmail.com" class="hover:text-gold transition-colors duration-300">Contact</a>
        </div>
    </nav>

    <!-- 首屏主視覺 (Hero Section) - 混合響應式佈局 -->
    <section class="w-full max-w-[1440px] mx-auto relative flex flex-col md:block bg-white">
        <!-- 滿版圖片：等比例縮放，不強制裁切 -->
        <img src="https://i.ibb.co/F4bmp5kt/2.png" alt="Akari Hero Banner" class="w-full h-auto object-cover block">
        
        <!-- 按鈕區：響應式邏輯 -->
        <!-- 桌面端 (md以上): 絕對定位浮動於左下角 (bottom/left 控制位置) -->
        <!-- 行動端 (md以下): 自動排列於圖片下方，給予充足留白與點擊空間，避免遮蔽縮小後的圖片文字 -->
        <div class="md:absolute md:bottom-[8%] md:left-[5%] flex flex-col sm:flex-row gap-2 px-6 md:px-0 py-6 md:py-0 w-full md:w-auto z-10 bg-white md:bg-transparent">
            
            <a href="mailto:opulcytec.design02@gmail.com" class="bg-gold text-white px-4 py-2 rounded text-xs font-medium shadow-sm hover:bg-[#b89865] hover:-translate-y-0.5 transition-all duration-300 flex items-center justify-center gap-1.5 w-full sm:w-auto tracking-wide">
                Commission Open <span class="text-white/90 font-serif">✦</span>
            </a>
            
            <a href="#portfolio" class="bg-white/80 backdrop-blur-md border border-gold text-gold px-4 py-2 rounded text-xs font-medium hover:bg-gold hover:text-white transition-all duration-300 flex items-center justify-center gap-1.5 w-full sm:w-auto tracking-wide">
                View Portfolio <span class="tracking-tighter">⟶</span>
            </a>
            
        </div>
    </section>

    <!-- 作品展示區 (Portfolio Section) -->
    <section id="portfolio" class="bg-[#fafafa] w-full py-16 md:py-20 lg:py-32 border-t border-gray-100">
        <div class="max-w-[1440px] mx-auto px-6 lg:px-12">
            
            <div class="flex items-center gap-4 mb-10 md:mb-16">
                <span class="text-gold text-2xl font-serif">✦</span>
                <h2 class="text-3xl md:text-4xl font-serif text-deepblue">Portfolio</h2>
            </div>

            <!-- 5位一排的矩陣佈局，行動裝置自動轉為 2 排，平板 3 排 -->
            <div id="grid-container" class="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-5 gap-4 md:gap-6 lg:gap-8">
                <!-- Javascript 將自動渲染這 10 張卡片 -->
            </div>
            
        </div>
    </section>

    <!-- 頁尾 (Footer) -->
    <footer class="w-full max-w-[1440px] mx-auto px-6 lg:px-12 py-8 md:py-12 flex flex-col md:flex-row justify-between items-center text-xs md:text-sm text-deepblue/50 border-t border-gray-100">
        <div class="flex items-center gap-2 mb-4 md:mb-0">
            <span class="text-gold">✦</span> © 2026 Akari. All rights reserved.
        </div>
        <div>
            Focus on the soul of pixels.
        </div>
    </footer>

    <!-- 全螢幕懸停大圖彈窗 (Hover/Click Modal) -->
    <div id="preview-modal" class="fixed inset-0 flex items-center justify-center opacity-0 -z-10 pointer-events-none transition-all duration-300 ease-out">
        <div class="absolute inset-0 bg-white/90 backdrop-blur-sm"></div>
        <img id="preview-img" src="" alt="Full Body Detail" class="relative z-10 max-h-[90vh] max-w-[95vw] object-contain drop-shadow-2xl transform scale-95 transition-transform duration-300 ease-out">
        
        <div id="close-hint" class="absolute bottom-10 left-1/2 transform -translate-x-1/2 bg-deepblue text-white px-6 py-2 rounded-full text-sm font-medium opacity-0 transition-opacity pointer-events-auto shadow-lg hidden">
            Tap anywhere to close
        </div>
    </div>

    <!-- 核心互動邏輯腳本 -->
    <script>
        // 資料集
        const works = [
            { thumb: "https://i.meee.com.tw/Ul7CuAu.png", full: "https://i.meee.com.tw/qFnAEoY.png" },
            { thumb: "https://i.meee.com.tw/DNTxdWu.png", full: "https://i.meee.com.tw/AzANbQ3.png" },
            { thumb: "https://i.meee.com.tw/PUT9vpx.png", full: "https://i.meee.com.tw/jxoPtEq.png" },
            { thumb: "https://i.meee.com.tw/KrWGhaw.png", full: "https://i.meee.com.tw/beYobFH.png" },
            { thumb: "https://i.meee.com.tw/GXtBEBo.png", full: "https://i.meee.com.tw/JTVuQnB.png" },
            { thumb: "https://i.meee.com.tw/R6upXkA.png", full: "https://i.meee.com.tw/xHuWKaZ.png" },
            { thumb: "https://i.meee.com.tw/XSFkBi0.png", full: "https://i.meee.com.tw/wyTBdYU.png" },
            { thumb: "https://i.meee.com.tw/J3oNejP.png", full: "https://i.meee.com.tw/HwEQczL.png" },
            { thumb: "https://i.meee.com.tw/YPY2LHg.png", full: "https://i.meee.com.tw/F55aecN.png" },
            { thumb: "https://i.meee.com.tw/fA7iwTt.png", full: "https://i.meee.com.tw/poSN7NF.png" },
        ];

        const gridContainer = document.getElementById('grid-container');
        const modal = document.getElementById('preview-modal');
        const previewImg = document.getElementById('preview-img');
        const closeHint = document.getElementById('close-hint');
        
        const isTouchDevice = ('ontouchstart' in window) || (navigator.maxTouchPoints > 0);

        const showPreview = (fullImgUrl) => {
            previewImg.src = fullImgUrl;
            modal.classList.remove('opacity-0', '-z-10');
            modal.classList.add('opacity-100', 'z-50');
            previewImg.classList.remove('scale-95');
            previewImg.classList.add('scale-100');
            
            if(isTouchDevice) {
                modal.classList.remove('pointer-events-none');
                closeHint.classList.remove('hidden');
                setTimeout(() => closeHint.classList.add('opacity-100'), 100);
            }
        };

        const hidePreview = () => {
            modal.classList.remove('opacity-100', 'z-50', 'pointer-events-auto');
            modal.classList.add('opacity-0', '-z-10');
            previewImg.classList.remove('scale-100');
            previewImg.classList.add('scale-95');
            
            if(isTouchDevice) {
                modal.classList.add('pointer-events-none');
                closeHint.classList.remove('opacity-100');
                setTimeout(() => closeHint.classList.add('hidden'), 300);
            }
        };

        works.forEach((work, index) => {
            const card = document.createElement('div');
            card.className = "group relative cursor-pointer rounded-xl md:rounded-2xl overflow-hidden bg-white shadow-sm hover:shadow-2xl hover:shadow-gold/20 transition-all duration-300 transform hover:-translate-y-1 md:hover:-translate-y-2 border border-gray-100";
            
            card.innerHTML = `
                <div class="aspect-square w-full overflow-hidden bg-[#f8f9fa]">
                    <img src="${work.thumb}" alt="Vtuber Portfolio ${index + 1}" class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-700 ease-in-out" loading="lazy" />
                </div>
                <div class="absolute inset-1 md:inset-2 border border-gold opacity-0 group-hover:opacity-100 rounded-lg md:rounded-xl transition-opacity duration-300 pointer-events-none"></div>
            `;

            if (!isTouchDevice) {
                card.addEventListener('mouseenter', () => showPreview(work.full));
                card.addEventListener('mouseleave', hidePreview);
            } else {
                card.addEventListener('click', () => showPreview(work.full));
            }

            gridContainer.appendChild(card);
        });

        if (isTouchDevice) {
            modal.addEventListener('click', hidePreview);
        }
    </script>
</body>
</html>
