<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
    <title>Sanjay · Java Backend Engineer | Real-Time Profile</title>
    <!-- Google Fonts + Tailwind + FontAwesome + GSAP -->
    <link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500;600;700&display=swap" rel="stylesheet">
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.5/gsap.min.js"></script>
    <style>
        * { font-family: 'JetBrains Mono', monospace; transition: background 0.3s, color 0.2s, border-color 0.2s; }
        body {
            background: linear-gradient(135deg, #0f172a 0%, #1e293b 100%);
            background-attachment: fixed;
        }
        body.light {
            background: linear-gradient(135deg, #f8fafc 0%, #e2e8f0 100%);
        }
        .glass-card {
            background: rgba(15, 23, 42, 0.6);
            backdrop-filter: blur(12px);
            border: 1px solid rgba(0, 255, 204, 0.2);
            border-radius: 2rem;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        .glass-card:hover {
            transform: translateY(-6px);
            box-shadow: 0 20px 35px -15px rgba(0, 255, 204, 0.3);
            border-color: #00ffcc;
        }
        body.light .glass-card {
            background: rgba(255, 255, 255, 0.7);
            border-color: #00b894;
        }
        .glow-text {
            text-shadow: 0 0 6px #00ffcc80;
        }
        .skill-icon {
            transition: all 0.25s ease;
            display: inline-block;
        }
        .skill-icon:hover {
            transform: scale(1.15) translateY(-5px);
            filter: drop-shadow(0 0 8px #00ffcc);
        }
        .animate-pulse-slow {
            animation: pulse 2s cubic-bezier(0.4, 0, 0.6, 1) infinite;
        }
        @keyframes fadeUp {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        .fade-up {
            animation: fadeUp 0.6s ease forwards;
        }
        .contribution-cell {
            background-color: #1e293b;
            border-radius: 3px;
        }
        body.light .contribution-cell {
            background-color: #cbd5e1;
        }
        .tooltip {
            position: relative;
        }
        .tooltip:hover::after {
            content: attr(data-tooltip);
            position: absolute;
            bottom: 100%;
            left: 50%;
            transform: translateX(-50%);
            background: #0f172a;
            color: #00ffcc;
            padding: 4px 8px;
            border-radius: 8px;
            font-size: 12px;
            white-space: nowrap;
            z-index: 10;
        }
    </style>
</head>
<body class="text-gray-200 antialiased">
    <div class="container max-w-6xl mx-auto px-4 py-8 md:py-12">
        <!-- Header Section -->
        <div class="text-center fade-up">
            <h1 class="text-4xl md:text-6xl font-bold bg-gradient-to-r from-cyan-300 to-teal-400 bg-clip-text text-transparent">Hi 👋, I'm <span class="text-[#00FFCC]">Sanjay</span></h1>
            <p class="text-lg md:text-xl mt-3 text-gray-300">A Passionate Java Backend Developer who Crafts Code with ❤️.</p>
            <div class="mt-4">
                <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&size=22&pause=1000&color=00FFCC&center=true&vCenter=true&width=600&height=45&lines=Java+%7C+Spring+Boot+%7C+Microservices;Docker+%7C+Kafka+%7C+Clean+Architecture;Cloud+Ready+Scalable+Apps" alt="Typing SVG" class="mx-auto">
            </div>
        </div>

        <!-- Theme Toggle + Refresh Row -->
        <div class="flex justify-end items-center gap-4 mt-6 mb-8">
            <button id="refreshBtn" class="bg-cyan-800/40 hover:bg-cyan-700/60 px-4 py-2 rounded-full text-sm flex items-center gap-2 backdrop-blur-sm transition"><i class="fas fa-sync-alt"></i> Refresh</button>
            <button id="themeToggle" class="bg-slate-700/50 hover:bg-slate-600/60 px-4 py-2 rounded-full text-sm flex items-center gap-2 backdrop-blur-sm"><i class="fas fa-moon"></i> Dark/Light</button>
        </div>

        <!-- Stats Grid: GitHub + LeetCode + GFG -->
        <div class="grid grid-cols-1 md:grid-cols-3 gap-6 mb-12">
            <!-- GitHub Card -->
            <div class="glass-card p-6 fade-up" style="animation-delay: 0.1s;">
                <div class="flex items-center gap-3 border-b border-cyan-500/30 pb-3 mb-4">
                    <i class="fab fa-github text-3xl text-cyan-400"></i>
                    <h2 class="text-2xl font-bold">GitHub</h2>
                </div>
                <div id="githubStats" class="space-y-2 text-sm">
                    <div class="flex justify-between"><span>📦 Repos:</span><span id="repoCount" class="font-mono">--</span></div>
                    <div class="flex justify-between"><span>⭐ Total Stars:</span><span id="starCount" class="font-mono">--</span></div>
                    <div class="flex justify-between"><span>👥 Followers:</span><span id="followers" class="font-mono">--</span></div>
                    <div class="flex justify-between"><span>👤 Following:</span><span id="following" class="font-mono">--</span></div>
                    <div class="mt-3 pt-2 border-t border-gray-600/40"><span class="text-xs uppercase tracking-wide">🕒 Recent commits</span>
                        <ul id="recentCommits" class="mt-2 space-y-1 text-xs max-h-32 overflow-y-auto"></ul>
                    </div>
                </div>
                <div class="mt-4 text-center text-[10px] text-gray-400" id="githubUpdateTime"></div>
            </div>

            <!-- LeetCode Card -->
            <div class="glass-card p-6 fade-up" style="animation-delay: 0.2s;">
                <div class="flex items-center gap-3 border-b border-cyan-500/30 pb-3 mb-4">
                    <i class="fab fa-leetcode text-3xl text-orange-400"></i>
                    <h2 class="text-2xl font-bold">LeetCode</h2>
                </div>
                <div id="leetcodeStats">
                    <div class="flex justify-between"><span>✅ Total Solved:</span><span id="totalSolved" class="font-mono">--</span></div>
                    <div class="flex justify-between text-green-400"><span>Easy:</span><span id="easySolved" class="font-mono">--</span></div>
                    <div class="flex justify-between text-yellow-400"><span>Medium:</span><span id="mediumSolved" class="font-mono">--</span></div>
                    <div class="flex justify-between text-red-400"><span>Hard:</span><span id="hardSolved" class="font-mono">--</span></div>
                    <div class="flex justify-between"><span>🏆 Ranking:</span><span id="ranking" class="font-mono">--</span></div>
                </div>
            </div>

            <!-- GFG Card -->
            <div class="glass-card p-6 fade-up" style="animation-delay: 0.3s;">
                <div class="flex items-center gap-3 border-b border-cyan-500/30 pb-3 mb-4">
                    <i class="fas fa-code text-3xl text-emerald-400"></i>
                    <h2 class="text-2xl font-bold">GeeksforGeeks</h2>
                </div>
                <div id="gfgStats">
                    <div class="flex justify-between"><span>📝 Problems Solved:</span><span id="gfgSolved" class="font-mono">--</span></div>
                    <div class="flex justify-between"><span>⚡ Coding Score:</span><span id="gfgScore" class="font-mono">--</span></div>
                    <div class="flex justify-between"><span>📈 Rank:</span><span id="gfgRank" class="font-mono">--</span></div>
                </div>
            </div>
        </div>

        <!-- Tech Stack (Animated) -->
        <div class="glass-card p-6 mb-12 fade-up" style="animation-delay: 0.4s;">
            <h2 class="text-2xl font-bold text-center mb-6"><i class="fas fa-microchip"></i> Tech Stack</h2>
            <div class="flex flex-wrap justify-center gap-4 text-4xl md:text-5xl">
                <i class="fab fa-java skill-icon text-[#ED8B00] tooltip" data-tooltip="Java"></i>
                <i class="fas fa-leaf skill-icon text-[#6DB33F] tooltip" data-tooltip="Spring Boot"></i>
                <i class="fab fa-docker skill-icon text-[#2496ED] tooltip" data-tooltip="Docker"></i>
                <i class="fab fa-apache skill-icon text-[#231F20] tooltip" data-tooltip="Kafka"></i>
                <i class="fas fa-database skill-icon text-[#00758F] tooltip" data-tooltip="MySQL"></i>
                <i class="fas fa-cloud-upload-alt skill-icon text-[#FF9900] tooltip" data-tooltip="AWS"></i>
                <i class="fab fa-git-alt skill-icon text-[#F05032] tooltip" data-tooltip="Git"></i>
                <i class="fas fa-tools skill-icon text-[#FF6C37] tooltip" data-tooltip="Postman"></i>
            </div>
        </div>

        <!-- Contribution Heatmap (simulated with GitHub events style) -->
        <div class="glass-card p-6 mb-12 fade-up" style="animation-delay: 0.5s;">
            <h2 class="text-xl font-bold mb-3"><i class="fas fa-calendar-alt"></i> Contribution Activity (last 30 days)</h2>
            <div id="heatmap" class="grid grid-cols-7 gap-1.5 mt-3"></div>
            <div class="text-right text-xs text-gray-400 mt-2">based on recent GitHub events</div>
        </div>

        <!-- Footer / Connect -->
        <div class="text-center pt-4 fade-up">
            <div class="flex justify-center gap-5 text-2xl mb-4">
                <a href="mailto:devjava.sanjay@gmail.com" class="hover:text-cyan-400 transition"><i class="fas fa-envelope"></i></a>
                <a href="https://www.linkedin.com/in/sanjayjavadev" target="_blank" class="hover:text-cyan-400 transition"><i class="fab fa-linkedin"></i></a>
                <a href="https://github.com/Sanjay-119-super" target="_blank" class="hover:text-cyan-400 transition"><i class="fab fa-github"></i></a>
                <a href="https://x.com/SanjayJava6006" target="_blank" class="hover:text-cyan-400 transition"><i class="fab fa-twitter"></i></a>
            </div>
            <p class="text-xs text-gray-400">⚡ Real-time updates every 60 sec • Last fetched: <span id="lastFetchTime">--</span></p>
            <img src="https://capsule-render.vercel.app/api?type=waving&color=00FFCC&height=100&section=footer" class="w-full mt-6 opacity-80">
        </div>
    </div>

    <script>
        // ---------- CONFIGURATION ----------
        const GITHUB_USER = "Sanjay-119-super";   // ✅ your GitHub
        const LEETCODE_USER = "Sanjay119";        // 🔁 change to your actual LeetCode ID or keep as is (will fallback)
        const GFG_USER = "sanjay119";              // 🔁 change to your GFG username

        // DOM elements
        const repoCountSpan = document.getElementById('repoCount');
        const starCountSpan = document.getElementById('starCount');
        const followersSpan = document.getElementById('followers');
        const followingSpan = document.getElementById('following');
        const recentCommitsList = document.getElementById('recentCommits');
        const githubUpdateSpan = document.getElementById('githubUpdateTime');
        const totalSolvedSpan = document.getElementById('totalSolved');
        const easySolvedSpan = document.getElementById('easySolved');
        const mediumSolvedSpan = document.getElementById('mediumSolved');
        const hardSolvedSpan = document.getElementById('hardSolved');
        const rankingSpan = document.getElementById('ranking');
        const gfgSolvedSpan = document.getElementById('gfgSolved');
        const gfgScoreSpan = document.getElementById('gfgScore');
        const gfgRankSpan = document.getElementById('gfgRank');
        const lastFetchSpan = document.getElementById('lastFetchTime');
        const heatmapDiv = document.getElementById('heatmap');

        // Helper: format time
        function updateLastFetchTime() {
            const now = new Date();
            lastFetchSpan.innerText = now.toLocaleTimeString();
        }

        // ---------- 1. GitHub stats + recent commits + contribution heatmap ----------
        async function fetchGitHubStats() {
            try {
                // user data
                const userRes = await fetch(`https://api.github.com/users/${GITHUB_USER}`);
                const userData = await userRes.json();
                if (userData.login) {
                    followersSpan.innerText = userData.followers ?? 0;
                    followingSpan.innerText = userData.following ?? 0;
                }
                // repos for stars
                const reposRes = await fetch(`https://api.github.com/users/${GITHUB_USER}/repos?per_page=100`);
                const repos = await reposRes.json();
                let totalStars = 0;
                if (Array.isArray(repos)) {
                    totalStars = repos.reduce((acc, repo) => acc + (repo.stargazers_count || 0), 0);
                    repoCountSpan.innerText = repos.length;
                    starCountSpan.innerText = totalStars;
                }
                // recent events (commits)
                const eventsRes = await fetch(`https://api.github.com/users/${GITHUB_USER}/events/public`);
                const events = await eventsRes.json();
                if (Array.isArray(events)) {
                    const pushEvents = events.filter(e => e.type === 'PushEvent').slice(0, 5);
                    recentCommitsList.innerHTML = pushEvents.map(e => {
                        const repoName = e.repo.name.split('/')[1];
                        const commitMsg = e.payload.commits?.[0]?.message || 'commit';
                        const shortMsg = commitMsg.length > 40 ? commitMsg.slice(0,40)+'...' : commitMsg;
                        return `<li class="truncate"><span class="text-cyan-300">📌 ${repoName}</span> – ${shortMsg}</li>`;
                    }).join('');
                    if(pushEvents.length === 0) recentCommitsList.innerHTML = '<li>No recent commits found</li>';
                }
                // Build heatmap (last 30 days based on push dates)
                if (Array.isArray(events)) {
                    const pushDates = events.filter(e => e.type === 'PushEvent').map(e => e.created_at.split('T')[0]);
                    const dateCount = new Map();
                    pushDates.forEach(d => dateCount.set(d, (dateCount.get(d)||0)+1));
                    const today = new Date();
                    const heatmapHTML = [];
                    for (let i = 29; i >= 0; i--) {
                        const d = new Date(today);
                        d.setDate(today.getDate() - i);
                        const dateStr = d.toISOString().split('T')[0];
                        const count = dateCount.get(dateStr) || 0;
                        let intensity = 'bg-gray-600/30';
                        if (count > 0) intensity = 'bg-green-400/70';
                        if (count > 2) intensity = 'bg-green-500';
                        if (count > 4) intensity = 'bg-green-600';
                        heatmapHTML.push(`<div class="w-7 h-7 rounded ${intensity} tooltip" data-tooltip="${dateStr}: ${count} commits"></div>`);
                    }
                    heatmapDiv.innerHTML = heatmapHTML.join('');
                } else {
                    heatmapDiv.innerHTML = '<div class="col-span-7 text-center">No contribution data</div>';
                }
                githubUpdateSpan.innerText = `last sync: ${new Date().toLocaleTimeString()}`;
            } catch (err) {
                console.warn("GitHub API error", err);
                repoCountSpan.innerText = "❌ error";
            }
        }

        // ---------- 2. LeetCode stats (via unofficial api) ----------
        async function fetchLeetCodeStats() {
            try {
                const response = await fetch(`https://leetcode-stats-api.herokuapp.com/${LEETCODE_USER}`);
                if (!response.ok) throw new Error('LC API fail');
                const data = await response.json();
                if (data.status === "success") {
                    totalSolvedSpan.innerText = data.totalSolved ?? 0;
                    easySolvedSpan.innerText = data.easySolved ?? 0;
                    mediumSolvedSpan.innerText = data.mediumSolved ?? 0;
                    hardSolvedSpan.innerText = data.hardSolved ?? 0;
                    rankingSpan.innerText = data.ranking ? `#${data.ranking}` : 'N/A';
                } else {
                    throw new Error('invalid user');
                }
            } catch (err) {
                totalSolvedSpan.innerText = "unavailable";
                easySolvedSpan.innerText = "—";
                mediumSolvedSpan.innerText = "—";
                hardSolvedSpan.innerText = "—";
                rankingSpan.innerText = "—";
            }
        }

        // ---------- 3. GFG stats (public proxy) ----------
        async function fetchGFGStats() {
            try {
                const proxyUrl = `https://geeks-for-geeks-stats-api.vercel.app/?username=${GFG_USER}`;
                const res = await fetch(proxyUrl);
                if (!res.ok) throw new Error('GFG API fail');
                const data = await res.json();
                if (data && data.info) {
                    gfgSolvedSpan.innerText = data.info.totalProblemsSolved ?? '0';
                    gfgScoreSpan.innerText = data.info.codingScore ?? 'N/A';
                    gfgRankSpan.innerText = data.info.rank ? `#${data.info.rank}` : '—';
                } else {
                    throw new Error('no data');
                }
            } catch (err) {
                gfgSolvedSpan.innerText = "unavailable";
                gfgScoreSpan.innerText = "—";
                gfgRankSpan.innerText = "—";
            }
        }

        // ---------- Master fetch + auto refresh + animations ----------
        async function refreshAllData() {
            // animate refresh icon
            const refreshIcon = document.querySelector('#refreshBtn i');
            refreshIcon.classList.add('fa-spin');
            await Promise.allSettled([fetchGitHubStats(), fetchLeetCodeStats(), fetchGFGStats()]);
            refreshIcon.classList.remove('fa-spin');
            updateLastFetchTime();
            // GSAP subtle highlight
            gsap.fromTo('.glass-card', { scale: 0.98, opacity: 0.9 }, { scale: 1, opacity: 1, duration: 0.5, stagger: 0.05 });
        }

        // ---------- Dark / Light mode ----------
        const themeBtn = document.getElementById('themeToggle');
        themeBtn.addEventListener('click', () => {
            document.body.classList.toggle('light');
            const icon = themeBtn.querySelector('i');
            if (document.body.classList.contains('light')) {
                icon.classList.remove('fa-moon');
                icon.classList.add('fa-sun');
                document.body.style.color = '#0f172a';
            } else {
                icon.classList.remove('fa-sun');
                icon.classList.add('fa-moon');
                document.body.style.color = '';
            }
        });

        // initial load and auto-refresh
        refreshAllData();
        setInterval(refreshAllData, 60000); // every 60 seconds
        document.getElementById('refreshBtn').addEventListener('click', refreshAllData);

        // extra entrance animation
        gsap.from('h1', { duration: 0.8, y: -40, opacity: 0, ease: 'back' });
        gsap.from('.glass-card', { duration: 0.6, y: 30, opacity: 0, stagger: 0.1, delay: 0.2 });
    </script>
</body>
</html>
