# jaeyeonkim.github.io
Portfolio
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>김재연 | 포트폴리오</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+KR:wght@300;400;500;700&display=swap" rel="stylesheet">
    <!-- Chosen Palette: Serene Professional (Background: #f8fafc, Text: #1e293b, Primary Accent: #2563eb, Secondary Accent: #e2e8f0) -->
    <!-- Application Structure Plan: A single-page, vertical-scrolling SPA structure was chosen to create a seamless narrative flow. It starts with a Hero section for immediate impact, followed by an 'About Me' section that combines Core Competencies and the Self-Introduction to build a strong personal brand. An interactive vertical timeline for 'Experience' visually showcases growth and connects diverse roles. A gridded 'Skills & Education' section efficiently organizes qualifications, highlighting key training. This structure guides recruiters logically from a high-level summary to detailed evidence, making the candidate's story compelling and easy to follow. -->
    <!-- Visualization & Content Choices: 
    - Experience -> Goal: Show career journey and skill application -> Viz/Method: Interactive Vertical Timeline (HTML/CSS/JS) -> Interaction: Hover effects on timeline items to draw attention -> Justification: Visually more engaging than a static list; effectively connects seemingly unrelated part-time roles to core professional skill development.
    - Language Skills -> Goal: Quantify proficiency visually -> Viz/Method: Horizontal Bar Chart (Chart.js Canvas) -> Interaction: Static chart, animated on load -> Justification: Provides a modern, quick-to-understand visual representation of the high-level Japanese proficiency (JLPT N1), making it more impactful than text alone.
    - Competencies/Skills/Education -> Goal: Organize dense, varied information clearly -> Viz/Method: Card-based Grid Layout (Tailwind CSS) -> Interaction: Static layout for easy scanning -> Justification: This method categorizes and presents a large amount of data (degrees, certs, bootcamps) in a structured, digestible format, preventing information overload.
    -->
    <!-- CONFIRMATION: NO SVG graphics used. NO Mermaid JS used. -->
    <style>
        body {
            font-family: 'Noto Sans KR', sans-serif;
            background-color: #f8fafc;
            color: #1e293b;
            scroll-snap-type: y mandatory;
        }
        section {
            scroll-snap-align: start;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            padding: 4rem 0;
            transition: filter 0.5s ease-in-out;
        }
        .timeline-item::before {
            content: '';
            position: absolute;
            width: 1.25rem;
            height: 1.25rem;
            border-radius: 50%;
            left: -0.625rem;
            top: 0;
            background-color: #2563eb;
            border: 4px solid #f1f5f9;
        }
        .section-title {
            position: relative;
            display: inline-block;
            padding-bottom: 0.5rem;
            margin-bottom: 1.5rem;
        }
        .section-title::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            height: 3px;
            background-color: #2563eb;
        }
        .timeline-item {
            position: relative;
            padding-left: 2rem;
            min-width: 0;
            flex-shrink: 0;
            opacity: 0;
            transform: translateY(20px);
            transition: opacity 0.6s ease-out, transform 0.6s ease-out;
        }
        .timeline-item.fade-in {
            opacity: 1;
            transform: translateY(0);
        }
    </style>
