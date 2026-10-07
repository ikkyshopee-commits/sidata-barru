# sidata-barru
Portal Data Perkawinan dan Perceraian Kabupaten Barru
<!DOCTYPE html>
<html lang="id" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sidata Barru - Portal Data Perkawinan & Perceraian</title>

    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    
    <!-- Font Awesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <!-- Google Fonts: Inter -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    
    <!-- Chart.js CDN for Visualizations -->
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>

    <!-- Tailwind Custom Configuration -->
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        navy: {
                            50: '#f0f4f8',
                            100: '#d9e2ec',
                            500: '#334e68',
                            800: '#102a43',
                            900: '#0b1b2b',
                        },
                        gold: {
                            400: '#fbbf24',
                            500: '#f59e0b',
                            600: '#d97706',
                        },
                        tealAccent: {
                            500: '#14b8a6',
                            600: '#0d9488',
                        }
                    },
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                    }
                }
            }
        }
    </script>

    <style>
        /* Custom Custom Scrollbar & Utility Animations */
        ::-webkit-scrollbar {
            width: 8px;
            height: 8px;
        }
        ::-webkit-scrollbar-track {
            background: #f1f5f9;
        }
        ::-webkit-scrollbar-thumb {
            background: #cbd5e1;
            border-radius: 4px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #94a3b8;
        }
        .gradient-bg {
            background: linear-gradient(135deg, #0b1b2b 0%, #102a43 60%, #1e3a5f 100%);
        }
        .gold-gradient-text {
            background: linear-gradient(135deg, #fef08a 0%, #f59e0b 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
    </style>
</head>
<body class="bg-slate-50 text-slate-800 font-sans antialiased min-h-screen flex flex-col justify-between">

    <!-- NAVIGATION BAR -->
    <header class="sticky top-0 z-50 bg-navy-900/95 backdrop-blur-md border-b border-navy-800 text-white shadow-lg">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between items-center h-20">
                <!-- Logo & Brand -->
                <div class="flex items-center space-x-3 cursor-pointer" onclick="window.scrollTo({top: 0, behavior: 'smooth'})">
                    <div class="w-11 h-11 rounded-xl bg-gradient-to-tr from-gold-500 to-tealAccent-500 flex items-center justify-center text-navy-900 shadow-md">
                        <i class="fa-solid fa-hands-holding-child text-2xl"></i>
                    </div>
                    <div>
                        <span class="text-xl font-extrabold tracking-tight text-white block leading-none">Sidata <span class="gold-gradient-text">Barru</span></span>
                        <span class="text-[10px] text-slate-300 font-medium tracking-wider uppercase">Kabupaten Barru, Sulsel</span>
                    </div>
                </div>

                <!-- Desktop Menu -->
                <nav class="hidden md:flex space-x-1 lg:space-x-2 font-medium text-sm">
                    <a href="#beranda" class="px-3 py-2 rounded-lg hover:bg-navy-800 transition text-slate-200 hover:text-white">Beranda</a>
                    <a href="#statistik" class="px-3 py-2 rounded-lg hover:bg-navy-800 transition text-slate-200 hover:text-white">Statistik Ringkas</a>
                    <a href="#grafik" class="px-3 py-2 rounded-lg hover:bg-navy-800 transition text-slate-200 hover:text-white">Grafik & Analisis</a>
                    <a href="#tabel-data" class="px-3 py-2 rounded-lg hover:bg-navy-800 transition text-slate-200 hover:text-white">Tabel Kecamatan</a>
                    <a href="#edukasi" class="px-3 py-2 rounded-lg hover:bg-navy-800 transition text-slate-200 hover:text-white">Layanan & Edukasi</a>
                </nav>

                <!-- Actions CTA -->
                <div class="hidden lg:flex items-center space-x-3">
                    <a href="#tabel-data" class="bg-gold-500 hover:bg-gold-600 text-navy-900 font-semibold px-4 py-2 rounded-lg transition shadow-md flex items-center text-xs">
                        <i class="fa-solid fa-magnifying-glass mr-2"></i> Cari Data
                    </a>
                </div>

                <!-- Mobile Menu Button -->
                <div class="md:hidden flex items-center">
                    <button id="mobile-menu-btn" class="p-2 rounded-md text-slate-300 hover:text-white hover:bg-navy-800 focus:outline-none">
                        <i class="fa-solid fa-bars text-xl"></i>
                    </button>
                </div>
            </div>
        </div>

        <!-- Mobile Dropdown Menu -->
        <div id="mobile-menu" class="hidden md:hidden bg-navy-900 border-b border-navy-800 px-4 pt-2 pb-4 space-y-2">
            <a href="#beranda" class="block px-3 py-2 rounded-md text-base font-medium text-slate-200 hover:bg-navy-800">Beranda</a>
            <a href="#statistik" class="block px-3 py-2 rounded-md text-base font-medium text-slate-200 hover:bg-navy-800">Statistik Ringkas</a>
            <a href="#grafik" class="block px-3 py-2 rounded-md text-base font-medium text-slate-200 hover:bg-navy-800">Grafik & Analisis</a>
            <a href="#tabel-data" class="block px-3 py-2 rounded-md text-base font-medium text-slate-200 hover:bg-navy-800">Tabel Kecamatan</a>
            <a href="#edukasi" class="block px-3 py-2 rounded-md text-base font-medium text-slate-200 hover:bg-navy-800">Layanan & Edukasi</a>
        </div>
    </header>

    <main class="flex-grow">
        <!-- HERO SECTION -->
        <section id="beranda" class="gradient-bg text-white relative overflow-hidden py-16 lg:py-24">
            <!-- Background Elements -->
            <div class="absolute inset-0 opacity-10 bg-[radial-gradient(#fff_1px,transparent_1px)] [background-size:16px_16px]"></div>
            <div class="absolute -right-20 -bottom-20 w-96 h-96 bg-tealAccent-500/20 rounded-full blur-3xl"></div>
            <div class="absolute -left-20 -top-20 w-96 h-96 bg-gold-500/10 rounded-full blur-3xl"></div>

            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
                <div class="grid lg:grid-cols-12 gap-12 items-center">
                    
                    <!-- Left Copywriting -->
                    <div class="lg:col-span-7 space-y-6 text-center lg:text-left">
                        <div class="inline-flex items-center space-x-2 bg-navy-800/80 border border-navy-500/40 text-gold-400 text-xs font-semibold px-3 py-1.5 rounded-full">
                            <span class="w-2 h-2 rounded-full bg-gold-400 animate-pulse"></span>
                            <span>Portal Resmi Pengolahan Data KUA & Pengadilan Agama</span>
                        </div>
                        
                        <h1 class="text-3xl sm:text-4xl lg:text-5xl font-extrabold tracking-tight leading-tight">
                            Transparansi Data Perkawinan & Perceraian <span class="gold-gradient-text">Kabupaten Barru</span>
                        </h1>
                        
                        <p class="text-slate-300 text-base sm:text-lg max-w-2xl font-light leading-relaxed">
                            Akses statistik terpadu mengenai dinamika pernikahan, angka permohonan dispensasi usia dini, hingga faktor pemicu perceraian untuk mendukung kebijakan sosial dan ketahanan keluarga di Kabupaten Barru.
                        </p>

                        <div class="flex flex-col sm:flex-row justify-center lg:justify-start gap-4 pt-2">
                            <a href="#tabel-data" class="bg-gold-500 hover:bg-gold-600 text-navy-900 font-bold px-6 py-3.5 rounded-xl transition shadow-lg flex items-center justify-center">
                                <i class="fa-solid fa-chart-column mr-2"></i> Jelajahi Data Wilayah
                            </a>
                            <button onclick="downloadReportModal()" class="bg-navy-800/80 hover:bg-navy-800 text-white border border-slate-600 font-semibold px-6 py-3.5 rounded-xl transition flex items-center justify-center">
                                <i class="fa-solid fa-file-pdf mr-2 text-rose-400"></i> Unduh Laporan Tahunan
                            </button>
                        </div>
                    </div>

                    <!-- Right Quick Filter Widget -->
                    <div class="lg:col-span-5 bg-navy-800/90 backdrop-blur-md p-6 rounded-2xl border border-navy-500/40 shadow-2xl">
                        <div class="border-b border-navy-700 pb-4 mb-4 flex items-center justify-between">
                            <h3 class="font-bold text-lg text-white flex items-center">
                                <i class="fa-solid fa-sliders text-gold-400 mr-2"></i> Filter Cepat Statistik
                            </h3>
                            <span class="text-xs bg-tealAccent-500/20 text-tealAccent-500 font-medium px-2.5 py-1 rounded-md">Live Preview</span>
                        </div>

                        <form id="hero-filter-form" class="space-y-4 text-slate-200">
                            <div>
                                <label class="block text-xs font-semibold mb-1.5 uppercase text-slate-400">Tahun Periode</label>
                                <select id="filter-tahun" class="w-full bg-navy-900 border border-navy-600 rounded-lg px-3 py-2.5 text-sm text-white focus:outline-none focus:border-gold-500">
                                    <option value="2025" selected>2025 (Tahun Berjalan)</option>
                                    <option value="2024">2024</option>
                                    <option value="2023">2023</option>
                                    <option value="2022">2022</option>
                                    <option value="2021">2021</option>
                                </select>
                            </div>

                            <div>
                                <label class="block text-xs font-semibold mb-1.5 uppercase text-slate-400">Kecamatan (Kab. Barru)</label>
                                <select id="filter-kecamatan" class="w-full bg-navy-900 border border-navy-600 rounded-lg px-3 py-2.5 text-sm text-white focus:outline-none focus:border-gold-500">
                                    <option value="ALL" selected>Semua Kecamatan (7 Wilayah)</option>
                                    <option value="Barru">Kecamatan Barru</option>
                                    <option value="Tanete Rilau">Kecamatan Tanete Rilau</option>
                                    <option value="Tanete Riaja">Kecamatan Tanete Riaja</option>
                                    <option value="Soppeng Riaja">Kecamatan Soppeng Riaja</option>
                                    <option value="Balusu">Kecamatan Balusu</option>
                                    <option value="Mallusetasi">Kecamatan Mallusetasi</option>
                                    <option value="Pujananting">Kecamatan Pujananting</option>
                                </select>
                            </div>

                            <div class="pt-2">
                                <button type="button" onclick="applyFilters()" class="w-full bg-gradient-to-r from-tealAccent-500 to-tealAccent-600 hover:from-tealAccent-600 hover:to-tealAccent-600 text-white font-bold py-3 rounded-lg shadow-md transition flex items-center justify-center">
                                    <i class="fa-solid fa-filter mr-2"></i> Tampilkan Statistik
                                </button>
                            </div>
                        </form>
                    </div>

                </div>
            </div>
        </section>

        <!-- SUMMARY METRIC CARDS -->
        <section id="statistik" class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 -mt-10 relative z-20">
            <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-5">
                
                <!-- Card 1: Total Perkawinan -->
                <div class="bg-white rounded-2xl p-6 shadow-xl border border-slate-100 flex items-center justify-between hover:translate-y-[-2px] transition duration-300">
                    <div>
                        <p class="text-xs font-bold uppercase tracking-wider text-slate-400">Pernikahan Terdaftar</p>
                        <h3 id="stat-nikah" class="text-3xl font-extrabold text-navy-900 mt-1">1,245</h3>
                        <p class="text-xs text-emerald-600 font-medium mt-1 flex items-center">
                            <i class="fa-solid fa-arrow-up mr-1"></i> +3.2% dibanding 2024
                        </p>
                    </div>
                    <div class="w-14 h-14 bg-emerald-50 rounded-2xl flex items-center justify-center text-emerald-600">
                        <i class="fa-solid fa-heart text-2xl"></i>
                    </div>
                </div>

                <!-- Card 2: Total Perceraian -->
                <div class="bg-white rounded-2xl p-6 shadow-xl border border-slate-100 flex items-center justify-between hover:translate-y-[-2px] transition duration-300">
                    <div>
                        <p class="text-xs font-bold uppercase tracking-wider text-slate-400">Total Perceraian</p>
                        <h3 id="stat-cerai" class="text-3xl font-extrabold text-navy-900 mt-1">284</h3>
                        <p class="text-xs text-rose-500 font-medium mt-1 flex items-center">
                            <i class="fa-solid fa-arrow-down mr-1"></i> -1.8% dari tahun lalu
                        </p>
                    </div>
                    <div class="w-14 h-14 bg-rose-50 rounded-2xl flex items-center justify-center text-rose-500">
                        <i class="fa-solid fa-heart-crack text-2xl"></i>
                    </div>
                </div>

                <!-- Card 3: Pernikahan Dini / Dispensasi -->
                <div class="bg-white rounded-2xl p-6 shadow-xl border border-slate-100 flex items-center justify-between hover:translate-y-[-2px] transition duration-300">
                    <div>
                        <p class="text-xs font-bold uppercase tracking-wider text-slate-400">Dispensasi Nikah</p>
                        <h3 id="stat-dispensasi" class="text-3xl font-extrabold text-navy-900 mt-1">32</h3>
                        <p class="text-xs text-amber-600 font-medium mt-1 flex items-center">
                            <i class="fa-solid fa-triangle-exclamation mr-1"></i> Perlu Atensi Khusus
                        </p>
                    </div>
                    <div class="w-14 h-14 bg-amber-50 rounded-2xl flex items-center justify-center text-amber-500">
                        <i class="fa-solid fa-child text-2xl"></i>
                    </div>
                </div>

                <!-- Card 4: Tingkat Mediasi -->
                <div class="bg-white rounded-2xl p-6 shadow-xl border border-slate-100 flex items-center justify-between hover:translate-y-[-2px] transition duration-300">
                    <div>
                        <p class="text-xs font-bold uppercase tracking-wider text-slate-400">Keberhasilan Mediasi</p>
                        <h3 id="stat-mediasi" class="text-3xl font-extrabold text-navy-900 mt-1">41.5%</h3>
                        <p class="text-xs text-teal-600 font-medium mt-1 flex items-center">
                            <i class="fa-solid fa-handshake mr-1"></i> Pengadilan Agama Barru
                        </p>
                    </div>
                    <div class="w-14 h-14 bg-teal-50 rounded-2xl flex items-center justify-center text-teal-600">
                        <i class="fa-solid fa-scale-balanced text-2xl"></i>
                    </div>
                </div>

            </div>
        </section>

        <!-- CHART VISUALIZATIONS SECTION -->
        <section id="grafik" class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-16">
            <div class="text-center max-w-3xl mx-auto mb-12">
                <span class="text-gold-600 font-bold text-xs uppercase tracking-widest bg-amber-100 px-3 py-1 rounded-full">Visualisasi Data</span>
                <h2 class="text-3xl font-extrabold text-navy-900 mt-3">Analisis Grafis & Tren Sosial</h2>
                <p class="text-slate-600 mt-2">Gambaran visual distribusi perkawinan, tren tahunan, serta faktor penyebab dominan perceraian di Kabupaten Barru.</p>
            </div>

            <!-- Grid Charts Layout -->
            <div class="grid grid-cols-1 lg:grid-cols-12 gap-8">
                
                <!-- Chart 1: Tren 5 Tahun -->
                <div class="lg:col-span-7 bg-white p-6 rounded-2xl shadow-md border border-slate-200">
                    <div class="flex items-center justify-between mb-6">
                        <div>
                            <h3 class="font-bold text-lg text-navy-900">Tren Perkawinan vs Perceraian</h3>
                            <p class="text-xs text-slate-500">Perbandingan data historis periode 2021 - 2025</p>
                        </div>
                        <span class="text-xs bg-slate-100 text-slate-600 px-2.5 py-1 rounded-md font-medium"><i class="fa-regular fa-clock mr-1"></i> 5 Tahun</span>
                    </div>
                    <div class="relative h-72 w-full">
                        <canvas id="chartTren"></canvas>
                    </div>
                </div>

                <!-- Chart 2: Faktor Penyebab Perceraian -->
                <div class="lg:col-span-5 bg-white p-6 rounded-2xl shadow-md border border-slate-200">
                    <div class="flex items-center justify-between mb-6">
                        <div>
                            <h3 class="font-bold text-lg text-navy-900">Faktor Utama Perceraian</h3>
                            <p class="text-xs text-slate-500">Persentase alasan perkara gugatan</p>
                        </div>
                        <i class="fa-solid fa-chart-pie text-slate-400"></i>
                    </div>
                    <div class="relative h-72 w-full flex justify-center">
                        <canvas id="chartFaktor"></canvas>
                    </div>
                </div>

                <!-- Chart 3: Perbandingan Per Kecamatan -->
                <div class="lg:col-span-12 bg-white p-6 rounded-2xl shadow-md border border-slate-200">
                    <div class="flex flex-col sm:flex-row sm:items-center justify-between mb-6 gap-2">
                        <div>
                            <h3 class="font-bold text-lg text-navy-900">Distribusi Kasus Per Kecamatan</h3>
                            <p class="text-xs text-slate-500">Data angka pernikahan dan permohonan cerai per wilayah di Barru</p>
                        </div>
                        <div class="flex space-x-2 text-xs">
                            <span class="inline-flex items-center text-slate-600"><span class="w-3 h-3 bg-emerald-500 rounded-sm mr-1"></span> Perkawinan</span>
                            <span class="inline-flex items-center text-slate-600"><span class="w-3 h-3 bg-rose-500 rounded-sm mr-1"></span> Perceraian</span>
               