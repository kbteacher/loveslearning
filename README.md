<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>1960s Counterculture Learning Hub</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Arial', sans-serif;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4, #45b7d1, #96ceb4, #ffeaa7);
            background-size: 400% 400%;
            animation: psychedelicBg 8s ease infinite;
            min-height: 100vh;
            color: #333;
        }

        @keyframes psychedelicBg {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        .header {
            text-align: center;
            background: rgba(255, 255, 255, 0.95);
            border-radius: 20px;
            padding: 30px;
            margin-bottom: 30px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.2);
            backdrop-filter: blur(10px);
        }

        .header h1 {
            font-size: 3em;
            color: #2c3e50;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.1);
            margin-bottom: 10px;
        }

        .subtitle {
            font-size: 1.2em;
            color: #7f8c8d;
            margin-bottom: 20px;
        }

        .nav-tabs {
            display: flex;
            justify-content: center;
            gap: 10px;
            margin-bottom: 30px;
            flex-wrap: wrap;
        }

        .tab-btn {
            background: rgba(255, 255, 255, 0.9);
            border: none;
            padding: 15px 25px;
            border-radius: 25px;
            cursor: pointer;
            font-size: 1em;
            font-weight: bold;
            color: #2c3e50;
            transition: all 0.3s ease;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }

        .tab-btn:hover, .tab-btn.active {
            background: #e74c3c;
            color: white;
            transform: translateY(-3px);
            box-shadow: 0 10px 25px rgba(0,0,0,0.2);
        }

        .content-section {
            display: none;
            background: rgba(255, 255, 255, 0.95);
            border-radius: 20px;
            padding: 30px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.2);
            backdrop-filter: blur(10px);
            margin-bottom: 20px;
        }

        .content-section.active {
            display: block;
            animation: fadeIn 0.5s ease-in;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .timeline {
            position: relative;
            padding: 20px 0;
        }

        .timeline::before {
            content: '';
            position: absolute;
            left: 50%;
            top: 0;
            bottom: 0;
            width: 4px;
            background: linear-gradient(45deg, #e74c3c, #3498db);
            transform: translateX(-50%);
        }

        .timeline-item {
            display: flex;
            margin-bottom: 30px;
            position: relative;
        }

        .timeline-item:nth-child(even) {
            flex-direction: row-reverse;
        }

        .timeline-content {
            background: white;
            padding: 20px;
            border-radius: 15px;
            width: 45%;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            position: relative;
        }

        .timeline-date {
            position: absolute;
            left: 50%;
            transform: translateX(-50%);
            background: #e74c3c;
            color: white;
            padding: 10px 15px;
            border-radius: 20px;
            font-weight: bold;
            top: 20px;
        }

        .quiz-container {
            background: white;
            border-radius: 15px;
            padding: 25px;
            margin-bottom: 20px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }

        .question {
            font-size: 1.1em;
            font-weight: bold;
            margin-bottom: 15px;
            color: #2c3e50;
        }

        .options {
            display: grid;
            gap: 10px;
            margin-bottom: 20px;
        }

        .option {
            background: #f8f9fa;
            border: 2px solid #e9ecef;
            border-radius: 10px;
            padding: 15px;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .option:hover {
            background: #e3f2fd;
            border-color: #2196f3;
            transform: translateX(5px);
        }

        .option.selected {
            background: #4caf50;
            color: white;
            border-color: #4caf50;
        }

        .option.wrong {
            background: #f44336;
            color: white;
        }

        .gallery {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }

        .gallery-item {
            background: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            transition: transform 0.3s ease;
        }

        .gallery-item:hover {
            transform: scale(1.05);
        }

        .gallery-item img {
            width: 100%;
            height: 200px;
            object-fit: cover;
        }

        .gallery-info {
            padding: 20px;
        }

        .progress-bar {
            background: #ecf0f1;
            border-radius: 10px;
            height: 20px;
            margin: 20px 0;
            overflow: hidden;
        }

        .progress-fill {
            background: linear-gradient(45deg, #e74c3c, #3498db);
            height: 100%;
            border-radius: 10px;
            transition: width 0.5s ease;
            width: 0%;
        }

        .btn {
            background: #e74c3c;
            color: white;
            border: none;
            padding: 12px 25px;
            border-radius: 25px;
            cursor: pointer;
            font-size: 1em;
            font-weight: bold;
            transition: all 0.3s ease;
        }

        .btn:hover {
            background: #c0392b;
            transform: translateY(-2px);
        }

        .interactive-map {
            background: white;
            border-radius: 15px;
            padding: 20px;
            text-align: center;
            min-height: 300px;
            display: flex;
            flex-direction: column;
            justify-content: center;
        }

        .movement-card {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            border-radius: 15px;
            padding: 20px;
            margin: 10px;
            cursor: pointer;
            transition: all 0.3s ease;
            text-align: center;
        }

        .movement-card:hover {
            transform: rotateY(10deg) scale(1.05);
            box-shadow: 0 15px 35px rgba(0,0,0,0.3);
        }

        .reflection-area {
            background: white;
            border-radius: 15px;
            padding: 25px;
            margin: 20px 0;
        }

        .reflection-prompt {
            background: #f8f9fa;
            border-left: 5px solid #e74c3c;
            padding: 20px;
            margin: 15px 0;
            border-radius: 0 10px 10px 0;
        }

        textarea {
            width: 100%;
            min-height: 120px;
            border: 2px solid #e9ecef;
            border-radius: 10px;
            padding: 15px;
            font-family: inherit;
            font-size: 1em;
            resize: vertical;
        }

        .score-display {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            border-radius: 15px;
            padding: 20px;
            text-align: center;
            margin: 20px 0;
        }

        @media (max-width: 768px) {
            .timeline::before {
                left: 20px;
            }
            
            .timeline-item {
                flex-direction: column !important;
                padding-left: 40px;
            }
            
            .timeline-content {
                width: 100%;
            }
            
            .timeline-date {
                left: 20px;
                transform: none;
            }
            
            .header h1 {
                font-size: 2em;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>✌️ 1960s Counterculture Explorer ✌️</h1>
            <p class="subtitle">Journey Through the Revolutionary Decade</p>
            <div class="progress-bar">
                <div class="progress-fill" id="progressBar"></div>
            </div>
        </div>

        <div class="nav-tabs">
            <button class="tab-btn active" onclick="showTab('timeline')">Timeline</button>
            <button class="tab-btn" onclick="showTab('movements')">Movements</button>
            <button class="tab-btn" onclick="showTab('art')">Art & Culture</button>
            <button class="tab-btn" onclick="showTab('quiz')">Knowledge Check</button>
            <button class="tab-btn" onclick="showTab('reflection')">Reflection</button>
        </div>

        <!-- Timeline Section -->
        <div id="timeline" class="content-section active">
            <h2>Key Events Timeline</h2>
            <div class="timeline">
                <div class="timeline-item">
                    <div class="timeline-date">1960</div>
                    <div class="timeline-content">
                        <h3>Birth of the Student Movement</h3>
                        <p>The Student Nonviolent Coordinating Committee (SNCC) is formed, marking the beginning of student activism that would challenge traditional authority structures.</p>
                    </div>
                </div>
                <div class="timeline-item">
                    <div class="timeline-date">1963</div>
                    <div class="timeline-content">
                        <h3>Folk Music Revolution</h3>
                        <p>Bob Dylan's protest songs gain popularity, with music becoming a vehicle for social change and challenging mainstream values.</p>
                    </div>
                </div>
                <div class="timeline-item">
                    <div class="timeline-date">1965</div>
                    <div class="timeline-content">
                        <h3>Vietnam War Protests Begin</h3>
                        <p>Large-scale anti-war demonstrations start, challenging traditional patriotism and military authority.</p>
                    </div>
                </div>
                <div class="timeline-item">
                    <div class="timeline-date">1967</div>
                    <div class="timeline-content">
                        <h3>Summer of Love</h3>
                        <p>San Francisco becomes the epicenter of hippie culture, promoting peace, love, and alternative lifestyles.</p>
                    </div>
                </div>
                <div class="timeline-item">
                    <div class="timeline-date">1969</div>
                    <div class="timeline-content">
                        <h3>Woodstock Festival</h3>
                        <p>Half a million people gather for music and peace, symbolizing the counterculture's peak influence.</p>
                    </div>
                </div>
            </div>
        </div>

        <!-- Movements Section -->
        <div id="movements" class="content-section">
            <h2>Major Counterculture Movements</h2>
            <div class="gallery">
                <div class="movement-card" onclick="showMovementDetails('hippie')">
                    <h3>🌸 Hippie Movement</h3>
                    <p>Peace, love, and alternative lifestyles</p>
                </div>
                <div class="movement-card" onclick="showMovementDetails('antiwar')">
                    <h3>✊ Anti-War Movement</h3>
                    <p>Opposition to Vietnam War</p>
                </div>
                <div class="movement-card" onclick="showMovementDetails('civil')">
                    <h3>🎯 Civil Rights</h3>
                    <p>Fighting for racial equality</p>
                </div>
                <div class="movement-card" onclick="showMovementDetails('feminist')">
                    <h3>👩 Women's Liberation</h3>
                    <p>Gender equality and rights</p>
                </div>
                <div class="movement-card" onclick="showMovementDetails('environmental')">
                    <h3>🌍 Environmental Movement</h3>
                    <p>Earth Day and ecological awareness</p>
                </div>
                <div class="movement-card" onclick="showMovementDetails('free-speech')">
                    <h3>📢 Free Speech Movement</h3>
                    <p>Campus activism and academic freedom</p>
                </div>
            </div>
            <div id="movementDetails" class="reflection-area" style="display: none;">
                <h3 id="movementTitle"></h3>
                <p id="movementDescription"></p>
                <div id="movementValues"></div>
            </div>
        </div>

        <!-- Art & Culture Section -->
        <div id="art" class="content-section">
            <h2>Counterculture Art & Expression</h2>
            <div class="gallery">
                <div class="gallery-item">
                    <div style="background: linear-gradient(45deg, #ff6b6b, #4ecdc4); height: 200px; display: flex; align-items: center; justify-content: center; color: white; font-size: 2em;">🎨</div>
                    <div class="gallery-info">
                        <h3>Psychedelic Art</h3>
                        <p>Bright colors, swirling patterns, and mind-bending visuals that challenged conventional aesthetics and reflected altered consciousness.</p>
                    </div>
                </div>
                <div class="gallery-item">
                    <div style="background: linear-gradient(45deg, #96ceb4, #ffeaa7); height: 200px; display: flex; align-items: center; justify-content: center; color: white; font-size: 2em;">🎵</div>
                    <div class="gallery-info">
                        <h3>Protest Folk Music</h3>
                        <p>Songs that challenged war, inequality, and social injustice. Artists like Bob Dylan used music as a weapon for social change.</p>
                    </div>
                </div>
                <div class="gallery-item">
                    <div style="background: linear-gradient(45deg, #667eea, #764ba2); height: 200px; display: flex; align-items: center; justify-content: center; color: white; font-size: 2em;">🎭</div>
                    <div class="gallery-info">
                        <h3>Underground Comics</h3>
                        <p>R. Crumb and others created comics that mocked mainstream culture and promoted counterculture values.</p>
                    </div>
                </div>
                <div class="gallery-item">
                    <div style="background: linear-gradient(45deg, #fa709a, #fee140); height: 200px; display: flex; align-items: center; justify-content: center; color: white; font-size: 2em;">🎬</div>
                    <div class="gallery-info">
                        <h3>Independent Film</h3>
                        <p>Movies that rejected Hollywood conventions and explored themes of rebellion, alienation, and social critique.</p>
                    </div>
                </div>
            </div>
        </div>

        <!-- Quiz Section -->
        <div id="quiz" class="content-section">
            <h2>Test Your Knowledge</h2>
            <div id="quizContainer">
                <!-- Quiz questions will be loaded here -->
            </div>
            <div class="score-display" id="scoreDisplay" style="display: none;">
                <h3>Your Score: <span id="finalScore">0</span>/10</h3>
                <p id="scoreMessage"></p>
            </div>
        </div>

        <!-- Reflection Section -->
        <div id="reflection" class="content-section">
            <h2>Critical Thinking & Reflection</h2>
            
            <div class="reflection-area">
                <div class="reflection-prompt">
                    <h3>🤔 Analysis Prompt</h3>
                    <p><strong>Do you think members of the counterculture were successful in achieving their goals? Explain why or why not.</strong></p>
                    <p>Consider both immediate and long-term impacts on American society, politics, and culture.</p>
                </div>
                
                <textarea id="reflectionText" placeholder="Write your paragraph response here. Remember to start with a topic sentence stating your position, provide 2-3 supporting details, and end with a concluding sentence..."></textarea>
                
                <button class="btn" onclick="saveReflection()">Save Reflection</button>
                <button class="btn" onclick="provideFeedback()">Get Writing Tips</button>
            </div>

            <div class="reflection-area">
                <h3>📋 Assignment Checklist</h3>
                <div id="checklistItems">
                    <label><input type="checkbox"> 1. Identified two ways counterculture challenged traditional values</label><br>
                    <label><input type="checkbox"> 2. Listed positive and negative aspects of challenging values</label><br>
                    <label><input type="checkbox"> 3. Described two major features of counterculture art</label><br>
                    <label><input type="checkbox"> 4. Explained how art reflected cultural beliefs with example</label><br>
                    <label><input type="checkbox"> 5. Identified what counterculture criticized and why</label><br>
                    <label><input type="checkbox"> 6. Described desired changes to U.S. culture</label><br>
                    <label><input type="checkbox"> 7. Explained motivations for cultural change</label><br>
                    <label><input type="checkbox"> 8. Listed two political causes embraced</label><br>
                    <label><input type="checkbox"> 9. Described three political changes achieved</label><br>
                    <label><input type="checkbox"> 10. Wrote complete paragraph response with proper structure</label><br>
                </div>
            </div>
        </div>
    </div>

    <script>
        let currentQuestionIndex = 0;
        let score = 0;
        let quizCompleted = false;

        const quizQuestions = [
            {
                question: "Which of these was a major way the counterculture challenged traditional U.S. values?",
                options: [
                    "Supporting the Vietnam War",
                    "Rejecting materialism and consumerism",
                    "Promoting traditional gender roles",
                    "Encouraging conformity"
                ],
                correct: 1
            },
            {
                question: "What was a positive aspect of the counterculture's challenge to traditional values?",
                options: [
                    "Increased drug addiction",
                    "Promoted greater equality and civil rights",
                    "Decreased educational standards",
                    "Reduced economic growth"
                ],
                correct: 1
            },
            {
                question: "Which was a major feature of counterculture art?",
                options: [
                    "Traditional realistic styles",
                    "Government-approved themes",
                    "Psychedelic and experimental styles",
                    "Corporate sponsorship"
                ],
                correct: 2
            },
            {
                question: "How did counterculture art reflect artists' beliefs?",
                options: [
                    "By promoting war and violence",
                    "By supporting traditional authority",
                    "By challenging social norms through protest songs and psychedelic visuals",
                    "By avoiding political topics"
                ],
                correct: 2
            },
            {
                question: "What aspect of U.S. culture did the counterculture commonly criticize?",
                options: [
                    "Environmental protection",
                    "The military-industrial complex and war",
                    "Civil rights movements",
                    "Scientific advancement"
                ],
                correct: 1
            },
            {
                question: "What change did the counterculture hope to achieve?",
                options: [
                    "More corporate control",
                    "Increased military spending",
                    "A more peaceful, equal society",
                    "Stricter social conformity"
                ],
                correct: 2
            },
            {
                question: "Why did counterculture members want to change U.S. culture?",
                options: [
                    "They believed current systems promoted inequality and violence",
                    "They wanted to increase corporate profits",
                    "They supported traditional authority structures",
                    "They opposed civil rights"
                ],
                correct: 0
            },
            {
                question: "Which political cause was embraced by the counterculture?",
                options: [
                    "Supporting the Vietnam War",
                    "The Civil Rights Movement",
                    "Increasing military budgets",
                    "Restricting free speech"
                ],
                correct: 1
            },
            {
                question: "What political change resulted partly from counterculture ideals?",
                options: [
                    "Lowering the voting age to 18",
                    "Increasing military drafts",
                    "Restricting protest rights",
                    "Reducing environmental protection"
                ],
                correct: 0
            },
            {
                question: "Which best describes the counterculture's overall impact?",
                options: [
                    "It had no lasting effects",
                    "It only affected music and art",
                    "It contributed to significant social and political changes",
                    "It only influenced young people temporarily"
                ],
                correct: 2
            }
        ];

        const movementData = {
            hippie: {
                title: "Hippie Movement",
                description: "The hippie movement promoted peace, love, and harmony as alternatives to war and materialism. Hippies rejected conventional lifestyles, embraced communal living, and sought spiritual enlightenment.",
                values: "Values: Peace, love, harmony with nature, rejection of materialism, spiritual exploration, communal living"
            },
            antiwar: {
                title: "Anti-War Movement",
                description: "Opposition to the Vietnam War became a central cause, with protests, draft resistance, and moral arguments against military intervention challenging traditional notions of patriotism.",
                values: "Values: Peace, non-violence, questioning authority, moral conscience over blind obedience"
            },
            civil: {
                title: "Civil Rights Movement",
                description: "Fighting for racial equality and justice, challenging segregation and discrimination through peaceful protest and civil disobedience.",
                values: "Values: Equality, justice, human dignity, non-violent resistance, integration"
            },
            feminist: {
                title: "Women's Liberation Movement",
                description: "Challenging traditional gender roles and fighting for equal rights, opportunities, and treatment for women in all aspects of society.",
                values: "Values: Gender equality, personal freedom, reproductive rights, workplace equality"
            },
            environmental: {
                title: "Environmental Movement",
                description: "Growing awareness of environmental destruction led to Earth Day 1970 and efforts to protect nature from industrial pollution.",
                values: "Values: Environmental protection, sustainability, harmony with nature, corporate responsibility"
            },
            'free-speech': {
                title: "Free Speech Movement",
                description: "Campus activism demanding academic freedom and the right to political expression, challenging university authority and restrictions on student activities.",
                values: "Values: Academic freedom, free expression, student rights, democratic participation"
            }
        };

        function showTab(tabName) {
            // Hide all content sections
            const sections = document.querySelectorAll('.content-section');
            sections.forEach(section => section.classList.remove('active'));
            
            // Remove active class from all buttons
            const buttons = document.querySelectorAll('.tab-btn');
            buttons.forEach(btn => btn.classList.remove('active'));
            
            // Show selected section and activate button
            document.getElementById(tabName).classList.add('active');
            event.target.classList.add('active');
            
            // Load quiz if quiz tab is selected
            if (tabName === 'quiz' && !quizCompleted) {
                loadQuiz();
            }
            
            updateProgress();
        }

        function showMovementDetails(movementKey) {
            const details = document.getElementById('movementDetails');
            const data = movementData[movementKey];
            
            document.getElementById('movementTitle').textContent = data.title;
            document.getElementById('movementDescription').textContent = data.description;
            document.getElementById('movementValues').innerHTML = `<strong>${data.values}</strong>`;
            
            details.style.display = 'block';
            details.scrollIntoView({ behavior: 'smooth' });
        }

        function loadQuiz() {
            const container = document.getElementById('quizContainer');
            const existingContent = container.innerHTML;
            
            // Keep any encouragement message that might be there
            if (!existingContent.includes('quiz-container')) {
                // This is a fresh start or retry - keep existing content
            } else {
                container.innerHTML = '';
            }
            
            const questionDiv = document.createElement('div');
            questionDiv.className = 'quiz-container';
            
            const question = quizQuestions[currentQuestionIndex];
            questionDiv.innerHTML = `
                <div style="background: #f8f9fa; padding: 15px; border-radius: 10px; margin-bottom: 20px; text-align: center;">
                    <strong>Question ${currentQuestionIndex + 1} of ${quizQuestions.length}</strong>
                    <div style="margin-top: 10px;">Progress: ${currentQuestionIndex}/${quizQuestions.length} completed</div>
                </div>
                <div class="question">${currentQuestionIndex + 1}. ${question.question}</div>
                <div class="options">
                    ${question.options.map((option, index) => 
                        `<div class="option" onclick="selectAnswer(${index})">${option}</div>`
                    ).join('')}
                </div>
                <button class="btn" onclick="nextQuestion()" id="nextBtn" style="display: none;">
                    ${currentQuestionIndex < quizQuestions.length - 1 ? 'Next Question' : 'See Results'}
                </button>
            `;
            
            container.appendChild(questionDiv);
        }

        function selectAnswer(selectedIndex) {
            const options = document.querySelectorAll('.option');
            const question = quizQuestions[currentQuestionIndex];
            
            options.forEach((option, index) => {
                option.style.pointerEvents = 'none';
                if (index === selectedIndex) {
                    option.classList.add(index === question.correct ? 'selected' : 'wrong');
                } else if (index === question.correct) {
                    option.classList.add('selected');
                }
            });
            
            if (selectedIndex === question.correct) {
                score++;
            }
            
            document.getElementById('nextBtn').style.display = 'block';
        }

        function nextQuestion() {
            currentQuestionIndex++;
            
            if (currentQuestionIndex < quizQuestions.length) {
                loadQuiz();
            } else {
                showQuizResults();
            }
        }

        function showQuizResults() {
            const scoreDisplay = document.getElementById('scoreDisplay');
            const finalScore = document.getElementById('finalScore');
            const scoreMessage = document.getElementById('scoreMessage');
            
            finalScore.textContent = score;
            
            let message = '';
            let passedQuiz = score >= 8; // 80% or higher (8/10)
            
            if (score >= 8) {
                message = 'Excellent! You have a strong understanding of 1960s counterculture! ✨';
                quizCompleted = true;
            } else {
                message = `You scored ${score}/10 (${score * 10}%). You need at least 80% to pass. Please review the material and try again! 📚`;
            }
            
            scoreMessage.innerHTML = message;
            
            // Create retry section if student didn't pass
            if (!passedQuiz) {
                const retrySection = document.createElement('div');
                retrySection.innerHTML = `
                    <div style="margin-top: 20px; padding: 20px; background: #fff3cd; border: 2px solid #ffc107; border-radius: 10px;">
                        <h4 style="color: #856404; margin-bottom: 15px;">📖 Study Recommendations:</h4>
                        <p style="color: #856404; margin-bottom: 15px;">Before retaking the quiz, please review these sections:</p>
                        <ul style="color: #856404; margin-bottom: 15px; text-align: left;">
                            <li>Timeline of key events (1960-1969)</li>
                            <li>Major counterculture movements and their values</li>
                            <li>Art forms and their cultural significance</li>
                            <li>Political causes and changes achieved</li>
                        </ul>
                        <button class="btn" onclick="retakeQuiz()" style="background: #ffc107; color: #856404; margin-right: 10px;">🔄 Retake Quiz</button>
                        <button class="btn" onclick="reviewMaterial()" style="background: #17a2b8; color: white;">📚 Review Material</button>
                    </div>
                `;
                scoreDisplay.appendChild(retrySection);
            }
            
            scoreDisplay.style.display = 'block';
            updateProgress();
        }

        function retakeQuiz() {
            // Reset quiz variables
            currentQuestionIndex = 0;
            score = 0;
            quizCompleted = false;
            
            // Clear and reload quiz
            document.getElementById('quizContainer').innerHTML = '';
            document.getElementById('scoreDisplay').style.display = 'none';
            
            // Add encouraging message
            const encouragementDiv = document.createElement('div');
            encouragementDiv.innerHTML = `
                <div style="background: #d4edda; border: 2px solid #28a745; border-radius: 10px; padding: 20px; margin-bottom: 20px; text-align: center;">
                    <h3 style="color: #155724; margin-bottom: 10px;">🌟 Ready for Round Two!</h3>
                    <p style="color: #155724;">You've got this! Take your time and think carefully about each answer.</p>
                </div>
            `;
            document.getElementById('quizContainer').appendChild(encouragementDiv);
            
            // Start quiz again
            setTimeout(() => {
                loadQuiz();
            }, 1000);
        }

        function reviewMaterial() {
            // Automatically switch to timeline tab and encourage review
            showTab('timeline');
            
            // Add a review guidance popup
            const reviewGuide = document.createElement('div');
            reviewGuide.innerHTML = `
                <div style="position: fixed; top: 50%; left: 50%; transform: translate(-50%, -50%); 
                           background: white; border: 3px solid #e74c3c; border-radius: 15px; 
                           padding: 30px; box-shadow: 0 20px 40px rgba(0,0,0,0.3); z-index: 10000; max-width: 500px;">
                    <h3 style="color: #e74c3c; margin-bottom: 15px;">📚 Study Guide</h3>
                    <p style="margin-bottom: 15px;">Follow this study path for best results:</p>
                    <ol style="text-align: left; margin-bottom: 20px;">
                        <li><strong>Timeline:</strong> Study key dates and events</li>
                        <li><strong>Movements:</strong> Click each movement card to learn details</li>
                        <li><strong>Art & Culture:</strong> Understand how art reflected beliefs</li>
                        <li><strong>Return to Quiz:</strong> Try again when ready!</li>
                    </ol>
                    <button class="btn" onclick="this.parentElement.parentElement.remove()">Got It! 👍</button>
                </div>
                <div style="position: fixed; top: 0; left: 0; width: 100%; height: 100%; 
                           background: rgba(0,0,0,0.5); z-index: 9999;" 
                     onclick="this.parentElement.remove()"></div>
            `;
            document.body.appendChild(reviewGuide);
        }

        function saveReflection() {
            const text = document.getElementById('reflectionText').value;
            if (text.length > 50) {
                alert('Reflection saved! Great work on your analysis. Remember to check your paragraph structure.');
                updateProgress();
            } else {
                alert('Please write a more complete response (at least one full paragraph).');
            }
        }

        function provideFeedback() {
            const tips = `
Writing Tips for Your Paragraph:

1. Topic Sentence: Start with a clear statement of your position
   Example: "The counterculture movement was largely successful in achieving its goals of social change."

2. Supporting Details: Provide 2-3 specific examples
   - Civil rights advances
   - Anti-war movement impact
   - Cultural shifts in values

3. Concluding Sentence: Tie your ideas together
   Example: "While not all goals were immediately achieved, the counterculture fundamentally transformed American society."

4. Use specific evidence from the 1960s to support your argument!
            `;
            alert(tips);
        }

        function updateProgress() {
            let completedSections = 0;
            const totalSections = 5;
            
            // Check if user has engaged with each section
            if (document.querySelector('#timeline').classList.contains('active') || 
                document.querySelector('#timeline').dataset.visited) {
                completedSections++;
                document.querySelector('#timeline').dataset.visited = 'true';
            }
            
            if (document.querySelector('#movementDetails').style.display === 'block') {
                completedSections++;
            }
            
            if (document.querySelector('#art').classList.contains('active') || 
                document.querySelector('#art').dataset.visited) {
                completedSections++;
                document.querySelector('#art').dataset.visited = 'true';
            }
            
            // Only count quiz as completed if student passed (80% or higher)
            if (quizCompleted && score >= 8) {
                completedSections++;
            }
            
            if (document.getElementById('reflectionText').value.length > 50) {
                completedSections++;
            }
            
            const progressPercentage = (completedSections / totalSections) * 100;
            document.getElementById('progressBar').style.width = progressPercentage + '%';
        }

        // Initialize the activity
        document.addEventListener('DOMContentLoaded', function() {
            updateProgress();
            
            // Add event listener for checklist items
            const checkboxes = document.querySelectorAll('#checklistItems input[type="checkbox"]');
            checkboxes.forEach(checkbox => {
                checkbox.addEventListener('change', updateProgress);
            });
            
            // Mark sections as visited when clicked
            const tabs = document.querySelectorAll('.tab-btn');
            tabs.forEach(tab => {
                tab.addEventListener('click', function() {
                    const targetSection = this.onclick.toString().match(/showTab\('(.+)'\)/)[1];
                    document.querySelector(`#${targetSection}`).dataset.visited = 'true';
                });
            });
        });

        // Add some interactive elements
        function createFloatingElements() {
            for (let i = 0; i < 5; i++) {
                const element = document.createElement('div');
                element.innerHTML = ['✌️', '🌸', '☮️', '🎵', '💫'][i];
                element.style.position = 'fixed';
                element.style.fontSize = '2em';
                element.style.pointerEvents = 'none';
                element.style.zIndex = '1000';
                element.style.opacity = '0.7';
                element.style.animation = `float 6s ease-in-out infinite ${i * 0.5}s`;
                
                const style = document.createElement('style');
                style.textContent = `
                    @keyframes float {
                        0%, 100% { transform: translateY(0px) rotate(0deg); }
                        50% { transform: translateY(-20px) rotate(180deg); }
                    }
                `;
                document.head.appendChild(style);
                
                element.style.left = Math.random() * 90 + '%';
                element.style.top = Math.random() * 90 + '%';
                
                document.body.appendChild(element);
                
                setTimeout(() => {
                    element.remove();
                }, 10000);
            }
        }

        // Create floating elements periodically
        setInterval(createFloatingElements, 15000);
        createFloatingElements(); // Initial call
    </script>
</body>
</html># loveslearning
60's Counterculture Activity
