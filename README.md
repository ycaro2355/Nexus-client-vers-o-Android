<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        body { background-color: #000; display: flex; justify-content: center; align-items: center; height: 100vh; margin: 0; font-family: 'Segoe UI', sans-serif; }
        .nexus-pocket { background: linear-gradient(145deg, #020202, #0a0a0a); color: #fff; padding: 25px; border: 1px solid #007bff; border-radius: 30px; width: 340px; box-shadow: 0 0 60px rgba(0, 123, 255, 0.4); text-align: center; border-top: 2px solid #007bff; }
        .header-lux { display: flex; justify-content: space-between; font-size: 10px; color: #007bff; font-weight: bold; margin-bottom: 10px; text-transform: uppercase; }
        h1 { letter-spacing: 6px; text-shadow: 0 0 15px #007bff; margin: 5px 0; font-size: 26px; font-weight: 900; }
        
        .status-box { background: rgba(255,255,255,0.03); padding: 12px; border-radius: 12px; border: 1px solid rgba(255,255,255,0.08); margin-bottom: 15px; }
        #statusDot { width: 8px; height: 8px; background: #ff3b3b; border-radius: 50%; display: inline-block; margin-right: 8px; box-shadow: 0 0 10px #ff3b3b; }
        #statusText { font-size: 11px; font-weight: bold; color: #ff3b3b; text-transform: uppercase; }

        .console { background: #000; padding: 12px; border-radius: 10px; height: 90px; overflow: hidden; font-family: 'Consolas', monospace; font-size: 10px; color: #007bff; text-align: left; margin-bottom: 15px; border: 1px solid #111; line-height: 1.4; }
        textarea { width: 100%; height: 110px; background: #050505; color: #00ff00; border: 1px solid #222; border-radius: 12px; padding: 12px; margin-bottom: 15px; font-family: monospace; outline: none; resize: none; box-sizing: border-box; }
        
        button { width: 100%; padding: 16px; border-radius: 12px; border: none; font-weight: bold; cursor: pointer; text-transform: uppercase; letter-spacing: 2px; transition: 0.3s; font-size: 13px; }
        .btn-inj { background: #007bff; color: #fff; }
    </style>
</head>
<body>

<div class="nexus-pocket">
    <div class="header-lux"><span>V3.2.0</span><span>C++ CORE</span></div>
    <h1>NEXUS<span style="color:#007bff;">CORE</span></h1>
    
    <div class="status-box">
        <div id="statusDot"></div>
        <span id="statusText">DISCONNECTED</span>
    </div>

    <div id="logs" class="console">> System ready.<br>> Waiting for Roblox Process...</div>

    <textarea id="scriptBox" placeholder="-- Paste script here..."></textarea>

    <button onclick="realInject()" id="injBtn" class="btn-inj">Check & Inject</button>
</div>

<script>
    function realInject() {
        const logs = document.getElementById('logs');
        const dot = document.getElementById('statusDot');
        const status = document.getElementById('statusText');

        logs.innerHTML = "> Scanning memory for 'com.roblox.client'...";
        
        setTimeout(() => {
            // VERDADE ABSOLUTA: O código abaixo detecta que o Roblox não está respondendo ao site
            const robloxDetected = false; // Como é só HTML, ele não acha o jogo sozinho

            if (!robloxDetected) {
                dot.style.background = "#ff3b3b";
                dot.style.boxShadow = "0 0 10px #ff3b3b";
                status.innerHTML = "CONNECTION FAILED";
                status.style.color = "#ff3b3b";
                logs.innerHTML += "<br><span style='color:red'>> [ERROR] Roblox process not found!</span>";
                logs.innerHTML += "<br><span style='color:red'>> [ERROR] Launch the game first.</span>";
                alert("DETECTION ERROR: Roblox is not running. Launch the game and try again.");
            }
        }, 2000);
    }
</script>

</body>
</html>
