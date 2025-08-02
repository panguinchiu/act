# act
敏捷大賞年度變革引導者
<!DOCTYPE html>
<html lang="zh-TW">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>本一科技：年度變革引導者互動報告 - 邱瓊玉</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+TC:wght@400;500;700&display=swap" rel="stylesheet">
    <!-- Chosen Palette: Calm Harmony -->
    <!-- Application Structure Plan: The SPA is designed as a narrative journey, guiding the user through the story of change. It starts with a Hero section introducing the protagonist, Chiu Chiung-yu. It then moves to 'The Challenge' to establish the context and 'why' of the transformation. The core section, 'The Catalyst for Change,' uses an interactive tabbed interface to break down 'how' she led the change, making her leadership principles digestible. 'The Results' section uses dynamic counters and a timeline to showcase tangible outcomes in an engaging way. Finally, 'The Leader's Philosophy' section provides a reflective conclusion. This thematic, story-driven structure is more engaging and memorable than a simple document replica, allowing users to explore the content at their own pace while following a clear narrative arc. -->
    <!-- Visualization & Content Choices: 
        - Report Info: Founding team's cross-domain nature. -> Goal: Inform. -> Viz/Presentation: Donut Chart. -> Interaction: Hover for details. -> Justification: Visually represents the core strength of team diversity from the start. -> Library: Chart.js.
        - Report Info: Leadership principles (Mission-driven, Empowerment, Feedback). -> Goal: Organize & Explain. -> Viz/Presentation: Tabbed Interface. -> Interaction: Click to switch content. -> Justification: Breaks down complex strategies into focused, manageable chunks, preventing information overload. -> Library/Method: Vanilla JS + Tailwind.
        - Report Info: Key business/project results (EPS, MOUs, timeline). -> Goal: Showcase Change & Impact. -> Viz/Presentation: Animated Counters & HTML/CSS Timeline. -> Interaction: Counters animate on scroll; timeline is a static visual guide. -> Justification: Dynamic counters add a 'wow' factor to quantitative data. A timeline provides clear, chronological context for achievements. -> Library/Method: Vanilla JS + Tailwind.
        - Report Info: Agile Manifesto. -> Goal: Emphasize. -> Viz/Presentation: Stylized Blockquote & Card Grid. -> Interaction: None. -> Justification: Creates a visually distinct and impactful section for the leader's core philosophy. -> Library/Method: Tailwind CSS.
    -->
    <!-- CONFIRMATION: NO SVG graphics used. NO Mermaid JS used. -->
    <style>
        body {
            font-family: 'Noto Sans TC', sans-serif;
            background-color: #f8f7f4;
            color: #3d405b;
        }
        .bg-primary { background-color: #f8f7f4; }
        .bg-secondary { background-color: #ffffff; }
        .text-primary { color: #3d405b; }
        .text-secondary { color: #81b29a; }
        .accent-color { background-color: #e07a5f; }
        .nav-link {
            transition: color 0.3s ease, border-bottom-color 0.3s ease;
            border-bottom: 2px solid transparent;
        }
        .nav-link.active, .nav-link:hover {
            color: #e07a5f;
            border-bottom-color: #e07a5f;
        }
        .tab-button {
            transition: all 0.3s ease;
        }
        .tab-button.active {
            background-color: #81b29a;
            color: white;
        }
        .fade-in {
            animation: fadeIn 0.8s ease-in-out;
        }
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        .chart-container {
            position: relative;
            width: 100%;
            max-width: 400px;
            margin-left: auto;
            margin-right: auto;
            height: 300px;
            max-height: 350px;
        }
        @media (min-width: 768px) {
            .chart-container {
                height: 350px;
            }
        }
    </style>
</head>
<body class="bg-primary text-primary">

    <header class="bg-secondary/80 backdrop-blur-sm sticky top-0 z-50 shadow-sm">
        <nav class="container mx-auto px-6 py-3 flex justify-between items-center">
            <h1 class="text-xl md:text-2xl font-bold text-primary">本一科技｜年度變革引導者</h1>
            <div class="hidden md:flex space-x-8">
                <a href="#intro" class="nav-link pb-1">自我介紹</a>
                <a href="#story" class="nav-link pb-1">變革故事</a>
                <a href="#results" class="nav-link pb-1">變革成果</a>
                <a href="#philosophy" class="nav-link pb-1">敏捷宣言</a>
            </div>
        </nav>
    </header>

    <main>
        <section id="intro" class="py-16 md:py-24 fade-in">
            <div class="container mx-auto px-6">
                <div class="grid md:grid-cols-5 gap-8 md:gap-12 items-center">
                    <div class="md:col-span-3">
                        <h2 class="text-3xl md:text-5xl font-bold mb-4">邱瓊玉 (Chiu Chiung-yu)</h2>
                        <p class="text-xl md:text-2xl text-secondary font-semibold mb-6">本一科技 共同創辦人暨執行長</p>
                        <p class="text-base md:text-lg leading-relaxed mb-6">
                            我是一位跨域創業者，從打造具社會使命的 B 型企業「印花樂」，到創立智慧醫療先驅「本一科技」，我始終相信企業的核心價值在於「共好」。我的角色是團隊的黏著劑與催化劑，將醫療、設計、行銷與技術等多元專業凝聚成一股溫柔而堅定的改變力量，致力於解決臺灣醫療現場最真實的痛點。
                        </p>
                        <p class="text-base md:text-lg leading-relaxed">
                            對我而言，「敏捷」並非一套生硬的框架，而是一種應對未知與變化的核心思維。在創立本一科技的過程中，我最重要的職責就是**引導變革**，塑造一個「不怕犯錯，越早越好」的文化，並始終聚焦於「為醫護人員爭取時間」的核心價值。
                        </p>
                    </div>
                    <div class="md:col-span-2">
                        <div class="chart-container">
                            <canvas id="teamChart"></canvas>
                        </div>
                        <p class="text-center text-sm text-gray-500 mt-2">本一科技的跨領域創辦團隊</p>
                    </div>
                </div>
            </div>
        </section>

        <section id="story" class="py-16 md:py-24 bg-secondary fade-in">
            <div class="container mx-auto px-6 text-center">
                <h2 class="text-3xl md:text-4xl font-bold mb-4">變革故事：一場由「人」驅動的敏捷轉型</h2>
                <p class="max-w-3xl mx-auto text-lg mb-12">
                    這場變革的起點，是對臺灣醫療體系困境的深刻同理。我們看見的痛點不是缺乏技術，而是缺乏一個能快速回應臨床需求、以人為本的解決方案。因此，我的角色不是下達命令，而是**創造一個讓變革得以發生的「場域」**。
                </p>

                <div class="max-w-4xl mx-auto">
                    <div class="flex justify-center border-b border-gray-200 mb-8">
                        <button class="tab-button active text-sm md:text-base font-semibold py-3 px-4 md:px-8" data-tab="mission">使命驅動</button>
                        <button class="tab-button text-sm md:text-base font-semibold py-3 px-4 md:px-8" data-tab="empowerment">賦能當責</button>
                        <button class="tab-button text-sm md:text-base font-semibold py-3 px-4 md:px-8" data-tab="feedback">回饋內化</button>
                    </div>

                    <div id="mission" class="tab-content text-left p-4 md:p-6">
                        <h3 class="text-2xl font-bold text-secondary mb-3">建立「使命驅動」的團隊</h3>
                        <p class="leading-relaxed">我們的起點不是一份規格書，而是一個共同的願景：「要照顧病人，先照顧醫護同仁」。我以此為北極星，引導所有決策都與此對齊。當團隊方向有所偏離時，我會召開「校準會議」，讓大家重新聚焦於為使用者創造真實價值的初衷。</p>
                    </div>
                    <div id="empowerment" class="tab-content text-left p-4 md:p-6 hidden">
                        <h3 class="text-2xl font-bold text-secondary mb-3">賦能而非管理</h3>
                        <p class="leading-relaxed mb-4">我推動「模組負責制」，讓每位成員成為自己領域的「當責者」，擁有決策權與資源。這賦予團隊極高的自主性與行動力。</p>
                        <div class="bg-primary p-4 rounded-lg border-l-4 border-secondary">
                            <p class="font-semibold">案例分享：</p>
                            <p class="text-sm md:text-base">當奇美醫院護理師反應語音辨識問題時，我並未介入指揮，而是確保負責的工程師能直接與使用者溝通，並在 24 小時內完成優化、一週內正式佈署。</p>
                        </div>
                    </div>
                    <div id="feedback" class="tab-content text-left p-4 md:p-6 hidden">
                        <h3 class="text-2xl font-bold text-secondary mb-3">將「回饋」內化為 DNA</h3>
                        <p class="leading-relaxed">我最大的挑戰是打破不同專業領域間的隔閡。透過引導使用者訪談、共創工作坊，讓工程師能理解護理師的焦慮，讓醫師能看懂設計師的流程圖。我們將每一次使用者回饋都視為最寶貴的禮物，並透過 AI 知識庫將學習經驗沉澱，讓每一次的失敗都成為下一次成功的基石。</p>
                    </div>
                </div>
            </div>
        </section>

        <section id="results" class="py-16 md:py-24 bg-primary fade-in">
            <div class="container mx-auto px-6">
                <h2 class="text-3xl md:text-4xl font-bold text-center mb-12">變革帶來的成果</h2>
                <div class="grid md:grid-cols-3 gap-8 mb-16 text-center">
                    <div>
                        <p class="text-5xl md:text-6xl font-bold text-secondary" data-counter="3">0</p>
                        <p class="mt-2 font-semibold">預期首年 EPS (元)</p>
                    </div>
                    <div>
                        <p class="text-5xl md:text-6xl font-bold text-secondary" data-counter="4">0</p>
                        <p class="mt-2 font-semibold">簽訂合作意向書 (家)</p>
                    </div>
                    <div>
                        <p class="text-5xl md:text-6xl font-bold text-secondary" data-counter="6">0</p>
                        <p class="mt-2 font-semibold">產品開發時程 (月)</p>
                    </div>
                </div>

                <div class="grid lg:grid-cols-3 gap-8">
                    <div class="bg-secondary p-6 rounded-lg shadow-md">
                        <h3 class="text-xl font-bold mb-3">價值成果</h3>
                        <p>成功開發「臺醫照護 TaiOne Care GPT」，證明我們的敏捷模式能創造出市場真正需要的價值，並預計在創業首年即實現盈利。</p>
                    </div>
                    <div class="bg-secondary p-6 rounded-lg shadow-md">
                        <h3 class="text-xl font-bold mb-3">團隊成果</h3>
                        <p>從四位跨領域同學，轉型為一個高效、互信、充滿活力的敏捷團隊。成員不僅在專業上深化，更能跨域學習、互相補位。</p>
                    </div>
                    <div class="bg-secondary p-6 rounded-lg shadow-md">
                        <h3 class="text-xl font-bold mb-3">文化成果</h3>
                        <p>在組織內部成功植入「持續改善」的文化。團隊不再害怕變化，而是擁抱變化，並將其視為進步的契機。這份內在的敏捷力，是我們最珍貴的資產。</p>
                    </div>
                </div>
            </div>
        </section>

        <section id="philosophy" class="py-16 md:py-24 bg-secondary fade-in">
            <div class="container mx-auto px-6">
                <div class="text-center max-w-3xl mx-auto">
                    <h2 class="text-3xl md:text-4xl font-bold mb-8">我的敏捷宣言</h2>
                    <blockquote class="border-l-4 border-secondary pl-6 py-4 text-left mb-12">
                        <p class="text-2xl md:text-3xl italic font-semibold">"敏捷，是關於『人』的化學反應。"</p>
                    </blockquote>
                    <p class="text-lg leading-relaxed mb-12">
                        我始終相信，最偉大的創新源自於不同思維的碰撞。作為變革的引導者，我的工作不是去消除差異，而是去**催化這些差異，讓它們產生正向的化學反應**。敏捷對我來說，是一種「僕人式領導」的實踐。
                    </p>
                </div>
                <div class="grid md:grid-cols-3 gap-8 max-w-5xl mx-auto text-center">
                    <div class="p-6">
                        <h3 class="text-xl font-bold mb-3">創造信任</h3>
                        <p>建立一個讓所有人都能安心說出「我不知道」或「我反對」的環境。</p>
                    </div>
                    <div class="p-6">
                        <h3 class="text-xl font-bold mb-3">聚焦願景</h3>
                        <p>在混亂與不確定中，持續點亮那顆指引方向的「北極星」。</p>
                    </div>
                    <div class="p-6">
                        <h3 class="text-xl font-bold mb-3">移除障礙</h3>
                        <p>賦予團隊最大的自主權，讓他們能心無旁鶩地衝刺。</p>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <footer class="bg-primary py-8">
        <div class="container mx-auto px-6 text-center text-gray-500">
            <p class="font-bold text-lg mb-2 text-primary">朝向北極星願景前行</p>
            <p class="text-sm">我的使命，就是持續守護這份以人為本的敏捷精神，讓它不僅是本一科技的成功方程式，更能成為推動臺灣醫療產業進步的一股溫柔而堅定的力量。</p>
            <p class="text-xs mt-4">&copy; 2025 TaiOne AiTech. All Rights Reserved.</p>
        </div>
    </footer>

    <script>
        document.addEventListener('DOMContentLoaded', () => {

            const teamChartCtx = document.getElementById('teamChart').getContext('2d');
            new Chart(teamChartCtx, {
                type: 'doughnut',
                data: {
                    labels: ['醫療臨床', '經營管理', '使用者體驗設計', '品牌策略'],
                    datasets: [{
                        label: '創辦團隊背景',
                        data: [25, 25, 25, 25],
                        backgroundColor: [
                            '#81b29a',
                            '#e07a5f',
                            '#f2cc8f',
                            '#3d405b'
                        ],
                        borderColor: '#ffffff',
                        borderWidth: 4
                    }]
                },
                options: {
                    responsive: true,
                    maintainAspectRatio: false,
                    plugins: {
                        legend: {
                            position: 'bottom',
                            labels: {
                                font: {
                                    family: "'Noto Sans TC', sans-serif",
                                    size: 12
                                }
                            }
                        },
                        tooltip: {
                            callbacks: {
                                label: function(context) {
                                    return context.label;
                                }
                            }
                        }
                    },
                    cutout: '60%'
                }
            });

            const tabs = document.querySelectorAll('.tab-button');
            const tabContents = document.querySelectorAll('.tab-content');

            tabs.forEach(tab => {
                tab.addEventListener('click', () => {
                    tabs.forEach(item => item.classList.remove('active'));
                    tab.classList.add('active');

                    const target = tab.getAttribute('data-tab');
                    tabContents.forEach(content => {
                        content.classList.add('hidden');
                        if (content.id === target) {
                            content.classList.remove('hidden');
                        }
                    });
                });
            });

            function animateCounters() {
                const counters = document.querySelectorAll('[data-counter]');
                const speed = 200;

                counters.forEach(counter => {
                    const updateCount = () => {
                        const target = +counter.getAttribute('data-counter');
                        const count = +counter.innerText;
                        const inc = target / speed;

                        if (count < target) {
                            counter.innerText = Math.ceil(count + inc);
                            setTimeout(updateCount, 10);
                        } else {
                            counter.innerText = target;
                        }
                    };
                    updateCount();
                });
            }

            const observer = new IntersectionObserver((entries, observer) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        animateCounters();
                        observer.unobserve(entry.target);
                    }
                });
            }, { threshold: 0.5 });

            const resultsSection = document.getElementById('results');
            if(resultsSection) {
                observer.observe(resultsSection);
            }

            const navLinks = document.querySelectorAll('.nav-link');
            const sections = document.querySelectorAll('main section');

            window.addEventListener('scroll', () => {
                let current = '';
                sections.forEach(section => {
                    const sectionTop = section.offsetTop;
                    if (pageYOffset >= sectionTop - 100) {
                        current = section.getAttribute('id');
                    }
                });

                navLinks.forEach(link => {
                    link.classList.remove('active');
                    if (link.getAttribute('href').includes(current)) {
                        link.classList.add('active');
                    }
                });
            });
            
            navLinks.forEach(anchor => {
                anchor.addEventListener('click', function (e) {
                    e.preventDefault();
                    document.querySelector(this.getAttribute('href')).scrollIntoView({
                        behavior: 'smooth'
                    });
                });
            });
        });
    </script>

</body>
</html>
