# Global-Impact
Here you can see a lot of problems on our planet.
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Global Challenges Observatory | Understanding Our World</title>
    <style>
        :root {
            --bg-primary: #0b0f19;
            --bg-secondary: #151c2c;
            --bg-card: #1e293b;
            --bg-card-hover: #26334d;
            --accent-primary: #38bdf8;
            --accent-hover: #0284c7;
            --text-main: #f8fafc;
            --text-muted: #94a3b8;
            --border: #334155;
            --danger: #f43f5e;
            --warning: #fbbf24;
            --success: #34d399;
        }

        [data-theme="light"] {
            --bg-primary: #f8fafc;
            --bg-secondary: #ffffff;
            --bg-card: #f1f5f9;
            --bg-card-hover: #e2e8f0;
            --text-main: #0f172a;
            --text-muted: #64748b;
            --border: #cbd5e1;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Segoe UI', system-ui, -apple-system, BlinkMacSystemFont, Roboto, sans-serif;
        }

        body {
            background-color: var(--bg-primary);
            color: var(--text-main);
            line-height: 1.6;
            transition: background-color 0.3s, color 0.3s;
        }

        /* Navigation */
        nav {
            background-color: rgba(11, 15, 25, 0.85);
            backdrop-filter: blur(12px);
            position: fixed;
            top: 0;
            width: 100%;
            z-index: 100;
            border-bottom: 1px solid var(--border);
        }

        .nav-container {
            max-width: 1280px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1rem 2rem;
        }

        .logo {
            font-size: 1.4rem;
            font-weight: 700;
            color: var(--accent-primary);
            text-decoration: none;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .nav-links {
            display: flex;
            gap: 2rem;
            list-style: none;
            align-items: center;
        }

        .nav-links a {
            color: var(--text-main);
            text-decoration: none;
            font-size: 0.95rem;
            font-weight: 500;
            transition: color 0.2s;
        }

        .nav-links a:hover {
            color: var(--accent-primary);
        }

        .theme-toggle {
            background: none;
            border: 1px solid var(--border);
            color: var(--text-main);
            padding: 0.4rem 0.8rem;
            border-radius: 6px;
            cursor: pointer;
            font-size: 0.85rem;
        }

        /* Hero Header */
        header.hero {
            padding: 10rem 2rem 5rem;
            text-align: center;
            background: radial-gradient(circle at 50% 20%, rgba(56, 189, 248, 0.12) 0%, transparent 60%);
        }

        .hero-badge {
            display: inline-block;
            background-color: rgba(56, 189, 248, 0.1);
            color: var(--accent-primary);
            border: 1px solid rgba(56, 189, 248, 0.2);
            padding: 0.35rem 1rem;
            border-radius: 20px;
            font-size: 0.85rem;
            font-weight: 600;
            margin-bottom: 1.5rem;
        }

        .hero h1 {
            font-size: 3.2rem;
            font-weight: 800;
            letter-spacing: -0.02em;
            margin-bottom: 1.2rem;
            line-height: 1.15;
            max-width: 900px;
            margin-left: auto;
            margin-right: auto;
        }

        .hero p {
            font-size: 1.2rem;
            color: var(--text-muted);
            max-width: 760px;
            margin: 0 auto 2.5rem;
        }

        /* Interactive Filters */
        .filter-container {
            display: flex;
            justify-content: center;
            gap: 0.75rem;
            margin-bottom: 3rem;
            flex-wrap: wrap;
        }

        .filter-btn {
            background: var(--bg-secondary);
            border: 1px solid var(--border);
            color: var(--text-muted);
            padding: 0.6rem 1.2rem;
            border-radius: 8px;
            cursor: pointer;
            font-weight: 500;
            transition: all 0.2s;
        }

        .filter-btn:hover, .filter-btn.active {
            background: var(--accent-primary);
            color: #000;
            border-color: var(--accent-primary);
        }

        /* Layout Container */
        .container {
            max-width: 1280px;
            margin: 0 auto;
            padding: 0 2rem 4rem;
        }

        /* Dashboard Metrics */
        .metrics-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
            gap: 1.5rem;
            margin-bottom: 4rem;
        }

        .metric-card {
            background-color: var(--bg-secondary);
            border: 1px solid var(--border);
            border-radius: 12px;
            padding: 1.75rem;
            position: relative;
            overflow: hidden;
        }

        .metric-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 4px;
            height: 100%;
            background-color: var(--accent-primary);
        }

        .metric-value {
            font-size: 2.2rem;
            font-weight: 800;
            color: var(--text-main);
            margin-bottom: 0.25rem;
        }

        .metric-title {
            font-size: 0.9rem;
            font-weight: 600;
            color: var(--text-muted);
            text-transform: uppercase;
            letter-spacing: 0.05em;
        }

        .metric-sub {
            font-size: 0.8rem;
            color: var(--text-muted);
            margin-top: 0.5rem;
        }

        /* Issues Section */
        .issues-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(360px, 1fr));
            gap: 2rem;
        }

        .issue-card {
            background-color: var(--bg-secondary);
            border: 1px solid var(--border);
            border-radius: 14px;
            padding: 2rem;
            cursor: pointer;
            transition: transform 0.25s, border-color 0.25s, box-shadow 0.25s;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
        }

        .issue-card:hover {
            transform: translateY(-4px);
            border-color: var(--accent-primary);
            box-shadow: 0 12px 24px -10px rgba(0, 0, 0, 0.5);
        }

        .card-header {
            display: flex;
            justify-content: space-between;
            align-items: flex-start;
            margin-bottom: 1rem;
        }

        .card-icon {
            font-size: 2.2rem;
        }

        .badge {
            padding: 0.25rem 0.6rem;
            border-radius: 6px;
            font-size: 0.75rem;
            font-weight: 700;
            text-transform: uppercase;
        }

        .badge-danger { background-color: rgba(244, 63, 94, 0.15); color: var(--danger); }
        .badge-warning { background-color: rgba(251, 191, 36, 0.15); color: var(--warning); }

        .issue-card h3 {
            font-size: 1.4rem;
            font-weight: 700;
            margin-bottom: 0.75rem;
        }

        .issue-card p {
            color: var(--text-muted);
            font-size: 0.95rem;
            margin-bottom: 1.5rem;
        }

        .card-footer {
            border-top: 1px solid var(--border);
            padding-top: 1rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
            font-size: 0.85rem;
            color: var(--accent-primary);
            font-weight: 600;
        }

        /* Detail Modal Drawer */
        .modal-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.75);
            backdrop-filter: blur(4px);
            z-index: 200;
            display: none;
            justify-content: center;
            align-items: center;
            padding: 1.5rem;
        }

        .modal-card {
            background-color: var(--bg-secondary);
            border: 1px solid var(--border);
            border-radius: 16px;
            max-width: 800px;
            width: 100%;
            max-height: 85vh;
            overflow-y: auto;
            padding: 2.5rem;
            position: relative;
        }

        .close-modal {
            position: absolute;
            top: 1.5rem;
            right: 1.5rem;
            background: none;
            border: none;
            color: var(--text-muted);
            font-size: 1.5rem;
            cursor: pointer;
        }

        .modal-title {
            font-size: 2rem;
            margin-bottom: 1rem;
            display: flex;
            align-items: center;
            gap: 0.75rem;
        }

        .modal-section {
            margin-top: 1.5rem;
        }

        .modal-section h4 {
            font-size: 1.1rem;
            color: var(--accent-primary);
            margin-bottom: 0.5rem;
        }

        /* Quiz Widget */
        .quiz-section {
            background: var(--bg-secondary);
            border: 1px solid var(--border);
            border-radius: 16px;
            padding: 3rem 2rem;
            margin-top: 5rem;
            text-align: center;
        }

        .quiz-options {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 1rem;
            max-width: 600px;
            margin: 2rem auto 0;
        }

        .quiz-btn {
            background: var(--bg-card);
            border: 1px solid var(--border);
            color: var(--text-main);
            padding: 1rem;
            border-radius: 8px;
            cursor: pointer;
            font-weight: 500;
            transition: all 0.2s;
        }

        .quiz-btn:hover {
            border-color: var(--accent-primary);
            background: var(--bg-card-hover);
        }

        /* Footer */
        footer {
            border-top: 1px solid var(--border);
            padding: 3rem 2rem;
            text-align: center;
            color: var(--text-muted);
            font-size: 0.9rem;
            margin-top: 5rem;
        }

        @media (max-width: 768px) {
            .hero h1 { font-size: 2.2rem; }
            .quiz-options { grid-template-columns: 1fr; }
            .nav-links { display: none; }
        }
    </style>
