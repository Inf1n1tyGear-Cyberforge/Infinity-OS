# Infinity-OS
Infinity OS is a platform-agnostic, modular command framework that unifies real-time telemetry, biometric synchronization, and AI-driven control across diverse exoskeleton architectures, providing a standardized, high-performance tactical dashboard for seamless human-machine integration and operator safety in complex robotic environments.




THIS IS THE HTML CODE 



<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>System Interface Portal</title>
  <script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;700&family=Plus+Jakarta+Sans:wght@400;600;800&display=swap" rel="stylesheet">
  
  <style>
    body {
      font-family: 'Plus Jakarta Sans', sans-serif;
    }
    .font-mono-tech {
      font-family: 'JetBrains Mono', monospace;
    }
    /* Smooth transition framework for interactive components */
    .smooth-transition {
      transition: all 0.2s cubic-bezier(0.4, 0, 0.2, 1);
    }
  </style>
</head>
<body class="bg-slate-950 text-slate-100 h-screen w-screen overflow-hidden select-none">

  <section id="module-auth" class="flex flex-col items-center justify-center h-full w-full px-4">
    <div class="bg-slate-900 border border-slate-800 p-8 rounded-2xl max-w-md w-full shadow-2xl">
      
      <div class="text-center mb-6">
        <h1 class="text-xl font-extrabold tracking-tight text-white">System Access Gateway</h1>
        <p class="text-xs text-slate-400 mt-1">Provide operator parameters to initialize link layers</p>
      </div>
      
      <div class="space-y-4">
        <div>
          <label class="text-xs font-semibold text-slate-300 block mb-1.5">Operator Identification Key</label>
          <input type="text" id="input-username" value="OPERATOR_DEFAULT_NODE" class="w-full px-4 py-3 bg-slate-950 rounded-xl border border-slate-700 text-slate-200 text-sm focus:outline-none focus:border-blue-500 font-mono-tech smooth-transition">
        </div>
        
        <div>
          <label class="text-xs font-semibold text-slate-300 block mb-1.5">Security Credentials</label>
          <input type="password" id="input-password" value="system_secure_pass" class="w-full px-4 py-3 bg-slate-950 rounded-xl border border-slate-700 text-slate-200 text-sm focus:outline-none focus:border-blue-500 smooth-transition">
        </div>

        <button onclick="handleLoginRoute()" class="w-full bg-blue-600 hover:bg-blue-500 text-white font-bold text-sm py-3.5 rounded-xl mt-2 smooth-transition shadow-lg shadow-blue-900/20 active:scale-[0.98] cursor-pointer">
          Verify System Authentication
        </button>
      </div>
    </div>
  </section>


  <section id="module-pin" class="flex flex-col items-center justify-center h-full w-full px-4" style="display: none;">
    <div class="bg-slate-900 border border-slate-800 p-8 rounded-2xl max-w-xs w-full text-center shadow-2xl">
      
      <div class="mb-4">
        <h2 class="text-base font-bold text-white">Pipeline Authorization</h2>
        <p class="text-[11px] text-slate-400 mt-0.5">Input system authorization PIN passcode</p>
      </div>
      
      <div id="pin-secure-mask" class="text-2xl font-bold py-3.5 mb-5 bg-slate-950 rounded-xl border border-slate-800 text-blue-400 tracking-widest font-mono-tech shadow-inner">
        _ _ _ _
      </div>
      
      <div class="grid grid-cols-3 gap-2 max-w-[220px] mx-auto font-mono-tech">
        <button onclick="appendPinDigit('1')" class="bg-slate-800 text-slate-200 p-3.5 rounded-xl font-bold text-lg hover:bg-slate-700 active:bg-slate-600 smooth-transition cursor-pointer">1</button>
        <button onclick="appendPinDigit('2')" class="bg-slate-800 text-slate-200 p-3.5 rounded-xl font-bold text-lg hover:bg-slate-700 active:bg-slate-600 smooth-transition cursor-pointer">2</button>
        <button onclick="appendPinDigit('3')" class="bg-slate-800 text-slate-200 p-3.5 rounded-xl font-bold text-lg hover:bg-slate-700 active:bg-slate-600 smooth-transition cursor-pointer">3</button>
        <button onclick="appendPinDigit('4')" class="bg-slate-800 text-slate-200 p-3.5 rounded-xl font-bold text-lg hover:bg-slate-700 active:bg-slate-600 smooth-transition cursor-pointer">4</button>
        <button onclick="appendPinDigit('5')" class="bg-slate-800 text-slate-200 p-3.5 rounded-xl font-bold text-lg hover:bg-slate-700 active:bg-slate-600 smooth-transition cursor-pointer">5</button>
        <button onclick="appendPinDigit('6')" class="bg-slate-800 text-slate-200 p-3.5 rounded-xl font-bold text-lg hover:bg-slate-700 active:bg-slate-600 smooth-transition cursor-pointer">6</button>
        <button onclick="appendPinDigit('7')" class="bg-slate-800 text-slate-200 p-3.5 rounded-xl font-bold text-lg hover:bg-slate-700 active:bg-slate-600 smooth-transition cursor-pointer">7</button>
        <button onclick="appendPinDigit('8')" class="bg-slate-800 text-slate-200 p-3.5 rounded-xl font-bold text-lg hover:bg-slate-700 active:bg-slate-600 smooth-transition cursor-pointer">8</button>
        <button onclick="appendPinDigit('9')" class="bg-slate-800 text-slate-200 p-3.5 rounded-xl font-bold text-lg hover:bg-slate-700 active:bg-slate-600 smooth-transition cursor-pointer">9</button>
        <button onclick="resetPinInput()" class="bg-slate-950 text-rose-400 p-3.5 rounded-xl font-bold text-xs hover:bg-rose-950/40 smooth-transition cursor-pointer">CLR</button>
        <button onclick="appendPinDigit('0')" class="bg-slate-800 text-slate-200 p-3.5 rounded-xl font-bold text-lg hover:bg-slate-700 active:bg-slate-600 smooth-transition cursor-pointer">0</button>
        <button onclick="popPinDigit()" class="bg-slate-950 text-slate-400 p-3.5 rounded-xl font-bold text-lg hover:bg-slate-800 smooth-transition cursor-pointer">⌫</button>
      </div>
      <p class="text-[10px] text-slate-500 font-mono-tech mt-5">DEFAULT HANDSHAKE PIN: 1234</p>
    </div>
  </section>


  <section id="module-dashboard" class="h-full w-full flex flex-col p-4 bg-slate-950" style="display: none;">
    
    <header class="flex justify-between items-center border-b border-slate-800 pb-3 mb-4">
      <div class="flex items-center gap-2.5">
        <span class="text-white font-extrabold text-lg tracking-tight">Console Monitor</span>
        <span class="text-[10px] bg-slate-900 border border-slate-800 text-slate-400 px-2 py-0.5 rounded-md font-mono-tech">v2.1.0-PRO</span>
      </div>
      
      <div class="flex items-center gap-4 bg-slate-900 border border-slate-800 px-3 py-1.5 rounded-xl">
        <div class="flex items-center gap-2">
          <span class="w-2 h-2 bg-emerald-500 rounded-full"></span>
          <span class="text-xs font-semibold text-emerald-400 font-mono-tech">PIPELINE_CONNECTED</span>
        </div>
        <button onclick="location.reload()" class="text-xs text-slate-400 hover:text-rose-400 font-semibold pl-2 border-l border-slate-800 smooth-transition cursor-pointer">Exit Session</button>
      </div>
    </header>

    <div class="grid grid-cols-12 gap-4 flex-1 overflow-hidden">
      
      <nav class="col-span-3 bg-slate-900 border border-slate-800 rounded-xl p-3 flex flex-col justify-between">
        <div class="space-y-1">
          <span class="text-[10px] uppercase font-bold tracking-wider text-slate-500 px-2 block mb-2 font-mono-tech">Console Viewports</span>
          
          <button id="tab-control-telemetry" onclick="renderSubTabViewport('view-telemetry')" class="w-full flex items-center justify-between px-3 py-2.5 rounded-lg bg-blue-600/10 text-blue-400 border border-blue-500/20 text-xs font-bold tracking-wide smooth-transition cursor-pointer">
            <span>📈 Diagnostics Board</span>
          </button>
          <button id="tab-control-streams" onclick="renderSubTabViewport('view-streams')" class="w-full flex items-center justify-between px-3 py-2.5 rounded-lg text-slate-400 hover:bg-slate-800 hover:text-slate-200 text-xs font-bold tracking-wide smooth-transition cursor-pointer">
            <span>🔌 Pipeline Controls</span>
          </button>
        </div>

        <div class="bg-slate-950 p-3 rounded-lg border border-slate-800 text-[11px] font-mono-tech text-slate-500 space-y-1">
          <div>SOCKET CHANNEL: <span class="text-emerald-400 font-bold">READY</span></div>
          <div>REMOTE HOST: <span class="text-slate-400">LOCAL_LOOPBACK</span></div>
        </div>
      </nav>

      <main class="col-span-9 h-full relative">

        <div id="subtab-view-telemetry" class="h-full grid grid-cols-2 gap-4">
          <div class="bg-slate-900 border border-slate-800 rounded-xl p-4 flex flex-col justify-between">
            <div class="border-b border-slate-800 pb-2 flex justify-between items-center">
              <span class="text-xs font-bold text-slate-400">Kinematic Structural Layout</span>
              <span class="text-[10px] bg-blue-500/10 text-blue-400 px-2 py-0.5 rounded font-mono-tech">Static Axis</span>
            </div>
            
            <div class="my-auto flex justify-center py-4">
              <svg viewBox="0 0 100 120" class="w-36 h-auto text-blue-500" fill="none" stroke="currentColor" stroke-width="2">
                <line x1="50" y1="20" x2="50" y2="80" stroke-dasharray="2,2" stroke-width="1"/>
                <line x1="50" y1="40" x2="20" y2="70" />
                <line x1="50" y1="40" x2="80" y2="70" />
                <line x1="50" y1="80" x2="35" y2="110" />
                <line x1="50" y1="80" x2="65" y2="110" />
                <circle cx="50" cy="20" r="4" fill="#3b82f6" />
                <circle cx="50" cy="40" r="3.5" fill="#3b82f6" />
                <circle cx="20" cy="70" r="3.5" fill="#3b82f6" />
                <circle cx="80" cy="70" r="3.5" fill="#3b82f6" />
              </svg>
            </div>

            <div class="border-t border-slate-800/60 pt-2 text-[10px] text-slate-500 flex justify-between font-mono-tech">
              <span>CANVAS HOVER MAP</span>
              <span class="text-emerald-500 font-bold">STABLE INTEGRITY</span>
            </div>
          </div>

          <div class="flex flex-col gap-4">
            <div class="flex-1 bg-slate-900 border border-slate-800 rounded-xl p-4 flex flex-col justify-between">
              <span class="text-xs font-bold text-slate-400">Mechanical Strain Load</span>
              <div class="my-2">
                <div id="runtime-strain-val" class="text-4xl font-extrabold text-white font-mono-tech">0.00<span class="text-base text-slate-500 ml-0.5">%</span></div>
              </div>
              <p class="text-xs text-slate-500 leading-normal">Main monitoring parameter reporting structural mechanical load values across internal matrix channels.</p>
            </div>

            <div class="flex-1 bg-slate-900 border border-slate-800 rounded-xl p-4 flex flex-col justify-between">
              <span class="text-xs font-bold text-slate-400">Interface Pulse Velocity</span>
              <div class="my-2">
                <div id="runtime-pulse-val" class="text-4xl font-extrabold text-white font-mono-tech">-- <span class="text-base text-slate-500 ml-0.5">HZ</span></div>
              </div>
              <p class="text-xs text-slate-500 leading-normal">Aggregated frame update calculations sampling active internal channel routing pipeline updates.</p>
            </div>
          </div>
        </div>

        <div id="subtab-view-streams" class="h-full bg-slate-900 border border-slate-800 rounded-xl p-5 flex flex-col justify-between" style="display: none;">
          <div class="space-y-4">
            <div class="border-b border-slate-800 pb-3">
              <h3 class="text-sm font-bold text-white">Pipeline Execution Center</h3>
              <p class="text-xs text-slate-400 mt-0.5">Manage live automated array deployment configurations and system stream logs.</p>
            </div>
            
            <div class="space-y-4 max-w-md">
              <div>
                <label class="text-xs font-semibold text-slate-300 block mb-1.5">Compilation Endpoint Vector URL</label>
                <input type="text" value="ws://127.0.0.1:8080/stream/pipeline" class="w-full bg-slate-950 p-2.5 rounded-lg border border-slate-800 text-xs text-blue-400 font-mono-tech focus:outline-none" readonly>
              </div>
              
              <div>
                <label class="text-xs font-semibold text-slate-300 block mb-1.5">Runtime Architecture Package Target</label>
                <select class="w-full bg-slate-950 p-2.5 rounded-lg border border-slate-800 text-xs text-slate-300 focus:outline-none">
                  <option>Core Standard UI Matrix Assembly Bundle</option>
                </select>
              </div>
            </div>
          </div>

          <div class="pt-4 border-t border-slate-800">
            <button id="stream-action-btn" onclick="toggleLocalStreamInstance()" class="bg-blue-600 hover:bg-blue-500 text-white font-bold text-xs py-3 px-5 rounded-lg smooth-transition cursor-pointer shadow-md shadow-blue-900/10 uppercase tracking-wider">
              Initialize Data Streaming
            </button>
            <div id="console-stream-logger" class="mt-4 bg-slate-950 p-3 rounded-lg border border-slate-800 text-[11px] text-slate-500 font-mono-tech h-24 overflow-y-auto">
              [SYSTEM] Interface layer diagnostic subsystem idle. Awaiting user link...
            </div>
          </div>
        </div>

      </main>
    </div>
  </section>


  <script>
    let currentAuthPin = "";
    const SystemAccessPin = "1234";
    let activeStreamStatus = false;
    let metricLoopInterval;

    // --- GATEWAY LOGIN SCREEN ROUTING CONTROL ---
    function handleLoginRoute() {
      const userField = document.getElementById('input-username').value;
      if (userField.trim() !== "") {
        document.getElementById('module-auth').style.display = 'none';
        document.getElementById('module-pin').style.display = 'flex';
      }
    }

    // --- TACTILE PIN HANDLING ARCHITECTURE ---
    function appendPinDigit(digit) {
      if (currentAuthPin.length < 4) {
        currentAuthPin += digit;
        refreshPinLayoutDisplay();
      }
      if (currentAuthPin.length === 4) {
        setTimeout(verifySystemPinHandshake, 250);
      }
    }

    function refreshPinLayoutDisplay() {
      let activeDots = currentAuthPin.split("").map(() => "●").join(" ");
      let openSlots = Array(4 - currentAuthPin.length).fill("_").join(" ");
      document.getElementById('pin-secure-mask').innerText = (activeDots + " " + openSlots).trim();
    }

    function resetPinInput() {
      currentAuthPin = "";
      refreshPinLayoutDisplay();
    }

    function popPinDigit() {
      currentAuthPin = currentAuthPin.slice(0, -1);
      refreshPinLayoutDisplay();
    }

    function verifySystemPinHandshake() {
      if (currentAuthPin === SystemAccessPin) {
        document.getElementById('module-pin').style.display = 'none';
        document.getElementById('module-dashboard').style.display = 'flex';
      } else {
        alert("ACCESS DENIED: Internal link configuration authentication failure.");
        resetPinInput();
      }
    }

    // --- DASHBOARD INNER SIDEBAR VIEWPORT SWITCHING ---
    function renderSubTabViewport(selectedViewId) {
      const subviews = ['view-telemetry', 'view-streams'];
      subviews.forEach(view => {
        document.getElementById(`subtab-${view}`).style.display = 'none';
      });
      
      // Target specific container layouts structurally
      if (selectedViewId === 'view-telemetry') {
        document.getElementById(`subtab-${selectedViewId}`).style.display = 'grid';
      } else {
        document.getElementById(`subtab-${selectedViewId}`).style.display = 'flex';
      }

      // Update button aesthetic state changes
      const interfaceTabs = { 'view-telemetry': 'telemetry', 'view-streams': 'streams' };
      Object.keys(interfaceTabs).forEach(key => {
        let actionButton = document.getElementById(`tab-control-${interfaceTabs[key]}`);
        if(key === selectedViewId) {
          actionButton.className = "w-full flex items-center justify-between px-3 py-2.5 rounded-lg bg-blue-600/10 text-blue-400 border border-blue-500/20 text-xs font-bold tracking-wide smooth-transition cursor-pointer";
        } else {
          actionButton.className = "w-full flex items-center justify-between px-3 py-2.5 rounded-lg text-slate-400 hover:bg-slate-800 hover:text-slate-200 text-xs font-bold tracking-wide smooth-transition cursor-pointer";
        }
      });
    }

    // --- PIPELINE LOG STREAM SIMULATION MOTOR ---
    function toggleLocalStreamInstance() {
      const logContainer = document.getElementById('console-stream-logger');
      const systemBtn = document.getElementById('stream-action-btn');

      if (!activeStreamStatus) {
        activeStreamStatus = true;
        systemBtn.innerText = "Terminate Active Stream";
        systemBtn.className = "bg-rose-600 hover:bg-rose-500 text-white font-bold text-xs py-3 px-5 rounded-lg smooth-transition cursor-pointer shadow-md shadow-rose-900/10 uppercase tracking-wider";
        
        let timeStampStr = new Date().toLocaleTimeString();
        logContainer.innerHTML += `<div class="text-emerald-400 mt-1">[${timeStampStr}] [SOCKET] Channel pipeline handshake established. Telemetry mounting...</div>`;
        logContainer.scrollTop = logContainer.scrollHeight;

        fireMockTelemetryInterval();
      } else {
        activeStreamStatus = false;
        systemBtn.innerText = "Initialize Data Streaming";
        systemBtn.className = "bg-blue-600 hover:bg-blue-500 text-white font-bold text-xs py-3 px-5 rounded-lg smooth-transition cursor-pointer shadow-md shadow-blue-900/10 uppercase tracking-wider";
        
        logContainer.innerHTML += `<div class="text-rose-400 mt-1">[SYSTEM] Pipeline session sequence manually interrupted by operator.</div>`;
        logContainer.scrollTop = logContainer.scrollHeight;
        
        clearMockTelemetryInterval();
      }
    }

    function fireMockTelemetryInterval() {
      metricLoopInterval = setInterval(() => {
        let randomizedStrain = (Math.random() * 8 + 22).toFixed(2);
        document.getElementById('runtime-strain-val').innerHTML = `${randomizedStrain}<span class="text-base text-slate-500 ml-0.5">%</span>`;
        
        let randomizedPulse = Math.floor(Math.random() * 12 + 58);
        document.getElementById('runtime-pulse-val').innerHTML = `${randomizedPulse}<span class="text-base text-slate-500 ml-0.5">HZ</span>`;
      }, 400);
    }

    function clearMockTelemetryInterval() {
      clearInterval(metricLoopInterval);
      document.getElementById('runtime-strain-val').innerHTML = `0.00<span class="text-base text-slate-500 ml-0.5">%</span>`;
      document.getElementById('runtime-pulse-val').innerHTML = `-- <span class="text-base text-slate-500 ml-0.5">HZ</span>`;
    }
  </script>