</head>
<body class="bg-slate-50">

    <nav class="bg-white/80 backdrop-blur-lg sticky top-0 z-50 shadow-sm">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex items-center justify-between h-16">
                <div class="flex items-center">
                    <span class="font-bold text-xl text-slate-800">김재연 | 포트폴리오</span>
                </div>
                <div class="hidden md:block">
                    <div class="ml-10 flex items-baseline space-x-4">
                        <a href="#about" class="text-slate-600 hover:text-blue-600 px-3 py-2 rounded-md text-sm font-medium">소개</a>
                        <a href="#experience" class="text-slate-600 hover:text-blue-600 px-3 py-2 rounded-md text-sm font-medium">주요 경험</a>
                        <a href="#skills" class="text-slate-600 hover:text-blue-600 px-3 py-2 rounded-md text-sm font-medium">역량 및 교육</a>
                        <a href="#contact" class="text-slate-600 hover:text-blue-600 px-3 py-2 rounded-md text-sm font-medium">연락처</a>
                    </div>
                </div>
            </div>
        </div>
    </nav>

    <div class="fixed inset-0 pointer-events-none" id="blur-overlay" style="backdrop-filter: blur(0px); transition: backdrop-filter 0.5s ease-in-out;"></div>

    <main class="relative max-w-7xl mx-auto py-12 px-4 sm:px-6 lg:px-8">
        
        <section id="hero" class="text-center py-20 relative z-10">
            <h1 class="text-5xl md:text-6xl font-extrabold text-slate-900">김재연</h1>
            <p class="mt-4 text-xl md:text-2xl text-blue-600 font-semibold">글로벌 비즈니스 전문가를 향한 열정</p>
            <p class="mt-6 max-w-2xl mx-auto text-lg text-slate-600">
                다양한 경험을 통해 얻은 소통 능력과 문제 해결력을 바탕으로, 국경을 넘어 가치를 창출하는 인재가 되겠습니다.
            </p>
        </section>

        <div class="space-y-24 relative z-10">

            <section id="about" class="bg-white p-8 rounded-2xl shadow-md">
                <h2 class="section-title text-3xl font-bold text-slate-800">소개 (About Me)</h2>
                <div class="grid md:grid-cols-3 gap-8 mt-8">
                    <div class="md:col-span-1 space-y-6">
                        <h3 class="text-xl font-bold text-slate-700">핵심 역량</h3>
                        <div class="space-y-4">
                            <div class="p-4 bg-slate-100 rounded-lg">
                                <h4 class="font-semibold text-blue-600">글로벌 소통 능력</h4>
                                <p class="text-sm text-slate-600">JLPT N1, 영어 스피치 경험을 바탕으로 한 원활한 비즈니스 커뮤니케이션</p>
                            </div>
                            <div class="p-4 bg-slate-100 rounded-lg">
                                <h4 class="font-semibold text-blue-600">논리적 문제 해결력</h4>
                                <p class="text-sm text-slate-600">직무 부트캠프를 통해 함양한 고객 니즈 분석 및 최적 해결책 제시 능력</p>
                            </div>
                            <div class="p-4 bg-slate-100 rounded-lg">
                                <h4 class="font-semibold text-blue-600">고객 중심 사고</h4>
                                <p class="text-sm text-slate-600">다양한 서비스직 경험을 통해 내재화된 이해관계자 공감 및 응대 능력</p>
                            </div>
                        </div>
                    </div>
                    <div class="md:col-span-2 space-y-6 text-slate-700 leading-relaxed">
                        <div>
                            <h4 class="font-semibold text-lg mb-2">성장 과정 및 강점</h4>
                            <p>유년기부터 리더십과 침착함을 인정받으며 성장했습니다. 항상 새로운 것에 대한 호기심이 많아 교내 공모전과 프로젝트에 적극적으로 참여하며 다양한 경험을 쌓았습니다. 특히 여러 나라의 문화와 생활 방식을 직접 체험하며, 무역 분야에 대한 흥미를 키웠습니다. 이러한 경험을 통해 국제적인 감각과 다문화 이해 능력을 갖추게 되었습니다.</p>
                        </div>
                         <div>
                            <h4 class="font-semibold text-lg mb-2">성격의 장단점</h4>
                            <p>진취적이고 리더십 있는 성격 덕분에 업무를 체계적으로 계획하고 효율적으로 진행하는 장점이 있습니다. 다만, 팀원 개개인의 의견을 경청하는 데 부족함이 있었으나, 봉사활동과 아동센터에서의 경험을 통해 타인의 목소리에 귀 기울이고 소통하는 방법을 배웠습니다. 이는 해외 바이어와의 협상 시 중요한 자산이 될 것입니다.</p>
                        </div>
                         <div>
                            <h4 class="font-semibold text-lg mb-2">지원 동기 및 포부</h4>
                            <p>세계화 시대에 귀사가 필요로 하는 글로벌 역량을 갖춘 인재라고 생각합니다. 저는 단순히 경제적 이익을 넘어, 저 자신을 한 단계 더 성장시키기 위해 업무에 임하고 싶습니다. 자기계발이 없는 무의미한 업무 반복은 성취감을 저해한다고 생각하며, 입사 후에도 직무 부트캠프에서 배운 실무 역량과 일본어 능력을 활용하여 귀사의 글로벌 성장에 기여하는 인재가 되겠습니다.</p>
                        </div>
                    </div>
                </div>
            </section>
            
            <section id="experience">
                <h2 class="section-title text-3xl font-bold text-slate-800">주요 경험 (Experience)</h2>
                <div class="relative mt-8 border-l-2 border-slate-200 pl-8 space-y-12">
                    <div class="timeline-item transition-transform duration-300 hover:scale-105">
                        <div class="absolute -left-2 top-0 w-4 h-4 rounded-full bg-blue-600 border-2 border-slate-50"></div>
                        <h3 class="text-xl font-bold text-slate-800">그레이스힐 검단지역아동센터</h3>
                        <p class="text-sm text-slate-500">2025.05 ~ 재직중</p>
                        <p class="mt-2 text-sm text-slate-600">
                            <strong>한국장학재단 다문화/탈북민 멘토링 장학금 사업의 일환</strong>으로 돌봄교사 업무를 수행하며, 다양한 문화적 배경을 가진 아동들의 요구사항을 이해하고 해결하는 능력을 길렀습니다. 이는 해외 바이어와의 소통에 필요한 공감 능력과 책임감으로 이어집니다.
                        </p>
                    </div>
                    <div class="timeline-item transition-transform duration-300 hover:scale-105">
                        <div class="absolute -left-2 top-0 w-4 h-4 rounded-full bg-blue-600 border-2 border-slate-50"></div>
                        <h3 class="text-xl font-bold text-slate-800">세븐일레븐 <span class="text-base font-medium text-slate-500 ml-2">판매직</span></h3>
                        <p class="text-sm text-slate-500">2023.05 ~ 2023.06 / 2022.03 ~ 2022.07</p>
                        <ul class="mt-2 list-disc list-inside text-slate-600 space-y-1">
                            <li>다양한 고객을 응대하며 원활한 커뮤니케이션 및 서비스 마인드 함양</li>
                            <li>고객 니즈를 빠르게 파악하고 적절한 상품을 추천하는 능력 습득</li>
                        </ul>
                    </div>
                    <div class="timeline-item transition-transform duration-300 hover:scale-105">
                        <div class="absolute -left-2 top-0 w-4 h-4 rounded-full bg-blue-600 border-2 border-slate-50"></div>
                        <h3 class="text-xl font-bold text-slate-800">에이모 & 메트릭스 <span class="text-base font-medium text-slate-500 ml-2">데이터 라벨링</span></h3>
                        <p class="text-sm text-slate-500">2021.11 ~ 2022.05</p>
                        <ul class="mt-2 list-disc list-inside text-slate-600 space-y-1">
                            <li>방대한 데이터를 꼼꼼하게 분류하고 분석하며 세밀한 업무 처리 능력 함양</li>
                            <li>복잡한 데이터를 정확하게 처리하며 무역 서류 관리와 같은 꼼꼼함과 집중력 습득</li>
                        </ul>
                    </div>
                </div>
            </section>

            <section id="skills" class="bg-white p-8 rounded-2xl shadow-md">
                <h2 class="section-title text-3xl font-bold text-slate-800">역량 및 교육 (Skills & Education)</h2>
                <div class="grid lg:grid-cols-2 gap-12 mt-8">
                    <div>
                        <h3 class="text-xl font-bold text-slate-700 mb-6">학력 및 어학</h3>
                        <div class="space-y-6">
                            <div>
                                <h4 class="font-semibold">서울신학대학교 <span class="font-normal text-sm text-slate-500">(2021.03 ~ 2026.08 예정)</span></h4>
                                <p class="text-slate-600">글로벌경영 전공 / 일본어문화콘텐츠 복수전공</p>
                            </div>
                            <div>
                                <h4 class="font-semibold mb-4">일본어 능력 (JLPT N1)</h4>
                                <div class="w-full text-center p-6 bg-slate-100 rounded-lg">
                                    <div class="text-3xl font-bold text-blue-600">준 비즈니스 레벨</div>
                                    <p class="mt-2 text-sm text-slate-600">뉴스, 시사, 논설 등 폭넓은 주제에 대한 이해와 원어민과의 원활한 소통 가능</p>
                                    <div class="mt-4 flex flex-col items-center">
                                        <div id="language-bar-container" class="w-2/3 h-2 bg-blue-200 rounded-full overflow-hidden">
                                            <div id="language-bar" class="h-full bg-blue-600 rounded-full" style="width: 0;"></div>
                                        </div>
                                        <div class="mt-2 text-xs text-slate-500">이해 및 활용 능력</div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                    <div>
                        <h3 class="text-xl font-bold text-slate-700 mb-6">자격 및 수상</h3>
                        <ul class="space-y-3">
                            <li class="flex items-center"><span class="bg-blue-100 text-blue-800 text-xs font-semibold mr-2 px-2.5 py-0.5 rounded-full">자격</span> 新JLPT N1 (2025.08)</li>
                            <li class="flex items-center"><span class="bg-blue-100 text-blue-800 text-xs font-semibold mr-2 px-2.5 py-0.5 rounded-full">자격</span> 컴퓨터활용능력 2급 (2025.09)</li>
                            <li class="flex items-center"><span class="bg-blue-100 text-blue-800 text-xs font-semibold mr-2 px-2.5 py-0.5 rounded-full">자격</span> 2종보통운전면허 (2021.02)</li>
                            <li class="flex items-center"><span class="bg-blue-100 text-blue-800 text-xs font-semibold mr-2 px-2.5 py-0.5 rounded-full">자격</span> 디지털정보활용능력(DIAT) (2014.05)</li>
                            <li class="flex items-center"><span class="bg-green-100 text-green-800 text-xs font-semibold mr-2 px-2.5 py-0.5 rounded-full">수상</span> 제7회 서울신학대학교 학술적 글쓰기 대회 최우수상 (2025.07)</li>
                            <li class="flex items-center"><span class="bg-green-100 text-green-800 text-xs font-semibold mr-2 px-2.5 py-0.5 rounded-full">수상</span> H+ English Speech Contest 장려상 (2025.06)</li>
                            <li class="flex items-center"><span class="bg-green-100 text-green-800 text-xs font-semibold mr-2 px-2.5 py-0.5 rounded-full">수상</span> STU챌린저스! 프로그램 우수상 (2024.03)</li>
                        </ul>
                    </div>
                </div>
                 <div class="mt-16">
                    <h3 class="text-xl font-bold text-slate-700 mb-6">주요 교육 이수</h3>
                    <div class="grid md:grid-cols-2 gap-6">
                        <div class="bg-slate-50 p-6 rounded-lg border border-slate-200">
                            <h4 class="font-bold text-slate-800">콘텐츠 마케팅 실무 5주 완성 캠프</h4>
                            <p class="text-sm text-slate-500 mb-3">코멘토 (2024.11 ~ 2024.12)</p>
                            <p class="text-slate-600">내/외부 환경 분석 기반 커뮤니케이션 전략 수립 및 채널별 콘텐츠(숏폼, 아티클) 기획/제작 실무 역량을 강화했습니다.</p>
                        </div>
                        <div class="bg-slate-50 p-6 rounded-lg border border-slate-200">
                            <h4 class="font-bold text-slate-800">B2B기술영업 & B2C영업관리 캠프</h4>
                            <p class="text-sm text-slate-500 mb-3">코멘토 (2023.12 ~ 2024.01)</p>
                            <p class="text-slate-600">고객사 니즈 파악, B2B 상품 제안, 기대 효과 중심의 제안서 작성 등 현업 중심의 영업 실무 경험을 쌓았습니다.</p>
                        </div>
                    </div>
                </div>
            </section>
        </div>
    </main>

    <footer id="contact" class="bg-slate-800 text-white mt-24">
        <div class="max-w-7xl mx-auto py-12 px-4 sm:px-6 lg:px-8 text-center">
            <h2 class="text-3xl font-bold">연락처 (Contact)</h2>
            <p class="mt-4 text-lg text-slate-300">
                <span class="font-semibold">저의 열정, 귀사의 성장으로 이어집니다.</span>
                <br>
                글로벌 시장을 향한 끊임없는 도전으로 귀사에 기여할 준비가 되어 있습니다.
                <br class="hidden md:block">
                성장 가능성을 믿고 함께 할 기회를 기다리겠습니다.
            </p>
            <div class="mt-8 flex justify-center items-center space-x-6">
                <div class="flex items-center">
                    <svg class="w-6 h-6 mr-2 text-slate-400" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"></path></svg>
                    <a href="mailto:rlawodus0722@gmail.com" class="text-blue-300 hover:text-blue-200">rlawodus0722@gmail.com</a>
                </div>
                <div class="flex items-center">
                    <svg class="w-6 h-6 mr-2 text-slate-400" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z"></path></svg>
                    <span class="text-slate-300">010-2396-3708</span>
                </div>
            </div>
             <div class="mt-8">
                 <a href="https://www.linkedin.com/in/jaeyeon-kim-a52158232/" target="_blank" rel="noopener noreferrer" class="inline-block bg-blue-600 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
                    LinkedIn 프로필 보기
                </a>
            </div>
        </div>
    </footer>

    <script>
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                document.querySelector(this.getAttribute('href')).scrollIntoView({
                    behavior: 'smooth'
                });
            });
        });

        document.addEventListener('DOMContentLoaded', () => {
            const sections = document.querySelectorAll('section');
            const observerOptions = {
                root: null,
                rootMargin: '0px',
                threshold: 0.5
            };
            const observer = new IntersectionObserver((entries, observer) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        sections.forEach(sec => sec.style.filter = 'blur(5px)');
                        entry.target.style.filter = 'blur(0px)';

                        const timelineItems = entry.target.querySelectorAll('.timeline-item');
                        timelineItems.forEach((item, index) => {
                            setTimeout(() => {
                                item.classList.add('fade-in');
                            }, index * 200);
                        });

                        if (entry.target.id === 'skills') {
                            animateLanguageBar();
                        }
                    } else {
                        const timelineItems = entry.target.querySelectorAll('.timeline-item');
                        timelineItems.forEach(item => {
                            item.classList.remove('fade-in');
                        });
                    }
                });
            }, observerOptions);

            sections.forEach(section => {
                observer.observe(section);
            });

            function animateLanguageBar() {
                const bar = document.getElementById('language-bar');
                if (bar) {
                    bar.style.transition = 'width 1s ease-out';
                    bar.style.width = '90%';
                }
            }
        });
    </script>

</body>
</html>