</head>
<body>

    <nav>
        <div class="nav-container">
            <a href="#" class="logo">🌍 Global Observatory</a>
            <ul class="nav-links">
                <li><a href="#dashboard">Metrics</a></li>
                <li><a href="#issues">Core Issues</a></li>
                <li><a href="#quiz">Interactive Quiz</a></li>
            </ul>
            <button class="theme-toggle" onclick="toggleTheme()">🌗 Toggle Theme</button>
        </div>
    </nav>

    <header class="hero">
        <span class="hero-badge">Global Issues & Sustainability Analysis</span>
        <h1>Critical Challenges Facing Humanity</h1>
        <p>An interactive intelligence framework documenting global risks, systemic causes, empirical statistics, and strategic pathways toward resolution.</p>

        <div class="filter-container">
            <button class="filter-btn active" onclick="filterIssues('all', this)">All Sectors</button>
            <button class="filter-btn" onclick="filterIssues('environmental', this)">Environmental</button>
            <button class="filter-btn" onclick="filterIssues('socioeconomic', this)">Socio-Economic</button>
            <button class="filter-btn" onclick="filterIssues('rights', this)">Human Rights & Health</button>
        </div>
    </header>

    <main class="container">

        <!-- Global Dashboard Metrics -->
        <section id="dashboard" class="metrics-grid">
            <div class="metric-card">
                <div class="metric-value">+1.15°C</div>
                <div class="metric-title">Global Warming Offset</div>
                <div class="metric-sub">Above pre-industrial baseline average</div>
            </div>
            <div class="metric-card">
                <div class="metric-value">712M</div>
                <div class="metric-title">Extreme Poverty</div>
                <div class="metric-sub">Individuals living on less than $2.15/day</div>
            </div>
            <div class="metric-card">
                <div class="metric-value">110M+</div>
                <div class="metric-title">Forced Displacement</div>
                <div class="metric-sub">Refugees & asylum seekers worldwide</div>
            </div>
            <div class="metric-card">
                <div class="metric-value">2.2B</div>
                <div class="metric-title">Water Stress</div>
                <div class="metric-sub">People lacking safely managed drinking water</div>
            </div>
        </section>

        <!-- Dynamic Grid of Global Issues -->
        <section id="issues">
            <div class="issues-grid" id="issuesContainer">
                <!-- Cards injected dynamically via JS -->
            </div>
        </section>

        <!-- Interactive Knowledge Quiz -->
        <section id="quiz" class="quiz-section">
            <h2>Interactive Knowledge Check</h2>
            <p id="quizQuestion" style="color: var(--text-muted); margin-top: 0.5rem;">According to UN reports, approximately how many people worldwide lack access to safely managed drinking water?</p>
            
            <div class="quiz-options" id="quizOptions">
                <button class="quiz-btn" onclick="checkAnswer(false)">500 Million</button>
                <button class="quiz-btn" onclick="checkAnswer(false)">1.1 Billion</button>
                <button class="quiz-btn" onclick="checkAnswer(true)">2.2 Billion</button>
                <button class="quiz-btn" onclick="checkAnswer(false)">4.5 Billion</button>
            </div>
            <div id="quizResult" style="margin-top: 1.5rem; font-weight: 600;"></div>
        </section>

    </main>

    <!-- Modal Drawer for Extended Details -->
    <div class="modal-overlay" id="modalOverlay" onclick="closeModal(event)">
        <div class="modal-card" onclick="event.stopPropagation()">
            <button class="close-modal" onclick="closeModalDirect()">&times;</button>
            <div id="modalContent"></div>
        </div>
    </div>

    <footer>
        <p>&copy; Global Observatory Project. Educational resource based on datasets from the United Nations, World Bank, and IPCC.</p>
    </footer>

    <script>
        // Complex Knowledge Base Object
        const globalIssuesData = [
            {
                id: "climate",
                category: "environmental",
                badge: "Critical Escalation",
                badgeClass: "badge-danger",
                icon: "🌡️",
                title: "Climate Change & Biosphere Collapse",
                summary: "Anthropogenic greenhouse gas emissions are accelerating atmospheric warming, leading to extreme climatic events, ocean acidification, and rapid biodiversity loss.",
                drivers: "Fossil fuel combustion, deforestation, intensive agriculture, industrial processes.",
                impacts: "Rising sea levels threatening coastal cities, severe droughts, crop yields reduction, displacement of coastal populations.",
                sdg: "SDG 13: Climate Action & SDG 15: Life on Land",
                solution: "Transition to renewable energy networks, global carbon pricing frameworks, reforestation, circular economy implementation."
            },
            {
                id: "poverty",
                category: "socioeconomic",
                badge: "Structural Inequality",
                badgeClass: "badge-danger",
                icon: "📉",
                title: "Global Poverty & Wealth Disparity",
                summary: "Economic power concentration combined with unequal access to financial markets perpetuates systemic poverty across global regions.",
                drivers: "Regressive tax models, political corruption, lack of social safety nets, historical economic exploitation.",
                impacts: "Chronic malnutrition, reduced life expectancy, barrier to higher education, intergenerational inequality.",
                sdg: "SDG 1: No Poverty & SDG 10: Reduced Inequalities",
                solution: "Progressive taxation strategies, universal basic infrastructure, micro-financing access, fair global trade agreements."
            },
            {
                id: "water",
                category: "environmental",
                badge: "Resource Deficit",
                badgeClass: "badge-warning",
                icon: "💧",
                title: "Water Scarcity & Pollution",
                summary: "Aquifer depletion, industrial contamination, and mismanagement leave over two billion people without secure access to clean freshwater.",
                drivers: "Over-extraction for agriculture, untreated industrial runoff, population growth in arid zones.",
                impacts: "Spread of waterborne diseases, geopolitical conflict over river basins, collapse of freshwater ecosystems.",
                sdg: "SDG 6: Clean Water and Sanitation",
                solution: "Advanced desalination powered by renewables, drip irrigation systems, strict industrial discharge regulations."
            },
            {
                id: "food",
                category: "socioeconomic",
                badge: "Distribution Failure",
                badgeClass: "badge-warning",
                icon: "🌾",
                title: "Food Insecurity & Malnutrition",
                summary: "Despite producing sufficient calorie yields globally, inefficient supply chains and geopolitical shocks leave millions undernourished.",
                drivers: "Supply chain disruptions, agricultural vulnerability to climate, post-harvest food waste, armed conflict.",
                impacts: "Child stunting, economic productivity losses, political instability driven by food price inflation.",
                sdg: "SDG 2: Zero Hunger",
                solution: "Climate-resilient crop engineering, localized urban agriculture, food waste reduction programs, supply chain stabilization."
            },
            {
                id: "displacement",
                category: "rights",
                badge: "Humanitarian Crisis",
                badgeClass: "badge-danger",
                icon: "🕊️",
                title: "Forced Displacement & Conflict",
                summary: "Armed conflicts, political prosecution, and environmental degradation have driven global displacement figures to record highs.",
                drivers: "Geopolitical rivalries, civil wars, state fragility, resource competition exacerbated by climate stresses.",
                impacts: "Overburdened humanitarian asylum systems, loss of human capital, long-term psychological trauma for populations.",
                sdg: "SDG 16: Peace, Justice and Strong Institutions",
                solution: "Multilateral diplomacy acceleration, legal protections for climate refugees, sustained foreign aid integration."
            },
            {
                id: "education",
                category: "rights",
                badge: "Access Gap",
                badgeClass: "badge-warning",
                icon: "📚",
                title: "Educational Deficits & Digital Divide",
                summary: "Over 250 million children lack school access, while billions remain disconnected from digital infrastructure essential for modern employment.",
                drivers: "Underfunded public sectors, gender discrimination, rural-urban infrastructure disparities.",
                impacts: "Stunted economic expansion, vulnerability to disinformation, reinforcement of poverty traps.",
                sdg: "SDG 4: Quality Education",
                solution: "Satellite broadband deployment, subsidized public education, global digital literacy initiatives."
            }
        ];

        // Render Issue Cards
        function renderIssues(filter = 'all') {
            const container = document.getElementById('issuesContainer');
            container.innerHTML = '';

            const filteredData = filter === 'all' 
                ? globalIssuesData 
                : globalIssuesData.filter(item => item.category === filter);

            filteredData.forEach(issue => {
                const card = document.createElement('div');
                card.className = 'issue-card';
                card.onclick = () => openModal(issue.id);

                card.innerHTML = `
                    <div>
                        <div class="card-header">
                            <span class="card-icon">${issue.icon}</span>
                            <span class="badge ${issue.badgeClass}">${issue.badge}</span>
                        </div>
                        <h3>${issue.title}</h3>
                        <p>${issue.summary}</p>
                    </div>
                    <div class="card-footer">
                        <span>Explore Analysis & Solutions</span>
                        <span>→</span>
                    </div>
                `;
                container.appendChild(card);
            });
        }

        // Filter Logic
        function filterIssues(category, btnElement) {
            document.querySelectorAll('.filter-btn').forEach(btn => btn.classList.remove('active'));
            btnElement.classList.add('active');
            renderIssues(category);
        }

        // Modal Control
        function openModal(id) {
            const issue = globalIssuesData.find(item => item.id === id);
            if (!issue) return;

            const modalContent = document.getElementById('modalContent');
            modalContent.innerHTML = `
                <div class="modal-title">
                    <span>${issue.icon}</span>
                    <h2>${issue.title}</h2>
                </div>
                <p style="font-size: 1.1rem; color: var(--text-main); margin-bottom: 1.5rem;">${issue.summary}</p>
                
                <div class="modal-section">
                    <h4>Primary Drivers</h4>
                    <p style="color: var(--text-muted);">${issue.drivers}</p>
                </div>

                <div class="modal-section">
                    <h4>Systemic Impacts</h4>
                    <p style="color: var(--text-muted);">${issue.impacts}</p>
                </div>

                <div class="modal-section">
                    <h4>UN Framework Target</h4>
                    <p style="color: var(--text-muted);">${issue.sdg}</p>
                </div>

                <div class="modal-section">
                    <h4>Strategic Action Pathways</h4>
                    <p style="color: var(--text-muted);">${issue.solution}</p>
                </div>
            `;

            document.getElementById('modalOverlay').style.display = 'flex';
        }

        function closeModal(event) {
            if (event.target.id === 'modalOverlay') {
                document.getElementById('modalOverlay').style.display = 'none';
            }
        }

        function closeModalDirect() {
            document.getElementById('modalOverlay').style.display = 'none';
        }

        // Quiz Logic
        function checkAnswer(isCorrect) {
            const resultDiv = document.getElementById('quizResult');
            if (isCorrect) {
                resultDiv.style.color = 'var(--success)';
                resultDiv.innerText = 'Correct! According to WHO and UNICEF, approximately 2.2 billion people lack access to safely managed drinking water.';
            } else {
                resultDiv.style.color = 'var(--danger)';
                resultDiv.innerText = 'Incorrect. The correct answer is 2.2 Billion people.';
            }
        }

        // Theme Switcher
        function toggleTheme() {
            const body = document.body;
            if (body.hasAttribute('data-theme')) {
                body.removeAttribute('data-theme');
            } else {
                body.setAttribute('data-theme', 'light');
            }
        }

        // Initial Load
        renderIssues();
    </script>
</body>
</html>
