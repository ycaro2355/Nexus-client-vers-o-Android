<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        body { background-color: #000; display: flex; justify-content: center; align-items: center; height: 100vh; margin: 0; font-family: 'Segoe UI', sans-serif; }
        .nexus-pocket { background: linear-gradient(145deg, #020202, #0a0a0a); color: #fff; padding: 25px; border: 1px solid #007bff; border-radius: 30px; width: 320px; box-shadow: 0 0 50px rgba(0, 123, 255, 0.3); text-align: center; }
        .v-tag { text-align: right; font-size: 10px; color: #007bff; font-weight: bold; letter-spacing: 2px; }
        h1 { letter-spacing: 5px; text-shadow: 0 0 15px #007bff; margin: 10px 0; font-size: 24px; }
        .status-box { background: rgba(255,255,255,0.03); padding: 12px; border-radius: 12px; border: 1px solid rgba(255,255,255,0.05); margin-bottom: 20px; }
        #statusDot { width: 8px; height: 8px; background: #ff3b3b; border-radius: 50%; display: inline-block; margin-right: 8px; box-shadow: 0 0 10px #ff3b3b; }
        #statusText { font-size: 11px; font-weight: bold; color: #eee; text-transform: uppercase; }
        #logs { background: #000; padding: 10px; border-radius: 8px; height: 70px; overflow: hidden; font-family: monospace; font-size: 10px; color: #007bff; text-align: left; margin-bottom: 15px; border: 1px solid #111; }
        textarea { width: 100%; height: 100px; background: #050505; color: #00ff00; border: 1px solid #222; border-radius: 10px; padding: 10px; margin-bottom: 20px; font-family: monospace; outline: none; resize: none; box-sizing: border-box; }
        button { width: 100%; padding: 15px; border-radius: 10px; border: none; font-weight: bold; cursor: pointer; text-transform: uppercase; letter-spacing: 2px; transition: 0.3s; }
        .btn-inj { background: #007bff; color: #fff; box-shadow: 0 5px 15px rgba(0, 123, 255, 0.4); }
        .btn-exe { background: #28a745; color: #fff; display: none; }
    </style>
</head>
<body>

<div class="nexus-pocket">
    <div class="v-tag">V3.0.1 PREMIUM</div>
    <h1>NEXUS<span style="color:#007bff;">CORE</span></h1>
    
    <div class="status-box">
        <div id="statusDot"></div>
        <span id="statusText">SCANNING PROCESS...</span>
    </div>

    <div id="logs">> Awaiting User Action...</div>

    <textarea id="scriptBox" placeholder="-- Paste Lua Script Here..."></textarea>

    <button onclick="checkAndInject()" id="injBtn" class="btn-inj">INJECT ENGINE</button>
    <button onclick="execute()" id="exeBtn" class="btn-exe">EXECUTE ON ROBLOX</button>
</div>

<script>
    // Altere para 'true' se quiser simular que o Roblox está aberto
    let isRobloxOpen = false; 

    const statusText = document.getElementById('statusText');
    const statusDot = document.getElementById('statusDot');
    const logs = document.getElementById('logs');

    function checkAndInject() {
        logs.innerHTML = "> Scanning Android Tasks...<br>> Looking for 'com.roblox.client'...";
        
        setTimeout(() => {
            if (!isRobloxOpen) {
                statusDot.style.background = "#ff3b3b";
                statusText.innerHTML = "ROBLOX NOT FOUND";
                logs.innerHTML += "<br><span style='color:red'>> [ERROR] Please open Roblox first!</span>";
                alert("FAILED: Roblox process not detected in background.");
            } else {
                statusDot.style.background = "#00ff00";
                statusDot.style.boxShadow = "0 0 15px #00ff00";
                statusText.innerHTML = "INJECTED ✅";
                statusText.style.color = "#00ff00";
                logs.innerHTML += "<br><span style='color:white'>> [SUCCESS] Nexus C++ Attached!</span>";
                document.getElementById('injBtn').style.display = "none";
                document.getElementById('exeBtn').style.display = "block";
            }
        }, 2000);
    }

    function execute() {
        logs.innerHTML += "<br>> Sending Bytecode...";
        alert("EXECUTED ✅");
    }
</script>

</body>
</html>