</body>
</html>




THIS IS THE CSS CODE 



<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>System Interface Portal</title>
  <script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;700&family=Plus+Jakarta+Sans:wght@400;600;800&display=swap" rel="stylesheet">
  
  <style>
    body {
      font-family: 'Plus Jakarta Sans', sans-serif;
    }
    .font-mono-tech {
      font-family: 'JetBrains Mono', monospace;
    }
    /* Smooth transition framework for interactive components */
    .smooth-transition {
      transition: all 0.2s cubic-bezier(0.4, 0, 0.2, 1);
    }
  </style>
</head>
<body class="bg-slate-950 text-slate-100 h-screen w-screen overflow-hidden select-none">

  <section id="module-auth" class="flex flex-col items-center justify-center h-full w-full px-4">
    <div class="bg-slate-900 border border-slate-800 p-8 rounded-2xl max-w-md w-full shadow-2xl">
      
      <div class="text-center mb-6">
        <h1 class="text-xl font-extrabold tracking-tight text-white">System Access Gateway</h1>
        <p class="text-xs text-slate-400 mt-1">Provide operator parameters to initialize link layers</p>
      </div>
      
      <div class="space-y-4">
        <div>
          <label class="text-xs font-semibold text-slate-300 block mb-1.5">Operator Identification Key</label>
          <input type="text" id="input-username" value="OPERATOR_DEFAULT_NODE" class="w-full px-4 py-3 bg-slate-950 rounded-xl border border-slate-700 text-slate-200 text-sm focus:outline-none focus:border-blue-500 font-mono-tech smooth-transition">
        </div>
        
        <div>
          <label class="text-xs font-semibold text-slate-300 block mb-1.5">Security Credentials</label>
          <input type="password" id="input-password" value="system_secure_pass" class="w-full px-4 py-3 bg-slate-950 rounded-xl border border-slate-700 text-slate-200 text-sm focus:outline-none focus:border-blue-500 smooth-transition">
        </div>

        <button onclick="handleLoginRoute()" class="w-full bg-blue-600 hover:bg-blue-500 text-white font-bold text-sm py-3.5 rounded-xl mt-2 smooth-transition shadow-lg shadow-blue-900/20 active:scale-[0.98] cursor-pointer">
          Verify System Authentication
        </button>
      </div>
    </div>
  </section>


  <section id="module-pin" class="flex flex-col items-center justify-center h-full w-full px-4" style="display: none;">
    <div class="bg-slate-900 border border-slate-800 p-8 rounded-2xl max-w-xs w-full text-center shadow-2xl">
      
      <div class="mb-4">
        <h2 class="text-base font-bold text-white">Pipeline Authorization</h2>
        <p class="text-[11px] text-slate-400 mt-0.5">Input system authorization PIN passcode</p>
      </div>
      
      <div id="pin-secure-mask" class="text-2xl font-bold py-3.5 mb-5 bg-slate-950 rounded-xl border border-slate-800 text-blue-400 tracking-widest font-mono-tech shadow-inner">
        _ _ _ _
      </div>
      
      <div class="grid grid-cols-3 gap-2 max-w-[220px] mx-auto font-mono-tech">
        <button onclick="appendPinDigit('1')" class="bg-slate-800 text-slate-200 p-3.5 rounded-xl font-bold text-lg hover:bg-slate-700 active:bg-slate-600 smooth-transition cursor-pointer">1</button>
        <button onclick="appendPinDigit('2')" class="bg-slate-800 text-slate-200 p-3.5 rounded-xl font-bold text-lg hover:bg-slate-700 active:bg-slate-600 smooth-transition cursor-pointer">2</button>
        <button onclick="appendPinDigit('3')" class="bg-slate-800 text-slate-200 p-3.5 rounded-xl font-bold text-lg hover:bg-slate-700 active:bg-slate-600 smooth-transition cursor-pointer">3</button>
        <button onclick="appendPinDigit('4')" class="bg-slate-800 text-slate-200 p-3.5 rounded-xl font-bold text-lg hover:bg-slate-700 active:bg-slate-600 smooth-transition cursor-pointer">4</button>
        <button onclick="appendPinDigit('5')" class="bg-slate-800 text-slate-200 p-3.5 rounded-xl font-bold text-lg hover:bg-slate-700 active:bg-slate-600 smooth-transition cursor-pointer">5</button>
        <button onclick="appendPinDigit('6')" class="bg-slate-800 text-slate-200 p-3.5 rounded-xl font-bold text-lg hover:bg-slate-700 active:bg-slate-600 smooth-transition cursor-pointer">6</button>
        <button onclick="appendPinDigit('7')" class="bg-slate-800 text-slate-200 p-3.5 rounded-xl font-bold text-lg hover:bg-slate-700 active:bg-slate-600 smooth-transition cursor-pointer">7</button>
        <button onclick="appendPinDigit('8')" class="bg-slate-800 text-slate-200 p-3.5 rounded-xl font-bold text-lg hover:bg-slate-700 active:bg-slate-600 smooth-transition cursor-pointer">8</button>
        <button onclick="appendPinDigit('9')" class="bg-slate-800 text-slate-200 p-3.5 rounded-xl font-bold text-lg hover:bg-slate-700 active:bg-slate-600 smooth-transition cursor-pointer">9</button>
        <button onclick="resetPinInput()" class="bg-slate-950 text-rose-400 p-3.5 rounded-xl font-bold text-xs hover:bg-rose-950/40 smooth-transition cursor-pointer">CLR</button>
        <button onclick="appendPinDigit('0')" class="bg-slate-800 text-slate-200 p-3.5 rounded-xl font-bold text-lg hover:bg-slate-700 active:bg-slate-600 smooth-transition cursor-pointer">0</button>
        <button onclick="popPinDigit()" class="bg-slate-950 text-slate-400 p-3.5 rounded-xl font-bold text-lg hover:bg-slate-800 smooth-transition cursor-pointer">⌫</button>
      </div>
      <p class="text-[10px] text-slate-500 font-mono-tech mt-5">DEFAULT HANDSHAKE PIN: 1234</p>
    </div>
  </section>


  <section id="module-dashboard" class="h-full w-full flex flex-col p-4 bg-slate-950" style="display: none;">
    
    <header class="flex justify-between items-center border-b border-slate-800 pb-3 mb-4">
      <div class="flex items-center gap-2.5">
        <span class="text-white font-extrabold text-lg tracking-tight">Console Monitor</span>
        <span class="text-[10px] bg-slate-900 border border-slate-800 text-slate-400 px-2 py-0.5 rounded-md font-mono-tech">v2.1.0-PRO</span>
      </div>
      
      <div class="flex items-center gap-4 bg-slate-900 border border-slate-800 px-3 py-1.5 rounded-xl">
        <div class="flex items-center gap-2">
          <span class="w-2 h-2 bg-emerald-500 rounded-full"></span>
          <span class="text-xs font-semibold text-emerald-400 font-mono-tech">PIPELINE_CONNECTED</span>
        </div>
        <button onclick="location.reload()" class="text-xs text-slate-400 hover:text-rose-400 font-semibold pl-2 border-l border-slate-800 smooth-transition cursor-pointer">Exit Session</button>
      </div>
    </header>

    <div class="grid grid-cols-12 gap-4 flex-1 overflow-hidden">
      
      <nav class="col-span-3 bg-slate-900 border border-slate-800 rounded-xl p-3 flex flex-col justify-between">
        <div class="space-y-1">
          <span class="text-[10px] uppercase font-bold tracking-wider text-slate-500 px-2 block mb-2 font-mono-tech">Console Viewports</span>
          
          <button id="tab-control-telemetry" onclick="renderSubTabViewport('view-telemetry')" class="w-full flex items-center justify-between px-3 py-2.5 rounded-lg bg-blue-600/10 text-blue-400 border border-blue-500/20 text-xs font-bold tracking-wide smooth-transition cursor-pointer">
            <span>📈 Diagnostics Board</span>
          </button>
          <button id="tab-control-streams" onclick="renderSubTabViewport('view-streams')" class="w-full flex items-center justify-between px-3 py-2.5 rounded-lg text-slate-400 hover:bg-slate-800 hover:text-slate-200 text-xs font-bold tracking-wide smooth-transition cursor-pointer">
            <span>🔌 Pipeline Controls</span>
          </button>
        </div>

        <div class="bg-slate-950 p-3 rounded-lg border border-slate-800 text-[11px] font-mono-tech text-slate-500 space-y-1">
          <div>SOCKET CHANNEL: <span class="text-emerald-400 font-bold">READY</span></div>
          <div>REMOTE HOST: <span class="text-slate-400">LOCAL_LOOPBACK</span></div>
        </div>
      </nav>

      <main class="col-span-9 h-full relative">

        <div id="subtab-view-telemetry" class="h-full grid grid-cols-2 gap-4">
          <div class="bg-slate-900 border border-slate-800 rounded-xl p-4 flex flex-col justify-between">
            <div class="border-b border-slate-800 pb-2 flex justify-between items-center">
              <span class="text-xs font-bold text-slate-400">Kinematic Structural Layout</span>
              <span class="text-[10px] bg-blue-500/10 text-blue-400 px-2 py-0.5 rounded font-mono-tech">Static Axis</span>
            </div>
            
            <div class="my-auto flex justify-center py-4">
              <svg viewBox="0 0 100 120" class="w-36 h-auto text-blue-500" fill="none" stroke="currentColor" stroke-width="2">
                <line x1="50" y1="20" x2="50" y2="80" stroke-dasharray="2,2" stroke-width="1"/>
                <line x1="50" y1="40" x2="20" y2="70" />
                <line x1="50" y1="40" x2="80" y2="70" />
                <line x1="50" y1="80" x2="35" y2="110" />
                <line x1="50" y1="80" x2="65" y2="110" />
                <circle cx="50" cy="20" r="4" fill="#3b82f6" />
                <circle cx="50" cy="40" r="3.5" fill="#3b82f6" />
                <circle cx="20" cy="70" r="3.5" fill="#3b82f6" />
                <circle cx="80" cy="70" r="3.5" fill="#3b82f6" />
              </svg>
            </div>

            <div class="border-t border-slate-800/60 pt-2 text-[10px] text-slate-500 flex justify-between font-mono-tech">
              <span>CANVAS HOVER MAP</span>
              <span class="text-emerald-500 font-bold">STABLE INTEGRITY</span>
            </div>
          </div>

          <div class="flex flex-col gap-4">
            <div class="flex-1 bg-slate-900 border border-slate-800 rounded-xl p-4 flex flex-col justify-between">
              <span class="text-xs font-bold text-slate-400">Mechanical Strain Load</span>
              <div class="my-2">
                <div id="runtime-strain-val" class="text-4xl font-extrabold text-white font-mono-tech">0.00<span class="text-base text-slate-500 ml-0.5">%</span></div>
              </div>
              <p class="text-xs text-slate-500 leading-normal">Main monitoring parameter reporting structural mechanical load values across internal matrix channels.</p>
            </div>

            <div class="flex-1 bg-slate-900 border border-slate-800 rounded-xl p-4 flex flex-col justify-between">
              <span class="text-xs font-bold text-slate-400">Interface Pulse Velocity</span>
              <div class="my-2">
                <div id="runtime-pulse-val" class="text-4xl font-extrabold text-white font-mono-tech">-- <span class="text-base text-slate-500 ml-0.5">HZ</span></div>
              </div>
              <p class="text-xs text-slate-500 leading-normal">Aggregated frame update calculations sampling active internal channel routing pipeline updates.</p>
            </div>
          </div>
        </div>

        <div id="subtab-view-streams" class="h-full bg-slate-900 border border-slate-800 rounded-xl p-5 flex flex-col justify-between" style="display: none;">
          <div class="space-y-4">
            <div class="border-b border-slate-800 pb-3">
              <h3 class="text-sm font-bold text-white">Pipeline Execution Center</h3>
              <p class="text-xs text-slate-400 mt-0.5">Manage live automated array deployment configurations and system stream logs.</p>
            </div>
            
            <div class="space-y-4 max-w-md">
              <div>
                <label class="text-xs font-semibold text-slate-300 block mb-1.5">Compilation Endpoint Vector URL</label>
                <input type="text" value="ws://127.0.0.1:8080/stream/pipeline" class="w-full bg-slate-950 p-2.5 rounded-lg border border-slate-800 text-xs text-blue-400 font-mono-tech focus:outline-none" readonly>
              </div>
              
              <div>
                <label class="text-xs font-semibold text-slate-300 block mb-1.5">Runtime Architecture Package Target</label>
                <select class="w-full bg-slate-950 p-2.5 rounded-lg border border-slate-800 text-xs text-slate-300 focus:outline-none">
                  <option>Core Standard UI Matrix Assembly Bundle</option>
                </select>
              </div>
            </div>
          </div>

          <div class="pt-4 border-t border-slate-800">
            <button id="stream-action-btn" onclick="toggleLocalStreamInstance()" class="bg-blue-600 hover:bg-blue-500 text-white font-bold text-xs py-3 px-5 rounded-lg smooth-transition cursor-pointer shadow-md shadow-blue-900/10 uppercase tracking-wider">
              Initialize Data Streaming
            </button>
            <div id="console-stream-logger" class="mt-4 bg-slate-950 p-3 rounded-lg border border-slate-800 text-[11px] text-slate-500 font-mono-tech h-24 overflow-y-auto">
              [SYSTEM] Interface layer diagnostic subsystem idle. Awaiting user link...
            </div>
          </div>
        </div>

      </main>
    </div>
  </section>


  <script>
    let currentAuthPin = "";
    const SystemAccessPin = "1234";
    let activeStreamStatus = false;
    let metricLoopInterval;

    // --- GATEWAY LOGIN SCREEN ROUTING CONTROL ---
    function handleLoginRoute() {
      const userField = document.getElementById('input-username').value;
      if (userField.trim() !== "") {
        document.getElementById('module-auth').style.display = 'none';
        document.getElementById('module-pin').style.display = 'flex';
      }
    }

    // --- TACTILE PIN HANDLING ARCHITECTURE ---
    function appendPinDigit(digit) {
      if (currentAuthPin.length < 4) {
        currentAuthPin += digit;
        refreshPinLayoutDisplay();
      }
      if (currentAuthPin.length === 4) {
        setTimeout(verifySystemPinHandshake, 250);
      }
    }

    function refreshPinLayoutDisplay() {
      let activeDots = currentAuthPin.split("").map(() => "●").join(" ");
      let openSlots = Array(4 - currentAuthPin.length).fill("_").join(" ");
      document.getElementById('pin-secure-mask').innerText = (activeDots + " " + openSlots).trim();
    }

    function resetPinInput() {
      currentAuthPin = "";
      refreshPinLayoutDisplay();
    }

    function popPinDigit() {
      currentAuthPin = currentAuthPin.slice(0, -1);
      refreshPinLayoutDisplay();
    }

    function verifySystemPinHandshake() {
      if (currentAuthPin === SystemAccessPin) {
        document.getElementById('module-pin').style.display = 'none';
        document.getElementById('module-dashboard').style.display = 'flex';
      } else {
        alert("ACCESS DENIED: Internal link configuration authentication failure.");
        resetPinInput();
      }
    }

    // --- DASHBOARD INNER SIDEBAR VIEWPORT SWITCHING ---
    function renderSubTabViewport(selectedViewId) {
      const subviews = ['view-telemetry', 'view-streams'];
      subviews.forEach(view => {
        document.getElementById(`subtab-${view}`).style.display = 'none';
      });
      
      // Target specific container layouts structurally
      if (selectedViewId === 'view-telemetry') {
        document.getElementById(`subtab-${selectedViewId}`).style.display = 'grid';
      } else {
        document.getElementById(`subtab-${selectedViewId}`).style.display = 'flex';
      }

      // Update button aesthetic state changes
      const interfaceTabs = { 'view-telemetry': 'telemetry', 'view-streams': 'streams' };
      Object.keys(interfaceTabs).forEach(key => {
        let actionButton = document.getElementById(`tab-control-${interfaceTabs[key]}`);
        if(key === selectedViewId) {
          actionButton.className = "w-full flex items-center justify-between px-3 py-2.5 rounded-lg bg-blue-600/10 text-blue-400 border border-blue-500/20 text-xs font-bold tracking-wide smooth-transition cursor-pointer";
        } else {
          actionButton.className = "w-full flex items-center justify-between px-3 py-2.5 rounded-lg text-slate-400 hover:bg-slate-800 hover:text-slate-200 text-xs font-bold tracking-wide smooth-transition cursor-pointer";
        }
      });
    }

    // --- PIPELINE LOG STREAM SIMULATION MOTOR ---
    function toggleLocalStreamInstance() {
      const logContainer = document.getElementById('console-stream-logger');
      const systemBtn = document.getElementById('stream-action-btn');

      if (!activeStreamStatus) {
        activeStreamStatus = true;
        systemBtn.innerText = "Terminate Active Stream";
        systemBtn.className = "bg-rose-600 hover:bg-rose-500 text-white font-bold text-xs py-3 px-5 rounded-lg smooth-transition cursor-pointer shadow-md shadow-rose-900/10 uppercase tracking-wider";
        
        let timeStampStr = new Date().toLocaleTimeString();
        logContainer.innerHTML += `<div class="text-emerald-400 mt-1">[${timeStampStr}] [SOCKET] Channel pipeline handshake established. Telemetry mounting...</div>`;
        logContainer.scrollTop = logContainer.scrollHeight;

        fireMockTelemetryInterval();
      } else {
        activeStreamStatus = false;
        systemBtn.innerText = "Initialize Data Streaming";
        systemBtn.className = "bg-blue-600 hover:bg-blue-500 text-white font-bold text-xs py-3 px-5 rounded-lg smooth-transition cursor-pointer shadow-md shadow-blue-900/10 uppercase tracking-wider";
        
        logContainer.innerHTML += `<div class="text-rose-400 mt-1">[SYSTEM] Pipeline session sequence manually interrupted by operator.</div>`;
        logContainer.scrollTop = logContainer.scrollHeight;
        
        clearMockTelemetryInterval();
      }
    }

    function fireMockTelemetryInterval() {
      metricLoopInterval = setInterval(() => {
        let randomizedStrain = (Math.random() * 8 + 22).toFixed(2);
        document.getElementById('runtime-strain-val').innerHTML = `${randomizedStrain}<span class="text-base text-slate-500 ml-0.5">%</span>`;
        
        let randomizedPulse = Math.floor(Math.random() * 12 + 58);
        document.getElementById('runtime-pulse-val').innerHTML = `${randomizedPulse}<span class="text-base text-slate-500 ml-0.5">HZ</span>`;
      }, 400);
    }

    function clearMockTelemetryInterval() {
      clearInterval(metricLoopInterval);
      document.getElementById('runtime-strain-val').innerHTML = `0.00<span class="text-base text-slate-500 ml-0.5">%</span>`;
      document.getElementById('runtime-pulse-val').innerHTML = `-- <span class="text-base text-slate-500 ml-0.5">HZ</span>`;
    }
  </script>
