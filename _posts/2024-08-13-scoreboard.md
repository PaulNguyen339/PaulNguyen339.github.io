---
layout: default
title: "Phân cặp Pickleball"
date: 2024-08-13
categories: tools
---

<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Phân cặp Pickleball</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            padding: 10px;
        }

        .container {
            max-width: 400px;
            margin: 0 auto;
            background: white;
            border-radius: 12px;
            padding: 20px;
            box-shadow: 0 10px 25px rgba(0,0,0,0.1);
        }

        h1 {
            text-align: center;
            color: #333;
            margin-bottom: 20px;
            font-size: 24px;
        }

        .section {
            margin-bottom: 25px;
        }

        .section-title {
            font-weight: 600;
            color: #555;
            margin-bottom: 15px;
            font-size: 16px;
        }

        .player-item {
            background: #f8f9fa;
            border-radius: 8px;
            padding: 12px;
            margin-bottom: 10px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .player-name {
            flex: 1;
            border: 1px solid #ddd;
            border-radius: 6px;
            padding: 8px;
            font-size: 14px;
        }

        .skill-input {
            width: 50px;
            border: 1px solid #ddd;
            border-radius: 6px;
            padding: 8px;
            text-align: center;
            font-size: 14px;
        }

        .skill-badge {
            padding: 4px 8px;
            border-radius: 12px;
            font-size: 10px;
            font-weight: 600;
        }

        .skill-high { background: #fee2e2; color: #dc2626; }
        .skill-medium { background: #fef3c7; color: #d97706; }
        .skill-low { background: #dcfce7; color: #16a34a; }

        .btn {
            width: 100%;
            padding: 12px;
            border: none;
            border-radius: 8px;
            font-size: 16px;
            font-weight: 600;
            cursor: pointer;
            margin-bottom: 10px;
            transition: all 0.3s;
        }

        .btn-primary {
            background: #3b82f6;
            color: white;
        }

        .btn-primary:hover { background: #2563eb; }
        .btn-primary:disabled { background: #9ca3af; cursor: not-allowed; }

        .btn-secondary {
            background: #10b981;
            color: white;
        }

        .btn-danger {
            background: #ef4444;
            color: white;
            padding: 6px;
            width: auto;
            margin: 0;
            font-size: 12px;
        }

        .btn-small {
            padding: 6px 12px;
            font-size: 12px;
            width: auto;
            margin: 0 5px 0 0;
        }

        .match-item {
            background: linear-gradient(135deg, #f0f9ff 0%, #ecfdf5 100%);
            border-radius: 8px;
            padding: 15px;
            margin-bottom: 15px;
            border: 1px solid #e5e7eb;
        }

        .match-completed {
            background: linear-gradient(135deg, #fef3c7 0%, #fde68a 100%);
            border: 2px solid #f59e0b;
        }

        .match-header {
            display: flex;
            justify-content: space-between;
            margin-bottom: 10px;
        }

        .match-number {
            font-weight: 600;
            color: #1e40af;
        }

        .skill-diff {
            font-size: 12px;
            color: #6b7280;
        }

        .teams {
            display: flex;
            justify-content: space-between;
            align-items: center;
            text-align: center;
            margin-bottom: 15px;
        }

        .team {
            flex: 1;
        }

        .team-title {
            font-weight: 600;
            margin-bottom: 8px;
            font-size: 14px;
        }

        .team1 .team-title { color: #1e40af; }
        .team2 .team-title { color: #059669; }

        .vs {
            font-weight: 600;
            color: #6b7280;
            margin: 0 15px;
        }

        .player-in-match {
            font-size: 13px;
            margin-bottom: 4px;
        }

        .team-avg {
            font-size: 11px;
            color: #6b7280;
            margin-top: 4px;
        }

        .score-section {
            background: #f9fafb;
            border-radius: 6px;
            padding: 12px;
            margin-top: 10px;
        }

        .score-input-row {
            display: flex;
            align-items: center;
            gap: 10px;
            margin-bottom: 10px;
        }

        .score-input {
            width: 50px;
            border: 1px solid #ddd;
            border-radius: 4px;
            padding: 6px;
            text-align: center;
            font-size: 14px;
        }

        .score-vs {
            font-weight: 600;
            color: #6b7280;
        }

        .score-result {
            font-weight: 600;
            margin-top: 8px;
            padding: 8px;
            border-radius: 6px;
            text-align: center;
        }

        .team1-wins {
            background: #dbeafe;
            color: #1e40af;
        }

        .team2-wins {
            background: #d1fae5;
            color: #059669;
        }

        .stats {
            background: #f9fafb;
            border-radius: 8px;
            padding: 15px;
            margin-top: 20px;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 15px;
        }

        .stat-item {
            text-align: center;
        }

        .stat-value {
            font-size: 24px;
            font-weight: bold;
            color: #1e40af;
        }

        .stat-label {
            font-size: 12px;
            color: #6b7280;
            margin-top: 4px;
        }

        .info-text {
            font-size: 12px;
            color: #6b7280;
            text-align: center;
            margin-top: 10px;
        }

        .leaderboard {
            background: #f9fafb;
            border-radius: 8px;
            padding: 15px;
            margin-top: 20px;
        }

        .leaderboard-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 10px;
            margin-bottom: 8px;
            background: white;
            border-radius: 6px;
            border: 1px solid #e5e7eb;
        }

        .rank {
            font-weight: 600;
            color: #1e40af;
            width: 30px;
        }

        .player-info {
            flex: 1;
            margin-left: 10px;
        }

        .player-name-rank {
            font-weight: 600;
            margin-bottom: 2px;
        }

        .player-stats {
            font-size: 11px;
            color: #6b7280;
        }

        .wins-losses {
            text-align: right;
        }

        .wins {
            font-weight: 600;
            color: #059669;
        }

        .losses {
            font-weight: 600;
            color: #dc2626;
        }

        .btn-row {
            display: flex;
            gap: 10px;
            margin-bottom: 15px;
        }

        .btn-row .btn {
            margin: 0;
        }

        @media (max-width: 380px) {
            .container { padding: 15px; }
            h1 { font-size: 20px; }
            .teams { flex-direction: column; gap: 10px; }
            .vs { margin: 10px 0; }
            .score-input-row { justify-content: center; }
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>🏓 Phân cặp Pickleball</h1>

        <div class="section">
            <div class="section-title">👥 Người chơi (<span id="playerCount">5</span>)</div>
            <div id="playersList"></div>
            <button class="btn btn-primary" onclick="addPlayer()" id="addBtn">➕ Thêm người chơi</button>
        </div>

        <div class="section">
            <button class="btn btn-secondary" onclick="generateSchedule()" id="generateBtn">🎯 Tạo lịch thi đấu</button>
            <div class="info-text" id="matchInfo"></div>
        </div>

        <div class="section" id="scheduleSection" style="display: none;">
            <div class="section-title">📅 Lịch thi đấu (<span id="matchCount">0</span> trận)</div>
            <div class="btn-row">
                <button class="btn btn-danger btn-small" onclick="clearResults()">🗑️ Xóa kết quả</button>
                <button class="btn btn-danger btn-small" onclick="clearAll()">🗑️ Xóa tất cả</button>
            </div>
            <div id="scheduleList"></div>
            <div class="stats" id="statsSection"></div>
        </div>

        <div class="section" id="leaderboardSection" style="display: none;">
            <div class="section-title">🏆 Bảng xếp hạng</div>
            <div class="leaderboard" id="leaderboard"></div>
        </div>
    </div>

    <script>
        // Sử dụng biến global thay vì localStorage trong môi trường này
        let players = [
            { id: 1, name: 'Nguyễn Văn A', skill: 7 },
            { id: 2, name: 'Trần Thị B', skill: 8 },
            { id: 3, name: 'Lê Văn C', skill: 6 },
            { id: 4, name: 'Phạm Thị D', skill: 9 },
            { id: 5, name: 'Hoàng Văn E', skill: 7 }
        ];
        let nextId = 6;
        let schedule = [];
        let matchResults = {};

        // Khởi tạo khi load trang
        window.onload = function() {
            loadFromStorage();
            renderPlayers();
        };

        function saveToStorage() {
            // Trong môi trường thật, sẽ lưu vào localStorage
            // localStorage.setItem('pickleballData', JSON.stringify({players, nextId, schedule, matchResults}));
        }

        function loadFromStorage() {
            // Trong môi trường thật, sẽ load từ localStorage
            // const saved = localStorage.getItem('pickleballData');
            // if (saved) { const data = JSON.parse(saved); ... }
        }

        function clearAll() {
            if (confirm('Bạn có chắc muốn xóa tất cả dữ liệu (người chơi, lịch thi đấu, kết quả)?')) {
                players = [
                    { id: 1, name: 'Nguyễn Văn A', skill: 7 },
                    { id: 2, name: 'Trần Thị B', skill: 8 },
                    { id: 3, name: 'Lê Văn C', skill: 6 },
                    { id: 4, name: 'Phạm Thị D', skill: 9 },
                    { id: 5, name: 'Hoàng Văn E', skill: 7 }
                ];
                nextId = 6;
                schedule = [];
                matchResults = {};

                document.getElementById('scheduleSection').style.display = 'none';
                document.getElementById('leaderboardSection').style.display = 'none';
                renderPlayers();
            }
        }

        function clearResults() {
            if (confirm('Bạn có chắc muốn xóa tất cả kết quả trận đấu?')) {
                matchResults = {};
                saveToStorage();
                renderSchedule();
            }
        }

        function updatePlayerCount() {
            document.getElementById('playerCount').textContent = players.length;
            document.getElementById('addBtn').disabled = players.length >= 7;
            document.getElementById('generateBtn').disabled = players.length < 4;

            const totalMatches = calculateTotalMatches();
            const infoEl = document.getElementById('matchInfo');
            if (players.length >= 4) {
                infoEl.textContent = `Mỗi người sẽ đánh ${totalMatches} trận`;
                infoEl.style.color = '#059669';
            } else {
                infoEl.textContent = 'Cần ít nhất 4 người chơi';
                infoEl.style.color = '#dc2626';
            }
        }

        function getSkillBadgeClass(skill) {
            if (skill >= 9) return 'skill-high';
            if (skill >= 7) return 'skill-medium';
            return 'skill-low';
        }

        function getSkillText(skill) {
            if (skill >= 9) return 'Cao';
            if (skill >= 7) return 'TB';
            return 'Thấp';
        }

        function renderPlayers() {
            const container = document.getElementById('playersList');
            container.innerHTML = players.map(player => `
                <div class="player-item">
                    <input type="text" class="player-name" value="${player.name}"
                           onchange="updatePlayerName(${player.id}, this.value)">
                    <input type="number" class="skill-input" min="5" max="10" value="${player.skill}"
                           onchange="updatePlayerSkill(${player.id}, parseInt(this.value))">
                    <span class="skill-badge ${getSkillBadgeClass(player.skill)}">${getSkillText(player.skill)}</span>
                    ${players.length > 4 ? `<button class="btn-danger" onclick="removePlayer(${player.id})">🗑️</button>` : ''}
                </div>
            `).join('');
            updatePlayerCount();
        }

        function addPlayer() {
            if (players.length < 7) {
                players.push({
                    id: nextId,
                    name: `Người chơi ${nextId}`,
                    skill: 7
                });
                nextId++;
                renderPlayers();
                saveToStorage();
            }
        }

        function removePlayer(id) {
            if (players.length > 4) {
                players = players.filter(p => p.id !== id);
                renderPlayers();
                saveToStorage();
            }
        }

        function updatePlayerName(id, name) {
            const player = players.find(p => p.id === id);
            if (player) {
                player.name = name;
                saveToStorage();
            }
        }

        function updatePlayerSkill(id, skill) {
            const player = players.find(p => p.id === id);
            if (player) {
                player.skill = Math.max(5, Math.min(10, skill));
                renderPlayers();
                saveToStorage();
            }
        }

        function calculateTotalMatches() {
            const n = players.length;
            if (n < 4) return 0;
            const possibleOpponents = n - 1;
            return Math.ceil(possibleOpponents / 3) * 3;
        }

        function generateAllPairs() {
            const pairs = [];
            for (let i = 0; i < players.length; i++) {
                for (let j = i + 1; j < players.length; j++) {
                    pairs.push([players[i], players[j]]);
                }
            }
            return pairs;
        }

        function calculateSkillDifference(team1, team2) {
            const team1Avg = (team1[0].skill + team1[1].skill) / 2;
            const team2Avg = (team2[0].skill + team2[1].skill) / 2;
            return Math.abs(team1Avg - team2Avg);
        }

        function canPlay(pair1, pair2) {
            const ids1 = [pair1[0].id, pair1[1].id];
            const ids2 = [pair2[0].id, pair2[1].id];
            return !ids1.some(id => ids2.includes(id));
        }

        function generateSchedule() {
            if (players.length < 4) return;

            const totalMatches = calculateTotalMatches();
            const allPairs = generateAllPairs();
            schedule = [];
            matchResults = {};
            const playerStats = {};
            const pairHistory = new Set();
            const consecutiveGames = {};

            players.forEach(p => {
                playerStats[p.id] = { matches: 0, lastRound: -2 };
                consecutiveGames[p.id] = 0;
            });

            let round = 1;

            while (round <= totalMatches) {
                const availableMatches = [];

                for (let i = 0; i < allPairs.length; i++) {
                    for (let j = i + 1; j < allPairs.length; j++) {
                        const pair1 = allPairs[i];
                        const pair2 = allPairs[j];

                        if (canPlay(pair1, pair2)) {
                            const pairKey1 = `${Math.min(pair1[0].id, pair1[1].id)}-${Math.max(pair1[0].id, pair1[1].id)}`;
                            const pairKey2 = `${Math.min(pair2[0].id, pair2[1].id)}-${Math.max(pair2[0].id, pair2[1].id)}`;

                            const allPlayers = [...pair1, ...pair2];
                            const canAllPlay = allPlayers.every(p => {
                                const stats = playerStats[p.id];
                                const wouldBeConsecutive = stats.lastRound === round - 1;
                                const currentConsecutive = wouldBeConsecutive ? consecutiveGames[p.id] + 1 : 1;
                                return currentConsecutive <= 2 && stats.matches < totalMatches;
                            });

                            if (canAllPlay) {
                                const skillDiff = calculateSkillDifference(pair1, pair2);
                                const pairRepeat = pairHistory.has(pairKey1) || pairHistory.has(pairKey2);

                                availableMatches.push({
                                    pair1, pair2, skillDiff, pairRepeat, pairKey1, pairKey2, players: allPlayers
                                });
                            }
                        }
                    }
                }

                if (availableMatches.length === 0) break;

                availableMatches.sort((a, b) => {
                    if (a.pairRepeat !== b.pairRepeat) return a.pairRepeat - b.pairRepeat;
                    return a.skillDiff - b.skillDiff;
                });

                const bestMatch = availableMatches[0];

                schedule.push({
                    round,
                    team1: bestMatch.pair1,
                    team2: bestMatch.pair2,
                    skillDiff: bestMatch.skillDiff.toFixed(1)
                });

                bestMatch.players.forEach(p => {
                    const stats = playerStats[p.id];
                    stats.matches++;

                    if (stats.lastRound === round - 1) {
                        consecutiveGames[p.id]++;
                    } else {
                        consecutiveGames[p.id] = 1;
                    }
                    stats.lastRound = round;
                });

                pairHistory.add(bestMatch.pairKey1);
                pairHistory.add(bestMatch.pairKey2);

                round++;
            }

            saveToStorage();
            renderSchedule();
        }

        function saveScore(matchIndex, team1Score, team2Score) {
            if (team1Score !== '' && team2Score !== '' &&
                !isNaN(team1Score) && !isNaN(team2Score)) {
                matchResults[matchIndex] = {
                    team1Score: parseInt(team1Score),
                    team2Score: parseInt(team2Score)
                };
                saveToStorage();
                renderSchedule();
            }
        }

        function clearMatchScore(matchIndex) {
            delete matchResults[matchIndex];
            saveToStorage();
            renderSchedule();
        }

        function renderSchedule() {
            document.getElementById('scheduleSection').style.display = 'block';
            document.getElementById('matchCount').textContent = schedule.length;

            const container = document.getElementById('scheduleList');
            container.innerHTML = schedule.map((match, index) => {
                const result = matchResults[index];
                const isCompleted = result !== undefined;

                let scoreSection = '';
                if (isCompleted) {
                    const team1Wins = result.team1Score > result.team2Score;
                    scoreSection = `
                        <div class="score-section">
                            <div class="score-result ${team1Wins ? 'team1-wins' : 'team2-wins'}">
                                Kết quả: ${result.team1Score} - ${result.team2Score}
                                ${team1Wins ? ' (Đội 1 thắng)' : ' (Đội 2 thắng)'}
                            </div>
                            <button class="btn btn-danger btn-small" onclick="clearMatchScore(${index})" style="margin-top: 8px;">Xóa kết quả</button>
                        </div>
                    `;
                } else {
                    scoreSection = `
                        <div class="score-section">
                            <div style="font-weight: 600; margin-bottom: 8px; text-align: center;">Nhập tỉ số</div>
                            <div class="score-input-row">
                                <input type="number" class="score-input" id="team1Score${index}" min="0" placeholder="0">
                                <span class="score-vs">-</span>
                                <input type="number" class="score-input" id="team2Score${index}" min="0" placeholder="0">
                                <button class="btn btn-primary btn-small" onclick="saveScore(${index}, document.getElementById('team1Score${index}').value, document.getElementById('team2Score${index}').value)">Lưu</button>
                            </div>
                        </div>
                    `;
                }

                return `
                    <div class="match-item ${isCompleted ? 'match-completed' : ''}">
                        <div class="match-header">
                            <span class="match-number">Trận ${match.round}</span>
                            <span class="skill-diff">Chênh lệch: ${match.skillDiff}</span>
                        </div>
                        <div class="teams">
                            <div class="team team1">
                                <div class="team-title">Đội 1</div>
                                ${match.team1.map(p => `
                                    <div class="player-in-match">
                                        ${p.name} <span class="skill-badge ${getSkillBadgeClass(p.skill)}">${p.skill}</span>
                                    </div>
                                `).join('')}
                                <div class="team-avg">TB: ${((match.team1[0].skill + match.team1[1].skill) / 2).toFixed(1)}</div>
                            </div>
                            <div class="vs">VS</div>
                            <div class="team team2">
                                <div class="team-title">Đội 2</div>
                                ${match.team2.map(p => `
                                    <div class="player-in-match">
                                        ${p.name} <span class="skill-badge ${getSkillBadgeClass(p.skill)}">${p.skill}</span>
                                    </div>
                                `).join('')}
                                <div class="team-avg">TB: ${((match.team2[0].skill + match.team2[1].skill) / 2).toFixed(1)}</div>
                            </div>
                        </div>
                        ${scoreSection}
                    </div>
                `;
            }).join('');

            renderStats();
            renderLeaderboard();
        }

        function renderStats() {
            const completedMatches = Object.keys(matchResults).length;
            const avgSkillDiff = schedule.length > 0 ?
                (schedule.reduce((sum, match) => sum + parseFloat(match.skillDiff), 0) / schedule.length).toFixed(1) : '0';

            document.getElementById('statsSection').innerHTML = `
                <div class="section-title">📊 Thống kê</div>
                <div class="stats-grid">
                    <div class="stat-item">
                        <div class="stat-value">${schedule.length}</div>
                        <div class="stat-label">Tổng số trận</div>
                    </div>
                    <div class="stat-item">
                        <div class="stat-value">${completedMatches}</div>
                        <div class="stat-label">Đã hoàn thành</div>
                    </div>
                    <div class="stat-item">
                        <div class="stat-value">${avgSkillDiff}</div>
                        <div class="stat-label">Chênh lệch TB</div>
                    </div>
                    <div class="stat-item">
                        <div class="stat-value">${Math.round((completedMatches / schedule.length) * 100)}%</div>
                        <div class="stat-label">Tiến độ</div>
                    </div>
                </div>
            `;
        }

        function renderLeaderboard() {
            const playerStats = {};

            // Initialize stats
            players.forEach(p => {
                playerStats[p.id] = {
                    name: p.name,
                    skill: p.skill,
                    wins: 0,
                    losses: 0,
                    matches: 0
                };
            });

            // Calculate stats from completed matches
            schedule.forEach((match, index) => {
                const result = matchResults[index];
                if (result) {
                    const team1Players = match.team1;
                    const team2Players = match.team2;
                    const team1Wins = result.team1Score > result.team2Score;

                    team1Players.forEach(p => {
                        playerStats[p.id].matches++;
                        if (team1Wins) {
                            playerStats[p.id].wins++;
                        } else {
                            playerStats[p.id].losses++;
                        }
                    });

                    team2Players.forEach(p => {
                        playerStats[p.id].matches++;
                        if (!team1Wins) {
                            playerStats[p.id].wins++;
                        } else {
                            playerStats[p.id].losses++;
                        }
                    });
                }
            });

            // Sort by wins (descending), then by win rate
            const sortedPlayers = Object.values(playerStats).sort((a, b) => {
                if (b.wins !== a.wins) return b.wins - a.wins;
                if (a.matches === 0 && b.matches === 0) return 0;
                const aWinRate = a.matches > 0 ? a.wins / a.matches : 0;
                const bWinRate = b.matches > 0 ? b.wins / b.matches : 0;
                return bWinRate - aWinRate;
            });

            const hasAnyMatches = sortedPlayers.some(p => p.matches > 0);

            if (hasAnyMatches) {
                document.getElementById('leaderboardSection').style.display = 'block';
                document.getElementById('leaderboard').innerHTML = sortedPlayers.map((player, index) => {
                    const winRate = player.matches > 0 ? ((player.wins / player.matches) * 100).toFixed(0) : '0';

                    return `
                        <div class="leaderboard-item">
                            <div class="rank">#${index + 1}</div>
                            <div class="player-info">
                                <div class="player-name-rank">${player.name}</div>
                                <div class="player-stats">
                                    <span class="skill-badge ${getSkillBadgeClass(player.skill)}">${player.skill}</span>
                                    • ${player.matches} trận • Tỷ lệ thắng: ${winRate}%
                                </div>
                            </div>
                            <div class="wins-losses">
                                <div class="wins">${player.wins} thắng</div>
                                <div class="losses">${player.losses} thua</div>
                            </div>
                        </div>
                    `;
                }).join('');
            } else {
                document.getElementById('leaderboardSection').style.display = 'none';
            }
        }

        // Khởi tạo
        renderPlayers();
    </script>
</body>
</html>
