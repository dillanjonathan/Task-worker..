<!DOCTYPE html>
<html lang="en" class="dark">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Task Worker | Automated Task Execution Platform</title>
  
  <!-- SEO Meta Tags for Search Engines -->
  <meta name="description" content="Task Worker is an automated task execution platform where users define workflows, prompts, and step-by-step instructions." />
  <meta name="keywords" content="Task Worker, task automation, workflow execution, web scraper, AI summarizer" />

  <!-- Tailwind CSS CDN -->
  <script src="https://cdn.tailwindcss.com"></script>
  <script>
    tailwind.config = {
      darkMode: 'class',
      theme: {
        extend: {
          colors: {
            brand: {
              50: '#f0f9ff',
              100: '#e0f2fe',
              400: '#38bdf8',
              500: '#0284c7',
              600: '#0284c7',
              700: '#0369a1',
              800: '#075985',
              900: '#0c4a6e',
              950: '#082f49',
            },
            accent: {
              cyan: '#06b6d4',
              teal: '#14b8a6',
              blue: '#2563eb'
            }
          },
          fontFamily: {
            mono: ['Fira Code', 'Courier New', 'monospace'],
          }
        }
      }
    }
  </script>
  
  <!-- Lucide Icons -->
  <script src="https://unpkg.com/lucide@latest"></script>

  <style>
    @keyframes pulse-glow {
      0%, 100% { box-shadow: 0 0 15px rgba(6, 182, 212, 0.2); }
      50% { box-shadow: 0 0 25px rgba(6, 182, 212, 0.5); }
    }
    .glow-effect {
      animation: pulse-glow 3s infinite;
    }
    .custom-scrollbar::-webkit-scrollbar {
      width: 6px;
    }
    .custom-scrollbar::-webkit-scrollbar-track {
      background: #0f172a;
    }
    .custom-scrollbar::-webkit-scrollbar-thumb {
      background: #334155;
      border-radius: 3px;
    }
  </style>
