<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Newsvendor Game</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
    <!-- Chart.js for visualizations -->
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <style>
        body {
            font-family: 'Inter', sans-serif;
        }
        .card {
            background-color: white;
            border-radius: 0.75rem;
            box-shadow: 0 4px 6px -1px rgb(0 0 0 / 0.1), 0 2px 4px -2px rgb(0 0 0 / 0.1);
            padding: 1.5rem;
        }
        .input-group {
            margin-bottom: 1rem;
        }
        .input-group label {
            display: block;
            margin-bottom: 0.5rem;
            color: #4b5563;
            font-weight: 500;
        }
        .input-group input {
            width: 100%;
            padding: 0.5rem 0.75rem;
            border: 1px solid #d1d5db;
            border-radius: 0.375rem;
            transition: border-color 0.2s, box-shadow 0.2s;
        }
        .input-group input:focus {
            outline: none;
            border-color: #3b82f6;
            box-shadow: 0 0 0 2px #bfdbfe;
        }
        .btn {
            padding: 0.75rem 1.5rem;
            border-radius: 0.375rem;
            font-weight: 600;
            color: white;
            cursor: pointer;
            transition: background-color 0.2s;
        }
        .btn-primary {
            background-color: #2563eb;
        }
        .btn-primary:hover {
            background-color: #1d4ed8;
        }
        .btn-disabled {
            background-color: #9ca3af;
            cursor: not-allowed;
        }
    </style>
