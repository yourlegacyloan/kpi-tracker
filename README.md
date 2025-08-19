# kpi-tracker
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>Real Estate Agent KPI Tracker</title>
    <style type="text/css">
        @import url('https://fonts.googleapis.com/css2?family=League+Spartan:wght@700&display=swap');
        
        .container {
            font-family: 'League Spartan', Arial, sans-serif;
            font-weight: 700;
            max-width: 800px;
            margin: 0 auto;
            background-color: #ffffff;
            color: #332b34;
        }
        
        .header {
            background: linear-gradient(135deg, #02ccfe, #01b3e3);
            color: #332b34;
            padding: 30px 20px;
            text-align: center;
            border-radius: 10px 10px 0 0;
            margin-bottom: 0;
        }
        
        .header h1 {
            margin: 0 0 10px 0;
            font-size: 28px;
            font-weight: 700;
        }
        
        .header p {
            margin: 0;
            font-size: 16px;
        }
        
        .download-section {
            background-color: #332b34;
            color: #ffffff;
            padding: 20px;
            text-align: center;
            border-radius: 0 0 10px 10px;
            margin-bottom: 20px;
        }
        
        .download-button {
            background: linear-gradient(135deg, #02ccfe, #01b3e3);
            color: #332b34;
            padding: 12px 25px;
            border: none;
            border-radius: 25px;
            font-family: 'League Spartan', Arial, sans-serif;
            font-weight: 700;
            cursor: pointer;
            font-size: 14px;
            margin: 5px;
            text-decoration: none;
            display: inline-block;
            transition: all 0.3s ease;
        }
        
        .download-button:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(2,204,254,0.4);
        }
        
        .month-year {
            background-color: #02ccfe;
            color: #332b34;
            padding: 15px;
            text-align: center;
            font-size: 18px;
            font-weight: 700;
            margin-bottom: 20px;
        }
        
        .kpi-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin-bottom: 30px;
        }
        
        .kpi-card {
            background-color: #ffffff;
            border: 3px solid #02ccfe;
            border-radius: 10px;
            padding: 20px;
            text-align: center;
            box-shadow: 0 3px 10px rgba(2,204,254,0.1);
            display: flex;
            flex-direction: column;
            height: auto;
            min-height: 140px;
        }
        
        .kpi-card h3 {
            color: #02ccfe;
            margin: 0 0 15px 0;
            font-size: 16px;
            flex-shrink: 0;
        }
        
        .kpi-input {
            font-size: 24px;
            font-weight: 700;
            border: 2px solid #02ccfe;
            border-radius: 5px;
            padding: 15px 10px;
            text-align: center;
            width: 100%;
            color: #332b34;
            font-family: 'League Spartan', Arial, sans-serif;
            box-sizing: border-box;
            height: 60px;
            background-color: #ffffff;
        }
        
        .kpi-target {
            font-size: 14px;
            color: #332b34;
            margin-top: 8px;
            flex-shrink: 0;
        }
        
        .section-header {
            background-color: #332b34;
            color: #ffffff;
            padding: 15px;
            text-align: center;
            font-size: 18px;
            font-weight: 700;
            margin: 30px 0 20px 0;
        }
        
        .activity-tracker {
            background-color: #ffffff;
            border: 2px solid #02ccfe;
            border-radius: 10px;
            overflow: hidden;
            margin-bottom: 20px;
        }
        
        .activity-tracker table {
            width: 100%;
            border-collapse: collapse;
        }
        
        .activity-tracker th {
            background-color: #02ccfe;
            color: #332b34;
            padding: 12px;
            font-weight: 700;
            text-align: center;
        }
        
        .activity-tracker td {
            padding: 10px;
            text-align: center;
            border-bottom: 1px solid #02ccfe;
        }
        
        .activity-tracker input {
            border: 1px solid #02ccfe;
            border-radius: 3px;
            padding: 5px;
            text-align: center;
            width: 60px;
            font-family: 'League Spartan', Arial, sans-serif;
            font-weight: 700;
        }
        
        .week-header {
            background-color: #f8f9fa;
            font-weight: 700;
            color: #332b34;
        }
        
        .notes-section {
            background-color: #ffffff;
            border: 2px solid #02ccfe;
            border-radius: 10px;
            padding: 20px;
            margin-bottom: 20px;
        }
        
        .notes-section textarea {
            width: 100%;
            height: 100px;
            border: 1px solid #02ccfe;
            border-radius: 5px;
            padding: 10px;
            font-family: 'League Spartan', Arial, sans-serif;
            font-weight: 700;
            color: #332b34;
            resize: vertical;
        }
        
        .goal-section {
            background: linear-gradient(135deg, rgba(2,204,254,0.1), rgba(255,255,255,0.9));
            border: 2px solid #02ccfe;
            border-radius: 10px;
            padding: 20px;
            margin-bottom: 20px;
        }
        
        .goal-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 10px;
            padding: 10px;
            background-color: #ffffff;
            border-radius: 5px;
        }
        
        .goal-item input[type="text"] {
            flex-grow: 1;
            margin-right: 10px;
            padding: 8px;
            border: 1px solid #02ccfe;
            border-radius: 3px;
            font-family: 'League Spartan', Arial, sans-serif;
            font-weight: 700;
        }
        
        .goal-item input[type="number"] {
            width: 80px;
            padding: 8px;
            border: 1px solid #02ccfe;
            border-radius: 3px;
            text-align: center;
            font-family: 'League Spartan', Arial, sans-serif;
            font-weight: 700;
        }
        
        .calculation-section {
            background-color: #332b34;
            color: #ffffff;
            padding: 20px;
            border-radius: 10px;
            margin-bottom: 20px;
        }
        
        .calculation-row {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 10px;
            padding: 8px 0;
            border-bottom: 1px solid #02ccfe;
        }
        
        .calculation-row:last-child {
            border-bottom: none;
            font-size: 18px;
            font-weight: 700;
            background-color: #02ccfe;
            color: #332b34;
            padding: 12px;
            border-radius: 5px;
        }
    </style>
