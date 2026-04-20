<!doctype html>
<html lang="en" class="h-full">
 <head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Excel Expert Portfolio</title>
  <script src="https://cdn.tailwindcss.com/3.4.17"></script>
  <script src="https://cdn.jsdelivr.net/npm/lucide@0.263.0/dist/umd/lucide.min.js"></script>
  <script src="/_sdk/element_sdk.js"></script>
  <link href="https://fonts.googleapis.com/css2?family=DM+Sans:wght@400;500;600;700&amp;family=Space+Mono:wght@400;700&amp;display=swap" rel="stylesheet">
  <script>
tailwind.config = {
  theme: {
    extend: {
      fontFamily: {
        heading: ['Space Mono', 'monospace'],
        body: ['DM Sans', 'sans-serif']
      }
    }
  }
}
</script>
  <style>
html, body { height: 100%; margin: 0; }

/* Grid background */
.grid-bg {
  background-image:
    linear-gradient(rgba(59,130,246,0.06) 1px, transparent 1px),
    linear-gradient(90deg, rgba(59,130,246,0.06) 1px, transparent 1px);
  background-size: 40px 40px;
}

/* Animated gradient orb */
.orb {
  position: absolute;
  border-radius: 50%;
  filter: blur(80px);
  opacity: 0.15;
  animation: float 8s ease-in-out infinite;
}
@keyframes float {
  0%, 100% { transform: translateY(0) scale(1); }
  50% { transform: translateY(-30px) scale(1.05); }
}

/* Skill bar animation */
.skill-fill {
  width: 0;
  transition: width 1.2s cubic-bezier(0.4, 0, 0.2, 1);
}
.skill-fill.active {
  width: var(--target-width);
}

/* Fade in on scroll */
.fade-up {
  opacity: 0;
  transform: translateY(30px);
  transition: opacity 0.7s ease, transform 0.7s ease;
}
.fade-up.visible {
  opacity: 1;
  transform: translateY(0);
}

/* Stagger children */
.stagger > .fade-up:nth-child(1) { transition-delay: 0.05s; }
.stagger > .fade-up:nth-child(2) { transition-delay: 0.1s; }
.stagger > .fade-up:nth-child(3) { transition-delay: 0.15s; }
.stagger > .fade-up:nth-child(4) { transition-delay: 0.2s; }
.stagger > .fade-up:nth-child(5) { transition-delay: 0.25s; }

/* Nav */
.nav-scrolled {
  background: rgba(10, 15, 28, 0.92);
  backdrop-filter: blur(12px);
  border-bottom: 1px solid rgba(59,130,246,0.15);
}

/* Project card hover */
.project-card {
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}
.project-card:hover {
  transform: translateY(-6px);
  box-shadow: 0 12px 40px rgba(59,130,246,0.15);
}

/* Smooth scroll */
html { scroll-behavior: smooth; }