</head>
<body class="bg-gray-50 text-gray-800">

    <div id="app-container" class="w-full p-4 md:p-8">

        <!-- STUDENT GAME SCREEN -->
        <div id="game-screen">
            <h1 class="text-2xl font-bold mb-4 text-center text-gray-900">The Newsvendor Challenge</h1>

            <!-- Game Information & Current Round -->
            <div class="grid md:grid-cols-2 gap-6 mb-6">
                <!-- Game Info -->
                <div class="card">
                    <h2 class="text-lg font-semibold mb-3 text-gray-700">Your Business Details</h2>
                    <div class="space-y-2">
                        <p><strong>Selling Price:</strong> <span id="info-selling-price" class="font-mono text-green-600"></span></p>
                        <p><strong>Purchase Cost:</strong> <span id="info-purchase-cost" class="font-mono text-red-600"></span></p>
                        <p><strong>Salvage Value:</strong> <span id="info-salvage-value" class="font-mono text-blue-600"></span></p>
                    </div>
                    <div class="mt-4 pt-4 border-t">
                         <h3 class="text-lg font-semibold text-gray-700">Total Profit</h3>
                         <p id="total-profit" class="text-2xl font-bold font-mono">$0.00</p>
                    </div>
                </div>

                <!-- Current Round -->
                <div class="card bg-blue-50">
                     <h2 id="round-title" class="text-lg font-semibold mb-3 text-gray-700">Round 1 of 20</h2>
                     <div class="input-group">
                        <label for="order-quantity">How many units will you order?</label>
                        <input type="number" id="order-quantity" placeholder="e.g., 110" min="0">
                     </div>
                     <button id="place-order-btn" class="btn btn-primary w-full">Place Order</button>
                     <div id="game-over-message" class="hidden mt-4 text-center p-4 bg-green-100 text-green-800 rounded-lg">
                        <h3 class="font-bold">Game Over!</h3>
                        <p>Your final total profit is <span id="final-total-profit" class="font-bold"></span>.</p>
                        <p class="mt-2">Please take a screenshot of this page for your records.</p>
                     </div>
                </div>
            </div>

            <!-- Profit Visualization -->
            <div class="card mb-6">
                <h2 class="text-lg font-semibold mb-3 text-gray-700">Round Profit Visualization</h2>
                <div class="h-64">
                    <canvas id="profit-chart"></canvas>
                </div>
            </div>

            <!-- History Table -->
            <div class="card">
                <h2 class="text-lg font-semibold mb-3 text-gray-700">Performance History</h2>
                <div class="overflow-x-auto">
                    <table class="w-full text-left">
                        <thead class="bg-gray-100 text-gray-600">
                            <tr>
                                <th class="p-3 font-semibold">Round</th>
                                <th class="p-3 font-semibold">Your Order</th>
                                <th class="p-3 font-semibold">Actual Demand</th>
                                <th class="p-3 font-semibold">Units Sold</th>
                                <th class="p-3 font-semibold">Units Salvaged</th>
                                <th class="p-3 font-semibold">Round Profit</th>
                            </tr>
                        </thead>
                        <tbody id="history-table-body">
                           <!-- Rows will be added by JS -->
                        </tbody>
                    </table>
                </div>
            </div>
        </div>
    </div>

    <script>
        // --- INSTRUCTOR: EDIT GAME PARAMETERS HERE ---
        const gameParameters = {
            // Demand parameters (hidden from student)
            mean: 100,
            stdDev: 25,
            
            // Economic parameters (shown to student)
            sellingPrice: 15,
            purchaseCost: 10,
            salvageValue: 3,
            
            // Game length
            totalRounds: 20,
        };
        // ---------------------------------------------

        // DOM Elements
        const placeOrderBtn = document.getElementById('place-order-btn');

        // Game State
        let gameState = {
            params: gameParameters,
            currentRound: 1,
            history: [],
            cumulativeProfit: 0,
        };
        let profitChart; // To hold the chart instance

        // --- UTILITY FUNCTIONS ---
        
        function boxMullerTransform() {
            let u1 = 0, u2 = 0;
            while (u1 === 0) u1 = Math.random();
            while (u2 === 0) u2 = Math.random();
            const z0 = Math.sqrt(-2.0 * Math.log(u1)) * Math.cos(2.0 * Math.PI * u2);
            return z0;
        }
        
        function getNormallyDistributedRandomNumber(mean, stdDev) {
            const z0 = boxMullerTransform();
            const value = z0 * stdDev + mean;
            return Math.round(Math.max(0, value));
        }

        function formatCurrency(value) {
            const isNegative = value < 0;
            const formatted = Math.abs(value).toLocaleString('en-US', {
                style: 'currency',
                currency: 'USD'
            });
            return isNegative ? `-${formatted}` : formatted;
        }

        // --- GAME LOGIC ---

        function initializeGame() {
            // The game state is already initialized with parameters.
            // Just update the UI to reflect them.
            updateGameUI();
            initializeChart();
        }

        function playRound() {
            const orderQuantityInput = document.getElementById('order-quantity');
            const orderQuantity = parseInt(orderQuantityInput.value, 10);

            if (isNaN(orderQuantity) || orderQuantity < 0) {
                alert("Please enter a valid, non-negative order quantity.");
                return;
            }
            
            const demand = getNormallyDistributedRandomNumber(gameState.params.mean, gameState.params.stdDev);
            const unitsSold = Math.min(orderQuantity, demand);
            const unitsSalvaged = Math.max(0, orderQuantity - demand);
            const revenue = unitsSold * gameState.params.sellingPrice;
            const salvageRevenue = unitsSalvaged * gameState.params.salvageValue;
            const cost = orderQuantity * gameState.params.purchaseCost;
            const profit = (revenue + salvageRevenue) - cost;

            const roundData = { round: gameState.currentRound, orderQuantity, demand, unitsSold, unitsSalvaged, profit };
            gameState.cumulativeProfit += profit;
            gameState.history.push(roundData);

            updateHistoryTable();
            updateChart(roundData);
            updateGameUI();

            if (gameState.currentRound >= gameState.params.totalRounds) {
                endGame();
            } else {
                gameState.currentRound++;
                document.getElementById('round-title').textContent = `Round ${gameState.currentRound} of ${gameState.params.totalRounds}`;
                orderQuantityInput.value = '';
                orderQuantityInput.focus();
            }
        }

        function endGame() {
            document.getElementById('order-quantity').disabled = true;
            placeOrderBtn.disabled = true;
            placeOrderBtn.classList.add('btn-disabled');
            document.getElementById('final-total-profit').textContent = formatCurrency(gameState.cumulativeProfit);
            document.getElementById('game-over-message').classList.remove('hidden');
            document.getElementById('round-title').textContent = `Game Complete (${gameState.params.totalRounds} Rounds)`;
        }


        // --- UI & CHART UPDATE FUNCTIONS ---
        function initializeChart() {
            const ctx = document.getElementById('profit-chart').getContext('2d');
            profitChart = new Chart(ctx, {
                type: 'line',
                data: {
                    labels: [],
                    datasets: [{
                        label: 'Profit per Round',
                        data: [],
                        borderColor: 'rgba(59, 130, 246, 0.8)',
                        pointBackgroundColor: [],
                        pointBorderColor: '#ffffff',
                        pointBorderWidth: 2,
                        pointRadius: 5,
                        tension: 0.1
                    }]
                },
                options: {
                    scales: {
                        y: {
                            ticks: {
                                callback: function(value, index, values) {
                                    return '$' + value;
                                }
                            }
                        }
                    },
                    plugins: {
                        legend: {
                            display: false
                        }
                    },
                    responsive: true,
                    maintainAspectRatio: false
                }
            });
        }

        function updateChart(roundData) {
            profitChart.data.labels.push(`Round ${roundData.round}`);
            profitChart.data.datasets[0].data.push(roundData.profit.toFixed(2));
            
            const profitColor = roundData.profit >= 0 ? 'rgba(34, 197, 94, 1)' : 'rgba(239, 68, 68, 1)';
            profitChart.data.datasets[0].pointBackgroundColor.push(profitColor);

            profitChart.update();
        }

        function updateGameUI() {
            const { sellingPrice, purchaseCost, salvageValue, totalRounds } = gameState.params;
            document.getElementById('info-selling-price').textContent = formatCurrency(sellingPrice);
            document.getElementById('info-purchase-cost').textContent = formatCurrency(purchaseCost);
            document.getElementById('info-salvage-value').textContent = formatCurrency(salvageValue);
            document.getElementById('round-title').textContent = `Round ${gameState.currentRound} of ${totalRounds}`;
            const totalProfitEl = document.getElementById('total-profit');
            totalProfitEl.textContent = formatCurrency(gameState.cumulativeProfit);
            totalProfitEl.style.color = gameState.cumulativeProfit >= 0 ? '#16a34a' : '#dc2626';
        }

        function updateHistoryTable() {
            const tableBody = document.getElementById('history-table-body');
            tableBody.innerHTML = '';
            [...gameState.history].reverse().forEach(round => {
                const row = document.createElement('tr');
                row.classList.add('border-b');
                const profitColor = round.profit >= 0 ? 'text-green-700' : 'text-red-700';
                row.innerHTML = `
                    <td class="p-3 font-medium">${round.round}</td>
                    <td class="p-3 font-mono">${round.orderQuantity}</td>
                    <td class="p-3 font-mono">${round.demand}</td>
                    <td class="p-3 font-mono">${round.unitsSold}</td>
                    <td class="p-3 font-mono">${round.unitsSalvaged}</td>
                    <td class="p-3 font-mono font-semibold ${profitColor}">${formatCurrency(round.profit)}</td>
                `;
                tableBody.appendChild(row);
            });
        }

        // --- EVENT LISTENERS ---
        document.addEventListener('DOMContentLoaded', initializeGame);
        placeOrderBtn.addEventListener('click', playRound);
        
        document.getElementById('order-quantity').addEventListener('keyup', function(event) {
            if (event.key === 'Enter') {
                placeOrderBtn.click();
            }
        });

    </script>
</body>
</html>
