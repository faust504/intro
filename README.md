<!DOCTYPE html>

<html lang="en">
<head>
<meta charset="utf-8"/>
<meta content="width=device-width, initial-scale=1.0" name="viewport"/>
<title>90icetea Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&amp;family=Montserrat:wght@400;500;700&amp;display=swap" rel="stylesheet"/>
<style>
        :root {
            --bg: #1a1a1a;
            --panel: #252525;
            --muted: #8b8b8b;
            --accent: #e0e0e0;
            --border: #3a3a3a;
            --inner-shadow: rgba(0,0,0,0.3);
            --radius: 12px;
            --grid-color: #333;
            --grid-highlight: #444;
        }

        /* Moving grid background */
        @keyframes moveGrid {
            0% { background-position: 0 0, 0 0; }
            100% { background-position: 0 44px, 0 44px; }
        }

        html, body { 
            height: 100%; 
            margin: 0;
            padding: 0;
        }
        
        body {
            font-family: 'Poppins', 'Segoe UI', 'Montserrat', 'Roboto', 'Helvetica Neue', sans-serif;
            background-color: var(--bg);
            background-image: 
                linear-gradient(90deg, var(--grid-color) 1px, transparent 1px),
                linear-gradient(var(--grid-color) 1px, transparent 1px);
            background-size: 44px 44px;
            background-position: 0 0;
            animation: moveGrid 10s linear infinite;
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 20px;
            color: var(--accent);
            -webkit-font-smoothing: antialiased;
            -moz-osx-font-smoothing: grayscale;
        }

        /* outer window */
        .window {
            width: 820px;
            max-width: calc(100% - 40px);
            height: 600px;
            max-height: calc(100vh - 40px);
            background: var(--panel);
            border-radius: 14px;
            border: 2px solid var(--border);
            box-shadow: 0 8px 18px var(--inner-shadow);
            overflow: hidden;
            display: flex;
            flex-direction: column;
        }

        /* top bar */
        .topbar {
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 10px;
            background: linear-gradient(#2c2c2c, #252525);
            border-bottom: 1px solid var(--border);
            flex-shrink: 0;
        }
        
        .window-controls {
            display: flex;
            gap: 8px;
            padding-right: 8px;
        }
        
        .btn-circle {
            width: 18px; 
            height: 18px; 
            border-radius: 4px; 
            border: 1px solid #3a3a3a; 
            background: #333;
            display: inline-flex; 
            align-items: center; 
            justify-content: center; 
            font-size: 11px; 
            color: #999;
            box-shadow: inset 0 1px 0 rgba(255,255,255,0.1);
        }
        
        .url {
            flex: 1;
            display: flex;
            align-items: center;
            gap: 8px;
            padding: 0 10px;
        }
        
        .url input {
            width: 100%;
            border-radius: 6px;
            border: 1px solid #333;
            padding: 8px 10px;
            background: #1f1f1f;
            font-size: 13px;
            color: #e0e0e0;
            font-family: 'Poppins', sans-serif;
        }
        
        .title-badge {
            display: flex;
            align-items: center;
            gap: 8px;
            font-size: 12px;
            color: var(--muted);
            min-width: 120px;
            font-family: 'Montserrat', sans-serif;
        }

        /* tabs */
        .tabs {
            display: flex;
            align-items: center;
            justify-content: space-between;
            background: #2c2c2c;
            border-bottom: 1px solid var(--border);
            flex-shrink: 0;
        }
        
        .tab-list {
            display: flex;
            gap: 8px;
            padding: 8px 12px;
        }
        
        .tab {
            padding: 10px 14px;
            font-weight: 600;
            background: transparent;
            border-radius: 6px 6px 0 0;
            border-bottom: 3px solid transparent;
            cursor: pointer;
            color: #bbb;
            font-family: 'Montserrat', sans-serif;
            transition: all 0.2s ease;
        }
        
        .tab.active {
            background: linear-gradient(#333, #2a2a2a);
            border-bottom-color: #e0e0e0;
            color: #fff;
        }
        
        .tab-right {
            padding-right: 12px;
            color: var(--muted);
            font-size: 13px;
        }

        /* main area - FIXED SCROLLING */
        .content {
            flex: 1;
            overflow-y: auto;
            overflow-x: hidden;
            scrollbar-width: thin;
            scrollbar-color: #333 #1a1a1a;
        }

        .content::-webkit-scrollbar {
            width: 10px;
        }
        .content::-webkit-scrollbar-track {
            background: #1a1a1a;
        }
        .content::-webkit-scrollbar-thumb {
            background: #333;
            border-radius: 6px;
        }
        .content::-webkit-scrollbar-thumb:hover {
            background: #555;
        }

        /* Tab content containers */
        .tab-content {
            display: none;
            padding: 14px;
            min-height: 100%;
            box-sizing: border-box;
        }

        #main-tab {
            display: flex;
            gap: 14px;
        }

        /* left column */
        .left {
            width: 220px;
            min-width: 180px;
            flex-shrink: 0;
        }
        
        .card {
            background: linear-gradient(#2f2f2f, #292929);
            border: 1px solid var(--border);
            padding: 12px;
            border-radius: 8px;
            margin-bottom: 12px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
        }
        
        .small-h {
            font-weight: 700; 
            color: #f0f0f0; 
            margin: 0 0 8px 0; 
            font-size: 14px;
            font-family: 'Montserrat', sans-serif;
        }
        
        .find-list {
            counter-reset: item;
            padding-left: 8px;
            color: #ddd;
        }
        
        .find-list li {
            list-style: none;
            padding: 8px 0;
            border-bottom: 1px dashed #3a3a3a;
            position: relative;
            padding-left: 28px;
            font-size: 14px;
            transition: background 0.2s;
        }
        
        .find-list li:hover {
            background: rgba(255,255,255,0.05);
        }
        
        .find-list li::before {
            counter-increment: item;
            content: counter(item) ".";
            position: absolute;
            left: 6px; 
            top: 8px;
            color: var(--muted);
            font-weight: 700;
        }
        
        .social-link {
            display: flex;
            align-items: center;
            gap: 8px;
            color: #ddd;
            text-decoration: none;
            transition: color 0.2s;
        }
        
        .social-link:hover {
            color: #fff;
        }
        
        .social-icon {
            width: 16px;
            height: 16px;
            display: inline-block;
            background-size: contain;
            background-repeat: no-repeat;
        }

        /* center column */
        .center {
            flex: 1;
            min-width: 340px;
            display: flex;
            flex-direction: column;
        }
        
        .avatar-row {
            display: flex;
            gap: 12px;
            align-items: center;
        }
        
        .avatar {
            width: 110px; 
            height: 110px; 
            border-radius: 8px;
            border: 1px solid var(--border);
            overflow: hidden;
            box-shadow: 0 4px 8px rgba(0,0,0,0.2);
            flex-shrink: 0;
        }
        
        .avatar img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .meta {
            flex: 1;
            padding: 6px 0;
        }
        
        .meta h2 {
            margin: 0; 
            font-size: 18px; 
            font-family: 'Montserrat', sans-serif;
            color: #fff;
        }
        
        .meta p {
            margin: 6px 0; 
            color: var(--muted); 
            font-size: 13px;
            line-height: 1.4;
        }
        
        .mood {
            font-weight: 700; 
            margin-top: 8px; 
            color: #ddd; 
            font-size: 13px;
            font-style: italic;
        }

        /* now playing bar */
        .playing {
            margin-top: 12px;
            display: block;
            border-top: 1px solid var(--border);
            padding-top: 10px;
        }
        
        .playing .track {
            display: flex;
            align-items: center;
            gap: 10px;
            font-weight: 600;
            color: #ddd;
            font-size: 13px;
        }
        
        .player-controls {
            display: flex;
            gap: 8px;
            align-items: center;
            margin-top: 8px;
        }
        
        .play-btn {
            width: 28px; 
            height: 28px; 
            border-radius: 6px; 
            border: 1px solid var(--border); 
            display: inline-flex; 
            align-items: center; 
            justify-content: center; 
            cursor: pointer;
            background: #333;
            color: #ddd;
            transition: all 0.2s;
        }
        
        .play-btn:hover {
            background: #3a3a3a;
        }
        
        .progress-row {
            display: flex; 
            align-items: center; 
            gap: 8px; 
            margin-top: 6px;
        }
        
        .time {
            font-size: 12px; 
            color: var(--muted); 
            width: 46px; 
            text-align: center;
        }
        
        input[type="range"] {
            -webkit-appearance: none;
            appearance: none;
            height: 6px; 
            background: #3a3a3a; 
            border-radius: 6px; 
            flex: 1;
        }
        
        input[type=range]::-webkit-slider-thumb { 
            -webkit-appearance: none; 
            appearance: none; 
            width: 12px;
            height: 12px;
            border-radius: 50%;
            background: #fff; 
            border: 2px solid #1a1a1a; 
            box-shadow: 0 0 0 1px #555;
            cursor: pointer;
        }

        /* gallery + side boxes - RESTRUCTURED */
        .media-row {
            display: flex; 
            gap: 12px; 
            margin-top: 12px;
            flex: 1;
        }
        
        .main-content-area {
            display: flex;
            gap: 12px;
            flex: 1;
        }

        .panel-left {
            flex: 1;
            border: 1px solid var(--border);
            border-radius: 8px;
            overflow: hidden;
            background: linear-gradient(#2f2f2f, #292929);
            display: flex;
            flex-direction: column;
        }
        
        .image-placeholder {
            height: 150px; 
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            padding: 8px;
            background: repeating-radial-gradient(circle at 10% 10%, #333 0 3px, #252525 3px 6px);
        }
        
        .image-placeholder .manga {
            width: 100%; 
            height: 100%; 
            display: block; 
            object-fit: cover;
        }
        
        .panel-right {
            width: 220px;
            min-width: 190px;
            display: flex;
            flex-direction: column;
            gap: 8px;
        }
        
        .info-box {
            border: 1px solid var(--border); 
            padding: 10px; 
            border-radius: 6px; 
            background: #2a2a2a;
            flex: 1;
        }
        
        .info-box h4 {
            margin: 0 0 6px 0; 
            font-size: 13px; 
            font-family: 'Montserrat', sans-serif;
            color: #f0f0f0;
        }
        
        .info-box p {
            margin: 0; 
            font-size: 13px; 
            color: #ddd;
            line-height: 1.4;
        }

        /* REPOSITIONED bottom note - spans full width */
        .note {
            margin-top: 12px;
            font-size: 13px;
            color: #ddd;
            border-top: 1px dashed #444;
            padding-top: 10px;
            grid-column: 1 / -1; /* Span full width */
        }
        
        .dninote {
            font-size: 12px; 
            color: var(--muted); 
            margin-top: 8px;
        }

        /* Interests section */
        .interests {
            font-size: 13px;
            color: #fff;
            line-height: 1.6;
            padding: 8px 0;
        }

        /* Portfolio section - FIXED SCROLLING */
        .portfolio-content {
            display: none;
            flex-direction: column;
            width: 100%;
            height: 100%;
            padding: 10px;
        }
        
        .portfolio-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
            gap: 16px;
            margin-top: 15px;
            flex: 1;
        }
        
        .portfolio-item {
            background: #2a2a2a;
            border: 1px solid var(--border);
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 2px 6px rgba(0,0,0,0.1);
            transition: transform 0.2s, box-shadow 0.2s;
            display: flex;
            flex-direction: column;
        }
        
        .portfolio-item:hover {
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
        }
        
        .portfolio-image {
            height: 140px;
            background: linear-gradient(45deg, #333, #2a2a2a);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 40px;
            color: #555;
            border-bottom: 1px solid var(--border);
            flex-shrink: 0;
            background-size: cover;
            background-position: center;
            background-repeat: no-repeat;
        }
        
        .portfolio-desc {
            padding: 12px;
            font-size: 13px;
            line-height: 1.4;
            flex: 1;
        }
        
        .portfolio-desc h4 {
            margin: 0 0 6px 0;
            color: #f0f0f0;
            font-size: 14px;
            font-family: 'Montserrat', sans-serif;
        }
        
        .portfolio-desc p {
            color: #ccc;
            margin: 0;
        }
        
        /* Misc section */
        .misc-content {
            display: none;
            padding: 20px;
            text-align: center;
            color: var(--muted);
            font-size: 14px;
            height: 100%;
            flex-direction: column;
            align-items: center;
            justify-content: center;
        }

        /* utility */
        .muted { color: var(--muted) }
        .btn {
            padding: 6px 8px; 
            border-radius: 6px; 
            border: 1px solid var(--border); 
            background: #333; 
            cursor: pointer; 
            font-size: 13px;
            color: #ddd;
            transition: all 0.2s;
            font-family: 'Poppins', sans-serif;
        }
        
        .btn:hover {
            background: #3a3a3a;
            border-color: #555;
        }
        
        .linklike {
            color: #ddd; 
            text-decoration: underline; 
            cursor: pointer;
            transition: color 0.2s;
        }
        
        .linklike:hover {
            color: #fff;
        }

        /* MOBILE RESPONSIVE - FIXED */
        @media (max-width: 820px) {
            body {
                padding: 10px;
            }
            
            .window {
                width: 100%;
                max-width: none;
                height: 100vh;
                max-height: 100vh;
                margin: 0;
            }
            
            #main-tab {
                flex-direction: column;
                gap: 14px;
            }
            
            .left { 
                width: 100%;
                order: 1;
            }
            
            .center {
                width: 100%;
                min-width: auto;
                order: 2;
            }
            
            .media-row { 
                flex-direction: column;
                gap: 12px;
            }
            
            .main-content-area {
                flex-direction: column;
                gap: 12px;
            }
            
            .panel-right { 
                width: 100%;
                flex-direction: row;
                gap: 8px;
            }
            
            .info-box {
                flex: 1;
            }
            
            .portfolio-grid {
                grid-template-columns: 1fr;
            }
            
            .avatar-row {
                flex-direction: column;
                text-align: center;
            }
            
            .avatar {
                align-self: center;
            }
        }

        @media (max-width: 600px) {
            .panel-right {
                flex-direction: column;
                gap: 8px;
            }
            
            .topbar {
                padding: 8px;
            }
            
            .title-badge {
                min-width: auto;
                font-size: 11px;
            }
            
            .url input {
                font-size: 12px;
                padding: 6px 8px;
            }
        }
</style>
</head>
<body>
<div aria-label="profile window" class="window" role="application">
<div class="topbar">
<div class="title-badge"> 90icetea introduction.</div>
<div class="url" role="search">
<input aria-label="address" value="https://90icetea.github.io"/>
</div>
<div aria-hidden="true" class="window-controls">
<div class="btn-circle" title="min">—</div>
<div class="btn-circle" title="max">▢</div>
<div class="btn-circle" title="close">✕</div>
</div>
</div>
<nav aria-label="main tabs" class="tabs">
<div aria-label="Profile tabs" class="tab-list" role="tablist">
<button aria-selected="true" class="tab active" data-tab="main" role="tab">Main</button>
<button class="tab" data-tab="portfolio" role="tab">Portfolio</button>
<button class="tab" data-tab="misc" role="tab">Misc</button>
</div>
<div class="tab-right">
<span class="muted">Help</span> | <span class="linklike">Log Out</span>
</div>
</nav>
<main class="content" id="mainContent">
<!-- Main content (visible by default) -->
<div class="tab-content" id="main-tab">
<!-- LEFT -->
<aside aria-label="left column" class="left">
<div class="card">
<h3 class="small-h">Socials</h3>
<ol aria-label="accounts" class="find-list">
<li>
<a class="social-link" href="https://instagram.com/90icetea" target="_blank">
<span class="social-icon" style="background-image: url('data:image/svg+xml;utf8,&lt;svg xmlns=\'http://www.w3.org/2000/svg\' viewBox=\'0 0 24 24\' fill=\'%23ddd\'&gt;&lt;path d=\'M12 2c2.717 0 3.056.01 4.122.06 1.065.05 1.79.217 2.428.465.66.254 1.216.598 1.772 1.153a4.908 4.908 0 0 1 1.153 1.772c.247.637.415 1.363.465 2.428.047 1.066.06 1.405.06 4.122 0 2.717-.01 3.056-.06 4.122-.05 1.065-.218 1.79-.465 2.428a4.883 4.883 0 0 1-1.153 1.772 4.915 4.915 0 0 1-1.772 1.153c-.637.247-1.363.415-2.428.465-1.066.047-1.405.06-4.122.06-2.717 0-3.056-.01-4.122-.06-1.065-.05-1.79-.218-2.428-.465a4.89 4.89 0 0 1-1.772-1.153 4.904 4.904 0 0 1-1.153-1.772c-.248-.637-.415-1.363-.465-2.428C2.013 15.056 2 14.717 2 12c0-2.717.01-3.056.06-4.122.05-1.066.217-1.79.465-2.428a4.88 4.88 0 0 1 1.153-1.772A4.897 4.897 0 0 1 5.45 2.525c.638-.248 1.362-.415 2.428-.465C8.944 2.013 9.283 2 12 2zm0 5a5 5 0 1 0 0 10 5 5 0 0 0 0-10zm6.5-.25a1.25 1.25 0 0 0-2.5 0 1.25 1.25 0 0 0 2.5 0zM12 9a3 3 0 1 1 0 6 3 3 0 0 1 0-6z\'/&gt;&lt;/svg&gt;')"></span>
                                    Instagram
                                </a>
</li>
<li>
<a class="social-link" href="https://github.com/90icetea" target="_blank">
<span class="social-icon" style="background-image: url('data:image/svg+xml;utf8,&lt;svg xmlns=\'http://www.w3.org/2000/svg\' viewBox=\'0 0 24 24\' fill=\'%23ddd\'&gt;&lt;path d=\'M12 .297c-6.63 0-12 5.373-12 12 0 5.303 3.438 9.8 8.205 11.385.6.113.82-.258.82-.577 0-.285-.01-1.04-.015-2.04-3.338.724-4.042-1.61-4.042-1.61C4.422 18.07 3.633 17.7 3.633 17.7c-1.087-.744.084-.729.084-.729 1.205.084 1.838 1.236 1.838 1.236 1.07 1.835 2.809 1.305 3.495.998.108-.776.417-1.305.76-1.605-2.665-.3-5.466-1.332-5.466-5.93 0-1.31.465-2.38 1.235-3.22-.135-.303-.54-1.523.105-3.176 0 0 1.005-.322 3.3 1.23.96-.267 1.98-.399 3-.405 1.02.006 2.04.138 3 .405 2.28-1.552 3.285-1.23 3.285-1.23.645 1.653.24 2.873.12 3.176.765.84 1.23 1.91 1.23 3.22 0 4.61-2.805 5.625-5.475 5.92.42.36.81 1.096.81 2.22 0 1.606-.015 2.896-.015 3.286 0 .315.21.69.825.57C20.565 22.092 24 17.592 24 12.297c0-6.627-5.373-12-12-12\'/&gt;&lt;/svg&gt;')"></span>
                                    Github
                                </a>
</li>
<li>
<a class="social-link" href="https://open.spotify.com/user/90icetea" target="_blank">
<span class="social-icon" style="background-image: url('data:image/svg+xml;utf8,&lt;svg xmlns=\'http://www.w3.org/2000/svg\' viewBox=\'0 0 24 24\' fill=\'%23ddd\'&gt;&lt;path d=\'M12 0C5.4 0 0 5.4 0 12s5.4 12 12 12 12-5.4 12-12S18.66 0 12 0zm5.521 17.34c-.24.359-.66.48-1.021.24-2.82-1.74-6.36-2.101-10.561-1.141-.418.122-.779-.179-.899-.539-.12-.421.18-.78.54-.9 4.56-1.021 8.52-.6 11.64 1.32.42.18.479.659.301 1.02zm1.44-3.3c-.301.42-.841.6-1.262.3-3.239-2-8.159-2.58-11.939-1.38-.479.12-1.02-.12-1.14-.6-.12-.48.12-1.021.6-1.141C9.6 9.9 15 10.561 18.72 12.84c.361.181.54.78.241 1.2zm.12-3.36C15.24 8.4 8.82 8.16 5.16 9.301c-.6.179-1.2-.181-1.38-.721-.18-.601.18-1.2.72-1.381 4.26-1.26 11.28-1.02 15.721 1.621.539.3.719 1.02.419 1.56-.299.421-1.02.599-1.559.3z\'/&gt;&lt;/svg&gt;')"></span>
                                    Spotify
                                </a>
</li>
<li>
<a class="social-link" href="https://discordapp.com/users/90icetea" target="_blank">
<span class="social-icon" style="background-image: url('data:image/svg+xml;utf8,&lt;svg xmlns=\'http://www.w3.org/2000/svg\' viewBox=\'0 0 24 24\' fill=\'%23ddd\'&gt;&lt;path d=\'M20.222 0c1.406 0 2.54 1.137 2.609 2.498V24l-2.679-2.27-1.48-1.338-1.611-1.475.67 2.205H3.71c-1.402 0-2.54-1.196-2.54-2.6V2.48C1.17 1.142 2.31.003 3.715.003h16.5L20.222 0zm-6.118 5.683h-.03l-.202.2c2.073.6 3.076 1.537 3.076 1.537-1.336-.668-2.54-1.002-3.744-1.137-.87-.135-1.74-.064-2.475 0h-.2c-.47 0-1.47.2-2.81.735-.467.203-.735.336-.735.336s1.002-1.002 3.21-1.537l-.135-.135s-1.672-.064-3.477 1.27c0 0-1.805 3.144-1.805 7.02 0 0 1 1.74 3.743 1.806 0 0 .4-.533.805-1.002-1.54-.468-2.14-1.404-2.14-1.404s.134.066.335.2h.06c.03 0 .044.015.06.03v.006c.016.016.03.03.06.03.33.136.66.27.93.4.466.202 1.065.403 1.8.536.93.135 1.996.2 3.21 0 .6-.135 1.2-.267 1.8-.535.39-.2.87-.4 1.397-.737 0 0-.6.936-2.205 1.404.33.466.795 1 .795 1 2.744-.06 3.81-1.8 3.87-1.726 0-3.87-1.815-7.02-1.815-7.02-1.635-1.27-3.165-1.27-3.435-1.27l.045-.047zm-10.117 8.06c1.1 0 1.997-.9 1.997-2.003 0-1.104-.894-2.004-1.997-2.004-1.1 0-1.996.9-1.996 2.004 0 1.103.896 2.003 1.996 2.003zm7.77 0c1.1 0 1.996-.9 1.996-2.003 0-1.104-.895-2.004-1.997-2.004-1.1 0-1.996.9-1.996 2.004 0 1.103.896 2.003 1.996 2.003z\'/&gt;&lt;/svg&gt;')"></span>
                                    Discord
                                </a>
</li>
</ol>
</div>
<div class="card">
<h3 class="small-h">Interests</h3>
<div class="interests">video-editing, motion-graphics, python, roblox animation, roblox world-building, lua, photography, visual-design.</div>
</div>
</aside>
<!-- CENTER -->
<section aria-live="polite" class="center">
<div class="avatar-row">
<div class="avatar" title="avatar">
<img alt="90icetea profile picture" src="https://iili.io/FQKZeNp.webp"/>
</div>
<div class="meta">
<h2>90icetea<small style="font-weight:600;color:#aaa"> • a.k.a rashya</small></h2>
<p class="muted">
                                subaverage software lover | he/him, male · fluent english, indonesian, a bit of javanese · currently interested in compsci
                            </p>
<div class="mood">"Cogito, ergo sum." -René Descartes</div>
</div>
</div>
<!-- player -->
<div class="playing" id="player">
<div class="track">▶︎ Tubuh Yang Terpadam Sulut - Harum Manis <span id="durationLabel" style="margin-left:auto;font-weight:600;color:var(--muted)">00:00 / 03:36</span></div>
<div class="player-controls">
<button aria-pressed="false" class="play-btn btn" id="playBtn" title="Play / pause">▶</button>
<button class="btn" id="archiveBtn">Archive</button>
<button class="btn" id="shareBtn">Share</button>
<div style="flex:1"></div>
<input accept="audio/*" id="audioFile" style="display:none" type="file"/>
<button class="btn" id="loadBtn">Load audio</button>
</div>
<div aria-hidden="false" aria-label="player progress" class="progress-row">
<div class="time" id="currentTime">00:00</div>
<input aria-valuemax="100" aria-valuemin="0" id="progress" max="100" min="0" type="range" value="0"/>
<div class="time" id="totalTime">03:36</div>
</div>
</div>
<!-- image + info boxes -->
<div class="media-row">
<div class="main-content-area">
<div class="panel-left">
<div class="image-placeholder" id="gallery">
<!-- simple stylized 'manga panel' SVG -->
<svg aria-hidden="true" class="manga" viewbox="0 0 600 300" xmlns="https://tse1.mm.bing.net/th/id/OIP.rIbWlUS6ivcJmcGxCuYgWgHaEK">
<rect fill="#2a2a2a" height="100%" width="100%"></rect>
<g fill="#333">
<rect height="260" rx="8" width="150" x="20" y="20"></rect>
<rect height="260" rx="8" width="150" x="190" y="20"></rect>
<rect height="260" rx="8" width="220" x="360" y="20"></rect>
</g>
<g fill="#555" font-family="sans-serif" font-size="18" text-anchor="middle">
<text x="95" y="178">●</text>
<text x="265" y="170">● ●</text>
<text x="470" y="160">● ● ●</text>
</g>
</svg>
</div>
<div style="padding:10px">
<p style="margin:0;font-weight:700;color:#f0f0f0">After Effects Progress <span style="font-weight:500;color:var(--muted)">• 6.8.2025</span>
</p>
<p class="muted" style="margin-top:6px">emu otori edit remake timelapse in the gif above. took some time switching from alight motion to after effects.</p>
</div>
</div>
<aside aria-label="info" class="panel-right">
<div class="info-box">
<h4>Music</h4>
<p>malcolm todd, the smiths, mac demarco, radiohead, tyler the creator, wifiskeleton, jades/otuka.</p>
</div>
<div class="info-box">
<h4>Visual Media</h4>
<p>neon genesis evangelion, breaking bad, 500 days of summer, one piece, bladerunner 2049, dr. stone, the pianist.</p>
</div>
<div class="info-box">
<h4>Games</h4>
<p>minecraft, roblox, pubgm, free fire, chess, singleplayer story games.</p>
</div>
</aside>
</div>
<!-- MOVED NOTE TO SPAN BELOW BOTH COLUMNS -->
<div class="note">
<strong>that's about it. i'm not really active on instagram, discord dms preferred for contacting. mostly online 10 hours a day.</strong>
<div class="dninote"><strong>DNI:</strong> aparat, zionists, pedophiles.</div>
</div>
</div>

</section>
</div>
<!-- Portfolio content -->
<div class="tab-content portfolio-content" id="portfolio-tab">
<h2 style="margin: 10px 0; font-size: 20px; color: #f0f0f0; font-family: 'Montserrat', sans-serif;">My Works</h2>
<p class="muted">A collection of my recent work and projects</p>
<div class="portfolio-grid">
<div class="portfolio-item">
<div class="portfolio-image" style="background-image: url('https://via.placeholder.com/300x200/333333/666666?text=Mobile+App')">📱</div>
<div class="portfolio-desc">
<h4>Carrd Tutorial Series</h4>
<p>A comprehensive guide to building beautiful websites with Carrd. Includes advanced techniques and custom CSS tips.</p>
</div>
</div>
<div class="portfolio-item">
<div class="portfolio-image" style="background-image: url('https://via.placeholder.com/300x200/333333/666666?text=Design+Work')">🎨</div>
<div class="portfolio-desc">
<h4>Retro Design Collection</h4>
<p>Curated collection of retro UI elements and templates inspired by 90s web aesthetics.</p>
</div>
</div>
<div class="portfolio-item">
<div class="portfolio-image" style="background-image: url('https://via.placeholder.com/300x200/333333/666666?text=Web+Template')">💻</div>
<div class="portfolio-desc">
<h4>Personal Website Template</h4>
<p>Minimalist portfolio template with dark mode support and responsive design.</p>
</div>
</div>
<div class="portfolio-item">
<div class="portfolio-image" style="background-image: url('https://via.placeholder.com/300x200/333333/666666?text=CSS+Library')">📝</div>
<div class="portfolio-desc">
<h4>CSS Animation Library</h4>
<p>A collection of lightweight CSS animations for buttons, loaders, and transitions.</p>
</div>
</div>
<div class="portfolio-item">
<div class="portfolio-image" style="background-image: url('https://via.placeholder.com/300x200/333333/666666?text=Music+Player')">🎵</div>
<div class="portfolio-desc">
<h4>Music Player UI Kit</h4>
<p>Retro-inspired music player interface with custom controls and visualizations.</p>
</div>
</div>
<div class="portfolio-item">
<div class="portfolio-image" style="background-image: url('https://via.placeholder.com/300x200/333333/666666?text=Image+Gallery')">🖼️</div>
<div class="portfolio-desc">
<h4>Image Gallery Component</h4>
<p>Responsive gallery with masonry layout and lightbox functionality.</p>
</div>
</div>
<div class="portfolio-item">
<div class="portfolio-image" style="background-image: url('https://via.placeholder.com/300x200/333333/666666?text=Dashboard')">📊</div>
<div class="portfolio-desc">
<h4>Data Visualization Dashboard</h4>
<p>Interactive dashboard with real-time data visualization using D3.js.</p>
</div>
</div>
<div class="portfolio-item">
<div class="portfolio-image" style="background-image: url('https://via.placeholder.com/300x200/333333/666666?text=Browser+Extension')">🌐</div>
<div class="portfolio-desc">
<h4>Browser Extension Suite</h4>
<p>Collection of productivity-focused browser extensions with unified UI.</p>
</div>
</div>
</div>
</div>
<!-- Misc content -->
<div class="tab-content misc-content" id="misc-tab">
<div style="text-align: center; max-width: 500px; margin: 0 auto;">
<h2 style="color: #f0f0f0; font-family: 'Montserrat', sans-serif; margin-bottom: 15px;">Coming Soon!</h2>
<p class="muted">This section is under development</p>
<div style="margin: 25px 0; font-size: 60px; color: #555;">🚧</div>
<p style="margin-top: 20px; color: #bbb;">Working on something special here. Check back soon for updates and new features!</p>
</div>
</div>
</main>
<script>
        (function(){
            const playBtn = document.getElementById('playBtn');
            const progress = document.getElementById('progress');
            const currentTimeEl = document.getElementById('currentTime');
            const totalTimeEl = document.getElementById('totalTime');
            const durationLabel = document.getElementById('durationLabel');
            const loadBtn = document.getElementById('loadBtn');
            const audioFileInput = document.getElementById('audioFile');
            const shareBtn = document.getElementById('shareBtn');
            
            // Tab functionality
            const tabs = document.querySelectorAll('.tab');
            const tabContents = document.querySelectorAll('.tab-content');
            
            // default simulated track
            let isPlaying = false;
            let useRealAudio = false;
            let simDuration = 198; // 3:18 in seconds
            let simTime = 0;
            let simInterval = null;
            let audio = new Audio();
            audio.preload = 'metadata';
            audio.crossOrigin = 'anonymous';

            function formatTime(s){
                s = Math.max(0, Math.floor(s));
                const m = Math.floor(s/60);
                const sec = s % 60;
                return (m < 10 ? '0'+m : m) + ':' + (sec < 10 ? '0'+sec : sec);
            }

            // init UI
            progress.max = 100;
            totalTimeEl.textContent = formatTime(simDuration);
            durationLabel.textContent = formatTime(simTime) + " / " + formatTime(simDuration);
            currentTimeEl.textContent = formatTime(simTime);

            function startSim(){
                if(simInterval) clearInterval(simInterval);
                simInterval = setInterval(()=>{
                    simTime += 1;
                    if(simTime >= simDuration){
                        simTime = simDuration;
                        pause();
                    }
                    updateUI();
                }, 1000);
            }
            function stopSim(){ if(simInterval) { clearInterval(simInterval); simInterval = null; } }

            function play(){
                if(useRealAudio){
                    audio.play();
                } else {
                    isPlaying = true;
                    playBtn.textContent = '▌▌';
                    playBtn.setAttribute('aria-pressed','true');
                    startSim();
                }
            }
            function pause(){
                if(useRealAudio){
                    audio.pause();
                } else {
                    isPlaying = false;
                    playBtn.textContent = '▶';
                    playBtn.setAttribute('aria-pressed','false');
                    stopSim();
                }
            }

            function togglePlay(){
                if(useRealAudio){
                    if(audio.paused) audio.play(); else audio.pause();
                } else {
                    if(isPlaying) pause(); else play();
                }
            }

            function updateUI(){
                const t = useRealAudio ? audio.currentTime : simTime;
                const d = useRealAudio ? (audio.duration || simDuration) : simDuration;
                const percent = d ? Math.round((t/d)*100) : 0;
                progress.value = Math.min(100,Math.max(0,percent));
                currentTimeEl.textContent = formatTime(t);
                totalTimeEl.textContent = formatTime(d);
                durationLabel.textContent = formatTime(t) + " / " + formatTime(d);
            }

            // slider interaction
            let dragging = false;
            progress.addEventListener('input', (e)=>{
                dragging = true;
                const pct = progress.value / 100;
                const d = useRealAudio ? (audio.duration || simDuration) : simDuration;
                const newT = Math.round(pct * d);
                currentTimeEl.textContent = formatTime(newT);
                durationLabel.textContent = formatTime(newT) + " / " + formatTime(d);
            });
            progress.addEventListener('change', (e)=>{
                const pct = progress.value / 100;
                const d = useRealAudio ? (audio.duration || simDuration) : simDuration;
                const newT = Math.round(pct * d);
                if(useRealAudio){
                    audio.currentTime = newT;
                } else {
                    simTime = newT;
                }
                dragging = false;
                updateUI();
            });

            // play button
            playBtn.addEventListener('click', togglePlay);

            // simulated timer UI refresh
            setInterval(()=> {
                if(!dragging) updateUI();
            }, 300);

            // load audio button -> file input
            loadBtn.addEventListener('click', ()=> audioFileInput.click());
            audioFileInput.addEventListener('change', (e)=>{
                const file = e.target.files && e.target.files[0];
                if(!file) return;
                const url = URL.createObjectURL(file);
                audio.src = url;
                useRealAudio = true;
                audio.addEventListener('loadedmetadata', ()=> {
                    // when real audio loaded, set duration and UI
                    totalTimeEl.textContent = formatTime(audio.duration);
                    // if audio paused by default
                    updateUI();
                    // auto play
                    audio.play();
                    playBtn.textContent = '▌▌';
                    playBtn.setAttribute('aria-pressed','true');
                }, {once:true});

                audio.addEventListener('timeupdate', updateUI);
                audio.addEventListener('play', ()=>{ playBtn.textContent='▌▌'; playBtn.setAttribute('aria-pressed','true'); });
                audio.addEventListener('pause', ()=>{ playBtn.textContent='▶'; playBtn.setAttribute('aria-pressed','false'); });
                // clean fallback sim
                stopSim();
            });

            // support drag-and-drop audio onto the window to play
            const win = document.querySelector('.window');
            ['dragenter','dragover'].forEach(ev=>{
                win.addEventListener(ev, (e)=>{ e.preventDefault(); win.style.outline='2px dashed #666'; });
            });
            ['dragleave','drop'].forEach(ev=>{
                win.addEventListener(ev, (e)=>{ e.preventDefault(); win.style.outline='none'; });
            });
            win.addEventListener('drop', (e)=>{
                const file = (e.dataTransfer.files && e.dataTransfer.files[0]);
                if(!file) return;
                if(!file.type.startsWith('audio')) { alert('Please drop an audio file.'); return; }
                const url = URL.createObjectURL(file);
                audio.src = url;
                useRealAudio = true;
                audio.addEventListener('loadedmetadata', ()=> {
                    totalTimeEl.textContent = formatTime(audio.duration);
                    audio.play();
                }, {once:true});
                audio.addEventListener('timeupdate', updateUI);
                audio.addEventListener('play', ()=>{ playBtn.textContent='▌▌'; playBtn.setAttribute('aria-pressed','true'); });
                audio.addEventListener('pause', ()=>{ playBtn.textContent='▶'; playBtn.setAttribute('aria-pressed','false'); });
            });

            // when using real audio, sync slider to audio
            audio.addEventListener('timeupdate', ()=> {
                if(!useRealAudio) return;
                updateUI();
            });
            audio.addEventListener('ended', ()=> { playBtn.textContent='▶'; playBtn.setAttribute('aria-pressed','false'); });

            // archive/share behavior (small UI helpers)
            document.getElementById('archiveBtn').addEventListener('click', ()=>{
                alert('Saved to archive (simulated).');
            });

            shareBtn.addEventListener('click', async ()=>{
                try{
                    await navigator.clipboard.writeText(window.location.href);
                    alert('Link copied to clipboard!');
                }catch(e){
                    alert('Could not copy — fallback: ' + window.location.href);
                }
            });

            // Tab switching functionality
            tabs.forEach(btn=>{
                btn.addEventListener('click', ()=>{
                    // Update tab UI
                    document.querySelectorAll('.tab').forEach(t=> { 
                        t.classList.remove('active'); 
                        t.setAttribute('aria-selected','false');
                    });
                    btn.classList.add('active'); 
                    btn.setAttribute('aria-selected','true');
                    
                    // Show the corresponding tab content
                    const tabId = btn.getAttribute('data-tab');
                    tabContents.forEach(content => {
                        content.style.display = 'none';
                    });
                    document.getElementById(`${tabId}-tab`).style.display = 'flex';
                });
            });

            // start simulated playback paused (user must press play)
            updateUI();

        })();
    </script>
</div>
</body>
</html>
