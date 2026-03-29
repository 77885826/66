# 66
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>李明 - 全栈开发者 | 个人主页</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary-color: #2563eb;
            --secondary-color: #7c3aed;
            --dark-bg: #0f172a;
            --light-bg: #f8fafc;
            --text-dark: #1e293b;
            --text-light: #f1f5f9;
            --card-bg: #ffffff;
            --shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1);
        }
        
        [data-theme="dark"] {
            --primary-color: #60a5fa;
            --dark-bg: #f8fafc;
            --light-bg: #0f172a;
            --text-dark: #f1f5f9;
            --text-light: #1e293b;
            --card-bg: #1e293b;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            transition: background-color 0.3s, color 0.3s;
        }
        
        body {
            font-family: 'Segoe UI', system-ui, sans-serif;
            line-height: 1.6;
            background-color: var(--light-bg);
            color: var(--text-dark);
        }
        
        .container {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        /* 导航栏 */
        header {
            position: fixed;
            top: 0;
            width: 100%;
            background-color: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            z-index: 1000;
            box-shadow: var(--shadow);
        }
        
        [data-theme="dark"] header {
            background-color: rgba(30, 41, 59, 0.95);
        }
        
        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1.2rem 0;
        }
        
        .logo {
            font-size: 1.8rem;
            font-weight: 700;
            background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }
        
        .nav-links {
            display: flex;
            gap: 2.5rem;
            list-style: none;
        }
        
        .nav-links a {
            text-decoration: none;
            color: var(--text-dark);
            font-weight: 500;
            position: relative;
            padding: 0.5rem 0;
        }
        
        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 2px;
            background: linear-gradient(90deg, var(--primary-color), var(--secondary-color));
            transition: width 0.3s;
        }
        
        .nav-links a:hover::after {
            width: 100%;
        }
        
        .theme-toggle {
            background: none;
            border: none;
            font-size: 1.2rem;
            cursor: pointer;
            color: var(--text-dark);
        }
        
        /* 英雄区域 */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            padding-top: 80px;
        }
        
        .hero-content {
            max-width: 600px;
        }
        
        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 1rem;
            background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }
        
        .hero h2 {
            font-size: 1.8rem;
            margin-bottom: 1.5rem;
            color: var(--text-dark);
            opacity: 0.9;
        }
        
        .hero p {
            font-size: 1.1rem;
            margin-bottom: 2.5rem;
            color: var(--text-dark);
            opacity: 0.8;
        }
        
        .cta-buttons {
            display: flex;
            gap: 1rem;
        }
        
        .btn {
            padding: 0.8rem 2rem;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s;
        }
        
        .btn-primary {
            background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
            color: white;
        }
        
        .btn-outline {
            border: 2px solid var(--primary-color);
            color: var(--primary-color);
        }
        
        .btn:hover {
            transform: translateY(-3px);
            box-shadow: var(--shadow);
        }
        
        /* 关于部分 */
        section {
            padding: 5rem 0;
        }
        
        .section-title {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 3rem;
            color: var(--text-dark);
        }
        
        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
            align-items: center;
        }
        
        .about-text h3 {
            font-size: 1.8rem;
            margin-bottom: 1.5rem;
            color: var(--text-dark);
        }
        
        .about-text p {
            margin-bottom: 1.5rem;
            color: var(--text-dark);
            opacity: 0.9;
        }
        
        /* 技能部分 */
        .skills-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }
        
        .skill-category {
            background: var(--card-bg);
            padding: 2rem;
            border-radius: 15px;
            box-shadow: var(--shadow);
        }
        
        .skill-item {
            margin-bottom: 1.5rem;
        }
        
        .skill-info {
            display: flex;
            justify-content: space-between;
            margin-bottom: 0.5rem;
        }
        
        .skill-bar {
            height: 8px;
            background: #e2e8f0;
            border-radius: 4px;
            overflow: hidden;
        }
        
        .skill-progress {
            height: 100%;
            background: linear-gradient(90deg, var(--primary-color), var(--secondary-color));
            border-radius: 4px;
        }
        
        /* 项目部分 */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
        }
        
        .project-card {
            background: var(--card-bg);
            border-radius: 15px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: transform 0.3s;
        }
        
        .project-card:hover {
            transform: translateY(-10px);
        }
        
        .project-img {
            height: 200px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 3rem;
        }
        
        .project-content {
            padding: 1.5rem;
        }
        
        .project-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            margin: 1rem 0;
        }
        
        .tag {
            background: var(--primary-color);
            color: white;
            padding: 0.3rem 0.8rem;
            border-radius: 20px;
            font-size: 0.9rem;
        }
        
        /* 联系表单 */
        .contact-form {
            max-width: 600px;
            margin: 0 auto;
        }
        
        .form-group {
            margin-bottom: 1.5rem;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            color: var(--text-dark);
            font-weight: 500;
        }
        
        .form-control {
            width: 100%;
            padding: 0.8rem 1rem;
            border: 2px solid #cbd5e1;
            border-radius: 8px;
            font-size: 1rem;
            background: var(--card-bg);
            color: var(--text-dark);
        }
        
        .form-control:focus {
            outline: none;
            border-color: var(--primary-color);
        }
        
        /* 页脚 */
        footer {
            background: var(--dark-bg);
            color: var(--text-light);
            padding: 3rem 0;
            text-align: center;
        }
        
        .social-links {
            display: flex;
            justify-content: center;
            gap: 1.5rem;
            margin: 2rem 0;
        }
        
        .social-links a {
            color: var(--text-light);
            font-size: 1.5rem;
            transition: color 0.3s;
        }
        
        .social-links a:hover {
            color: var(--primary-color);
        }
        
        .copyright {
            margin-top: 2rem;
            opacity: 0.8;
        }
        
        /* 响应式设计 */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }
            
            .hero h1 {
                font-size: 2.5rem;
            }
            
            .about-content {
                grid-template-columns: 1fr;
            }
            
            .cta-buttons {
                flex-direction: column;
            }
        }
    </style>