/* Toast */
.toast {
  animation: slideUp 0.4s ease, fadeOut 0.4s ease 2.6s forwards;
}
@keyframes slideUp {
  from { transform: translateY(20px); opacity: 0; }
  to { transform: translateY(0); opacity: 1; }
}
@keyframes fadeOut {
  to { opacity: 0; transform: translateY(-10px); }
}
</style>
  <style>body { box-sizing: border-box; }</style>
  <script src="/_sdk/data_sdk.js" type="text/javascript"></script>
 </head>
 <body class="h-full bg-[#0a0f1c] text-gray-200 font-body overflow-auto"><!-- NAV -->
  <nav id="mainNav" class="fixed top-0 left-0 w-full z-50 transition-all duration-300 px-6 py-4">
   <div class="max-w-6xl mx-auto flex items-center justify-between"><a href="#hero" class="font-heading font-bold text-lg tracking-tight" id="navLogo"> <span class="text-blue-400">&lt;</span>Excel<span class="text-blue-400">/&gt;</span> </a>
    <div class="hidden md:flex items-center gap-8 text-sm font-medium"><a href="#about" class="hover:text-blue-400 transition-colors">About</a> <a href="#skills" class="hover:text-blue-400 transition-colors">Skills</a> <a href="#projects" class="hover:text-blue-400 transition-colors">Projects</a> <a href="#tools" class="hover:text-blue-400 transition-colors">Tools</a> <a href="#contact" class="px-4 py-2 bg-blue-600 hover:bg-blue-500 rounded-lg transition-colors text-white">Contact</a>
    </div><button id="mobileMenuBtn" class="md:hidden text-gray-300 hover:text-white" aria-label="Menu"> <i data-lucide="menu" style="width:24px;height:24px;"></i> </button>
   </div><!-- Mobile menu -->
   <div id="mobileMenu" class="hidden md:hidden mt-4 pb-4 border-t border-gray-700/50 pt-4 flex flex-col gap-4 text-sm font-medium"><a href="#about" class="hover:text-blue-400">About</a> <a href="#skills" class="hover:text-blue-400">Skills</a> <a href="#projects" class="hover:text-blue-400">Projects</a> <a href="#tools" class="hover:text-blue-400">Tools</a> <a href="#contact" class="hover:text-blue-400">Contact</a>
   </div>
  </nav><!-- HERO -->
  <section id="hero" class="relative min-h-[100%] flex items-center justify-center grid-bg overflow-hidden px-6">
   <div class="orb w-72 h-72 bg-blue-500 top-[10%] left-[15%]"></div>
   <div class="orb w-96 h-96 bg-cyan-500 bottom-[10%] right-[10%]" style="animation-delay:-3s;"></div><!-- Decorative spreadsheet cells -->
   <div class="absolute top-20 right-[8%] hidden lg:grid grid-cols-3 gap-px opacity-20">
    <div class="w-16 h-8 border border-blue-500/40 rounded-sm flex items-center justify-center text-[10px] text-blue-400 font-heading">
     A1
    </div>
    <div class="w-16 h-8 border border-blue-500/40 rounded-sm flex items-center justify-center text-[10px] text-blue-400 font-heading">
     B1
    </div>
    <div class="w-16 h-8 border border-blue-500/40 rounded-sm flex items-center justify-center text-[10px] text-blue-400 font-heading">
     C1
    </div>
    <div class="w-16 h-8 border border-blue-500/40 rounded-sm flex items-center justify-center text-[10px] text-green-400 font-heading">
     247
    </div>
    <div class="w-16 h-8 border border-blue-500/40 rounded-sm flex items-center justify-center text-[10px] text-green-400 font-heading">
     891
    </div>
    <div class="w-16 h-8 border border-blue-500/40 rounded-sm flex items-center justify-center text-[10px] text-green-400 font-heading">
     1,138
    </div>
   </div>
   <div class="relative z-10 text-center max-w-3xl mx-auto">
    <div class="inline-block mb-6 px-4 py-1.5 border border-blue-500/30 rounded-full text-blue-400 text-xs font-heading tracking-widest uppercase">
     =VLOOKUP("Excellence", Skills, 2, TRUE)
    </div>
    <h1 id="heroName" class="font-heading text-4xl sm:text-5xl lg:text-6xl font-bold text-white mb-4 leading-tight">Your Name</h1>
    <p id="heroTitle" class="text-lg sm:text-xl text-blue-400 font-medium mb-4">Microsoft Excel Expert &amp; Data Analyst</p>
    <p id="heroTagline" class="text-gray-400 text-base sm:text-lg mb-10 max-w-xl mx-auto">Transforming data into clear, actionable insights</p>
    <div class="flex flex-wrap justify-center gap-4"><a href="#projects" class="px-8 py-3 bg-blue-600 hover:bg-blue-500 text-white rounded-lg font-semibold transition-all hover:shadow-lg hover:shadow-blue-600/25 flex items-center gap-2"> <i data-lucide="layout-grid" style="width:18px;height:18px;"></i> View Projects </a> <a href="#contact" class="px-8 py-3 border border-gray-600 hover:border-blue-400 text-gray-300 hover:text-blue-400 rounded-lg font-semibold transition-all flex items-center gap-2"> <i data-lucide="mail" style="width:18px;height:18px;"></i> Contact Me </a>
    </div>
   </div><!-- Scroll indicator -->
   <div class="absolute bottom-8 left-1/2 -translate-x-1/2 flex flex-col items-center gap-2 text-gray-500 text-xs"><span>Scroll</span> <i data-lucide="chevron-down" style="width:16px;height:16px;" class="animate-bounce"></i>
   </div>
  </section><!-- ABOUT -->
  <section id="about" class="py-24 px-6">
   <div class="max-w-5xl mx-auto">
    <div class="fade-up flex flex-col lg:flex-row gap-12 items-center"><!-- Avatar area -->
     <div class="flex-shrink-0 w-52 h-52 rounded-2xl bg-gradient-to-br from-blue-600/20 to-cyan-600/20 border border-blue-500/20 flex items-center justify-center">
      <div class="text-center">
       <div class="text-5xl mb-2">
        📊
       </div><span class="font-heading text-xs text-blue-400 tracking-wider">DATA DRIVEN</span>
      </div>
     </div>
     <div>
      <h2 class="font-heading text-2xl sm:text-3xl font-bold text-white mb-2">About Me</h2>
      <div class="w-12 h-1 bg-blue-500 rounded mb-6"></div>
      <p id="aboutText" class="text-gray-400 leading-relaxed mb-6">With over a decade of experience transforming raw data into meaningful business intelligence, I specialize in building powerful Excel solutions that save time, reduce errors, and drive smarter decisions. From complex financial models to automated reporting systems, I bring precision and clarity to every spreadsheet I touch.</p>
      <div class="grid grid-cols-2 sm:grid-cols-3 gap-4">
       <div class="flex items-center gap-2 text-sm">
        <i data-lucide="bar-chart-2" style="width:16px;height:16px;" class="text-blue-400"></i><span>Data Analysis</span>
       </div>
       <div class="flex items-center gap-2 text-sm">
        <i data-lucide="table" style="width:16px;height:16px;" class="text-blue-400"></i><span>Pivot Tables</span>
       </div>
       <div class="flex items-center gap-2 text-sm">
        <i data-lucide="layout-dashboard" style="width:16px;height:16px;" class="text-blue-400"></i><span>Dashboards</span>
       </div>
       <div class="flex items-center gap-2 text-sm">
        <i data-lucide="function-square" style="width:16px;height:16px;" class="text-blue-400"></i><span>Formulas</span>
       </div>
       <div class="flex items-center gap-2 text-sm">
        <i data-lucide="zap" style="width:16px;height:16px;" class="text-blue-400"></i><span>Automation</span>
       </div>
       <div class="flex items-center gap-2 text-sm">
        <i data-lucide="pie-chart" style="width:16px;height:16px;" class="text-blue-400"></i><span>Visualization</span>
       </div>
      </div>
     </div>
    </div>
   </div>
  </section><!-- SKILLS -->
  <section id="skills" class="py-24 px-6 bg-[#0d1225]">
   <div class="max-w-4xl mx-auto">
    <div class="text-center mb-16 fade-up">
     <h2 class="font-heading text-2xl sm:text-3xl font-bold text-white mb-2">Core Skills</h2>
     <div class="w-12 h-1 bg-blue-500 rounded mx-auto mb-4"></div>
     <p class="text-gray-400">Expertise honed through years of real-world data challenges</p>
    </div>
    <div class="space-y-6 stagger" id="skillBars"><!-- Skills rendered by JS -->
    </div>
   </div>
  </section><!-- PROJECTS -->
  <section id="projects" class="py-24 px-6">
   <div class="max-w-6xl mx-auto">
    <div class="text-center mb-16 fade-up">
     <h2 class="font-heading text-2xl sm:text-3xl font-bold text-white mb-2">Featured Projects</h2>
     <div class="w-12 h-1 bg-blue-500 rounded mx-auto mb-4"></div>
     <p class="text-gray-400">A selection of Excel solutions I've built for real business needs</p>
    </div>
    <div class="grid sm:grid-cols-2 gap-6 stagger" id="projectGrid"><!-- Projects rendered by JS -->
    </div>
   </div>
  </section><!-- TOOLS -->
  <section id="tools" class="py-24 px-6 bg-[#0d1225]">
   <div class="max-w-4xl mx-auto">
    <div class="text-center mb-16 fade-up">
     <h2 class="font-heading text-2xl sm:text-3xl font-bold text-white mb-2">Tools &amp; Technologies</h2>
     <div class="w-12 h-1 bg-blue-500 rounded mx-auto mb-4"></div>
    </div>
    <div class="grid grid-cols-1 sm:grid-cols-3 gap-6 stagger" id="toolsGrid"><!-- Tools rendered by JS -->
    </div>
   </div>
  </section><!-- CONTACT -->
  <section id="contact" class="py-24 px-6">
   <div class="max-w-2xl mx-auto">
    <div class="text-center mb-12 fade-up">
     <h2 id="contactHeading" class="font-heading text-2xl sm:text-3xl font-bold text-white mb-2">Let's Work Together</h2>
     <div class="w-12 h-1 bg-blue-500 rounded mx-auto mb-4"></div>
     <p id="contactSubtext" class="text-gray-400">Let's work together on your data needs</p>
    </div>
    <form id="contactForm" class="fade-up space-y-5 bg-[#0d1225] border border-gray-800 rounded-2xl p-8">
     <div><label for="nameInput" class="block text-sm font-medium text-gray-300 mb-1">Name</label> <input id="nameInput" type="text" placeholder="Your name" class="w-full px-4 py-3 bg-[#0a0f1c] border border-gray-700 rounded-lg text-gray-200 placeholder-gray-600 focus:outline-none focus:border-blue-500 transition-colors">
     </div>
     <div><label for="emailInput" class="block text-sm font-medium text-gray-300 mb-1">Email</label> <input id="emailInput" type="email" placeholder="you@example.com" class="w-full px-4 py-3 bg-[#0a0f1c] border border-gray-700 rounded-lg text-gray-200 placeholder-gray-600 focus:outline-none focus:border-blue-500 transition-colors">
     </div>
     <div><label for="messageInput" class="block text-sm font-medium text-gray-300 mb-1">Message</label> <textarea id="messageInput" rows="4" placeholder="Tell me about your project..." class="w-full px-4 py-3 bg-[#0a0f1c] border border-gray-700 rounded-lg text-gray-200 placeholder-gray-600 focus:outline-none focus:border-blue-500 transition-colors resize-none"></textarea>
     </div><button type="submit" class="w-full py-3 bg-blue-600 hover:bg-blue-500 text-white rounded-lg font-semibold transition-all flex items-center justify-center gap-2"> <i data-lucide="send" style="width:18px;height:18px;"></i> Send Message </button>
     <div id="formSuccess" class="hidden text-center text-green-400 text-sm py-2"><i data-lucide="check-circle" style="width:16px;height:16px;display:inline;vertical-align:middle;"></i> Message sent! I'll get back to you soon.
     </div>
    </form><!-- Social links -->
    <div class="flex justify-center gap-6 mt-10"><a href="#" class="w-10 h-10 flex items-center justify-center rounded-full border border-gray-700 hover:border-blue-400 hover:text-blue-400 transition-all" aria-label="LinkedIn"> <i data-lucide="linkedin" style="width:18px;height:18px;"></i> </a> <a href="#" class="w-10 h-10 flex items-center justify-center rounded-full border border-gray-700 hover:border-blue-400 hover:text-blue-400 transition-all" aria-label="GitHub"> <i data-lucide="github" style="width:18px;height:18px;"></i> </a> <a href="#" class="w-10 h-10 flex items-center justify-center rounded-full border border-gray-700 hover:border-blue-400 hover:text-blue-400 transition-all" aria-label="Email"> <i data-lucide="mail" style="width:18px;height:18px;"></i> </a>
    </div>
   </div>
  </section><!-- FOOTER -->
  <footer class="py-8 px-6 border-t border-gray-800 text-center text-gray-500 text-sm">
   <p>© 2024 <span id="footerName">Your Name</span>. Built with precision.</p>
  </footer>
  <script>
