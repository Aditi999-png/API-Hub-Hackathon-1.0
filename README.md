# API-Hub-Hackathon-1.0
Landing Page of the APIman-APIhub Support Bot 
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>APIman - APIhub Support Bot</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600&family=Fira+Code&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary-color: #00bcd4;
            --secondary-color: #008ba3;
            --accent-color: #00e5ff;
            --dark-bg: #121212;
            --dark-surface: #1e1e1e;
            --dark-surface-light: #2d2d2d;
            --dark-text: #e0e0e0;
            --dark-text-secondary: #9e9e9e;
            --success-color: #10b981;
            --warning-color: #f59e0b;
            --danger-color: #ef4444;
            --online-color: #10b981;
            --image-api-color: #8a2be2;
            --video-api-color: #ff5722;
            --jokes-api-color: #ffeb3b;
            --profile-api-color: #4caf50;
        }
        
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, sans-serif;
        }
        
        body {
            background-color: var(--dark-bg);
            color: var(--dark-text);
            line-height: 1.6;
        }
        
        /* Landing Page Styles */
        header.landing-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 40px;
            background-color: var(--dark-surface);
            border-bottom: 1px solid #333;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.3);
        }
        
        header.landing-header h1 {
            font-size: 1.8rem;
            color: var(--primary-color);
            text-shadow: 0 0 10px rgba(0, 188, 212, 0.3);
            animation: glow 2s ease-in-out infinite alternate;
        }
        
        @keyframes glow {
            from {
                text-shadow: 0 0 5px rgba(0, 188, 212, 0.3);
            }
            to {
                text-shadow: 0 0 15px rgba(0, 188, 212, 0.6), 0 0 20px rgba(0, 188, 212, 0.4);
            }
        }
        
        header.landing-header button {
            padding: 10px 20px;
            background-color: var(--primary-color);
            color: #000;
            border: none;
            border-radius: 6px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
        }
        
        header.landing-header button:hover {
            background-color: var(--accent-color);
            transform: translateY(-2px);
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.3);
        }
        
        section {
            padding: 60px 40px;
        }
        
        .features, .team {
            display: flex;
            gap: 20px;
            justify-content: space-around;
            flex-wrap: wrap;
        }
        
        .feature-card, .team-member {
            background-color: var(--dark-surface);
            padding: 20px;
            border-radius: 12px;
            flex: 1;
            min-width: 250px;
            text-align: center;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            transition: all 0.3s;
            border-top: 3px solid var(--primary-color);
        }
        
        .feature-card:hover, .team-member:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 15px rgba(0, 0, 0, 0.2);
        }
        
        .highlight {
            display: flex;
            gap: 40px;
            flex-wrap: wrap;
            align-items: center;
        }
        
        .highlight div {
            flex: 1;
            min-width: 300px;
        }
        
        footer {
            padding: 40px;
            background-color: var(--dark-surface);
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
            border-top: 1px solid #333;
        }
        
        .footer-section {
            background-color: var(--dark-surface-light);
            padding: 20px;
            border-radius: 10px;
            transition: transform 0.3s;
        }
        
        .footer-section:hover {
            transform: translateY(-5px);
        }
        
        .footer-section h3 {
            margin-bottom: 10px;
            color: var(--primary-color);
        }
        
        .graph {
            height: 100px;
            background: linear-gradient(90deg, var(--primary-color) 0%, var(--accent-color) 100%);
            border-radius: 6px;
            animation: gradientBG 5s ease infinite;
            background-size: 200% 200%;
        }
        
        @keyframes gradientBG {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }
        
        /* Chat Interface Styles */
        .chat-header {
            padding: 15px 20px;
            background-color: var(--dark-surface-light);
            color: var(--dark-text);
            font-weight: 600;
            display: flex;
            align-items: center;
            border-bottom: 1px solid var(--dark-surface-light);
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        }
        
        .chat-header::before {
            content: "";
            display: inline-block;
            width: 10px;
            height: 10px;
            background-color: var(--online-color);
            border-radius: 50%;
            margin-right: 10px;
            animation: pulse 2s infinite;
        }
        
        @keyframes pulse {
            0% { transform: scale(0.95); }
            50% { transform: scale(1.1); }
            100% { transform: scale(0.95); }
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }
        
        .chat-container {
            display: flex;
            height: calc(100vh - 180px);
            margin-top: 20px;
            border-radius: 12px;
            overflow: hidden;
            box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.3);
            animation: fadeIn 0.5s ease-out;
        }
        
        .sidebar {
            width: 300px;
            background-color: var(--dark-surface);
            border-right: 1px solid var(--dark-surface-light);
            padding: 20px;
            overflow-y: auto;
            scrollbar-width: thin;
            scrollbar-color: var(--dark-surface-light) var(--dark-surface);
        }
        
        .sidebar::-webkit-scrollbar {
            width: 6px;
        }
        
        .sidebar::-webkit-scrollbar-track {
            background: var(--dark-surface);
        }
        
        .sidebar::-webkit-scrollbar-thumb {
            background-color: var(--dark-surface-light);
            border-radius: 3px;
        }
        
        .chat-area {
            flex: 1;
            display: flex;
            flex-direction: column;
            background-color: var(--dark-surface);
        }
        
        .chat-messages {
            flex: 1;
            padding: 20px;
            overflow-y: auto;
            background-color: var(--dark-surface);
            scrollbar-width: thin;
            scrollbar-color: var(--dark-surface-light) var(--dark-surface);
            background-image: 
                linear-gradient(rgba(30, 30, 30, 0.9), rgba(30, 30, 30, 0.9)),
                url('data:image/svg+xml;utf8,<svg width="100" height="100" viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg"><path d="M30,30 L70,30 L70,70 L30,70 Z" fill="none" stroke="%232d2d2d" stroke-width="0.5"/></svg>');
            background-size: 50px 50px;
        }
        
        .chat-messages::-webkit-scrollbar {
            width: 6px;
        }
        
        .chat-messages::-webkit-scrollbar-track {
            background: var(--dark-surface);
        }
        
        .chat-messages::-webkit-scrollbar-thumb {
            background-color: var(--dark-surface-light);
            border-radius: 3px;
        }
        
        .message {
            margin-bottom: 15px;
            max-width: 75%;
            padding: 12px 16px;
            border-radius: 18px;
            line-height: 1.5;
            position: relative;
            font-size: 0.95rem;
            animation: fadeIn 0.3s ease-out;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .bot-message {
            background-color: var(--dark-surface-light);
            color: var(--dark-text);
            border-radius: 18px 18px 18px 4px;
            align-self: flex-start;
            border-left: 3px solid var(--primary-color);
        }
        
        .user-message {
            background-color: var(--primary-color);
            color: white;
            border-radius: 18px 18px 4px 18px;
            align-self: flex-end;
            margin-left: auto;
            border-right: 3px solid var(--secondary-color);
        }
        
        .ticket-message {
            background-color: rgba(245, 158, 11, 0.15);
            border: 1px solid rgba(245, 158, 11, 0.3);
            border-radius: 10px;
            padding: 15px;
            margin: 15px 0;
            color: var(--dark-text);
            animation: pulse 2s infinite;
        }
        
        .ticket-message h4 {
            color: var(--warning-color);
            margin-bottom: 8px;
        }
        
        .chat-input {
            display: flex;
            padding: 15px;
            background-color: var(--dark-surface-light);
            border-top: 1px solid var(--dark-surface-light);
        }
        
        .chat-input input {
            flex: 1;
            padding: 12px 18px;
            background-color: var(--dark-surface);
            color: var(--dark-text);
            border: 1px solid var(--dark-surface-light);
            border-radius: 25px;
            outline: none;
            font-size: 0.95rem;
            transition: all 0.2s;
            box-shadow: inset 0 1px 3px rgba(0, 0, 0, 0.2);
        }
        
        .chat-input input:focus {
            border-color: var(--accent-color);
            box-shadow: 0 0 0 2px rgba(0, 188, 212, 0.3);
        }
        
        .chat-input input::placeholder {
            color: var(--dark-text-secondary);
        }
        
        .chat-input button {
            background-color: var(--primary-color);
            color: white;
            border: none;
            border-radius: 25px;
            padding: 0 24px;
            margin-left: 12px;
            cursor: pointer;
            font-weight: 500;
            transition: all 0.3s;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
        }
        
        .chat-input button:hover {
            background-color: var(--secondary-color);
            transform: translateY(-2px);
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.3);
        }
        
        .ticket-item {
            padding: 12px;
            margin-bottom: 10px;
            background-color: var(--dark-surface-light);
            border-radius: 8px;
            cursor: pointer;
            transition: all 0.3s;
            border-left: 4px solid var(--warning-color);
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .ticket-item:hover {
            background-color: rgba(0, 188, 212, 0.1);
            transform: translateX(5px);
        }
        
        .ticket-item.resolved {
            border-left-color: var(--success-color);
            opacity: 0.8;
        }
        
        .ticket-item h4 {
            margin-bottom: 5px;
            font-size: 0.95rem;
            font-weight: 500;
            flex: 1;
        }
        
        .ticket-item p {
            font-size: 0.85rem;
            color: var(--dark-text-secondary);
            display: flex;
            align-items: center;
            justify-content: space-between;
        }
        
        .ticket-details {
            display: none;
            padding: 20px;
            background-color: var(--dark-surface-light);
            border-radius: 10px;
            margin-top: 20px;
            animation: fadeIn 0.3s ease-out;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
        }
        
        .ticket-details h3 {
            margin-bottom: 15px;
            color: var(--accent-color);
            font-weight: 600;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .ticket-details .meta {
            display: flex;
            justify-content: space-between;
            margin-bottom: 15px;
            font-size: 0.9em;
            color: var(--dark-text-secondary);
            background-color: var(--dark-surface);
            padding: 10px;
            border-radius: 6px;
        }
        
        .ticket-details .content {
            background-color: var(--dark-surface);
            padding: 15px;
            border-radius: 8px;
            border-left: 3px solid var(--primary-color);
        }
        
        .ticket-details .content h4 {
            margin-bottom: 8px;
            color: var(--accent-color);
            font-weight: 500;
        }
        
        .status-badge {
            display: inline-block;
            padding: 4px 10px;
            border-radius: 12px;
            font-size: 0.8em;
            font-weight: 600;
            text-transform: capitalize;
        }
        
        .status-open {
            background-color: rgba(16, 185, 129, 0.15);
            color: var(--success-color);
        }
        
        .status-pending {
            background-color: rgba(245, 158, 11, 0.15);
            color: var(--warning-color);
        }
        
        .status-resolved {
            background-color: rgba(239, 68, 68, 0.15);
            color: var(--danger-color);
        }
        
        .api-card {
            background-color: var(--dark-surface-light);
            border-radius: 8px;
            padding: 15px;
            margin-bottom: 15px;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s;
            border-top: 3px solid var(--primary-color);
        }
        
        .api-card:hover {
            transform: translateY(-3px);
            box-shadow: 0 5px 10px rgba(0, 0, 0, 0.2);
        }
        
        .api-card.image-api {
            border-top-color: var(--image-api-color);
        }
        
        .api-card.video-api {
            border-top-color: var(--video-api-color);
        }
        
        .api-card.jokes-api {
            border-top-color: var(--jokes-api-color);
        }
        
        .api-card.profile-api {
            border-top-color: var(--profile-api-color);
        }
        
        .api-card h3 {
            color: var(--accent-color);
            margin-bottom: 10px;
            font-size: 1rem;
            font-weight: 600;
            display: flex;
            align-items: center;
            gap: 8px;
        }
        
        .api-card p {
            margin-bottom: 8px;
            font-size: 0.9rem;
            color: var(--dark-text);
        }
        
        .api-card .endpoint {
            font-family: 'Fira Code', monospace;
            background-color: rgba(0, 188, 212, 0.2);
            padding: 2px 6px;
            border-radius: 4px;
            font-size: 0.85rem;
            color: var(--accent-color);
        }
        
        .section-title {
            font-size: 0.9rem;
            text-transform: uppercase;
            letter-spacing: 0.5px;
            color: var(--dark-text-secondary);
            margin: 20px 0 10px 0;
            font-weight: 600;
            display: flex;
            align-items: center;
            gap: 8px;
        }
        
        /* Typography enhancements */
        h1, h2, h3, h4, h5, h6 {
            font-weight: 600;
        }
        
        ul, ol {
            padding-left: 20px;
            margin: 10px 0;
        }
        
        li {
            margin-bottom: 5px;
        }
        
        a {
            color: var(--accent-color);
            text-decoration: none;
            transition: all 0.2s;
        }
        
        a:hover {
            text-decoration: underline;
            color: var(--primary-color);
        }
        
        /* Loading animation */
        .typing-indicator {
            display: flex;
            padding: 10px 15px;
            background-color: var(--dark-surface-light);
            border-radius: 18px;
            width: fit-content;
            margin-bottom: 15px;
        }
        
        .typing-indicator span {
            height: 8px;
            width: 8px;
            background-color: var(--dark-text-secondary);
            border-radius: 50%;
            display: inline-block;
            margin: 0 2px;
            animation: bounce 1.5s infinite ease-in-out;
        }
        
        .typing-indicator span:nth-child(2) {
            animation-delay: 0.2s;
        }
        
        .typing-indicator span:nth-child(3) {
            animation-delay: 0.4s;
        }
        
        @keyframes bounce {
            0%, 60%, 100% { transform: translateY(0); }
            30% { transform: translateY(-5px); }
        }
        
        /* Page transitions */
        .page {
            display: none;
            animation: fadeIn 0.5s ease-out;
        }
        
        .page.active {
            display: block;
        }
        
        /* API icons */
        .api-icon {
            font-size: 1.2rem;
        }
        
        /* Responsive styles */
        @media (max-width: 768px) {
            .chat-container {
                flex-direction: column;
                height: auto;
            }
            
            .sidebar {
                width: 100%;
                border-right: none;
                border-bottom: 1px solid var(--dark-surface-light);
                max-height: 250px;
            }
            
            header.landing-header {
                flex-direction: column;
                gap: 15px;
                padding: 20px;
                text-align: center;
            }
            
            .features, .team {
                flex-direction: column;
            }
            
            .highlight {
                flex-direction: column;
            }
            
            .highlight div {
                order: 2;
            }
            
            .highlight .graph {
                order: 1;
                margin-bottom: 20px;
            }
            
            .message {
                max-width: 85%;
            }
        }
        
        /* Floating action button */
        .fab {
            position: fixed;
            bottom: 30px;
            right: 30px;
            width: 60px;
            height: 60px;
            background-color: var(--primary-color);
            color: white;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.3);
            transition: all 0.3s;
            z-index: 100;
            animation: pulse 2s infinite;
        }
        
        .fab:hover {
            transform: scale(1.1);
            background-color: var(--accent-color);
        }
        
        /* Code blocks */
        .code-block {
            background-color: rgba(0, 0, 0, 0.3);
            border-radius: 6px;
            padding: 12px;
            font-family: 'Fira Code', monospace;
            font-size: 0.85rem;
            margin: 10px 0;
            overflow-x: auto;
            border-left: 3px solid var(--primary-color);
        }
        
        /* Highlight text */
        .highlight-text {
            color: var(--accent-color);
            font-weight: 600;
        }
        
        /* Warning box */
        .warning-box {
            background-color: rgba(245, 158, 11, 0.15);
            border-left: 3px solid var(--warning-color);
            padding: 12px;
            border-radius: 0 6px 6px 0;
            margin: 10px 0;
        }
        
        /* Success box */
        .success-box {
            background-color: rgba(16, 185, 129, 0.15);
            border-left: 3px solid var(--success-color);
            padding: 12px;
            border-radius: 0 6px 6px 0;
            margin: 10px 0;
        }
    </style>
</head>

<body>
    <!-- Floating Action Button -->
    <div class="fab" onclick="showChatInterface()">
        <i class="fas fa-comment-dots" style="font-size: 1.5rem;"></i>
    </div>

    <!-- Landing Page -->
    <div id="landing-page" class="page active">
        <header class="landing-header">
            <h1><i class="fas fa-robot api-icon"></i> APIman: APIhub Support Bot</h1>
            <button onclick="showChatInterface()"><i class="fas fa-comments" style="margin-right: 8px;"></i> Start Chat</button>
        </header>
        
        <section class="features">
            <div class="feature-card">
                <h2><i class="fas fa-brain" style="color: var(--accent-color);"></i> Domain-Specific Chatbot</h2>
                <p>Answers only APIhub-related queries using a curated knowledge base.</p>
            </div>
            <div class="feature-card">
                <h2><i class="fas fa-level-up-alt" style="color: var(--warning-color);"></i> Smart Escalation</h2>
                <p>Auto-generates support tickets when the bot can't resolve issues.</p>
            </div>
            <div class="feature-card">
                <h2><i class="fas fa-ticket-alt" style="color: var(--success-color);"></i> Structured Ticketing</h2>
                <p>Captures ticket ID, timestamp, query, and user info. Sent to admins.</p>
            </div>
        </section>
        
        <section class="highlight">
            <div>
                <h2><i class="fas fa-cogs" style="color: var(--primary-color);"></i> How It Works</h2>
                <p>
                    The <span class="highlight-text">APIman bot</span> helps developers with endpoint details, authentication, rate limits,
                    and error messages. For unresolved queries, it generates a structured support ticket
                    sent to admins with full details.
                </p>
                <button onclick="showChatInterface()" style="margin-top: 20px; padding: 10px 20px; background-color: var(--primary-color); color: #000; border: none; border-radius: 6px; cursor: pointer; font-weight: 600; display: flex; align-items: center; gap: 8px;">
                    <i class="fas fa-bolt"></i> Try It Now
                </button>
            </div>
            <div class="graph"></div>
        </section>
        
        <section class="team">
            <div class="team-member">
                <h3><i class="fas fa-server" style="color: var(--primary-color);"></i> Backend Engineer</h3>
                <p>Built chatbot logic & escalation system</p>
            </div>
            <div class="team-member">
                <h3><i class="fas fa-paint-brush" style="color: var(--accent-color);"></i> Frontend Developer</h3>
                <p>Crafted UI with dark theme support</p>
            </div>
            <div class="team-member">
                <h3><i class="fas fa-user-circle" style="color: var(--warning-color);"></i> UX Designer</h3>
                <p>Designed flow for ticket & chat UX</p>
            </div>
            <div class="team-member">
                <h3><i class="fas fa-tasks" style="color: var(--success-color);"></i> Product Manager</h3>
                <p>Defined challenge goals and APIs</p>
            </div>
        </section>
        
        <section>
            <div class="feature-card">
                <h2><i class="fas fa-star" style="color: var(--jokes-api-color);"></i> Bonus Features</h2>
                <ul>
                    <li><i class="fas fa-envelope" style="color: var(--dark-text-secondary); margin-right: 8px;"></i> Admin email notifications</li>
                    <li><i class="fas fa-chart-bar" style="color: var(--dark-text-secondary); margin-right: 8px;"></i> Dashboard ticket tracker</li>
                    <li><i class="fas fa-clock" style="color: var(--dark-text-secondary); margin-right: 8px;"></i> Auto-escalation timer</li>
                    <li><i class="fas fa-memory" style="color: var(--dark-text-secondary); margin-right: 8px;"></i> Context-aware sessions</li>
                </ul>
            </div>
        </section>
        
        <footer>
            <div class="footer-section">
                <h3><i class="fas fa-link"></i> Quick Links</h3>
                <ul>
                    <li><a href="#"><i class="fas fa-book" style="width: 20px;"></i> Docs</a></li>
                    <li><a href="#"><i class="fas fa-code" style="width: 20px;"></i> API Reference</a></li>
                    <li><a href="#" onclick="showChatInterface()"><i class="fas fa-question-circle" style="width: 20px;"></i> Support</a></li>
                </ul>
            </div>
            <div class="footer-section">
                <h3><i class="fas fa-check-circle"></i> Resolved Tickets</h3>
                <p><span class="highlight-text">1000+</span> cases successfully handled</p>
                <div class="success-box">
                    <i class="fas fa-thumbs-up" style="margin-right: 8px;"></i> 98% satisfaction rate
                </div>
            </div>
            <div class="footer-section">
                <h3><i class="fas fa-chart-line"></i> Ticket Trend</h3>
                <div class="graph"></div>
                <p style="margin-top: 10px; font-size: 0.9rem;"><i class="fas fa-arrow-down" style="color: var(--success-color);"></i> 15% decrease this month</p>
            </div>
        </footer>
    </div>

    <!-- Chat Interface -->
    <div id="chat-interface" class="page">
        <div class="container">
            <div class="chat-container">
                <div class="sidebar">
                    <div class="section-title"><i class="fas fa-plug"></i> Available APIs</div>
                    <div class="api-card">
                        <h3><i class="fas fa-cloud-sun" style="color: var(--primary-color);"></i> Weather API</h3>
                        <p>Provides real-time weather data</p>
                        <p><strong>Endpoints:</strong> <span class="endpoint">/current</span>, <span class="endpoint">/forecast</span></p>
                        <p><strong>Authentication:</strong> API key in X-API-Key header</p>
                        <p><strong>Rate Limit:</strong> 100 requests/hour</p>
                    </div>
                    
                    <div class="api-card">
                        <h3><i class="fas fa-credit-card" style="color: var(--primary-color);"></i> Payment API</h3>
                        <p>Process payments and transactions</p>
                        <p><strong>Endpoints:</strong> <span class="endpoint">/charge</span>, <span class="endpoint">/refund</span></p>
                        <p><strong>Authentication:</strong> OAuth 2.0</p>
                        <p><strong>Rate Limit:</strong> 50 requests/minute</p>
                    </div>
                    
                    <div class="api-card image-api">
                        <h3><i class="fas fa-image" style="color: var(--image-api-color);"></i> Image API</h3>
                        <p>Generate, edit, and process images</p>
                        <p><strong>Endpoints:</strong> <span class="endpoint">/generate</span>, <span class="endpoint">/resize</span>, <span class="endpoint">/filter</span></p>
                        <p><strong>Authentication:</strong> API key</p>
                        <p><strong>Rate Limit:</strong> 200 requests/day</p>
                    </div>
                    
                    <div class="api-card video-api">
                        <h3><i class="fas fa-video" style="color: var(--video-api-color);"></i> Video API</h3>
                        <p>Process and stream video content</p>
                        <p><strong>Endpoints:</strong> <span class="endpoint">/upload</span>, <span class="endpoint">/transcode</span>, <span class="endpoint">/stream</span></p>
                        <p><strong>Authentication:</strong> JWT Token</p>
                        <p><strong>Rate Limit:</strong> 30 requests/minute</p>
                    </div>
                    
                    <div class="api-card jokes-api">
                        <h3><i class="fas fa-laugh-squint" style="color: var(--jokes-api-color);"></i> Jokes API</h3>
                        <p>Get random jokes and puns</p>
                        <p><strong>Endpoints:</strong> <span class="endpoint">/random</span>, <span class="endpoint">/categories</span></p>
                        <p><strong>Authentication:</strong> None</p>
                        <p><strong>Rate Limit:</strong> Unlimited</p>
                    </div>
                    
                    <div class="api-card profile-api">
                        <h3><i class="fas fa-user-circle" style="color: var(--profile-api-color);"></i> Profile Pic API</h3>
                        <p>Generate profile pictures and avatars</p>
                        <p><strong>Endpoints:</strong> <span class="endpoint">/generate</span>, <span class="endpoint">/customize</span></p>
                        <p><strong>Authentication:</strong> API key</p>
                        <p><strong>Rate Limit:</strong> 100 requests/hour</p>
                    </div>
                    
                    <div class="section-title"><i class="fas fa-ticket-alt"></i> Support Tickets</div>
                    <div id="tickets-list">
                        <!-- Tickets will be populated here -->
                    </div>
                    
                    <div id="ticket-details" class="ticket-details">
                        <!-- Ticket details will be shown here -->
                    </div>
                </div>
                
                <div class="chat-area">
                    <div class="chat-header">
                        <i class="fas fa-robot" style="margin-right: 8px;"></i> APIhub Support Bot
                        <button onclick="showLandingPage()" style="margin-left: auto; background: none; border: none; color: var(--accent-color); cursor: pointer; font-size: 0.8rem; display: flex; align-items: center; gap: 5px;">
                            <i class="fas fa-home"></i> Home
                        </button>
                    </div>
                    
                    <div class="chat-messages" id="chat-messages">
                        <div class="message bot-message">
                            <h3 style="margin-bottom: 10px; color: var(--accent-color);"><i class="fas fa-robot"></i> APIhub Support Bot</h3>
                            Hello! I'm the APIhub Support Bot. How can I help you with our APIs today?
                            <br><br>
                            <div class="warning-box">
                                <i class="fas fa-lightbulb" style="margin-right: 8px;"></i> I can help with:
                                <ul style="margin-top: 8px;">
                                    <li>API documentation</li>
                                    <li>Authentication issues</li>
                                    <li>Rate limits</li>
                                    <li>Error messages</li>
                                </ul>
                                If I can't help, I'll automatically create a support ticket for you.
                            </div>
                            <p style="margin-top: 10px;">Try asking about:</p>
                            <div style="display: flex; flex-wrap: wrap; gap: 8px; margin-top: 8px;">
                                <span style="background-color: rgba(0, 188, 212, 0.2); padding: 4px 8px; border-radius: 12px; font-size: 0.8rem;">Weather API endpoints</span>
                                <span style="background-color: rgba(0, 188, 212, 0.2); padding: 4px 8px; border-radius: 12px; font-size: 0.8rem;">Payment API auth</span>
                                <span style="background-color: rgba(0, 188, 212, 0.2); padding: 4px 8px; border-radius: 12px; font-size: 0.8rem;">Image API limits</span>
                            </div>
                        </div>
                    </div>
                    
                    <div class="chat-input">
                        <input type="text" id="user-input" placeholder="Ask about our APIs (e.g. 'How do I authenticate with the Payment API?')" autofocus>
                        <button id="send-button"><i class="fas fa-paper-plane" style="margin-right: 8px;"></i> Send</button>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <script>
        // Page navigation
        function showChatInterface() {
            document.getElementById('landing-page').classList.remove('active');
            document.getElementById('chat-interface').classList.add('active');
            document.getElementById('user-input').focus();
        }
        
        function showLandingPage() {
            document.getElementById('chat-interface').classList.remove('active');
            document.getElementById('landing-page').classList.add('active');
        }
        
        // Chat functionality
        document.addEventListener('DOMContentLoaded', function() {
            const chatMessages = document.getElementById('chat-messages');
            const userInput = document.getElementById('user-input');
            const sendButton = document.getElementById('send-button');
            const ticketsList = document.getElementById('tickets-list');
            const ticketDetails = document.getElementById('ticket-details');
            
            // Sample knowledge base
            const knowledgeBase = {
                "weather_api": {
                    "description": "Provides real-time weather data for any location worldwide.",
                    "endpoints": {
                        "/current": "Get current weather for a location (requires location parameter)",
                        "/forecast": "Get 5-day weather forecast (requires location parameter)",
                        "/historical": "Get historical weather data (requires date range)"
                    },
                    "authentication": "API key in X-API-Key header",
                    "rate_limit": "100 requests/hour",
                    "data_format": "JSON",
                    "errors": {
                        "401": "Invalid API key",
                        "404": "Location not found",
                        "429": "Rate limit exceeded"
                    },
                    "example": `// Example Weather API request
fetch('https://api.apihub.com/weather/current', {
    headers: {
        'X-API-Key': 'your_api_key_here',
        'Content-Type': 'application/json'
    },
    body: JSON.stringify({ location: 'New York' })
})`
                },
                "payment_api": {
                    "description": "Process payments and transactions with multiple payment methods.",
                    "endpoints": {
                        "/charge": "Process a payment (amount, currency, and payment method required)",
                        "/refund": "Issue a refund (transaction ID required)",
                        "/methods": "List available payment methods"
                    },
                    "authentication": "OAuth 2.0 with bearer token",
                    "rate_limit": "50 requests/minute",
                    "data_format": "JSON",
                    "errors": {
                        "400": "Invalid request data",
                        "401": "Unauthorized - invalid token",
                        "402": "Payment failed",
                        "403": "Insufficient permissions"
                    },
                    "example": `// Example Payment API request
const token = 'your_oauth_token_here';
fetch('https://api.apihub.com/payment/charge', {
    method: 'POST',
    headers: {
        'Authorization': 'Bearer ' + token,
        'Content-Type': 'application/json'
    },
    body: JSON.stringify({
        amount: 19.99,
        currency: 'USD',
        method: 'credit_card'
    })
})`
                },
                "image_api": {
                    "description": "Generate, edit, and process images with advanced AI capabilities.",
                    "endpoints": {
                        "/generate": "Generate images from text prompts",
                        "/resize": "Resize images while maintaining quality",
                        "/filter": "Apply artistic filters to images",
                        "/remove-bg": "Remove image backgrounds automatically"
                    },
                    "authentication": "API key in Authorization header",
                    "rate_limit": "200 requests/day",
                    "data_format": "JSON for metadata, binary for images",
                    "errors": {
                        "400": "Invalid image data",
                        "401": "Invalid API key",
                        "413": "Image file too large",
                        "415": "Unsupported image format"
                    },
                    "example": `// Example Image API request
const apiKey = 'your_api_key_here';
fetch('https://api.apihub.com/image/generate', {
    method: 'POST',
    headers: {
        'Authorization': apiKey,
        'Content-Type': 'application/json'
    },
    body: JSON.stringify({
        prompt: 'a sunset over mountains',
        style: 'digital art'
    })
})`
                },
                "video_api": {
                    "description": "Process and stream video content with cloud transcoding.",
                    "endpoints": {
                        "/upload": "Upload video files for processing",
                        "/transcode": "Convert videos to different formats",
                        "/stream": "Get streaming URLs for videos",
                        "/thumbnail": "Generate video thumbnails"
                    },
                    "authentication": "JWT Token in Authorization header",
                    "rate_limit": "30 requests/minute",
                    "data_format": "JSON for metadata, binary for videos",
                    "errors": {
                        "400": "Invalid video parameters",
                        "401": "Invalid JWT token",
                        "415": "Unsupported video format",
                        "429": "Too many concurrent transcodes"
                    },
                    "example": `// Example Video API request
const token = 'your_jwt_token_here';
fetch('https://api.apihub.com/video/transcode', {
    method: 'POST',
    headers: {
        'Authorization': 'Bearer ' + token,
        'Content-Type': 'application/json'
    },
    body: JSON.stringify({
        video_id: '12345',
        format: 'mp4',
        resolution: '1080p'
    })
})`
                },
                "jokes_api": {
                    "description": "Get random jokes, puns, and humorous content for your applications.",
                    "endpoints": {
                        "/random": "Get a random joke",
                        "/categories": "List available joke categories",
                        "/search": "Search jokes by keyword",
                        "/custom": "Create custom jokes with templates"
                    },
                    "authentication": "None (public API)",
                    "rate_limit": "Unlimited (be nice!)",
                    "data_format": "JSON",
                    "errors": {
                        "404": "Category not found",
                        "418": "I'm a teapot (April Fools!)"
                    },
                    "example": `// Example Jokes API request
fetch('https://api.apihub.com/jokes/random')
    .then(response => response.json())
    .then(data => console.log(data.joke));`
                },
                "profile_api": {
                    "description": "Generate profile pictures and avatars based on user data or randomly.",
                    "endpoints": {
                        "/generate": "Generate a profile picture (requires seed or parameters)",
                        "/customize": "Customize an existing profile picture",
                        "/identicon": "Create GitHub-style identicons",
                        "/avatar": "Generate cartoon-style avatars"
                    },
                    "authentication": "API key in X-API-Key header",
                    "rate_limit": "100 requests/hour",
                    "data_format": "JSON for parameters, PNG/SVG for images",
                    "errors": {
                        "400": "Invalid generation parameters",
                        "401": "Invalid API key",
                        "429": "Too many avatar generations"
                    },
                    "example": `// Example Profile API request
fetch('https://api.apihub.com/profile/generate', {
    headers: {
        'X-API-Key': 'your_api_key_here',
        'Content-Type': 'application/json'
    },
    body: JSON.stringify({
        seed: 'user@example.com',
        style: 'geometric'
    })
})`
                },
                "general": {
                    "authentication": "Most APIs require authentication. Common methods include API keys (in X-API-Key header) and OAuth tokens. Always check the specific API documentation for requirements.",
                    "rate_limits": "Rate limits vary by API and your subscription plan. Free tier typically has lower limits. Consider implementing caching if you're hitting rate limits frequently.",
                    "contact": "For issues I can't resolve, I'll create a support ticket for you. You can also email support@apihub.com for urgent matters.",
                    "getting_started": "To get started with any API:\n1. Obtain your API keys from the dashboard\n2. Review the API documentation\n3. Make your first test request\n4. Implement error handling\n5. Monitor your usage",
                    "best_practices": "API Best Practices:\n- Always cache responses when possible\n- Implement exponential backoff for retries\n- Validate all inputs before sending\n- Handle all possible error responses\n- Monitor your API usage metrics"
                }
            };
            
            // Sample tickets data
            let tickets = [
                {
                    id: "TICKET-1001",
                    timestamp: new Date(Date.now() - 86400000).toISOString(),
                    query: "How do I integrate with PayPal?",
                    status: "resolved",
                    response: "We currently don't support PayPal integration directly. You can use our Payment API with credit card processing instead. We've added this as a feature request for future development."
                },
                {
                    id: "TICKET-1002",
                    timestamp: new Date(Date.now() - 3600000).toISOString(),
                    query: "Getting 401 errors with valid API key",
                    status: "open",
                    response: ""
                },
                {
                    id: "TICKET-1003",
                    timestamp: new Date(Date.now() - 7200000).toISOString(),
                    query: "Video API transcoding quality issues",
                    status: "pending",
                    response: "Our engineering team is investigating the quality degradation in 1080p transcodes. Expected resolution time: 24 hours."
                }
            ];
            
            // Display existing tickets
            renderTickets();
            
            // Handle send button click
            sendButton.addEventListener('click', sendMessage);
            
            // Handle Enter key in input field
            userInput.addEventListener('keypress', function(e) {
                if (e.key === 'Enter') {
                    sendMessage();
                }
            });
            
            function sendMessage() {
                const message = userInput.value.trim();
                if (message === '') return;
                
                // Add user message to chat
                addMessage(message, 'user');
                userInput.value = '';
                
                // Show typing indicator
                const typingIndicator = document.createElement('div');
                typingIndicator.classList.add('typing-indicator');
                typingIndicator.innerHTML = '<span></span><span></span><span></span>';
                chatMessages.appendChild(typingIndicator);
                chatMessages.scrollTop = chatMessages.scrollHeight;
                
                // Process the message and get bot response
                setTimeout(() => {
                    // Remove typing indicator
                    chatMessages.removeChild(typingIndicator);
                    
                    const response = processMessage(message);
                    addMessage(response.text, 'bot', response.ticket);
                    
                    // If a ticket was created, update the tickets list
                    if (response.ticket) {
                        tickets.unshift(response.ticket);
                        renderTickets();
                    }
                }, 1000 + Math.random() * 1000); // Random delay for more natural feel
            }
            
            function addMessage(text, sender, ticketData = null) {
                const messageDiv = document.createElement('div');
                messageDiv.classList.add('message');
                
                if (sender === 'user') {
                    messageDiv.classList.add('user-message');
                    messageDiv.innerHTML = `
                        <div style="display: flex; align-items: center; gap: 8px; margin-bottom: 5px;">
                            <i class="fas fa-user" style="font-size: 0.8rem;"></i>
                            <span style="font-weight: 600;">You</span>
                        </div>
                        ${text}
                    `;
                } else {
                    messageDiv.classList.add('bot-message');
                    
                    // Check if the response contains code blocks and format them
                    let formattedText = text;
                    if (text.includes('`')) {
                        formattedText = text.replace(/`([^`]+)`/g, '<code>$1</code>');
                    }
                    
                    messageDiv.innerHTML = `
                        <div style="display: flex; align-items: center; gap: 8px; margin-bottom: 5px;">
                            <i class="fas fa-robot" style="font-size: 0.8rem;"></i>
                            <span style="font-weight: 600;">APIman</span>
                        </div>
                        ${formattedText}
                    `;
                    
                    if (ticketData) {
                        const ticketDiv = document.createElement('div');
                        ticketDiv.classList.add('ticket-message');
                        ticketDiv.innerHTML = `
                            <h4><i class="fas fa-ticket-alt"></i> Support Ticket Created</h4>
                            <p><strong>Ticket ID:</strong> ${ticketData.id}</p>
                            <p><strong>Status:</strong> <span class="status-badge status-${ticketData.status}">${ticketData.status}</span></p>
                            <p>Our team will contact you shortly with a solution.</p>
                            <p style="margin-top: 10px; font-size: 0.9em;"><i class="fas fa-envelope"></i> You'll receive updates at your registered email.</p>
                        `;
                        messageDiv.appendChild(ticketDiv);
                    }
                }
                
                chatMessages.appendChild(messageDiv);
                chatMessages.scrollTop = chatMessages.scrollHeight;
            }
            
            function processMessage(message) {
                const lowerMessage = message.toLowerCase();
                let response = '';
                let ticket = null;
                
                // Check for API-specific questions
                if (lowerMessage.includes('weather api')) {
                    response = handleWeatherAPIQuery(lowerMessage);
                }
                else if (lowerMessage.includes('payment api')) {
                    response = handlePaymentAPIQuery(lowerMessage);
                }
                else if (lowerMessage.includes('image api')) {
                    response = handleImageAPIQuery(lowerMessage);
                }
                else if (lowerMessage.includes('video api')) {
                    response = handleVideoAPIQuery(lowerMessage);
                }
                else if (lowerMessage.includes('jokes api') || lowerMessage.includes('joke api')) {
                    response = handleJokesAPIQuery(lowerMessage);
                }
                else if (lowerMessage.includes('profile api') || lowerMessage.includes('avatar api') || lowerMessage.includes('pic api')) {
                    response = handleProfileAPIQuery(lowerMessage);
                }
                // Check for general questions
                else if (lowerMessage.includes('authentication') || lowerMessage.includes('auth')) {
                    response = `<strong>Authentication Information:</strong><br>${knowledgeBase.general.authentication}`;
                }
                else if (lowerMessage.includes('limit') || lowerMessage.includes('rate')) {
                    response = `<strong>Rate Limit Information:</strong><br>${knowledgeBase.general.rate_limits}`;
                }
                else if (lowerMessage.includes('getting started') || lowerMessage.includes('beginner') || lowerMessage.includes('start')) {
                    response = `<strong>Getting Started:</strong><br>${knowledgeBase.general.getting_started.replace(/\n/g, '<br>')}`;
                }
                else if (lowerMessage.includes('best practice') || lowerMessage.includes('recommendation')) {
                    response = `<strong>API Best Practices:</strong><br>${knowledgeBase.general.best_practices.replace(/\n/g, '<br>')}`;
                }
                else if (lowerMessage.includes('contact support') || lowerMessage.includes('help')) {
                    response = knowledgeBase.general.contact;
                }
                // If we don't have an answer, create a ticket
                else {
                    response = "I couldn't find an answer to your question. I've created a support ticket for you.";
                    ticket = createTicket(message);
                }
                
                return { text: response, ticket };
            }
            
            function handleWeatherAPIQuery(lowerMessage) {
                let response = '';
                if (lowerMessage.includes('authentication') || lowerMessage.includes('auth')) {
                    response = `<strong>Weather API Authentication:</strong><br>${knowledgeBase.weather_api.authentication}`;
                    response += `<div class="code-block">${knowledgeBase.weather_api.example}</div>`;
                } 
                else if (lowerMessage.includes('endpoint') || lowerMessage.includes('endpoints')) {
                    response = `<strong>Weather API Endpoints:</strong><br>`;
                    for (const [endpoint, desc] of Object.entries(knowledgeBase.weather_api.endpoints)) {
                        response += `<span class="endpoint">${endpoint}</span>: ${desc}<br>`;
                    }
                }
                else if (lowerMessage.includes('error') || lowerMessage.includes('code')) {
                    response = `<strong>Weather API Error Codes:</strong><br>`;
                    for (const [code, desc] of Object.entries(knowledgeBase.weather_api.errors)) {
                        response += `<strong>${code}</strong>: ${desc}<br>`;
                    }
                }
                else if (lowerMessage.includes('limit') || lowerMessage.includes('rate')) {
                    response = `<strong>Weather API Rate Limits:</strong><br>${knowledgeBase.weather_api.rate_limit}`;
                    response += `<div class="warning-box"><i class="fas fa-exclamation-triangle"></i> Exceeding rate limits will result in 429 errors. Implement caching if possible.</div>`;
                }
                else {
                    response = `<strong>Weather API:</strong><br>${knowledgeBase.weather_api.description}`;
                }
                return response;
            }
            
            function handlePaymentAPIQuery(lowerMessage) {
                let response = '';
                if (lowerMessage.includes('authentication') || lowerMessage.includes('auth')) {
                    response = `<strong>Payment API Authentication:</strong><br>${knowledgeBase.payment_api.authentication}`;
                    response += `<div class="code-block">${knowledgeBase.payment_api.example}</div>`;
                    response += `<div class="warning-box"><i class="fas fa-lock"></i> Always keep your OAuth tokens secure and never expose them in client-side code.</div>`;
                } 
                else if (lowerMessage.includes('endpoint') || lowerMessage.includes('endpoints')) {
                    response = `<strong>Payment API Endpoints:</strong><br>`;
                    for (const [endpoint, desc] of Object.entries(knowledgeBase.payment_api.endpoints)) {
                        response += `<span class="endpoint">${endpoint}</span>: ${desc}<br>`;
                    }
                }
                else if (lowerMessage.includes('error') || lowerMessage.includes('code')) {
                    response = `<strong>Payment API Error Codes:</strong><br>`;
                    for (const [code, desc] of Object.entries(knowledgeBase.payment_api.errors)) {
                        response += `<strong>${code}</strong>: ${desc}<br>`;
                    }
                }
                else if (lowerMessage.includes('limit') || lowerMessage.includes('rate')) {
                    response = `<strong>Payment API Rate Limits:</strong><br>${knowledgeBase.payment_api.rate_limit}`;
                }
                else {
                    response = `<strong>Payment API:</strong><br>${knowledgeBase.payment_api.description}`;
                }
                return response;
            }
            
            function handleImageAPIQuery(lowerMessage) {
                let response = '';
                if (lowerMessage.includes('authentication') || lowerMessage.includes('auth')) {
                    response = `<strong>Image API Authentication:</strong><br>${knowledgeBase.image_api.authentication}`;
                    response += `<div class="code-block">${knowledgeBase.image_api.example}</div>`;
                } 
                else if (lowerMessage.includes('endpoint') || lowerMessage.includes('endpoints')) {
                    response = `<strong>Image API Endpoints:</strong><br>`;
                    for (const [endpoint, desc] of Object.entries(knowledgeBase.image_api.endpoints)) {
                        response += `<span class="endpoint">${endpoint}</span>: ${desc}<br>`;
                    }
                    response += `<div class="success-box"><i class="fas fa-lightbulb"></i> Try the /remove-bg endpoint for automatic background removal - no green screen needed!</div>`;
                }
                else if (lowerMessage.includes('error') || lowerMessage.includes('code')) {
                    response = `<strong>Image API Error Codes:</strong><br>`;
                    for (const [code, desc] of Object.entries(knowledgeBase.image_api.errors)) {
                        response += `<strong>${code}</strong>: ${desc}<br>`;
                    }
                }
                else if (lowerMessage.includes('limit') || lowerMessage.includes('rate')) {
                    response = `<strong>Image API Rate Limits:</strong><br>${knowledgeBase.image_api.rate_limit}`;
                }
                else if (lowerMessage.includes('generate') || lowerMessage.includes('creation')) {
                    response = `<strong>Image Generation:</strong><br>Our AI can generate images from text prompts. Use the <span class="endpoint">/generate</span> endpoint with a description of what you want.<br><br>`;
                    response += `<strong>Example:</strong> "a futuristic city at night with neon lights"`;
                }
                else {
                    response = `<strong>Image API:</strong><br>${knowledgeBase.image_api.description}`;
                    response += `<div style="margin-top: 10px;"><i class="fas fa-magic" style="color: var(--image-api-color);"></i> <strong>Pro Tip:</strong> Our AI understands artistic styles like "digital art", "watercolor", or "pixel art".</div>`;
                }
                return response;
            }
            
            function handleVideoAPIQuery(lowerMessage) {
                let response = '';
                if (lowerMessage.includes('authentication') || lowerMessage.includes('auth')) {
                    response = `<strong>Video API Authentication:</strong><br>${knowledgeBase.video_api.authentication}`;
                    response += `<div class="code-block">${knowledgeBase.video_api.example}</div>`;
                } 
                else if (lowerMessage.includes('endpoint') || lowerMessage.includes('endpoints')) {
                    response = `<strong>Video API Endpoints:</strong><br>`;
                    for (const [endpoint, desc] of Object.entries(knowledgeBase.video_api.endpoints)) {
                        response += `<span class="endpoint">${endpoint}</span>: ${desc}<br>`;
                    }
                }
                else if (lowerMessage.includes('error') || lowerMessage.includes('code')) {
                    response = `<strong>Video API Error Codes:</strong><br>`;
                    for (const [code, desc] of Object.entries(knowledgeBase.video_api.errors)) {
                        response += `<strong>${code}</strong>: ${desc}<br>`;
                    }
                }
                else if (lowerMessage.includes('limit') || lowerMessage.includes('rate')) {
                    response = `<strong>Video API Rate Limits:</strong><br>${knowledgeBase.video_api.rate_limit}`;
                    response += `<div class="warning-box"><i class="fas fa-exclamation-triangle"></i> Video processing consumes significant resources. Please batch operations when possible.</div>`;
                }
                else if (lowerMessage.includes('transcode') || lowerMessage.includes('convert')) {
                    response = `<strong>Video Transcoding:</strong><br>Our cloud transcoding supports:<br>`;
                    response += `<ul>
                        <li>Formats: MP4, WebM, MOV, AVI</li>
                        <li>Resolutions: 240p to 4K</li>
                        <li>Codecs: H.264, H.265, VP9</li>
                    </ul>`;
                }
                else {
                    response = `<strong>Video API:</strong><br>${knowledgeBase.video_api.description}`;
                }
                return response;
            }
            
            function handleJokesAPIQuery(lowerMessage) {
                let response = '';
                if (lowerMessage.includes('endpoint') || lowerMessage.includes('endpoints')) {
                    response = `<strong>Jokes API Endpoints:</strong><br>`;
                    for (const [endpoint, desc] of Object.entries(knowledgeBase.jokes_api.endpoints)) {
                        response += `<span class="endpoint">${endpoint}</span>: ${desc}<br>`;
                    }
                    response += `<div class="code-block">${knowledgeBase.jokes_api.example}</div>`;
                }
                else if (lowerMessage.includes('category') || lowerMessage.includes('type')) {
                    response = `<strong>Joke Categories:</strong><br>`;
                    response += `<ul>
                        <li>Programming</li>
                        <li>Puns</li>
                        <li>Knock-knock</li>
                        <li>Dad jokes</li>
                        <li>One-liners</li>
                    </ul>`;
                    response += `Use the <span class="endpoint">/categories</span> endpoint for the full list.`;
                }
                else if (lowerMessage.includes('example') || lowerMessage.includes('sample')) {
                    response = `<strong>Joke Example:</strong><br>`;
                    response += `Why do programmers prefer dark mode?<br>Because light attracts bugs!`;
                    response += `<div style="margin-top: 10px;"><i class="fas fa-grin-squint-tears" style="color: var(--jokes-api-color);"></i> Want more? Try the <span class="endpoint">/random</span> endpoint!</div>`;
                }
                else {
                    response = `<strong>Jokes API:</strong><br>${knowledgeBase.jokes_api.description}`;
                    response += `<div style="margin-top: 10px;"><i class="fas fa-laugh-beam" style="color: var(--jokes-api-color);"></i> This API is completely free with no authentication required!</div>`;
                }
                return response;
            }
            
            function handleProfileAPIQuery(lowerMessage) {
                let response = '';
                if (lowerMessage.includes('authentication') || lowerMessage.includes('auth')) {
                    response = `<strong>Profile API Authentication:</strong><br>${knowledgeBase.profile_api.authentication}`;
                    response += `<div class="code-block">${knowledgeBase.profile_api.example}</div>`;
                } 
                else if (lowerMessage.includes('endpoint') || lowerMessage.includes('endpoints')) {
                    response = `<strong>Profile API Endpoints:</strong><br>`;
                    for (const [endpoint, desc] of Object.entries(knowledgeBase.profile_api.endpoints)) {
                        response += `<span class="endpoint">${endpoint}</span>: ${desc}<br>`;
                    }
                }
                else if (lowerMessage.includes('style') || lowerMessage.includes('type')) {
                    response = `<strong>Avatar Styles:</strong><br>`;
                    response += `<ul>
                        <li>Geometric</li>
                        <li>Pixel art</li>
                        <li>Minimalist</li>
                        <li>Cartoon</li>
                        <li>Abstract</li>
                    </ul>`;
                }
                else if (lowerMessage.includes('generate') || lowerMessage.includes('create')) {
                    response = `<strong>Generating Profile Pictures:</strong><br>`;
                    response += `You can generate avatars based on:<br>
                    <ul>
                        <li>Email addresses</li>
                        <li>Usernames</li>
                        <li>Random seeds</li>
                        <li>Initials</li>
                    </ul>`;
                    response += `<div class="code-block">${knowledgeBase.profile_api.example}</div>`;
                }
                else {
                    response = `<strong>Profile API:</strong><br>${knowledgeBase.profile_api.description}`;
                }
                return response;
            }
            
            function createTicket(query) {
                const ticketId = `TICKET-${1000 + tickets.length + 1}`;
                const timestamp = new Date().toISOString();
                
                const ticket = {
                    id: ticketId,
                    timestamp,
                    query,
                    status: "open",
                    response: ""
                };
                
                // In a real app, you would send this to your backend
                console.log("Ticket created:", ticket);
                
                return ticket;
            }
            
            function renderTickets() {
                ticketsList.innerHTML = '';
                
                if (tickets.length === 0) {
                    ticketsList.innerHTML = '<p style="color: var(--dark-text-secondary); font-size: 0.9rem;"><i class="fas fa-check-circle"></i> No active tickets</p>';
                    return;
                }
                
                tickets.forEach(ticket => {
                    const ticketDiv = document.createElement('div');
                    ticketDiv.classList.add('ticket-item');
                    if (ticket.status === 'resolved') {
                        ticketDiv.classList.add('resolved');
                    }
                    
                    const date = new Date(ticket.timestamp);
                    const timeString = date.toLocaleTimeString([], { hour: '2-digit', minute: '2-digit' });
                    
                    ticketDiv.innerHTML = `
                        <i class="fas fa-ticket-alt" style="color: ${ticket.status === 'resolved' ? 'var(--success-color)' : ticket.status === 'pending' ? 'var(--warning-color)' : 'var(--primary-color)'}"></i>
                        <div style="flex: 1;">
                            <h4>${ticket.query.substring(0, 30)}${ticket.query.length > 30 ? '...' : ''}</h4>
                            <p>${timeString} <span class="status-badge status-${ticket.status}">${ticket.status}</span></p>
                        </div>
                        <i class="fas fa-chevron-right" style="color: var(--dark-text-secondary);"></i>
                    `;
                    
                    ticketDiv.addEventListener('click', () => showTicketDetails(ticket));
                    ticketsList.appendChild(ticketDiv);
                });
            }
            
            function showTicketDetails(ticket) {
                const date = new Date(ticket.timestamp);
                const dateString = date.toLocaleDateString();
                const timeString = date.toLocaleTimeString();
                
                ticketDetails.innerHTML = `
                    <h3><i class="fas fa-ticket-alt"></i> Ticket Details</h3>
                    <div class="meta">
                        <span><strong>ID:</strong> ${ticket.id}</span>
                        <span><strong>Status:</strong> <span class="status-badge status-${ticket.status}">${ticket.status}</span></span>
                    </div>
                    <div class="meta">
                        <span><strong>Date:</strong> ${dateString}</span>
                        <span><strong>Time:</strong> ${timeString}</span>
                    </div>
                    <div class="content">
                        <h4><i class="fas fa-question-circle"></i> Original Query:</h4>
                        <p>${ticket.query}</p>
                        
                        ${ticket.response ? `
                            <h4><i class="fas fa-reply"></i> Response:</h4>
                            <p>${ticket.response}</p>
                        ` : '<p><em><i class="fas fa-spinner fa-pulse"></i> No response yet - our team is working on it</em></p>'}
                    </div>
                    ${ticket.status !== 'resolved' ? `
                    <div style="margin-top: 15px; display: flex; gap: 10px;">
                        <button style="padding: 8px 15px; background-color: var(--primary-color); border: none; border-radius: 4px; cursor: pointer;"><i class="fas fa-thumbs-up"></i> Helpful</button>
                        <button style="padding: 8px 15px; background-color: var(--dark-surface); border: 1px solid var(--dark-surface-light); color: var(--dark-text); border-radius: 4px; cursor: pointer;"><i class="fas fa-comment"></i> Add Comment</button>
                    </div>
                    ` : ''}
                `;
                
                ticketDetails.style.display = 'block';
            }
        });
    </script>
</body>
</html>
