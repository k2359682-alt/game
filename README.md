<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>7-Reel Ultimate Slot Game</title>
    <!-- Google AdSense Script (ແທນທີ່ ca-pub-XXXXXXXXXXXXXXXX ດ້ວຍ Pub ID ແທ້ຂອງທ່ານ) -->
    <script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js?client=ca-pub-XXXXXXXXXXXXXXXX" crossorigin="anonymous"></script>
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: #0b0c10;
            color: #fff;
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 10px;
            margin: 0;
            overflow-x: hidden;
        }

        /* Auto-Translate Widget */
        #google_translate_element {
            margin-bottom: 8px;
        }

        /* Loading Screen */
        #loadingScreen {
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            background-color: #0b0c10;
            display: flex; flex-direction: column;
            justify-content: center; align-items: center;
            z-index: 9999;
            transition: opacity 0.6s ease, visibility 0.6s;
        }
        .loading-icon { font-size: 70px; animation: bounceSpin 1.2s infinite ease-in-out; }
        @keyframes bounceSpin {
            0% { transform: scale(1) rotate(0deg); }
            50% { transform: scale(1.2) rotate(180deg); }
            100% { transform: scale(1) rotate(360deg); }
        }
        .progress-container {
            width: 250px; height: 16px; background-color: #222;
            border-radius: 10px; border: 2px solid #ffd700; overflow: hidden; margin-top: 15px;
        }
        .progress-bar { width: 0%; height: 100%; background: linear-gradient(90deg, #00e5ff, #00ff66); }

        /* Profile & Top Header Bar */
        .profile-card {
            background: #1f2833;
            border: 2px solid #45a29e;
            border-radius: 12px;
            padding: 10px 15px;
            width: 100%; max-width: 650px;
            display: flex; align-items: center; justify-content: space-between;
            box-sizing: border-box; margin-bottom: 10px;
        }
        .profile-info { display: flex; align-items: center; gap: 10px; }
        .avatar-img { font-size: 35px; background: #0b0c10; border-radius: 50%; padding: 5px; border: 2px solid #66fcf1; cursor: pointer; }
        .user-details { display: flex; flex-direction: column; }
        .username-text { font-size: 16px; font-weight: bold; color: #66fcf1; display: flex; align-items: center; gap: 5px; }
        .rank-badge { font-size: 12px; background: #ff4081; color: #fff; padding: 2px 6px; border-radius: 4px; font-weight: normal; }
        
        .stats-display { font-size: 16px; font-weight: bold; color: #ffd700; display: flex; gap: 10px; }

        /* 7-Reel Slot Container */
        .slot-container {
            display: flex; gap: 5px; background: #1f2833;
            padding: 12px; border-radius: 12px;
            box-shadow: 0 0 20px rgba(102, 252, 241, 0.2);
            border: 2px solid #66fcf1; margin-top: 5px;
            max-width: 100%; overflow-x: auto;
        }
        .reel-window {
            width: 50px; height: 60px; background: #0b0c10;
            border-radius: 6px; overflow: hidden; position: relative;
            border: 1px solid #45a29e;
        }
        .reel {
            display: flex; flex-direction: column; align-items: center;
            position: absolute; width: 100%; top: 0;
        }
        .symbol {
            width: 100%; height: 60px; font-size: 32px;
            display: flex; align-items: center; justify-content: center;
        }

        /* Controls */
        .controls { display: flex; gap: 8px; margin-top: 10px; flex-wrap: wrap; justify-content: center; }
        .spin-btn {
            padding: 10px 15px; font-size: 14px; font-weight: bold;
            background: #e50914; color: white; border: none; border-radius: 6px; cursor: pointer;
        }
        .spin-btn:disabled { background: #555 !important; cursor: not-allowed; }
        .buff-btn { background: #2e7d32; }

        /* Dashboard & Stats Section */
        .dashboard {
            background: #1f2833; border-radius: 10px; padding: 10px;
            width: 100%; max-width: 650px; margin-top: 10px; box-sizing: border-box;
            border: 1px solid #45a29e;
        }
        .stats-grid {
            display: grid; grid-template-columns: repeat(3, 1fr); gap: 6px;
            font-size: 12px; text-align: center; margin-top: 8px;
        }
        .stat-box { background: #0b0c10; padding: 6px; border-radius: 6px; border: 1px solid #333; }

        /* Leaderboard Modal / Section */
        .leaderboard-box {
            background: #0b0c10; border-radius: 8px; padding: 10px;
            max-height: 200px; overflow-y: auto; margin-top: 8px; border: 1px solid #45a29e;
        }
        .leader-row {
            display: flex; justify-content: space-between; padding: 4px 8px;
            font-size: 13px; border-bottom: 1px solid #222;
        }
        .leader-row.my-rank { background: rgba(102, 252, 241, 0.2); font-weight: bold; color: #66fcf1; }

        /* Real Google Ads Container */
        .ad-banner-container {
            width: 100%; max-width: 650px; margin: 15px 0; text-align: center;
            background: #1a1a1a; border: 1px dashed #555; padding: 5px; border-radius: 8px;
        }

        /* Modal Popup */
        .modal {
            display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(0,0,0,0.85); justify-content: center; align-items: center; z-index: 100;
        }
        .modal-content {
            background: #1f2833; padding: 20px; border-radius: 10px; border: 2px solid #66fcf1;
            width: 300px; text-align: center; color: #fff;
        }
        .modal-content input {
            width: 90%; padding: 8px; margin: 10px 0; border-radius: 5px; border: 1px solid #45a29e;
            background: #0b0c10; color: #fff; text-align: center;
        }
        .avatar-picker { display: flex; justify-content: center; gap: 10px; margin-bottom: 10px; font-size: 28px; }
        .avatar-option { cursor: pointer; border: 2px solid transparent; border-radius: 50%; padding: 2px; }
        .avatar-option.selected { border-color: #66fcf1; }
    </style>
</head>
<body>

    <!-- Google Auto Translate -->
    <div id="google_translate_element"></div>

    <!-- Loading Screen -->
    <div id="loadingScreen">
        <div class="loading-icon">🎰</div>
        <h3 style="color: #66fcf1;">Loading 7-Reel Slot Game...</h3>
        <div class="progress-container"><div class="progress-bar" id="progressBar"></div></div>
        <div id="loadingText" style="margin-top: 5px; color: #00ff66;">0%</div>
    </div>

    <!-- Top Profile & Stats Bar -->
    <div class="profile-card">
        <div class="profile-info">
            <div class="avatar-img" id="userAvatarDisplay" onclick="openProfileModal()">😎</div>
            <div class="user-details">
                <div class="username-text">
                    <span id="userNameDisplay">Player1</span> ✏️
                </div>
                <div><span class="rank-badge" id="myRankDisplay">World Rank: #--</span></div>
            </div>
        </div>
        <div class="stats-display">
            <span>💎 <span id="gemsCount">100</span></span>
            <span>🍀 <span id="luckCount">0</span></span>
        </div>
    </div>

    <!-- Real Google AdSense Banner (Top) -->
    <div class="ad-banner-container">
        <ins class="adsbygoogle"
             style="display:block"
             data-ad-client="ca-pub-XXXXXXXXXXXXXXXX"
             data-ad-slot="1234567890"
             data-ad-format="auto"
             data-full-width-responsive="true"></ins>
        <script>(adsbygoogle = window.adsbygoogle || []).push({});</script>
    </div>

    <h2 style="margin: 5px 0; color: #ffd700;">🎰 7-Reel Slot Game 🎰</h2>

    <!-- 7-Reel Slot Machine -->
    <div class="slot-container">
        <div class="reel-window"><div class="reel" id="reel0"></div></div>
        <div class="reel-window"><div class="reel" id="reel1"></div></div>
        <div class="reel-window"><div class="reel" id="reel2"></div></div>
        <div class="reel-window"><div class="reel" id="reel3"></div></div>
        <div class="reel-window"><div class="reel" id="reel4"></div></div>
        <div class="reel-window"><div class="reel" id="reel5"></div></div>
        <div class="reel-window"><div class="reel" id="reel6"></div></div>
    </div>

    <div id="buffStatus" style="height:20px; color:#00ff66; margin-top:5px; font-weight:bold;"></div>

    <!-- Controls -->
    <div class="controls">
        <button class="spin-btn" id="spin1Btn" onclick="spin(1)">Spin 1x (10 💎)</button>
        <button class="spin-btn" id="spin10Btn" onclick="spin(10)">Spin 10x (90 💎)</button>
        <button class="spin-btn buff-btn" id="useLuckBtn" onclick="useLuckBuff()">Luck Buff 🍀</button>
        <button class="spin-btn" style="background: #2196F3;" onclick="watchAdReward()">📺 Ad (+20 💎)</button>
    </div>

    <div id="result" style="margin-top: 8px; font-size: 16px; font-weight: bold; color: #66fcf1; height: 22px;"></div>

    <!-- Win Rate Statistics & Dashboard -->
    <div class="dashboard">
        <h4 style="margin: 0; color: #ffd700;">📊 Win Rates & Match Statistics</h4>
        <div class="stats-grid">
            <div class="stat-box">7 Match (1%): <b id="m7">0</b></div>
            <div class="stat-box">6 Match (3%): <b id="m6">0</b></div>
            <div class="stat-box">5 Match (4%): <b id="m5">0</b></div>
            <div class="stat-box">4 Match (5%): <b id="m4">0</b></div>
            <div class="stat-box">3 Match (8%): <b id="m3">0</b></div>
            <div class="stat-box">2 Match (10%): <b id="m2">0</b></div>
        </div>
        <div style="text-align: center; margin-top: 6px; font-size: 13px; color: #aaa;">
            Total Spins: <span id="totalSpins">0</span> | Win Rate: <span id="winRateVal" style="color:#00ff66;">0%</span>
        </div>
    </div>

    <!-- Global Leaderboard (Top 1 - 100) -->
    <div class="dashboard">
        <h4 style="margin: 0 0 6px 0; color: #ffd700;">🏆 Global Leaderboard (Top 100)</h4>
        <div class="leaderboard-box" id="leaderboardList">
            <!-- Dynamic Leaderboard Content -->
        </div>
    </div>

    <!-- Profile Edit Modal -->
    <div class="modal" id="profileModal">
        <div class="modal-content">
            <h3>Edit Profile</h3>
            <p style="font-size: 12px; color: #aaa;">Choose Avatar & Set Unique Name</p>
            <div class="avatar-picker">
                <span class="avatar-option" onclick="selectAvatar('😎')">😎</span>
                <span class="avatar-option" onclick="selectAvatar('🙀')">🙀</span>
                <span class="avatar-option" onclick="selectAvatar('🤑')">🤑</span>
                <span class="avatar-option" onclick="selectAvatar('🦦')">🦦</span>
            </div>
            <input type="text" id="usernameInput" placeholder="Enter unique username..." maxlength="12">
            <button class="spin-btn" style="background: #45a29e; width: 100%;" onclick="saveProfile()">Save Profile</button>
        </div>
    </div>

    <!-- Google Translate Script -->
    <script type="text/javascript">
        function googleTranslateElementInit() {
            new google.translate.TranslateElement({
                pageLanguage: 'en',
                layout: google.translate.TranslateElement.InlineLayout.SIMPLE
            }, 'google_translate_element');
        }
    </script>
    <script type="text/javascript" src="//translate.google.com/translate_a/element.js?cb=googleTranslateElementInit"></script>

    <script>
        // --- Game Setup & 10 Emojis ---
        const symbols = ['😲', '⌚', '🦦', '🤑', '♟️', '🍕', '❤️', '🦽', '🙀', '😎'];
        const reelElements = [0,1,2,3,4,5,6].map(i => document.getElementById(`reel${i}`));

        // Saved Data Keys
        let gems = parseInt(localStorage.getItem('slot_gems')) || 100;
        let luckItems = parseInt(localStorage.getItem('slot_luck')) || 0;
        let userName = localStorage.getItem('slot_username') || "Player_" + Math.floor(1000 + Math.random() * 9000);
        let userAvatar = localStorage.getItem('slot_avatar') || "😎";
        let selectedTempAvatar = userAvatar;

        // Statistics Storage
        let matchStats = JSON.parse(localStorage.getItem('slot_stats')) || { m7: 0, m6: 0, m5: 0, m4: 0, m3: 0, m2: 0, spins: 0 };

        // Registered Names Database (Simulated Unique Usernames)
        let takenNames = new Set(["Admin", "Kongkham", "ProPlayer", "KingSlot", "Lucky777"]);

        // Loading Screen Animation
        window.addEventListener('load', () => {
            let progress = 0;
            const interval = setInterval(() => {
                progress += Math.floor(Math.random() * 15) + 5;
                if (progress > 100) progress = 100;
                document.getElementById('progressBar').style.width = `${progress}%`;
                document.getElementById('loadingText').innerText = `${progress}%`;
                if (progress >= 100) {
                    clearInterval(interval);
                    setTimeout(() => {
                        document.getElementById('loadingScreen').style.opacity = '0';
                        document.getElementById('loadingScreen').style.visibility = 'hidden';
                    }, 300);
                }
            }, 60);
        });

        // Initialize Reel Symbols
        reelElements.forEach(r => r.innerHTML = `<div class="symbol">${symbols[0]}</div>`);
        updateUI();
        renderLeaderboard();

        function updateUI() {
            document.getElementById('gemsCount').innerText = gems;
            document.getElementById('luckCount').innerText = luckItems;
            document.getElementById('userNameDisplay').innerText = userName;
            document.getElementById('userAvatarDisplay').innerText = userAvatar;

            document.getElementById('spin1Btn').disabled = gems < 10;
            document.getElementById('spin10Btn').disabled = gems < 90;
            document.getElementById('useLuckBtn').disabled = luckItems <= 0;

            // Stats Update
            document.getElementById('m7').innerText = matchStats.m7;
            document.getElementById('m6').innerText = matchStats.m6;
            document.getElementById('m5').innerText = matchStats.m5;
            document.getElementById('m4').innerText = matchStats.m4;
            document.getElementById('m3').innerText = matchStats.m3;
            document.getElementById('m2').innerText = matchStats.m2;
            document.getElementById('totalSpins').innerText = matchStats.spins;

            const totalWins = matchStats.m7 + matchStats.m6 + matchStats.m5 + matchStats.m4 + matchStats.m3 + matchStats.m2;
            const rate = matchStats.spins > 0 ? ((totalWins / matchStats.spins) * 100).toFixed(1) : 0;
            document.getElementById('winRateVal').innerText = `${rate}%`;

            // Save to LocalStorage
            localStorage.setItem('slot_gems', gems);
            localStorage.setItem('slot_luck', luckItems);
            localStorage.setItem('slot_username', userName);
            localStorage.setItem('slot_avatar', userAvatar);
            localStorage.setItem('slot_stats', JSON.stringify(matchStats));
        }

        // --- Custom Win Rate Logic ---
        function generateOutcome() {
            const rand = Math.random() * 100;
            let matchType = 0;

            // Specified Win Probabilities: 7=1%, 6=3%, 5=4%, 4=5%, 3=8%, 2=10%
            if (rand < 1) matchType = 7;
            else if (rand < 1 + 3) matchType = 6;
            else if (rand < 1 + 3 + 4) matchType = 5;
            else if (rand < 1 + 3 + 4 + 5) matchType = 4;
            else if (rand < 1 + 3 + 4 + 5 + 8) matchType = 3;
            else if (rand < 1 + 3 + 4 + 5 + 8 + 10) matchType = 2;
            else matchType = 0;

            let res = Array(7).fill('');
            const mainSym = symbols[Math.floor(Math.random() * symbols.length)];

            if (matchType > 0) {
                // Fill target matches
                for (let i = 0; i < matchType; i++) res[i] = mainSym;
                // Fill remaining with random non-matching symbols
                for (let i = matchType; i < 7; i++) {
                    let other = symbols[Math.floor(Math.random() * symbols.length)];
                    while (other === mainSym) other = symbols[Math.floor(Math.random() * symbols.length)];
                    res[i] = other;
                }
                // Shuffle symbols
                res.sort(() => Math.random() - 0.5);
            } else {
                for (let i = 0; i < 7; i++) res[i] = symbols[Math.floor(Math.random() * symbols.length)];
            }

            return { finalSymbols: res, matchType: matchType };
        }

        // --- Spin Mechanics ---
        async function spin(times) {
            const cost = times === 1 ? 10 : 90;
            if (gems < cost) return;

            gems -= cost;
            updateUI();
            document.getElementById('spin1Btn').disabled = true;
            document.getElementById('spin10Btn').disabled = true;

            let totalReward = 0;
            // Optimized Spin Duration for Fast 10x Spin
            const animDuration = times === 10 ? 300 : 800;

            for (let t = 0; t < times; t++) {
                document.getElementById('result').innerText = `Spinning... (${t + 1}/${times})`;
                const outcome = generateOutcome();
                matchStats.spins++;

                await animateSpin(outcome.finalSymbols, animDuration);

                // Specific Rewards based on matches
                if (outcome.matchType === 7) { totalReward += 200; matchStats.m7++; }
                else if (outcome.matchType === 6) { totalReward += 150; matchStats.m6++; }
                else if (outcome.matchType === 5) { totalReward += 120; matchStats.m5++; }
                else if (outcome.matchType === 4) { totalReward += 100; matchStats.m4++; }
                else if (outcome.matchType === 3) { totalReward += 75; matchStats.m3++; }
                else if (outcome.matchType === 2) { totalReward += 50; matchStats.m2++; }
            }

            gems += totalReward;
            updateUI();
            renderLeaderboard();

            document.getElementById('result').innerText = totalReward > 0 ? 
                `🎉 Total Win: +${totalReward} 💎!` : `❌ No match, try again!`;
        }

        function animateSpin(finalSymbols, speed) {
            return new Promise(resolve => {
                reelElements.forEach((reel, index) => {
                    let strip = '';
                    for (let i = 0; i < 6; i++) {
                        strip += `<div class="symbol">${symbols[Math.floor(Math.random()*symbols.length)]}</div>`;
                    }
                    strip += `<div class="symbol">${finalSymbols[index]}</div>`;
                    reel.innerHTML = strip;
                    reel.style.transition = 'none';
                    reel.style.top = '0px';

                    setTimeout(() => {
                        reel.style.transition = `top ${speed / 1000}s cubic-bezier(0.1, 0.9, 0.2, 1)`;
                        reel.style.top = `-${6 * 60}px`;
                    }, 20);
                });
                setTimeout(resolve, speed + 50);
            });
        }

        // --- Leaderboard System (Top 100 & My Rank) ---
        function renderLeaderboard() {
            const listEl = document.getElementById('leaderboardList');
            listEl.innerHTML = '';

            // Generate Simulated World Players
            let worldPlayers = [
                { name: userName, gems: gems, avatar: userAvatar, isMe: true },
                { name: "Kongkham_VIP", gems: 15400, avatar: "😎" },
                { name: "SlotMaster", gems: 12100, avatar: "🤑" },
                { name: "LuckyCat", gems: 9800, avatar: "🙀" },
                { name: "OtterKing", gems: 8500, avatar: "🦦" }
            ];

            for (let i = 6; i <= 100; i++) {
                worldPlayers.push({
                    name: `Player_${1000 + i}`,
                    gems: Math.floor(7000 - (i * 65) + Math.random() * 50),
                    avatar: symbols[i % symbols.length],
                    isMe: false
                });
            }

            // Sort Players by Gems
            worldPlayers.sort((a, b) => b.gems - a.gems);

            let myRank = 0;
            worldPlayers.forEach((player, index) => {
                const rank = index + 1;
                if (player.isMe) myRank = rank;

                // Render Top 100 Items
                const row = document.createElement('div');
                row.className = `leader-row ${player.isMe ? 'my-rank' : ''}`;
                row.innerHTML = `
                    <span><b>#${rank}</b> ${player.avatar} ${player.name}</span>
                    <span>💎 ${player.gems}</span>
                `;
                listEl.appendChild(row);
            });

            document.getElementById('myRankDisplay').innerText = `World Rank: #${myRank}`;
        }

        // --- Profile Edit & Unique Name Check ---
        function openProfileModal() {
            document.getElementById('usernameInput').value = userName;
            document.getElementById('profileModal').style.display = 'flex';
        }

        function selectAvatar(emoji) {
            selectedTempAvatar = emoji;
        }

        function saveProfile() {
            const newName = document.getElementById('usernameInput').value.trim();
            
            if (!newName) {
                alert("Please enter a valid name!");
                return;
            }

            if (newName !== userName && takenNames.has(newName)) {
                alert("❌ Username already taken! Choose another one.");
                return;
            }

            takenNames.delete(userName);
            userName = newName;
            takenNames.add(userName);
            userAvatar = selectedTempAvatar;

            updateUI();
            renderLeaderboard();
            document.getElementById('profileModal').style.display = 'none';
            alert("✅ Profile updated successfully!");
        }

        function useLuckBuff() {
            if (luckItems <= 0) return;
            luckItems--;
            updateUI();
            alert("🍀 Luck Buff activated!");
        }

        function watchAdReward() {
            alert("📺 Google Ad Playing... You earned +20 💎!");
            gems += 20;
            updateUI();
            renderLeaderboard();
        }
    </script>
</body>
</html>