// --- DATA ---
const skills = [
  { name: 'Advanced Excel Formulas', pct: 97, icon: 'function-square' },
  { name: 'Data Cleaning & Analysis', pct: 94, icon: 'filter' },
  { name: 'Dashboard Creation', pct: 92, icon: 'layout-dashboard' },
  { name: 'Charts & Reporting', pct: 90, icon: 'bar-chart-2' },
  { name: 'Spreadsheet Automation', pct: 88, icon: 'zap' }
];

const projects = [
  {
    title: 'Financial Dashboard',
    desc: 'Interactive P&L dashboard with dynamic charts, KPI tracking, and monthly trend analysis for executive reporting.',
    tags: ['Pivot Tables', 'Charts', 'Formulas'],
    color: 'from-blue-600/20 to-blue-900/20',
    icon: 'trending-up',
    mockData: [64, 45, 78, 52, 91, 67, 83]
  },
  {
    title: 'Data Tracking System',
    desc: 'Automated data pipeline that consolidates inputs from multiple sources into a unified tracking sheet with validation.',
    tags: ['Automation', 'Data Validation', 'VBA'],
    color: 'from-cyan-600/20 to-cyan-900/20',
    icon: 'database',
    mockData: [30, 55, 42, 68, 50, 75, 60]
  },
  {
    title: 'Inventory Management',
    desc: 'Real-time inventory tracking with automated reorder alerts, supplier management, and stock level dashboards.',
    tags: ['Conditional Logic', 'Alerts', 'Dashboard'],
    color: 'from-emerald-600/20 to-emerald-900/20',
    icon: 'package',
    mockData: [88, 72, 65, 80, 55, 90, 70]
  },
  {
    title: 'Business Report Templates',
    desc: 'Suite of automated monthly reporting templates with one-click refresh, branded formatting, and PDF export.',
    tags: ['Templates', 'Macros', 'Formatting'],
    color: 'from-purple-600/20 to-purple-900/20',
    icon: 'file-text',
    mockData: [40, 60, 35, 80, 55, 70, 90]
  }
];

