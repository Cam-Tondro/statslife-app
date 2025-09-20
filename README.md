# statslife-app
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>StatsLife - Your Life in Numbers</title>
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
            color: white;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }
        
        .header {
            text-align: center;
            margin-bottom: 40px;
        }
        
        .header h1 {
            font-size: 4rem;
            font-weight: 800;
            margin-bottom: 20px;
            background: linear-gradient(45deg, #fff, #f0f8ff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }
        
        .header p {
            font-size: 1.2rem;
            opacity: 0.9;
            max-width: 600px;
            margin: 0 auto 40px;
        }
        
        .controls {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 30px;
            margin-bottom: 40px;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
            margin-bottom: 40px;
        }
        
        .form-group {
            margin-bottom: 20px;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
        }
        
        .form-group input,
        .form-group select {
            width: 100%;
            padding: 12px;
            border: 1px solid rgba(255, 255, 255, 0.3);
            border-radius: 10px;
            background: rgba(255, 255, 255, 0.2);
            color: white;
            font-size: 16px;
        }
        
        .form-group input::placeholder {
            color: rgba(255, 255, 255, 0.7);
        }
        
        .form-group select option {
            background: #333;
            color: white;
        }
        
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 20px;
            margin-bottom: 40px;
        }
        
        .stat-card {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 16px;
            padding: 24px;
            border: 1px solid rgba(255, 255, 255, 0.2);
            transition: transform 0.3s ease, background 0.3s ease;
        }
        
        .stat-card:hover {
            transform: translateY(-5px);
            background: rgba(255, 255, 255, 0.15);
        }
        
        .stat-header {
            display: flex;
            align-items: center;
            margin-bottom: 16px;
        }
        
        .stat-icon {
            font-size: 2rem;
            margin-right: 12px;
        }
        
        .stat-title {
            font-size: 1.1rem;
            font-weight: 600;
        }
        
        .stat-value {
            text-align: right;
        }
        
        .stat-number {
            font-size: 2.5rem;
            font-weight: 800;
            line-height: 1;
            margin-bottom: 4px;
        }
        
        .stat-details {
            font-size: 0.9rem;
            opacity: 0.8;
        }
        
        .coming-soon {
            background: linear-gradient(45deg, #ff6b6b, #ffa500);
            border-radius: 20px;
            padding: 40px;
            text-align: center;
            margin-top: 40px;
        }
        
        .coming-soon h2 {
            font-size: 2rem;
            margin-bottom: 16px;
        }
        
        .coming-soon p {
            margin-bottom: 24px;
            opacity: 0.9;
        }
        
        .email-form {
            display: flex;
            gap: 12px;
            max-width: 400px;
            margin: 0 auto;
        }
        
        .email-input {
            flex: 1;
            padding: 12px 16px;
            border: none;
            border-radius: 25px;
            font-size: 16px;
        }
        
        .email-button {
            padding: 12px 24px;
            background: #fff;
            color: #333;
            border: none;
            border-radius: 25px;
            font-weight: 600;
            cursor: pointer;
            transition: transform 0.2s ease;
        }
        
        .email-button:hover {
            transform: scale(1.05);
        }
        
        @media (max-width: 768px) {
            .header h1 {
                font-size: 2.5rem;
            }
            
            .stats-grid {
                grid-template-columns: 1fr;
            }
            
            .email-form {
                flex-direction: column;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header class="header">
            <h1>StatsLife</h1>
            <p>Your life in numbers - like a video game achievement system for reality. Discover the incredible statistics of your everyday existence.</p>
        </header>
        
        <div class="controls">
            <div class="form-group">
                <label for="age">Your Age</label>
                <input type="number" id="age" value="25" min="1" max="120">
            </div>
            
            <div class="form-group">
                <label for="gender">Gender (affects heart rate)</label>
                <select id="gender">
                    <option value="">Please select</option>
                    <option value="male">Male</option>
                    <option value="female">Female</option>
                    <option value="other">Other</option>
                    <option value="prefer_not_to_say">I'd rather not say</option>
                </select>
            </div>
            
            <div class="form-group">
                <label for="activity">Activity Level</label>
                <select id="activity">
                    <option value="sedentary">Sedentary (office job, minimal exercise)</option>
                    <option value="average">Average (some walking, occasional exercise)</option>
                    <option value="active">Active (regular exercise, 10k+ steps)</option>
                    <option value="very_active">Very Active (athlete, daily intense exercise)</option>
                </select>
            </div>
        </div>
        
        <div class="stats-grid" id="statsGrid">
            <!-- Stats will be generated by JavaScript -->
        </div>
        
        <div class="coming-soon">
            <h2>🚀 More Features Coming Soon!</h2>
            <p>AI-powered custom stats, sharing features, achievements, and so much more. Be the first to know when we launch new features!</p>
            <form class="email-form" id="emailForm">
                <input type="email" class="email-input" placeholder="Enter your email" required>
                <button type="submit" class="email-button">Notify Me</button>
            </form>
        </div>
    </div>
    
    <script>
        // Stats configuration
        const statsConfig = [
            {
                id: 'heartbeats',
                title: 'Heartbeats',
                icon: '❤️',
                calculate: (age, gender, activity) => {
                    let rate = 70; // Default baseline
                    if (gender === 'female') rate = 75;
                    if (gender === 'male') rate = 68;
                    if (gender === 'other' || gender === 'prefer_not_to_say' || gender === '') {
                        rate = 71.5; // Average of male (68) and female (75)
                    }
                    if (age > 60) rate -= 5;
                    if (activity === 'sedentary') rate += 5;
                    if (activity === 'active') rate -= 5;
                    if (activity === 'very_active') rate -= 10;
                    return Math.floor(age * 365.25 * 24 * 60 * rate);
                }
            },
            {
                id: 'breaths',
                title: 'Breaths Taken',
                icon: '💨',
                calculate: (age) => {
                    const rate = age < 12 ? 20 : (age < 65 ? 16 : 18);
                    return Math.floor(age * 365.25 * 24 * 60 * rate);
                }
            },
            {
                id: 'steps',
                title: 'Steps Walked',
                icon: '👟',
                calculate: (age, gender, activity) => {
                    let dailySteps = 7500;
                    if (activity === 'sedentary') dailySteps = 4000;
                    if (activity === 'active') dailySteps = 10000;
                    if (activity === 'very_active') dailySteps = 15000;
                    return Math.floor(age * 365.25 * dailySteps);
                }
            },
            {
                id: 'blinks',
                title: 'Eye Blinks',
                icon: '👁️',
                calculate: (age) => Math.floor(age * 365.25 * 24 * 60 * 17)
            },
            {
                id: 'words',
                title: 'Words Spoken',
                icon: '💬',
                calculate: (age, gender, activity) => {
                    let daily = 16000;
                    if (activity === 'sedentary') daily = 12000;
                    if (activity === 'very_active') daily = 20000;
                    return Math.floor(age * 365.25 * daily);
                }
            },
            {
                id: 'meals',
                title: 'Meals Eaten',
                icon: '🍽️',
                calculate: (age) => Math.floor(age * 365.25 * 3)
            },
            {
                id: 'sleep',
                title: 'Hours Slept',
                icon: '😴',
                calculate: (age, gender, activity) => {
                    let daily = 8;
                    if (activity === 'very_active') daily = 8.5;
                    if (age < 18) daily = 9;
                    if (age > 65) daily = 7;
                    return Math.floor(age * 365.25 * daily);
                }
            },
            {
                id: 'laughs',
                title: 'Times Laughed',
                icon: '😂',
                calculate: (age) => Math.floor(age * 365.25 * 15)
            }
        ];
        
        // Format large numbers
        function formatNumber(num) {
            if (num >= 1000000000) {
                return (num / 1000000000).toFixed(1) + 'B';
            }
            if (num >= 1000000) {
                return (num / 1000000).toFixed(1) + 'M';
            }
            if (num >= 1000) {
                return (num / 1000).toFixed(1) + 'K';
            }
            return num.toLocaleString();
        }
        
        // Calculate and display stats
        function updateStats() {
            const age = parseInt(document.getElementById('age').value);
            const gender = document.getElementById('gender').value;
            const activity = document.getElementById('activity').value;
            
            const statsGrid = document.getElementById('statsGrid');
            statsGrid.innerHTML = '';
            
            statsConfig.forEach(stat => {
                const value = stat.calculate(age, gender, activity);
                
                const card = document.createElement('div');
                card.className = 'stat-card';
                card.innerHTML = `
                    <div class="stat-header">
                        <div class="stat-icon">${stat.icon}</div>
                        <div class="stat-title">${stat.title}</div>
                    </div>
                    <div class="stat-value">
                        <div class="stat-number">${formatNumber(value)}</div>
                        <div class="stat-details">${value.toLocaleString()}</div>
                    </div>
                `;
                
                statsGrid.appendChild(card);
            });
        }
        
        // Event listeners
        document.getElementById('age').addEventListener('input', updateStats);
        document.getElementById('gender').addEventListener('change', updateStats);
        document.getElementById('activity').addEventListener('change', updateStats);
        
        // Email form
        document.getElementById('emailForm').addEventListener('submit', function(e) {
            e.preventDefault();
            const email = this.querySelector('.email-input').value;
            alert(`Thanks! We'll notify ${email} when new features launch!`);
            this.querySelector('.email-input').value = '';
        });
        
        // Initialize stats
        updateStats();
    </script>
</body>
</html>
