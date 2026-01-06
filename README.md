[food-showcase.html](https://github.com/user-attachments/files/24455966/food-showcase.html)
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>万家厨房 - 精选美食</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
            line-height: 1.6;
            color: #333;
            background: #f8f9fa;
        }

        /* 导航栏 */
        header {
            background: #fff;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
        }

        nav {
            max-width: 1200px;
            margin: 0 auto;
            padding: 1rem 2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: bold;
            color: #e74c3c;
        }

        .nav-links {
            display: flex;
            gap: 2rem;
            list-style: none;
        }

        .nav-links a {
            text-decoration: none;
            color: #333;
            font-weight: 500;
            transition: color 0.3s;
        }

        .nav-links a:hover {
            color: #e74c3c;
        }

        /* 主横幅 */
        .hero {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 8rem 2rem 4rem;
            text-align: center;
            margin-top: 60px;
        }

        .hero h1 {
            font-size: 3rem;
            margin-bottom: 1rem;
        }

        .hero p {
            font-size: 1.2rem;
            opacity: 0.9;
        }

        /* 产品容器 */
        .container {
            max-width: 1200px;
            margin: 3rem auto;
            padding: 0 2rem;
        }

        .section-title {
            text-align: center;
            font-size: 2rem;
            margin-bottom: 2rem;
            color: #2c3e50;
        }

        /* 产品网格 */
        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2rem;
            margin-bottom: 3rem;
        }

        .product-card {
            background: white;
            border-radius: 12px;
            overflow: hidden;
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
            transition: transform 0.3s, box-shadow 0.3s;
            cursor: pointer;
        }

        .product-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 25px rgba(0,0,0,0.15);
        }

        .product-image {
            width: 100%;
            height: 200px;
            object-fit: cover;
            background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
        }

        .product-info {
            padding: 1.5rem;
        }

        .product-name {
            font-size: 1.3rem;
            font-weight: bold;
            margin-bottom: 0.5rem;
            color: #2c3e50;
        }

        .product-description {
            color: #7f8c8d;
            font-size: 0.95rem;
            margin-bottom: 1rem;
        }

        .product-details {
            color: #555;
            font-size: 0.9rem;
            line-height: 1.8;
            padding: 1rem;
            background: #f8f9fa;
            border-radius: 8px;
            margin-top: 1rem;
        }

        .product-details h4 {
            color: #2c3e50;
            font-size: 1rem;
            margin-bottom: 0.5rem;
        }

        .product-details ul {
            list-style: none;
            padding-left: 0;
        }

        .product-details li {
            padding: 0.3rem 0;
            padding-left: 1.2rem;
            position: relative;
        }

        .product-details li:before {
            content: "•";
            color: #e74c3c;
            position: absolute;
            left: 0;
            font-weight: bold;
        }

        .product-badge {
            display: inline-block;
            background: #27ae60;
            color: white;
            padding: 0.25rem 0.75rem;
            border-radius: 20px;
            font-size: 0.85rem;
            margin-bottom: 0.5rem;
        }

        .product-badge.new {
            background: #3498db;
        }

        .product-badge.hot {
            background: #e74c3c;
        }

        /* 特色区域 */
        .features {
            background: white;
            padding: 4rem 2rem;
            margin-top: 3rem;
        }

        .features-grid {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
        }

        .feature-item {
            text-align: center;
            padding: 2rem;
        }

        .feature-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
        }

        .feature-title {
            font-size: 1.2rem;
            font-weight: bold;
            margin-bottom: 0.5rem;
        }

        .feature-desc {
            color: #7f8c8d;
        }

        /* 页脚 */
        footer {
            background: #2c3e50;
            color: white;
            padding: 3rem 2rem;
            text-align: center;
            margin-top: 3rem;
        }

        .footer-links {
            margin-bottom: 1.5rem;
        }

        .footer-links a {
            color: white;
            text-decoration: none;
            margin: 0 1rem;
            opacity: 0.8;
            transition: opacity 0.3s;
        }

        .footer-links a:hover {
            opacity: 1;
        }

        /* 响应式设计 */
        @media (max-width: 768px) {
            .hero h1 {
                font-size: 2rem;
            }

            .nav-links {
                gap: 1rem;
            }

            .products-grid {
                grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            }
        }
    </style>