const tools = [
  { name: 'Microsoft Excel', level: 'Expert', desc: 'Advanced formulas, VBA, Power Query, Pivot Tables', icon: 'table', pct: 98 },
  { name: 'Google Sheets', level: 'Advanced', desc: 'Apps Script, collaborative workflows, cloud functions', icon: 'cloud', pct: 90 },
  { name: 'Data Visualization', level: 'Proficient', desc: 'Charts, conditional formatting, sparklines, Power BI basics', icon: 'pie-chart', pct: 85 }
];

// --- RENDER SKILLS ---
const skillContainer = document.getElementById('skillBars');
skills.forEach(s => {
  const div = document.createElement('div');
  div.className = 'fade-up';
  div.innerHTML = `
    <div class="flex items-center justify-between mb-2">
      <div class="flex items-center gap-2">
        <i data-lucide="${s.icon}" style="width:16px;height:16px;" class="text-blue-400"></i>
        <span class="text-sm font-medium text-gray-200">${s.name}</span>
      </div>
      <span class="text-xs text-blue-400 font-heading">${s.pct}%</span>
    </div>
    <div class="w-full h-2 bg-gray-800 rounded-full overflow-hidden">
      <div class="skill-fill h-full bg-gradient-to-r from-blue-600 to-cyan-400 rounded-full" style="--target-width:${s.pct}%"></div>
    </div>`;
  skillContainer.appendChild(div);
});

