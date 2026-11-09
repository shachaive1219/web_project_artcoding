# web_project_artcoding
아트코딩 웹 프로젝트
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>acarive - 스마트한 자동차 정보 아카이브 & 시세 백과</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+KR:wght@300;400;500;600;700;800&family=Montserrat:wght@700;800;900&display=swap" rel="stylesheet">
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    fontFamily: {
                        sans: ['Noto Sans KR', 'sans-serif'],
                        brand: ['Montserrat', 'sans-serif'],
                    },
                    colors: {
                        acarive: {
                            50: '#f0f9ff',
                            100: '#e0f2fe',
                            500: '#0284c7',
                            600: '#0369a1',
                            700: '#0f2c59',
                            800: '#091e3e',
                            accent: '#00c2ff'
                        }
                    }
                }
            }
        }
    </script>
    <style>
        .mega-menu {
            opacity: 0;
            visibility: hidden;
            transform: translateY(-8px);
            transition: all 0.2s ease-in-out;
        }
        .group:hover .mega-menu {
            opacity: 1;
            visibility: visible;
            transform: translateY(0);
        }
        ::-webkit-scrollbar {
            width: 6px;
        }
        ::-webkit-scrollbar-thumb {
            background: #cbd5e1;
            border-radius: 9999px;
        }
    </style>