</head>
<body>
    <!-- 导航栏 -->
    <header>
        <nav>
            <div class="logo">万家厨房</div>
            <ul class="nav-links">
                <li><a href="#home">首页</a></li>
                <li><a href="#products">产品</a></li>
                <li><a href="#about">关于</a></li>
                <li><a href="#contact">联系</a></li>
            </ul>
        </nav>
    </header>

    <!-- 主横幅 -->
    <section class="hero" id="home">
        <h1>精选美食，味蕾盛宴</h1>
        <p>探索我们精心挑选的美味佳肴，每一道都是匠心之作</p>
    </section>

    <!-- 产品展示 -->
    <section class="container" id="products">
        <h2 class="section-title">当季推荐</h2>
        <div class="products-grid">
            <!-- 产品卡片 1 -->
            <div class="product-card">
                <div class="product-image" style="background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);"></div>
                <div class="product-info">
                    <span class="product-badge hot">招牌</span>
                    <h3 class="product-name">臭豆腐</h3>
                    <p class="product-description">长沙特色小吃，外酥里嫩，香辣可口</p>
                    <div class="product-details">
                        <h4>产品特色</h4>
                        <ul>
                            <li>选用优质黄豆，传统工艺发酵</li>
                            <li>外皮金黄酥脆，内里嫩滑鲜美</li>
                            <li>秘制酱料，香辣开胃</li>
                            <li>现炸现卖，保证最佳口感</li>
                        </ul>
                    </div>
                </div>
            </div>

            <!-- 产品卡片 2 -->
            <div class="product-card">
                <div class="product-image" style="background: linear-gradient(135deg, #4facfe 0%, #00f2fe 100%);"></div>
                <div class="product-info">
                    <span class="product-badge new">人气</span>
                    <h3 class="product-name">鸡蛋仔</h3>
                    <p class="product-description">香港街头经典小吃，外酥里软，蛋香浓郁</p>
                    <div class="product-details">
                        <h4>产品特色</h4>
                        <ul>
                            <li>香港原配方，地道风味</li>
                            <li>新鲜鸡蛋制作，蛋香四溢</li>
                            <li>外脆内软，Q弹有嚼劲</li>
                            <li>可搭配冰淇淋、水果等</li>
                        </ul>
                    </div>
                </div>
            </div>

            <!-- 产品卡片 3 -->
            <div class="product-card">
                <div class="product-image" style="background: linear-gradient(135deg, #43e97b 0%, #38f9d7 100%);"></div>
                <div class="product-info">
                    <span class="product-badge">精选</span>
                    <h3 class="product-name">章鱼小丸子</h3>
                    <p class="product-description">日式风味，章鱼鲜嫩，外皮酥脆，香味四溢</p>
                    <div class="product-details">
                        <h4>产品特色</h4>
                        <ul>
                            <li>进口鲜章鱼，肉质鲜甜</li>
                            <li>日式秘制配方，口感正宗</li>
                            <li>外皮金黄酥脆，内馅松软</li>
                            <li>木鱼花、海苔粉点缀</li>
                        </ul>
                    </div>
                </div>
            </div>

            <!-- 产品卡片 4 -->
            <div class="product-card">
                <div class="product-image" style="background: linear-gradient(135deg, #fa709a 0%, #fee140 100%);"></div>
                <div class="product-info">
                    <span class="product-badge hot">热卖</span>
                    <h3 class="product-name">华夫饼</h3>
                    <p class="product-description">比利时经典，格子花纹，松软香甜</p>
                    <div class="product-details">
                        <h4>产品特色</h4>
                        <ul>
                            <li>比利时传统配方</li>
                            <li>松软香甜，口感丰富</li>
                            <li>可搭配蜂蜜、水果、冰淇淋</li>
                            <li>现做现卖，热气腾腾</li>
                        </ul>
                    </div>
                </div>
            </div>

            <!-- 产品卡片 5 -->
            <div class="product-card">
                <div class="product-image" style="background: linear-gradient(135deg, #a18cd1 0%, #fbc2eb 100%);"></div>
                <div class="product-info">
                    <span class="product-badge new">推荐</span>
                    <h3 class="product-name">霸王肉串</h3>
                    <p class="product-description">超大肉串，肉质鲜嫩，烧烤风味十足</p>
                    <div class="product-details">
                        <h4>产品特色</h4>
                        <ul>
                            <li>精选优质肉类，肉质鲜嫩</li>
                            <li>秘制腌料，入味透彻</li>
                            <li>孜然香料调味，香味浓郁</li>
                            <li>现串现烤，保留肉汁</li>
                        </ul>
                    </div>
                </div>
            </div>

            <!-- 产品卡片 6 -->
            <div class="product-card">
                <div class="product-image" style="background: linear-gradient(135deg, #ffecd2 0%, #fcb69f 100%);"></div>
                <div class="product-info">
                    <span class="product-badge">健康</span>
                    <h3 class="product-name">鲜榨橙汁</h3>
                    <p class="product-description">100%鲜橙现榨，酸甜适中，补充维生素C</p>
                    <div class="product-details">
                        <h4>产品特色</h4>
                        <ul>
                            <li>精选新鲜脐橙，品质上乘</li>
                            <li>100%原汁，无添加无水</li>
                            <li>富含维生素C，健康养生</li>
                            <li>现点现榨，新鲜营养</li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- 特色优势 -->
    <section class="features" id="about">
        <h2 class="section-title">我们的优势</h2>
        <div class="features-grid">
            <div class="feature-item">
                <div class="feature-icon">🌿</div>
                <h3 class="feature-title">新鲜食材</h3>
                <p class="feature-desc">严选优质原料，每日新鲜配送</p>
            </div>
            <div class="feature-item">
                <div class="feature-icon">👨‍🍳</div>
                <h3 class="feature-title">匠心制作</h3>
                <p class="feature-desc">经验丰富的厨师团队精心烹饪</p>
            </div>
            <div class="feature-item">
                <div class="feature-icon">🚚</div>
                <h3 class="feature-title">快速配送</h3>
                <p class="feature-desc">全程冷链配送，保证新鲜度</p>
            </div>
            <div class="feature-item">
                <div class="feature-icon">💯</div>
                <h3 class="feature-title">品质保证</h3>
                <p class="feature-desc">严格质检，不满意全额退款</p>
            </div>
        </div>
    </section>

    <!-- 页脚 -->
    <footer id="contact">
        <div class="footer-links">
            <a href="#">关于我们</a>
            <a href="#">产品介绍</a>
            <a href="#">配送说明</a>
            <a href="#">联系客服</a>
        </div>
        <p>&copy; 2026 万家厨房 - 让美食传递幸福</p>
    </footer>

    <script>
        // 平滑滚动
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });
    </script>
</body>
</html>