// --- RENDER PROJECTS ---
const projectGrid = document.getElementById('projectGrid');
projects.forEach(p => {
  const card = document.createElement('div');
  card.className = 'fade-up project-card bg-[#0d1225] border border-gray-800 rounded-2xl overflow-hidden';
  const bars = p.mockData.map((v, i) => `<div class="flex-1 flex flex-col justify-end"><div class="bg-gradient-to-t from-blue-500 to-cyan-400 rounded-t-sm opacity-70" style="height:${v}%;transition:height 0.5s ease ${i*0.05}s"></div></div>`).join('');
  card.innerHTML = `
    <div class="h-40 bg-gradient-to-br ${p.color} p-5 relative overflow-hidden">
      <div class="absolute inset-0 grid-bg opacity-30"></div>
      <div class="relative h-full flex items-end gap-1 px-2">${bars}</div>
    </div>
    <div class="p-6">
      <div class="flex items-center gap-2 mb-2">
        <i data-lucide="${p.icon}" style="width:18px;height:18px;" class="text-blue-400"></i>
        <h3 class="font-heading text-base font-bold text-white">${p.title}</h3>
      </div>
      <p class="text-gray-400 text-sm mb-4 leading-relaxed">${p.desc}</p>
      <div class="flex flex-wrap gap-2">${p.tags.map(t => `<span class="text-[11px] px-2.5 py-1 bg-blue-500/10 text-blue-400 rounded-full border border-blue-500/20">${t}</span>`).join('')}</div>
    </div>`;
  projectGrid.appendChild(card);
});

// --- RENDER TOOLS ---
const toolsGridEl = document.getElementById('toolsGrid');
tools.forEach(t => {
  const card = document.createElement('div');
  card.className = 'fade-up bg-[#0a0f1c] border border-gray-800 rounded-2xl p-6 text-center hover:border-blue-500/30 transition-colors';
  card.innerHTML = `
    <div class="w-14 h-14 mx-auto mb-4 rounded-xl bg-blue-600/10 border border-blue-500/20 flex items-center justify-center">
      <i data-lucide="${t.icon}" style="width:24px;height:24px;" class="text-blue-400"></i>
    </div>
    <h3 class="font-heading text-sm font-bold text-white mb-1">${t.name}</h3>
    <span class="text-xs text-blue-400 font-medium">${t.level}</span>
    <p class="text-gray-500 text-xs mt-2 leading-relaxed">${t.desc}</p>
    <div class="mt-4 w-full h-1.5 bg-gray-800 rounded-full overflow-hidden">
      <div class="skill-fill h-full bg-blue-500 rounded-full" style="--target-width:${t.pct}%"></div>
    </div>`;
  toolsGridEl.appendChild(card);
});

// --- FORM ---
document.getElementById('contactForm').addEventListener('submit', function(e) {
  e.preventDefault();
  const success = document.getElementById('formSuccess');
  success.classList.remove('hidden');
  this.reset();
  setTimeout(() => success.classList.add('hidden'), 3000);
});

// --- NAV SCROLL ---
const nav = document.getEl