</head>
<body class="bg-slate-950 text-slate-100 min-h-screen font-sans antialiased flex flex-col selection:bg-cyan-500 selection:text-slate-950">

  <!-- TOP NAVIGATION BAR -->
  <header class="sticky top-0 z-40 w-full border-b border-slate-800 bg-slate-950/80 backdrop-blur-md">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 h-16 flex items-center justify-between">
      
      <!-- LOGO -->
      <div class="flex items-center gap-3 cursor-pointer" onclick="window.scrollTo({top: 0, behavior: 'smooth'})">
        <div class="relative flex items-center justify-center w-10 h-10 rounded-xl bg-gradient-to-tr from-blue-700 via-cyan-500 to-teal-400 p-[2px] shadow-lg shadow-cyan-500/20">
          <div class="w-full h-full bg-slate-950 rounded-[10px] flex items-center justify-center overflow-hidden">
            <svg class="w-7 h-7 text-cyan-400" viewBox="0 0 100 100" fill="none" xmlns="http://www.w3.org/2000/svg">
              <circle cx="50" cy="50" r="45" stroke="currentColor" stroke-width="4" stroke-dasharray="6 4" class="opacity-40" />
              <!-- Monogram TW -->
              <path d="M 22 32 L 38 72 L 50 42 L 62 72 L 78 32" stroke="currentColor" stroke-width="9" stroke-linecap="round" stroke-linejoin="round" />
              <path d="M 32 32 L 68 32" stroke="currentColor" stroke-width="9" stroke-linecap="round" />
            </svg>
          </div>
        </div>
        <div>
          <span class="text-xl font-extrabold tracking-wider text-white font-mono flex items-center gap-1">
            TASK<span class="text-transparent bg-clip-text bg-gradient-to-r from-cyan-400 to-blue-500">WORKER</span>
          </span>
          <span class="block text-[10px] tracking-widest text-slate-400 font-mono uppercase -mt-1">Automated Execution Platform</span>
        </div>
      </div>

      <!-- NAV LINKS & UPGRADE BUTTON -->
      <div class="flex items-center gap-4">
        <nav class="hidden md:flex items-center gap-6 text-sm font-medium text-slate-400">
          <a href="#builder" class="hover:text-cyan-400 transition-colors">Task Builder</a>
          <a href="#history" class="hover:text-cyan-400 transition-colors">Logs & History</a>
          <a href="#pricing" class="hover:text-cyan-400 transition-colors">Pricing Plan</a>
        </nav>
        
        <button id="upgradeNavBtn" class="relative group overflow-hidden rounded-lg p-[1px] font-semibold text-xs transition-all duration-300 hover:scale-105 cursor-pointer">
          <span class="absolute inset-0 bg-gradient-to-r from-cyan-500 via-blue-500 to-purple-600 rounded-lg pointer-events-none"></span>
          <span class="relative block px-4 py-2 bg-slate-950 rounded-[7px] text-cyan-300 group-hover:bg-opacity-0 group-hover:text-white transition-all flex items-center gap-1.5 font-mono uppercase tracking-wider">
            <i data-lucide="zap" class="w-3.5 h-3.5 text-yellow-400 fill-yellow-400"></i>
            Upgrade to Plus
          </span>
        </button>
      </div>
    </div>
  </header>

  <!-- HERO SECTION -->
  <section class="relative pt-12 pb-16 overflow-hidden border-b border-slate-800/80 bg-gradient-to-b from-slate-950 via-slate-900 to-slate-950">
    <div class="absolute inset-0 bg-[radial-gradient(ellipse_80%_80%_at_50%_-20%,rgba(6,182,212,0.15),rgba(255,255,255,0))] pointer-events-none"></div>
    
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10 text-center">
      <div class="inline-flex items-center gap-2 px-3 py-1.5 rounded-full bg-slate-900 border border-slate-700/80 text-xs text-cyan-400 mb-6 font-mono">
        <span class="flex h-2 w-2 rounded-full bg-cyan-400 animate-ping"></span>
        <span>TW Engine v2.4 Active • Zero-Code Task Automation</span>
      </div>
      
      <h1 class="text-4xl sm:text-6xl font-black text-white tracking-tight mb-6 max-w-4xl mx-auto leading-tight">
        Tell it what to do. <br/>
        <span class="text-transparent bg-clip-text bg-gradient-to-r from-cyan-400 via-blue-500 to-teal-300">
          Task Worker handles the rest.
        </span>
      </h1>
      
      <p class="text-slate-400 text-lg sm:text-xl max-w-2xl mx-auto mb-8 font-light">
        Define your workflow, map your step-by-step instructions, and let our cloud worker execute repetitive web tasks, data extractions, and API workflows automatically.
      </p>

      <!-- PRESET RECIPES SLIDER -->
      <div class="flex flex-wrap items-center justify-center gap-2 text-xs text-slate-400 mb-2 font-mono">
        <span class="text-slate-500">Quick Recipe Shortcuts:</span>
        <button onclick="loadRecipe('scrape')" class="px-3 py-1 rounded-md bg-slate-800 hover:bg-slate-700 border border-slate-700 text-cyan-300 transition-all flex items-center gap-1.5 cursor-pointer">
          <i data-lucide="globe" class="w-3.5 h-3.5"></i> Daily Web Scraper
        </button>
        <button onclick="loadRecipe('ai_summary')" class="px-3 py-1 rounded-md bg-slate-800 hover:bg-slate-700 border border-slate-700 text-cyan-300 transition-all flex items-center gap-1.5 cursor-pointer">
          <i data-lucide="sparkles" class="w-3.5 h-3.5 text-purple-400"></i> AI Article Summarizer
        </button>
        <button onclick="loadRecipe('webhook')" class="px-3 py-1 rounded-md bg-slate-800 hover:bg-slate-700 border border-slate-700 text-cyan-300 transition-all flex items-center gap-1.5 cursor-pointer">
          <i data-lucide="webhook" class="w-3.5 h-3.5 text-teal-400"></i> Discord Webhook Alert
        </button>
      </div>
    </div>
  </section>

  <!-- MAIN APPLICATION WORKSPACE -->
  <main class="flex-grow max-w-7xl w-full mx-auto px-4 sm:px-6 lg:px-8 py-8 space-y-12">
    
    <!-- TASK WORKER BUILDER CARD -->
    <section id="builder" class="scroll-mt-20">
      <div class="bg-slate-900 rounded-2xl border border-slate-800 shadow-2xl overflow-hidden glow-effect">
        
        <!-- WORKSPACE HEADER -->
        <div class="bg-slate-950 px-6 py-4 border-b border-slate-800 flex flex-wrap items-center justify-between gap-4">
          <div class="flex items-center gap-3">
            <div class="w-3 h-3 rounded-full bg-red-500/80"></div>
            <div class="w-3 h-3 rounded-full bg-yellow-500/80"></div>
            <div class="w-3 h-3 rounded-full bg-green-500/80"></div>
            <span class="text-xs font-mono text-slate-400 ml-2 border-l border-slate-800 pl-3">
              task_worker_config.json
            </span>
          </div>

          <div class="flex items-center gap-3 text-xs font-mono">
            <span id="accountBadge" class="px-2.5 py-1 rounded bg-slate-800 text-slate-300 border border-slate-700 flex items-center gap-1.5">
              <span class="w-2 h-2 rounded-full bg-slate-400"></span>
              Tier: Free User
            </span>
            <button id="upgradeTriggerBtn" class="text-cyan-400 hover:underline flex items-center gap-1 font-semibold cursor-pointer">
              <i data-lucide="arrow-up-right" class="w-3.5 h-3.5"></i> Upgrade for Turbo Speed
            </button>
          </div>
        </div>

        <div class="p-6 md:p-8 grid grid-cols-1 lg:grid-cols-12 gap-8">
          
          <!-- LEFT COLUMN: TASK CONFIGURATION FORM -->
          <div class="lg:col-span-7 space-y-6">
            
            <!-- STEP 1: TASK PROMPT / GOAL -->
            <div class="space-y-2">
              <label class="text-xs font-mono uppercase tracking-wider text-cyan-400 font-bold flex items-center gap-2">
                <i data-lucide="target" class="w-4 h-4"></i> 1. Task Objective & Goal
              </label>
              <textarea id="taskPrompt" rows="3" class="w-full bg-slate-950 border border-slate-800 rounded-xl p-3.5 text-sm text-slate-200 placeholder-slate-500 focus:outline-none focus:border-cyan-500 focus:ring-1 focus:ring-cyan-500 transition-all font-sans" placeholder="Describe what Task Worker should do... (e.g. Scrape modern tech news headlines, summarize key points, and post to Discord)"></textarea>
            </div>

            <!-- STEP 2: STEP-BY-STEP INSTRUCTION CONFIGURATOR -->
            <div class="space-y-3">
              <div class="flex items-center justify-between">
                <label class="text-xs font-mono uppercase tracking-wider text-cyan-400 font-bold flex items-center gap-2">
                  <i data-lucide="list-checks" class="w-4 h-4"></i> 2. Execution Instructions
                </label>
                <span id="stepLimitCount" class="text-xs font-mono text-slate-400">
                  Steps: <span id="currentStepCount" class="text-cyan-400 font-bold">2</span> / <span id="maxStepCount">3 (Free)</span>
                </span>
              </div>

              <!-- DYNAMIC STEPS CONTAINER -->
              <div id="stepsContainer" class="space-y-3">
                <!-- STEP ITEM 1 -->
                <div class="step-card bg-slate-950/60 border border-slate-800 rounded-xl p-3.5 flex items-start gap-3 relative group">
                  <span class="w-6 h-6 rounded-lg bg-slate-800 text-cyan-400 text-xs font-mono font-bold flex items-center justify-center shrink-0 mt-1">1</span>
                  <div class="flex-grow space-y-2">
                    <div class="grid grid-cols-1 sm:grid-cols-3 gap-2">
                      <select class="action-type bg-slate-900 border border-slate-700 rounded-lg text-xs text-slate-200 p-2 font-mono focus:border-cyan-500 focus:outline-none cursor-pointer">
                        <option value="SCRAPE">Web Scrape</option>
                        <option value="HTTP">HTTP Request</option>
                        <option value="AI">AI Transform</option>
                        <option value="WEBHOOK">Trigger Webhook</option>
                      </select>
                      <input type="text" class="action-target sm:col-span-2 bg-slate-900 border border-slate-700 rounded-lg text-xs text-slate-200 p-2 focus:border-cyan-500 focus:outline-none" value="https://news.ycombinator.com" placeholder="Target URL / Endpoint" />
                    </div>
                    <input type="text" class="action-desc w-full bg-slate-900/50 border border-slate-800 rounded-lg text-xs text-slate-400 p-2 focus:border-cyan-500 focus:outline-none" value="Extract top 5 trending technology headline titles and links" placeholder="Instruction details" />
                  </div>
                  <button onclick="removeStep(this)" class="text-slate-500 hover:text-red-400 p-1 rounded transition-colors shrink-0 cursor-pointer">
                    <i data-lucide="trash-2" class="w-4 h-4"></i>
                  </button>
                </div>

                <!-- STEP ITEM 2 -->
                <div class="step-card bg-slate-950/60 border border-slate-800 rounded-xl p-3.5 flex items-start gap-3 relative group">
                  <span class="w-6 h-6 rounded-lg bg-slate-800 text-cyan-400 text-xs font-mono font-bold flex items-center justify-center shrink-0 mt-1">2</span>
                  <div class="flex-grow space-y-2">
                    <div class="grid grid-cols-1 sm:grid-cols-3 gap-2">
                      <select class="action-type bg-slate-900 border border-slate-700 rounded-lg text-xs text-slate-200 p-2 font-mono focus:border-cyan-500 focus:outline-none cursor-pointer">
                        <option value="AI" selected>AI Transform</option>
                        <option value="SCRAPE">Web Scrape</option>
                        <option value="HTTP">HTTP Request</option>
                        <option value="WEBHOOK">Trigger Webhook</option>
                      </select>
                      <input type="text" class="action-target sm:col-span-2 bg-slate-900 border border-slate-700 rounded-lg text-xs text-slate-200 p-2 focus:border-cyan-500 focus:outline-none" value="GPT-4o Mini Engine" placeholder="Target Model / Logic" />
                    </div>
                    <input type="text" class="action-desc w-full bg-slate-900/50 border border-slate-800 rounded-lg text-xs text-slate-400 p-2 focus:border-cyan-500 focus:outline-none" value="Synthesize headlines into a 3-bullet executive summary" placeholder="Instruction details" />
                  </div>
                  <button onclick="removeStep(this)" class="text-slate-500 hover:text-red-400 p-1 rounded transition-colors shrink-0 cursor-pointer">
                    <i data-lucide="trash-2" class="w-4 h-4"></i>
                  </button>
                </div>
              </div>

              <!-- ADD STEP BUTTON -->
              <button onclick="addStep()" class="w-full py-2.5 rounded-xl border border-dashed border-slate-700 text-slate-400 hover:text-cyan-300 hover:border-cyan-500/50 hover:bg-slate-950/40 text-xs font-mono flex items-center justify-center gap-2 transition-all cursor-pointer">
                <i data-lucide="plus" class="w-4 h-4"></i> Add Step Instruction
              </button>
            </div>

            <!-- SETTINGS: TRIGGER & PRIORITY -->
            <div class="grid grid-cols-1 sm:grid-cols-2 gap-4 pt-2">
              <div>
                <label class="text-xs font-mono uppercase tracking-wider text-slate-400 mb-1.5 block">Trigger Mode</label>
                <select id="triggerSelect" class="w-full bg-slate-950 border border-slate-800 rounded-xl p-2.5 text-xs text-slate-200 font-mono focus:border-cyan-500 focus:outline-none cursor-pointer">
                  <option value="manual">Manual On-Demand</option>
                  <option value="cron_1h">Schedule: Every Hour</option>
                  <option value="cron_24h">Schedule: Daily at 8 AM</option>
                  <option value="webhook" disabled>Webhook Event (Plus Only 🔒)</option>
                </select>
              </div>

              <div>
                <label class="text-xs font-mono uppercase tracking-wider text-slate-400 mb-1.5 block">Worker Speed</label>
                <div class="bg-slate-950 border border-slate-800 rounded-xl p-2 flex items-center justify-between">
                  <span id="speedLabel" class="text-xs font-mono text-slate-300">Standard (1.0x)</span>
                  <span id="speedBadge" class="text-[10px] font-mono px-2 py-0.5 rounded bg-slate-800 text-slate-400">Normal Queue</span>
                </div>
              </div>
            </div>

            <!-- EXECUTE BUTTON -->
            <button id="runTaskBtn" onclick="runTaskWorker()" class="w-full py-4 rounded-xl bg-gradient-to-r from-cyan-500 via-blue-600 to-teal-400 text-slate-950 font-black text-sm uppercase tracking-wider hover:opacity-95 transition-all shadow-lg shadow-cyan-500/20 flex items-center justify-center gap-2 cursor-pointer">
              <i data-lucide="play" class="w-4 h-4 fill-slate-950"></i> Run Task Worker
            </button>
          </div>

          <!-- RIGHT COLUMN: LIVE WORKER TERMINAL & OUTPUT -->
          <div class="lg:col-span-5 flex flex-col h-full bg-slate-950 border border-slate-800 rounded-xl p-4 font-mono">
            
            <div class="flex items-center justify-between pb-3 border-b border-slate-800 mb-3">
              <div class="flex items-center gap-2 text-xs text-slate-400">
                <i data-lucide="terminal" class="w-4 h-4 text-cyan-400"></i> Live Console Output
              </div>
              <span id="executionTimer" class="text-[10px] text-slate-500">Idle</span>
            </div>

            <!-- PROGRESS BAR -->
            <div class="w-full bg-slate-900 rounded-full h-1.5 mb-3 overflow-hidden">
              <div id="workerProgressBar" class="bg-gradient-to-r from-cyan-400 to-blue-500 h-1.5 w-0 transition-all duration-300"></div>
            </div>

            <!-- CONSOLE LOGS WINDOW -->
            <div id="consoleLogs" class="flex-grow min-h-[220px] max-h-[300px] overflow-y-auto space-y-2 text-xs custom-scrollbar pr-1 text-slate-400">
              <div class="text-slate-600 italic">// Task Worker initialized. Awaiting run signal...</div>
            </div>

            <!-- OUTPUT PAYLOAD DISPLAY -->
            <div class="mt-4 pt-3 border-t border-slate-800 space-y-2">
              <div class="flex items-center justify-between text-[11px] text-slate-400">
                <span>Task Worker Result Payload:</span>
                <button onclick="copyLogs()" class="hover:text-cyan-400 flex items-center gap-1 text-[10px] cursor-pointer">
                  <i data-lucide="copy" class="w-3 h-3"></i> Copy Output
                </button>
              </div>
              <pre id="outputPayload" class="bg-slate-900/90 border border-slate-800 rounded-lg p-3 text-[11px] text-slate-300 overflow-x-auto max-h-32 custom-scrollbar font-mono">
{ "status": "idle", "message": "No active output generated." }</pre>
            </div>

          </div>
        </div>

      </div>
    </section>

    <!-- TASK RUN HISTORY LOGS SECTION -->
    <section id="history" class="space-y-4">
      <div class="flex items-center justify-between">
        <div>
          <h2 class="text-xl font-bold text-white flex items-center gap-2">
            <i data-lucide="history" class="w-5 h-5 text-cyan-400"></i> Execution History & Metrics
          </h2>
          <p class="text-xs text-slate-400">Recent automatic executions by your Task Worker instances</p>
        </div>
        <button onclick="clearHistory()" class="text-xs text-slate-500 hover:text-slate-300 font-mono cursor-pointer">
          Clear Logs
        </button>
      </div>

      <div class="bg-slate-900 border border-slate-800 rounded-xl overflow-hidden shadow-xl">
        <div class="overflow-x-auto">
          <table class="w-full text-left text-xs font-mono">
            <thead class="bg-slate-950 border-b border-slate-800 text-slate-400">
              <tr>
                <th class="p-3.5">Task ID</th>
                <th class="p-3.5">Objective / Prompt</th>
                <th class="p-3.5">Steps</th>
                <th class="p-3.5">Trigger</th>
                <th class="p-3.5">Status</th>
                <th class="p-3.5">Time Saved</th>
                <th class="p-3.5 text-right">Action</th>
              </tr>
            </thead>
            <tbody id="historyTableBody" class="divide-y divide-slate-800/60 text-slate-300">
              <tr>
                <td class="p-3.5 text-slate-500">#TW-8092</td>
                <td class="p-3.5 font-sans font-medium text-slate-200">Scrape HackerNews top 5 technology headlines</td>
                <td class="p-3.5">2 steps</td>
                <td class="p-3.5 text-slate-400">Manual</td>
                <td class="p-3.5"><span class="px-2 py-0.5 rounded bg-emerald-950 text-emerald-400 border border-emerald-800">SUCCESS</span></td>
                <td class="p-3.5 text-cyan-400">~15 mins</td>
                <td class="p-3.5 text-right">
                  <button onclick="reRunTask('#TW-8092')" class="text-cyan-400 hover:underline cursor-pointer">Re-run</button>
                </td>
              </tr>
              <tr>
                <td class="p-3.5 text-slate-500">#TW-8089</td>
                <td class="p-3.5 font-sans font-medium text-slate-200">AI summarize tech trends and format markdown</td>
                <td class="p-3.5">2 steps</td>
                <td class="p-3.5 text-slate-400">Scheduled (1h)</td>
                <td class="p-3.5"><span class="px-2 py-0.5 rounded bg-emerald-950 text-emerald-400 border border-emerald-800">SUCCESS</span></td>
                <td class="p-3.5 text-cyan-400">~22 mins</td>
                <td class="p-3.5 text-right">
                  <button onclick="reRunTask('#TW-8089')" class="text-cyan-400 hover:underline cursor-pointer">Re-run</button>
                </td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
    </section>

    <!-- TASK WORKER PLUS PRICING SECTION -->
    <section id="pricing" class="pt-8 scroll-mt-20">
      <div class="text-center max-w-2xl mx-auto mb-10 space-y-2">
        <span class="text-xs font-mono uppercase tracking-widest text-cyan-400 font-semibold">Upgrade Tier</span>
        <h2 class="text-3xl font-black text-white">Unlock Task Worker Plus</h2>
        <p class="text-slate-400 text-sm">Supercharge your task automation with priority cloud queues, unlimited steps, and instant webhook triggers.</p>
      </div>

      <div class="grid grid-cols-1 md:grid-cols-2 gap-8 max-w-4xl mx-auto">
        
        <!-- FREE TIER CARD -->
        <div class="bg-slate-900/60 border border-slate-800 rounded-2xl p-6 sm:p-8 flex flex-col justify-between">
          <div class="space-y-4">
            <div class="inline-block px-3 py-1 rounded-full bg-slate-800 text-slate-300 text-xs font-mono">
              Free Tier
            </div>
            <div>
              <span class="text-4xl font-black text-white">$0</span>
              <span class="text-slate-500 text-sm">/ forever</span>
            </div>
            <p class="text-xs text-slate-400">Perfect for light automation and personal quick tasks.</p>
            
            <ul class="space-y-2.5 text-xs text-slate-300 pt-4 border-t border-slate-800">
              <li class="flex items-center gap-2">
                <i data-lucide="check" class="w-4 h-4 text-emerald-400"></i> Up to 3 instructions per task
              </li>
              <li class="flex items-center gap-2">
                <i data-lucide="check" class="w-4 h-4 text-emerald-400"></i> Standard queue speed (1.0x)
              </li>
              <li class="flex items-center gap-2">
                <i data-lucide="check" class="w-4 h-4 text-emerald-400"></i> Manual & Hourly triggers
              </li>
              <li class="flex items-center gap-2 text-slate-500 line-through">
                <i data-lucide="x" class="w-4 h-4 text-slate-600"></i> Webhook Event Triggers
              </li>
              <li class="flex items-center gap-2 text-slate-500 line-through">
                <i data-lucide="x" class="w-4 h-4 text-slate-600"></i> Concurrent Parallel Execution
              </li>
            </ul>
          </div>

          <button class="w-full mt-8 py-3 rounded-xl border border-slate-700 text-slate-300 font-semibold text-xs cursor-default bg-slate-950/50">
            Current Active Plan
          </button>
        </div>

        <!-- TASK WORKER PLUS CARD -->
        <div class="bg-gradient-to-b from-slate-900 via-slate-900 to-slate-950 border-2 border-cyan-500/80 rounded-2xl p-6 sm:p-8 flex flex-col justify-between relative shadow-2xl shadow-cyan-500/10">
          <div class="absolute -top-3 right-6 bg-gradient-to-r from-cyan-400 to-blue-500 text-slate-950 font-black text-[10px] uppercase tracking-wider px-3 py-1 rounded-full shadow">
            RECOMMENDED
          </div>

          <div class="space-y-4">
            <div class="inline-flex items-center gap-1.5 px-3 py-1 rounded-full bg-cyan-950/80 border border-cyan-800 text-cyan-300 text-xs font-mono font-semibold">
              <i data-lucide="zap" class="w-3.5 h-3.5 text-yellow-400 fill-yellow-400"></i> Task Worker Plus
            </div>
            <div>
              <span class="text-4xl font-black text-white">$19</span>
              <span class="text-slate-400 text-sm">/ month</span>
            </div>
            <p class="text-xs text-slate-400">For power users who need fast, complex, and high-frequency automated workers.</p>

            <ul class="space-y-2.5 text-xs text-slate-200 pt-4 border-t border-slate-800">
              <li class="flex items-center gap-2">
                <i data-lucide="check-circle" class="w-4 h-4 text-cyan-400"></i> <strong>Unlimited Step Instructions</strong>
              </li>
              <li class="flex items-center gap-2">
                <i data-lucide="check-circle" class="w-4 h-4 text-cyan-400"></i> <strong>Turbo Execution Queue (2.5x Speed)</strong>
              </li>
              <li class="flex items-center gap-2">
                <i data-lucide="check-circle" class="w-4 h-4 text-cyan-400"></i> Instant Webhook & Minute-Cron Triggers
              </li>
              <li class="flex items-center gap-2">
                <i data-lucide="check-circle" class="w-4 h-4 text-cyan-400"></i> Up to 10 Concurrent Parallel Workers
              </li>
              <li class="flex items-center gap-2">
                <i data-lucide="check-circle" class="w-4 h-4 text-cyan-400"></i> Priority Cloud Sandbox & Error Fallbacks
              </li>
            </ul>
          </div>

          <button id="pricingUpgradeBtn" onclick="openUpgradeModal()" class="w-full mt-8 py-3.5 rounded-xl bg-gradient-to-r from-cyan-400 via-blue-500 to-teal-300 text-slate-950 font-black text-xs uppercase tracking-wider hover:opacity-95 transition-all shadow-lg shadow-cyan-500/20 cursor-pointer">
            Upgrade To Plus Now
          </button>
        </div>

      </div>
    </section>

  </main>

  <!-- FOOTER -->
  <footer class="border-t border-slate-800/80 bg-slate-950 py-8 mt-16 text-center text-xs text-slate-500 font-mono">
    <div class="max-w-7xl mx-auto px-4 flex flex-col sm:flex-row items-center justify-between gap-4">
      <div class="flex items-center gap-2">
        <svg class="w-5 h-5 text-cyan-400" viewBox="0 0 100 100" fill="none" xmlns="http://www.w3.org/2000/svg">
          <circle cx="50" cy="50" r="45" stroke="currentColor" stroke-width="4" stroke-dasharray="6 4" class="opacity-40" />
          <path d="M 22 32 L 38 72 L 50 42 L 62 72 L 78 32" stroke="currentColor" stroke-width="9" stroke-linecap="round" stroke-linejoin="round" />
          <path d="M 32 32 L 68 32" stroke="currentColor" stroke-width="9" stroke-linecap="round" />
        </svg>
        <span class="text-slate-300 font-bold">TASK WORKER</span> © 2026. All rights reserved.
      </div>
      <div>
        Automated Task Execution Cloud Engine • Built for Efficiency
      </div>
    </div>
  </footer>

  <!-- UPGRADE MODAL DIALOG -->
  <div id="upgradeModal" class="fixed inset-0 z-50 bg-slate-950/80 backdrop-blur-sm hidden items-center justify-center p-4">
    <div class="bg-slate-900 border border-slate-800 rounded-2xl max-w-md w-full p-6 shadow-2xl relative space-y-6">
      
      <button onclick="closeUpgradeModal()" class="absolute top-4 right-4 text-slate-400 hover:text-white cursor-pointer">
        <i data-lucide="x" class="w-5 h-5"></i>
      </button>

      <div class="text-center space-y-2">
        <div class="inline-flex p-3 rounded-2xl bg-cyan-950/80 border border-cyan-800 text-cyan-400 mb-1">
          <svg class="w-8 h-8" viewBox="0 0 100 100" fill="none" xmlns="http://www.w3.org/2000/svg">
            <circle cx="50" cy="50" r="45" stroke="currentColor" stroke-width="4" stroke-dasharray="6 4" class="opacity-40" />
            <path d="M 22 32 L 38 72 L 50 42 L 62 72 L 78 32" stroke="currentColor" stroke-width="9" stroke-linecap="round" stroke-linejoin="round" />
            <path d="M 32 32 L 68 32" stroke="currentColor" stroke-width="9" stroke-linecap="round" />
          </svg>
        </div>
        <h3 class="text-xl font-black text-white">Upgrade to Task Worker Plus</h3>
        <p class="text-xs text-slate-400">Unlock maximum speed, unlimited instruction steps, and webhook triggers.</p>
      </div>

      <!-- BILLING TOGGLE -->
      <div class="bg-slate-950 p-1 rounded-xl flex items-center justify-between text-xs font-mono border border-slate-800">
        <button id="monthlyToggleBtn" onclick="setBillingCycle('monthly')" class="w-1/2 py-2 rounded-lg bg-slate-800 text-cyan-300 font-bold cursor-pointer">Monthly ($19/mo)</button>
        <button id="annualToggleBtn" onclick="setBillingCycle('annual')" class="w-1/2 py-2 rounded-lg text-slate-400 hover:text-white cursor-pointer">Annual ($15/mo - Save 20%)</button>
      </div>

      <!-- HIGHLIGHTS -->
      <div class="space-y-2 text-xs text-slate-300">
        <div class="flex items-center gap-2">
          <i data-lucide="zap" class="w-4 h-4 text-yellow-400 fill-yellow-400"></i>
          <span>2.5x Faster Execution Queue Turbo-Speed</span>
        </div>
        <div class="flex items-center gap-2">
          <i data-lucide="infinity" class="w-4 h-4 text-cyan-400"></i>
          <span>Unlimited Steps Per Task (Free is limited to 3)</span>
        </div>
        <div class="flex items-center gap-2">
          <i data-lucide="webhook" class="w-4 h-4 text-teal-400"></i>
          <span>Instant Webhooks & API Webhook Trigger access</span>
        </div>
      </div>

      <!-- SIMULATED CHECKOUT BUTTON -->
      <button onclick="processUpgrade()" id="checkoutBtn" class="w-full py-3.5 rounded-xl bg-gradient-to-r from-cyan-400 via-blue-500 to-teal-300 text-slate-950 font-black text-xs uppercase tracking-wider hover:opacity-95 shadow-lg shadow-cyan-500/20 flex items-center justify-center gap-2 cursor-pointer">
        <span>Upgrade Now — <span id="checkoutPrice">$19.00</span></span>
      </button>

      <p class="text-[10px] text-center text-slate-500 font-mono">Cancel anytime. 14-day money back guarantee.</p>
    </div>
  </div>

  <!-- JAVASCRIPT LOGIC -->
  <script>
    // INITIALIZE LUCIDE ICONS
    lucide.createIcons();

    // STATE MANAGEMENT
    let isPlusUser = false;
    let isRunning = false;
    let stepsCount = 2;
    let selectedBilling = 'monthly';

    // DOM ELEMENTS
    const stepsContainer = document.getElementById('stepsContainer');
    const currentStepCountEl = document.getElementById('currentStepCount');
    const maxStepCountEl = document.getElementById('maxStepCount');
    const consoleLogs = document.getElementById('consoleLogs');
    const outputPayload = document.getElementById('outputPayload');
    const progressBar = document.getElementById('workerProgressBar');
    const executionTimer = document.getElementById('executionTimer');
    const accountBadge = document.getElementById('accountBadge');
    const speedLabel = document.getElementById('speedLabel');
    const speedBadge = document.getElementById('speedBadge');
    const triggerSelect = document.getElementById('triggerSelect');

    // UPGRADE MODAL LOGIC
    function openUpgradeModal() {
      if (isPlusUser) return;
      const modal = document.getElementById('upgradeModal');
      modal.classList.remove('hidden');
      modal.classList.add('flex');
    }

    function closeUpgradeModal() {
      const modal = document.getElementById('upgradeModal');
      modal.classList.remove('flex');
      modal.classList.add('hidden');
    }

    document.getElementById('upgradeNavBtn').addEventListener('click', openUpgradeModal);
    document.getElementById('upgradeTriggerBtn').addEventListener('click', openUpgradeModal);

    function setBillingCycle(type) {
      selectedBilling = type;
      const mBtn = document.getElementById('monthlyToggleBtn');
      const aBtn = document.getElementById('annualToggleBtn');
      const priceEl = document.getElementById('checkoutPrice');

      if (type === 'monthly') {
        mBtn.className = "w-1/2 py-2 rounded-lg bg-slate-800 text-cyan-300 font-bold cursor-pointer";
        aBtn.className = "w-1/2 py-2 rounded-lg text-slate-400 hover:text-white cursor-pointer";
        priceEl.innerText = "$19.00 / mo";
      } else {
        aBtn.className = "w-1/2 py-2 rounded-lg bg-slate-800 text-cyan-300 font-bold cursor-pointer";
        mBtn.className = "w-1/2 py-2 rounded-lg text-slate-400 hover:text-white cursor-pointer";
        priceEl.innerText = "$180.00 / yr";
      }
    }

    function processUpgrade() {
      const btn = document.getElementById('checkoutBtn');
      btn.innerHTML = `<i data-lucide="loader-2" class="w-4 h-4 animate-spin"></i> Upgrading Account...`;
      lucide.createIcons();

      setTimeout(() => {
        isPlusUser = true;
        closeUpgradeModal();
        
        accountBadge.className = "px-2.5 py-1 rounded bg-cyan-950 text-cyan-300 border border-cyan-800 flex items-center gap-1.5 font-bold";
        accountBadge.innerHTML = `<span class="w-2 h-2 rounded-full bg-cyan-400 animate-pulse"></span> Tier: Task Worker PLUS`;
        
        maxStepCountEl.innerText = "Unlimited (Plus)";
        speedLabel.innerText = "Turbo High-Speed (2.5x)";
        speedBadge.innerText = "Priority Queue";
        speedBadge.className = "text-[10px] font-mono px-2 py-0.5 rounded bg-cyan-950 text-cyan-300 border border-cyan-800 font-bold";

        const navBtn = document.getElementById('upgradeNavBtn');
        navBtn.innerHTML = `<span class="relative block px-4 py-2 bg-cyan-950 text-cyan-300 rounded-[7px] font-mono uppercase tracking-wider flex items-center gap-1.5 font-bold border border-cyan-800"><i data-lucide="check" class="w-3.5 h-3.5"></i> Plus Active</span>`;
        navBtn.onclick = null;
        
        const triggerBtn = document.getElementById('upgradeTriggerBtn');
        if (triggerBtn) triggerBtn.style.display = 'none';

        const pricingBtn = document.getElementById('pricingUpgradeBtn');
        pricingBtn.className = "w-full mt-8 py-3.5 rounded-xl bg-cyan-950/80 border border-cyan-800 text-cyan-300 font-bold text-xs uppercase tracking-wider cursor-default flex items-center justify-center gap-2";
        pricingBtn.innerHTML = `<i data-lucide="check-circle" class="w-4 h-4 text-cyan-400"></i> Current Active Plan`;
        pricingBtn.onclick = null;

        const webhookOption = triggerSelect.querySelector('option[value="webhook"]');
        if (webhookOption) {
          webhookOption.disabled = false;
          webhookOption.innerText = "Webhook Event (Active)";
        }

        lucide.createIcons();
        alert("🎉 Congratulations! You have upgraded to Task Worker Plus. You now have access to Turbo Queue Speed & Unlimited Task Steps.");
      }, 1200);
    }

    // STEP MANAGEMENT
    function updateStepNumbers() {
      const stepCards = stepsContainer.querySelectorAll('.step-card');
      stepsCount = stepCards.length;
      currentStepCountEl.innerText = stepsCount;

      stepCards.forEach((card, index) => {
        const badge = card.querySelector('span');
        if (badge) badge.innerText = index + 1;
      });
    }

    function addStep(type = "HTTP", target = "", desc = "") {
      if (!isPlusUser && stepsCount >= 3) {
        openUpgradeModal();
        return;
      }

      const stepDiv = document.createElement('div');
      stepDiv.className = "step-card bg-slate-950/60 border border-slate-800 rounded-xl p-3.5 flex items-start gap-3 relative group";
      stepDiv.innerHTML = `
        <span class="w-6 h-6 rounded-lg bg-slate-800 text-cyan-400 text-xs font-mono font-bold flex items-center justify-center shrink-0 mt-1">${stepsCount + 1}</span>
        <div class="flex-grow space-y-2">
          <div class="grid grid-cols-1 sm:grid-cols-3 gap-2">
            <select class="action-type bg-slate-900 border border-slate-700 rounded-lg text-xs text-slate-200 p-2 font-mono focus:border-cyan-500 focus:outline-none cursor-pointer">
              <option value="SCRAPE" ${type === 'SCRAPE' ? 'selected' : ''}>Web Scrape</option>
              <option value="HTTP" ${type === 'HTTP' ? 'selected' : ''}>HTTP Request</option>
              <option value="AI" ${type === 'AI' ? 'selected' : ''}>AI Transform</option>
              <option value="WEBHOOK" ${type === 'WEBHOOK' ? 'selected' : ''}>Trigger Webhook</option>
            </select>
            <input type="text" class="action-target sm:col-span-2 bg-slate-900 border border-slate-700 rounded-lg text-xs text-slate-200 p-2 focus:border-cyan-500 focus:outline-none" value="${target}" placeholder="Target URL / Endpoint" />
          </div>
          <input type="text" class="action-desc w-full bg-slate-900/50 border border-slate-800 rounded-lg text-xs text-slate-400 p-2 focus:border-cyan-500 focus:outline-none" value="${desc}" placeholder="Instruction details" />
        </div>
        <button onclick="removeStep(this)" class="text-slate-500 hover:text-red-400 p-1 rounded transition-colors shrink-0 cursor-pointer">
          <i data-lucide="trash-2" class="w-4 h-4"></i>
        </button>
      `;

      stepsContainer.appendChild(stepDiv);
      updateStepNumbers();
      lucide.createIcons();
    }

    function removeStep(btn) {
      if (stepsContainer.querySelectorAll('.step-card').length <= 1) {
        alert("A Task Worker must have at least 1 step instruction.");
        return;
      }
      btn.closest('.step-card').remove();
      updateStepNumbers();
    }

    // RECIPE PRESETS
    function loadRecipe(type) {
      stepsContainer.innerHTML = '';
      const promptInput = document.getElementById('taskPrompt');

      if (type === 'scrape') {
        promptInput.value = "Scrape trending news headlines from HackerNews and log output.";
        addStep('SCRAPE', 'https://news.ycombinator.com', 'Extract article titles and link URLs');
        addStep('HTTP', 'https://api.taskworker.internal/store', 'Save structured news items to storage DB');
      } else if (type === 'ai_summary') {
        promptInput.value = "Read recent updates, produce a brief executive summary using AI, and return formatted Markdown.";
        addStep('SCRAPE', 'https://techcrunch.com', 'Get main article body');
        addStep('AI', 'GPT-4o Mini Engine', 'Summarize content into 3 concise bullet points');
      } else if (type === 'webhook') {
        promptInput.value = "Check system operational status and send instant alert payload to Discord.";
        addStep('HTTP', 'https://status.github.com/api/v2/status.json', 'Fetch current system health');
        addStep('WEBHOOK', 'https://discord.com/api/webhooks/xyz', 'Post status notification payload');
      }
    }

    // SIMULATED TASK EXECUTION
    function appendLog(message, type = "info") {
      const time = new Date().toLocaleTimeString();
      const div = document.createElement('div');
      
      let colorClass = "text-slate-300";
      if (type === "success") colorClass = "text-emerald-400 font-semibold";
      if (type === "debug") colorClass = "text-cyan-400";
      if (type === "warn") colorClass = "text-yellow-400";

      div.className = `${colorClass} leading-relaxed`;
      div.innerHTML = `<span class="text-slate-600">[${time}]</span> ${message}`;
      consoleLogs.appendChild(div);
      consoleLogs.scrollTop = consoleLogs.scrollHeight;
    }

    function runTaskWorker() {
      if (isRunning) return;
      isRunning = true;

      const runBtn = document.getElementById('runTaskBtn');
      runBtn.disabled = true;
      runBtn.classList.add('opacity-50');
      runBtn.innerHTML = `<i data-lucide="loader-2" class="w-4 h-4 animate-spin"></i> Task Worker Executing...`;
      lucide.createIcons();

      consoleLogs.innerHTML = '';
      outputPayload.innerText = '{\n  "status": "processing"\n}';
      progressBar.style.width = '10%';
      executionTimer.innerText = 'Running...';

      const delayMultiplier = isPlusUser ? 0.4 : 1.0;

      appendLog("Task Worker worker_node_01 spawned", "debug");
      appendLog("Parsing instructions payload...");

      setTimeout(() => {
        progressBar.style.width = '40%';
        appendLog("Step 1 Executing: Fetching target endpoint data...", "info");
      }, 700 * delayMultiplier);

      setTimeout(() => {
        progressBar.style.width = '70%';
        appendLog("Step 2 Executing: Processing transformations...", "info");
      }, 1500 * delayMultiplier);

      setTimeout(() => {
        progressBar.style.width = '100%';
        appendLog("All instructions completed successfully!", "success");
        executionTimer.innerText = isPlusUser ? 'Completed in 0.4s (Turbo)' : 'Completed in 1.2s';

        const result = {
          task_id: "TW-" + Math.floor(1000 + Math.random() * 9000),
          status: "SUCCESS",
          execution_speed: isPlusUser ? "Turbo (2.5x)" : "Standard (1.0x)",
          timestamp: new Date().toISOString(),
          extracted_items: [
            { title: "AI Automation Tools in 2026", link: "https://example.com/ai" },
            { title: "Task Worker Engine Release Notes", link: "https://example.com/tw" }
          ]
        };

        outputPayload.innerText = JSON.stringify(result, null, 2);
        addHistoryRow(result.task_id, document.getElementById('taskPrompt').value || "Custom Task Execution");

        runBtn.disabled = false;
        runBtn.classList.remove('opacity-50');
        runBtn.innerHTML = `<i data-lucide="play" class="w-4 h-4 fill-slate-950"></i> Run Task Worker`;
        lucide.createIcons();
        isRunning = false;

      }, 2300 * delayMultiplier);
    }

    function addHistoryRow(id, prompt) {
      const tbody = document.getElementById('historyTableBody');
      const tr = document.createElement('tr');
      tr.innerHTML = `
        <td class="p-3.5 text-slate-500">#${id}</td>
        <td class="p-3.5 font-sans font-medium text-slate-200">${prompt}</td>
        <td class="p-3.5">${stepsCount} steps</td>
        <td class="p-3.5 text-slate-400">Manual</td>
        <td class="p-3.5"><span class="px-2 py-0.5 rounded bg-emerald-950 text-emerald-400 border border-emerald-800">SUCCESS</span></td>
        <td class="p-3.5 text-cyan-400">~${Math.floor(Math.random() * 20 + 5)} mins</td>
        <td class="p-3.5 text-right">
          <button onclick="reRunTask('${id}')" class="text-cyan-400 hover:underline cursor-pointer">Re-run</button>
        </td>
      `;
      tbody.prepend(tr);
    }

    function reRunTask(id) {
      window.scrollTo({ top: document.getElementById('builder').offsetTop - 80, behavior: 'smooth' });
      runTaskWorker();
    }

    function clearHistory() {
      document.getElementById('historyTableBody').innerHTML = '<tr><td colspan="7" class="p-4 text-center text-slate-500">History cleared.</td></tr>';
    }

    function copyLogs() {
      navigator.clipboard.writeText(outputPayload.innerText);
      alert("Payload copied to clipboard!");
    }
  </script>
</body>
</html>