</head>
<body style="margin: 0; padding: 20px; background-color: #f8f9fa;">
    
    <div class="container">
        <!-- Header -->
        <div class="header">
            <h1>📊 Monthly KPI Tracker</h1>
            <p>Track Your Success, Build Your Business</p>
        </div>
        
        <!-- Download Section -->
        <div class="download-section">
            <p style="margin: 0 0 15px 0;">💾 Save this tracker for offline use:</p>
            <button class="download-button" onclick="downloadExcel()">📊 Download Excel</button>
            <button class="download-button" onclick="downloadPDF()">📄 Download PDF</button>
            <button class="download-button" onclick="printTracker()">🖨️ Print Version</button>
        </div>
        
        <!-- Month/Year -->
        <div class="month-year">
            <label for="month-select">Month: </label>
            <select id="month-select" style="padding: 5px; border: none; border-radius: 3px; font-weight: 700;">
                <option value="January">January</option>
                <option value="February">February</option>
                <option value="March">March</option>
                <option value="April">April</option>
                <option value="May">May</option>
                <option value="June">June</option>
                <option value="July">July</option>
                <option value="August">August</option>
                <option value="September">September</option>
                <option value="October">October</option>
                <option value="November">November</option>
                <option value="December">December</option>
            </select>
            
            <label for="year-input" style="margin-left: 20px;">Year: </label>
            <input type="number" id="year-input" value="2025" style="width: 80px; padding: 5px; border: none; border-radius: 3px; font-weight: 700; text-align: center;">
        </div>
        
        <!-- Key Performance Indicators -->
        <div class="section-header">🎯 KEY PERFORMANCE INDICATORS</div>
        
        <div class="kpi-grid">
            <div class="kpi-card">
                <h3>Listings Taken</h3>
                <input type="number" class="kpi-input" id="listings-taken" placeholder="0">
                <div class="kpi-target">Target: 3-5/month</div>
            </div>
            
            <div class="kpi-card">
                <h3>Listings Sold</h3>
                <input type="number" class="kpi-input" id="listings-sold" placeholder="0">
                <div class="kpi-target">Target: 80% of listings</div>
            </div>
            
            <div class="kpi-card">
                <h3>Buyer Sales</h3>
                <input type="number" class="kpi-input" id="buyer-sales" placeholder="0">
                <div class="kpi-target">Target: 2-4/month</div>
            </div>
            
            <div class="kpi-card">
                <h3>Total Volume ($)</h3>
                <input type="number" class="kpi-input" id="total-volume" placeholder="0">
                <div class="kpi-target">Target: Your goal</div>
            </div>
            
            <div class="kpi-card">
                <h3>New Leads</h3>
                <input type="number" class="kpi-input" id="new-leads" placeholder="0">
                <div class="kpi-target">Target: 15-25/month</div>
            </div>
            
            <div class="kpi-card">
                <h3>Lead Conversion %</h3>
                <input type="number" class="kpi-input" id="conversion-rate" placeholder="0" max="100">
                <div class="kpi-target">Target: 15-25%</div>
            </div>
        </div>
        
        <!-- Monthly Goals -->
        <div class="section-header">🏆 MONTHLY GOALS & PROGRESS</div>
        
        <div class="goal-section">
            <div class="goal-item">
                <input type="text" placeholder="Goal Description" value="Total Transactions">
                <input type="number" placeholder="Target" value="6">
                <input type="number" placeholder="Actual" style="background-color: #02ccfe; color: #332b34;">
            </div>
            
            <div class="goal-item">
                <input type="text" placeholder="Goal Description" value="Gross Commission Income">
                <input type="number" placeholder="Target" value="18000">
                <input type="number" placeholder="Actual" style="background-color: #02ccfe; color: #332b34;">
            </div>
            
            <div class="goal-item">
                <input type="text" placeholder="Goal Description" value="New Client Contacts">
                <input type="number" placeholder="Target" value="50">
                <input type="number" placeholder="Actual" style="background-color: #02ccfe; color: #332b34;">
            </div>
            
            <div class="goal-item">
                <input type="text" placeholder="Goal Description" value="Referrals Received">
                <input type="number" placeholder="Target" value="3">
                <input type="number" placeholder="Actual" style="background-color: #02ccfe; color: #332b34;">
            </div>
        </div>
        
        <!-- Weekly Activity Tracker -->
        <div class="section-header">📅 WEEKLY ACTIVITY TRACKER</div>
        
        <div class="activity-tracker">
            <table>
                <thead>
                    <tr>
                        <th>Activity</th>
                        <th>Week 1</th>
                        <th>Week 2</th>
                        <th>Week 3</th>
                        <th>Week 4</th>
                        <th>Total</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td style="text-align: left; font-weight: 700;">Prospecting Calls</td>
                        <td><input type="number" class="activity-input" data-row="0" data-week="1"></td>
                        <td><input type="number" class="activity-input" data-row="0" data-week="2"></td>
                        <td><input type="number" class="activity-input" data-row="0" data-week="3"></td>
                        <td><input type="number" class="activity-input" data-row="0" data-week="4"></td>
                        <td class="total-cell" id="total-0">0</td>
                    </tr>
                    <tr>
                        <td style="text-align: left; font-weight: 700;">Listing Appointments</td>
                        <td><input type="number" class="activity-input" data-row="1" data-week="1"></td>
                        <td><input type="number" class="activity-input" data-row="1" data-week="2"></td>
                        <td><input type="number" class="activity-input" data-row="1" data-week="3"></td>
                        <td><input type="number" class="activity-input" data-row="1" data-week="4"></td>
                        <td class="total-cell" id="total-1">0</td>
                    </tr>
                    <tr>
                        <td style="text-align: left; font-weight: 700;">Buyer Showings</td>
                        <td><input type="number" class="activity-input" data-row="2" data-week="1"></td>
                        <td><input type="number" class="activity-input" data-row="2" data-week="2"></td>
                        <td><input type="number" class="activity-input" data-row="2" data-week="3"></td>
                        <td><input type="number" class="activity-input" data-row="2" data-week="4"></td>
                        <td class="total-cell" id="total-2">0</td>
                    </tr>
                    <tr>
                        <td style="text-align: left; font-weight: 700;">Open Houses Held</td>
                        <td><input type="number" class="activity-input" data-row="3" data-week="1"></td>
                        <td><input type="number" class="activity-input" data-row="3" data-week="2"></td>
                        <td><input type="number" class="activity-input" data-row="3" data-week="3"></td>
                        <td><input type="number" class="activity-input" data-row="3" data-week="4"></td>
                        <td class="total-cell" id="total-3">0</td>
                    </tr>
                    <tr>
                        <td style="text-align: left; font-weight: 700;">Follow-up Contacts</td>
                        <td><input type="number" class="activity-input" data-row="4" data-week="1"></td>
                        <td><input type="number" class="activity-input" data-row="4" data-week="2"></td>
                        <td><input type="number" class="activity-input" data-row="4" data-week="3"></td>
                        <td><input type="number" class="activity-input" data-row="4" data-week="4"></td>
                        <td class="total-cell" id="total-4">0</td>
                    </tr>
                </tbody>
            </table>
        </div>
        
        <!-- Performance Calculations -->
        <div class="section-header">🧮 PERFORMANCE CALCULATIONS</div>
        
        <div class="calculation-section">
            <div class="calculation-row">
                <span>Average Commission per Transaction:</span>
                <span id="avg-commission">$0</span>
            </div>
            <div class="calculation-row">
                <span>Conversion Rate (Leads to Sales):</span>
                <span id="conversion-calc">0%</span>
            </div>
            <div class="calculation-row">
                <span>Average Days to Close:</span>
                <span>30 days (manual entry)</span>
            </div>
            <div class="calculation-row">
                <span>Monthly Income Goal Progress:</span>
                <span id="income-progress">$0 / $18,000</span>
            </div>
        </div>
        
        <!-- Notes Section -->
        <div class="section-header">📝 MONTHLY NOTES & INSIGHTS</div>
        
        <div class="notes-section">
            <h3 style="color: #02ccfe; margin-top: 0;">Key Wins This Month:</h3>
            <textarea placeholder="Record your biggest successes, breakthrough moments, and achievements..."></textarea>
            
            <h3 style="color: #02ccfe;">Areas for Improvement:</h3>
            <textarea placeholder="What didn't work? What would you do differently? Action items for next month..."></textarea>
            
            <h3 style="color: #02ccfe;">Market Insights:</h3>
            <textarea placeholder="Trends you're seeing, client feedback, market conditions affecting your business..."></textarea>
        </div>
        
    </div>
    
    <script>
        // Set current month and year
        document.addEventListener('DOMContentLoaded', function() {
            const now = new Date();
            const monthSelect = document.getElementById('month-select');
            const yearInput = document.getElementById('year-input');
            
            monthSelect.value = now.toLocaleString('default', { month: 'long' });
            yearInput.value = now.getFullYear();
            
            // Add event listeners for activity calculations
            const activityInputs = document.querySelectorAll('.activity-input');
            activityInputs.forEach(input => {
                input.addEventListener('input', calculateTotals);
            });
            
            // Add event listeners for KPI calculations
            const kpiInputs = document.querySelectorAll('.kpi-input');
            kpiInputs.forEach(input => {
                input.addEventListener('input', calculatePerformance);
            });
        });
        
        function calculateTotals() {
            for (let row = 0; row < 5; row++) {
                let total = 0;
                for (let week = 1; week <= 4; week++) {
                    const input = document.querySelector(`[data-row="${row}"][data-week="${week}"]`);
                    const value = parseInt(input.value) || 0;
                    total += value;
                }
                document.getElementById(`total-${row}`).textContent = total;
            }
        }
        
        function calculatePerformance() {
            const totalVolume = parseFloat(document.getElementById('total-volume').value) || 0;
            const totalTransactions = (parseFloat(document.getElementById('listings-sold').value) || 0) + 
                                    (parseFloat(document.getElementById('buyer-sales').value) || 0);
            const newLeads = parseFloat(document.getElementById('new-leads').value) || 0;
            
            // Average commission (assuming 3% average commission rate)
            const avgCommission = totalTransactions > 0 ? (totalVolume * 0.03) / totalTransactions : 0;
            document.getElementById('avg-commission').textContent = '$' + avgCommission.toLocaleString(undefined, {maximumFractionDigits: 0});
            
            // Conversion rate
            const conversionRate = newLeads > 0 ? (totalTransactions / newLeads * 100) : 0;
            document.getElementById('conversion-calc').textContent = conversionRate.toFixed(1) + '%';
            
            // Income progress
            const totalIncome = totalVolume * 0.03;
            document.getElementById('income-progress').textContent = '$' + totalIncome.toLocaleString(undefined, {maximumFractionDigits: 0}) + ' / $18,000';
        }
        
        function downloadExcel() {
            alert('📊 Excel download feature would connect to your preferred spreadsheet tool. For now, use Print and save as PDF, or manually transfer data to Excel.');
        }
        
        function downloadPDF() {
            window.print();
        }
        
        function printTracker() {
            window.print();
        }
    </script>
    
</body>
</html>