</head>
<body class="bg-slate-50 text-slate-800 font-sans antialiased">

    <!-- TOP NOTICE BAR -->
    <div class="bg-acarive-800 text-slate-200 text-xs py-2 px-4 text-center">
        <span><strong class="text-acarive-accent">acarive Auto Archive</strong> : 제조사별 제원, 연비, 출고 시세 및 유지비 백과사전</span>
    </div>

    <!-- MAIN HEADER -->
    <header class="sticky top-0 z-50 bg-white/95 backdrop-blur-md border-b border-slate-200 shadow-sm">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex items-center justify-between h-20">
                
                <!-- Left: acarive Logo + Mega Menu -->
                <div class="flex items-center space-x-6 sm:space-x-8">
                    <!-- Brand Logo -->
                    <a href="#" class="flex items-center space-x-2.5 shrink-0 group">
                        <div class="w-10 h-10 bg-gradient-to-tr from-acarive-700 to-acarive-accent rounded-xl flex items-center justify-center text-white shadow-md group-hover:scale-105 transition">
                            <i class="fa-solid fa-car-rear text-lg"></i>
                        </div>
                        <div class="flex flex-col">
                            <span class="text-2xl font-black font-brand tracking-tighter text-acarive-700 leading-none">
                                aca<span class="text-acarive-500">rive</span>
                            </span>
                            <span class="text-[9px] text-slate-400 font-bold tracking-widest mt-0.5 uppercase">Car Knowledge Archive</span>
                        </div>
                    </a>

                    <!-- Vertical Line -->
                    <div class="hidden md:block h-7 w-[1px] bg-slate-200"></div>

                    <!-- Mega Menu Nav -->
                    <nav class="hidden md:flex items-center space-x-1 lg:space-x-2">
                        
                        <!-- 현대 -->
                        <div class="group relative py-6">
                            <button class="flex items-center space-x-1 px-3 py-2 rounded-lg font-bold text-slate-800 hover:text-acarive-500 hover:bg-slate-100 transition text-sm">
                                <span>현대</span>
                                <i class="fa-solid fa-chevron-down text-[9px] text-slate-400 group-hover:rotate-180 transition-transform"></i>
                            </button>
                            <div class="mega-menu absolute top-full left-0 w-[580px] bg-white rounded-2xl shadow-2xl border border-slate-100 p-5 grid grid-cols-2 gap-4 z-50">
                                <div>
                                    <div class="text-xs font-black text-acarive-700 border-b border-slate-100 pb-2 mb-2">세단 &amp; SUV</div>
                                    <ul class="space-y-2 text-xs text-slate-600 font-medium">
                                        <li onclick="showCarDetailByName('그랜저')" class="hover:text-acarive-500 cursor-pointer flex justify-between p-1 rounded hover:bg-slate-50">
                                            <span>그랜저 (준대형)</span> <span class="font-bold text-slate-400">평균 4.2천만</span>
                                        </li>
                                        <li onclick="showCarDetailByName('쏘나타')" class="hover:text-acarive-500 cursor-pointer flex justify-between p-1 rounded hover:bg-slate-50">
                                            <span>쏘나타 (중형)</span> <span class="font-bold text-slate-400">평균 2.9천만</span>
                                        </li>
                                        <li onclick="showCarDetailByName('싼타페')" class="hover:text-acarive-500 cursor-pointer flex justify-between p-1 rounded hover:bg-slate-50">
                                            <span>싼타페 (중형 SUV)</span> <span class="font-bold text-slate-400">평균 3.8천만</span>
                                        </li>
                                    </ul>
                                </div>
                                <div class="bg-sky-50 rounded-xl p-3 border border-sky-100 flex flex-col justify-between">
                                    <div>
                                        <span class="text-[10px] font-bold text-acarive-600 bg-white px-2 py-0.5 rounded">HYUNDAI</span>
                                        <div class="font-extrabold text-sm text-acarive-700 mt-2">현대 자동차 아카이브</div>
                                        <p class="text-[11px] text-slate-500 mt-1">대중성과 하이브리드 기술력을 고루 갖춘 국내 대표 브랜드</p>
                                    </div>
                                    <button onclick="filterByBrand('현대')" class="w-full py-2 bg-acarive-500 hover:bg-acarive-600 text-white font-bold rounded-lg text-xs mt-3">현대 라인업 전체보기</button>
                                </div>
                            </div>
                        </div>

                        <!-- 기아 -->
                        <div class="group relative py-6">
                            <button class="flex items-center space-x-1 px-3 py-2 rounded-lg font-bold text-slate-800 hover:text-acarive-500 hover:bg-slate-100 transition text-sm">
                                <span>기아</span>
                                <i class="fa-solid fa-chevron-down text-[9px] text-slate-400 group-hover:rotate-180 transition-transform"></i>
                            </button>
                            <div class="mega-menu absolute top-full left-0 w-[580px] bg-white rounded-2xl shadow-2xl border border-slate-100 p-5 grid grid-cols-2 gap-4 z-50">
                                <div>
                                    <div class="text-xs font-black text-acarive-700 border-b border-slate-100 pb-2 mb-2">승용 &amp; 패밀리 RV</div>
                                    <ul class="space-y-2 text-xs text-slate-600 font-medium">
                                        <li onclick="showCarDetailByName('쏘렌토')" class="hover:text-acarive-500 cursor-pointer flex justify-between p-1 rounded hover:bg-slate-50">
                                            <span>쏘렌토 (중형 SUV)</span> <span class="font-bold text-slate-400">평균 4.1천만</span>
                                        </li>
                                        <li onclick="showCarDetailByName('카니발')" class="hover:text-acarive-500 cursor-pointer flex justify-between p-1 rounded hover:bg-slate-50">
                                            <span>카니발 (패밀리 MPV)</span> <span class="font-bold text-slate-400">평균 3.8천만</span>
                                        </li>
                                        <li onclick="showCarDetailByName('K8')" class="hover:text-acarive-500 cursor-pointer flex justify-between p-1 rounded hover:bg-slate-50">
                                            <span>K8 (준대형 세단)</span> <span class="font-bold text-slate-400">평균 3.9천만</span>
                                        </li>
                                    </ul>
                                </div>
                                <div class="bg-sky-50 rounded-xl p-3 border border-sky-100 flex flex-col justify-between">
                                    <div>
                                        <span class="text-[10px] font-bold text-acarive-600 bg-white px-2 py-0.5 rounded">KIA</span>
                                        <div class="font-extrabold text-sm text-acarive-700 mt-2">기아 자동차 아카이브</div>
                                        <p class="text-[11px] text-slate-500 mt-1">세련된 디자인과 공간 활용성 높은 SUV 라인업 중심</p>
                                    </div>
                                    <button onclick="filterByBrand('기아')" class="w-full py-2 bg-acarive-500 hover:bg-acarive-600 text-white font-bold rounded-lg text-xs mt-3">기아 라인업 전체보기</button>
                                </div>
                            </div>
                        </div>

                        <!-- 제네시스 -->
                        <div class="group relative py-6">
                            <button class="flex items-center space-x-1 px-3 py-2 rounded-lg font-bold text-slate-800 hover:text-acarive-500 hover:bg-slate-100 transition text-sm">
                                <span>제네시스</span>
                                <i class="fa-solid fa-chevron-down text-[9px] text-slate-400 group-hover:rotate-180 transition-transform"></i>
                            </button>
                            <div class="mega-menu absolute top-full left-0 w-[500px] bg-white rounded-2xl shadow-2xl border border-slate-100 p-5 grid grid-cols-2 gap-4 z-50">
                                <div>
                                    <div class="text-xs font-black text-acarive-700 border-b border-slate-100 pb-2 mb-2">프리미엄 라인</div>
                                    <ul class="space-y-2 text-xs text-slate-600 font-medium">
                                        <li onclick="showCarDetailByName('G80')" class="hover:text-acarive-500 cursor-pointer flex justify-between p-1 rounded hover:bg-slate-50">
                                            <span>G80 (럭셔리 세단)</span> <span class="font-bold text-slate-400">평균 6.5천만</span>
                                        </li>
                                        <li onclick="showCarDetailByName('GV80')" class="hover:text-acarive-500 cursor-pointer flex justify-between p-1 rounded hover:bg-slate-50">
                                            <span>GV80 (플래그십 SUV)</span> <span class="font-bold text-slate-400">평균 7.8천만</span>
                                        </li>
                                    </ul>
                                </div>
                                <div class="bg-slate-900 text-white rounded-xl p-3 flex flex-col justify-between">
                                    <div>
                                        <span class="text-[10px] font-bold text-amber-400 bg-slate-800 px-2 py-0.5 rounded">PREMIUM</span>
                                        <div class="font-extrabold text-sm text-white mt-2">제네시스 라인업</div>
                                        <p class="text-[11px] text-slate-300 mt-1">대한민국 대표 럭셔리 브랜드의 승차감과 디테일</p>
                                    </div>
                                    <button onclick="filterByBrand('제네시스')" class="w-full py-2 bg-acarive-accent text-acarive-800 font-bold rounded-lg text-xs mt-3">제네시스 전체보기</button>
                                </div>
                            </div>
                        </div>

                        <!-- 수입차 -->
                        <div class="group relative py-6">
                            <button class="flex items-center space-x-1 px-3 py-2 rounded-lg font-bold text-slate-800 hover:text-acarive-500 hover:bg-slate-100 transition text-sm">
                                <span>수입 럭셔리</span>
                                <i class="fa-solid fa-chevron-down text-[9px] text-slate-400 group-hover:rotate-180 transition-transform"></i>
                            </button>
                            <div class="mega-menu absolute top-full left-0 w-[420px] bg-white rounded-2xl shadow-2xl border border-slate-100 p-4 z-50">
                                <div class="text-xs font-black text-acarive-700 border-b border-slate-100 pb-2 mb-2">벤츠 &amp; BMW 주요 모델</div>
                                <ul class="space-y-1.5 text-xs text-slate-600 font-semibold">
                                    <li onclick="showCarDetailByName('E-Class')" class="hover:text-acarive-500 cursor-pointer flex justify-between p-1.5 hover:bg-slate-50 rounded-lg">
                                        <span>Mercedes E-Class</span> <span class="text-acarive-500">8,200만 원</span>
                                    </li>
                                    <li onclick="showCarDetailByName('5시리즈')" class="hover:text-acarive-500 cursor-pointer flex justify-between p-1.5 hover:bg-slate-50 rounded-lg">
                                        <span>BMW 5시리즈</span> <span class="text-acarive-500">7,800만 원</span>
                                    </li>
                                    <li onclick="showCarDetailByName('Model Y')" class="hover:text-acarive-500 cursor-pointer flex justify-between p-1.5 hover:bg-slate-50 rounded-lg">
                                        <span>Tesla Model Y (전기)</span> <span class="text-acarive-500">5,499만 원</span>
                                    </li>
                                </ul>
                            </div>
                        </div>

                    </nav>
                </div>

                <!-- Right Quick Search -->
                <div class="flex items-center space-x-2">
                    <div class="relative hidden sm:block">
                        <input type="text" id="header-search-input" onkeyup="searchCarCatalog(this.value)" placeholder="차종 검색 (예: 쏘렌토, 전기차)" class="w-48 lg:w-64 bg-slate-100 border border-slate-200 rounded-full py-2 pl-9 pr-4 text-xs font-semibold text-slate-800 focus:outline-none focus:ring-2 focus:ring-acarive-500 transition">
                        <i class="fa-solid fa-magnifying-glass absolute left-3.5 top-2.5 text-slate-400 text-xs"></i>
                    </div>
                </div>

            </div>
        </div>
    </header>

    <!-- HERO SECTION -->
    <section class="relative bg-gradient-to-b from-acarive-800 via-acarive-700 to-acarive-800 text-white py-16 lg:py-20 overflow-hidden">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10 text-center">
            
            <div class="inline-flex items-center space-x-2 bg-sky-500/10 border border-sky-400/30 text-acarive-accent px-4 py-1.5 rounded-full text-xs font-semibold mb-6">
                <i class="fa-solid fa-book-bookmark text-acarive-accent"></i>
                <span>더 명확하고 투명한 자동차 정보 아카이브, <strong>acarive</strong></span>
            </div>

            <h1 class="text-3xl sm:text-5xl font-black leading-tight tracking-tight max-w-4xl mx-auto font-brand">
                내게 맞는 자동차를 가장 빠르게 찾는 법,<br class="hidden sm:block">
                <span class="bg-gradient-to-r from-acarive-accent via-sky-200 to-indigo-200 bg-clip-text text-transparent">acarive</span>에서 한눈에 비교해 보세요
            </h1>

            <p class="text-slate-300 text-sm sm:text-base max-w-2xl mx-auto mt-4 font-normal leading-relaxed">
                출고가, 복합 연비, 배기량, 연료 특성 및 예상 세금까지 — 복잡한 카탈로그 데이터를 알기 쉽게 정리해 드립니다.
            </p>

            <!-- HERO FILTER -->
            <div class="mt-10 max-w-4xl mx-auto bg-white rounded-2xl p-5 shadow-2xl text-slate-800 border border-slate-100 text-left">
                <div class="text-xs font-bold text-slate-400 uppercase tracking-wider mb-3 flex items-center justify-between">
                    <span><i class="fa-solid fa-filter text-acarive-500 mr-1.5"></i> 맞춤 차종 필터</span>
                    <span class="text-[11px] text-slate-400 font-normal">데이터 아카이브 실시간 필터링</span>
                </div>

                <div class="grid grid-cols-1 sm:grid-cols-4 gap-3">
                    <!-- Brand -->
                    <div>
                        <label class="block text-xs font-bold text-slate-600 mb-1">제조사</label>
                        <select id="filter-brand" onchange="applyFilters()" class="w-full bg-slate-50 border border-slate-200 rounded-xl p-2.5 text-xs font-bold text-slate-700 focus:outline-none focus:ring-2 focus:ring-acarive-500">
                            <option value="전체">전체 브랜드</option>
                            <option value="현대">현대 (Hyundai)</option>
                            <option value="기아">기아 (Kia)</option>
                            <option value="제네시스">제네시스 (Genesis)</option>
                            <option value="벤츠">메르세데스-벤츠</option>
                            <option value="BMW">BMW</option>
                            <option value="테슬라">테슬라 (Tesla)</option>
                        </select>
                    </div>

                    <!-- Type -->
                    <div>
                        <label class="block text-xs font-bold text-slate-600 mb-1">차종 형태</label>
                        <select id="filter-type" onchange="applyFilters()" class="w-full bg-slate-50 border border-slate-200 rounded-xl p-2.5 text-xs font-bold text-slate-700 focus:outline-none focus:ring-2 focus:ring-acarive-500">
                            <option value="전체">전체 형태</option>
                            <option value="세단">세단 (Sedan)</option>
                            <option value="SUV">SUV / RV</option>
                        </select>
                    </div>

                    <!-- Fuel -->
                    <div>
                        <label class="block text-xs font-bold text-slate-600 mb-1">연료 방식</label>
                        <select id="filter-fuel" onchange="applyFilters()" class="w-full bg-slate-50 border border-slate-200 rounded-xl p-2.5 text-xs font-bold text-slate-700 focus:outline-none focus:ring-2 focus:ring-acarive-500">
                            <option value="전체">전체 연료</option>
                            <option value="하이브리드">하이브리드 (HEV)</option>
                            <option value="가솔린">가솔린</option>
                            <option value="전기">순수 전기 (EV)</option>
                        </select>
                    </div>

                    <!-- Price -->
                    <div>
                        <label class="block text-xs font-bold text-slate-600 mb-1">평균 예산</label>
                        <select id="filter-price" onchange="applyFilters()" class="w-full bg-slate-50 border border-slate-200 rounded-xl p-2.5 text-xs font-bold text-slate-700 focus:outline-none focus:ring-2 focus:ring-acarive-500">
                            <option value="전체">전체 가격</option>
                            <option value="3500">3,500만 원 이하</option>
                            <option value="5000">3,500만 ~ 5,000만 원</option>
                            <option value="8000">5,000만 ~ 8,000만 원</option>
                            <option value="10000">8,000만 원 이상</option>
                        </select>
                    </div>
                </div>
            </div>

        </div>
    </section>

    <!-- CAR KNOWLEDGE / HIGHLIGHTS SECTION -->
    <section class="py-12 bg-white border-b border-slate-200">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                <div class="flex items-start space-x-4 p-4 rounded-2xl bg-slate-50 border border-slate-100">
                    <div class="w-12 h-12 rounded-xl bg-sky-100 text-acarive-500 flex items-center justify-center text-xl shrink-0">
                        <i class="fa-solid fa-gas-pump"></i>
                    </div>
                    <div>
                        <h4 class="font-extrabold text-sm text-slate-900">연비 및 구동계 이해하기</h4>
                        <p class="text-xs text-slate-500 mt-1">도심 주행이 많다면 HEV(하이브리드), 장거리 주행이 많다면 고효율 가솔린/디젤을 고려해 보세요.</p>
                    </div>
                </div>

                <div class="flex items-start space-x-4 p-4 rounded-2xl bg-slate-50 border border-slate-100">
                    <div class="w-12 h-12 rounded-xl bg-indigo-100 text-indigo-600 flex items-center justify-center text-xl shrink-0">
                        <i class="fa-solid fa-receipt"></i>
                    </div>
                    <div>
                        <h4 class="font-extrabold text-sm text-slate-900">신차 구매 부대비용</h4>
                        <p class="text-xs text-slate-500 mt-1">차량가 외에 보통 차량 가격의 약 7% 취등록세와 공채 할인, 탁송비가 추가로 발생합니다.</p>
                    </div>
                </div>

                <div class="flex items-start space-x-4 p-4 rounded-2xl bg-slate-50 border border-slate-100">
                    <div class="w-12 h-12 rounded-xl bg-amber-100 text-amber-600 flex items-center justify-center text-xl shrink-0">
                        <i class="fa-solid fa-bolt"></i>
                    </div>
                    <div>
                        <h4 class="font-extrabold text-sm text-slate-900">전기차(EV) 보조금 체크</h4>
                        <p class="text-xs text-slate-500 mt-1">전기차는 국고 및 지자체 보조금 여부에 따라 실제 구매가가 300만~700만 원가량 낮아집니다.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- CAR CATALOG GRID SECTION -->
    <section class="py-16 bg-slate-50">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            
            <div class="flex flex-col sm:flex-row justify-between items-start sm:items-end mb-8 gap-4">
                <div>
                    <span class="text-xs font-black text-acarive-500 bg-sky-100 px-3 py-1 rounded-full uppercase tracking-wider">acarive catalog</span>
                    <h2 class="text-2xl sm:text-3xl font-black text-slate-900 mt-2">차종별 제원 및 평균가 백과</h2>
                </div>
                <div class="text-xs font-bold text-slate-500">
                    총 <span id="car-count-text" class="text-acarive-500 font-black text-base">0</span>개의 차종 등록됨
                </div>
            </div>

            <!-- CAR CARDS GRID -->
            <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6" id="catalog-grid">
                <!-- Javascript fills this -->
            </div>

        </div>
    </section>

    <!-- FOOTER -->
    <footer class="bg-acarive-800 text-slate-400 text-xs py-12 border-t border-slate-700">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 flex flex-col md:flex-row justify-between items-center gap-6">
            <div class="flex flex-col sm:flex-row items-center sm:space-x-3 text-center sm:text-left">
                <div class="flex items-center space-x-2">
                    <div class="w-8 h-8 bg-acarive-accent rounded-lg flex items-center justify-center text-acarive-800 font-bold">
                        <i class="fa-solid fa-car-rear"></i>
                    </div>
                    <span class="text-xl font-black font-brand text-white">aca<span class="text-acarive-accent">rive</span></span>
                </div>
                <span class="hidden sm:inline text-slate-500">|</span>
                <span class="text-slate-400 mt-1 sm:mt-0 font-medium">스마트 자동차 정보 &amp; 가격 가이드 플랫폼</span>
            </div>
            <p class="text-slate-400 text-center md:text-right text-[11px] leading-relaxed max-w-md">
                acarive는 구매자와 자동차 매니아를 위해 표준 제원 및 평균 출고 시세를 체계적으로 정리해 제공하는 자동차 전문 정보 아카이브입니다.
            </p>
        </div>
    </footer>

    <!-- DETAIL MODAL -->
    <div id="modal-backdrop" class="fixed inset-0 bg-slate-950/70 backdrop-blur-sm z-50 hidden flex items-center justify-center p-4">
        <div class="bg-white rounded-3xl max-w-lg w-full p-6 shadow-2xl relative text-slate-800 animate-in fade-in zoom-in-95 duration-150">
            <button onclick="closeModal()" class="absolute top-5 right-5 p-2 text-slate-400 hover:text-slate-700">
                <i class="fa-solid fa-xmark text-xl"></i>
            </button>

            <div id="modal-content">
                <!-- Javascript will inject data -->
            </div>
        </div>
    </div>

    <!-- JAVASCRIPT LOGIC -->
    <script>
        // acarive 자동차 데이터베이스 (제원 및 가이드 정보 보강)
        const carDatabase = [
            { 
                name: '그랜저', 
                brand: '현대', 
                type: '세단', 
                avgPrice: 4200, 
                range: '3,700만 ~ 5,200만 원', 
                fuel: '가솔린 / 하이브리드', 
                fuelEfficiency: '10.0 ~ 18.0 km/ℓ', 
                displacement: '1,598 ~ 3,470 cc',
                feature: '국내 준대형 세단 판매 1위, 넓은 실내와 패밀리 세단으로서의 완성도' 
            },
            { 
                name: '싼타페', 
                brand: '현대', 
                type: 'SUV', 
                avgPrice: 3800, 
                range: '3,540만 ~ 4,700만 원', 
                fuel: '가솔린 / 하이브리드', 
                fuelEfficiency: '10.0 ~ 15.5 km/ℓ', 
                displacement: '1,598 ~ 2,497 cc',
                feature: '각진 박스형 정통 SUV 스타일과 넓은 트렁크 공간, 차박 및 패밀리카 최적화' 
            },
            { 
                name: '쏘나타', 
                brand: '현대', 
                type: '세단', 
                avgPrice: 2900, 
                range: '2,800만 ~ 3,900만 원', 
                fuel: '가솔린 / 하이브리드', 
                fuelEfficiency: '11.1 ~ 19.4 km/ℓ', 
                displacement: '1,598 ~ 2,497 cc',
                feature: '날렵한 패스트백 디자인과 뛰어난 가성비의 중형 패밀리 세단' 
            },
            { 
                name: '쏘렌토', 
                brand: '기아', 
                type: 'SUV', 
                avgPrice: 4100, 
                range: '3,500만 ~ 4,800만 원', 
                fuel: '가솔린 / 하이브리드', 
                fuelEfficiency: '10.8 ~ 15.7 km/ℓ', 
                displacement: '1,598 ~ 2,497 cc',
                feature: '국내 전체 판매 1위를 다투는 스테디셀러 SUV, 높은 잔존가치와 완성도' 
            },
            { 
                name: '카니발', 
                brand: '기아', 
                type: 'SUV', 
                avgPrice: 3800, 
                range: '3,470만 ~ 4,900만 원', 
                fuel: '가솔린 / 하이브리드', 
                fuelEfficiency: '9.0 ~ 14.0 km/ℓ', 
                displacement: '1,598 ~ 3,470 cc',
                feature: '대체 불가능한 대한민국 대표 다인승 패밀리 미니밴(MPV)' 
            },
            { 
                name: 'K8', 
                brand: '기아', 
                type: '세단', 
                avgPrice: 3900, 
                range: '3,700만 ~ 4,600만 원', 
                fuel: '가솔린 / 하이브리드', 
                fuelEfficiency: '10.2 ~ 18.0 km/ℓ', 
                displacement: '1,598 ~ 3,470 cc',
                feature: '세련된 실내 커브드 디스플레이와 안락한 정숙성을 갖춘 준대형 세단' 
            },
            { 
                name: 'GV80', 
                brand: '제네시스', 
                type: 'SUV', 
                avgPrice: 7800, 
                range: '6,930만 ~ 9,100만 원', 
                fuel: '가솔린', 
                fuelEfficiency: '7.7 ~ 9.7 km/ℓ', 
                displacement: '2,497 ~ 3,470 cc',
                feature: '수입 럭셔리 SUV와 경쟁하는 국산 최고급 플래그십 SUV' 
            },
            { 
                name: 'G80', 
                brand: '제네시스', 
                type: '세단', 
                avgPrice: 6500, 
                range: '5,890만 ~ 7,500만 원', 
                fuel: '가솔린', 
                fuelEfficiency: '8.9 ~ 10.6 km/ℓ', 
                displacement: '2,497 ~ 3,470 cc',
                feature: '우아한 비율과 최상급 승차감을 제공하는 제네시스의 간판 세단' 
            },
            { 
                name: 'E-Class', 
                brand: '벤츠', 
                type: '세단', 
                avgPrice: 8200, 
                range: '7,390만 ~ 1억 1,500만 원', 
                fuel: '가솔린', 
                fuelEfficiency: '10.5 ~ 12.4 km/ℓ', 
                displacement: '1,999 cc',
                feature: '독일 프리미엄 세단의 정수, 최첨단 실내 인포테인먼트와 브랜드 가치' 
            },
            { 
                name: '5시리즈', 
                brand: 'BMW', 
                type: '세단', 
                avgPrice: 7800, 
                range: '6,880만 ~ 8,870만 원', 
                fuel: '가솔린', 
                fuelEfficiency: '11.1 ~ 14.7 km/ℓ', 
                displacement: '1,998 cc',
                feature: '역동적인 주행 퍼포먼스와 스포티한 감각이 돋보이는 대표 비즈니스 세단' 
            },
            { 
                name: 'Model Y', 
                brand: '테슬라', 
                type: 'SUV', 
                avgPrice: 5499, 
                range: '5,299만 ~ 7,200만 원', 
                fuel: '전기', 
                fuelEfficiency: '4.8 ~ 5.3 km/kWh', 
                displacement: '순수 전기 모터',
                feature: '글로벌 베스트셀러 전기 SUV, 압도적인 오토파일럿과 충전 인프라' 
            }
        ];

        function renderCatalog(items) {
            const grid = document.getElementById('catalog-grid');
            const countText = document.getElementById('car-count-text');
            grid.innerHTML = '';
            countText.innerText = items.length;

            if (items.length === 0) {
                grid.innerHTML = `
                    <div class="col-span-full py-16 text-center text-slate-400 bg-white rounded-3xl border border-dashed border-slate-200">
                        <i class="fa-solid fa-car-burst text-5xl mb-3 text-slate-300"></i>
                        <p class="text-base font-bold text-slate-700">조건에 일치하는 자동차 정보가 없습니다.</p>
                        <p class="text-xs text-slate-400 mt-1">필터 조건을 재설정하거나 다른 검색어를 입력해 보세요.</p>
                    </div>
                `;
                return;
            }

            items.forEach(car => {
                const card = document.createElement('div');
                card.className = 'bg-white rounded-3xl p-5 border border-slate-200/80 hover:border-acarive-500 hover:shadow-xl hover:-translate-y-1 transition duration-200 flex flex-col justify-between';
                
                // 연료 배지 색상
                let fuelBadge = 'bg-slate-100 text-slate-600';
                if(car.fuel.includes('전기')) fuelBadge = 'bg-emerald-50 text-emerald-600 font-bold';
                else if(car.fuel.includes('하이브리드')) fuelBadge = 'bg-sky-50 text-acarive-600 font-bold';

                card.innerHTML = `
                    <div>
                        <div class="flex justify-between items-center mb-2">
                            <span class="text-[11px] font-bold bg-slate-100 text-slate-700 px-2.5 py-0.5 rounded-full">${car.brand}</span>
                            <span class="text-xs font-bold text-acarive-500">${car.type}</span>
                        </div>
                        <h3 class="text-xl font-black text-slate-900">${car.name}</h3>
                        <p class="text-[11px] text-slate-400 line-clamp-1 mt-0.5">${car.feature}</p>
                        
                        <!-- Visual Icon Graphic -->
                        <div class="my-4 h-28 bg-gradient-to-tr from-slate-100 to-sky-50 rounded-2xl flex items-center justify-center text-slate-300">
                            <i class="fa-solid fa-car-side text-5xl text-slate-400/80"></i>
                        </div>

                        <div class="space-y-1.5 text-xs text-slate-600 mb-4 bg-slate-50 p-3 rounded-xl border border-slate-100">
                            <div class="flex justify-between items-center">
                                <span class="text-slate-400">대표 평균가</span>
                                <strong class="text-acarive-700 text-sm font-black">${car.avgPrice.toLocaleString()}만 원</strong>
                            </div>
                            <div class="flex justify-between items-center">
                                <span class="text-slate-400">연비</span>
                                <span class="font-bold text-slate-700">${car.fuelEfficiency}</span>
                            </div>
                            <div class="flex justify-between items-center">
                                <span class="text-slate-400">구동 연료</span>
                                <span class="text-[11px] px-1.5 py-0.2 rounded ${fuelBadge}">${car.fuel}</span>
                            </div>
                        </div>
                    </div>

                    <button onclick="showCarDetailByName('${car.name}')" class="w-full py-2.5 bg-slate-50 border border-slate-200 hover:bg-acarive-500 hover:text-white hover:border-acarive-500 text-slate-800 font-bold rounded-xl text-xs transition flex items-center justify-center space-x-1.5">
                        <i class="fa-solid fa-circle-info"></i>
                        <span>차량 정보 &amp; 비용 분석</span>
                    </button>
                `;
                grid.appendChild(card);
            });
        }

        function applyFilters() {
            const brand = document.getElementById('filter-brand').value;
            const type = document.getElementById('filter-type').value;
            const fuel = document.getElementById('filter-fuel').value;
            const price = document.getElementById('filter-price').value;

            let filtered = carDatabase.filter(item => {
                if (brand !== '전체' && item.brand !== brand) return false;
                if (type !== '전체' && item.type !== type) return false;
                if (fuel !== '전체' && !item.fuel.includes(fuel)) return false;
                if (price === '3500' && item.avgPrice > 3500) return false;
                if (price === '5000' && (item.avgPrice < 3500 || item.avgPrice > 5000)) return false;
                if (price === '8000' && (item.avgPrice < 5000 || item.avgPrice > 8000)) return false;
                if (price === '10000' && item.avgPrice < 8000) return false;
                return true;
            });

            renderCatalog(filtered);
        }

        function filterByBrand(brandName) {
            document.getElementById('filter-brand').value = brandName;
            applyFilters();
            window.scrollTo({ top: 580, behavior: 'smooth' });
        }

        function searchCarCatalog(query) {
            const q = query.trim().toLowerCase();
            const filtered = carDatabase.filter(car => 
                car.name.toLowerCase().includes(q) || 
                car.brand.toLowerCase().includes(q) ||
                car.fuel.toLowerCase().includes(q)
            );
            renderCatalog(filtered);
        }

        function showCarDetailByName(carName) {
            const car = carDatabase.find(c => c.name === carName);
            if (!car) return;

            const backdrop = document.getElementById('modal-backdrop');
            const content = document.getElementById('modal-content');
            backdrop.classList.remove('hidden');

            const tax = Math.round(car.avgPrice * 0.07);

            content.innerHTML = `
                <div class="text-center pb-3 border-b border-slate-100">
                    <span class="text-[10px] font-bold bg-sky-100 text-acarive-600 px-2.5 py-0.5 rounded-full">${car.brand} · ${car.type}</span>
                    <h3 class="text-2xl font-black text-slate-900 mt-1">${car.name}</h3>
                    <p class="text-xs text-slate-500 mt-1 px-4">${car.feature}</p>
                </div>

                <div class="py-4 space-y-3 text-xs">
                    <div class="bg-slate-50 p-4 rounded-2xl border border-slate-100">
                        <span class="text-slate-400 font-bold text-[11px]">기준 평균 출고가</span>
                        <div class="text-2xl font-black text-acarive-700 mt-0.5">${car.avgPrice.toLocaleString()}만 원</div>
                        <p class="text-[11px] text-slate-500 mt-1">예상 트림 가격대: ${car.range}</p>
                    </div>

                    <div class="bg-white rounded-xl border border-slate-100 divide-y divide-slate-100 font-medium">
                        <div class="flex justify-between py-2 px-3">
                            <span class="text-slate-500">배기량 / 모터</span>
                            <span class="font-bold text-slate-800">${car.displacement}</span>
                        </div>
                        <div class="flex justify-between py-2 px-3">
                            <span class="text-slate-500">연료 방식</span>
                            <span class="font-bold text-slate-800">${car.fuel}</span>
                        </div>
                        <div class="flex justify-between py-2 px-3">
                            <span class="text-slate-500">복합 연비</span>
                            <span class="font-bold text-slate-800">${car.fuelEfficiency}</span>
                        </div>
                        <div class="flex justify-between py-2 px-3">
                            <span class="text-slate-500">예상 취등록세 (7%)</span>
                            <span class="font-bold text-acarive-600">약 ${tax.toLocaleString()}만 원</span>
                        </div>
                    </div>
                </div>

                <button onclick="closeModal()" class="w-full py-3 bg-acarive-700 hover:bg-acarive-800 text-white font-bold rounded-xl text-xs transition">
                    확인 완료
                </button>
            `;
        }

        function closeModal() {
            document.getElementById('modal-backdrop').classList.add('hidden');
        }

        // 모달 바깥 배경 클릭 시 닫기
        document.getElementById('modal-backdrop').addEventListener('click', function(e) {
            if (e.target === this) closeModal();
        });

        window.onload = function() {
            renderCatalog(carDatabase);
        };
    </script>
</body>
</html>
