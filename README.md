<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>AI Promo Studio — Premium AI Campaign Platform</title>
<script src="https://cdn.tailwindcss.com"></script>
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&family=DM+Sans:ital,opsz,wght@0,9..40,300;0,9..40,400;0,9..40,500;0,9..40,600;0,9..40,700;1,9..40,400&display=swap" rel="stylesheet">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
<script src="https://cdnjs.cloudflare.com/ajax/libs/html2pdf.js/0.10.1/html2pdf.bundle.min.js"></script>
<script>
tailwind.config={theme:{extend:{colors:{srf:{900:'#09090b',800:'#0e0e11',700:'#141417',600:'#1a1a1e',500:'#222228',400:'#2a2a31',300:'#3a3a42'},txt:{50:'#f5f0e8',100:'#d8d3ca',200:'#9a958d',300:'#6a655e'},brd:{DEFAULT:'#232329',hover:'#3a3a42'},accent:{light:'#f0b848',DEFAULT:'#e8a030',dark:'#c88820',darker:'#a06810',glow:'rgba(232,160,48,0.12)'}},fontFamily:{display:['"Space Grotesk"','sans-serif'],body:['"DM Sans"','sans-serif']}}}}
</script>
<style>
*{scrollbar-width:thin;scrollbar-color:#2a2a31 transparent}
::-webkit-scrollbar{width:6px}::-webkit-scrollbar-track{background:transparent}::-webkit-scrollbar-thumb{background:#2a2a31;border-radius:3px}
body{font-family:'DM Sans',sans-serif;background:#09090b;color:#f5f0e8;overflow:hidden;height:100vh}
.nav-item{color:#9a958d;position:relative}.nav-item:hover{color:#f5f0e8;background:#1a1a1e}
.nav-item.active{color:#f5f0e8;background:rgba(232,160,48,0.07);box-shadow:inset 3px 0 0 #e8a030}
.view-section{display:none;height:100%;overflow-y:auto;padding:2rem}.view-section.active{display:block}
.step-panel{display:none;animation:fadeSlideIn .4s ease}.step-panel.active{display:block}
@keyframes fadeSlideIn{from{opacity:0;transform:translateX(30px)}to{opacity:1;transform:translateX(0)}}
@keyframes fadeIn{from{opacity:0}to{opacity:1}}
@keyframes pulse-glow{0%,100%{box-shadow:0 0 20px rgba(232,160,48,0.25)}50%{box-shadow:0 0 40px rgba(232,160,48,0.45)}}
@keyframes bar-fill{from{width:0}to{width:var(--bar-w)}}
.gen-btn{background:linear-gradient(135deg,#e8a030,#c88820);animation:pulse-glow 3s ease-in-out infinite;transition:all .3s}
.gen-btn:hover{transform:translateY(-2px);box-shadow:0 0 50px rgba(232,160,48,0.5)!important}
.stat-card{transition:all .3s}.stat-card:hover{border-color:rgba(232,160,48,0.3);transform:translateY(-2px);box-shadow:0 8px 30px rgba(0,0,0,0.3)}
.hook-card{transition:all .3s;cursor:pointer}.hook-card:hover{border-color:#3a3a42;background:#1a1a1e}
.hook-card.selected{border-color:#e8a030;background:rgba(232,160,48,0.06);box-shadow:0 0 20px rgba(232,160,48,0.1)}
.option-card{transition:all .3s;cursor:pointer}.option-card:hover{border-color:#3a3a42}
.option-card.selected{border-color:#e8a030;background:rgba(232,160,48,0.06)}
.upload-zone{border:2px dashed #2a2a31;transition:all .3s}.upload-zone:hover,.upload-zone.dragover{border-color:#e8a030;background:rgba(232,160,48,0.04)}
.tag{display:inline-flex;align-items:center;gap:6px;padding:4px 10px;border-radius:6px;font-size:12px;background:rgba(232,160,48,0.1);color:#f0b848;border:1px solid rgba(232,160,48,0.2)}
.tag button{cursor:pointer;opacity:.6;transition:opacity .2s}.tag button:hover{opacity:1}
.bg-orb{position:fixed;border-radius:50%;filter:blur(80px);opacity:.07;pointer-events:none;z-index:0}
.score-bar{height:6px;border-radius:3px;background:#222228;overflow:hidden}
.score-bar-fill{height:100%;border-radius:3px;animation:bar-fill 1s ease forwards;width:var(--bar-w)}
.overlay-modal{position:fixed;inset:0;background:rgba(9,9,11,0.9);z-index:100;display:flex;align-items:center;justify-content:center;backdrop-filter:blur(10px)}
.gen-stage.done .stage-icon{color:#4ade80}
.script-section{border-left:3px solid #2a2a31;padding-left:12px;margin-bottom:12px}
.script-section .section-label{font-size:10px;text-transform:uppercase;letter-spacing:1.5px;color:#e8a030;font-weight:600;margin-bottom:4px}
input,textarea,select{background:#141417;border:1px solid #232329;color:#f5f0e8;border-radius:8px;padding:10px 14px;font-size:14px;font-family:'DM Sans',sans-serif;transition:border-color .2s;width:100%;outline:none}
input:focus,textarea:focus,select:focus{border-color:#e8a030}
input::placeholder,textarea::placeholder{color:#6a655e}
select option{background:#141417;color:#f5f0e8}
.toast{position:fixed;bottom:24px;right:24px;padding:12px 20px;border-radius:10px;font-size:14px;z-index:200;animation:fadeIn .3s ease;transition:opacity .3s}
.char-tab{padding:8px 20px;border-radius:8px;font-size:13px;font-weight:500;cursor:pointer;transition:all .2s;color:#9a958d}
.char-tab.active{background:rgba(232,160,48,0.1);color:#e8a030}
.range-slider{-webkit-appearance:none;width:100%;height:4px;border-radius:2px;background:#222228;outline:none}
.range-slider::-webkit-slider-thumb{-webkit-appearance:none;width:18px;height:18px;border-radius:50%;background:#e8a030;cursor:pointer;box-shadow:0 0 10px rgba(232,160,48,0.3)}
.filter-tab{padding:6px 14px;border-radius:8px;font-size:12px;font-weight:500;cursor:pointer;transition:all .2s;color:#9a958d;border:1px solid transparent}
.filter-tab:hover{color:#f5f0e8}.filter-tab.active{background:rgba(232,160,48,0.08);color:#e8a030;border-color:rgba(232,160,48,0.2)}
.persist-badge{font-size:9px;padding:1px 6px;border-radius:4px;background:rgba(74,222,128,0.1);color:#4ade80;border:1px solid rgba(74,222,128,0.2)}
.pdf-export-zone{display:none}
@media print{.no-print{display:none!important}.pdf-export-zone{display:block!important}}
@media(max-width:1023px){.view-section{padding:1rem}.sidebar-open #sidebar{transform:translateX(0)!important}}
</style>
</head>
<body>
<div class="bg-orb" style="width:500px;height:500px;background:#e8a030;top:-150px;right:-100px"></div>
<div class="bg-orb" style="width:400px;height:400px;background:#c88820;bottom:-100px;left:-100px"></div>

<div id="app" class="flex h-screen relative z-10">
<aside id="sidebar" class="fixed left-0 top-0 h-full w-64 bg-srf-800/95 backdrop-blur-xl border-r border-brd flex flex-col z-50 transition-transform duration-300 lg:translate-x-0 -translate-x-full">
    <div class="p-5 border-b border-brd">
        <div class="flex items-center gap-3">
            <div class="w-9 h-9 rounded-lg bg-gradient-to-br from-accent-light to-accent-dark flex items-center justify-center flex-shrink-0"><i class="fa-solid fa-wand-magic-sparkles text-srf-900 text-sm"></i></div>
            <div><h1 class="font-display font-bold text-base text-txt-50 leading-tight">AI Promo Studio</h1><p class="text-[10px] text-txt-200 uppercase tracking-[0.15em]">Premium Platform</p></div>
        </div>
    </div>
    <nav class="flex-1 py-3 px-3 space-y-0.5 overflow-y-auto">
        <button onclick="navigateTo('dashboard')" data-nav="dashboard" class="nav-item active w-full flex items-center gap-3 px-3 py-2.5 rounded-lg text-sm"><i class="fa-solid fa-table-columns w-5 text-center text-xs"></i><span>Dashboard</span></button>
        <button onclick="navigateTo('campaign')" data-nav="campaign" class="nav-item w-full flex items-center gap-3 px-3 py-2.5 rounded-lg text-sm"><i class="fa-solid fa-wand-magic-sparkles w-5 text-center text-xs"></i><span>Create Campaign</span></button>
        <button onclick="navigateTo('characters')" data-nav="characters" class="nav-item w-full flex items-center gap-3 px-3 py-2.5 rounded-lg text-sm"><i class="fa-solid fa-user-group w-5 text-center text-xs"></i><span>Saved Characters</span></button>
        <button onclick="navigateTo('hooks')" data-nav="hooks" class="nav-item w-full flex items-center gap-3 px-3 py-2.5 rounded-lg text-sm"><i class="fa-solid fa-anchor w-5 text-center text-xs"></i><span>Hook Library</span></button>
        <button onclick="navigateTo('templates')" data-nav="templates" class="nav-item w-full flex items-center gap-3 px-3 py-2.5 rounded-lg text-sm"><i class="fa-solid fa-layer-group w-5 text-center text-xs"></i><span>Templates</span></button>
        <button onclick="navigateTo('analytics')" data-nav="analytics" class="nav-item w-full flex items-center gap-3 px-3 py-2.5 rounded-lg text-sm"><i class="fa-solid fa-chart-line w-5 text-center text-xs"></i><span>Analytics</span></button>
        <div class="pt-3 mt-3 border-t border-brd">
            <button onclick="navigateTo('settings')" data-nav="settings" class="nav-item w-full flex items-center gap-3 px-3 py-2.5 rounded-lg text-sm"><i class="fa-solid fa-gear w-5 text-center text-xs"></i><span>Settings</span></button>
        </div>
    </nav>
    <div class="p-4 border-t border-brd">
        <div class="flex items-center justify-between mb-2">
            <span class="persist-badge"><i class="fa-solid fa-bolt mr-1"></i>Instant Mode</span>
        </div>
        <div class="flex items-center gap-3">
            <div class="w-9 h-9 rounded-full bg-gradient-to-br from-accent to-accent-dark flex items-center justify-center text-srf-900 font-bold text-sm flex-shrink-0">J</div>
            <div class="min-w-0"><p class="text-sm font-medium text-txt-50 truncate" id="sidebarUserName">John Doe</p><p class="text-xs text-accent">Pro Plan</p></div>
        </div>
    </div>
</aside>
<div id="sidebarOverlay" class="fixed inset-0 bg-black/50 z-40 hidden lg:hidden" onclick="toggleSidebar()"></div>

<main class="flex-1 h-screen overflow-hidden relative">
    <div class="lg:hidden flex items-center gap-3 px-4 py-3 border-b border-brd bg-srf-800/80 backdrop-blur-xl no-print">
        <button onclick="toggleSidebar()" class="w-9 h-9 rounded-lg bg-srf-700 flex items-center justify-center text-txt-200"><i class="fa-solid fa-bars text-sm"></i></button>
        <span class="font-display font-semibold text-sm text-txt-50">AI Promo Studio</span>
    </div>

<!-- DASHBOARD -->
<section id="viewDashboard" class="view-section active">
<div class="max-w-7xl mx-auto">
    <div class="mb-8"><h2 class="font-display text-2xl md:text-3xl font-bold text-txt-50 mb-1">Welcome back, <span id="dashName">John</span></h2><p class="text-txt-200 text-sm">Campaign performance overview — data tersimpan lokal</p></div>
    <div class="grid grid-cols-1 sm:grid-cols-2 xl:grid-cols-4 gap-4 mb-8">
        <div class="stat-card bg-srf-700 border border-brd rounded-xl p-5"><div class="flex items-center justify-between mb-3"><div class="w-10 h-10 rounded-lg bg-accent/10 flex items-center justify-center"><i class="fa-solid fa-rocket text-accent text-sm"></i></div><span class="text-xs text-green-400 bg-green-400/10 px-2 py-0.5 rounded-full font-medium">+12%</span></div><p class="text-2xl font-display font-bold text-txt-50" id="statCampaigns">0</p><p class="text-sm text-txt-200">Campaigns Created</p></div>
        <div class="stat-card bg-srf-700 border border-brd rounded-xl p-5"><div class="flex items-center justify-between mb-3"><div class="w-10 h-10 rounded-lg bg-blue-500/10 flex items-center justify-center"><i class="fa-solid fa-bullseye text-blue-400 text-sm"></i></div><span class="text-xs text-green-400 bg-green-400/10 px-2 py-0.5 rounded-full font-medium">+5.2%</span></div><p class="text-2xl font-display font-bold text-txt-50" id="statScore">0</p><p class="text-sm text-txt-200">Avg. Quality Score</p></div>
        <div class="stat-card bg-srf-700 border border-brd rounded-xl p-5"><div class="flex items-center justify-between mb-3"><div class="w-10 h-10 rounded-lg bg-emerald-500/10 flex items-center justify-center"><i class="fa-solid fa-arrow-trend-up text-emerald-400 text-sm"></i></div><span class="text-xs text-green-400 bg-green-400/10 px-2 py-0.5 rounded-full font-medium">+18%</span></div><p class="text-2xl font-display font-bold text-txt-50" id="statConversions">0</p><p class="text-sm text-txt-200">Est. Conversions</p></div>
        <div class="stat-card bg-srf-700 border border-brd rounded-xl p-5"><div class="flex items-center justify-between mb-3"><div class="w-10 h-10 rounded-lg bg-purple-500/10 flex items-center justify-center"><i class="fa-solid fa-clock text-purple-400 text-sm"></i></div><span class="persist-badge">Local</span></div><p class="text-2xl font-display font-bold text-txt-50" id="statChars">0</p><p class="text-sm text-txt-200">Saved Characters</p></div>
    </div>
    <div class="grid grid-cols-1 xl:grid-cols-3 gap-6 mb-8">
        <div class="xl:col-span-2 bg-srf-700 border border-brd rounded-xl p-6">
            <div class="flex items-center justify-between mb-5"><h3 class="font-display font-semibold text-txt-50">Recent Campaigns</h3><button onclick="navigateTo('campaign')" class="text-xs text-accent hover:text-accent-light transition">New Campaign <i class="fa-solid fa-arrow-right ml-1"></i></button></div>
            <div class="space-y-3" id="recentCampaigns"><p class="text-sm text-txt-300 text-center py-8">Belum ada campaign. Buat campaign pertamamu.</p></div>
        </div>
        <div class="bg-srf-700 border border-brd rounded-xl p-6">
            <h3 class="font-display font-semibold text-txt-50 mb-5">Quick Actions</h3>
            <div class="space-y-3">
                <button onclick="navigateTo('campaign')" class="w-full flex items-center gap-3 p-3 rounded-lg bg-accent/8 border border-accent/15 hover:border-accent/30 transition text-left"><div class="w-9 h-9 rounded-lg bg-accent/15 flex items-center justify-center flex-shrink-0"><i class="fa-solid fa-plus text-accent text-xs"></i></div><div><p class="text-sm font-medium text-txt-50">New Campaign</p><p class="text-xs text-txt-200">Create from scratch</p></div></button>
                <button onclick="navigateTo('characters')" class="w-full flex items-center gap-3 p-3 rounded-lg bg-srf-600 border border-brd hover:border-brd-hover transition text-left"><div class="w-9 h-9 rounded-lg bg-srf-500 flex items-center justify-center flex-shrink-0"><i class="fa-solid fa-user-plus text-txt-200 text-xs"></i></div><div><p class="text-sm font-medium text-txt-50">Saved Characters</p><p class="text-xs text-txt-200">Manage characters</p></div></button>
                <button onclick="navigateTo('hooks')" class="w-full flex items-center gap-3 p-3 rounded-lg bg-srf-600 border border-brd hover:border-brd-hover transition text-left"><div class="w-9 h-9 rounded-lg bg-srf-500 flex items-center justify-center flex-shrink-0"><i class="fa-solid fa-book text-txt-200 text-xs"></i></div><div><p class="text-sm font-medium text-txt-50">Hook Library</p><p class="text-xs text-txt-200">Browse proven hooks</p></div></button>
            </div>
            <div class="mt-5 pt-5 border-t border-brd">
                <h4 class="text-xs text-txt-200 uppercase tracking-wider mb-3">Performance Trend</h4>
                <div class="flex items-end gap-1.5 h-20" id="perfChart"></div>
            </div>
        </div>
    </div>
</div>
</section>

<!-- CAMPAIGN -->
<section id="viewCampaign" class="view-section">
<div class="max-w-5xl mx-auto">
    <div id="campaignProgress" class="mb-8">
        <div class="flex items-center justify-between mb-3"><button onclick="resetCampaign()" class="text-xs text-txt-200 hover:text-txt-50 transition"><i class="fa-solid fa-arrow-left mr-1"></i> Back</button><span class="text-xs text-txt-200 font-medium" id="stepLabel">Step 1 of 6</span></div>
        <div class="flex gap-2"><div class="step-dot flex-1 h-1 rounded-full bg-accent transition-all" data-step="1"></div><div class="step-dot flex-1 h-1 rounded-full bg-srf-500 transition-all" data-step="2"></div><div class="step-dot flex-1 h-1 rounded-full bg-srf-500 transition-all" data-step="3"></div><div class="step-dot flex-1 h-1 rounded-full bg-srf-500 transition-all" data-step="4"></div><div class="step-dot flex-1 h-1 rounded-full bg-srf-500 transition-all" data-step="5"></div><div class="step-dot flex-1 h-1 rounded-full bg-srf-500 transition-all" data-step="6"></div></div>
    </div>
    
    <!-- STEP 1: Product Input -->
    <div id="step1" class="step-panel active">
        <div class="mb-6"><h2 class="font-display text-2xl font-bold text-txt-50 mb-1">Product Input</h2><p class="text-txt-200 text-sm">Upload produk dan berikan detail untuk analisis instan</p></div>
        <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
            <div><label class="block text-sm font-medium text-txt-100 mb-2">Gambar Produk</label><div id="productUploadZone" class="upload-zone rounded-xl p-8 flex flex-col items-center justify-center text-center min-h-[240px] cursor-pointer" onclick="document.getElementById('productImageInput').click()"><div id="productImagePreview" class="hidden w-full h-full"><img id="productImg" class="w-full h-full object-contain rounded-lg" src="" alt="Product"></div><div id="productUploadPlaceholder"><div class="w-14 h-14 rounded-full bg-srf-500 flex items-center justify-center mx-auto mb-3"><i class="fa-solid fa-cloud-arrow-up text-txt-200 text-xl"></i></div><p class="text-sm text-txt-100 mb-1">Drag & drop atau klik untuk upload</p><p class="text-xs text-txt-300">PNG, JPG — Max 5MB</p></div></div><input type="file" id="productImageInput" class="hidden" accept="image/*" onchange="handleProductImage(event)"></div>
            <div class="space-y-4">
                <div><label class="block text-sm font-medium text-txt-100 mb-2">Nama Produk</label><input type="text" id="productName" placeholder="Contoh: GlowSkin Serum Vitamin C"></div>
                <div><label class="block text-sm font-medium text-txt-100 mb-2">Deskripsi Produk</label><textarea id="productDesc" rows="3" placeholder="Jelaskan produk secara singkat..."></textarea></div>
                <div><label class="block text-sm font-medium text-txt-100 mb-2">Manfaat Utama</label><div class="flex gap-2"><input type="text" id="benefitInput" placeholder="Ketik manfaat lalu Enter" onkeydown="if(event.key==='Enter')addBenefitManual()"><button onclick="addBenefitManual()" class="px-3 rounded-lg bg-srf-500 border border-brd text-txt-200 hover:text-txt-50 transition flex-shrink-0"><i class="fa-solid fa-plus text-xs"></i></button></div><div id="benefitsList" class="flex flex-wrap gap-2 mt-2"></div></div>
                <div><label class="block text-sm font-medium text-txt-100 mb-2">Target Audience</label><input type="text" id="targetAudience" placeholder="Contoh: Wanita 25-40, peduli kulit"></div>
                <div><label class="block text-sm font-medium text-txt-100 mb-2">Niche Kategori</label><select id="nicheCategory"><option value="">Pilih niche...</option><option value="beauty">Beauty & Skincare</option><option value="tech">Tech & Gadget</option><option value="health">Health & Fitness</option><option value="finance">Finance & Bisnis</option><option value="fashion">Fashion & Style</option><option value="food">Food & Beverage</option><option value="home">Home & Living</option><option value="education">Education</option><option value="other">Lainnya</option></select></div>
            </div>
        </div>
        <div class="flex justify-end mt-8"><button onclick="nextStep()" class="px-6 py-2.5 rounded-lg bg-accent text-srf-900 font-semibold text-sm hover:bg-accent-light transition">Lanjutkan <i class="fa-solid fa-arrow-right ml-2"></i></button></div>
    </div>
    
    <!-- STEP 2: Niche Intelligence -->
    <div id="step2" class="step-panel">
        <div class="mb-6"><h2 class="font-display text-2xl font-bold text-txt-50 mb-1">Deep Niche Intelligence</h2><p class="text-txt-200 text-sm">Hasil analisis pasar dan strategi promosi (Instant)</p></div>
        
        <div id="nicheResults" class="space-y-5">
            <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                <div class="bg-srf-700 border border-brd rounded-xl p-5"><p class="text-xs text-accent uppercase tracking-wider mb-2 font-semibold">Niche & Sub-Niche</p><p class="text-txt-50 font-medium" id="resNiche"></p><p class="text-sm text-txt-200 mt-1" id="resSubNiche"></p></div>
                <div class="bg-srf-700 border border-brd rounded-xl p-5"><p class="text-xs text-accent uppercase tracking-wider mb-2 font-semibold">Market Maturity</p><div class="flex items-center gap-3 mt-1"><div class="flex-1 h-2 rounded-full bg-srf-500"><div id="resMaturity" class="h-full rounded-full bg-gradient-to-r from-accent-dark to-accent" style="width:0%;transition:width 1s ease"></div></div><span class="text-sm font-medium text-txt-50" id="resMaturityLabel"></span></div></div>
                <div class="bg-srf-700 border border-brd rounded-xl p-5"><p class="text-xs text-accent uppercase tracking-wider mb-2 font-semibold">Buyer Persona</p><p class="text-sm text-txt-100" id="resPersona"></p></div>
                <div class="bg-srf-700 border border-brd rounded-xl p-5"><p class="text-xs text-accent uppercase tracking-wider mb-2 font-semibold">Selected Strategy</p><div class="flex items-center gap-2 mt-1"><div class="w-8 h-8 rounded-lg bg-accent/15 flex items-center justify-center"><i class="fa-solid fa-bullseye text-accent text-xs"></i></div><p class="text-txt-50 font-medium" id="resStrategy"></p></div></div>
            </div>
            <div class="bg-srf-700 border border-brd rounded-xl p-5"><p class="text-xs text-accent uppercase tracking-wider mb-3 font-semibold">Emotional Drivers</p><div id="resDrivers" class="flex flex-wrap gap-2"></div></div>
            <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
                <div class="bg-srf-700 border border-brd rounded-xl p-5"><p class="text-xs text-red-400 uppercase tracking-wider mb-2 font-semibold">Pain Points</p><ul id="resPains" class="space-y-1.5 text-sm text-txt-100"></ul></div>
                <div class="bg-srf-700 border border-brd rounded-xl p-5"><p class="text-xs text-amber-400 uppercase tracking-wider mb-2 font-semibold">Hidden Desires</p><ul id="resDesires" class="space-y-1.5 text-sm text-txt-100"></ul></div>
                <div class="bg-srf-700 border border-brd rounded-xl p-5"><p class="text-xs text-blue-400 uppercase tracking-wider mb-2 font-semibold">Resistance Factors</p><ul id="resResistance" class="space-y-1.5 text-sm text-txt-100"></ul></div>
            </div>
            <div class="bg-srf-700 border border-brd rounded-xl p-5"><p class="text-xs text-accent uppercase tracking-wider mb-3 font-semibold">Best-Performing Promo Angles</p><div id="resAngles" class="grid grid-cols-1 sm:grid-cols-2 gap-2"></div></div>
            <div class="flex justify-between mt-6"><button onclick="prevStep()" class="px-5 py-2.5 rounded-lg bg-srf-600 border border-brd text-txt-100 text-sm hover:bg-srf-500 transition"><i class="fa-solid fa-arrow-left mr-2"></i> Kembali</button><button onclick="nextStep()" class="px-6 py-2.5 rounded-lg bg-accent text-srf-900 font-semibold text-sm hover:bg-accent-light transition">Lanjutkan <i class="fa-solid fa-arrow-right ml-2"></i></button></div>
        </div>
    </div>
    
    <!-- STEP 3: Character System -->
    <div id="step3" class="step-panel"><div class="mb-6"><h2 class="font-display text-2xl font-bold text-txt-50 mb-1">Character System</h2><p class="text-txt-200 text-sm">Pilih karakter untuk representasi visual campaign Anda</p></div><div class="flex gap-2 mb-6"><button class="char-tab active" onclick="switchCharTab('upload',this)">Upload Karakter</button><button class="char-tab" onclick="switchCharTab('generate',this)">Generate Karakter</button></div><div id="charUpload" class="grid grid-cols-1 md:grid-cols-2 gap-6"><div><label class="block text-sm font-medium text-txt-100 mb-2">Upload Gambar Karakter</label><div id="charUploadZone" class="upload-zone rounded-xl p-8 flex flex-col items-center justify-center text-center min-h-[280px] cursor-pointer" onclick="document.getElementById('charImageInput').click()"><div id="charImagePreview" class="hidden w-full h-full"><img id="charImg" class="w-full h-full object-cover rounded-lg" src="" alt="Character"></div><div id="charUploadPlaceholder"><div class="w-14 h-14 rounded-full bg-srf-500 flex items-center justify-center mx-auto mb-3"><i class="fa-solid fa-user text-txt-200 text-xl"></i></div><p class="text-sm text-txt-100 mb-1">Upload foto karakter/model</p><p class="text-xs text-txt-300">Referensi konsistensi visual</p></div></div><input type="file" id="charImageInput" class="hidden" accept="image/*" onchange="handleCharImage(event)"></div><div class="space-y-4"><div><label class="block text-sm font-medium text-txt-100 mb-2">Nama Karakter</label><input type="text" id="charName" placeholder="Contoh: Sarah"></div><div><label class="block text-sm font-medium text-txt-100 mb-2">Deskripsi Singkat</label><textarea id="charDesc" rows="4" placeholder="Ciri khas, gaya, personality..."></textarea></div><div class="bg-srf-600 border border-brd rounded-xl p-4"><div class="flex items-start gap-3"><i class="fa-solid fa-circle-info text-accent text-sm mt-0.5"></i><div><p class="text-sm text-txt-100 font-medium">Character Consistency Engine</p><p class="text-xs text-txt-200 mt-1">Identitas visual karakter tetap konsisten di seluruh output. <span class="persist-badge">Tersimpan lokal</span></p></div></div></div></div></div><div id="charGenerate" class="hidden"><div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-4"><div><label class="block text-xs font-medium text-txt-200 mb-1.5">Gender</label><select id="charGender"><option value="female">Female</option><option value="male">Male</option></select></div><div><label class="block text-xs font-medium text-txt-200 mb-1.5">Age Range</label><div class="flex items-center gap-3"><input type="range" id="charAge" class="range-slider flex-1" min="18" max="55" value="28"><span class="text-sm text-txt-50 font-medium w-8" id="charAgeVal">28</span></div></div><div><label class="block text-xs font-medium text-txt-200 mb-1.5">Ethnicity</label><select id="charEthnicity"><option value="southeast-asian">Southeast Asian</option><option value="east-asian">East Asian</option><option value="south-asian">South Asian</option><option value="caucasian">Caucasian</option><option value="latino">Latino</option><option value="african">African</option><option value="middle-eastern">Middle Eastern</option></select></div><div><label class="block text-xs font-medium text-txt-200 mb-1.5">Facial Expression</label><select id="charExpression"><option value="confident-smile">Confident Smile</option><option value="warm-friendly">Warm & Friendly</option><option value="serious-professional">Serious & Professional</option><option value="surprised-excited">Surprised & Excited</option><option value="curious-intrigued">Curious & Intrigued</option><option value="subtle-satisfaction">Subtle Satisfaction</option></select></div><div><label class="block text-xs font-medium text-txt-200 mb-1.5">Hairstyle</label><select id="charHair"><option value="long-flowing">Long Flowing</option><option value="short-modern">Short Modern</option><option value="medium-wavy">Medium Wavy</option><option value="slicked-back">Slicked Back</option><option value="curly-natural">Curly Natural</option><option value="updo-elegant">Updo Elegant</option></select></div><div><label class="block text-xs font-medium text-txt-200 mb-1.5">Clothing Style</label><select id="charClothing"><option value="casual-chic">Casual Chic</option><option value="professional-elegant">Professional Elegant</option><option value="minimalist-modern">Minimalist Modern</option><option value="sporty-active">Sporty Active</option><option value="luxury-glam">Luxury Glam</option><option value="bohemian-free">Bohemian Free</option></select></div><div><label class="block text-xs font-medium text-txt-200 mb-1.5">Personality Vibe</label><select id="charVibe"><option value="approachable-trusted">Approachable & Trusted</option><option value="sophisticated-luxury">Sophisticated Luxury</option><option value="energetic-youthful">Energetic Youthful</option><option value="calm-authority">Calm Authority</option><option value="playful-charming">Playful Charming</option></select></div><div><label class="block text-xs font-medium text-txt-200 mb-1.5">Body Language</label><select id="charBodyLang"><option value="relaxed-confident">Relaxed & Confident</option><option value="leaning-in-engaged">Leaning In Engaged</option><option value="open-welcoming">Open & Welcoming</option><option value="dynamic-action">Dynamic Action</option><option value="contemplative-thoughtful">Contemplative</option></select></div><div><label class="block text-xs font-medium text-txt-200 mb-1.5">Setting / Location</label><select id="charSetting"><option value="modern-living-room">Modern Living Room</option><option value="clean-studio">Clean Studio</option><option value="luxury-bathroom">Luxury Bathroom</option><option value="cafe-aesthetic">Aesthetic Cafe</option><option value="nature-outdoor">Nature Outdoor</option><option value="office-professional">Office Professional</option><option value="minimalist-white">Minimalist White</option></select></div></div><div class="mt-4"><label class="block text-xs font-medium text-txt-200 mb-1.5">Custom Prompt Tambahan</label><textarea id="charCustomPrompt" rows="2" placeholder="Detail spesifik tambahan tentang karakter..."></textarea></div></div><div class="flex justify-between mt-8"><button onclick="prevStep()" class="px-5 py-2.5 rounded-lg bg-srf-600 border border-brd text-txt-100 text-sm hover:bg-srf-500 transition"><i class="fa-solid fa-arrow-left mr-2"></i> Kembali</button><button onclick="nextStep()" class="px-6 py-2.5 rounded-lg bg-accent text-srf-900 font-semibold text-sm hover:bg-accent-light transition">Lanjutkan <i class="fa-solid fa-arrow-right ml-2"></i></button></div></div>
    
    <!-- STEP 4: Hook Strategy -->
    <div id="step4" class="step-panel"><div class="mb-6"><h2 class="font-display text-2xl font-bold text-txt-50 mb-1">Hook Strategy</h2><p class="text-txt-200 text-sm">Pilih jenis pembuka yang paling efektif untuk niche Anda</p></div><div id="aiHookRec" class="bg-accent/5 border border-accent/15 rounded-xl p-4 mb-6 hidden"><div class="flex items-start gap-3"><i class="fa-solid fa-lightbulb text-accent mt-0.5"></i><div><p class="text-sm font-medium text-txt-50">AI Recommendation</p><p class="text-sm text-txt-200 mt-1" id="aiHookRecText"></p></div></div></div><div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-3" id="hookGrid"></div><div class="flex justify-between mt-8"><button onclick="prevStep()" class="px-5 py-2.5 rounded-lg bg-srf-600 border border-brd text-txt-100 text-sm hover:bg-srf-500 transition"><i class="fa-solid fa-arrow-left mr-2"></i> Kembali</button><button onclick="nextStep()" class="px-6 py-2.5 rounded-lg bg-accent text-srf-900 font-semibold text-sm hover:bg-accent-light transition">Lanjutkan <i class="fa-solid fa-arrow-right ml-2"></i></button></div></div>
    
    <!-- STEP 5: Output Count -->
    <div id="step5" class="step-panel"><div class="mb-6"><h2 class="font-display text-2xl font-bold text-txt-50 mb-1">Output Variations</h2><p class="text-txt-200 text-sm">Tentukan jumlah variasi konten</p></div><div class="grid grid-cols-2 lg:grid-cols-4 gap-4" id="outputCountGrid"></div><div id="storyArcNote" class="hidden mt-5 bg-blue-500/5 border border-blue-500/15 rounded-xl p-4"><div class="flex items-start gap-3"><i class="fa-solid fa-film text-blue-400 mt-0.5"></i><div><p class="text-sm font-medium text-txt-50">Story Arc Builder</p><p class="text-xs text-txt-200 mt-1">Dengan 2+ output, AI menyusun setiap konten sebagai serial campaign.</p></div></div></div><div class="flex justify-between mt-8"><button onclick="prevStep()" class="px-5 py-2.5 rounded-lg bg-srf-600 border border-brd text-txt-100 text-sm hover:bg-srf-500 transition"><i class="fa-solid fa-arrow-left mr-2"></i> Kembali</button><button onclick="nextStep()" class="px-6 py-2.5 rounded-lg bg-accent text-srf-900 font-semibold text-sm hover:bg-accent-light transition">Lanjutkan <i class="fa-solid fa-arrow-right ml-2"></i></button></div></div>
    
    <!-- STEP 6: Video Duration -->
    <div id="step6" class="step-panel"><div class="mb-6"><h2 class="font-display text-2xl font-bold text-txt-50 mb-1">Video Duration</h2><p class="text-txt-200 text-sm">Durasi menentukan pacing script</p></div><div class="grid grid-cols-2 lg:grid-cols-4 gap-4" id="durationGrid"></div><div class="mt-8 text-center"><button onclick="generateCampaign()" class="gen-btn px-10 py-4 rounded-xl text-srf-900 font-display font-bold text-base"><i class="fa-solid fa-wand-magic-sparkles mr-2"></i> Generate Campaign (Instant)</button><p class="text-xs text-txt-300 mt-3">Hasil akan langsung dibuat tanpa waktu tunggu buatan.</p></div><div class="flex justify-start mt-4"><button onclick="prevStep()" class="px-5 py-2.5 rounded-lg bg-srf-600 border border-brd text-txt-100 text-sm hover:bg-srf-500 transition"><i class="fa-solid fa-arrow-left mr-2"></i> Kembali</button></div></div>
    
    <!-- FINAL OUTPUT -->
    <div id="finalOutput" class="step-panel"></div>
</div>
</section>

<!-- SAVED CHARACTERS -->
<section id="viewCharacters" class="view-section">
<div class="max-w-6xl mx-auto">
    <div class="flex items-center justify-between mb-8"><div><h2 class="font-display text-2xl font-bold text-txt-50 mb-1">Saved Characters</h2><p class="text-txt-200 text-sm">Karakter tersimpan secara lokal di browser Anda</p></div><button onclick="document.getElementById('charUploadZone')&&navigateTo('campaign')" class="px-4 py-2 rounded-lg bg-accent text-srf-900 font-semibold text-sm hover:bg-accent-light transition"><i class="fa-solid fa-plus mr-2"></i> Add Character</button></div>
    <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-4" id="savedCharsGrid"></div>
</div>
</section>

<!-- HOOK LIBRARY -->
<section id="viewHooks" class="view-section">
<div class="max-w-6xl mx-auto">
    <div class="mb-8"><h2 class="font-display text-2xl font-bold text-txt-50 mb-1">Hook Library</h2><p class="text-txt-200 text-sm">Koleksi hook terbukti efektif</p></div>
    <div class="flex gap-2 mb-6 flex-wrap" id="hookFilterTabs"></div>
    <div class="space-y-3" id="hookLibraryList"></div>
</div>
</section>

<!-- TEMPLATES -->
<section id="viewTemplates" class="view-section">
<div class="max-w-6xl mx-auto">
    <div class="mb-8"><h2 class="font-display text-2xl font-bold text-txt-50 mb-1">Templates</h2><p class="text-txt-200 text-sm">Template campaign siap pakai</p></div>
    <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-4" id="templatesGrid"></div>
</div>
</section>

<!-- ANALYTICS -->
<section id="viewAnalytics" class="view-section">
<div class="max-w-6xl mx-auto">
    <div class="mb-8"><h2 class="font-display text-2xl font-bold text-txt-50 mb-1">Analytics</h2><p class="text-txt-200 text-sm">Performa campaign dari data lokal</p></div>
    <div class="grid grid-cols-1 sm:grid-cols-3 gap-4 mb-8">
        <div class="bg-srf-700 border border-brd rounded-xl p-5 text-center"><p class="text-3xl font-display font-bold text-accent" id="anaScore">0</p><p class="text-sm text-txt-200 mt-1">Avg. Quality Score</p></div>
        <div class="bg-srf-700 border border-brd rounded-xl p-5 text-center"><p class="text-3xl font-display font-bold text-green-400" id="anaConv">0%</p><p class="text-sm text-txt-200 mt-1">Est. Conversion Rate</p></div>
        <div class="bg-srf-700 border border-brd rounded-xl p-5 text-center"><p class="text-3xl font-display font-bold text-blue-400" id="anaHook">0%</p><p class="text-sm text-txt-200 mt-1">Hook Effectiveness</p></div>
    </div>
    <div class="grid grid-cols-1 lg:grid-cols-2 gap-6">
        <div class="bg-srf-700 border border-brd rounded-xl p-6"><h3 class="font-display font-semibold text-txt-50 mb-4">Top Performing Hooks</h3><div class="space-y-3" id="topHooksAnalytics"></div></div>
        <div class="bg-srf-700 border border-brd rounded-xl p-6"><h3 class="font-display font-semibold text-txt-50 mb-4">Niche Performance</h3><div class="space-y-3" id="nichePerformance"></div></div>
    </div>
</div>
</section>

<!-- SETTINGS -->
<section id="viewSettings" class="view-section">
<div class="max-w-3xl mx-auto">
    <div class="mb-8"><h2 class="font-display text-2xl font-bold text-txt-50 mb-1">Settings</h2><p class="text-txt-200 text-sm">Konfigurasi akun dan Brand DNA Memory</p></div>
    <div class="space-y-6">
        <div class="bg-srf-700 border border-brd rounded-xl p-6"><h3 class="font-display font-semibold text-txt-50 mb-4">Profile</h3><div class="space-y-4"><div><label class="block text-sm text-txt-200 mb-1.5">Nama</label><input type="text" id="settingsName" value="John Doe"></div><div><label class="block text-sm text-txt-200 mb-1.5">Email</label><input type="email" id="settingsEmail" value="john@example.com"></div></div></div>
        <div class="bg-srf-700 border border-brd rounded-xl p-6"><h3 class="font-display font-semibold text-txt-50 mb-4"><i class="fa-solid fa-dna text-accent mr-2"></i>Brand DNA Memory <span class="persist-badge">Persistent</span></h3><p class="text-sm text-txt-200 mb-4">Gaya brand Anda tersimpan dan otomatis diterapkan ke semua campaign.</p><div class="space-y-4"><div><label class="block text-sm text-txt-200 mb-1.5">Brand Voice</label><select id="settingsVoice"><option>Professional & Trusted</option><option>Casual & Friendly</option><option>Luxury & Exclusive</option><option>Energetic & Youthful</option></select></div><div><label class="block text-sm text-txt-200 mb-1.5">Default Tone</label><select id="settingsTone"><option>Conversational</option><option>Authoritative</option><option>Storytelling</option><option>Direct & Punchy</option></select></div><div><label class="block text-sm text-txt-200 mb-1.5">Brand Keywords</label><input type="text" id="settingsKeywords" value="premium, terpercaya, hasil nyata" placeholder="Pisahkan dengan koma"></div></div></div>
        <div class="bg-srf-700 border border-brd rounded-xl p-6"><h3 class="font-display font-semibold text-txt-50 mb-4"><i class="fa-solid fa-database text-accent mr-2"></i>Local Storage</h3><p class="text-sm text-txt-200 mb-4">Semua data disimpan di browser Anda. Tidak ada data yang dikirim ke server.</p><div class="flex items-center justify-between p-3 rounded-lg bg-srf-600 border border-brd mb-3"><span class="text-sm text-txt-100"><i class="fa-solid fa-folder-tree mr-2 text-txt-300"></i>Campaigns tersimpan</span><span class="text-sm font-medium text-accent" id="lsCampaignCount">0</span></div><div class="flex items-center justify-between p-3 rounded-lg bg-srf-600 border border-brd mb-3"><span class="text-sm text-txt-100"><i class="fa-solid fa-users mr-2 text-txt-300"></i>Characters tersimpan</span><span class="text-sm font-medium text-accent" id="lsCharCount">0</span></div><button onclick="clearAllData()" class="w-full py-2 rounded-lg bg-red-500/10 border border-red-500/20 text-red-400 text-sm font-medium hover:bg-red-500/20 transition"><i class="fa-solid fa-trash mr-2"></i>Hapus Semua Data Lokal</button></div>
        <div class="text-center"><button onclick="saveSettings()" class="px-6 py-2.5 rounded-lg bg-accent text-srf-900 font-semibold text-sm hover:bg-accent-light transition">Save Changes</button></div>
    </div>
</div>
</section>

</main>
</div>

<!-- Generation Overlay -->
<div id="genOverlay" class="overlay-modal hidden" style="animation:fadeIn .2s ease">
<div class="bg-srf-700 border border-brd rounded-2xl p-8 max-w-md w-full mx-4">
    <div class="text-center mb-6"><div class="w-14 h-14 rounded-full bg-accent/10 flex items-center justify-center mx-auto mb-3"><i class="fa-solid fa-bolt text-accent text-xl"></i></div><h3 class="font-display font-bold text-lg text-txt-50">Menyusun Campaign</h3><p class="text-sm text-txt-200 mt-1">Selesai dalam sekejap...</p></div>
    <div class="space-y-3" id="genStages"></div>
</div>
</div>

<div id="toast" class="toast hidden"></div>

<script>
/* ================================================================
   LOCAL STORAGE HELPERS
   ================================================================ */
var LS_PREFIX = 'aips_';

function lsSave(key, data) {
    try { localStorage.setItem(LS_PREFIX + key, JSON.stringify(data)); } catch(e) { console.warn('LS save failed', e); }
}
function lsLoad(key, fallback) {
    try {
        var raw = localStorage.getItem(LS_PREFIX + key);
        return raw ? JSON.parse(raw) : fallback;
    } catch(e) { return fallback; }
}
function clearAllData() {
    var keys = Object.keys(localStorage).filter(function(k){ return k.indexOf(LS_PREFIX) === 0; });
    keys.forEach(function(k){ localStorage.removeItem(k); });
    showToast('Semua data lokal berhasil dihapus', 'success');
    renderDashboard();
    renderSavedChars();
    renderAnalytics();
    updateLSCounts();
    loadSettings();
}
function updateLSCounts() {
    var camps = lsLoad('campaigns', []);
    var chars = lsLoad('characters', []);
    var el1 = document.getElementById('lsCampaignCount');
    var el2 = document.getElementById('lsCharCount');
    if (el1) el1.textContent = camps.length;
    if (el2) el2.textContent = chars.length;
}

/* ================================================================
   STATE & DATA
   ================================================================ */
var S = { view:'dashboard', step:1, product:{image:null,name:'',desc:'',benefits:[],audience:'',niche:''}, charMode:'upload', charImage:null, hook:null, outputCount:1, duration:15 };

var unsplash = {
    beauty: { product: 'https://images.unsplash.com/photo-1556228578-0d85b1a4d571?w=600&h=450&fit=crop&auto=format', lifestyle: 'https://images.unsplash.com/photo-1596462502278-27bfdc403348?w=600&h=450&fit=crop&auto=format', detail: 'https://images.unsplash.com/photo-1570194065650-d99fb4b38b17?w=600&h=450&fit=crop&auto=format', social: 'https://images.unsplash.com/photo-1522335789203-aabd1fc54bc9?w=600&h=450&fit=crop&auto=format' },
    tech: { product: 'https://images.unsplash.com/photo-1505740420928-5e560c06d30e?w=600&h=450&fit=crop&auto=format', lifestyle: 'https://images.unsplash.com/photo-1498050108023-c5249f4df085?w=600&h=450&fit=crop&auto=format', detail: 'https://images.unsplash.com/photo-1519389950473-47ba0277781c?w=600&h=450&fit=crop&auto=format', social: 'https://images.unsplash.com/photo-1531297484001-80022131f5a1?w=600&h=450&fit=crop&auto=format' },
    health: { product: 'https://images.unsplash.com/photo-1526698905402-e13b9763e5a8?w=600&h=450&fit=crop&auto=format', lifestyle: 'https://images.unsplash.com/photo-1571019613454-1cb2f99b2d8b?w=600&h=450&fit=crop&auto=format', detail: 'https://images.unsplash.com/photo-1540497077202-7c8a3999166f?w=600&h=450&fit=crop&auto=format', social: 'https://images.unsplash.com/photo-1518611012118-696072aa579a?w=600&h=450&fit=crop&auto=format' },
    finance: { product: 'https://images.unsplash.com/photo-1554224155-6726b3ff858f?w=600&h=450&fit=crop&auto=format', lifestyle: 'https://images.unsplash.com/photo-1553028826-f4804a6dba3b?w=600&h=450&fit=crop&auto=format', detail: 'https://images.unsplash.com/photo-1611974789855-9c2a0a7236a3?w=600&h=450&fit=crop&auto=format', social: 'https://images.unsplash.com/photo-1553729459-uj8mwk0mjZ0c?w=600&h=450&fit=crop&auto=format' },
    fashion: { product: 'https://images.unsplash.com/photo-1445205170230-053b83016050?w=600&h=450&fit=crop&auto=format', lifestyle: 'https://images.unsplash.com/photo-1509631179647-0177331693ae?w=600&h=450&fit=crop&auto=format', detail: 'https://images.unsplash.com/photo-1558618666-fcd25c85f82e?w=600&h=450&fit=crop&auto=format', social: 'https://images.unsplash.com/photo-1469334031218-e382a71b716b?w=600&h=450&fit=crop&auto=format' },
    food: { product: 'https://images.unsplash.com/photo-1490645935967-10de6ba17061?w=600&h=450&fit=crop&auto=format', lifestyle: 'https://images.unsplash.com/photo-1476224203421-9ac39bcb3327?w=600&h=450&fit=crop&auto=format', detail: 'https://images.unsplash.com/photo-1498837167922-ddd27525d352?w=600&h=450&fit=crop&auto=format', social: 'https://images.unsplash.com/photo-1565299624946-b28f40a0ae38?w=600&h=450&fit=crop&auto=format' },
    home: { product: 'https://images.unsplash.com/photo-1586023492125-27b2c045efd7?w=600&h=450&fit=crop&auto=format', lifestyle: 'https://images.unsplash.com/photo-1616486338812-3dadae4b4ace?w=600&h=450&fit=crop&auto=format', detail: 'https://images.unsplash.com/photo-1618221195710-dd6b41faaea6?w=600&h=450&fit=crop&auto=format', social: 'https://images.unsplash.com/photo-1600210492486-724fe5c67fb0?w=600&h=450&fit=crop&auto=format' },
    education: { product: 'https://images.unsplash.com/photo-1456513080510-7bf3a84b82f8?w=600&h=450&fit=crop&auto=format', lifestyle: 'https://images.unsplash.com/photo-1522202176988-66273c2fd55f?w=600&h=450&fit=crop&auto=format', detail: 'https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?w=600&h=450&fit=crop&auto=format', social: 'https://images.unsplash.com/photo-1529156069898-49953e39b3ac?w=600&h=450&fit=crop&auto=format' },
    other: { product: 'https://images.unsplash.com/photo-1505740420928-5e560c06d30e?w=600&h=450&fit=crop&auto=format', lifestyle: 'https://images.unsplash.com/photo-1553028826-f4804a6dba3b?w=600&h=450&fit=crop&auto=format', detail: 'https://images.unsplash.com/photo-1553729459-uj8mwk0mjZ0c?w=600&h=450&fit=crop&auto=format', social: 'https://images.unsplash.com/photo-1611162617213-7d7a39e9b1d7?w=600&h=450&fit=crop&auto=format' }
};

var unsplashChars = ['https://images.unsplash.com/photo-1494790108377-be9c29b29330?w=300&h=400&fit=crop&auto=format', 'https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?w=300&h=400&fit=crop&auto=format', 'https://images.unsplash.com/photo-1534528741775-53994a69daeb?w=300&h=400&fit=crop&auto=format', 'https://images.unsplash.com/photo-1500648767791-00dcc994a43e?w=300&h=400&fit=crop&auto=format', 'https://images.unsplash.com/photo-1517841905240-472988babdf9?w=300&h=400&fit=crop&auto=format', 'https://images.unsplash.com/photo-1506794778202-cad84cf45f1d?w=300&h=400&fit=crop&auto=format'];
var unsplashTemplates = ['https://images.unsplash.com/photo-1556228578-0d85b1a4d571?w=400&h=250&fit=crop&auto=format', 'https://images.unsplash.com/photo-1498050108023-c5249f4df085?w=400&h=250&fit=crop&auto=format', 'https://images.unsplash.com/photo-1526698905402-e13b9763e5a8?w=400&h=250&fit=crop&auto=format', 'https://images.unsplash.com/photo-1554224155-6726b3ff858f?w=400&h=250&fit=crop&auto=format', 'https://images.unsplash.com/photo-1445205170230-053b83016050?w=400&h=250&fit=crop&auto=format', 'https://images.unsplash.com/photo-1586023492125-27b2c045efd7?w=400&h=250&fit=crop&auto=format'];

var hookTypes = [
    {id:'emotional',icon:'fa-heart',label:'Emotional Story',desc:'Cerita emosional yang menyentuh hati',niches:['beauty','health','education']},
    {id:'curiosity',icon:'fa-magnifying-glass',label:'Curiosity',desc:'Membuat penonton penasaran',niches:['tech','finance','education']},
    {id:'problem',icon:'fa-lightbulb',label:'Problem-Solution',desc:'Identifikasi masalah, tawarkan solusi',niches:['health','tech','home','finance']},
    {id:'authority',icon:'fa-shield-halved',label:'Authority',desc:'Posisi sebagai ahli terpercaya',niches:['health','finance','education','tech']},
    {id:'socialproof',icon:'fa-users',label:'Social Proof',desc:'Bukti sosial dari pengguna nyata',niches:['beauty','fashion','food','health']},
    {id:'urgency',icon:'fa-bolt',label:'Urgency',desc:'Sense of urgency & FOMO',niches:['tech','fashion','finance']},
    {id:'luxury',icon:'fa-gem',label:'Luxury Appeal',desc:'Positioning premium & eksklusif',niches:['beauty','fashion','home']},
    {id:'viral',icon:'fa-fire',label:'Viral Trend',desc:'Ride on trend yang sedang viral',niches:['beauty','food','fashion','tech']}
];

var nicheData = {
    beauty:{niche:'Beauty & Skincare',sub:'Anti-aging & Brightening',maturity:78,maturityLabel:'Mature',persona:'Wanita 25-40 tahun, urban, career-driven, peduli pada penampilan dan self-care. Aktif di Instagram & TikTok. Bersedia membayar premium untuk hasil nyata.',strategy:'Aspiration-Driven + Transformation Promise',drivers:['Kepercayaan diri','Tampil awet muda','Status sosial','Self-reward'],pains:['Kulit kusam dan tidak merata','Tanda penuaan dini','Produk mahal tapi tidak bekerja','Bingung pilih produk yang tepat'],desires:['Kulit glowing tanpa filter','Dipuji lingkungan sosial','Merasa investasi skincare worth it','Routine sederhana tapi efektif'],resistance:['Sudah coba banyak produk tidak ada hasil','Takut efek samping bahan kimia','Harga premium vs budget terbatas'],angles:['Before-After Transformation','Expert Recommendation','Ingredient Science','Luxury Self-Care Ritual','Relatable Skincare Journey'],recHook:'emotional'},
    tech:{niche:'Tech & Gadget',sub:'Productivity & Lifestyle Enhancement',maturity:65,maturityLabel:'Growing',persona:'Pria 22-38 tahun, early adopter, produktivitas-focused. Mengikuti review channel YouTube. Value for money oriented.',strategy:'Authority-Led + Problem-Solution',drivers:['Efisiensi waktu','Status early adopter','Kemudahan hidup','FOMO teknologi baru'],pains:['Workflow tidak efisien','Perangkat lambat','Terlalu banyak tools','Budget terbatas tapi ingin terbaik'],desires:['Satu device solve semua masalah','Dipandang tech-savvy','Produktivitas meningkat drastis','Investasi gadget yang tepat'],resistance:['Skeptis terhadap review biasa','Takut beli lalu menyesal','Perbandingan dengan kompetitor'],angles:['Problem-Solver Demo','Hands-On Review','Comparison Killer','Productivity Hack','Unboxing Experience'],recHook:'curiosity'},
    health:{niche:'Health & Fitness',sub:'Supplement & Body Transformation',maturity:82,maturityLabel:'Mature',persona:'Pria/Wanita 20-45 tahun, aktif secara fisik atau ingin memulai. Following fitness influencer. Goal-oriented.',strategy:'Transformation Promise + Authority',drivers:['Hasil fisik terlihat','Kesehatan jangka panjang','Disiplin & konsistensi','Komunitas fitness'],pains:['Progres stagnan','Sulit konsisten','Informasi bertentangan','Supplement tidak bekerja'],desires:['Body goal tercapai','Dipuji karena perubahan','Merasa fit & energik','Program yang simple'],resistance:['Sudah coba berbagai supplement','Takut efek samping jangka panjang','Budget untuk supplement'],angles:['Transformation Timeline','Expert Breakdown','Myth Busting','Daily Routine Integration','Community Challenge'],recHook:'problem'},
    finance:{niche:'Finance & Bisnis',sub:'Passive Income & Wealth Building',maturity:70,maturityLabel:'Growing',persona:'Pria/Wanita 25-45 tahun, penghasilan menengah-atas, ingin financial freedom. Konsumen konten financial literacy.',strategy:'Authority-Led + Aspiration-Driven',drivers:['Financial freedom','Keamanan masa depan','Status ekonomi','Pengembangan aset'],pains:['Gaji habis untuk kebutuhan','Tidak punya investasi','Takut salah investasi','Informasi keuangan membingungkan'],desires:['Passive income stream','Pensiun nyaman','Bisa beli apa yang diinginkan','Dipandang sukses secara finansial'],resistance:['Takut risiko kerugian','Skeptis terhadap get rich quick','Tidak punya modal besar','Kompleksitas produk finansial'],angles:['Number Proof Strategy','Risk Reversal','Step-by-Step Blueprint','Common Mistake Revelation','Aspirational Lifestyle'],recHook:'authority'},
    fashion:{niche:'Fashion & Style',sub:'Affordable Luxury & Trend',maturity:75,maturityLabel:'Mature',persona:'Wanita 20-35 tahun, fashion-conscious, aktif di media sosial. Mengikuti tren tapi sadar budget.',strategy:'Social Proof + Luxury Positioning',drivers:['Tampil stylish','Dipuji di media sosial','Feeling exclusive','Bargain satisfaction'],pains:['Outfit terlihat basic','Trend cepat berubah','Budget vs desire gap','Tidak tahu mix & match'],desires:['Wardrobe yang impressif','Foto OOTD yang viral','Feeling stylish tanpa effort','Brand yang dikenal orang'],angles:['Outfit Transformation','Budget vs Look Challenge','Celebrity Style Decode','Wardrobe Essentials','Trend Forecast'],recHook:'socialproof'},
    food:{niche:'Food & Beverage',sub:'Healthy & Convenient',maturity:60,maturityLabel:'Growing',persona:'Wanita/Pria 22-40, sibuk tapi peduli gizi. Looking for convenient healthy options.',strategy:'Viral Trend + Problem-Solution',drivers:['Kenikmatan tanpa rasa bersalah','Kemudahan & kepraktisan','Trend following','Status lifestyle'],pains:['Makanan sehat tidak enak','Tidak punya waktu masak','Bingung pilih menu sehat','Diet membosankan'],desires:['Makan enak tapi tetap sehat','Praktis tapi tetap premium','Diet yang sustainable','Konten makanan yang estetik'],angles:['Taste Test Challenge','Healthy Hack','Behind The Recipe','Lifestyle Integration','Visual Food Porn'],recHook:'viral'},
    home:{niche:'Home & Living',sub:'Smart & Aesthetic Living',maturity:55,maturityLabel:'Emerging',persona:'Wanita/Pria 25-45, homeowner atau renter, ingin ruangan nyaman dan estetik.',strategy:'Aspiration-Driven + Transformation Promise',drivers:['Rumah sebagai refleksi diri','Kenyamanan mental','Prestasi memiliki rumah indah','Social media worthy space'],pains:['Rumah terasa cramped','Tidak tahu cara dekorasi','Budget renovasi terbatas','Inspirasi tapi bingung eksekusi'],desires:['Rumah estetik seperti di majalah','Ruang yang calming & cozy','Dipuji tamu yang datang','Smart home yang praktis'],angles:['Room Transformation','Budget Makeover','Small Space Hack','Aesthetic on Budget','Smart Home Upgrade'],recHook:'emotional'},
    education:{niche:'Education',sub:'Skill Acquisition & Career',maturity:68,maturityLabel:'Growing',persona:'Pria/Wanita 20-35 tahun, ingin upgrade skill untuk karir. Belajar online.',strategy:'Authority-Led + Aspiration-Driven',drivers:['Karir lebih baik','Penghasilan meningkat','Kompetensi unggul','Investasi diri'],pains:['Skill tidak relevan pasar','Tidak punya waktu belajar','Kursus mahal tidak ada hasil','Bingung mulai dari mana'],desires:['Skill yang langsung applicable','Sertifikat yang diakui','Income increase terukur','Learning path yang jelas'],angles:['Career Transformation','Skill Gap Analysis','Quick Win Method','Success Story','Industry Insider'],recHook:'authority'},
    other:{niche:'General Market',sub:'Broad Consumer',maturity:50,maturityLabel:'Emerging',persona:'Konsumen umum 20-45 tahun, terbuka terhadap rekomendasi.',strategy:'Problem-Solution + Social Proof',drivers:['Kemudahan','Value for money','Rekomendasi terpercaya','Novelty'],pains:['Keputusan pembelian bingung','Takut beli salah','Budget terbatas','Informasi terlalu banyak'],desires:['Produk yang benar-benar bekerja','Pembelian tanpa penyesalan','Feeling smart shopper','Rekomendasi yang bisa diandalkan'],angles:['Honest Review','Problem Solver','Value Breakdown','Versus Comparison','User Experience'],recHook:'problem'}
};

var hookScripts = {
    emotional: function(p){return ['Saya hampir menyerah sampai '+p+' mengubah segalanya...','Tahun lalu saya tidak percaya diri. Sekarang? Semua berkat '+p+'.','Cerita terbaik saya bukan tentang sukses — tapi tentang menemukan '+p+'.','Jika kamu tahu betapa besar perubahan yang '+p+' bawa, kamu tidak akan menunda lagi.'];},
    curiosity: function(p){return ['Ternyata selama ini kita salah tentang '+p+'...','Satu hal yang orang tidak tahu tentang '+p+'.','Saya menemukan sesuatu tentang '+p+' yang bikin saya kaget.','Ada alasan mengapa '+p+' tiba-tiba menjadi viral — dan itu bukan yang kamu kira.'];},
    problem: function(p){return ['Kalau kamu masih mengalami masalah ini, '+p+' adalah jawabannya.','Berhenti buang waktu — inilah solusi yang kamu cari: '+p+'.','Masalah yang sama terus muncul? '+p+' bisa menghentikannya.','Setiap kali kamu frustrasi dengan masalah ini, ingat bahwa '+p+' ada untuk alasan ini.'];},
    authority: function(p){return ['Setelah menganalisis ratusan produk, '+p+' yang paling saya rekomendasikan.','Sebagai praktisi di bidang ini, saya hanya merekomendasikan '+p+'.','Data tidak berbohong — inilah mengapa '+p+' standarnya berbeda.','Saya sudah mereview produk selama 5 tahun. '+p+' masuk top 3 sepanjang masa.'];},
    socialproof: function(p){return ['Ribuan orang sudah membuktikan — '+p+' bukan sekadar klaim.','Lihat apa yang terjadi setelah mereka mencoba '+p+'.','Komunitas kami tumbuh karena satu alasan: '+p+' benar-benar bekerja.','Testimoni masuk setiap hari tentang '+p+' — ini yang paling sering muncul.'];},
    urgency: function(p){return ['Promo '+p+' ini tidak akan lama — jangan sampai ketinggalan.','Stok '+p+' terbatas dan permintaan tinggi. Act now.','Harga '+p+' bisa naik kapan saja. Ambil keputusan sekarang.','Hanya tersisa sedikit slot untuk '+p+' dengan harga ini.'];},
    luxury: function(p){return ['Untuk mereka yang mengerti kualitas — '+p+' adalah standar baru.','Tidak untuk semua orang. '+p+' dibuat untuk mereka yang tahu.','Ketika kualitas bukan kompromi — '+p+' jawabannya.','Premium bukan tentang harga. '+p+' mendefinisikan ulang apa artinya kualitas nyata.'];},
    viral: function(p){return ['Semenjak viral, semua orang cari '+p+'. Ini alasan sebenarnya.','Trending sekarang — tapi apakah '+p+' benar-benar worth it?','Semua orang bicara tentang '+p+'. Saya tes sendiri, begini hasilnya.','Saya tidak percaya hype — sampai saya coba '+p+' sendiri.'];}
};

var scriptTemplates = {
    beauty: {
        pain: [function(p){return 'Kulit kusam, noda hitam yang tidak kunjung hilang, dan produk mahal yang hanya menjanjikan — tanpa hasil. Kamu bukan sendirian.';}, function(p){return 'Bercermin dan melihat kulit yang tidak merata itu menyakitkan. Terutama ketika kamu sudah mencoba semua rekomendasi teman.';}, function(p){return 'Setiap malam kamu merawat kulit dengan harapan hasil berbeda. Tapi pagi harinya, cermin tetap menunjukkan hal yang sama.';}],
        desire: ['Bayangkan bangun pagi, kulit glowing alami tanpa filter. Percaya diri tanpa makeup tebal. Itu bukan mimpi — itu bisa jadi kenyataan.','Merasa glowing dari dalam, dipuji teman-teman tanpa mereka tahu rahasiamu. itu perasaan yang ingin kamu rasakan setiap hari.','Satu rutinitas sederhana yang mengubah cara orang melihat kamu. Bukan karena makeup — tapi karena kulit yang sebenarnya.'],
        solution: [function(p){return p+' diformulasikan dengan bahan aktif terbukti yang menargetkan akar masalah, bukan hanya permukaan.';}, function(p){return p+' menggunakan teknologi delivery system yang memastikan bahan aktif menembus hingga lapisan kulit terdalam.';}, function(p){return p+' dikembangkan berdasarkan riset dermatologi terbaru — bukan sekadar tren, tapi sains nyata.';}],
        proof: [function(p){return 'Dalam 14 hari, 9 dari 10 pengguna melihat perubahan nyata pada kecerahan dan tekstur kulit mereka.';}, function(p){return 'Klinis teruji: penggunaan rutin '+p+' selama 28 hari menunjukkan peningkatan hidrasi 47% dan pengurangan noda gelap 62%.';}, function(p){return 'Lebih dari 12,000 pengguna di Indonesia sudah merasakan perubahan. Rating rata-rata mereka: 4.9 dari 5.';}],
        cta: [function(p){return 'Klik link di bio sekarang dan dapatkan '+p+' dengan harga spesial hari ini saja.';}, function(p){return 'Jangan tunggu kulitmu makin parah. Mulai rutinitas dengan '+p+' sekarang — link di bio.';}, function(p){return 'Pesan '+p+' sekarang dan dapatkan panduan skincare gratis senilai Rp 299.000. Link di bio.';}]
    },
    tech: {
        pain: [function(p){return 'Workflow kamu tidak efisien. Beralih antar tools, loading yang lama, dan produktivitas yang terhambat.';}, function(p){return 'Setiap hari kamu kehilangan 2 jam hanya karena perangkat yang bukan standarmu. Itu 14 jam seminggu — setengah hari kerja.';}, function(p){return 'Kamu tahu ada cara yang lebih baik, tapi terlalu banyak pilihan dan terlalu sedikit waktu untuk riset.';}],
        desire: ['Satu perangkat yang menyederhanakan semuanya. Setup yang clean, performa instan, dan kamu fokus pada yang penting.','Bayangkan bisa menyelesaikan pekerjaan 2x lebih cepat tanpa frustrasi teknis. Itu bukan impian — itu perangkat yang tepat.','Kerja dari mana saja, kapan saja, tanpa hambatan. Perangkat yang mengikuti kecepatan pikiranmu.'],
        solution: [function(p){return p+' dirancang untuk menghilangkan bottleneck — performa tinggi dalam desain minimalis.';}, function(p){return p+' mengintegrasikan apa yang biasanya butuh 3 tools terpisah menjadi satu ekosistem seamless.';}, function(p){return p+' dibangun untuk profesional yang menolak kompromi antara portabilitas dan performa.';}],
        proof: [function(p){return 'Lebih dari 5,000 profesional sudah beralih dan melihat produktivitas naik rata-rata 40%.';}, function(p){return 'Benchmark independen menunjukkan '+p+' mengungguli kompetitor di kelasnya di 7 dari 8 kategori performa.';}, function(p){return 'Review dari 200+ tech creator dengan rata-rata skor 9.2/10. Angka yang berbicara sendiri.';}],
        cta: [function(p){return 'Dapatkan '+p+' sekarang dengan diskon eksklusif. Link di bio.';}, function(p){return 'Upgrade produktivitasmu dengan '+p+'. Stok terbatas — link di bio.';}, function(p){return 'Join 5,000+ profesional yang sudah switch ke '+p+'. Link di bio untuk penawaran terbatas.';}]
    },
    health: {
        pain: [function(p){return 'Progres stagnan, konsistensi sulit dijaga, dan suplemen yang kamu konsumsi tidak memberikan hasil terukur.';}, function(p){return 'Kamu sudah rajin gym, tapi tubuh tidak berubah sesuai ekspektasi. Frustrasi itu nyata dan valid.';}, function(p){return 'Setiap bulan ganti suplemen, setiap bulan harapan baru tapi hasil yang sama. Siklus yang harus dihentikan.';}],
        desire: ['Body goal yang tercapai, energi melimpah setiap hari, dan bangga dengan perubahan yang bisa dilihat semua orang.','Merasa kuat, bugar, dan percaya diri. Bukan hanya penampilan — tapi bagaimana tubuhmu bekerja untukmu.','Transformasi yang nyata dan bertahan lama. Bukan hasil instan yang menghilang dalam seminggu.'],
        solution: [function(p){return p+' menggunakan formulasi berbasis riset klinis yang menargetkan recovery dan pertumbuhan secara optimal.';}, function(p){return p+' menggabungkan bahan aktif dalam rasio yang sudah terbukti klinis — bukan sekadar campuran sembarangan.';}, function(p){return p+' dirancang untuk mengisi gap nutrisi yang paling sering terlewatkan oleh orang aktif.';}],
        proof: [function(p){return 'Studi menunjukkan pengguna '+p+' mengalami peningkatan performa 3x lebih cepat dibanding placebo.';}, function(p){return 'Dalam 60 hari, 87% pengguna '+p+' melihat perubahan yang bisa diukur pada komposisi tubuh mereka.';}, function(p){return 'Digunakan oleh 500+ atlet profesional Indonesia. Bukan sekadar klaim — ini bukti nyata.';}],
        cta: [function(p){return 'Mulai transformasi kamu sekarang. '+p+' tersedia dengan potongan harga khusus. Link di bio.';}, function(p){return 'Jangan buang satu hari lagi untuk progres yang lambat. '+p+' — link di bio.';}, function(p){return 'Pesan '+p+' sekarang dan dapatkan meal plan gratis. Link di bio.';}]
    },
    finance: {
        pain: [function(p){return 'Gaji habis untuk kebutuhan, tidak punya investasi, dan merasa tertinggal dari orang-orang seumuran.';}, function(p){return 'Kamu tahu kamu harus mulai investasi, tapi setiap kali mau mulai, bingung dari mana dan takut salah langkah.';}, function(p){return 'Setiap bulan sama saja — uang masuk, uang keluar, dan tabungan tidak bertambah signifikan.';}],
        desire: ['Passive income yang masuk setiap bulan, financial freedom yang nyata, dan masa depan yang aman tanpa khawatir.','Bayangkan tidak lagi cek saldo sebelum belanja sesuatu. Kebebasan finansial itu bukan mimpi.','Masa depan yang kamu kendalikan penuh — bukan dikendalikan oleh kebutuhan dan kekhawatiran finansial.'],
        solution: [function(p){return p+' memberikan blueprint langkah demi langkah yang bisa diikuti siapa saja, bahkan tanpa pengalaman investasi.';}, function(p){return p+' menyederhanakan konsep keuangan yang kompleks menjadi aksi harian yang bisa langsung kamu lakukan.';}, function(p){return p+' bukan teori — ini sistem yang sudah terbukti menghasilkan income tambahan bagi ribuan orang.';}],
        proof: [function(p){return 'Lebih dari 2,000 peserta sudah berhasil membangun sumber income baru dalam 90 hari pertama.';}, function(p){return 'Rata-rata peserta '+p+' melihat pertumbuhan aset 35% dalam 6 bulan pertama mengikuti sistem ini.';}, function(p){return 'Audit independen membuktikan: 78% peserta yang konsisten mencapai target finansial mereka dalam 1 tahun.';}],
        cta: [function(p){return 'Jangan tunda lagi. Bergabung dengan '+p+' sekarang dan mulai perjalanan financial-mu. Link di bio.';}, function(p){return 'Kebebasan finansial dimulai dari satu keputusan. '+p+' — link di bio.';}, function(p){return 'Daftar '+p+' sekarang dan dapatkan sesi konsultasi gratis. Link di bio.';}]
    }
};

var defaultScript = {
    pain: [function(p){return 'Kamu sudah mencoba berbagai solusi tapi hasilnya tetap sama — frustrasi, buang waktu, dan buang uang.';}],
    desire: ['Bayangkan jika ada satu solusi yang benar-benar bekerja. Perubahan nyata yang bisa kamu rasakan dan lihat.'],
    solution: [function(p){return p+' dirancang berbeda — menyerang masalah dari sumbernya, bukan sekadar menutupi gejala.';}],
    proof: [function(p){return 'Ribuan pengguna sudah membuktikan. Hasilnya berbicara sendiri.';}],
    cta: [function(p){return 'Jangan tunggu lagi. Ambil '+p+' sekarang dan rasakan perbedaannya. Link di bio.';}]
};

var hookLibrary = [
    {type:'emotional',text:'Saya hampir menyerah sampai ini mengubah segalanya...',perf:92,used:342},
    {type:'emotional',text:'Tahun lalu saya tidak percaya diri. Sekarang semua berbeda.',perf:88,used:218},
    {type:'curiosity',text:'Ternyata selama ini kita semua salah tentang ini...',perf:95,used:567},
    {type:'curiosity',text:'Satu hal kecil yang orang tidak tahu — tapi mengubah segalanya.',perf:90,used:389},
    {type:'problem',text:'Kalau kamu masih mengalami ini, kamu perlu lihat ini.',perf:87,used:445},
    {type:'authority',text:'Setelah menganalisis ratusan produk, ini yang paling saya rekomendasikan.',perf:91,used:276},
    {type:'socialproof',text:'Ribuan orang sudah membuktikan — ini bukan sekadar klaim.',perf:89,used:521},
    {type:'urgency',text:'Promo ini tidak akan lama. Jangan sampai menyesal.',perf:78,used:198},
    {type:'luxury',text:'Untuk mereka yang mengerti kualitas — ini standar baru.',perf:85,used:167},
    {type:'viral',text:'Semua orang bicara tentang ini. Saya tes sendiri, begini hasilnya.',perf:93,used:634}
];

var defaultChars = [
    {name:'Sarah',desc:'Friendly beauty influencer, warm smile, relatable',img:unsplashChars[0],uses:8},
    {name:'Marcus',desc:'Professional tech reviewer, clean look, trustworthy',img:unsplashChars[1],uses:5},
    {name:'Aisha',desc:'Elegant lifestyle model, sophisticated presence',img:unsplashChars[2],uses:12},
    {name:'David',desc:'Fitness enthusiast, energetic and motivational',img:unsplashChars[3],uses:3},
    {name:'Luna',desc:'Young trendy fashion creator, street style vibe',img:unsplashChars[4],uses:6},
    {name:'Raj',desc:'Calm authority figure, trusted expert persona',img:unsplashChars[5],uses:9}
];

var templateData = [
    {name:'Glow Up Campaign',niche:'beauty',rating:4.9,uses:1247,img:unsplashTemplates[0]},
    {name:'Tech Unboxing Pro',niche:'tech',rating:4.7,uses:892,img:unsplashTemplates[1]},
    {name:'Fit Transformation',niche:'health',rating:4.8,uses:1056,img:unsplashTemplates[2]},
    {name:'Wealth Blueprint',niche:'finance',rating:4.6,uses:678,img:unsplashTemplates[3]},
    {name:'Style Upgrade',niche:'fashion',rating:4.8,uses:934,img:unsplashTemplates[4]},
    {name:'Home Makeover',niche:'home',rating:4.5,uses:543,img:unsplashTemplates[5]}
];

var genStagesList = [
    {label:'Analyzing Product Identity',icon:'fa-box-open'},
    {label:'Mapping Niche Intelligence',icon:'fa-magnifying-glass-chart'},
    {label:'Building Buyer Persona',icon:'fa-user-pen'},
    {label:'Crafting Hook Strategy',icon:'fa-anchor'},
    {label:'Generating Visual Concepts',icon:'fa-image'},
    {label:'Writing Conversion Scripts',icon:'fa-pen-nib'},
    {label:'Running Performance Predictor',icon:'fa-chart-line'},
    {label:'Final Quality Check',icon:'fa-shield-check'}
];

/* ================================================================
   NAVIGATION
   ================================================================ */
function navigateTo(view){
    S.view=view;
    var secs=document.querySelectorAll('.view-section');
    for(var i=0;i<secs.length;i++) secs[i].classList.remove('active');
    var el=document.getElementById('view'+view.charAt(0).toUpperCase()+view.slice(1));
    if(el) el.classList.add('active');
    var navs=document.querySelectorAll('.nav-item');
    for(var j=0;j<navs.length;j++) navs[j].classList.toggle('active',navs[j].getAttribute('data-nav')===view);
    if(view==='campaign'&&S.step===1) resetCampaign();
    if(view==='settings') loadSettings();
    closeSidebar();
}
function toggleSidebar(){document.getElementById('app').classList.toggle('sidebar-open');document.getElementById('sidebarOverlay').classList.toggle('hidden');}
function closeSidebar(){document.getElementById('app').classList.remove('sidebar-open');document.getElementById('sidebarOverlay').classList.add('hidden');}

/* ================================================================
   CAMPAIGN STEPS (Diperbarui agar super instan dan sinkron data kuat)
   ================================================================ */
function updateState(){
    var elName = document.getElementById('productName');
    var elDesc = document.getElementById('productDesc');
    var elAud = document.getElementById('targetAudience');
    var elNiche = document.getElementById('nicheCategory');
    
    if(elName) S.product.name = elName.value.trim();
    if(elDesc) S.product.desc = elDesc.value.trim();
    if(elAud)  S.product.audience = elAud.value.trim();
    if(elNiche) S.product.niche = elNiche.value.trim();
}

function updateStepUI(){
    var panels=document.querySelectorAll('.step-panel');
    for(var i=0;i<panels.length;i++) panels[i].classList.remove('active');
    var p=document.getElementById('step'+S.step);if(p)p.classList.add('active');
    document.getElementById('stepLabel').textContent='Step '+S.step+' of 6';
    var dots=document.querySelectorAll('.step-dot');
    for(var d=0;d<dots.length;d++){var s=parseInt(dots[d].getAttribute('data-step'));dots[d].style.background=(s<=S.step)?'#e8a030':'#222228';}
}

function nextStep(){
    // SELALU paksakan sinkronisasi data sebelum validasi untuk mencegah bug input
    updateState();
    
    if(S.step===1){
        if(!S.product.name){showToast('Masukkan nama produk','warning');return;}
        if(!S.product.niche){showToast('Pilih niche kategori','warning');return;}
        S.step=2;
        updateStepUI();
        runNicheAnalysis(); // Dipanggil secara instan
    }
    else if(S.step===2){S.step=3;updateStepUI();}
    else if(S.step===3){S.step=4;updateStepUI();renderHookGrid();}
    else if(S.step===4){if(!S.hook){showToast('Pilih hook strategy','warning');return;}S.step=5;updateStepUI();renderOutputCountGrid();}
    else if(S.step===5){S.step=6;updateStepUI();renderDurationGrid();}
}

function prevStep(){if(S.step>1){S.step--;updateStepUI();}}
function resetCampaign(){S.step=1;S.hook=null;S.outputCount=1;S.duration=15;document.getElementById('campaignProgress').classList.remove('hidden');updateStepUI();}

/* ================================================================
   PRODUCT INPUT
   ================================================================ */
function handleProductImage(e){var f=e.target.files[0];if(!f)return;var r=new FileReader();r.onload=function(ev){S.product.image=ev.target.result;document.getElementById('productImg').src=ev.target.result;document.getElementById('productImagePreview').classList.remove('hidden');document.getElementById('productUploadPlaceholder').classList.add('hidden');};r.readAsDataURL(f);}
function addBenefitManual(){var inp=document.getElementById('benefitInput');var v=inp.value.trim();if(!v)return;S.product.benefits.push(v);renderBenefits();inp.value='';}
function removeBenefit(idx){S.product.benefits.splice(idx,1);renderBenefits();}
function renderBenefits(){var h='';for(var i=0;i<S.product.benefits.length;i++){h+='<span class="tag">'+S.product.benefits[i]+'<button onclick="removeBenefit('+i+')"><i class="fa-solid fa-xmark text-[10px]"></i></button></span>';}document.getElementById('benefitsList').innerHTML=h;}

function setupDragDrop(zoneId,handler){var z=document.getElementById(zoneId);if(!z)return;z.addEventListener('dragover',function(e){e.preventDefault();z.classList.add('dragover');});z.addEventListener('dragleave',function(){z.classList.remove('dragover');});z.addEventListener('drop',function(e){e.preventDefault();z.classList.remove('dragover');handler({target:{files:e.dataTransfer.files}});});}

function handleCharImage(e){var f=e.target.files[0];if(!f)return;var r=new FileReader();r.onload=function(ev){S.charImage=ev.target.result;document.getElementById('charImg').src=ev.target.result;document.getElementById('charImagePreview').classList.remove('hidden');document.getElementById('charUploadPlaceholder').classList.add('hidden');};r.readAsDataURL(f);}
function switchCharTab(mode,btn){S.charMode=mode;var tabs=document.querySelectorAll('.char-tab');for(var i=0;i<tabs.length;i++)tabs[i].classList.remove('active');btn.classList.add('active');document.getElementById('charUpload').classList.toggle('hidden',mode!=='upload');document.getElementById('charGenerate').classList.toggle('hidden',mode!=='generate');}

/* ================================================================
   NICHE ANALYSIS (Dibuat INSTAN tanpa setTimeout)
   ================================================================ */
function runNicheAnalysis(){
    try {
        var data = nicheData[S.product.niche];
        if(!data) {
            console.warn("Niche tidak cocok sempurna, fallback ke other");
            data = nicheData.other;
        }
        
        document.getElementById('resNiche').textContent = data.niche || '-';
        document.getElementById('resSubNiche').textContent = data.sub || '-';
        document.getElementById('resMaturity').style.width = (data.maturity || 50) + '%';
        document.getElementById('resMaturityLabel').textContent = data.maturityLabel || '-';
        document.getElementById('resPersona').textContent = data.persona || '-';
        document.getElementById('resStrategy').textContent = data.strategy || '-';
        
        var dh=''; 
        if(data.drivers) { for(var d=0; d<data.drivers.length; d++) dh+='<span class="tag">'+data.drivers[d]+'</span>'; }
        document.getElementById('resDrivers').innerHTML=dh;
        
        var ph=''; 
        if(data.pains) { for(var p=0; p<data.pains.length; p++) ph+='<li class="flex items-start gap-2"><i class="fa-solid fa-circle text-[4px] text-red-400 mt-2"></i>'+data.pains[p]+'</li>'; }
        document.getElementById('resPains').innerHTML=ph;
        
        var drh=''; 
        if(data.desires) { for(var dr=0; dr<data.desires.length; dr++) drh+='<li class="flex items-start gap-2"><i class="fa-solid fa-circle text-[4px] text-amber-400 mt-2"></i>'+data.desires[dr]+'</li>'; }
        document.getElementById('resDesires').innerHTML=drh;
        
        var rh=''; 
        if(data.resistance) { for(var r=0; r<data.resistance.length; r++) rh+='<li class="flex items-start gap-2"><i class="fa-solid fa-circle text-[4px] text-blue-400 mt-2"></i>'+data.resistance[r]+'</li>'; }
        document.getElementById('resResistance').innerHTML=rh;
        
        var ah=''; 
        if(data.angles) {
            for(var a=0; a<data.angles.length; a++){
                var f=(a===0);
                ah+='<div class="flex items-center gap-2 p-2 rounded-lg '+(f?'bg-accent/8 border border-accent/15':'bg-srf-600 border border-brd')+'"><span class="text-xs font-bold '+(f?'text-accent':'text-txt-300')+'">#'+(a+1)+'</span><span class="text-sm '+(f?'text-txt-50':'text-txt-200')+'">'+data.angles[a]+'</span>'+(f?'<i class="fa-solid fa-crown text-accent text-[10px] ml-auto"></i>':'')+'</div>';
            }
        }
        document.getElementById('resAngles').innerHTML=ah;
        
    } catch(err) {
        console.error("Terjadi error ringan pada Niche Analysis, namun proses dilanjutkan:", err);
    }
}

/* ================================================================
   HOOK GRID
   ================================================================ */
function renderHookGrid(){
    var data=nicheData[S.product.niche]||nicheData.other;var recHook=data.recHook;
    document.getElementById('aiHookRec').classList.remove('hidden');
    var recLabel='';for(var h=0;h<hookTypes.length;h++){if(hookTypes[h].id===recHook){recLabel=hookTypes[h].label;break;}}
    document.getElementById('aiHookRecText').textContent='Berdasarkan analisis niche "'+data.niche+'", hook "'+recLabel+'" direkomendasikan.';
    var html='';for(var i=0;i<hookTypes.length;i++){var ht=hookTypes[i];var isR=(ht.id===recHook);var isS=(S.hook===ht.id);
    html+='<div class="hook-card bg-srf-700 border '+(isS?'border-accent selected':'border-brd')+' rounded-xl p-4 relative" onclick="selectHook(\''+ht.id+'\')">';
    if(isR)html+='<div class="absolute -top-2 -right-2 bg-accent text-srf-900 text-[10px] font-bold px-2 py-0.5 rounded-full">AI Pick</div>';
    html+='<div class="w-10 h-10 rounded-lg '+(isS?'bg-accent/15':'bg-srf-500')+' flex items-center justify-center mb-3"><i class="fa-solid '+ht.icon+' '+(isS?'text-accent':'text-txt-200')+' text-sm"></i></div>';
    html+='<p class="font-medium text-sm text-txt-50 mb-1">'+ht.label+'</p><p class="text-xs text-txt-200 leading-relaxed">'+ht.desc+'</p></div>';}
    document.getElementById('hookGrid').innerHTML=html;
}
function selectHook(id){S.hook=id;renderHookGrid();}

/* ================================================================
   OUTPUT COUNT & DURATION
   ================================================================ */
function renderOutputCountGrid(){
    var opts=[{n:1,desc:'Satu konten fokus dengan dampak maksimal'},{n:2,desc:'Dua variasi untuk A/B testing'},{n:3,desc:'Trilogi campaign yang saling melengkapi'},{n:4,desc:'Paket lengkap serial campaign'}];
    var html='';for(var i=0;i<opts.length;i++){var o=opts[i];var isS=(S.outputCount===o.n);
    html+='<div class="option-card bg-srf-700 border '+(isS?'border-accent selected':'border-brd')+' rounded-xl p-5 text-center" onclick="selectOutputCount('+o.n+')">';
    html+='<div class="w-12 h-12 rounded-full '+(isS?'bg-accent text-srf-900':'bg-srf-500 text-txt-200')+' flex items-center justify-center mx-auto mb-3 font-display font-bold text-lg">'+o.n+'</div>';
    html+='<p class="text-sm text-txt-100">'+o.desc+'</p></div>';}
    document.getElementById('outputCountGrid').innerHTML=html;document.getElementById('storyArcNote').classList.toggle('hidden',S.outputCount<2);
}
function selectOutputCount(n){S.outputCount=n;renderOutputCountGrid();}

function renderDurationGrid(){
    var opts=[{d:10,desc:'Ultra-punchy. Hook langsung ke CTA.',pacing:'1 hook + 1 CTA'},{d:15,desc:'Sweet spot untuk Reels/TikTok.',pacing:'Hook + Pain + CTA'},{d:30,desc:'Storytelling lengkap. Convert tinggi.',pacing:'Full funnel script'},{d:45,desc:'Deep dive. Edu-marketing optimal.',pacing:'Extended storytelling'}];
    var html='';for(var i=0;i<opts.length;i++){var o=opts[i];var isS=(S.duration===o.d);
    html+='<div class="option-card bg-srf-700 border '+(isS?'border-accent selected':'border-brd')+' rounded-xl p-5" onclick="selectDuration('+o.d+')">';
    html+='<p class="font-display font-bold text-2xl text-txt-50 mb-1">'+o.d+'<span class="text-sm font-normal text-txt-200">s</span></p>';
    html+='<p class="text-sm text-txt-100 mb-2">'+o.desc+'</p><p class="text-[11px] text-txt-300">'+o.pacing+'</p></div>';}
    document.getElementById('durationGrid').innerHTML=html;
}
function selectDuration(d){S.duration=d;renderDurationGrid();}

/* ================================================================
   GENERATE CAMPAIGN (Dibuat INSTAN, loading hanya 300ms untuk transisi)
   ================================================================ */
function generateCampaign(){
    var overlay=document.getElementById('genOverlay');
    overlay.classList.remove('hidden');
    
    // Tampilkan semua checklist centang hijau secara instan
    var sc=document.getElementById('genStages');
    var sh='';
    for(var i=0;i<genStagesList.length;i++){
        var st=genStagesList[i];
        sh+='<div class="gen-stage done flex items-center gap-3 p-2.5 rounded-lg"><i class="fa-solid '+st.icon+' stage-icon text-[#4ade80] text-sm w-5 text-center"></i><span class="text-sm text-txt-200">'+st.label+'</span><i class="fa-solid fa-check ml-auto text-[#4ade80] text-xs"></i></div>';
    }
    sc.innerHTML=sh;
    
    // Jeda super kilat hanya untuk visual agar pengguna tidak pusing, lalu langsung panggil Output
    setTimeout(function(){
        overlay.classList.add('hidden');
        showFinalOutput();
    }, 400);
}

/* ================================================================
   FINAL OUTPUT
   ================================================================ */
function showFinalOutput(){
    document.getElementById('campaignProgress').classList.add('hidden');
    var panels=document.querySelectorAll('.step-panel');for(var p=0;p<panels.length;p++)panels[p].classList.remove('active');
    var output=document.getElementById('finalOutput');output.classList.add('active');

    var pName=S.product.name||'Your Product';var nData=nicheData[S.product.niche]||nicheData.other;
    var hScripts=hookScripts[S.hook]||hookScripts.problem;var sTemplate=scriptTemplates[S.product.niche]||defaultScript;
    var cohesionScore=92+Math.floor(Math.random()*6);var varLabels=['Hero Shot','Close-Up Detail','Lifestyle Context','Social Proof Angle'];
    var arcLabels=['Awareness','Interest','Desire','Action'];
    var imgKeys=['product','detail','lifestyle','social'];var imgSet=unsplash[S.product.niche]||unsplash.other;

    var campaignData={id:Date.now(),name:pName,niche:S.product.niche,hook:S.hook,outputs:S.outputCount,duration:S.duration,cohesion:cohesionScore,date:new Date().toLocaleString('id-ID'),scores:[]};

    var outputsHTML='';
    for(var i=0;i<S.outputCount;i++){
        var hookArr=hScripts(pName);var hookText=hookArr[i%hookArr.length];
        var engS=78+Math.floor(Math.random()*17);var convS=72+Math.floor(Math.random()*20);
        var emoS=80+Math.floor(Math.random()*16);var brandS=83+Math.floor(Math.random()*14);
        campaignData.scores.push({engagement:engS,conversion:convS,emotional:emoS,brand:brandS});

        var painArr=sTemplate.pain;var desArr=sTemplate.desire;var solArr=sTemplate.solution;var proofArr=sTemplate.proof;var ctaArr=sTemplate.cta;
        var painText=(typeof painArr[0]==='function')?painArr[i%painArr.length](pName):painArr[0];
        var desireText=desArr[i%desArr.length];
        var solutionText=(typeof solArr[0]==='function')?solArr[i%solArr.length](pName):solArr[0];
        var proofText=(typeof proofArr[0]==='function')?proofArr[i%proofArr.length](pName):proofArr[0];
        var ctaText=(typeof ctaArr[0]==='function')?ctaArr[i%ctaArr.length](pName):ctaArr[0];

        var isShort=(S.duration<=10);var isMed=(S.duration<=15);
        var visImg=imgSet[imgKeys[i%imgKeys.length]];
        var charSetEl=document.getElementById('charSetting');var charExprEl=document.getElementById('charExpression');
        var setVal=charSetEl?charSetEl.value:'modern setting';var exprVal=charExprEl?charExprEl.value:'confident';
        var vidPrompt='Cinematic '+S.duration+'s promotional video: '+varLabels[i]+' of '+pName+'. '+nData.persona.split('.')[0]+' in '+setVal+', '+exprVal+'. Product prominently featured. '+nData.strategy+' angle. Professional lighting, shallow depth of field, 4K quality. Mood: '+['premium','warm','trustworthy','dynamic'][i]+'. Camera: '+['medium shot','close-up','wide establishing','over-the-shoulder'][i]+' transitioning to product detail. Color grading: warm golden tones with high contrast.';

        outputsHTML+='<div class="bg-srf-700 border border-brd rounded-xl overflow-hidden" data-output-id="'+i+'">';
        outputsHTML+='<div class="grid grid-cols-1 md:grid-cols-2"><div class="aspect-[4/3] md:aspect-auto relative overflow-hidden"><img src="'+visImg+'" class="w-full h-full object-cover" alt="Visual '+(i+1)+'"><div class="absolute top-3 left-3 bg-srf-900/80 backdrop-blur-sm text-xs font-medium text-accent px-3 py-1 rounded-full">Output #'+(i+1)+' — '+varLabels[i]+'</div></div>';
        outputsHTML+='<div class="p-5"><p class="text-xs text-txt-300 uppercase tracking-wider mb-3 font-semibold">Performance Predictor</p><div class="grid grid-cols-2 gap-x-4 gap-y-2 mb-4">';
        outputsHTML+='<div><div class="flex justify-between text-xs mb-1"><span class="text-txt-200">Engagement</span><span class="text-txt-50 font-medium">'+engS+'%</span></div><div class="score-bar"><div class="score-bar-fill bg-accent" style="--bar-w:'+engS+'%"></div></div></div>';
        outputsHTML+='<div><div class="flex justify-between text-xs mb-1"><span class="text-txt-200">Conversion</span><span class="text-txt-50 font-medium">'+convS+'%</span></div><div class="score-bar"><div class="score-bar-fill bg-green-400" style="--bar-w:'+convS+'%"></div></div></div>';
        outputsHTML+='<div><div class="flex justify-between text-xs mb-1"><span class="text-txt-200">Emotional Pull</span><span class="text-txt-50 font-medium">'+emoS+'%</span></div><div class="score-bar"><div class="score-bar-fill bg-blue-400" style="--bar-w:'+emoS+'%"></div></div></div>';
        outputsHTML+='<div><div class="flex justify-between text-xs mb-1"><span class="text-txt-200">Brand Fit</span><span class="text-txt-50 font-medium">'+brandS+'%</span></div><div class="score-bar"><div class="score-bar-fill bg-purple-400" style="--bar-w:'+brandS+'%"></div></div></div>';
        outputsHTML+='</div></div></div>';

        outputsHTML+='<div class="p-5 border-t border-brd"><p class="text-xs text-accent uppercase tracking-wider mb-2 font-semibold">Hook Script</p><div class="bg-accent/5 border border-accent/10 rounded-lg p-3 mb-4"><p class="text-sm text-txt-50 font-medium italic">"'+hookText+'"</p></div>';
        outputsHTML+='<p class="text-xs text-txt-300 uppercase tracking-wider mb-2 font-semibold">Connected Sales Script</p><div class="space-y-0">';
        if(!isShort)outputsHTML+='<div class="script-section"><p class="section-label">Pain</p><p class="text-sm text-txt-100">'+painText+'</p></div>';
        if(!isShort)outputsHTML+='<div class="script-section"><p class="section-label">Desire</p><p class="text-sm text-txt-100">'+desireText+'</p></div>';
        outputsHTML+='<div class="script-section"><p class="section-label">Solution</p><p class="text-sm text-txt-100">'+solutionText+'</p></div>';
        if(!isMed)outputsHTML+='<div class="script-section"><p class="section-label">Proof</p><p class="text-sm text-txt-100">'+proofText+'</p></div>';
        outputsHTML+='<div class="script-section" style="border-left-color:#e8a030"><p class="section-label" style="color:#e8a030">CTA</p><p class="text-sm text-txt-50 font-medium">'+ctaText+'</p></div>';
        outputsHTML+='</div></div>';

        outputsHTML+='<div class="px-5 pb-5"><p class="text-xs text-txt-300 uppercase tracking-wider mb-2 font-semibold">Video Prompt Ready</p><div class="bg-srf-900 rounded-lg p-3 relative group"><p class="text-xs text-txt-200 leading-relaxed font-mono">'+vidPrompt+'</p><button onclick="copyToClipboard(this.parentElement.querySelector(\'p\').textContent)" class="absolute top-2 right-2 w-7 h-7 rounded bg-srf-500 flex items-center justify-center text-txt-200 hover:text-txt-50 opacity-0 group-hover:opacity-100 transition"><i class="fa-solid fa-copy text-[10px]"></i></button></div></div></div>';
    }

    /* Story Arc */
    var storyArcHTML='';
    if(S.outputCount>=2){
        storyArcHTML='<div class="bg-srf-700 border border-brd rounded-xl p-5 mb-6"><div class="flex items-center gap-2 mb-4"><i class="fa-solid fa-film text-blue-400 text-sm"></i><p class="text-xs text-blue-400 uppercase tracking-wider font-semibold">Story Arc Builder</p></div><div class="flex items-center gap-2 overflow-x-auto pb-2">';
        for(var si=0;si<S.outputCount;si++){storyArcHTML+='<div class="flex items-center gap-2 flex-shrink-0"><div class="w-10 h-10 rounded-full bg-accent/10 border border-accent/20 flex items-center justify-center"><span class="text-xs font-bold text-accent">'+(si+1)+'</span></div><div><p class="text-sm font-medium text-txt-50">'+varLabels[si]+'</p><p class="text-[11px] text-txt-300">'+(arcLabels[si]||'Extension')+'</p></div>'+(si<S.outputCount-1?'<i class="fa-solid fa-arrow-right text-txt-300 text-xs mx-1 flex-shrink-0"></i>':'')+'</div>';}
        storyArcHTML+='</div></div>';
    }

    /* Competitor Lens */
    var compAngles=['Generic before-after','Basic feature listing','Price-focused comparison','Over-produced lifestyle'];var uniqueAngle=nData.angles[0];
    var compHTML='<div class="bg-srf-700 border border-brd rounded-xl p-5"><p class="text-xs text-txt-300 uppercase tracking-wider mb-2">Competitor Lens</p><p class="text-xs text-txt-200 mb-2">Approaches to avoid:</p><div class="flex flex-wrap gap-1.5 mb-3">';
    for(var ci=0;ci<compAngles.length;ci++)compHTML+='<span class="text-[11px] px-2 py-0.5 rounded bg-red-500/8 text-red-400 border border-red-500/15 line-through">'+compAngles[ci]+'</span>';
    compHTML+='</div><p class="text-xs text-accent font-medium">Your unique angle: '+uniqueAngle+'</p></div>';

    /* Quality Systems */
    var qsHTML='<div class="bg-srf-700 border border-brd rounded-xl p-5"><p class="text-xs text-txt-300 uppercase tracking-wider mb-2">Quality Systems Active</p><div class="space-y-2">';
    var qsItems=['Character Consistency Engine','Product Integrity Lock','Environment Locking','Style Diversity Layer','Conversion Optimization','Audience Emotion Mapping'];
    for(var qi=0;qi<qsItems.length;qi++)qsHTML+='<div class="flex items-center gap-2"><i class="fa-solid fa-circle-check text-green-400 text-[10px]"></i><span class="text-xs text-txt-100">'+qsItems[qi]+'</span></div>';
    qsHTML+='</div></div>';

    /* Cohesion SVG */
    var circDash=(cohesionScore/100)*220;
    var cohHTML='<div class="bg-srf-700 border border-brd rounded-xl p-5 text-center"><p class="text-xs text-txt-300 uppercase tracking-wider mb-2">Campaign Cohesion</p><div class="relative w-20 h-20 mx-auto mb-2"><svg class="w-20 h-20 -rotate-90" viewBox="0 0 80 80"><circle cx="40" cy="40" r="35" fill="none" stroke="#222228" stroke-width="5"/><circle cx="40" cy="40" r="35" fill="none" stroke="#e8a030" stroke-width="5" stroke-dasharray="'+circDash+' 220" stroke-linecap="round"/></svg><span class="absolute inset-0 flex items-center justify-center font-display font-bold text-lg text-accent">'+cohesionScore+'</span></div><p class="text-xs text-green-400">Excellent Cohesion</p></div>';

    /* Assemble */
    var fHTML='<div class="mb-8"><div class="flex items-center gap-3 mb-2"><div class="w-10 h-10 rounded-xl bg-accent/10 flex items-center justify-center"><i class="fa-solid fa-check-double text-accent"></i></div><div><h2 class="font-display text-2xl font-bold text-txt-50">Campaign Ready</h2><p class="text-sm text-txt-200">'+pName+' — '+S.outputCount+' Output'+(S.outputCount>1?'s':'')+' ('+S.duration+'s)</p></div></div></div>';
    fHTML+='<div class="grid grid-cols-1 md:grid-cols-3 gap-4 mb-6">'+cohHTML+compHTML+qsHTML+'</div>';
    fHTML+=storyArcHTML;
    fHTML+='<div class="space-y-6">'+outputsHTML+'</div>';
    fHTML+='<div class="flex flex-wrap gap-3 mt-8 justify-center no-print">';
    fHTML+='<button onclick="exportPDF()" class="px-6 py-2.5 rounded-lg bg-red-500/10 border border-red-500/20 text-red-400 font-semibold text-sm hover:bg-red-500/20 transition"><i class="fa-solid fa-file-pdf mr-2"></i> Export PDF</button>';
    fHTML+='<button onclick="saveCampaignToLS()" class="px-6 py-2.5 rounded-lg bg-accent text-srf-900 font-semibold text-sm hover:bg-accent-light transition"><i class="fa-solid fa-bookmark mr-2"></i> Save Campaign</button>';
    fHTML+='<button onclick="resetCampaign()" class="px-6 py-2.5 rounded-lg bg-srf-600 border border-brd text-txt-100 text-sm hover:bg-srf-500 transition"><i class="fa-solid fa-plus mr-2"></i> New Campaign</button>';
    fHTML+='</div>';

    output.innerHTML=fHTML;
    window._currentCampaignData=campaignData;
}

/* ================================================================
   SAVE CAMPAIGN TO LOCALSTORAGE
   ================================================================ */
function saveCampaignToLS(){
    if(!window._currentCampaignData){showToast('Tidak ada data campaign','warning');return;}
    var camps=lsLoad('campaigns',[]);
    camps.unshift(window._currentCampaignData);
    if(camps.length>50)camps=camps.slice(0,50);
    lsSave('campaigns',camps);
    showToast('Campaign berhasil disimpan secara lokal','success');
    renderDashboard();renderAnalytics();updateLSCounts();
}

function exportPDF(){
    var source=document.getElementById('finalOutput');
    if(!source){showToast('Tidak ada campaign untuk diekspor','warning');return;}
    showToast('Membuat PDF...','info');
    var opt={margin:[10,10,10,10],filename:'AI-Promo-Studio-Campaign.pdf',image:{type:'jpeg',quality:0.95},html2canvas:{scale:2,useCORS:true,backgroundColor:'#09090b'},jsPDF:{unit:'mm',format:'a4',orientation:'portrait'}};
    html2pdf().set(opt).from(source).save().then(function(){showToast('PDF berhasil diunduh','success');}).catch(function(){showToast('Gagal membuat PDF','warning');});
}

function showToast(msg,type){
    type=type||'info';var t=document.getElementById('toast');
    var c={success:'bg-green-500/15 border border-green-500/25 text-green-400',warning:'bg-amber-500/15 border border-amber-500/25 text-amber-400',info:'bg-blue-500/15 border border-blue-500/25 text-blue-400'};
    var ic={success:'fa-circle-check',warning:'fa-triangle-exclamation',info:'fa-circle-info'};
    t.className='toast '+(c[type]||c.info);t.innerHTML='<i class="fa-solid '+(ic[type]||ic.info)+' mr-2"></i>'+msg;t.classList.remove('hidden');
    setTimeout(function(){t.classList.add('hidden');},3000);
}

function copyToClipboard(text){if(navigator.clipboard&&window.isSecureContext){navigator.clipboard.writeText(text).then(function(){showToast('Copied to clipboard','success');});}else{var ta=document.createElement('textarea');ta.value=text;ta.style.position='fixed';ta.style.opacity='0';document.body.appendChild(ta);ta.select();try{document.execCommand('copy');showToast('Copied to clipboard','success');}catch(err){showToast('Gagal menyalin text','warning');}document.body.removeChild(ta);}}

/* ================================================================
   SETTINGS (Local Storage)
   ================================================================ */
function loadSettings() {
    var s = lsLoad('settings', {name:'John Doe', email:'john@example.com', voice:'Professional & Trusted', tone:'Conversational', keywords:'premium, terpercaya, hasil nyata'});
    document.getElementById('settingsName').value = s.name;
    document.getElementById('settingsEmail').value = s.email;
    document.getElementById('settingsVoice').value = s.voice;
    document.getElementById('settingsTone').value = s.tone;
    document.getElementById('settingsKeywords').value = s.keywords;
    document.getElementById('dashName').textContent = s.name.split(' ')[0] || 'User';
    document.getElementById('sidebarUserName').textContent = s.name || 'User';
}

function saveSettings() {
    var s = {
        name: document.getElementById('settingsName').value,
        email: document.getElementById('settingsEmail').value,
        voice: document.getElementById('settingsVoice').value,
        tone: document.getElementById('settingsTone').value,
        keywords: document.getElementById('settingsKeywords').value
    };
    lsSave('settings', s);
    loadSettings();
    showToast('Perubahan berhasil disimpan', 'success');
}

/* ================================================================
   RENDER VIEWS
   ================================================================ */
function renderDashboard(){
    var camps=lsLoad('campaigns',[]);var chars=lsLoad('characters',[]);
    document.getElementById('statCampaigns').textContent=camps.length;
    document.getElementById('statChars').textContent=chars.length;
    var nicheIcons={beauty:'fa-spa',tech:'fa-microchip',health:'fa-dumbbell',finance:'fa-chart-pie',fashion:'fa-shirt',food:'fa-utensils',home:'fa-house',education:'fa-graduation-cap'};
    if(camps.length===0){document.getElementById('recentCampaigns').innerHTML='<p class="text-sm text-txt-300 text-center py-8">Belum ada campaign. Buat campaign pertamamu.</p>';document.getElementById('statScore').textContent='0';document.getElementById('statConversions').textContent='0';}
    else{
        var html='';var totalScore=0;var totalConv=0;var shown=Math.min(5,camps.length);
        for(var i=0;i<shown;i++){var c=camps[i];var icon=nicheIcons[c.niche]||'fa-cube';
        var avgScore=0;var avgConv=0;
        if(c.scores&&c.scores.length){var se=0,sc2=0;for(var s=0;s<c.scores.length;s++){se+=c.scores[s].engagement;sc2+=c.scores[s].conversion;}avgScore=Math.round(se/c.scores.length);avgConv=Math.round(sc2/c.scores.length);}
        totalScore+=avgScore;totalConv+=avgConv;
        html+='<div class="flex items-center gap-4 p-3 rounded-lg bg-srf-600 border border-brd hover:border-brd-hover transition cursor-pointer"><div class="w-11 h-11 rounded-lg bg-srf-500 flex items-center justify-center flex-shrink-0"><i class="fa-solid '+icon+' text-txt-200 text-sm"></i></div><div class="flex-1 min-w-0"><p class="text-sm font-medium text-txt-50 truncate">'+c.name+'</p><p class="text-xs text-txt-300">'+c.outputs+' output'+(c.outputs>1?'s':'')+' · '+c.date+'</p></div><div class="text-right flex-shrink-0"><span class="text-sm font-display font-bold '+(avgScore>=90?'text-green-400':'text-accent')+'">'+avgScore+'</span><p class="text-[10px] text-txt-300">score</p></div></div>';}
        document.getElementById('recentCampaigns').innerHTML=html;
        document.getElementById('statScore').textContent=(totalScore/shown).toFixed(1);
        document.getElementById('statConversions').textContent=totalConv;
    }
    var bars=[65,72,68,80,85,78,88,92,87,90,85,94];var ch='';for(var b=0;b<bars.length;b++){var isL=(b===bars.length-1);ch+='<div class="flex-1 rounded-t-sm transition-all hover:opacity-80" style="height:'+bars[b]+'%;background:'+(isL?'#e8a030':'rgba(232,160,48,0.25)')+'" title="'+bars[b]+'"></div>';}
    document.getElementById('perfChart').innerHTML=ch;
}

function renderSavedChars(){
    var chars=lsLoad('characters',[]);
    if(chars.length===0)chars=defaultChars.map(function(c){return{name:c.name,desc:c.desc,img:c.img,uses:c.uses};});
    var html='';
    for(var i=0;i<chars.length;i++){var c=chars[i];
    html+='<div class="bg-srf-700 border border-brd rounded-xl overflow-hidden hover:border-accent/40 transition cursor-pointer group">';
    html+='<div class="aspect-[3/4] relative overflow-hidden"><img src="'+c.img+'" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500" alt="'+c.name+'" onerror="this.src=\'https://images.unsplash.com/photo-1535713875002-d1d0cf377fde?w=300&h=400&fit=crop&auto=format\'">';
    html+='<div class="absolute top-2 right-2 bg-srf-900/80 backdrop-blur-sm text-xs font-medium text-txt-50 px-2 py-1 rounded-md"><i class="fa-solid fa-star text-accent mr-1 text-[10px]"></i>'+c.uses+' uses</div>';
    html+='<div class="absolute bottom-0 left-0 right-0 bg-gradient-to-t from-srf-900/90 to-transparent p-4 translate-y-full group-hover:translate-y-0 transition-transform duration-300"><div class="flex gap-2"><button onclick="useCharacter('+i+')" class="flex-1 py-2 rounded-lg bg-accent text-srf-900 text-xs font-semibold hover:bg-accent-light transition">Use</button><button onclick="deleteCharacter('+i+')" class="py-2 px-3 rounded-lg bg-red-500/20 text-red-400 text-xs hover:bg-red-500/30 transition"><i class="fa-solid fa-trash"></i></button></div></div></div>';
    html+='<div class="p-4"><h3 class="font-display font-semibold text-txt-50">'+c.name+'</h3><p class="text-xs text-txt-200 mt-1">'+c.desc+'</p></div></div>';}
    document.getElementById('savedCharsGrid').innerHTML=html;
}
function useCharacter(idx){var chars=lsLoad('characters',[]);if(chars[idx]){showToast('Karakter "'+chars[idx].name+'" dipilih','success');navigateTo('campaign');}}
function deleteCharacter(idx){var chars=lsLoad('characters',[]);if(chars[idx]){chars.splice(idx,1);lsSave('characters',chars);renderSavedChars();updateLSCounts();showToast('Karakter dihapus','info');}}

function renderHookLibrary(filter){
    filter=filter||'all';var types=['all'];for(var t=0;t<hookTypes.length;t++)if(types.indexOf(hookTypes[t].id)===-1)types.push(hookTypes[t].id);
    var tabs='';for(var ti=0;ti<types.length;ti++){var tid=types[ti];var label=(tid==='all')?'All':'';if(tid!=='all')for(var ht=0;ht<hookTypes.length;ht++)if(hookTypes[ht].id===tid){label=hookTypes[ht].label;break;}tabs+='<button class="filter-tab '+(filter===tid?'active':'')+'" onclick="renderHookLibrary(\''+tid+'\')">'+label+'</button>';}
    document.getElementById('hookFilterTabs').innerHTML=tabs;
    var items='';for(var h=0;h<hookLibrary.length;h++){var item=hookLibrary[h];if(filter!=='all'&&item.type!==filter)continue;
    var tl='';for(var f=0;f<hookTypes.length;f++)if(hookTypes[f].id===item.type){tl=hookTypes[f].label;var ticon=hookTypes[f].icon;break;}
    items+='<div class="bg-srf-700 border border-brd rounded-xl p-4 flex items-center gap-4 hover:border-brd-hover transition group"><div class="w-10 h-10 rounded-lg bg-srf-500 flex items-center justify-center flex-shrink-0"><i class="fa-solid '+(ticon||'fa-anchor')+' text-txt-200 text-sm"></i></div><div class="flex-1 min-w-0"><p class="text-sm text-txt-50 font-medium">"'+item.text+'"</p><p class="text-xs text-txt-300 mt-1">'+tl+' · Used '+item.used+' times</p></div><div class="text-right flex-shrink-0"><p class="text-sm font-display font-bold text-accent">'+item.perf+'</p><p class="text-[10px] text-txt-300">perf</p></div><button onclick="copyToClipboard(\''+item.text.replace(/'/g,"\\'")+'\')" class="w-8 h-8 rounded-lg bg-srf-500 flex items-center justify-center text-txt-300 hover:text-txt-50 opacity-0 group-hover:opacity-100 transition flex-shrink-0"><i class="fa-solid fa-copy text-[10px]"></i></button></div>';}
    if(!items)items='<div class="text-center py-12 text-txt-300 text-sm">Tidak ada hook untuk filter ini.</div>';
    document.getElementById('hookLibraryList').innerHTML=items;
}

function renderTemplates(){
    var nc={beauty:'from-pink-500/20 to-rose-500/20',tech:'from-cyan-500/20 to-blue-500/20',health:'from-green-500/20 to-emerald-500/20',finance:'from-amber-500/20 to-yellow-500/20',fashion:'from-purple-500/20 to-fuchsia-500/20',home:'from-orange-500/20 to-red-500/20'};
    var html='';for(var i=0;i<templateData.length;i++){var t=templateData[i];var g=nc[t.niche]||'from-srf-500 to-srf-400';
    html+='<div class="bg-srf-700 border border-brd rounded-xl overflow-hidden hover:border-accent/30 transition cursor-pointer group"><div class="aspect-[16/10] relative overflow-hidden"><img src="'+t.img+'" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500" alt="'+t.name+'"><div class="absolute inset-0 bg-gradient-to-t '+g+'"></div><div class="absolute top-3 left-3 bg-srf-900/80 backdrop-blur-sm text-[10px] font-medium text-accent px-2 py-1 rounded-full uppercase tracking-wider">'+t.niche+'</div></div><div class="p-4"><div class="flex items-center justify-between mb-2"><h3 class="font-display font-semibold text-txt-50">'+t.name+'</h3><div class="flex items-center gap-1"><i class="fa-solid fa-star text-accent text-[10px]"></i><span class="text-sm font-medium text-txt-50">'+t.rating+'</span></div></div><p class="text-xs text-txt-300">'+t.uses+' uses</p><button onclick="navigateTo(\'campaign\');showToast(\'Template loaded\',\'info\')" class="w-full mt-3 py-2 rounded-lg bg-srf-600 border border-brd text-txt-100 text-xs font-medium hover:bg-srf-500 transition">Use Template</button></div></div>';}
    document.getElementById('templatesGrid').innerHTML=html;
}

function renderAnalytics(){
    var camps=lsLoad('campaigns',[]);
    if(camps.length===0){
        document.getElementById('anaScore').textContent='0';
        document.getElementById('anaConv').textContent='0%';
        document.getElementById('anaHook').textContent='0%';
        document.getElementById('topHooksAnalytics').innerHTML='<p class="text-sm text-txt-300 text-center py-8">Belum ada data.</p>';
        document.getElementById('nichePerformance').innerHTML='<p class="text-sm text-txt-300 text-center py-8">Belum ada data.</p>';
        return;
    }

    var totalEng=0, totalConv=0, count=0; 
    var hookCount={}; var nicheCount={}; var nicheScoreSum={};

    for(var i=0;i<camps.length;i++){
        var c=camps[i];
        if(!c.scores)continue;
        for(var s=0;s<c.scores.length;s++){
            totalEng+=c.scores[s].engagement;
            totalConv+=c.scores[s].conversion;
            count++;
        }
        if(c.hook) hookCount[c.hook] = (hookCount[c.hook]||0) + 1;
        if(c.niche){
            nicheCount[c.niche] = (nicheCount[c.niche]||0) + 1;
            if(!nicheScoreSum[c.niche]) nicheScoreSum[c.niche] = 0;
            var sa=0;
            if(c.scores) {
                for(var s2=0;s2<c.scores.length;s2++) sa+=c.scores[s2].engagement;
            }
            nicheScoreSum[c.niche] += sa;
        }
    }
    
    var avgEng = count ? Math.round(totalEng/count) : 0;
    var avgConv = count ? Math.round(totalConv/count) : 0;
    
    document.getElementById('anaScore').textContent=avgEng;
    document.getElementById('anaConv').textContent=avgConv+'%';
    document.getElementById('anaHook').textContent=Math.min(99,avgEng+5)+'%';

    var hookArr=[];
    for(var hk in hookCount) hookArr.push({type:hk,count:hookCount[hk]});
    hookArr.sort(function(a,b){return b.count-a.count;});
    
    var thHTML='';
    for(var hi=0;hi<Math.min(5,hookArr.length);hi++){
        var hko = hookArr[hi];
        var hl='';
        for(var hf=0;hf<hookTypes.length;hf++) {
            if(hookTypes[hf].id === hko.type){ hl=hookTypes[hf].label; break; }
        }
        thHTML+='<div class="flex items-center gap-3 p-2 rounded-lg bg-srf-600"><span class="text-xs font-bold text-accent w-5">#'+(hi+1)+'</span><div class="flex-1"><p class="text-sm text-txt-100">'+hl+'</p></div><span class="text-sm font-display font-bold text-txt-50">'+hko.count+'</span></div>';
    }
    document.getElementById('topHooksAnalytics').innerHTML=thHTML||'<p class="text-sm text-txt-300 text-center py-4">Belum ada data hook.</p>';

    var nicheColors = {beauty:'bg-pink-400',tech:'bg-cyan-400',health:'bg-green-400',finance:'bg-amber-400',fashion:'bg-purple-400',food:'bg-orange-400',home:'bg-red-400',education:'bg-blue-400'};
    var npHTML='';
    var nicheArr=[];

    for (var ni in nicheCount) {
        var totalOutputs = 0;
        for (var ci = 0; ci < camps.length; ci++) {
            if (camps[ci].niche === ni && camps[ci].scores) totalOutputs += camps[ci].scores.length;
        }
        var avg = totalOutputs > 0 ? Math.round(nicheScoreSum[ni] / totalOutputs) : 0;
        var label = nicheData[ni] ? nicheData[ni].niche : ni;
        nicheArr.push({niche: label, score: avg, color: nicheColors[ni] || 'bg-accent'});
    }
    
    nicheArr.sort(function(a, b){ return b.score - a.score; });
    
    for (var x = 0; x < nicheArr.length; x++) {
        var nio = nicheArr[x];
        npHTML += '<div>';
        npHTML += '<div class="flex justify-between text-sm mb-1"><span class="text-txt-100">' + nio.niche + '</span><span class="text-txt-50 font-medium">' + nio.score + '</span></div>';
        npHTML += '<div class="score-bar"><div class="score-bar-fill ' + nio.color + '" style="--bar-w:' + nio.score + '%"></div></div>';
        npHTML += '</div>';
    }
    document.getElementById('nichePerformance').innerHTML = npHTML || '<p class="text-sm text-txt-300 text-center py-4">Belum ada data niche.</p>';
}

/* ================================================================
   INITIALIZATION
   ================================================================ */
document.addEventListener('DOMContentLoaded', function() {
    setupDragDrop('productUploadZone', handleProductImage);
    setupDragDrop('charUploadZone', handleCharImage);
    var ageSlider = document.getElementById('charAge');
    if (ageSlider) ageSlider.addEventListener('input', function() { document.getElementById('charAgeVal').textContent = this.value; });

    loadSettings();
    updateLSCounts();
    renderDashboard();
    renderSavedChars();
    renderHookLibrary('all');
    renderTemplates();
    renderAnalytics();
});
</script>
</body>
</html>
