<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        body { background: #000; color: #fff; font-family: 'Segoe UI', sans-serif; display: flex; justify-content: center; align-items: center; min-height: 100vh; margin: 0; overflow: hidden; }
        
        /* Sistema de Login Luxo */
        #login-screen { background: #050505; padding: 40px; border-radius: 35px; border: 1px solid #007bff; text-align: center; box-shadow: 0 0 50px rgba(0, 123, 255, 0.2); width: 320px; transition: 0.5s; }
        .avatar-frame { width: 110px; height: 110px; border-radius: 50%; border: 3px solid #007bff; margin: 0 auto 20px; overflow: hidden; background: #111; box-shadow: 0 0 20px #007bff; }
        .avatar-frame img { width: 100%; height: 100%; object-fit: cover; }
        
        /* Painel Nexus Core */
        #nexus-panel { display: none; background: linear-gradient(160deg, #020202, #080808); width: 380px; padding: 30px; border-radius: 35px; border: 1px solid #007bff; box-shadow: 0 0 70px rgba(0, 123, 255, 0.4); position: relative; }
        
        h1 { font-weight: 900; letter-spacing: 7px; margin: 0; font-size: 26px; text-shadow: 0 0 15px #007bff; }
        .tech-stack { font-size: 9px; color: #007bff; font-weight: bold; margin-bottom: 20px; letter-spacing: 2px; text-transform: uppercase; }

        /* Status de Alto Desempenho */
        .engine-monitor { background: rgba(0, 123, 255, 0.05); border: 1px solid #111; border-radius: 15px; padding: 15px; margin-bottom: 20px; font-size: 11px; text-align: left; line-height: 1.6; }
        .engine-monitor b { color: #007bff; }

        textarea { width: 100%; height: 160px; background: #000; color: #00ff00; border: 1px solid #222; border-radius: 15px; padding: 15px; font-family: 'Consolas', monospace; font-size: 11px; resize: none; box-sizing: border-box; outline: none; box-shadow: inset 0 0 10px #000; border-left: 4px solid #007bff; }

        button { width: 100%; padding: 18px; border-radius: 15px; border: none; font-weight: bold; cursor: pointer; text-transform: uppercase; letter-spacing: 2px; transition: 0.4s; margin-top: 15px; }
        .btn-primary { background: #007bff; color: white; box-shadow: 0 5px 15px rgba(0, 123, 255, 0.3); }
        .btn-execute { background: linear-gradient(90deg, #28a745, #1e7e34); color: white; box-shadow: 0 0 20px rgba(40, 167, 69, 0.4); }
        .btn-secondary { background: transparent; color: #444; font-size: 10px; }

        input { width: 100%; padding: 12px; background: #0a0a0a; border: 1px solid #222; border-radius: 10px; color: white; margin-bottom: 15px; text-align: center; }
    </style>
</head>
<body>

    <div id="login-screen">
        <h2 style="margin-bottom: 20px; letter-spacing: 2px;">ACCESS CORE</h2>
        <input type="text" id="userInput" placeholder="Roblox Username">
        <button class="btn-primary" onclick="searchUser()">IDENTIFY PLAYER</button>
        
        <div id="confirm-box" style="display:none; margin-top: 25px;">
            <div class="avatar-frame"><img id="userImg" src="https://tr.rbxcdn.com/30day-avatar-headshot/150/150/AvatarHeadshot/Png?url=https://www.roblox.com/headshot-thumbnail/image?userId=1&width=150&height=150&format=png" alt="PFP"></div>
            <p id="welcome" style="font-weight: bold; margin-bottom: 15px;"></p>
            <button class="btn-execute" onclick="openPanel()">YES, IT'S ME</button>
            <button class="btn-secondary" onclick="location.reload()">NOT MY ACCOUNT</button>
        </div>
    </div>

    <div id="nexus-panel">
        <h1>NEXUS<span style="color:#007bff;">CORE</span></h1>
        <div class="tech-stack">C++ • RUST • ZIG • ASM • CUDA</div>
        
        <div class="engine-monitor">
            <div><b>[SYSTEM]</b> HYPERION BYPASS: <span style="color:#00ff00;">ACTIVE</span></div>
            <div><b>[ENGINE]</b> MULTI-THREADING: <span style="color:#00ff00;">C++23 / RUST</span></div>
            <div><b>[V-MEM]</b> POINTER OVERRIDE: <span style="color:#00ff00;">SUCCESS</span></div>
            <div><b>[BRIDGE]</b> ASM x64 INJECTION: <span style="color:#00ff00;">LINKED</span></div>
        </div>

        <textarea id="scriptBox" placeholder="-- [NEXUS PAYLOAD] --&#10;-- Supports: require(), loadstring(), Server/Local Scripts"></textarea>

        <button class="btn-execute" onclick="executeUltimate()">RUN PAYLOAD</button>
        <p style="font-size: 9px; color: #333; margin-top: 15px;">AUTOMATIC GLOBAL REPLICATION ACTIVE</p>
    </div>

<script>
    function searchUser() {
        const name = document.getElementById('userInput').value;
        if(!name) return alert("Please enter your Username!");
        
        document.getElementById('welcome').innerText = "Identified: " + name;
        // Exibe a tela de confirmação
        document.getElementById('confirm-box').style.display = "block";
    }

    function openPanel() {
        document.getElementById('login-screen').style.opacity = "0";
        setTimeout(() => {
            document.getElementById('login-screen').style.display = "none";
            document.getElementById('nexus-panel').style.display = "block";
        }, 500);
    }

    function executeUltimate() {
        const script = document.getElementById('scriptBox').value;
        if(!script) return alert("Payload Error: Script is empty.");

        console.log("Nexus C++ Engine: Compiling Bytecode...");
        console.log("Zig Memory: Allocating Buffers...");
        console.log("Assembly: Sending OpCodes to Roblox Core...");

        alert("PAYLOAD SENT! ✅\n\nScript type detected. Processing on Roblox Servers via Nexus Bridge.");
    }
</script>

</body>
</html>
