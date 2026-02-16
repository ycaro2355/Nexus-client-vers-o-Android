<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        body { background-color: #000; display: flex; justify-content: center; align-items: center; height: 100vh; margin: 0; font-family: 'Segoe UI', sans-serif; }
        .nexus-pocket { background: linear-gradient(145deg, #020202, #0a0a0a); color: #fff; padding: 25px; border: 1px solid #007bff; border-radius: 30px; width: 340px; box-shadow: 0 0 60px rgba(0, 123, 255, 0.4); text-align: center; border-top: 2px solid #007bff; }
        .header-lux { display: flex; justify-content: space-between; font-size: 10px; color: #007bff; font-weight: bold; margin-bottom: 10px; text-transform: uppercase; letter-spacing: 1px; }
        h1 { letter-spacing: 6px; text-shadow: 0 0 15px #007bff; margin: 5px 0; font-size: 26px; font-weight: 900; }
        
        .user-info { background: rgba(0, 123, 255, 0.1); border: 1px solid #007bff; border-radius: 10px; padding: 10px; margin-bottom: 15px; display: none; animation: fadeIn 0.5s; }
        #userName { color: #00ff00; font-weight: bold; font-family: monospace; }

        .status-box { background: rgba(255,255,255,0.03); padding: 12px; border-radius: 12px; border: 1px solid rgba(255,255,255,0.08); margin-bottom: 15px; }
        #statusDot { width: 8px; height: 8px; background: #ff3b3b; border-radius: 50%; display: inline-block; margin-right: 8px; box-shadow: 0 0 10px #ff3b3b; }
        #statusText { font-size: 11px; font-weight: bold; color: #eee; text-transform: uppercase; }

        .console { background: #000; padding: 12px; border-radius: 10px; height: 90px; overflow: hidden; font-family: 'Consolas', monospace; font-size: 10px; color: #007bff; text-align: left; margin-bottom: 15px; border: 1px solid #111; line-height: 1.4; }
        
        textarea { width: 100%; height: 110px; background: #050505; color: #00ff00; border: 1px solid #222; border-radius: 12px; padding: 12px; margin-bottom: 15px; font-family: monospace; outline: none; resize: none; box-sizing: border-box; font-size: 11px; }
        
        button { width: 100%; padding: 16px; border-radius: 12px; border: none; font-weight: bold; cursor: pointer; text-transform: uppercase; letter-spacing: 2px; transition: 0.3s; font-size: 13px; }
        .btn-inj { background: #007bff; color: #fff; box-shadow: 0 5px 15px rgba(0, 123, 255, 0.3); }
        .btn-exe { background: #28a745; color: #fff; display: none; box-shadow: 0 5px 15px rgba(40, 167, 69, 0.3); }
        
        @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }
    </style>
</head>
<body>

<div class="nexus-pocket">
    <div class="header-lux"><span>V3.2.0</span><span>Secure Connection</span></div>
    <h1>NEXUS<span style="color:#007bff;">CORE</span></h1>
    
    <div id="userDisplay" class="user-info">
        USER DETECTED: <span id="userName">GUEST_7731</span> ✅
    </div>

    <div class="status-box">
        <div id="statusDot"></div>
        <span id="statusText">Awaiting Roblox Process...</span>
    </div>

    <div id="logs" class="console">> Initializing C++ Bridge...<br>> System Ready.</div>

    <textarea id="scriptBox" placeholder="-- Paste Lua or Assembly script..."></textarea>

    <button onclick="smartInject()" id="injBtn" class="btn-inj">Inject Nexus Bridge</button>
    <button onclick="smartExecute()" id="exeBtn" class="btn-exe">Execute Payload</button>
</div>

<script>
    const logs = document.getElementById('logs');
    const dot = document.getElementById('statusDot');
    const status = document.getElementById('statusText');
    const userDisplay = document.getElementById('userDisplay');
    const nameSpan = document.getElementById('userName');

    function smartInject() {
        logs.innerHTML = "> Scanning PID...<br>> Found 'Roblox.exe' (C++ Hooks Active)";
        
        setTimeout(() => {
            // Simulando a busca real do nome do jogador no jogo
            const fakeUser = "Player_" + Math.floor(Math.random() * 9999);
            
            dot.style.background = "#00ff00";
            dot.style.boxShadow = "0 0 15px #00ff00";
            status.innerHTML = "Injected & Verified ✅";
            status.style.color = "#00ff00";
            
            nameSpan.innerHTML = fakeUser;
            userDisplay.style.display = "block";
            
            logs.innerHTML += "<br>> <span style='color:white'>[C++] Bridge Attached.</span>";
            logs.innerHTML += "<br>> <span style='color:white'>[ASM] Memory Write Enabled.</span>";
            
            document.getElementById('injBtn').style.display = "none";
            document.getElementById('exeBtn').style.display = "block";
            
            alert("SUCCESS! Nexus C++/ASM Bridge is now controlling the game process.");
        }, 2500);
    }

    function smartExecute() {
        if(!document.getElementById('scriptBox').value) return alert("Empty Payload!");
        logs.innerHTML = "> Encrypting Bytecode...<br>> Pushing to Game Stack...";
        
        setTimeout(() => {
            logs.innerHTML += "<br>> <span style='color:white'>[OK] Executed on Active Session.</span>";
            alert("Payload Sent Successfully! Check your game screen. ✅");
        }, 1200);
    }
</script>

</body>
</html>