</head>
<body>
    <!-- 导航栏 -->
    <header>
        <div class="container">
            <nav>
                <div class="logo">LiMing.dev</div>
                <ul class="nav-links">
                    <li><a href="#home">首页</a></li>
                    <li><a href="#about">关于</a></li>
                    <li><a href="#skills">技能</a></li>
                    <li><a href="#projects">项目</a></li>
                    <li><a href="#contact">联系</a></li>
                </ul>
                <button class="theme-toggle" id="themeToggle">
                    <i class="fas fa-moon"></i>
                </button>
            </nav>
        </div>
    </header>

    <!-- 英雄区域 -->
    <section id="home" class="hero">
        <div class="container">
            <div class="hero-content">
                <h1>李明</h1>
                <h2>全栈开发者 & UI/UX设计师</h2>
                <p>专注于创造优雅、高效的Web解决方案。拥有5年全栈开发经验，热衷于将复杂问题转化为简洁的代码和直观的用户体验。</p>
                <div class="cta-buttons">
                    <a href="#projects" class="btn btn-primary">查看项目</a>
                    <a href="#contact" class="btn btn-outline">联系我</a>
                </div>
            </div>
        </div>
    </section>

    <!-- 关于我 -->
    <section id="about">
        <div class="container">
            <h2 class="section-title">关于我</h2>
            <div class="about-content">
                <div class="about-text">
                    <h3>热爱技术的创造者</h3>
                    <p>我是一名充满热情的全栈开发者，专注于现代Web技术栈。拥有计算机科学硕士学位，曾在多家科技公司担任核心技术角色。</p>
                    <p>我相信好的代码应该像散文一样优雅，好的产品应该为用户提供无缝的体验。我不断学习新技术，追求代码的最佳实践。</p>
                    <p>除了编程，我还热衷于开源贡献、技术写作和 mentoring。在业余时间，我喜欢摄影、徒步和阅读科幻小说。</p>
                </div>
                <div class="about-text">
                    <h3>教育背景 & 经历</h3>
                    <p><strong>计算机科学硕士</strong> - 清华大学 (2017-2020)</p>
                    <p><strong>高级全栈工程师</strong> - 字节跳动 (2021-至今)</p>
                    <p><strong>前端开发工程师</strong> - 腾讯科技 (2019-2021)</p>
                    <p><strong>开源贡献者</strong> - React、Vue.js 等社区</p>
                </div>
            </div>
        </div>
    </section>

    <!-- 技能 -->
    <section id="skills">
        <div class="container">
            <h2 class="section-title">技术栈</h2>
            <div class="skills-container">
                <div class="skill-category">
                    <h3>前端技术</h3>
                    <div class="skill-item">
                        <div class="skill-info">
                            <span>React / Vue.js</span>
                            <span>95%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 95%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-info">
                            <span>TypeScript</span>
                            <span>90%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 90%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-info">
                            <span>CSS/SCSS</span>
                            <span>92%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 92%"></div>
                        </div>
                    </div>
                </div>
                
                <div class="skill-category">
                    <h3>后端技术</h3>
                    <div class="skill-item">
                        <div class="skill-info">
                            <span>Node.js</span>
                            <span>88%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 88%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-info">
                            <span>Python/Django</span>
                            <span>85%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 85%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-info">
                            <span>数据库设计</span>
                            <span>87%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 87%"></div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- 项目展示 -->
    <section id="projects">
        <div class="container">
            <h2 class="section-title">精选项目</h2>
            <div class="projects-grid">
                <div class="project-card">
                    <div class="project-img">
                        <i class="fas fa-chart-line"></i>
                    </div>
                    <div class="project-content">
                        <h3>智能数据分析平台</h3>
                        <p>基于React和D3.js构建的数据可视化平台，支持实时数据处理和交互式图表展示。</p>
                        <div class="project-tags">
                            <span class="tag">React</span>
                            <span class="tag">D3.js</span>
                            <span class="tag">TypeScript</span>
                        </div>
                    </div>
                </div>
                
                <div class="project-card">
                    <div class="project-img">
                        <i class="fas fa-shopping-cart"></i>
                    </div>
                    <div class="project-content">
                        <h3>电商微服务系统</h3>
                        <p>基于微服务架构的电商平台，包含用户管理、订单处理、支付网关等独立服务模块。</p>
                        <div class="project-tags">
                            <span class="tag">Node.js</span>
                            <span class="tag">Docker</span>
                            <span class="tag">MongoDB</span>
                        </div>
                    </div>
                </div>
                
                <div class="project-card">
                    <div class="project-img">
                        <i class="fas fa-robot"></i>
                    </div>
                    <div class="project-content">
                        <h3>AI内容生成助手</h3>
                        <p>集成OpenAI API的智能写作助手，支持多种内容类型的自动生成和优化建议。</p>
                        <div class="project-tags">
                            <span class="tag">Python</span>
                            <span class="tag">FastAPI</span>
                            <span class="tag">OpenAI</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- 联系表单 -->
    <section id="contact">
        <div class="container">
            <h2 class="section-title">联系我</h2>
            <form class="contact-form" id="contactForm">
                <div class="form-group">
                    <label for="name">姓名</label>
                    <input type="text" id="name" class="form-control" required>
                </div>
                <div class="form-group">
                    <label for="email">邮箱</label>
                    <input type="email" id="email" class="form-control" required>
                </div>
                <div class="form-group">
                    <label for="message">消息</label>
                    <textarea id="message" class="form-control" rows="5" required></textarea>
                </div>
                <button type="submit" class="btn btn-primary" style="width: 100%;">发送消息</button>
            </form>
        </div>
    </section>

    <!-- 页脚 -->
    <footer>
        <div class="container">
            <div class="social-links">
                <a href="#"><i class="fab fa-github"></i></a>
                <a href="#"><i class="fab fa-linkedin"></i></a>
                <a href="#"><i class="fab fa-twitter"></i></a>
                <a href="#"><i class="fab fa-codepen"></i></a>
            </div>
            <p>© 2026 李明. 保留所有权利</p>
            <p class="copyright">丙午马年 · 代码如诗，创意如马</p>
        </div>
    </footer>

    <script>
        // 主题切换功能
        const themeToggle = document.getElementById('themeToggle');
        const themeIcon = themeToggle.querySelector('i');
        
        themeToggle.addEventListener('click', () => {
            const isDark = document.body.getAttribute('data-theme') === 'dark';
            if (isDark) {
                document.body.removeAttribute('data-theme');
                themeIcon.className = 'fas fa-moon';
                localStorage.setItem('theme', 'light');
            } else {
                document.body.setAttribute('data-theme', 'dark');
                themeIcon.className = 'fas fa-sun';
                localStorage.setItem('theme', 'dark');
            }
        });
        
        // 加载保存的主题
        const savedTheme = localStorage.getItem('theme');
        if (savedTheme === 'dark') {
            document.body.setAttribute('data-theme', 'dark');
            themeIcon.className = 'fas fa-sun';
        }
        
        // 表单验证
        const contactForm = document.getElementById('contactForm');
        contactForm.addEventListener('submit', (e) => {
            e.preventDefault();
            
            const name = document.getElementById('name').value.trim();
            const email = document.getElementById('email').value.trim();
            const message = document.getElementById('message').value.trim();
            
            if (!name || !email || !message) {
                alert('请填写所有必填字段');
                return;
            }
            
            if (!/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email)) {
                alert('请输入有效的邮箱地址');
                return;
            }
            
            // 这里实际应该发送到服务器
            alert('感谢您的留言！我会尽快回复。');
            contactForm.reset();
        });
        
        // 平滑滚动
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const targetId = this.getAttribute('href');
                if (targetId === '#') return;
                
                const targetElement = document.querySelector(targetId);
                if (targetElement) {
                    window.scrollTo({
                        top: targetElement.offsetTop - 80,
                        behavior: 'smooth'
                    });
                }
            });
        });
    </script>
</body>
</html>