</body>
</html>




THIS IS THE JAVASCRIPT CODE 

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>System Interface Portal</title>
  <script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;700&family=Plus+Jakarta+Sans:wght@400;600;800&display=swap" rel="stylesheet">
  
  <style>
    body {
      font-family: 'Plus Jakarta Sans', sans-serif;
    }
    .font-mono-tech {
      font-family: 'JetBrains Mono', monospace;
    }
    /* Smooth transition framework for interactive components */
    .smooth-transition {
      transition: all 0.2s cubic-bezier(0.4, 0, 0.2, 1);
    }
  </style>
</head>
<body class="bg-slate-950 text-slate-100 h-screen w-screen overflow-hidden select-none">

  <section id="module-auth" class="flex flex-col items-center justify-center h-full w-full px-4">
    <div class="bg-slate-900 border border-slate-800 p-8 rounded-2xl max-w-md w-full shadow-2xl">
      
      <div class="text-center mb-6">
        <h1 class="text-xl font-extrabold tracking-tight text-white">System Access Gateway</h1>
        <p class="text-xs text-slate-400 mt-1">Provide operator parameters to initialize link layers</p>
      </div>
      
      <div class="space-y-4">
        <div>
          <label class="text-xs font-semibold text-slate-300 block mb-1.5">Operator Identification Key</label>
          <input type="text" id="input-username" value="OPERATOR_DEFAULT_NODE" class="w-full px-4 py-3 bg-slate-950 rounded-xl border border-slate-700 text-slate-200 text-sm focus:outline-none focus:border-blue-500 font-mono-tech smooth-transition">
        </div>
        
        <div>
          <label class="text-xs font-semibold text-slate-300 block mb-1.5">Security Credentials</label>
          <input type="password" id="input-password" value="system_secure_pass" class="w-full px-4 py-3 bg-slate-950 rounded-xl border border-slate-700 text-slate-200 text-sm focus:outline-none focus:border-blue-500 smooth-transition">
        </div>

        <button onclick="handleLoginRoute()" class="w-full bg-blue-600 hover:bg-blue-500 text-white font-bold text-sm py-3.5 rounded-xl mt-2 smooth-transition shadow-lg shadow-blue-900/20 active:scale-[0.98] cursor-pointer">
          Verify System Authentication
        </button>
      </div>
    </div>
  </section>


  <section id="module-pin" class="flex flex-col items-center justify-center h-full w-full px-4" style="display: none;">
    <div class="bg-slate-900 border border-slate-800 p-8 rounded-2xl max-w-xs w-full text-center shadow-2xl">
      
      <div class="mb-4">
        <h2 class="text-base font-bold text-white">Pipeline Authorization</h2>
        <p class="text-[11px] text-slate-400 mt-0.5">Input system authorization PIN passcode</p>
      </div>
      
      <div id="pin-secure-mask" class="text-2xl font-bold py-3.5 mb-5 bg-slate-950 rounded-xl border border-slate-800 text-blue-400 tracking-widest font-mono-tech shadow-inner">
        _ _ _ _
      </div>
      
      <div class="grid grid-cols-3 gap-2 max-w-[220px] mx-auto font-mono-tech">
        <button onclick="appendPinDigit('1')" class="bg-slate-800 text-slate-200 p-3.5 rounded-xl font-bold text-lg hover:bg-slate-700 active:bg-slate-600 smooth-transition cursor-pointer">1</button>
        <button onclick="appendPinDigit('2')" class="bg-slate-800 text-slate-200 p-3.5 rounded-xl font-bold text-lg hover:bg-slate-700 active:bg-slate-600 smooth-transition cursor-pointer">2</button>
        <button onclick="appendPinDigit('3')" class="bg-slate-800 text-slate-200 p-3.5 rounded-xl font-bold text-lg hover:bg-slate-700 active:bg-slate-600 smooth-transition cursor-pointer">3</button>
        <button onclick="appendPinDigit('4')" class="bg-slate-800 text-slate-200 p-3.5 rounded-xl font-bold text-lg hover:bg-slate-700 active:bg-slate-600 smooth-transition cursor-pointer">4</button>
        <button onclick="appendPinDigit('5')" class="bg-slate-800 text-slate-200 p-3.5 rounded-xl font-bold text-lg hover:bg-slate-700 active:bg-slate-600 smooth-transition cursor-pointer">5</button>
        <button onclick="appendPinDigit('6')" class="bg-slate-800 text-slate-200 p-3.5 rounded-xl font-bold text-lg hover:bg-slate-700 active:bg-slate-600 smooth-transition cursor-pointer">6</button>
        <button onclick="appendPinDigit('7')" class="bg-slate-800 text-slate-200 p-3.5 rounded-xl font-bold text-lg hover:bg-slate-700 active:bg-slate-600 smooth-transition cursor-pointer">7</button>
        <button onclick="appendPinDigit('8')" class="bg-slate-800 text-slate-200 p-3.5 rounded-xl font-bold text-lg hover:bg-slate-700 active:bg-slate-600 smooth-transition cursor-pointer">8</button>
        <button onclick="appendPinDigit('9')" class="bg-slate-800 text-slate-200 p-3.5 rounded-xl font-bold text-lg hover:bg-slate-700 active:bg-slate-600 smooth-transition cursor-pointer">9</button>
        <button onclick="resetPinInput()" class="bg-slate-950 text-rose-400 p-3.5 rounded-xl font-bold text-xs hover:bg-rose-950/40 smooth-transition cursor-pointer">CLR</button>
        <button onclick="appendPinDigit('0')" class="bg-slate-800 text-slate-200 p-3.5 rounded-xl font-bold text-lg hover:bg-slate-700 active:bg-slate-600 smooth-transition cursor-pointer">0</button>
        <button onclick="popPinDigit()" class="bg-slate-950 text-slate-400 p-3.5 rounded-xl font-bold text-lg hover:bg-slate-800 smooth-transition cursor-pointer">⌫</button>
      </div>
      <p class="text-[10px] text-slate-500 font-mono-tech mt-5">DEFAULT HANDSHAKE PIN: 1234</p>
    </div>
  </section>


  <section id="module-dashboard" class="h-full w-full flex flex-col p-4 bg-slate-950" style="display: none;">
    
    <header class="flex justify-between items-center border-b border-slate-800 pb-3 mb-4">
      <div class="flex items-center gap-2.5">
        <span class="text-white font-extrabold text-lg tracking-tight">Console Monitor</span>
        <span class="text-[10px] bg-slate-900 border border-slate-800 text-slate-400 px-2 py-0.5 rounded-md font-mono-tech">v2.1.0-PRO</span>
      </div>
      
      <div class="flex items-center gap-4 bg-slate-900 border border-slate-800 px-3 py-1.5 rounded-xl">
        <div class="flex items-center gap-2">
          <span class="w-2 h-2 bg-emerald-500 rounded-full"></span>
          <span class="text-xs font-semibold text-emerald-400 font-mono-tech">PIPELINE_CONNECTED</span>
        </div>
        <button onclick="location.reload()" class="text-xs text-slate-400 hover:text-rose-400 font-semibold pl-2 border-l border-slate-800 smooth-transition cursor-pointer">Exit Session</button>
      </div>
    </header>

    <div class="grid grid-cols-12 gap-4 flex-1 overflow-hidden">
      
      <nav class="col-span-3 bg-slate-900 border border-slate-800 rounded-xl p-3 flex flex-col justify-between">
        <div class="space-y-1">
          <span class="text-[10px] uppercase font-bold tracking-wider text-slate-500 px-2 block mb-2 font-mono-tech">Console Viewports</span>
          
          <button id="tab-control-telemetry" onclick="renderSubTabViewport('view-telemetry')" class="w-full flex items-center justify-between px-3 py-2.5 rounded-lg bg-blue-600/10 text-blue-400 border border-blue-500/20 text-xs font-bold tracking-wide smooth-transition cursor-pointer">
            <span>📈 Diagnostics Board</span>
          </button>
          <button id="tab-control-streams" onclick="renderSubTabViewport('view-streams')" class="w-full flex items-center justify-between px-3 py-2.5 rounded-lg text-slate-400 hover:bg-slate-800 hover:text-slate-200 text-xs font-bold tracking-wide smooth-transition cursor-pointer">
            <span>🔌 Pipeline Controls</span>
          </button>
        </div>

        <div class="bg-slate-950 p-3 rounded-lg border border-slate-800 text-[11px] font-mono-tech text-slate-500 space-y-1">
          <div>SOCKET CHANNEL: <span class="text-emerald-400 font-bold">READY</span></div>
          <div>REMOTE HOST: <span class="text-slate-400">LOCAL_LOOPBACK</span></div>
        </div>
      </nav>

      <main class="col-span-9 h-full relative">

        <div id="subtab-view-telemetry" class="h-full grid grid-cols-2 gap-4">
          <div class="bg-slate-900 border border-slate-800 rounded-xl p-4 flex flex-col justify-between">
            <div class="border-b border-slate-800 pb-2 flex justify-between items-center">
              <span class="text-xs font-bold text-slate-400">Kinematic Structural Layout</span>
              <span class="text-[10px] bg-blue-500/10 text-blue-400 px-2 py-0.5 rounded font-mono-tech">Static Axis</span>
            </div>
            
            <div class="my-auto flex justify-center py-4">
              <svg viewBox="0 0 100 120" class="w-36 h-auto text-blue-500" fill="none" stroke="currentColor" stroke-width="2">
                <line x1="50" y1="20" x2="50" y2="80" stroke-dasharray="2,2" stroke-width="1"/>
                <line x1="50" y1="40" x2="20" y2="70" />
                <line x1="50" y1="40" x2="80" y2="70" />
                <line x1="50" y1="80" x2="35" y2="110" />
                <line x1="50" y1="80" x2="65" y2="110" />
                <circle cx="50" cy="20" r="4" fill="#3b82f6" />
                <circle cx="50" cy="40" r="3.5" fill="#3b82f6" />
                <circle cx="20" cy="70" r="3.5" fill="#3b82f6" />
                <circle cx="80" cy="70" r="3.5" fill="#3b82f6" />
              </svg>
            </div>

            <div class="border-t border-slate-800/60 pt-2 text-[10px] text-slate-500 flex justify-between font-mono-tech">
              <span>CANVAS HOVER MAP</span>
              <span class="text-emerald-500 font-bold">STABLE INTEGRITY</span>
            </div>
          </div>

          <div class="flex flex-col gap-4">
            <div class="flex-1 bg-slate-900 border border-slate-800 rounded-xl p-4 flex flex-col justify-between">
              <span class="text-xs font-bold text-slate-400">Mechanical Strain Load</span>
              <div class="my-2">
                <div id="runtime-strain-val" class="text-4xl font-extrabold text-white font-mono-tech">0.00<span class="text-base text-slate-500 ml-0.5">%</span></div>
              </div>
              <p class="text-xs text-slate-500 leading-normal">Main monitoring parameter reporting structural mechanical load values across internal matrix channels.</p>
            </div>

            <div class="flex-1 bg-slate-900 border border-slate-800 rounded-xl p-4 flex flex-col justify-between">
              <span class="text-xs font-bold text-slate-400">Interface Pulse Velocity</span>
              <div class="my-2">
                <div id="runtime-pulse-val" class="text-4xl font-extrabold text-white font-mono-tech">-- <span class="text-base text-slate-500 ml-0.5">HZ</span></div>
              </div>
              <p class="text-xs text-slate-500 leading-normal">Aggregated frame update calculations sampling active internal channel routing pipeline updates.</p>
            </div>
          </div>
        </div>

        <div id="subtab-view-streams" class="h-full bg-slate-900 border border-slate-800 rounded-xl p-5 flex flex-col justify-between" style="display: none;">
          <div class="space-y-4">
            <div class="border-b border-slate-800 pb-3">
              <h3 class="text-sm font-bold text-white">Pipeline Execution Center</h3>
              <p class="text-xs text-slate-400 mt-0.5">Manage live automated array deployment configurations and system stream logs.</p>
            </div>
            
            <div class="space-y-4 max-w-md">
              <div>
                <label class="text-xs font-semibold text-slate-300 block mb-1.5">Compilation Endpoint Vector URL</label>
                <input type="text" value="ws://127.0.0.1:8080/stream/pipeline" class="w-full bg-slate-950 p-2.5 rounded-lg border border-slate-800 text-xs text-blue-400 font-mono-tech focus:outline-none" readonly>
              </div>
              
              <div>
                <label class="text-xs font-semibold text-slate-300 block mb-1.5">Runtime Architecture Package Target</label>
                <select class="w-full bg-slate-950 p-2.5 rounded-lg border border-slate-800 text-xs text-slate-300 focus:outline-none">
                  <option>Core Standard UI Matrix Assembly Bundle</option>
                </select>
              </div>
            </div>
          </div>

          <div class="pt-4 border-t border-slate-800">
            <button id="stream-action-btn" onclick="toggleLocalStreamInstance()" class="bg-blue-600 hover:bg-blue-500 text-white font-bold text-xs py-3 px-5 rounded-lg smooth-transition cursor-pointer shadow-md shadow-blue-900/10 uppercase tracking-wider">
              Initialize Data Streaming
            </button>
            <div id="console-stream-logger" class="mt-4 bg-slate-950 p-3 rounded-lg border border-slate-800 text-[11px] text-slate-500 font-mono-tech h-24 overflow-y-auto">
              [SYSTEM] Interface layer diagnostic subsystem idle. Awaiting user link...
            </div>
          </div>
        </div>

      </main>
    </div>
  </section>


  <script>
    let currentAuthPin = "";
    const SystemAccessPin = "1234";
    let activeStreamStatus = false;
    let metricLoopInterval;

    // --- GATEWAY LOGIN SCREEN ROUTING CONTROL ---
    function handleLoginRoute() {
      const userField = document.getElementById('input-username').value;
      if (userField.trim() !== "") {
        document.getElementById('module-auth').style.display = 'none';
        document.getElementById('module-pin').style.display = 'flex';
      }
    }

    // --- TACTILE PIN HANDLING ARCHITECTURE ---
    function appendPinDigit(digit) {
      if (currentAuthPin.length < 4) {
        currentAuthPin += digit;
        refreshPinLayoutDisplay();
      }
      if (currentAuthPin.length === 4) {
        setTimeout(verifySystemPinHandshake, 250);
      }
    }

    function refreshPinLayoutDisplay() {
      let activeDots = currentAuthPin.split("").map(() => "●").join(" ");
      let openSlots = Array(4 - currentAuthPin.length).fill("_").join(" ");
      document.getElementById('pin-secure-mask').innerText = (activeDots + " " + openSlots).trim();
    }

    function resetPinInput() {
      currentAuthPin = "";
      refreshPinLayoutDisplay();
    }

    function popPinDigit() {
      currentAuthPin = currentAuthPin.slice(0, -1);
      refreshPinLayoutDisplay();
    }

    function verifySystemPinHandshake() {
      if (currentAuthPin === SystemAccessPin) {
        document.getElementById('module-pin').style.display = 'none';
        document.getElementById('module-dashboard').style.display = 'flex';
      } else {
        alert("ACCESS DENIED: Internal link configuration authentication failure.");
        resetPinInput();
      }
    }

    // --- DASHBOARD INNER SIDEBAR VIEWPORT SWITCHING ---
    function renderSubTabViewport(selectedViewId) {
      const subviews = ['view-telemetry', 'view-streams'];
      subviews.forEach(view => {
        document.getElementById(`subtab-${view}`).style.display = 'none';
      });
      
      // Target specific container layouts structurally
      if (selectedViewId === 'view-telemetry') {
        document.getElementById(`subtab-${selectedViewId}`).style.display = 'grid';
      } else {
        document.getElementById(`subtab-${selectedViewId}`).style.display = 'flex';
      }

      // Update button aesthetic state changes
      const interfaceTabs = { 'view-telemetry': 'telemetry', 'view-streams': 'streams' };
      Object.keys(interfaceTabs).forEach(key => {
        let actionButton = document.getElementById(`tab-control-${interfaceTabs[key]}`);
        if(key === selectedViewId) {
          actionButton.className = "w-full flex items-center justify-between px-3 py-2.5 rounded-lg bg-blue-600/10 text-blue-400 border border-blue-500/20 text-xs font-bold tracking-wide smooth-transition cursor-pointer";
        } else {
          actionButton.className = "w-full flex items-center justify-between px-3 py-2.5 rounded-lg text-slate-400 hover:bg-slate-800 hover:text-slate-200 text-xs font-bold tracking-wide smooth-transition cursor-pointer";
        }
      });
    }

    // --- PIPELINE LOG STREAM SIMULATION MOTOR ---
    function toggleLocalStreamInstance() {
      const logContainer = document.getElementById('console-stream-logger');
      const systemBtn = document.getElementById('stream-action-btn');

      if (!activeStreamStatus) {
        activeStreamStatus = true;
        systemBtn.innerText = "Terminate Active Stream";
        systemBtn.className = "bg-rose-600 hover:bg-rose-500 text-white font-bold text-xs py-3 px-5 rounded-lg smooth-transition cursor-pointer shadow-md shadow-rose-900/10 uppercase tracking-wider";
        
        let timeStampStr = new Date().toLocaleTimeString();
        logContainer.innerHTML += `<div class="text-emerald-400 mt-1">[${timeStampStr}] [SOCKET] Channel pipeline handshake established. Telemetry mounting...</div>`;
        logContainer.scrollTop = logContainer.scrollHeight;

        fireMockTelemetryInterval();
      } else {
        activeStreamStatus = false;
        systemBtn.innerText = "Initialize Data Streaming";
        systemBtn.className = "bg-blue-600 hover:bg-blue-500 text-white font-bold text-xs py-3 px-5 rounded-lg smooth-transition cursor-pointer shadow-md shadow-blue-900/10 uppercase tracking-wider";
        
        logContainer.innerHTML += `<div class="text-rose-400 mt-1">[SYSTEM] Pipeline session sequence manually interrupted by operator.</div>`;
        logContainer.scrollTop = logContainer.scrollHeight;
        
        clearMockTelemetryInterval();
      }
    }

    function fireMockTelemetryInterval() {
      metricLoopInterval = setInterval(() => {
        let randomizedStrain = (Math.random() * 8 + 22).toFixed(2);
        document.getElementById('runtime-strain-val').innerHTML = `${randomizedStrain}<span class="text-base text-slate-500 ml-0.5">%</span>`;
        
        let randomizedPulse = Math.floor(Math.random() * 12 + 58);
        document.getElementById('runtime-pulse-val').innerHTML = `${randomizedPulse}<span class="text-base text-slate-500 ml-0.5">HZ</span>`;
      }, 400);
    }

    function clearMockTelemetryInterval() {
      clearInterval(metricLoopInterval);
      document.getElementById('runtime-strain-val').innerHTML = `0.00<span class="text-base text-slate-500 ml-0.5">%</span>`;
      document.getElementById('runtime-pulse-val').innerHTML = `-- <span class="text-base text-slate-500 ml-0.5">HZ</span>`;
    }
  </script>
</body>
</html>
