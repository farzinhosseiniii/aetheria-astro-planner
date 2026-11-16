<!DOCTYPE html>
<html lang="fa" dir="rtl" class="dark">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AETHERIA | پلنر هوشمند نجومی و تحلیل هندسی رشد کسب‌وکار</title>
    <!-- فونت وزیرمتن برای تایپوگرافی لوکس فارسی و اعداد فارسی -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Vazirmatn:wght@200;300;400;500;600;700;800;900&display=swap" rel="stylesheet">
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- آیکون‌های Lucide -->
    <script src="https://unpkg.com/lucide@latest"></script>
    <!-- تنظیمات سفارشی Tailwind -->
    <script>
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    fontFamily: {
                        sans: ['Vazirmatn', 'sans-serif'],
                    },
                    colors: {
                        obsidian: '#090A0F',
                        deepnavy: '#10131D',
                        metallic: '#161A26',
                        gold: {
                            DEFAULT: '#D4AF37',
                            light: '#F3E5AB',
                            dark: '#997A15',
                            glow: 'rgba(212, 175, 55, 0.38)'
                        },
                        cyber: {
                            DEFAULT: '#00F0FF',
                            dim: 'rgba(0, 240, 255, 0.15)'
                        }
                    },
                    boxShadow: {
                        'gold-glow': '0 0 30px rgba(212, 175, 55, 0.22)',
                        'cyber-glow': '0 0 25px rgba(0, 240, 255, 0.18)',
                        'luxury': '0 25px 60px rgba(0, 0, 0, 0.7)'
                    }
                }
            }
        }
    </script>
    <style>
        * {
            font-family: 'Vazirmatn', sans-serif;
            box-sizing: border-box;
        }
        body {
            background-color: #090A0F;
            color: #E2E8F0;
            overflow-x: hidden;
            background-image: 
                radial-gradient(circle at 12% 12%, rgba(212, 175, 55, 0.07) 0%, transparent 35%),
                radial-gradient(circle at 88% 88%, rgba(0, 240, 255, 0.06) 0%, transparent 40%),
                linear-gradient(180deg, #090A0F 0%, #0F121C 100%);
        }

        /* الگوی هندسی پس‌زمینه ظریف */
        .sacred-bg-pattern {
            background-image: radial-gradient(rgba(212, 175, 55, 0.12) 1px, transparent 1px);
            background-size: 30px 30px;
        }

        /* کارت‌های شیشه‌ای متالیک لوکس */
        .luxury-card {
            background: linear-gradient(145deg, rgba(22, 26, 38, 0.85), rgba(13, 16, 24, 0.94));
            backdrop-filter: blur(18px);
            -webkit-backdrop-filter: blur(18px);
            border: 1px solid rgba(212, 175, 55, 0.24);
            box-shadow: 0 14px 35px -4px rgba(0, 0, 0, 0.65), inset 0 1px 0 0 rgba(243, 229, 171, 0.14);
            transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
            position: relative;
        }
        .luxury-card:hover {
            border-color: rgba(212, 175, 55, 0.48);
            box-shadow: 0 18px 45px -4px rgba(0, 0, 0, 0.8), 0 0 22px rgba(212, 175, 55, 0.15);
        }

        /* گوشه‌های هندسی برش‌خورده لوکس */
        .geo-corner::before, .geo-corner::after {
            content: '';
            position: absolute;
            width: 11px;
            height: 11px;
            border-color: #D4AF37;
            border-style: solid;
            pointer-events: none;
            opacity: 0.75;
        }
        .geo-corner::before {
            top: -1px;
            right: -1px;
            border-width: 2px 2px 0 0;
            border-top-right-radius: 0.75rem;
        }
        .geo-corner::after {
            bottom: -1px;
            left: -1px;
            border-width: 0 0 2px 2px;
            border-bottom-left-radius: 0.75rem;
        }

        /* متن طلایی گرادیان */
        .text-gold-gradient {
            background: linear-gradient(135deg, #F3E5AB 0%, #D4AF37 50%, #997A15 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        /* دکمه طلایی متالیک */
        .btn-gold {
            background: linear-gradient(135deg, #D4AF37 0%, #997A15 100%);
            color: #090A0F;
            font-weight: 700;
            box-shadow: 0 4px 20px rgba(212, 175, 55, 0.4), inset 0 1px 1px rgba(255, 255, 255, 0.45);
            transition: all 0.25s ease;
        }
        .btn-gold:hover {
            background: linear-gradient(135deg, #F3E5AB 0%, #D4AF37 100%);
            transform: translateY(-1px);
            box-shadow: 0 6px 26px rgba(212, 175, 55, 0.6);
        }
        .btn-gold:active {
            transform: translateY(0);
        }

        /* اسکرول‌بار سفارشی لوکس */
        ::-webkit-scrollbar {
            width: 6px;
            height: 6px;
        }
        ::-webkit-scrollbar-track {
            background: #090A0F;
        }
        ::-webkit-scrollbar-thumb {
            background: rgba(212, 175, 55, 0.38);
            border-radius: 9999px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: rgba(212, 175, 55, 0.7);
        }

        /* انیمیشن چرخش آرام اسطرلاب */
        @keyframes slowSpin {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }
        @keyframes slowSpinReverse {
            from { transform: rotate(360deg); }
            to { transform: rotate(0deg); }
        }
        .spin-slow {
            animation: slowSpin 130s linear infinite;
            transform-origin: center;
        }
        .spin-reverse-slow {
            animation: slowSpinReverse 100s linear infinite;
            transform-origin: center;
        }

        /* استایل چاپ گزارش مدیریتی */
        @media print {
            body {
                background: #FFFFFF !important;
                color: #111827 !important;
            }
            .no-print {
                display: none !important;
            }
            .luxury-card {
                background: #FFFFFF !important;
                border: 1px solid #D4AF37 !important;
                box-shadow: none !important;
                color: #111827 !important;
                break-inside: avoid;
            }
            .text-gold-gradient {
                background: none !important;
                -webkit-text-fill-color: #997A15 !important;
                color: #997A15 !important;
            }
            .text-slate-300, .text-slate-400, .text-gray-300 {
                color: #374151 !important;
            }
        }
    </style>
</head>
<body class="min-h-screen sacred-bg-pattern selection:bg-gold selection:text-obsidian">

    <!-- سیستم نوتیفیکیشن اختصاصی (جایگزین alert) -->
    <div id="toast-container" class="fixed bottom-5 left-5 z-50 flex flex-col gap-2 max-w-sm w-full pointer-events-none"></div>

    <!-- هدر اصلی و نوار کنترل کیهانی -->
    <header class="sticky top-0 z-40 border-b border-gold/20 bg-obsidian/92 backdrop-blur-xl no-print">
        <div class="max-w-[1600px] mx-auto px-4 sm:px-6 py-3 flex flex-wrap items-center justify-between gap-4">
            <!-- برند و لوگو هندسی -->
            <div class="flex items-center gap-3">
                <div class="relative w-11 h-11 flex items-center justify-center rounded-xl bg-gradient-to-br from-gold/20 to-deepnavy border border-gold/50 shadow-gold-glow">
                    <svg class="w-7 h-7 text-gold" viewBox="0 0 100 100" fill="none">
                        <polygon points="50,5 93,28 93,72 50,95 7,72 7,28" stroke="currentColor" stroke-width="3" fill="none"/>
                        <polygon points="50,15 84,75 16,75" stroke="#00F0FF" stroke-width="2" fill="none" opacity="0.85"/>
                        <polygon points="50,85 84,25 16,25" stroke="currentColor" stroke-width="2" fill="none"/>
                        <circle cx="50" cy="50" r="8" fill="#D4AF37"/>
                    </svg>
                </div>
                <div>
                    <div class="flex items-center gap-2">
                        <h1 class="text-xl sm:text-2xl font-black tracking-wide text-gold-gradient">AETHERIA</h1>
                        <span class="text-[10px] px-2.5 py-0.5 rounded-full bg-gold/15 text-gold-light border border-gold/30 font-semibold">IAU 13-SIGN ENGINE</span>
                    </div>
                    <p class="text-xs text-slate-400">پلنر هوشمند استراتژیک و تحلیل هندسی مبتنی بر نجوم واقعی</p>
                </div>
            </div>

            <!-- انتخابگر تاریخ و ساعت فعال برای تحلیل و پلن -->
            <div class="flex flex-wrap items-center gap-2 sm:gap-3 bg-deepnavy/90 px-3 py-2 rounded-2xl border border-gold/25">
                <div class="flex items-center gap-1.5 text-xs text-gold-light">
                    <i data-lucide="calendar-clock" class="w-4 h-4 text-gold"></i>
                    <span class="hidden sm:inline">تاریخ و ساعت تحلیل:</span>
                </div>
                <input type="date" id="target-date" class="bg-obsidian/90 border border-gold/30 rounded-xl px-2.5 py-1.5 text-xs text-slate-100 focus:outline-none focus:border-gold">
                <input type="time" id="target-time" class="bg-obsidian/90 border border-gold/30 rounded-xl px-2.5 py-1.5 text-xs text-slate-100 focus:outline-none focus:border-gold">
                <button onclick="setNowDateTime()" class="px-2.5 py-1.5 rounded-xl bg-gold/15 hover:bg-gold/25 text-gold text-xs font-medium border border-gold/30 transition" title="تنظیم به لحظه اکنون">
                    اکنون
                </button>
            </div>

            <!-- ناوبری تب‌های اصلی -->
            <nav class="flex items-center gap-1.5 bg-deepnavy/90 p-1.5 rounded-2xl border border-gold/20 overflow-x-auto max-w-full">
                <button onclick="switchTab('dashboard')" id="tab-btn-dashboard" class="tab-btn active flex items-center gap-1.5 px-3.5 py-2 rounded-xl text-xs font-bold transition bg-gold text-obsidian shadow-gold-glow">
                    <i data-lucide="compass" class="w-4 h-4"></i>
                    <span>داشبورد کیهانی و رشد</span>
                </button>
                <button onclick="switchTab('planner')" id="tab-btn-planner" class="tab-btn flex items-center gap-1.5 px-3.5 py-2 rounded-xl text-xs font-medium text-slate-300 hover:text-gold transition">
                    <i data-lucide="sparkles" class="w-4 h-4"></i>
                    <span>پلنر هوشمند نجومی</span>
                </button>
                <button onclick="switchTab('report')" id="tab-btn-report" class="tab-btn flex items-center gap-1.5 px-3.5 py-2 rounded-xl text-xs font-medium text-slate-300 hover:text-gold transition">
                    <i data-lucide="file-spreadsheet" class="w-4 h-4"></i>
                    <span>گزارش تحلیلی جامع</span>
                </button>
            </nav>
        </div>
    </header>

    <!-- نوار وضعیت سریع نجومی لحظه‌ای (Ticker) -->
    <div class="border-b border-gold/15 bg-deepnavy/70 backdrop-blur-md no-print">
        <div class="max-w-[1600px] mx-auto px-4 sm:px-6 py-2 flex flex-wrap items-center justify-between gap-3 text-xs">
            <div class="flex flex-wrap items-center gap-4">
                <span class="flex items-center gap-1.5 text-slate-300">
                    <span class="w-2 h-2 rounded-full bg-cyber animate-pulse"></span>
                    <strong class="text-gold-light">تقویم:</strong>
                    <span id="header-persian-date" class="text-slate-200">--</span>
                </span>
                <span class="text-gold/40">|</span>
                <span class="flex items-center gap-1.5 text-slate-300">
                    <i data-lucide="sun" class="w-3.5 h-3.5 text-gold"></i>
                    <strong class="text-gold-light">خورشید نجومی (IAU):</strong>
                    <span id="header-sun-sign" class="text-cyber font-semibold">--</span>
                </span>
                <span class="text-gold/40">|</span>
                <span class="flex items-center gap-1.5 text-slate-300">
                    <i data-lucide="moon" class="w-3.5 h-3.5 text-cyber"></i>
                    <strong class="text-gold-light">برج قمر و فاز:</strong>
                    <span id="header-moon-sign" class="text-slate-200">--</span>
                </span>
                <span class="text-gold/40">|</span>
                <span class="flex items-center gap-1.5 text-slate-300">
                    <i data-lucide="hourglass" class="w-3.5 h-3.5 text-gold"></i>
                    <strong class="text-gold-light">ساعت کوکب حاکم:</strong>
                    <span id="header-planetary-hour" class="text-gold font-bold">--</span>
                </span>
            </div>
            <div id="scorpio-moon-badge" class="hidden items-center gap-1.5 px-2.5 py-0.5 rounded-full bg-red-500/20 border border-red-500/50 text-red-300 font-semibold animate-pulse">
                <i data-lucide="alert-triangle" class="w-3.5 h-3.5"></i>
                <span>هشدار نجومی: قمر در صورت فلکی عقرب</span>
            </div>
        </div>
    </div>

    <!-- محتوای اصلی اپلیکیشن -->
    <main class="max-w-[1600px] mx-auto px-4 sm:px-6 py-6 space-y-6">

        <!-- بخش ۱: داشبورد کیهانی و نمودارهای هندسی (TAB 1) -->
        <section id="view-dashboard" class="space-y-6">
            
            <!-- ردیف اول: پروفایل تولد کاربر + شاخص‌های کلیدی عملکرد (KPIs) -->
            <div class="grid grid-cols-1 lg:grid-cols-12 gap-6">
                
                <!-- کارت تنظیمات پروفایل نجومی کاربر -->
                <div class="lg:col-span-5 luxury-card geo-corner rounded-2xl p-5 flex flex-col justify-between">
                    <div>
                        <div class="flex items-center justify-between mb-4">
                            <div class="flex items-center gap-2">
                                <div class="p-2 rounded-xl bg-gold/15 border border-gold/30 text-gold">
                                    <i data-lucide="user-check" class="w-5 h-5"></i>
                                </div>
                                <div>
                                    <h2 class="text-base font-bold text-gold-light">پروفایل نجومی و مختصات جغرافیایی</h2>
                                    <p class="text-[11px] text-slate-400">مبنای محاسبه چارت زایچه (Natal) و ترانزیت‌های شخصی</p>
                                </div>
                            </div>
                            <span id="user-natal-sun-badge" class="px-2.5 py-1 rounded-xl bg-cyber/10 border border-cyber/40 text-cyber text-xs font-bold">
                                --
                            </span>
                        </div>

                        <div class="grid grid-cols-1 sm:grid-cols-2 gap-3 text-xs">
                            <div>
                                <label class="block text-slate-400 mb-1">نام / عنوان کسب‌وکار</label>
                                <input type="text" id="profile-name" value="آرش رادمنش | استودیو آلفا" class="w-full bg-obsidian/90 border border-gold/25 rounded-xl px-3 py-2 text-slate-100 focus:outline-none focus:border-gold">
                            </div>
                            <div>
                                <label class="block text-slate-400 mb-1">شهر محل تولد / فعالیت</label>
                                <select id="profile-city" class="w-full bg-obsidian/90 border border-gold/25 rounded-xl px-3 py-2 text-slate-100 focus:outline-none focus:border-gold">
                                    <option value="35.6892,51.3890,تهران">تهران (35.69°N, 51.39°E)</option>
                                    <option value="32.6546,51.6680,اصفهان">اصفهان (32.65°N, 51.67°E)</option>
                                    <option value="29.5918,52.5837,شیراز">شیراز (29.59°N, 52.58°E)</option>
                                    <option value="36.2605,59.6168,مشهد">مشهد (36.26°N, 59.62°E)</option>
                                    <option value="38.0962,46.2738,تبریز">تبریز (38.10°N, 46.27°E)</option>
                                    <option value="25.2048,55.2708,دبی">دبی (25.20°N, 55.27°E)</option>
                                    <option value="48.8566,2.3522,پاریس">پاریس (48.86°N, 2.35°E)</option>
                                    <option value="51.5074,-0.1278,لندن">لندن (51.51°N, 0.13°W)</option>
                                </select>
                            </div>
                            <div>
                                <label class="block text-slate-400 mb-1">تاریخ تولد (میلادی)</label>
                                <input type="date" id="birth-date" value="1992-12-05" class="w-full bg-obsidian/90 border border-gold/25 rounded-xl px-3 py-2 text-slate-100 focus:outline-none focus:border-gold">
                                <span id="birth-jalali-display" class="text-[10px] text-gold-light mt-1 block">معادل شمسی: ۱۴ آذر ۱۳۷۱</span>
                            </div>
                            <div>
                                <label class="block text-slate-400 mb-1">ساعت دقیق تولد</label>
                                <div class="flex gap-2">
                                    <input type="time" id="birth-time" value="08:45" class="w-full bg-obsidian/90 border border-gold/25 rounded-xl px-3 py-2 text-slate-100 focus:outline-none focus:border-gold">
                                    <button onclick="saveProfileAndRecalculate()" class="btn-gold px-4 py-2 rounded-xl text-xs whitespace-nowrap">
                                        بروزرسانی
                                    </button>
                                </div>
                            </div>
                        </div>
                    </div>

                    <!-- خلاصه سیارات شخصی -->
                    <div class="mt-4 pt-3 border-t border-gold/15 grid grid-cols-3 gap-2 text-center">
                        <div class="bg-obsidian/70 p-2 rounded-xl border border-gold/15">
                            <span class="text-[10px] text-slate-400 block">خورشید زایچه (IAU)</span>
                            <span id="natal-sun-text" class="text-xs font-bold text-gold-light">--</span>
                        </div>
                        <div class="bg-obsidian/70 p-2 rounded-xl border border-gold/15">
                            <span class="text-[10px] text-slate-400 block">قمر زایچه</span>
                            <span id="natal-moon-text" class="text-xs font-bold text-cyber">--</span>
                        </div>
                        <div class="bg-obsidian/70 p-2 rounded-xl border border-gold/15">
                            <span class="text-[10px] text-slate-400 block">طالع (Ascendant)</span>
                            <span id="natal-asc-text" class="text-xs font-bold text-gold">--</span>
                        </div>
                    </div>
                </div>

                <!-- ۴ کارت شاخص‌های کلیدی رشد و هم‌راستایی کیهانی -->
                <div class="lg:col-span-7 grid grid-cols-2 sm:grid-cols-4 gap-4">
                    <!-- KPI 1 -->
                    <div class="luxury-card geo-corner rounded-2xl p-4 flex flex-col justify-between">
                        <div class="flex items-center justify-between">
                            <span class="text-xs text-slate-400">نرخ تکمیل اهداف</span>
                            <div class="p-2 rounded-xl bg-gold/15 text-gold">
                                <i data-lucide="target" class="w-4 h-4"></i>
                            </div>
                        </div>
                        <div class="my-3">
                            <div id="kpi-completion" class="text-2xl sm:text-3xl font-black text-gold-gradient">۰٪</div>
                            <p id="kpi-tasks-count" class="text-[11px] text-slate-400 mt-1">۰ از ۰ تسک تکمیل شده</p>
                        </div>
                        <div class="w-full bg-obsidian rounded-full h-1.5 overflow-hidden border border-gold/20">
                            <div id="kpi-completion-bar" class="bg-gradient-to-l from-gold-light to-gold h-full transition-all duration-500" style="width: 0%"></div>
                        </div>
                    </div>

                    <!-- KPI 2 -->
                    <div class="luxury-card geo-corner rounded-2xl p-4 flex flex-col justify-between">
                        <div class="flex items-center justify-between">
                            <span class="text-xs text-slate-400">هم‌راستایی کیهانی</span>
                            <div class="p-2 rounded-xl bg-cyber/15 text-cyber">
                                <i data-lucide="orbit" class="w-4 h-4"></i>
                            </div>
                        </div>
                        <div class="my-3">
                            <div id="kpi-cosmic-score" class="text-2xl sm:text-3xl font-black text-cyber">۸۴٪</div>
                            <p id="kpi-cosmic-status" class="text-[11px] text-slate-400 mt-1">فاز صعودی استراتژیک</p>
                        </div>
                        <div class="text-[10px] text-cyber/90 bg-cyber/10 px-2 py-1 rounded-lg border border-cyber/20 text-center">
                            تثلیث مشتری و خورشید
                        </div>
                    </div>

                    <!-- KPI 3 -->
                    <div class="luxury-card geo-corner rounded-2xl p-4 flex flex-col justify-between">
                        <div class="flex items-center justify-between">
                            <span class="text-xs text-slate-400">شاخص رشد فیبوناچی</span>
                            <div class="p-2 rounded-xl bg-gold/15 text-gold">
                                <i data-lucide="trending-up" class="w-4 h-4"></i>
                            </div>
                        </div>
                        <div class="my-3">
                            <div id="kpi-phi-index" class="text-2xl sm:text-3xl font-black text-gold-gradient">۱.۶۱۸</div>
                            <p class="text-[11px] text-slate-400 mt-1">شتاب بهره‌وری ترکیبی</p>
                        </div>
                        <div class="text-[10px] text-gold-light bg-gold/10 px-2 py-1 rounded-lg border border-gold/20 text-center">
                            نسبت طلایی فعال است
                        </div>
                    </div>

                    <!-- KPI 4 -->
                    <div class="luxury-card geo-corner rounded-2xl p-4 flex flex-col justify-between">
                        <div class="flex items-center justify-between">
                            <span class="text-xs text-slate-400">پنجره طلایی امروز</span>
                            <div class="p-2 rounded-xl bg-emerald-500/15 text-emerald-400">
                                <i data-lucide="zap" class="w-4 h-4"></i>
                            </div>
                        </div>
                        <div class="my-3">
                            <div id="kpi-golden-window" class="text-lg sm:text-xl font-black text-emerald-400">۱۰:۳۰ - ۱۲:۰۰</div>
                            <p id="kpi-golden-planet" class="text-[11px] text-slate-400 mt-1">ساعت کوکب مشتری</p>
                        </div>
                        <div class="text-[10px] text-emerald-300 bg-emerald-500/10 px-2 py-1 rounded-lg border border-emerald-500/20 text-center">
                            اوج عقد قرارداد و توسعه
                        </div>
                    </div>
                </div>
            </div>

            <!-- ردیف دوم: اسطرلاب نجومی ۱۳ صورت فلکی IAU + جدول کواکب و زوایا -->
            <div class="grid grid-cols-1 xl:grid-cols-12 gap-6">
                
                <!-- اسطرلاب هندسی سه‌بعدی و چارت ۱۳ صورت فلکی IAU -->
                <div class="xl:col-span-7 luxury-card geo-corner rounded-2xl p-5">
                    <div class="flex flex-wrap items-center justify-between gap-2 mb-4">
                        <div>
                            <h3 class="text-base sm:text-lg font-bold text-gold-light flex items-center gap-2">
                                <i data-lucide="compass" class="w-5 h-5 text-gold"></i>
                                اسطرلاب هندسی ۱۳ صورت فلکی واقعی (IAU Sidereal Wheel)
                            </h3>
                            <p class="text-xs text-slate-400">نمایش زنده موقعیت اجرام سماوی (شامل مارافسای / Ophiuchus) و خطوط زوایای کیهانی</p>
                        </div>
                        <div class="flex items-center gap-2 text-[11px]">
                            <span class="flex items-center gap-1 text-emerald-400"><span class="w-2.5 h-0.5 bg-emerald-400 inline-block"></span> تثلیث/تسدیس</span>
                            <span class="flex items-center gap-1 text-rose-400"><span class="w-2.5 h-0.5 bg-rose-400 inline-block"></span> تربیع/مقابله</span>
                            <span class="flex items-center gap-1 text-gold"><span class="w-2.5 h-0.5 bg-gold inline-block"></span> مقارنه</span>
                        </div>
                    </div>

                    <div class="grid grid-cols-1 md:grid-cols-12 gap-4 items-center">
                        <!-- بوم SVG اسطرلاب -->
                        <div class="md:col-span-8 flex items-center justify-center relative">
                            <div id="astrolabe-container" class="w-full max-w-[440px] aspect-square relative flex items-center justify-center">
                                <!-- SVG توسط جاوااسکریپت رندر می‌شود -->
                            </div>
                        </div>

                        <!-- پنل جزئیات اجرام سماوی و زوایا -->
                        <div class="md:col-span-4 space-y-2.5">
                            <div class="text-xs font-bold text-gold border-b border-gold/20 pb-1.5 flex items-center justify-between">
                                <span>موقعیت لحظه‌ای اجرام</span>
                                <span class="text-[10px] text-slate-400">نجومی (IAU)</span>
                            </div>
                            <div id="planets-list" class="space-y-1.5 max-h-[250px] overflow-y-auto pr-1 text-xs">
                                <!-- لیست کواکب توسط JS پر می‌شود -->
                            </div>

                            <div class="text-xs font-bold text-cyber border-b border-cyber/20 pb-1.5 pt-2">
                                زوایای فعال (Aspects)
                            </div>
                            <div id="aspects-list" class="space-y-1 max-h-[120px] overflow-y-auto pr-1 text-[11px]">
                                <!-- لیست زوایا توسط JS پر می‌شود -->
                            </div>
                        </div>
                    </div>
                </div>

                <!-- نمودار رادار چندضلعی طلایی (Sacred Octagonal Growth Radar) -->
                <div class="xl:col-span-5 luxury-card geo-corner rounded-2xl p-5 flex flex-col justify-between">
                    <div>
                        <div class="flex items-center justify-between mb-2">
                            <div>
                                <h3 class="text-base sm:text-lg font-bold text-gold-light flex items-center gap-2">
                                    <i data-lucide="hexagon" class="w-5 h-5 text-gold"></i>
                                    هندسه تعادل و رشد کاری (Sacred Radar)
                                </h3>
                                <p class="text-xs text-slate-400">تحلیل شش‌ضلعی مقدس عملکرد فعلی در برابر پتانسیل نجومی</p>
                            </div>
                        </div>
                        <div class="flex items-center justify-center gap-4 text-[11px] my-2">
                            <span class="flex items-center gap-1.5 text-gold-light">
                                <span class="w-3 h-3 rounded-sm bg-gold/40 border border-gold inline-block"></span>
                                عملکرد واقعی تسک‌ها
                            </span>
                            <span class="flex items-center gap-1.5 text-cyber">
                                <span class="w-3 h-3 rounded-sm bg-cyber/20 border border-cyber border-dashed inline-block"></span>
                                پتانسیل کیهانی روز
                            </span>
                        </div>
                    </div>

                    <div id="radar-chart-container" class="w-full flex items-center justify-center my-2">
                        <!-- SVG نمودار رادار شش‌ضلعی -->
                    </div>

                    <!-- خلاصه امتیاز ابعاد شش‌گانه -->
                    <div id="radar-metrics-grid" class="grid grid-cols-3 gap-2 text-center text-[11px] pt-2 border-t border-gold/15">
                        <!-- توسط JS پر می‌شود -->
                    </div>
                </div>
            </div>

            <!-- ردیف سوم: مارپیچ فیبوناچی رشد + ماتریس ساعات کواکب (Planetary Hours) -->
            <div class="grid grid-cols-1 xl:grid-cols-12 gap-6">
                
                <!-- نمودار مارپیچ فیبوناچی و رشد تجمعی (Golden Ratio Spiral) -->
                <div class="xl:col-span-5 luxury-card geo-corner rounded-2xl p-5 flex flex-col justify-between">
                    <div>
                        <h3 class="text-base sm:text-lg font-bold text-gold-light flex items-center gap-2">
                            <i data-lucide="shell" class="w-5 h-5 text-gold"></i>
                            مارپیچ فیبوناچی و شتاب رشد تجمعی (φ = 1.618)
                        </h3>
                        <p class="text-xs text-slate-400">مدل‌سازی هندسی تکامل پروژه‌ها در ۷ فاز طلایی بر اساس نرخ پیشرفت</p>
                    </div>

                    <div id="fibonacci-chart-container" class="w-full flex items-center justify-center my-3">
                        <!-- SVG مارپیچ طلایی -->
                    </div>

                    <div class="bg-obsidian/80 rounded-xl p-3 border border-gold/20 text-xs flex items-center justify-between">
                        <div>
                            <span class="text-slate-400 block text-[11px]">مرحله فعلی مارپیچ رشد:</span>
                            <span id="fib-stage-name" class="text-gold-light font-bold">فاز ۵: گسترش شبکه و تثبیت درآمد (۸ واحد فیبوناچی)</span>
                        </div>
                        <span id="fib-growth-percent" class="px-3 py-1 rounded-xl bg-gold/20 text-gold font-black text-sm">+۶۸٪</span>
                    </div>
                </div>

                <!-- ماتریس هندسی ساعات کواکب واقعی (Planetary Hours) -->
                <div class="xl:col-span-7 luxury-card geo-corner rounded-2xl p-5">
                    <div class="flex flex-wrap items-center justify-between gap-2 mb-4">
                        <div>
                            <h3 class="text-base sm:text-lg font-bold text-gold-light flex items-center gap-2">
                                <i data-lucide="clock" class="w-5 h-5 text-gold"></i>
                                ماتریس هندسی ساعات کواکب و بهره‌وری (Planetary Hours)
                            </h3>
                            <p class="text-xs text-slate-400">محاسبه دقیق ساعات نجومی از طلوع تا غروب خورشید بر اساس مختصات شهر انتخابی</p>
                        </div>
                        <div class="flex items-center gap-3 text-xs bg-obsidian/80 px-3 py-1.5 rounded-xl border border-gold/20">
                            <span class="text-amber-300 flex items-center gap-1"><i data-lucide="sunrise" class="w-3.5 h-3.5"></i> طلوع: <strong id="sunrise-time">06:42</strong></span>
                            <span class="text-indigo-300 flex items-center gap-1"><i data-lucide="sunset" class="w-3.5 h-3.5"></i> غروب: <strong id="sunset-time">17:04</strong></span>
                        </div>
                    </div>

                    <!-- نمودار چندضلعی انرژی ساعتی + گرید ساعات کواکب -->
                    <div class="grid grid-cols-1 md:grid-cols-12 gap-4 items-center">
                        <div class="md:col-span-5 flex flex-col items-center justify-center">
                            <div id="hourly-polygon-container" class="w-full max-w-[260px] aspect-square flex items-center justify-center">
                                <!-- SVG چندضلعی انرژی ساعتی -->
                            </div>
                            <p class="text-[11px] text-center text-slate-400 mt-1">نمودار شعاعی توان اجرایی ۲۴ ساعت نجومی</p>
                        </div>

                        <div class="md:col-span-7">
                            <div class="flex items-center justify-between text-[11px] text-slate-400 mb-2">
                                <span>ساعات روزانه (طلوع تا غروب)</span>
                                <span class="text-gold">روی هر ساعت کلیک کنید تا زمان تحلیل تنظیم شود</span>
                            </div>
                            <div id="planetary-hours-grid" class="grid grid-cols-2 sm:grid-cols-3 gap-2 max-h-[260px] overflow-y-auto pr-1">
                                <!-- کارت‌های ساعات کواکب توسط JS پر می‌شود -->
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- بخش ۲: برنامه‌ریز هوشمند و پیشنهادگر خودکار نجومی (TAB 2) -->
        <section id="view-planner" class="hidden space-y-6">
            
            <!-- بنر مولد پلن هوشمند نجومی -->
            <div class="luxury-card geo-corner rounded-2xl p-6 bg-gradient-to-l from-deepnavy via-metallic to-obsidian border-gold/40">
                <div class="flex flex-col lg:flex-row items-start lg:items-center justify-between gap-4">
                    <div class="space-y-1.5 max-w-3xl">
                        <div class="inline-flex items-center gap-1.5 px-3 py-1 rounded-full bg-gold/15 border border-gold/30 text-gold text-xs font-bold">
                            <i data-lucide="sparkles" class="w-3.5 h-3.5"></i>
                            <span>موتور پیشنهادگر استراتژیک مبتنی بر ترانزیت‌های نجومی</span>
                        </div>
                        <h2 class="text-xl sm:text-2xl font-black text-gold-light">تولید خودکار برنامه روزانه منطبق با انرژی کواکب</h2>
                        <p id="astro-planner-advice" class="text-xs sm:text-sm text-slate-300 leading-relaxed">
                            بر اساس قرارگیری خورشید در صورت فلکی واقعی و زاویه هماهنگ عطارد و مشتری، امروز بهترین زمان برای تدوین استراتژی، مذاکرات کلان مالی و توسعه محصول است.
                        </p>
                    </div>
                    <div class="flex flex-wrap items-center gap-3 w-full lg:w-auto">
                        <button onclick="generateSmartAstroPlan()" class="btn-gold px-5 py-3 rounded-xl text-xs sm:text-sm flex items-center justify-center gap-2 w-full sm:w-auto">
                            <i data-lucide="wand-2" class="w-4 h-4"></i>
                            <span>تولید پلن هوشمند نجومی برای این تاریخ</span>
                        </button>
                    </div>
                </div>

                <!-- کانتینر پیشنهادهای تولید شده (پس از کلیک نمایش داده می‌شود) -->
                <div id="suggested-plan-box" class="hidden mt-5 pt-5 border-t border-gold/25">
                    <div class="flex flex-wrap items-center justify-between gap-2 mb-3">
                        <h3 class="text-sm font-bold text-cyber flex items-center gap-2">
                            <i data-lucide="cpu" class="w-4 h-4"></i>
                            <span>برنامه پیشنهادی بهینه‌شده بر اساس ساعات کواکب:</span>
                        </h3>
                        <button onclick="acceptAllSuggestedTasks()" class="px-3.5 py-1.5 rounded-xl bg-cyber/20 hover:bg-cyber/30 text-cyber border border-cyber/40 text-xs font-bold transition flex items-center gap-1.5">
                            <i data-lucide="check-check" class="w-4 h-4"></i>
                            <span>افزودن همه به برنامه من</span>
                        </button>
                    </div>
                    <div id="suggested-tasks-grid" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-3">
                        <!-- پیشنهادهای هوشمند -->
                    </div>
                </div>
            </div>

            <!-- فرم افزودن تسک جدید + لیست تسک‌های اجرایی -->
            <div class="grid grid-cols-1 lg:grid-cols-12 gap-6">
                
                <!-- فرم افزودن تسک و پروژه -->
                <div class="lg:col-span-4 luxury-card geo-corner rounded-2xl p-5 h-fit">
                    <h3 class="text-base font-bold text-gold-light mb-4 flex items-center gap-2">
                        <i data-lucide="plus-circle" class="w-5 h-5 text-gold"></i>
                        <span>ثبت هدف یا تسک جدید</span>
                    </h3>
                    <form id="task-form" onsubmit="handleAddTask(event)" class="space-y-3 text-xs">
                        <div>
                            <label class="block text-slate-400 mb-1">عنوان تسک یا اقدام اجرایی *</label>
                            <input type="text" id="task-title" required placeholder="مثال: جلسه عقد قرارداد سرمایه‌گذاری سری A" class="w-full bg-obsidian/90 border border-gold/25 rounded-xl px-3 py-2.5 text-slate-100 focus:outline-none focus:border-gold">
                        </div>
                        <div class="grid grid-cols-2 gap-2.5">
                            <div>
                                <label class="block text-slate-400 mb-1">حوزه رشد (بُعد هندسی)</label>
                                <select id="task-category" class="w-full bg-obsidian/90 border border-gold/25 rounded-xl px-3 py-2.5 text-slate-100 focus:outline-none focus:border-gold">
                                    <option value="strategy">استراتژی و رهبری</option>
                                    <option value="execution">اجرای پروژه و عملیات</option>
                                    <option value="finance">فروش، مالی و قرارداد</option>
                                    <option value="creativity">خلاقیت و نوآوری</option>
                                    <option value="network">شبکه‌سازی و ارتباطات</option>
                                    <option value="energy">مدیریت زمان و انرژی</option>
                                </select>
                            </div>
                            <div>
                                <label class="block text-slate-400 mb-1">درجه اولویت</label>
                                <select id="task-priority" class="w-full bg-obsidian/90 border border-gold/25 rounded-xl px-3 py-2.5 text-slate-100 focus:outline-none focus:border-gold">
                                    <option value="critical">بحرانی و طلایی (S-Tier)</option>
                                    <option value="high">بالا (High)</option>
                                    <option value="medium">متوسط (Medium)</option>
                                </select>
                            </div>
                        </div>
                        <div class="grid grid-cols-3 gap-2">
                            <div>
                                <label class="block text-slate-400 mb-1">تاریخ</label>
                                <input type="date" id="task-date" required class="w-full bg-obsidian/90 border border-gold/25 rounded-xl px-2 py-2 text-slate-100 focus:outline-none focus:border-gold">
                            </div>
                            <div>
                                <label class="block text-slate-400 mb-1">شروع</label>
                                <input type="time" id="task-start" value="09:00" required class="w-full bg-obsidian/90 border border-gold/25 rounded-xl px-2 py-2 text-slate-100 focus:outline-none focus:border-gold">
                            </div>
                            <div>
                                <label class="block text-slate-400 mb-1">پایان</label>
                                <input type="time" id="task-end" value="10:30" required class="w-full bg-obsidian/90 border border-gold/25 rounded-xl px-2 py-2 text-slate-100 focus:outline-none focus:border-gold">
                            </div>
                        </div>
                        <div>
                            <label class="block text-slate-400 mb-1">توضیحات تکمیلی و شاخص موفقیت</label>
                            <textarea id="task-notes" rows="2" placeholder="جزئیات کلیدی، خروجی مورد انتظار..." class="w-full bg-obsidian/90 border border-gold/25 rounded-xl px-3 py-2 text-slate-100 focus:outline-none focus:border-gold"></textarea>
                        </div>
                        <button type="submit" class="btn-gold w-full py-2.5 rounded-xl text-xs font-bold flex items-center justify-center gap-2 mt-2">
                            <i data-lucide="plus" class="w-4 h-4"></i>
                            <span>ثبت در ماتریس اجرایی</span>
                        </button>
                    </form>
                </div>

                <!-- لیست تسک‌ها و فیلترها -->
                <div class="lg:col-span-8 luxury-card geo-corner rounded-2xl p-5">
                    <div class="flex flex-wrap items-center justify-between gap-3 mb-4 pb-3 border-b border-gold/15">
                        <div>
                            <h3 class="text-base font-bold text-gold-light flex items-center gap-2">
                                <i data-lucide="list-checks" class="w-5 h-5 text-gold"></i>
                                <span>ماتریس تسک‌ها و زمان‌بندی کیهانی</span>
                            </h3>
                            <p class="text-[11px] text-slate-400">هر تسک به‌صورت خودکار با کوکب حاکم بر ساعت شروع تطبیق داده می‌شود</p>
                        </div>
                        <div class="flex items-center gap-1.5 text-xs">
                            <button onclick="filterTasks('all')" class="filter-btn active px-3 py-1.5 rounded-xl bg-gold/20 text-gold border border-gold/40 font-semibold">همه</button>
                            <button onclick="filterTasks('in_progress')" class="filter-btn px-3 py-1.5 rounded-xl bg-obsidian text-slate-400 border border-gold/15 hover:text-gold">در حال اجرا</button>
                            <button onclick="filterTasks('pending')" class="filter-btn px-3 py-1.5 rounded-xl bg-obsidian text-slate-400 border border-gold/15 hover:text-gold">در انتظار</button>
                            <button onclick="filterTasks('completed')" class="filter-btn px-3 py-1.5 rounded-xl bg-obsidian text-slate-400 border border-gold/15 hover:text-gold">تکمیل‌شده</button>
                        </div>
                    </div>

                    <div id="tasks-list-container" class="space-y-3 max-h-[540px] overflow-y-auto pr-1">
                        <!-- کارت‌های تسک توسط JS رندر می‌شوند -->
                    </div>
                </div>
            </div>
        </section>

        <!-- بخش ۳: سیستم گزارش‌نویس تحلیلی دقیق (TAB 3) -->
        <section id="view-report" class="hidden space-y-6">
            
            <!-- نوار ابزار گزارش مدیریتی -->
            <div class="luxury-card geo-corner rounded-2xl p-5 flex flex-wrap items-center justify-between gap-4 no-print">
                <div>
                    <h2 class="text-lg sm:text-xl font-black text-gold-gradient flex items-center gap-2">
                        <i data-lucide="file-check-2" class="w-6 h-6 text-gold"></i>
                        <span>گزارش تحلیلی جامع عملکرد و استراتژی نجومی</span>
                    </h2>
                    <p class="text-xs text-slate-400 mt-0.5">ترکیب داده‌های کمی بهره‌وری با محاسبات نجومی IAU، تحلیل SWOT و نقشه راه ۷ روز آینده</p>
                </div>
                <div class="flex flex-wrap items-center gap-2.5">
                    <button onclick="generateExecutiveReport()" class="px-4 py-2.5 rounded-xl bg-cyber/15 hover:bg-cyber/25 text-cyber border border-cyber/40 text-xs font-bold flex items-center gap-1.5 transition">
                        <i data-lucide="refresh-cw" class="w-4 h-4"></i>
                        <span>بازتولید تحلیل زنده</span>
                    </button>
                    <button onclick="copyReportToClipboard()" class="px-4 py-2.5 rounded-xl bg-gold/15 hover:bg-gold/25 text-gold border border-gold/40 text-xs font-bold flex items-center gap-1.5 transition">
                        <i data-lucide="copy" class="w-4 h-4"></i>
                        <span>کپی متن گزارش</span>
                    </button>
                    <button onclick="window.print()" class="btn-gold px-4 py-2.5 rounded-xl text-xs font-bold flex items-center gap-1.5">
                        <i data-lucide="printer" class="w-4 h-4"></i>
                        <span>چاپ / ذخیره PDF</span>
                    </button>
                </div>
            </div>

            <!-- بدنه اصلی گزارش مدیریتی -->
            <div id="executive-report-content" class="space-y-6">
                <!-- محتوای گزارش توسط JS به‌صورت پویا و بسیار دقیق تولید می‌شود -->
            </div>
        </section>

    </main>

    <!-- فوتر لوکس -->
    <footer class="border-t border-gold/15 bg-obsidian/92 py-4 mt-12 no-print">
        <div class="max-w-[1600px] mx-auto px-4 sm:px-6 flex flex-col sm:flex-row items-center justify-between gap-2 text-[11px] text-slate-500">
            <div class="flex items-center gap-2">
                <span class="text-gold font-bold">AETHERIA COSMIC ANALYTICS</span>
                <span>•</span>
                <span>مبتنی بر مختصات نجومی واقعی ۱۳ صورت فلکی (IAU Sidereal) و هندسه مقدس فیبوناچی</span>
            </div>
            <div>
                تمامی داده‌ها به‌صورت امن در حافظه محلی مرورگر (LocalStorage) ذخیره می‌شوند.
            </div>
        </div>
    </footer>

    <!-- اسکریپت کامل هسته نجومی، هندسی و مدیریتی -->
    <script>
        // ============================================================================
        // ۱. تعاریف و ثابت‌های نجومی (IAU 13-Sign Sidereal Zodiac & Planetary Hours)
        // ============================================================================
        
        // ۱۳ صورت فلکی واقعی نجومی طبق مرزهای اتحادیه بین‌المللی نجوم (IAU)
        const IAU_CONSTELLATIONS = [
            { id: 'aries', name: 'حمل (Aries)', symbol: '♈', startDeg: 28.7, endDeg: 53.4, element: 'آتش', ruler: 'مریخ', traits: 'آغازگری، جسارت، تصمیم‌گیری سریع' },
            { id: 'taurus', name: 'ثور (Taurus)', symbol: '♉', startDeg: 53.4, endDeg: 90.1, element: 'خاک', ruler: 'زهره', traits: 'تثبیت سرمایه، ثبات، ارزش‌آفرینی ملموس' },
            { id: 'gemini', name: 'جوزا (Gemini)', symbol: '♊', startDeg: 90.1, endDeg: 118.0, element: 'هوا', ruler: 'عطارد', traits: 'مذاکره، بازاریابی، شبکه‌سازی و ارتباطات' },
            { id: 'cancer', name: 'سرطان (Cancer)', symbol: '♋', startDeg: 118.0, endDeg: 138.0, element: 'آب', ruler: 'قمر', traits: 'حمایت از تیم، هوش هیجانی، برندسازی عاطفی' },
            { id: 'leo', name: 'اسد (Leo)', symbol: '♌', startDeg: 138.0, endDeg: 173.9, element: 'آتش', ruler: 'خورشید', traits: 'رهبری، ارائه پرقدرت، دیده‌شدن و خلاقیت' },
            { id: 'virgo', name: 'سنبله (Virgo)', symbol: '♍', startDeg: 173.9, endDeg: 217.8, element: 'خاک', ruler: 'عطارد', traits: 'تحلیل داده، بهینه‌سازی فرآیندها، دقت فنی' },
            { id: 'libra', name: 'میزان (Libra)', symbol: '♎', startDeg: 217.8, endDeg: 241.0, element: 'هوا', ruler: 'زهره', traits: 'عقد قرارداد، شراکت استراتژیک، دیپلماسی' },
            { id: 'scorpius', name: 'عقرب (Scorpius)', symbol: '♏', startDeg: 241.0, endDeg: 247.7, element: 'آب', ruler: 'مریخ/پلوتو', traits: 'تحول عمیق، مدیریت بحران، استراتژی پنهان' },
            { id: 'ophiuchus', name: 'مارافسای (Ophiuchus)', symbol: '⛎', startDeg: 247.7, endDeg: 266.2, element: 'اتر/آتش', ruler: 'کایرون/مشتری', traits: 'دانش نخبگانی، التیام سیستم‌ها، حکمت و نوآوری ساختارشکن' },
            { id: 'sagittarius', name: 'قوس (Sagittarius)', symbol: '♐', startDeg: 266.2, endDeg: 299.7, element: 'آتش', ruler: 'مشتری', traits: 'توسعه بین‌الملل، چشم‌انداز کلان، آموزش و رشد' },
            { id: 'capricornus', name: 'جدی (Capricornus)', symbol: '♑', startDeg: 299.7, endDeg: 327.5, element: 'خاک', ruler: 'زحل', traits: 'ساختارسازی، مدیریت اجرایی، انضباط و اهداف بلندمدت' },
            { id: 'aquarius', name: 'دلو (Aquarius)', symbol: '♒', startDeg: 327.5, endDeg: 351.5, element: 'هوا', ruler: 'اورانوس/زحل', traits: 'فناوری نوین، هوش مصنوعی، تفکر آینده‌نگر' },
            { id: 'pisces', name: 'حوت (Pisces)', symbol: '♓', startDeg: 351.5, endDeg: 388.7, element: 'آب', ruler: 'نپتون/مشتری', traits: 'شهود تجاری، چشم‌انداز هنری، هم‌افزایی معنوی' }
        ];

        // ترتیب کلدانی کواکب برای محاسبه ساعات کواکب (Chaldean Order)
        const CHALDEAN_PLANETS = [
            { id: 'saturn', name: 'زحل (Saturn)', symbol: '♄', color: '#94A3B8', energy: 62, bestFor: 'ساختارسازی، حسابرسی، امور حقوقی و برنامه‌ریزی بلندمدت', avoid: 'شروع پروژه‌های پرریسک هیجانی' },
            { id: 'jupiter', name: 'مشتری (Jupiter)', symbol: '♃', color: '#F59E0B', energy: 96, bestFor: 'عقد قراردادهای کلان، جذب سرمایه، توسعه بازار و تصمیم‌های استراتژیک', avoid: 'جزئی‌نگری بیش از حد و تردید' },
            { id: 'mars', name: 'مریخ (Mars)', symbol: '♂', color: '#EF4444', energy: 88, bestFor: 'اجرای سریع تسک‌های سخت، رقابت تجاری، فروش تهاجمی و رفع موانع', avoid: 'بحث‌های تنش‌زا با شرکا' },
            { id: 'sun', name: 'خورشید (Sun)', symbol: '☉', color: '#D4AF37', energy: 94, bestFor: 'جلسات مدیریتی، پرزنتیشن، برندینگ، مذاکره با مدیران ارشد', avoid: 'کارهای پشت‌صحنه و منزوی' },
            { id: 'venus', name: 'زهره (Venus)', symbol: '♀', color: '#EC4899', energy: 85, bestFor: 'طراحی محصول، بازاریابی، روابط عمومی، توافق و جذب مشتری', avoid: 'برخوردهای خشک و دستوری' },
            { id: 'mercury', name: 'عطارد (Mercury)', symbol: '☿', color: '#00F0FF', energy: 90, bestFor: 'تحلیل داده، کدنویسی، نگارش پروپوزال، مذاکره و مکاتبات', avoid: 'تصمیم‌گیری بدون بررسی مستندات' },
            { id: 'moon', name: 'قمر (Moon)', symbol: '☽', color: '#E2E8F0', energy: 70, bestFor: 'همدلی با تیم، ایده‌پردازی شهودی، بررسی نیاز مشتریان', avoid: 'امضای قراردادهای سنگین و قطعی' }
        ];

        // حاکم روزهای هفته (یکشنبه=خورشید ... شنبه=زحل)
        const DAY_RULERS = ['sun', 'moon', 'mars', 'mercury', 'jupiter', 'venus', 'saturn'];

        // ابعاد شش‌گانه هندسه رشد
        const GROWTH_DIMENSIONS = {
            strategy: { label: 'استراتژی و رهبری', short: 'استراتژی', icon: 'compass' },
            execution: { label: 'اجرای پروژه', short: 'اجرا', icon: 'cpu' },
            finance: { label: 'فروش و درآمد', short: 'مالی', icon: 'coins' },
            creativity: { label: 'خلاقیت و نوآوری', short: 'خلاقیت', icon: 'sparkles' },
            network: { label: 'شبکه ارتباطی', short: 'شبکه', icon: 'share-2' },
            energy: { label: 'مدیریت زمان و انرژی', short: 'انرژی', icon: 'battery-charging' }
        };

        // وضعیت سراسری اپلیکیشن
        let appState = {
            profile: {
                name: 'آرش رادمنش | استودیو آلفا',
                city: '35.6892,51.3890,تهران',
                birthDate: '1992-12-05',
                birthTime: '08:45'
            },
            targetDate: '',
            targetTime: '',
            tasks: [],
            currentFilter: 'all',
            suggestedTasks: [],
            astroData: null
        };

        // ============================================================================
        // ۲. موتور محاسبات نجومی دقیق (Sidereal Ephemeris & Sun/Moon Calculations)
        // ============================================================================

        // تبدیل تاریخ میلادی به شمسی دقیق
        function gregorianToJalali(gy, gm, gd) {
            const g_d_m = [0, 31, 59, 90, 120, 151, 181, 212, 243, 273, 304, 334];
            let gy2 = (gm > 2) ? (gy + 1) : gy;
            let days = 355666 + (365 * gy) + Math.floor((gy2 + 3) / 4) - Math.floor((gy2 + 99) / 100) + Math.floor((gy2 + 399) / 400) + gd + g_d_m[gm - 1];
            let jy = -1595 + (33 * Math.floor(days / 12053));
            days %= 12053;
            jy += 4 * Math.floor(days / 1461);
            days %= 1461;
            if (days > 365) {
                jy += Math.floor((days - 1) / 365);
                days = (days - 1) % 365;
            }
            let jm = (days < 186) ? 1 + Math.floor(days / 31) : 7 + Math.floor((days - 186) / 30);
            let jd = 1 + ((days < 186) ? (days % 31) : ((days - 186) % 30));
            const monthNames = ['فروردین', 'اردیبهشت', 'خرداد', 'تیر', 'مرداد', 'شهریور', 'مهر', 'آبان', 'آذر', 'دی', 'بهمن', 'اسفند'];
            return { jy, jm, jd, formatted: `${toPersianDigits(jd)} ${monthNames[jm - 1]} ${toPersianDigits(jy)}` };
        }

        function toPersianDigits(num) {
            const persian = ['۰', '۱', '۲', '۳', '۴', '۵', '۶', '۷', '۸', '۹'];
            return num.toString().replace(/\d/g, x => persian[x]);
        }

        // نرمال‌سازی زاویه بین 0 تا 360
        function norm360(deg) {
            let d = deg % 360;
            return d < 0 ? d + 360 : d;
        }

        // یافتن صورت فلکی IAU بر اساس طول دایرةالبروجی نجومی (Sidereal Longitude)
        function getIAUConstellation(siderealDeg) {
            const d = norm360(siderealDeg);
            if (d >= 351.5 || d < 28.7) {
                return IAU_CONSTELLATIONS[12]; // حوت (Pisces)
            }
            for (let i = 0; i < IAU_CONSTELLATIONS.length - 1; i++) {
                const c = IAU_CONSTELLATIONS[i];
                if (d >= c.startDeg && d < c.endDeg) {
                    return c;
                }
            }
            return IAU_CONSTELLATIONS[0];
        }

        // محاسبه دقیق طول جغرافیایی نجومی سیارات، خورشید، ماه و طالع برای یک لحظه زمانی
        function calculateAstronomicalPositions(dateObj, lat = 35.6892, lon = 51.3890) {
            const j2000 = Date.UTC(2000, 0, 1, 12, 0, 0);
            const d = (dateObj.getTime() - j2000) / 86400000.0;

            const ayanamsa = 23.853 + (d / 365.25) * 0.01396;

            const gSun = norm360(357.529 + 0.98560028 * d);
            const qSun = norm360(280.459 + 0.98564736 * d);
            const tropSun = norm360(qSun + 1.915 * Math.sin(gSun * Math.PI / 180) + 0.020 * Math.sin(2 * gSun * Math.PI / 180));
            const sidSun = norm360(tropSun - ayanamsa);

            const lMoon = norm360(218.316 + 13.176396 * d);
            const mMoon = norm360(134.963 + 13.064993 * d);
            const fMoon = norm360(93.272 + 13.229350 * d);
            const tropMoon = norm360(lMoon + 6.289 * Math.sin(mMoon * Math.PI / 180) - 1.274 * Math.sin((mMoon - 2 * fMoon) * Math.PI / 180));
            const sidMoon = norm360(tropMoon - ayanamsa);

            const mMerc = norm360(174.795 + 4.09233445 * d);
            const tropMerc = norm360(tropSun + 22.5 * Math.sin(mMerc * Math.PI / 180));
            const sidMerc = norm360(tropMerc - ayanamsa);

            const mVenus = norm360(50.416 + 1.60213034 * d);
            const tropVenus = norm360(tropSun + 45.8 * Math.sin(mVenus * Math.PI / 180));
            const sidVenus = norm360(tropVenus - ayanamsa);

            const mMars = norm360(19.373 + 0.52402068 * d);
            const lMars = norm360(355.433 + 0.52402068 * d + 10.691 * Math.sin(mMars * Math.PI / 180));
            const sidMars = norm360(lMars - ayanamsa);

            const mJup = norm360(20.020 + 0.08308529 * d);
            const lJup = norm360(34.351 + 0.08308529 * d + 5.555 * Math.sin(mJup * Math.PI / 180));
            const sidJup = norm360(lJup - ayanamsa);

            const mSat = norm360(317.020 + 0.03344414 * d);
            const lSat = norm360(50.077 + 0.03344414 * d + 6.358 * Math.sin(mSat * Math.PI / 180));
            const sidSat = norm360(lSat - ayanamsa);

            const gmst = norm360(280.46061837 + 360.98564736629 * d);
            const lst = norm360(gmst + lon);
            const eps = 23.4393 * Math.PI / 180;
            const lstRad = lst * Math.PI / 180;
            const latRad = lat * Math.PI / 180;
            const ascRad = Math.atan2(Math.cos(lstRad), -(Math.sin(lstRad) * Math.cos(eps) + Math.tan(latRad) * Math.sin(eps)));
            const tropAsc = norm360(ascRad * 180 / Math.PI);
            const sidAsc = norm360(tropAsc - ayanamsa);

            const moonPhaseAngle = norm360(sidMoon - sidSun);
            let moonPhaseName = '';
            let moonIllumination = Math.round((1 - Math.cos(moonPhaseAngle * Math.PI / 180)) / 2 * 100);
            if (moonPhaseAngle < 22.5 || moonPhaseAngle >= 337.5) moonPhaseName = 'محاق (ماه نو - آغاز نیت)';
            else if (moonPhaseAngle < 67.5) moonPhaseName = 'هلال فزاینده (رشد و اقدام)';
            else if (moonPhaseAngle < 112.5) moonPhaseName = 'تربیع اول (تصمیم و غلبه بر چالش)';
            else if (moonPhaseAngle < 157.5) moonPhaseName = 'تحدب فزاینده (توسعه و شتاب)';
            else if (moonPhaseAngle < 202.5) moonPhaseName = 'بدر کامل (اوج بهره‌وری و برداشت)';
            else if (moonPhaseAngle < 247.5) moonPhaseName = 'تحدب کاهنده (تحلیل و بهینه‌سازی)';
            else if (moonPhaseAngle < 292.5) moonPhaseName = 'تربیع دوم (بازنگری و پالایش)';
            else moonPhaseName = 'هلال کاهنده (تکمیل و جمع‌بندی)';

            const bodies = [
                { id: 'sun', name: 'خورشید', symbol: '☉', deg: sidSun, sign: getIAUConstellation(sidSun), color: '#D4AF37' },
                { id: 'moon', name: 'قمر (ماه)', symbol: '☽', deg: sidMoon, sign: getIAUConstellation(sidMoon), color: '#00F0FF' },
                { id: 'asc', name: 'طالع (ASC)', symbol: 'AC', deg: sidAsc, sign: getIAUConstellation(sidAsc), color: '#F3E5AB' },
                { id: 'mercury', name: 'عطارد', symbol: '☿', deg: sidMerc, sign: getIAUConstellation(sidMerc), color: '#38BDF8' },
                { id: 'venus', name: 'زهره', symbol: '♀', deg: sidVenus, sign: getIAUConstellation(sidVenus), color: '#F472B6' },
                { id: 'mars', name: 'مریخ', symbol: '♂', deg: sidMars, sign: getIAUConstellation(sidMars), color: '#FB7185' },
                { id: 'jupiter', name: 'مشتری', symbol: '♃', deg: sidJup, sign: getIAUConstellation(sidJup), color: '#FBBF24' },
                { id: 'saturn', name: 'زحل', symbol: '♄', deg: sidSat, sign: getIAUConstellation(sidSat), color: '#94A3B8' }
            ];

            const aspects = [];
            const aspectTypes = [
                { name: 'مقارنه (0°)', angle: 0, orb: 8, type: 'conjunction', color: '#D4AF37', harmony: 15 },
                { name: 'تسدیس (60°)', angle: 60, orb: 6, type: 'sextile', color: '#34D399', harmony: 12 },
                { name: 'تربیع (90°)', angle: 90, orb: 7, type: 'square', color: '#FB7185', harmony: -10 },
                { name: 'تثلیث (120°)', angle: 120, orb: 8, type: 'trine', color: '#10B981', harmony: 18 },
                { name: 'مقابله (180°)', angle: 180, orb: 8, type: 'opposition', color: '#F43F5E', harmony: -8 }
            ];

            for (let i = 0; i < bodies.length; i++) {
                for (let j = i + 1; j < bodies.length; j++) {
                    let diff = Math.abs(bodies[i].deg - bodies[j].deg);
                    if (diff > 180) diff = 360 - diff;
                    for (const asp of aspectTypes) {
                        if (Math.abs(diff - asp.angle) <= asp.orb) {
                            aspects.push({
                                p1: bodies[i],
                                p2: bodies[j],
                                ...asp,
                                exactDiff: diff.toFixed(1)
                            });
                            break;
                        }
                    }
                }
            }

            const planetarySchedule = calculatePlanetaryHours(dateObj, lat, lon);

            return {
                bodies,
                aspects,
                moonPhaseName,
                moonIllumination,
                isMoonInScorpio: getIAUConstellation(sidMoon).id === 'scorpius',
                planetarySchedule
            };
        }

        // محاسبه دقیق طلوع، غروب و ۲۴ ساعت کواکب
        function calculatePlanetaryHours(dateObj, lat, lon) {
            const startOfYear = new Date(dateObj.getFullYear(), 0, 0);
            const dayOfYear = Math.floor((dateObj - startOfYear) / 86400000);
            
            const decl = 23.44 * Math.sin((360 / 365 * (dayOfYear - 81)) * Math.PI / 180);
            const latRad = lat * Math.PI / 180;
            const declRad = decl * Math.PI / 180;
            const cosH = -Math.tan(latRad) * Math.tan(declRad);
            const clampedCosH = Math.max(-1, Math.min(1, cosH));
            const halfDayHours = (Math.acos(clampedCosH) * 180 / Math.PI) / 15;
            
            const solarNoon = 12.0;
            const sunriseDecimal = solarNoon - halfDayHours;
            const sunsetDecimal = solarNoon + halfDayHours;

            const dayDurationMins = (sunsetDecimal - sunriseDecimal) * 60;
            const nightDurationMins = (24 - (sunsetDecimal - sunriseDecimal)) * 60;
            const dayHourLength = dayDurationMins / 12;
            const nightHourLength = nightDurationMins / 12;

            const dayOfWeek = dateObj.getDay();
            const rulerId = DAY_RULERS[dayOfWeek];
            const startIdx = CHALDEAN_PLANETS.findIndex(p => p.id === rulerId);

            const hours = [];
            let currentMins = sunriseDecimal * 60;

            for (let i = 0; i < 24; i++) {
                const isDay = i < 12;
                const duration = isDay ? dayHourLength : nightHourLength;
                const planet = CHALDEAN_PLANETS[(startIdx + i) % 7];
                const startM = currentMins;
                const endM = currentMins + duration;

                hours.push({
                    index: i + 1,
                    isDay,
                    planet,
                    startStr: formatMinutesToTime(startM),
                    endStr: formatMinutesToTime(endM),
                    startMinutes: startM % 1440,
                    endMinutes: endM % 1440
                });
                currentMins = endM;
            }

            const selectedMins = dateObj.getHours() * 60 + dateObj.getMinutes();
            let activeHour = hours[0];
            for (const h of hours) {
                if (h.startMinutes <= h.endMinutes) {
                    if (selectedMins >= h.startMinutes && selectedMins < h.endMinutes) {
                        activeHour = h;
                        break;
                    }
                } else {
                    if (selectedMins >= h.startMinutes || selectedMins < h.endMinutes) {
                        activeHour = h;
                        break;
                    }
                }
            }

            return {
                sunriseStr: formatMinutesToTime(sunriseDecimal * 60),
                sunsetStr: formatMinutesToTime(sunsetDecimal * 60),
                hours,
                activeHour
            };
        }

        function formatMinutesToTime(totalMins) {
            let m = Math.round(totalMins) % 1440;
            if (m < 0) m += 1440;
            const hh = Math.floor(m / 60).toString().padStart(2, '0');
            const mm = (m % 60).toString().padStart(2, '0');
            return `${hh}:${mm}`;
        }

        // ============================================================================
        // ۳. رندر نمودارهای هندسی لوکس (Astrolabe, Sacred Radar, Fibonacci, Polygon)
        // ============================================================================

        function renderAstrolabeSVG(astroData) {
            const container = document.getElementById('astrolabe-container');
            const size = 440;
            const cx = size / 2;
            const cy = size / 2;
            const rOuter = 205;
            const rZodiac = 172;
            const rInner = 135;
            const rCore = 55;

            let svg = `<svg viewBox="0 0 ${size} ${size}" class="w-full h-full drop-shadow-[0_0_25px_rgba(212,175,55,0.22)]">
                <defs>
                    <radialGradient id="astroBg" cx="50%" cy="50%" r="50%">
                        <stop offset="0%" stop-color="#161A26" stop-opacity="0.96"/>
                        <stop offset="70%" stop-color="#0D1018" stop-opacity="0.98"/>
                        <stop offset="100%" stop-color="#090A0F" stop-opacity="1"/>
                    </radialGradient>
                    <linearGradient id="goldStroke" x1="0%" y1="0%" x2="100%" y2="100%">
                        <stop offset="0%" stop-color="#F3E5AB"/>
                        <stop offset="50%" stop-color="#D4AF37"/>
                        <stop offset="100%" stop-color="#997A15"/>
                    </linearGradient>
                </defs>

                <circle cx="${cx}" cy="${cy}" r="${rOuter}" fill="url(#astroBg)" stroke="url(#goldStroke)" stroke-width="2"/>
                <circle cx="${cx}" cy="${cy}" r="${rZodiac}" fill="none" stroke="rgba(212,175,55,0.35)" stroke-width="1"/>
                <circle cx="${cx}" cy="${cy}" r="${rInner}" fill="none" stroke="rgba(0,240,255,0.25)" stroke-width="1" stroke-dasharray="4 3"/>

                <g class="spin-slow" opacity="0.22">
                    <polygon points="${cx},${cy - rInner} ${cx + rInner * 0.866},${cy + rInner * 0.5} ${cx - rInner * 0.866},${cy + rInner * 0.5}" fill="none" stroke="#D4AF37" stroke-width="1"/>
                    <polygon points="${cx},${cy + rInner} ${cx + rInner * 0.866},${cy - rInner * 0.5} ${cx - rInner * 0.866},${cy - rInner * 0.5}" fill="none" stroke="#00F0FF" stroke-width="1"/>
                </g>
            `;

            IAU_CONSTELLATIONS.forEach((c) => {
                const startRad = (c.startDeg - 90) * Math.PI / 180;
                const endRad = (c.endDeg - 90) * Math.PI / 180;
                const midDeg = (c.startDeg + c.endDeg) / 2;
                const midRad = (midDeg - 90) * Math.PI / 180;

                const x1 = cx + rZodiac * Math.cos(startRad);
                const y1 = cy + rZodiac * Math.sin(startRad);
                const x2 = cx + rOuter * Math.cos(startRad);
                const y2 = cy + rOuter * Math.sin(startRad);

                const isOphiuchus = c.id === 'ophiuchus';
                svg += `<line x1="${x1}" y1="${y1}" x2="${x2}" y2="${y2}" stroke="${isOphiuchus ? '#00F0FF' : 'rgba(212,175,55,0.4)'}" stroke-width="${isOphiuchus ? '1.8' : '1'}"/>`;

                const rText = (rOuter + rZodiac) / 2;
                const tx = cx + rText * Math.cos(midRad);
                const ty = cy + rText * Math.sin(midRad);
                svg += `<text x="${tx}" y="${ty}" fill="${isOphiuchus ? '#00F0FF' : '#F3E5AB'}" font-size="13" font-weight="bold" text-anchor="middle" dominant-baseline="central">${c.symbol}</text>`;
            });

            const bodyCoords = {};
            astroData.bodies.forEach((b, idx) => {
                const rPlanet = rInner - 18 - (idx % 3) * 14;
                const rad = (b.deg - 90) * Math.PI / 180;
                const px = cx + rPlanet * Math.cos(rad);
                const py = cy + rPlanet * Math.sin(rad);
                bodyCoords[b.id] = { x: px, y: py, body: b };
            });

            astroData.aspects.forEach(asp => {
                const c1 = bodyCoords[asp.p1.id];
                const c2 = bodyCoords[asp.p2.id];
                if (c1 && c2) {
                    const dash = asp.type === 'square' || asp.type === 'opposition' ? '4 3' : 'none';
                    svg += `<line x1="${c1.x}" y1="${c1.y}" x2="${c2.x}" y2="${c2.y}" stroke="${asp.color}" stroke-width="1.3" stroke-opacity="0.75" stroke-dasharray="${dash}"/>`;
                }
            });

            Object.values(bodyCoords).forEach(({ x, y, body }) => {
                svg += `
                    <g class="cursor-pointer group">
                        <circle cx="${x}" cy="${y}" r="11" fill="#090A0F" stroke="${body.color}" stroke-width="1.8"/>
                        <text x="${x}" y="${y}" fill="${body.color}" font-size="11" font-weight="bold" text-anchor="middle" dominant-baseline="central">${body.symbol}</text>
                        <title>${body.name} در ${body.sign.name} (${Math.round(body.deg)}°)</title>
                    </g>
                `;
            });

            svg += `
                <circle cx="${cx}" cy="${cy}" r="${rCore}" fill="#090A0F" stroke="url(#goldStroke)" stroke-width="1.5"/>
                <polygon points="${cx},${cy - 28} ${cx + 24},${cy + 14} ${cx - 24},${cy + 14}" fill="none" stroke="#D4AF37" stroke-width="1.2" opacity="0.8"/>
                <polygon points="${cx},${cy + 28} ${cx + 24},${cy - 14} ${cx - 24},${cy - 14}" fill="none" stroke="#00F0FF" stroke-width="1.2" opacity="0.8"/>
                <circle cx="${cx}" cy="${cy}" r="5" fill="#D4AF37"/>
            </svg>`;

            container.innerHTML = svg;
        }

        function renderSacredRadarChart(scores, cosmicPotentials) {
            const container = document.getElementById('radar-chart-container');
            const size = 320;
            const cx = size / 2;
            const cy = size / 2;
            const maxR = 112;
            const keys = Object.keys(GROWTH_DIMENSIONS);
            const n = keys.length;

            let svg = `<svg viewBox="0 0 ${size} ${size}" class="w-full max-w-[320px] h-auto">
                <defs>
                    <linearGradient id="radarGoldFill" x1="0%" y1="0%" x2="100%" y2="100%">
                        <stop offset="0%" stop-color="#F3E5AB" stop-opacity="0.48"/>
                        <stop offset="100%" stop-color="#D4AF37" stop-opacity="0.2"/>
                    </linearGradient>
                </defs>
            `;

            [0.25, 0.5, 0.75, 1].forEach((scale, idx) => {
                const pts = keys.map((_, i) => {
                    const angle = (i * 2 * Math.PI / n) - Math.PI / 2;
                    return `${cx + maxR * scale * Math.cos(angle)},${cy + maxR * scale * Math.sin(angle)}`;
                }).join(' ');
                svg += `<polygon points="${pts}" fill="${idx === 3 ? 'rgba(22,26,38,0.5)' : 'none'}" stroke="rgba(212,175,55,${idx === 3 ? 0.45 : 0.18})" stroke-width="${idx === 3 ? 1.5 : 1}"/>`;
            });

            keys.forEach((key, i) => {
                const angle = (i * 2 * Math.PI / n) - Math.PI / 2;
                const x2 = cx + maxR * Math.cos(angle);
                const y2 = cy + maxR * Math.sin(angle);
                svg += `<line x1="${cx}" y1="${cy}" x2="${x2}" y2="${y2}" stroke="rgba(212,175,55,0.2)" stroke-width="1"/>`;

                const lx = cx + (maxR + 26) * Math.cos(angle);
                const ly = cy + (maxR + 22) * Math.sin(angle);
                svg += `<text x="${lx}" y="${ly}" fill="#F3E5AB" font-size="11" font-weight="600" text-anchor="middle" dominant-baseline="central">${GROWTH_DIMENSIONS[key].short}</text>`;
            });

            const cosmicPts = keys.map((key, i) => {
                const val = (cosmicPotentials[key] || 75) / 100;
                const angle = (i * 2 * Math.PI / n) - Math.PI / 2;
                return `${cx + maxR * val * Math.cos(angle)},${cy + maxR * val * Math.sin(angle)}`;
            }).join(' ');
            svg += `<polygon points="${cosmicPts}" fill="rgba(0,240,255,0.1)" stroke="#00F0FF" stroke-width="1.5" stroke-dasharray="4 3"/>`;

            const actualPts = keys.map((key, i) => {
                const val = Math.max(15, scores[key] || 40) / 100;
                const angle = (i * 2 * Math.PI / n) - Math.PI / 2;
                return `${cx + maxR * val * Math.cos(angle)},${cy + maxR * val * Math.sin(angle)}`;
            }).join(' ');
            svg += `<polygon points="${actualPts}" fill="url(#radarGoldFill)" stroke="#D4AF37" stroke-width="2.2"/>`;

            keys.forEach((key, i) => {
                const val = Math.max(15, scores[key] || 40) / 100;
                const angle = (i * 2 * Math.PI / n) - Math.PI / 2;
                const px = cx + maxR * val * Math.cos(angle);
                const py = cy + maxR * val * Math.sin(angle);
                svg += `<circle cx="${px}" cy="${py}" r="4" fill="#F3E5AB" stroke="#090A0F" stroke-width="1.5"/>`;
            });

            svg += `</svg>`;
            container.innerHTML = svg;

            const gridEl = document.getElementById('radar-metrics-grid');
            gridEl.innerHTML = keys.map(key => `
                <div class="bg-obsidian/70 px-2 py-1.5 rounded-xl border border-gold/15">
                    <span class="text-slate-400 block text-[10px]">${GROWTH_DIMENSIONS[key].short}</span>
                    <span class="text-gold-light font-bold">${toPersianDigits(scores[key])}٪</span>
                    <span class="text-cyber text-[9px] mr-1">(${toPersianDigits(cosmicPotentials[key])}٪)</span>
                </div>
            `).join('');
        }

        function renderFibonacciSpiralSVG(completionRate) {
            const container = document.getElementById('fibonacci-chart-container');
            const w = 380;
            const h = 235;
            
            let svg = `<svg viewBox="0 0 ${w} ${h}" class="w-full max-w-[380px] h-auto">
                <defs>
                    <linearGradient id="fibGrad" x1="0%" y1="0%" x2="100%" y2="0%">
                        <stop offset="0%" stop-color="#00F0FF"/>
                        <stop offset="50%" stop-color="#D4AF37"/>
                        <stop offset="100%" stop-color="#F3E5AB"/>
                    </linearGradient>
                </defs>

                <rect x="10" y="10" width="360" height="215" rx="12" fill="rgba(9,10,15,0.8)" stroke="rgba(212,175,55,0.3)" stroke-width="1.2"/>
                
                <line x1="232" y1="10" x2="232" y2="225" stroke="rgba(212,175,55,0.22)" stroke-width="1"/>
                <line x1="232" y1="143" x2="370" y2="143" stroke="rgba(212,175,55,0.22)" stroke-width="1"/>
                <line x1="285" y1="143" x2="285" y2="225" stroke="rgba(212,175,55,0.22)" stroke-width="1"/>
                <line x1="232" y1="176" x2="285" y2="176" stroke="rgba(212,175,55,0.22)" stroke-width="1"/>

                <path d="M 262 162 A 20 20 0 0 1 285 176 A 33 33 0 0 1 252 209 A 53 53 0 0 1 232 143 A 86 86 0 0 1 318 57 A 138 138 0 0 1 232 225 A 222 222 0 0 1 10 10" 
                      fill="none" stroke="rgba(212,175,55,0.18)" stroke-width="3" stroke-dasharray="4 4"/>

                <path id="fib-active-path" d="M 262 162 A 20 20 0 0 1 285 176 A 33 33 0 0 1 252 209 A 53 53 0 0 1 232 143 A 86 86 0 0 1 318 57 A 138 138 0 0 1 232 225 A 222 222 0 0 1 10 10" 
                      fill="none" stroke="url(#fibGrad)" stroke-width="4" stroke-linecap="round"
                      stroke-dasharray="620" stroke-dashoffset="${620 - (620 * Math.max(0.18, completionRate / 100))}"/>

                <circle cx="262" cy="162" r="4" fill="#00F0FF"/>
                <text x="255" y="155" fill="#94A3B8" font-size="9">1</text>

                <circle cx="285" cy="176" r="4" fill="#00F0FF"/>
                <text x="292" y="178" fill="#94A3B8" font-size="9">2</text>

                <circle cx="252" cy="209" r="4.5" fill="#D4AF37"/>
                <text x="248" y="220" fill="#94A3B8" font-size="9">3</text>

                <circle cx="232" cy="143" r="5" fill="#D4AF37"/>
                <text x="218" y="140" fill="#F3E5AB" font-size="10" font-weight="bold">5</text>

                <circle cx="318" cy="57" r="6" fill="#F3E5AB" stroke="#D4AF37" stroke-width="2"/>
                <text x="326" y="52" fill="#F3E5AB" font-size="11" font-weight="bold">8 (φ)</text>

                <circle cx="145" cy="95" r="5.5" fill="rgba(212,175,55,0.4)" stroke="#D4AF37" stroke-width="1.5"/>
                <text x="135" y="84" fill="#D4AF37" font-size="11" font-weight="bold">13</text>

                <circle cx="25" cy="25" r="6" fill="rgba(0,240,255,0.3)" stroke="#00F0FF" stroke-width="1.5"/>
                <text x="42" y="30" fill="#00F0FF" font-size="11" font-weight="bold">21</text>
            </svg>`;

            container.innerHTML = svg;

            const stages = [
                { min: 0, text: 'فاز ۲: بذرگذاری و اعتبارسنجی اولیه (۲ واحد فیبوناچی)' },
                { min: 25, text: 'فاز ۳: تثبیت فرآیندهای هسته‌ای (۳ واحد فیبوناچی)' },
                { min: 45, text: 'فاز ۵: گسترش شبکه و شتاب اجرایی (۵ واحد فیبوناچی)' },
                { min: 65, text: 'فاز ۸: هم‌افزایی طلایی و رشد تصاعدی (۸ واحد فیبوناچی)' },
                { min: 85, text: 'فاز ۱۳: تسلط بر بازار و رهبری استراتژیک (۱۳ واحد فیبوناچی)' }
            ];
            const currentStage = [...stages].reverse().find(s => completionRate >= s.min) || stages[0];
            document.getElementById('fib-stage-name').textContent = currentStage.text;
            document.getElementById('fib-growth-percent').textContent = `+${toPersianDigits(Math.round(completionRate * 1.18))}٪`;
        }

        function renderHourlyEnergyPolygon(hours, activeIndex) {
            const container = document.getElementById('hourly-polygon-container');
            const size = 250;
            const cx = size / 2;
            const cy = size / 2;
            const maxR = 98;
            const minR = 32;

            let svg = `<svg viewBox="0 0 ${size} ${size}" class="w-full h-full">
                <circle cx="${cx}" cy="${cy}" r="${maxR}" fill="rgba(9,10,15,0.85)" stroke="rgba(212,175,55,0.25)" stroke-width="1"/>
                <circle cx="${cx}" cy="${cy}" r="${(maxR + minR) / 2}" fill="none" stroke="rgba(212,175,55,0.15)" stroke-dasharray="3 3"/>
                <circle cx="${cx}" cy="${cy}" r="${minR}" fill="#10131D" stroke="rgba(0,240,255,0.3)" stroke-width="1"/>
            `;

            const points = hours.map((h, i) => {
                const angle = (i * 2 * Math.PI / 24) - Math.PI / 2;
                const r = minR + ((h.planet.energy - 50) / 50) * (maxR - minR);
                return {
                    x: cx + r * Math.cos(angle),
                    y: cy + r * Math.sin(angle),
                    h
                };
            });

            const polyStr = points.map(p => `${p.x},${p.y}`).join(' ');
            svg += `<polygon points="${polyStr}" fill="rgba(212,175,55,0.22)" stroke="#D4AF37" stroke-width="1.8"/>`;

            points.forEach((p, i) => {
                const isActive = p.h.index === activeIndex;
                svg += `
                    <circle cx="${p.x}" cy="${p.y}" r="${isActive ? 5.5 : 3}" fill="${isActive ? '#00F0FF' : p.h.planet.color}" stroke="#090A0F" stroke-width="1">
                        <title>ساعت ${toPersianDigits(p.h.index)} (${p.h.startStr}) - ${p.h.planet.name}: توان ${toPersianDigits(p.h.planet.energy)}٪</title>
                    </circle>
                `;
            });

            svg += `
                <text x="${cx}" y="${cy - 4}" fill="#F3E5AB" font-size="11" font-weight="bold" text-anchor="middle">۲۴ ساعت</text>
                <text x="${cx}" y="${cy + 10}" fill="#00F0FF" font-size="9" text-anchor="middle">کواکب</text>
            </svg>`;

            container.innerHTML = svg;
        }

        // ============================================================================
        // ۴. مدیریت داده‌ها، محاسبه امتیازات و آپدیت رابط کاربری
        // ============================================================================

        function initApp() {
            const saved = localStorage.getItem('aetheria_planner_state_v2');
            if (saved) {
                try {
                    appState = { ...appState, ...JSON.parse(saved) };
                } catch (e) {
                    console.error('Error parsing saved state');
                }
            }

            const now = new Date();
            const yyyy = now.getFullYear();
            const mm = String(now.getMonth() + 1).padStart(2, '0');
            const dd = String(now.getDate()).padStart(2, '0');
            const hh = String(now.getHours()).padStart(2, '0');
            const min = String(now.getMinutes()).padStart(2, '0');

            if (!appState.targetDate) appState.targetDate = `${yyyy}-${mm}-${dd}`;
            if (!appState.targetTime) appState.targetTime = `${hh}:${min}`;

            document.getElementById('target-date').value = appState.targetDate;
            document.getElementById('target-time').value = appState.targetTime;
            document.getElementById('task-date').value = appState.targetDate;
            document.getElementById('profile-name').value = appState.profile.name;
            document.getElementById('profile-city').value = appState.profile.city;
            document.getElementById('birth-date').value = appState.profile.birthDate;
            document.getElementById('birth-time').value = appState.profile.birthTime;

            if (!appState.tasks || appState.tasks.length === 0) {
                appState.tasks = [
                    {
                        id: 't-1',
                        title: 'بازنگری نقشه راه استراتژیک Q4 و هم‌راستایی با اهداف کلان',
                        category: 'strategy',
                        priority: 'critical',
                        date: appState.targetDate,
                        start: '09:30',
                        end: '11:00',
                        status: 'completed',
                        notes: 'تعیین KPIهای کلیدی رشد و تخصیص بودجه تحقیق و توسعه'
                    },
                    {
                        id: 't-2',
                        title: 'جلسه مذاکره نهایی با سرمایه‌گذاران و شرکای تجاری',
                        category: 'finance',
                        priority: 'critical',
                        date: appState.targetDate,
                        start: '11:15',
                        end: '12:30',
                        status: 'completed',
                        notes: 'ارائه مدل مالی و قرارداد مشارکت استراتژیک'
                    },
                    {
                        id: 't-3',
                        title: 'توسعه ماژول هوش مصنوعی و معماری داشبورد تحلیلی',
                        category: 'execution',
                        priority: 'high',
                        date: appState.targetDate,
                        start: '13:30',
                        end: '15:30',
                        status: 'in_progress',
                        notes: 'بهینه‌سازی سرعت پردازش داده‌ها و تست امنیت'
                    },
                    {
                        id: 't-4',
                        title: 'طراحی کمپین خلاقانه معرفی محصول جدید در شبکه‌های تخصصی',
                        category: 'creativity',
                        priority: 'high',
                        date: appState.targetDate,
                        start: '16:00',
                        end: '17:15',
                        status: 'in_progress',
                        notes: 'تولید محتوای بصری لوکس و سناریوی ویدیویی'
                    },
                    {
                        id: 't-5',
                        title: 'جلسه هم‌افزایی با مشاوران بین‌المللی و توسعه شبکه ارتباطی',
                        category: 'network',
                        priority: 'medium',
                        date: appState.targetDate,
                        start: '18:00',
                        end: '19:00',
                        status: 'pending',
                        notes: 'بررسی فرصت‌های صادرات خدمات و همکاری فرامرزی'
                    },
                    {
                        id: 't-6',
                        title: 'پایش شاخص‌های انرژی تیم و مدیتیشن استراتژیک پایان روز',
                        category: 'energy',
                        priority: 'medium',
                        date: appState.targetDate,
                        start: '20:30',
                        end: '21:15',
                        status: 'pending',
                        notes: 'ثبت دستاوردهای روزانه و آماده‌سازی ذهن برای فردا'
                    }
                ];
                saveState();
            }

            document.getElementById('target-date').addEventListener('change', (e) => {
                appState.targetDate = e.target.value;
                document.getElementById('task-date').value = e.target.value;
                saveState();
                updateAllViews();
            });
            document.getElementById('target-time').addEventListener('change', (e) => {
                appState.targetTime = e.target.value;
                saveState();
                updateAllViews();
            });

            updateAllViews();
            lucide.createIcons();
        }

        function saveState() {
            localStorage.setItem('aetheria_planner_state_v2', JSON.stringify(appState));
        }

        function setNowDateTime() {
            const now = new Date();
            appState.targetDate = `${now.getFullYear()}-${String(now.getMonth() + 1).padStart(2, '0')}-${String(now.getDate()).padStart(2, '0')}`;
            appState.targetTime = `${String(now.getHours()).padStart(2, '0')}:${String(now.getMinutes()).padStart(2, '0')}`;
            document.getElementById('target-date').value = appState.targetDate;
            document.getElementById('target-time').value = appState.targetTime;
            saveState();
            updateAllViews();
            showToast('زمان تحلیل به لحظه اکنون بروزرسانی شد.', 'info');
        }

        function saveProfileAndRecalculate() {
            appState.profile.name = document.getElementById('profile-name').value || 'کاربر استراتژیک';
            appState.profile.city = document.getElementById('profile-city').value;
            appState.profile.birthDate = document.getElementById('birth-date').value;
            appState.profile.birthTime = document.getElementById('birth-time').value;
            saveState();
            updateAllViews();
            showToast('پروفایل نجومی و مختصات جغرافیایی ذخیره و محاسبه شد.', 'success');
        }

        function updateAllViews() {
            const [latStr, lonStr] = appState.profile.city.split(',');
            const lat = parseFloat(latStr);
            const lon = parseFloat(lonStr);

            const [by, bm, bd] = appState.profile.birthDate.split('-').map(Number);
            const [bh, bmin] = appState.profile.birthTime.split(':').map(Number);
            const birthDateObj = new Date(by, bm - 1, bd, bh, bmin);
            const birthJalali = gregorianToJalali(by, bm, bd);
            document.getElementById('birth-jalali-display').textContent = `معادل شمسی: ${birthJalali.formatted}`;

            const natalAstro = calculateAstronomicalPositions(birthDateObj, lat, lon);
            const natalSun = natalAstro.bodies.find(b => b.id === 'sun');
            const natalMoon = natalAstro.bodies.find(b => b.id === 'moon');
            const natalAsc = natalAstro.bodies.find(b => b.id === 'asc');

            document.getElementById('user-natal-sun-badge').textContent = `${natalSun.sign.symbol} ${natalSun.sign.name}`;
            document.getElementById('natal-sun-text').textContent = natalSun.sign.name;
            document.getElementById('natal-moon-text').textContent = natalMoon.sign.name;
            document.getElementById('natal-asc-text').textContent = natalAsc.sign.name;

            const [ty, tm, td] = appState.targetDate.split('-').map(Number);
            const [th, tmin] = appState.targetTime.split(':').map(Number);
            const targetDateObj = new Date(ty, tm - 1, td, th, tmin);
            const targetJalali = gregorianToJalali(ty, tm, td);

            const transitAstro = calculateAstronomicalPositions(targetDateObj, lat, lon);
            appState.astroData = { natal: natalAstro, transit: transitAstro, jalali: targetJalali };

            const tSun = transitAstro.bodies.find(b => b.id === 'sun');
            const tMoon = transitAstro.bodies.find(b => b.id === 'moon');
            const activeHour = transitAstro.planetarySchedule.activeHour;

            document.getElementById('header-persian-date').textContent = `${targetJalali.formatted} | ساعت ${toPersianDigits(appState.targetTime)}`;
            document.getElementById('header-sun-sign').textContent = `${tSun.sign.symbol} ${tSun.sign.name} (${toPersianDigits(Math.round(tSun.deg))}°)`;
            document.getElementById('header-moon-sign').textContent = `${tMoon.sign.name} • ${transitAstro.moonPhaseName.split('(')[0]}`;
            document.getElementById('header-planetary-hour').textContent = `${activeHour.planet.symbol} ${activeHour.planet.name} (${activeHour.startStr} تا ${activeHour.endStr})`;

            const scorpioBadge = document.getElementById('scorpio-moon-badge');
            if (transitAstro.isMoonInScorpio) {
                scorpioBadge.classList.remove('hidden');
                scorpioBadge.classList.add('flex');
            } else {
                scorpioBadge.classList.add('hidden');
                scorpioBadge.classList.remove('flex');
            }

            renderAstrolabeSVG(transitAstro);
            renderPlanetsAndAspectsList(transitAstro);

            const metrics = calculateGrowthMetrics(transitAstro);
            renderSacredRadarChart(metrics.actualScores, metrics.cosmicPotentials);
            renderFibonacciSpiralSVG(metrics.completionRate);

            document.getElementById('kpi-completion').textContent = `${toPersianDigits(metrics.completionRate)}٪`;
            document.getElementById('kpi-tasks-count').textContent = `${toPersianDigits(metrics.completedCount)} از ${toPersianDigits(appState.tasks.length)} تسک تکمیل شده`;
            document.getElementById('kpi-completion-bar').style.width = `${metrics.completionRate}%`;

            document.getElementById('kpi-cosmic-score').textContent = `${toPersianDigits(metrics.cosmicAlignmentScore)}٪`;
            document.getElementById('kpi-cosmic-status').textContent = metrics.cosmicAlignmentScore >= 75 ? 'هم‌راستایی عالی کیهانی' : 'نیازمند مدیریت هوشمند انرژی';

            const phiVal = (1 + (metrics.completionRate / 100) * 0.618).toFixed(3);
            document.getElementById('kpi-phi-index').textContent = toPersianDigits(phiVal);

            const bestHour = transitAstro.planetarySchedule.hours.find(h => h.isDay && (h.planet.id === 'jupiter' || h.planet.id === 'sun')) || transitAstro.planetarySchedule.hours[2];
            document.getElementById('kpi-golden-window').textContent = `${bestHour.startStr} - ${bestHour.endStr}`;
            document.getElementById('kpi-golden-planet').textContent = `ساعت کوکب ${bestHour.planet.name}`;

            document.getElementById('sunrise-time').textContent = toPersianDigits(transitAstro.planetarySchedule.sunriseStr);
            document.getElementById('sunset-time').textContent = toPersianDigits(transitAstro.planetarySchedule.sunsetStr);
            renderPlanetaryHoursGrid(transitAstro.planetarySchedule);
            renderHourlyEnergyPolygon(transitAstro.planetarySchedule.hours, activeHour.index);

            renderTasksList();
            generateExecutiveReport();
            updateAstroPlannerAdvice(transitAstro, activeHour);
        }

        function renderPlanetsAndAspectsList(astroData) {
            const pList = document.getElementById('planets-list');
            pList.innerHTML = astroData.bodies.map(b => `
                <div class="flex items-center justify-between bg-obsidian/70 px-2.5 py-1.5 rounded-xl border border-gold/10">
                    <div class="flex items-center gap-1.5">
                        <span style="color: ${b.color}" class="font-bold text-sm">${b.symbol}</span>
                        <span class="text-slate-200 font-medium">${b.name}</span>
                    </div>
                    <div class="text-left">
                        <span class="text-gold-light font-semibold">${b.sign.name.split(' ')[0]}</span>
                        <span class="text-[10px] text-slate-400 mr-1">${toPersianDigits(Math.round(b.deg))}°</span>
                    </div>
                </div>
            `).join('');

            const aList = document.getElementById('aspects-list');
            if (astroData.aspects.length === 0) {
                aList.innerHTML = `<div class="text-slate-500 text-center py-2">زاویه دقیق عمده‌ای در این لحظه ثبت نشده است.</div>`;
            } else {
                aList.innerHTML = astroData.aspects.slice(0, 6).map(a => `
                    <div class="flex items-center justify-between bg-obsidian/60 px-2 py-1 rounded-lg border border-slate-800">
                        <span class="text-slate-300">${a.p1.name} <span style="color:${a.color}">●</span> ${a.p2.name}</span>
                        <span style="color:${a.color}" class="font-semibold">${a.name.split(' ')[0]}</span>
                    </div>
                `).join('');
            }
        }

        function renderPlanetaryHoursGrid(schedule) {
            const grid = document.getElementById('planetary-hours-grid');
            const dayHours = schedule.hours.slice(0, 12);
            grid.innerHTML = dayHours.map(h => {
                const isSelected = h.index === schedule.activeHour.index;
                return `
                    <div onclick="selectPlanetaryHour('${h.startStr}')" class="cursor-pointer p-2.5 rounded-xl border transition ${isSelected ? 'bg-gold/20 border-gold shadow-gold-glow' : 'bg-obsidian/75 border-gold/15 hover:border-gold/40'}">
                        <div class="flex items-center justify-between mb-1">
                            <span class="text-[10px] text-slate-400">ساعت ${toPersianDigits(h.index)}</span>
                            <span style="color: ${h.planet.color}" class="text-xs font-bold">${h.planet.symbol} ${h.planet.name.split(' ')[0]}</span>
                        </div>
                        <div class="text-xs font-bold text-slate-100">${toPersianDigits(h.startStr)} - ${toPersianDigits(h.endStr)}</div>
                        <div class="text-[10px] text-slate-400 truncate mt-0.5" title="${h.planet.bestFor}">${h.planet.bestFor}</div>
                    </div>
                `;
            }).join('');
        }

        function selectPlanetaryHour(timeStr) {
            appState.targetTime = timeStr;
            document.getElementById('target-time').value = timeStr;
            saveState();
            updateAllViews();
            showToast(`ساعت تحلیل روی ${toPersianDigits(timeStr)} تنظیم شد.`, 'info');
        }

        function calculateGrowthMetrics(transitAstro) {
            const total = appState.tasks.length;
            const completed = appState.tasks.filter(t => t.status === 'completed').length;
            const inProgress = appState.tasks.filter(t => t.status === 'in_progress').length;
            const completionRate = total > 0 ? Math.round(((completed + inProgress * 0.45) / total) * 100) : 0;

            const actualScores = {};
            const cosmicPotentials = {};
            const keys = Object.keys(GROWTH_DIMENSIONS);

            const harmonyBonus = transitAstro.aspects.reduce((acc, a) => acc + a.harmony, 0);
            const activeEnergy = transitAstro.planetarySchedule.activeHour.planet.energy;

            keys.forEach((k, idx) => {
                const catTasks = appState.tasks.filter(t => t.category === k);
                if (catTasks.length === 0) {
                    actualScores[k] = 45;
                } else {
                    const catDone = catTasks.filter(t => t.status === 'completed').length;
                    const catProg = catTasks.filter(t => t.status === 'in_progress').length;
                    actualScores[k] = Math.min(100, Math.round(30 + ((catDone + catProg * 0.5) / catTasks.length) * 70));
                }
                const basePot = 68 + ((idx * 7 + activeEnergy + harmonyBonus) % 28);
                cosmicPotentials[k] = Math.min(98, Math.max(60, basePot));
            });

            const cosmicAlignmentScore = Math.min(99, Math.max(52, Math.round(72 + harmonyBonus * 0.6 + (activeEnergy - 75) * 0.3)));

            return {
                total,
                completedCount: completed,
                inProgressCount: inProgress,
                completionRate,
                actualScores,
                cosmicPotentials,
                cosmicAlignmentScore
            };
        }

        // ============================================================================
        // ۵. برنامه‌ریز هوشمند نجومی و مدیریت تسک‌ها
        // ============================================================================

        function updateAstroPlannerAdvice(transitAstro, activeHour) {
            const sunSign = transitAstro.bodies.find(b => b.id === 'sun').sign;
            const adviceEl = document.getElementById('astro-planner-advice');
            adviceEl.innerHTML = `
                خورشید در صورت فلکی واقعی <strong class="text-gold-light">${sunSign.name}</strong> (با انرژی ${sunSign.traits}) قرار دارد و فاز قمر <strong class="text-cyber">${transitAstro.moonPhaseName}</strong> است. 
                در ساعت انتخابی شما، کوکب <strong class="text-gold">${activeHour.planet.name}</strong> حاکم است که بهترین بستر برای <em>«${activeHour.planet.bestFor}»</em> فراهم می‌کند.
            `;
        }

        function generateSmartAstroPlan() {
            if (!appState.astroData) return;
            const schedule = appState.astroData.planetarySchedule;
            const sunSign = appState.astroData.transit.bodies.find(b => b.id === 'sun').sign;

            const jupiterHour = schedule.hours.find(h => h.isDay && h.planet.id === 'jupiter') || schedule.hours[1];
            const mercuryHour = schedule.hours.find(h => h.isDay && h.planet.id === 'mercury') || schedule.hours[3];
            const sunHour = schedule.hours.find(h => h.isDay && h.planet.id === 'sun') || schedule.hours[5];
            const venusHour = schedule.hours.find(h => h.isDay && h.planet.id === 'venus') || schedule.hours[7];

            appState.suggestedTasks = [
                {
                    title: `مذاکره استراتژیک و بررسی جریان‌های درآمدی (هم‌راستا با ${sunSign.name.split(' ')[0]})`,
                    category: 'finance',
                    priority: 'critical',
                    date: appState.targetDate,
                    start: jupiterHour.startStr,
                    end: jupiterHour.endStr,
                    planet: jupiterHour.planet.name,
                    reason: 'ساعت کوکب مشتری: بالاترین ضریب موفقیت در توافقات مالی و توسعه کسب‌وکار'
                },
                {
                    title: 'تحلیل داده‌های کلیدی، بهینه‌سازی سیستم و مستندسازی فنی',
                    category: 'execution',
                    priority: 'high',
                    date: appState.targetDate,
                    start: mercuryHour.startStr,
                    end: mercuryHour.endStr,
                    planet: mercuryHour.planet.name,
                    reason: 'ساعت کوکب عطارد: اوج تمرکز ذهنی، سرعت پردازش و دقت تحلیلی'
                },
                {
                    title: 'جلسه هم‌ترازی رهبری و تصمیم‌گیری درباره چشم‌انداز پروژه',
                    category: 'strategy',
                    priority: 'critical',
                    date: appState.targetDate,
                    start: sunHour.startStr,
                    end: sunHour.endStr,
                    planet: sunHour.planet.name,
                    reason: 'ساعت کوکب خورشید: اقتدار مدیریتی، شفافیت مسیر و دیده‌شدن'
                },
                {
                    title: 'ارتباط با مشتریان کلیدی و طراحی تجربه کاربری/برندینگ',
                    category: 'creativity',
                    priority: 'medium',
                    date: appState.targetDate,
                    start: venusHour.startStr,
                    end: venusHour.endStr,
                    planet: venusHour.planet.name,
                    reason: 'ساعت کوکب زهره: جذابیت بصری، دیپلماسی و ایجاد وفاداری مشتری'
                }
            ];

            const box = document.getElementById('suggested-plan-box');
            const grid = document.getElementById('suggested-tasks-grid');
            box.classList.remove('hidden');

            grid.innerHTML = appState.suggestedTasks.map((st, idx) => `
                <div class="bg-obsidian/90 border border-cyber/30 rounded-xl p-3.5 flex flex-col justify-between gap-2">
                    <div>
                        <div class="flex items-center justify-between text-[10px] mb-1.5">
                            <span class="px-2 py-0.5 rounded bg-gold/15 text-gold font-bold">${toPersianDigits(st.start)} - ${toPersianDigits(st.end)}</span>
                            <span class="text-cyber font-semibold">${st.planet}</span>
                        </div>
                        <h4 class="text-xs font-bold text-slate-100 leading-snug">${st.title}</h4>
                        <p class="text-[11px] text-slate-400 mt-1.5 leading-relaxed">${st.reason}</p>
                    </div>
                    <button onclick="acceptSingleSuggestedTask(${idx})" class="mt-2 w-full py-1.5 rounded-lg bg-gold/15 hover:bg-gold text-gold hover:text-obsidian border border-gold/30 text-[11px] font-bold transition">
                        + افزودن به لیست من
                    </button>
                </div>
            `).join('');

            lucide.createIcons();
            showToast('پلن هوشمند نجومی بر اساس ساعات کواکب روز تولید شد.', 'success');
        }

        function acceptSingleSuggestedTask(idx) {
            const st = appState.suggestedTasks[idx];
            if (!st) return;
            appState.tasks.unshift({
                id: 't-' + Date.now() + '-' + idx,
                title: st.title,
                category: st.category,
                priority: st.priority,
                date: st.date,
                start: st.start,
                end: st.end,
                status: 'pending',
                notes: st.reason
            });
            saveState();
            updateAllViews();
            showToast('تسک پیشنهادی به برنامه اجرایی اضافه شد.', 'success');
        }

        function acceptAllSuggestedTasks() {
            appState.suggestedTasks.forEach((st, idx) => {
                appState.tasks.unshift({
                    id: 't-' + Date.now() + '-' + idx,
                    title: st.title,
                    category: st.category,
                    priority: st.priority,
                    date: st.date,
                    start: st.start,
                    end: st.end,
                    status: 'pending',
                    notes: st.reason
                });
            });
            document.getElementById('suggested-plan-box').classList.add('hidden');
            saveState();
            updateAllViews();
            showToast('تمامی برنامه‌های پیشنهادی نجومی به لیست شما اضافه شدند.', 'success');
        }

        function handleAddTask(e) {
            e.preventDefault();
            const newTask = {
                id: 't-' + Date.now(),
                title: document.getElementById('task-title').value.trim(),
                category: document.getElementById('task-category').value,
                priority: document.getElementById('task-priority').value,
                date: document.getElementById('task-date').value,
                start: document.getElementById('task-start').value,
                end: document.getElementById('task-end').value,
                status: 'pending',
                notes: document.getElementById('task-notes').value.trim()
            };
            appState.tasks.unshift(newTask);
            document.getElementById('task-form').reset();
            document.getElementById('task-date').value = appState.targetDate;
            saveState();
            updateAllViews();
            showToast('تسک جدید با موفقیت در ماتریس اجرایی ثبت شد.', 'success');
        }

        function toggleTaskStatus(id) {
            const task = appState.tasks.find(t => t.id === id);
            if (!task) return;
            const order = ['pending', 'in_progress', 'completed'];
            task.status = order[(order.indexOf(task.status) + 1) % order.length];
            saveState();
            updateAllViews();
            const statusLabels = { pending: 'در انتظار', in_progress: 'در حال اجرا', completed: 'تکمیل‌شده' };
            showToast(`وضعیت تسک به «${statusLabels[task.status]}» تغییر یافت.`, 'info');
        }

        function deleteTask(id) {
            appState.tasks = appState.tasks.filter(t => t.id !== id);
            saveState();
            updateAllViews();
            showToast('تسک از لیست حذف شد.', 'info');
        }

        function filterTasks(filter) {
            appState.currentFilter = filter;
            document.querySelectorAll('.filter-btn').forEach(btn => {
                btn.classList.remove('bg-gold/20', 'text-gold', 'border-gold/40', 'font-semibold');
                btn.classList.add('bg-obsidian', 'text-slate-400', 'border-gold/15');
            });
            event.target.classList.remove('bg-obsidian', 'text-slate-400', 'border-gold/15');
            event.target.classList.add('bg-gold/20', 'text-gold', 'border-gold/40', 'font-semibold');
            renderTasksList();
        }

        function renderTasksList() {
            const container = document.getElementById('tasks-list-container');
            let filtered = appState.tasks;
            if (appState.currentFilter !== 'all') {
                filtered = appState.tasks.filter(t => t.status === appState.currentFilter);
            }

            if (filtered.length === 0) {
                container.innerHTML = `
                    <div class="text-center py-10 text-slate-500 border border-dashed border-gold/20 rounded-2xl">
                        <p class="text-sm">هیچ تسکی در این فیلتر یافت نشد.</p>
                        <p class="text-xs mt-1">می‌توانید از دکمه «تولید پلن هوشمند نجومی» برای ایجاد برنامه خودکار استفاده کنید.</p>
                    </div>
                `;
                return;
            }

            const priorityBadges = {
                critical: '<span class="px-2 py-0.5 rounded-md bg-gold/20 text-gold border border-gold/40 text-[10px] font-bold">طلایی (S-Tier)</span>',
                high: '<span class="px-2 py-0.5 rounded-md bg-cyber/15 text-cyber border border-cyber/30 text-[10px] font-semibold">اولویت بالا</span>',
                medium: '<span class="px-2 py-0.5 rounded-md bg-slate-800 text-slate-300 text-[10px]">متوسط</span>'
            };

            const statusConfig = {
                completed: { label: 'تکمیل‌شده', badge: 'bg-emerald-500/20 text-emerald-300 border-emerald-500/40', icon: 'check-circle-2' },
                in_progress: { label: 'در حال اجرا', badge: 'bg-amber-500/20 text-amber-300 border-amber-500/40', icon: 'loader' },
                pending: { label: 'در انتظار', badge: 'bg-slate-800 text-slate-300 border-slate-700', icon: 'circle' }
            };

            container.innerHTML = filtered.map(t => {
                const st = statusConfig[t.status];
                const dim = GROWTH_DIMENSIONS[t.category] || GROWTH_DIMENSIONS.strategy;
                const [sh, sm] = t.start.split(':').map(Number);
                const taskMins = sh * 60 + sm;
                let matchingPlanet = CHALDEAN_PLANETS[1];
                if (appState.astroData) {
                    const foundH = appState.astroData.transit.planetarySchedule.hours.find(h => 
                        h.startMinutes <= h.endMinutes ? (taskMins >= h.startMinutes && taskMins < h.endMinutes) : (taskMins >= h.startMinutes || taskMins < h.endMinutes)
                    );
                    if (foundH) matchingPlanet = foundH.planet;
                }

                return `
                    <div class="bg-obsidian/85 hover:bg-obsidian border border-gold/20 rounded-xl p-3.5 transition flex flex-col sm:flex-row sm:items-center justify-between gap-3">
                        <div class="space-y-1.5 flex-1">
                            <div class="flex flex-wrap items-center gap-2">
                                ${priorityBadges[t.priority]}
                                <span class="text-[11px] text-gold-light bg-gold/10 px-2 py-0.5 rounded-md">${dim.label}</span>
                                <span class="text-[11px] text-slate-400 flex items-center gap-1">
                                    <i data-lucide="clock" class="w-3 h-3 text-gold"></i>
                                    ${toPersianDigits(t.start)} تا ${toPersianDigits(t.end)}
                                </span>
                                <span class="text-[10px] px-2 py-0.5 rounded-md bg-deepnavy border border-slate-700" style="color: ${matchingPlanet.color}">
                                    ${matchingPlanet.symbol} ساعت ${matchingPlanet.name.split(' ')[0]}
                                </span>
                            </div>
                            <h4 class="text-xs sm:text-sm font-bold ${t.status === 'completed' ? 'line-through text-slate-500' : 'text-slate-100'}">${t.title}</h4>
                            ${t.notes ? `<p class="text-[11px] text-slate-400">${t.notes}</p>` : ''}
                        </div>

                        <div class="flex items-center gap-2 self-end sm:self-center">
                            <button onclick="toggleTaskStatus('${t.id}')" class="px-3 py-1.5 rounded-xl border text-xs font-semibold flex items-center gap-1.5 transition ${st.badge}" title="کلیک برای تغییر وضعیت">
                                <i data-lucide="${st.icon}" class="w-3.5 h-3.5"></i>
                                <span>${st.label}</span>
                            </button>
                            <button onclick="deleteTask('${t.id}')" class="p-2 rounded-xl bg-rose-500/10 hover:bg-rose-500/25 text-rose-400 border border-rose-500/20 transition" title="حذف تسک">
                                <i data-lucide="trash-2" class="w-3.5 h-3.5"></i>
                            </button>
                        </div>
                    </div>
                `;
            }).join('');

            lucide.createIcons();
        }

        // ============================================================================
        // ۶. سیستم گزارش‌نویس تحلیلی جامع (Executive Analytical Report)
        // ============================================================================

        function generateExecutiveReport() {
            if (!appState.astroData) return;
            const { natal, transit, jalali } = appState.astroData;
            const metrics = calculateGrowthMetrics(transit);

            const tSun = transit.bodies.find(b => b.id === 'sun');
            const tMoon = transit.bodies.find(b => b.id === 'moon');
            const tMerc = transit.bodies.find(b => b.id === 'mercury');
            const tJup = transit.bodies.find(b => b.id === 'jupiter');
            const activeHour = transit.planetarySchedule.activeHour;

            const sortedDims = Object.entries(metrics.actualScores).sort((a, b) => b[1] - a[1]);
            const strongestDim = GROWTH_DIMENSIONS[sortedDims[0][0]];
            const weakestDim = GROWTH_DIMENSIONS[sortedDims[sortedDims.length - 1][0]];

            const [ty, tm, td] = appState.targetDate.split('-').map(Number);
            const [latStr, lonStr] = appState.profile.city.split(',');
            const forecast7Days = [];
            for (let i = 1; i <= 7; i++) {
                const futureDate = new Date(ty, tm - 1, td + i, 11, 0);
                const fJalali = gregorianToJalali(futureDate.getFullYear(), futureDate.getMonth() + 1, futureDate.getDate());
                const fAstro = calculateAstronomicalPositions(futureDate, parseFloat(latStr), parseFloat(lonStr));
                const fMoon = fAstro.bodies.find(b => b.id === 'moon');
                const fHarm = fAstro.aspects.reduce((acc, a) => acc + a.harmony, 0);
                const energyScore = Math.min(98, Math.max(58, 76 + fHarm));
                forecast7Days.push({
                    dateStr: fJalali.formatted,
                    moonSign: fMoon.sign.name.split(' ')[0],
                    phase: fAstro.moonPhaseName.split('(')[0],
                    energyScore,
                    focus: fAstro.isMoonInScorpio ? 'پایش ریسک، حسابرسی و پرهیز از قراردادهای عجولانه' : (energyScore >= 80 ? 'عقد قرارداد، توسعه فروش و جلسات کلیدی' : 'اجرای عملیات، بهینه‌سازی و کارهای تحلیلی')
                });
            }

            const reportContainer = document.getElementById('executive-report-content');
            reportContainer.innerHTML = `
                <div class="luxury-card geo-corner rounded-2xl p-6">
                    <div class="flex flex-col md:flex-row md:items-center justify-between gap-4 pb-4 border-b border-gold/25">
                        <div>
                            <span class="text-xs text-gold font-bold tracking-wider uppercase">AETHERIA EXECUTIVE INTELLIGENCE BRIEF</span>
                            <h3 class="text-xl font-black text-slate-100 mt-1">گزارش جامع عملکرد استراتژیک و هم‌راستایی نجومی (IAU)</h3>
                            <p class="text-xs text-slate-400 mt-1">تهیه شده برای: <strong class="text-gold-light">${appState.profile.name}</strong> | تاریخ گزارش: <strong>${jalali.formatted}</strong> (ساعت ${toPersianDigits(appState.targetTime)})</p>
                        </div>
                        <div class="flex items-center gap-3 bg-obsidian/90 px-4 py-3 rounded-2xl border border-gold/30">
                            <div class="text-center">
                                <span class="text-[10px] text-slate-400 block">شاخص کل بهره‌وری</span>
                                <span class="text-xl font-black text-gold-gradient">${toPersianDigits(metrics.completionRate)}٪</span>
                            </div>
                            <div class="h-8 w-px bg-gold/20"></div>
                            <div class="text-center">
                                <span class="text-[10px] text-slate-400 block">ضریب هم‌راستایی نجومی</span>
                                <span class="text-xl font-black text-cyber">${toPersianDigits(metrics.cosmicAlignmentScore)}٪</span>
                            </div>
                        </div>
                    </div>

                    <div class="mt-4 space-y-2 text-xs sm:text-sm text-slate-300 leading-relaxed">
                        <h4 class="text-sm font-bold text-gold-light flex items-center gap-1.5">
                            <i data-lucide="file-text" class="w-4 h-4 text-gold"></i>
                            <span>۱. خلاصه تحلیلی وضعیت فعلی کسب‌وکار و آسمان</span>
                        </h4>
                        <p>
                            بر اساس داده‌های ثبت‌شده در ماتریس اجرایی، تا این لحظه <strong class="text-gold-light">${toPersianDigits(metrics.completedCount)} تسک از مجموع ${toPersianDigits(metrics.total)} برنامه</strong> به‌طور کامل محقق شده و نرخ پیشرفت ترکیبی در سطح <strong class="text-gold">${toPersianDigits(metrics.completionRate)}٪</strong> قرار دارد. 
                            بیشترین تمرکز و دستاورد شما در بُعد <strong class="text-emerald-400">«${strongestDim.label}» (${toPersianDigits(sortedDims[0][1])}٪)</strong> ثبت شده است، در حالی که بُعد <strong class="text-amber-400">«${weakestDim.label}» (${toPersianDigits(sortedDims[sortedDims.length - 1][1])}٪)</strong> به‌عنوان گلوگاه اصلی نیازمند تخصیص منابع بیشتر است.
                        </p>
                        <p>
                            از منظر نجومی (طبق مرزهای واقعی ۱۳ صورت فلکی IAU)، قرارگیری خورشید در صورت فلکی <strong class="text-gold-light">${tSun.sign.name}</strong> و قمر در <strong class="text-cyber">${tMoon.sign.name}</strong> (فاز ${transit.moonPhaseName}) فضایی سرشار از انرژی <em>«${tSun.sign.traits}»</em> ایجاد کرده است. همچنین استقرار عطارد در <strong class="text-slate-100">${tMerc.sign.name.split(' ')[0]}</strong> و مشتری در <strong class="text-slate-100">${tJup.sign.name.split(' ')[0]}</strong> بستر مناسبی برای توسعه استراتژیک فراهم می‌سازد.
                        </p>
                    </div>
                </div>

                <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                    <div class="luxury-card rounded-2xl p-5 border-emerald-500/30">
                        <h4 class="text-sm font-bold text-emerald-400 mb-2 flex items-center gap-1.5">
                            <i data-lucide="shield-check" class="w-4 h-4"></i>
                            <span>نقاط قوت (Strengths)</span>
                        </h4>
                        <ul class="space-y-1.5 text-xs text-slate-300 list-disc list-inside">
                            <li>برتری عملکردی در حوزه <strong>${strongestDim.label}</strong> با امتیاز ${toPersianDigits(sortedDims[0][1])}٪.</li>
                            <li>انطباق بالای تسک‌های کلیدی با ساعات پربازده کواکب (به‌ویژه ساعت ${activeHour.planet.name}).</li>
                            <li>شتاب رشد فیبوناچی مثبت (${toPersianDigits((1 + (metrics.completionRate / 100) * 0.618).toFixed(2))}x) در تکمیل اهداف اولویت‌دار.</li>
                        </ul>
                    </div>

                    <div class="luxury-card rounded-2xl p-5 border-amber-500/30">
                        <h4 class="text-sm font-bold text-amber-400 mb-2 flex items-center gap-1.5">
                            <i data-lucide="alert-circle" class="w-4 h-4"></i>
                            <span>نقاط قابل بهبود و گلوگاه‌ها (Weaknesses)</span>
                        </h4>
                        <ul class="space-y-1.5 text-xs text-slate-300 list-disc list-inside">
                            <li>شکاف عملکردی در بُعد <strong>${weakestDim.label}</strong> نسبت به پتانسیل کیهانی روز.</li>
                            <li>وجود ${toPersianDigits(appState.tasks.filter(t => t.status === 'pending').length)} تسک در وضعیت انتظار که نیازمند زمان‌بندی در ساعات مشتری یا عطارد هستند.</li>
                            <li>لزوم متعادل‌سازی زمان بین کارهای عملیاتی و استراحت/بازیابی انرژی.</li>
                        </ul>
                    </div>

                    <div class="luxury-card rounded-2xl p-5 border-cyber/30">
                        <h4 class="text-sm font-bold text-cyber mb-2 flex items-center gap-1.5">
                            <i data-lucide="sparkles" class="w-4 h-4"></i>
                            <span>فرصت‌های کیهانی و تجاری (Opportunities)</span>
                        </h4>
                        <ul class="space-y-1.5 text-xs text-slate-300 list-disc list-inside">
                            <li>بهره‌گیری از انرژی صورت فلکی <strong>${tSun.sign.name.split(' ')[0]}</strong> برای ${tSun.sign.traits}.</li>
                            <li>استفاده از پنجره طلایی روزانه برای پیشبرد مذاکرات مالی و جذب شرکای جدید.</li>
                            <li>هم‌افزایی طالع شخصی شما (${natal.bodies.find(b => b.id === 'asc').sign.name.split(' ')[0]}) با ترانزیت‌های جاری.</li>
                        </ul>
                    </div>

                    <div class="luxury-card rounded-2xl p-5 border-rose-500/30">
                        <h4 class="text-sm font-bold text-rose-400 mb-2 flex items-center gap-1.5">
                            <i data-lucide="shield-alert" class="w-4 h-4"></i>
                            <span>تهدیدها و هشدارهای نجومی (Threats)</span>
                        </h4>
                        <ul class="space-y-1.5 text-xs text-slate-300 list-disc list-inside">
                            <li>${transit.isMoonInScorpio ? '<strong class="text-rose-300">هشدار فعال قمر در عقرب:</strong> از امضای قراردادهای نهایی و تصمیمات هیجانی خودداری کنید.' : 'زوایای تربیع/مقابله احتمالی در ساعات زحل و مریخ ممکن است باعث تنش در مذاکرات شوند.'}</li>
                            <li>ریسک فرسودگی در صورت تداوم کار در ساعات افت انرژی قمر بدون برنامه‌ریزی.</li>
                        </ul>
                    </div>
                </div>

                <div class="luxury-card geo-corner rounded-2xl p-5">
                    <h4 class="text-sm font-bold text-gold-light mb-3 flex items-center gap-1.5">
                        <i data-lucide="calendar-range" class="w-4 h-4 text-gold"></i>
                        <span>۲. نقشه راه و پیش‌بینی انرژی کیهانی ۷ روز آینده</span>
                    </h4>
                    <div class="overflow-x-auto">
                        <table class="w-full text-right text-xs border-collapse">
                            <thead>
                                <tr class="border-b border-gold/25 text-gold-light">
                                    <th class="py-2.5 px-3">تاریخ شمسی</th>
                                    <th class="py-2.5 px-3">موقعیت قمر (IAU)</th>
                                    <th class="py-2.5 px-3">فاز ماه</th>
                                    <th class="py-2.5 px-3">شاخص انرژی اجرایی</th>
                                    <th class="py-2.5 px-3">توصیه استراتژیک روز</th>
                                </tr>
                            </thead>
                            <tbody class="divide-y divide-gold/10 text-slate-300">
                                ${forecast7Days.map(day => `
                                    <tr class="hover:bg-gold/5 transition">
                                        <td class="py-2.5 px-3 font-semibold text-slate-100">${day.dateStr}</td>
                                        <td class="py-2.5 px-3 text-cyber">${day.moonSign}</td>
                                        <td class="py-2.5 px-3">${day.phase}</td>
                                        <td class="py-2.5 px-3">
                                            <span class="px-2 py-0.5 rounded-full font-bold ${day.energyScore >= 80 ? 'bg-emerald-500/20 text-emerald-300' : 'bg-gold/15 text-gold'}">
                                                ${toPersianDigits(day.energyScore)}٪
                                            </span>
                                        </td>
                                        <td class="py-2.5 px-3 text-slate-300">${day.focus}</td>
                                    </tr>
                                `).join('')}
                            </tbody>
                        </table>
                    </div>
                </div>
            `;

            lucide.createIcons();
        }

        function copyReportToClipboard() {
            const reportEl = document.getElementById('executive-report-content');
            const text = reportEl.innerText;
            const textarea = document.createElement('textarea');
            textarea.value = text;
            document.body.appendChild(textarea);
            textarea.select();
            try {
                document.execCommand('copy');
                showToast('متن کامل گزارش تحلیلی در حافظه (Clipboard) کپی شد.', 'success');
            } catch (err) {
                showToast('خطا در کپی کردن متن گزارش.', 'error');
            }
            document.body.removeChild(textarea);
        }

        // ============================================================================
        // ۷. کنترل تب‌ها و سیستم نوتیفیکیشن اختصاصی
        // ============================================================================

        function switchTab(tabName) {
            ['dashboard', 'planner', 'report'].forEach(t => {
                document.getElementById(`view-${t}`).classList.add('hidden');
                const btn = document.getElementById(`tab-btn-${t}`);
                btn.classList.remove('bg-gold', 'text-obsidian', 'font-bold', 'shadow-gold-glow');
                btn.classList.add('text-slate-300', 'font-medium');
            });

            document.getElementById(`view-${tabName}`).classList.remove('hidden');
            const activeBtn = document.getElementById(`tab-btn-${tabName}`);
            activeBtn.classList.remove('text-slate-300', 'font-medium');
            activeBtn.classList.add('bg-gold', 'text-obsidian', 'font-bold', 'shadow-gold-glow');
            lucide.createIcons();
        }

        function showToast(message, type = 'info') {
            const container = document.getElementById('toast-container');
            const toast = document.createElement('div');
            const colors = {
                success: 'border-emerald-500/60 bg-deepnavy/95 text-emerald-300',
                info: 'border-gold/60 bg-deepnavy/95 text-gold-light',
                error: 'border-rose-500/60 bg-deepnavy/95 text-rose-300'
            };
            toast.className = `pointer-events-auto px-4 py-3 rounded-xl border shadow-luxury backdrop-blur-xl text-xs font-semibold flex items-center justify-between gap-3 transition-all duration-300 ${colors[type]}`;
            toast.innerHTML = `
                <span>${message}</span>
                <span class="w-2 h-2 rounded-full bg-current"></span>
            `;
            container.appendChild(toast);
            setTimeout(() => {
                toast.style.opacity = '0';
                toast.style.transform = 'translateY(10px)';
                setTimeout(() => toast.remove(), 300);
            }, 3200);
        }

        window.addEventListener('DOMContentLoaded', initApp);
    </script>
</body>
</html>
