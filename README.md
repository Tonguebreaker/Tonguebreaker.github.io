<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Character Sheet</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Cinzel:wght@400;600;700&family=Cinzel+Decorative:wght@400;700&display=swap');
        
        body {
            margin: 0;
            padding: 20px;
            background: linear-gradient(135deg, #0a0a0a 0%, #1a1a1a 100%);
            font-family: 'Cinzel Decorative', serif;
            color: #ffffff;
            min-height: 100vh;
        }
        
        .character-sheet {
            max-width: 1200px;
            margin: 0 auto;
            background: #000;
            border: 3px solid #ffffff;
            border-radius: 15px;
            position: relative;
            padding: 30px;
            box-shadow: 0 0 30px rgba(255, 255, 255, 0.3);
        }
        
        .character-sheet::before {
            content: '';
            position: absolute;
            top: -5px;
            left: -5px;
            right: -5px;
            bottom: -5px;
            background: linear-gradient(45deg, #ffffff, #cccccc, #ffffff, #cccccc);
            border-radius: 20px;
            z-index: -1;
            animation: borderGlow 3s ease-in-out infinite alternate;
        }
        
        @keyframes borderGlow {
            0% { box-shadow: 0 0 20px rgba(255, 255, 255, 0.5); }
            100% { box-shadow: 0 0 40px rgba(255, 255, 255, 0.8); }
        }
        
        .header {
            text-align: center;
            margin-bottom: 30px;
            border-bottom: 2px solid #ffffff;
            padding-bottom: 20px;
        }
        
        .title {
            font-family: 'Cinzel Decorative', serif;
            font-size: 2.5em;
            font-weight: 700;
            color: #ffffff;
            text-shadow: 2px 2px 4px rgba(255, 255, 255, 0.3);
            margin-bottom: 10px;
        }

        .share-buttons {
            text-align: center;
            margin-bottom: 20px;
        }

        .btn {
            background: linear-gradient(135deg, #333 0%, #555 100%);
            border: 2px solid #ffffff;
            color: #ffffff;
            padding: 10px 20px;
            margin: 0 5px;
            border-radius: 8px;
            cursor: pointer;
            font-family: 'Cinzel Decorative', serif;
            font-size: 0.9em;
            text-transform: uppercase;
            letter-spacing: 1px;
            transition: all 0.3s ease;
        }

        .btn:hover {
            background: linear-gradient(135deg, #555 0%, #777 100%);
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(255, 255, 255, 0.2);
        }

        .btn.success {
            background: linear-gradient(135deg, #2a5934 0%, #4a8f5a 100%);
        }

        .btn.success:hover {
            background: linear-gradient(135deg, #4a8f5a 0%, #6abf7a 100%);
        }

        .btn.share {
            background: linear-gradient(135deg, #2a3459 0%, #4a5f8f 100%);
        }

        .btn.share:hover {
            background: linear-gradient(135deg, #4a5f8f 0%, #6a7fbf 100%);
        }

        .load-section {
            background: #111;
            border: 1px solid #666;
            border-radius: 8px;
            padding: 15px;
            margin: 10px 0;
            text-align: left;
        }

        .load-section input, .load-section textarea {
            width: 100%;
            background: #000;
            border: 1px solid #666;
            color: #fff;
            padding: 8px;
            border-radius: 5px;
            font-family: monospace;
            margin: 5px 0;
            font-size: 0.9em;
        }

        .load-section input:focus, .load-section textarea:focus {
            outline: none;
            border-color: #fff;
        }

        .url-share-input {
            font-size: 0.8em !important;
            word-break: break-all;
            resize: vertical;
            min-height: 60px;
        }

        .copy-btn {
            background: linear-gradient(135deg, #2a3459 0%, #4a5f8f 100%);
            border: 1px solid #666;
            color: #fff;
            padding: 5px 10px;
            border-radius: 5px;
            cursor: pointer;
            font-family: 'Cinzel Decorative', serif;
            font-size: 0.8em;
            margin-left: 5px;
            transition: all 0.3s ease;
        }

        .copy-btn:hover {
            background: linear-gradient(135deg, #4a5f8f 0%, #6a7fbf 100%);
        }
        
        .name-section {
            text-align: center;
            margin-bottom: 30px;
            background: linear-gradient(135deg, #111 0%, #222 100%);
            border: 2px solid #ffffff;
            border-radius: 15px;
            padding: 25px;
            position: relative;
        }
        
        .name-section::before {
            content: '';
            position: absolute;
            top: -1px;
            left: -1px;
            right: -1px;
            bottom: -1px;
            background: linear-gradient(45deg, transparent, rgba(255, 255, 255, 0.1), transparent);
            border-radius: 15px;
            z-index: -1;
        }
        
        .name-input {
            font-family: 'Cinzel Decorative', serif;
            font-size: 2.2em;
            font-weight: 600;
            background: transparent;
            border: none;
            border-bottom: 3px solid #ffffff;
            color: #ffffff;
            text-align: center;
            width: 100%;
            max-width: 500px;
            padding: 10px;
            margin-bottom: 15px;
        }
        
        .name-input:focus {
            outline: none;
            border-bottom-color: #cccccc;
            text-shadow: 0 0 10px rgba(255, 255, 255, 0.5);
        }
        
        .name-input::placeholder {
            color: #666;
            opacity: 0.7;
        }
        
        .titles-input {
            font-family: 'Cinzel Decorative', serif;
            font-size: 1.3em;
            background: transparent;
            border: none;
            border-bottom: 1px solid #cccccc;
            color: #cccccc;
            text-align: center;
            width: 100%;
            max-width: 600px;
            padding: 8px;
        }
        
        .titles-input:focus {
            outline: none;
            border-bottom-color: #ffffff;
        }
        
        .titles-input::placeholder {
            color: #555;
            opacity: 0.8;
        }
        
        .main-grid {
            display: grid;
            grid-template-columns: 1fr 1fr 1fr;
            gap: 30px;
            margin-bottom: 30px;
        }
        
        .section {
            background: linear-gradient(135deg, #111 0%, #222 100%);
            border: 2px solid #ffffff;
            border-radius: 10px;
            padding: 20px;
            position: relative;
        }
        
        .section::before {
            content: '';
            position: absolute;
            top: -1px;
            left: -1px;
            right: -1px;
            bottom: -1px;
            background: linear-gradient(45deg, transparent, rgba(255, 255, 255, 0.1), transparent);
            border-radius: 10px;
            z-index: -1;
        }
        
        .section-title {
            font-family: 'Cinzel Decorative', serif;
            font-size: 1.4em;
            color: #ffffff;
            text-align: center;
            margin-bottom: 15px;
            text-transform: uppercase;
            letter-spacing: 2px;
            border-bottom: 1px solid #ffffff;
            padding-bottom: 8px;
        }
        
        .basic-info {
            grid-column: 1 / -1;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
        }
        
        .info-field {
            display: flex;
            flex-direction: column;
        }
        
        .info-field label {
            font-family: 'Cinzel Decorative', serif;
            font-weight: 600;
            color: #ffffff;
            margin-bottom: 5px;
            text-transform: uppercase;
            font-size: 0.9em;
            letter-spacing: 1px;
        }
        
        .info-field input, .info-field textarea {
            background: #000;
            border: 1px solid #ffffff;
            border-radius: 5px;
            padding: 8px;
            color: #fff;
            font-family: 'Cinzel Decorative', serif;
        }
        
        .info-field input:focus, .info-field textarea:focus {
            outline: none;
            border-color: #cccccc;
            box-shadow: 0 0 10px rgba(255, 255, 255, 0.3);
        }
        
        .attributes-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 15px;
        }
        
        .attribute {
            display: flex;
            align-items: center;
            background: #000;
            border: 1px solid #ffffff;
            border-radius: 8px;
            padding: 10px;
        }
        
        .attribute-letter {
            font-family: 'Cinzel Decorative', serif;
            font-size: 2em;
            font-weight: 700;
            color: #ffffff;
            width: 40px;
            text-align: center;
            margin-right: 15px;
        }
        
        .attribute-details {
            flex: 1;
        }
        
        .attribute-name {
            font-family: 'Cinzel Decorative', serif;
            font-weight: 600;
            color: #ffffff;
            font-size: 1.1em;
            margin-bottom: 3px;
        }
        
        .attribute-desc {
            font-family: 'Cinzel Decorative', serif;
            font-size: 0.8em;
            color: #cccccc;
            line-height: 1.3;
        }
        
        .attribute-score {
            text-align: center;
            margin-left: 15px;
        }
        
        .attribute-score input {
            width: 50px;
            height: 50px;
            text-align: center;
            font-size: 1.5em;
            font-weight: bold;
            background: #000;
            border: 2px solid #ffffff;
            border-radius: 50%;
            color: #fff;
            font-family: 'Cinzel Decorative', serif;
        }
        
        .stats-section {
            display: flex;
            flex-direction: column;
        }
        
        .stats-stats {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 15px;
        }
        
        .stat-box {
            background: #000;
            border: 1px solid #ffffff;
            border-radius: 5px;
            padding: 10px;
            text-align: center;
        }
        
        .stat-label {
            font-family: 'Cinzel Decorative', serif;
            font-size: 0.9em;
            color: #ffffff;
            margin-bottom: 5px;
            text-transform: uppercase;
        }
        
        .stat-value {
            font-family: 'Cinzel Decorative', serif;
            font-size: 1.2em;
            font-weight: bold;
            color: #fff;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 5px;
        }

        .stat-input {
            width: 50px;
            height: 40px;
            background: transparent;
            border: none;
            color: #fff;
            text-align: center;
            font-size: 1.2em;
            font-family: 'Cinzel Decorative', serif;
            font-weight: bold;
        }

        .stat-input:focus {
            outline: none;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 3px;
        }
        
        .thaumaturgy-section {
            grid-column: 1 / -1;
        }
        
        .facets-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 15px;
            margin-top: 15px;
        }
        
        .facet {
            background: #000;
            border: 1px solid #ffffff;
            border-radius: 8px;
            padding: 15px;
            text-align: center;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        
        .facet:hover {
            background: #111;
            border-color: #cccccc;
            transform: translateY(-2px);
        }
        
        .facet.active {
            background: #ffffff;
            color: #000;
        }
        
        .facet-name {
            font-family: 'Cinzel Decorative', serif;
            font-weight: 600;
            margin-bottom: 5px;
            text-transform: uppercase;
        }
        
        .facet-desc {
            font-family: 'Cinzel Decorative', serif;
            font-size: 0.8em;
            opacity: 0.8;
        }
        
        .perks-traits-section {
            grid-column: 1 / -1;
        }
        
        .perks-traits-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 30px;
            margin-top: 15px;
        }
        
        .perks-column, .traits-column {
            background: #000;
            border: 1px solid #ffffff;
            border-radius: 8px;
            padding: 15px;
        }
        
        .perks-column h4, .traits-column h4 {
            font-family: 'Cinzel Decorative', serif;
            color: #ffffff;
            border-bottom: 1px solid #ffffff;
            padding-bottom: 5px;
            margin-bottom: 10px;
            text-transform: uppercase;
        }
        
        .perk-item, .trait-item {
            background: #111;
            border: 1px solid #666;
            border-radius: 5px;
            padding: 8px;
            margin-bottom: 8px;
            font-family: 'Cinzel Decorative', serif;
            font-size: 0.9em;
        }
        
        .perk-item input, .trait-item input {
            width: 100%;
            background: transparent;
            border: none;
            color: #ffffff;
            font-family: 'Cinzel Decorative', serif;
        }
        
        .perk-item input:focus, .trait-item input:focus {
            outline: none;
        }

        .blessings-section {
            grid-column: 1 / -1;
            margin-top: 20px;
        }

        .blessings-grid {
            display: grid;
            grid-template-columns: 1fr;
            gap: 15px;
            margin-top: 15px;
            max-width: 800px;
            margin-left: auto;
            margin-right: auto;
        }

        .blessing-item {
            background: #000;
            border: 1px solid #ffffff;
            border-radius: 8px;
            padding: 15px;
        }

        .blessing-name {
            margin-bottom: 10px;
        }

        .blessing-name input {
            width: 100%;
            background: transparent;
            border: none;
            border-bottom: 1px solid #ffffff;
            color: #ffffff;
            font-family: 'Cinzel Decorative', serif;
            font-weight: 600;
            font-size: 1.1em;
            padding: 5px 0;
        }

        .blessing-name input:focus {
            outline: none;
            border-bottom-color: #cccccc;
        }

        .blessing-description textarea {
            width: 100%;
            height: 60px;
            background: transparent;
            border: 1px solid #666;
            border-radius: 5px;
            color: #cccccc;
            font-family: 'Cinzel Decorative', serif;
            font-size: 0.9em;
            padding: 8px;
            resize: vertical;
        }

        .blessing-description textarea:focus {
            outline: none;
            border-color: #ffffff;
        }
        
        .equipment-section {
            grid-column: 1 / -1;
        }
        
        .equipment-grid {
            display: grid;
            grid-template-columns: 1fr 1fr 1fr;
            gap: 20px;
            margin-top: 15px;
        }
        
        .equipment-category h4 {
            font-family: 'Cinzel Decorative', serif;
            color: #ffffff;
            border-bottom: 1px solid #ffffff;
            padding-bottom: 5px;
            margin-bottom: 10px;
        }
        
        .equipment-list {
            max-height: 150px;
            overflow-y: auto;
        }
        
        .equipment-list::-webkit-scrollbar {
            width: 5px;
        }
        
        .equipment-list::-webkit-scrollbar-track {
            background: #000;
        }
        
        .equipment-list::-webkit-scrollbar-thumb {
            background: #ffffff;
            border-radius: 3px;
        }
        
        .notes-section {
            grid-column: 1 / -1;
            margin-top: 20px;
        }
        
        .notes-textarea {
            width: 100%;
            min-height: 100px;
            resize: vertical;
        }
        
        .ornamental {
            text-align: center;
            font-family: 'Cinzel Decorative', serif;
            font-size: 2em;
            color: #ffffff;
            margin: 20px 0;
        }

        .notification {
            position: fixed;
            top: 20px;
            right: 20px;
            background: linear-gradient(135deg, #2a5934 0%, #4a8f5a 100%);
            color: white;
            padding: 15px 20px;
            border-radius: 8px;
            border: 2px solid #ffffff;
            font-family: 'Cinzel Decorative', serif;
            z-index: 1000;
            transform: translateX(400px);
            transition: transform 0.3s ease;
        }

        .notification.show {
            transform: translateX(0);
        }

        .art-library-section {
            grid-column: 1 / -1;
            margin-top: 30px;
            background: linear-gradient(135deg, #111 0%, #222 100%);
            border: 3px solid #ffffff;
            border-radius: 15px;
            padding: 30px;
            position: relative;
        }

        .art-library-section::before {
            content: '';
            position: absolute;
            top: -2px;
            left: -2px;
            right: -2px;
            bottom: -2px;
            background: linear-gradient(45deg, #ffffff, #cccccc, #ffffff, #cccccc);
            border-radius: 18px;
            z-index: -1;
            animation: borderGlow 3s ease-in-out infinite alternate;
        }

        .art-library-title {
            font-family: 'Cinzel Decorative', serif;
            font-size: 2.2em;
            font-weight: 700;
            color: #ffffff;
            text-align: center;
            margin-bottom: 30px;
            text-transform: uppercase;
            letter-spacing: 3px;
            text-shadow: 2px 2px 4px rgba(255, 255, 255, 0.3);
        }

        .art-drop-zone {
            border: 3px dashed #666;
            border-radius: 12px;
            padding: 60px 40px;
            text-align: center;
            background: rgba(0, 0, 0, 0.5);
            transition: all 0.3s ease;
            cursor: pointer;
            position: relative;
            min-height: 200px;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
        }

        .art-drop-zone:hover {
            border-color: #ffffff;
            background: rgba(255, 255, 255, 0.05);
        }

        .art-drop-zone.dragover {
            border-color: #ffffff;
            background: rgba(255, 255, 255, 0.1);
            transform: scale(1.02);
        }

        .drop-text {
            font-family: 'Cinzel Decorative', serif;
            font-size: 1.4em;
            color: #ffffff;
            margin-bottom: 15px;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .drop-subtext {
            font-family: 'Cinzel Decorative', serif;
            font-size: 1em;
            color: #aaa;
            text-transform: uppercase;
            letter-spacing: 2px;
        }

        .file-input {
            display: none;
        }

        .art-gallery {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 20px;
            margin-top: 30px;
        }

        .art-item {
            background: #000;
            border: 2px solid #ffffff;
            border-radius: 10px;
            padding: 15px;
            text-align: center;
            position: relative;
            transition: all 0.3s ease;
        }

        .art-item:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(255, 255, 255, 0.2);
        }

        .art-image {
            width: 100%;
            height: 200px;
            object-fit: cover;
            border-radius: 8px;
            border: 1px solid #666;
        }

        .art-title {
            font-family: 'Cinzel Decorative', serif;
            color: #ffffff;
            margin-top: 10px;
            font-size: 1em;
            padding: 5px;
            background: transparent;
            border: none;
            border-bottom: 1px solid #666;
            text-align: center;
            width: 100%;
        }

        .art-title:focus {
            outline: none;
            border-bottom-color: #ffffff;
        }

        .remove-btn {
            position: absolute;
            top: 10px;
            right: 10px;
            background: rgba(255, 0, 0, 0.8);
            border: none;
            border-radius: 50%;
            width: 25px;
            height: 25px;
            color: white;
            cursor: pointer;
            font-size: 14px;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.3s ease;
        }

        .remove-btn:hover {
            background: rgba(255, 0, 0, 1);
            transform: scale(1.1);
        }

        .hidden {
            display: none !important;
        }

        .storage-info {
            background: #111;
            border: 1px solid #666;
            border-radius: 5px;
            padding: 10px;
            margin: 10px 0;
            font-size: 0.8em;
            color: #aaa;
        }
    </style>
</head>
<body>
    <!-- Simple LZ-string compression library -->
    <script>
        // Simplified LZ-string compression for character data
        const LZString = {
            compress: function(input) {
                if (input === null || input === undefined) return "";
                
                const dictionary = {};
                const data = input.split("");
                let phrase = data[0];
                let code = 256;
                let out = [];
                let i;
                
                for (i = 1; i < data.length; i++) {
                    const curChar = data[i];
                    if (dictionary[phrase + curChar] !== undefined) {
                        phrase += curChar;
                    } else {
                        out.push(phrase.length > 1 ? dictionary[phrase] : phrase.charCodeAt(0));
                        dictionary[phrase + curChar] = code;
                        code++;
                        phrase = curChar;
                    }
                }
                out.push(phrase.length > 1 ? dictionary[phrase] : phrase.charCodeAt(0));
                
                // Convert to base64-like string
                return out.map(num => String.fromCharCode(num + 33)).join('');
            },
            
            decompress: function(compressed) {
                if (!compressed) return "";
                
                try {
                    const data = compressed.split("").map(char => char.charCodeAt(0) - 33);
                    const dictionary = {};
                    let phrase = String.fromCharCode(data[0]);
                    let out = phrase;
                    let code = 256;
                    let i;
                    
                    for (i = 1; i < data.length; i++) {
                        const curCode = data[i];
                        let entry;
                        
                        if (dictionary[curCode] !== undefined) {
                            entry = dictionary[curCode];
                        } else if (curCode === code) {
                            entry = phrase + phrase.charAt(0);
                        } else {
                            entry = String.fromCharCode(curCode);
                        }
                        
                        out += entry;
                        dictionary[code] = phrase + entry.charAt(0);
                        code++;
                        phrase = entry;
                    }
                    
                    return out;
                } catch (e) {
                    return "";
                }
            }
        };
    </script>

    <div class="character-sheet">
        <div class="header">
            <div class="title">CHARACTER CODEX</div>
            <div class="share-buttons">
                <button class="btn" onclick="exportCharacter()">Export Data</button>
                <button class="btn" onclick="showImportSection()">Import Data</button>
                <button class="btn share" onclick="generateShareLink()">Share Link</button>
            </div>
            
            <div id="importSection" class="load-section hidden">
                <h4 style="color: #fff; margin-top: 0;">Import Character Data</h4>
                <div style="margin: 15px 0;">
                    <label style="color: #ccc; display: block; margin-bottom: 5px;">Import from file:</label>
                    <input type="file" id="importFile" accept=".json" onchange="importFromFile(this)">
                </div>
                <div class="storage-info">
                    Use Export/Import to save and load your characters or transfer between devices.
                </div>
            </div>

            <div id="shareLinkSection" class="load-section hidden">
                <h4 style="color: #fff; margin-top: 0;">Share Character Link</h4>
                <div style="margin: 15px 0;">
                    <label style="color: #ccc; display: block; margin-bottom: 5px;">Shareable URL (paste in Discord, forums, etc.):</label>
                    <div style="display: flex; align-items: flex-start;">
                        <textarea id="shareUrlOutput" class="url-share-input" readonly placeholder="Click 'Generate Link' to create a shareable URL..."></textarea>
                        <button class="copy-btn" onclick="copyShareLink()" id="copyBtn">Copy</button>
                    </div>
                </div>
                <div style="margin: 15px 0;">
                    <label style="color: #ccc; display: block; margin-bottom: 5px;">Or paste a shared link here to load:</label>
                    <textarea id="shareUrlInput" placeholder="Paste a character share link here..." style="width: 100%; background: #000; border: 1px solid #666; color: #fff; padding: 8px; border-radius: 5px; font-family: monospace; margin: 5px 0; font-size: 0.9em; min-height: 60px; resize: vertical;"></textarea>
                    <button class="btn" onclick="loadFromShareLink()">Load from Link</button>
                </div>
                <div class="storage-info">
                    Share links contain compressed character data. They work great for Discord, Reddit, forums, etc. No file uploads needed!
                </div>
            </div>
        </div>
        
        <div class="name-section">
            <input type="text" class="name-input" id="characterName" placeholder="Enter Character Name..." maxlength="50">
            <br>
            <input type="text" class="titles-input" id="titles" placeholder="Titles, Epithets, or Monikers..." maxlength="100">
        </div>
        
        <div class="main-grid">
            <div class="section basic-info">
                <div class="section-title">Character Details</div>
                <div class="info-field">
                    <label>Level</label>
                    <input type="text" id="level" placeholder="1">
                </div>
                <div class="info-field">
                    <label>Race</label>
                    <input type="text" id="race" placeholder="Enter race...">
                </div>
                <div class="info-field">
                    <label>Age</label>
                    <input type="text" id="age" placeholder="Enter age...">
                </div>
                <div class="info-field">
                    <label>Alignment</label>
                    <input type="text" id="alignment" placeholder="Enter alignment...">
                </div>
            </div>
        </div>
        
        <div class="main-grid">
            <div class="section">
                <div class="section-title">Core Attributes</div>
                <div class="attributes-grid">
                    <div class="attribute">
                        <div class="attribute-letter">I</div>
                        <div class="attribute-details">
                            <div class="attribute-name">Indomitability</div>
                            <div class="attribute-desc">Melee, strength, toughness, will</div>
                        </div>
                        <div class="attribute-score">
                            <input type="text" id="indomitability" placeholder="0">
                        </div>
                    </div>

                    <div class="attribute">
                        <div class="attribute-letter">F</div>
                        <div class="attribute-details">
                            <div class="attribute-name">Fluidity</div>
                            <div class="attribute-desc">Initiative, sneak, ranged, finesse</div>
                        </div>
                        <div class="attribute-score">
                            <input type="text" id="fluidity" placeholder="0">
                        </div>
                    </div>
                    
                    <div class="attribute">
                        <div class="attribute-letter">L</div>
                        <div class="attribute-details">
                            <div class="attribute-name">Lucidity</div>
                            <div class="attribute-desc">Problem-solving, Thaumaturgy</div>
                        </div>
                        <div class="attribute-score">
                            <input type="text" id="lucidity" placeholder="0">
                        </div>
                    </div>
                    
                    <div class="attribute">
                        <div class="attribute-letter">A</div>
                        <div class="attribute-details">
                            <div class="attribute-name">Authority</div>
                            <div class="attribute-desc">Persuasion, leadership, presence</div>
                        </div>
                        <div class="attribute-score">
                            <input type="text" id="authority" placeholder="0">
                        </div>
                    </div>
                </div>
            </div>
            
            <div class="section stats-section" style="grid-column: span 2;">
                <div class="section-title">Stats</div>
                <div class="stats-stats">
                    <div class="stat-box">
                        <div class="stat-label">HP</div>
                        <div class="stat-value">
                            <input type="text" class="stat-input" id="currentHP" placeholder="0"> / 
                            <input type="text" class="stat-input" id="maxHP" placeholder="0">
                        </div>
                    </div>
                    
                    <div class="stat-box">
                        <div class="stat-label">DEF</div>
                        <div class="stat-value">
                            <input type="text" class="stat-input" id="defense" placeholder="0">
                        </div>
                    </div>
                    
                    <div class="stat-box">
                        <div class="stat-label">AT</div>
                        <div class="stat-value">
                            <input type="text" class="stat-input" id="currentAtramenta" placeholder="0"> / 
                            <input type="text" class="stat-input" id="maxAtramenta" placeholder="0">
                        </div>
                    </div>
                    
                    <div class="stat-box">
                        <div class="stat-label">FT</div>
                        <div class="stat-value">
                            <input type="text" class="stat-input" id="movement" placeholder="0">
                        </div>
                    </div>
                </div>
            </div>
        </div>
        
        <div class="section perks-traits-section">
            <div class="section-title">Perks & Traits</div>
            <div class="perks-traits-grid">
                <div class="perks-column">
                    <h4>Perks</h4>
                    <div class="perk-item"><input type="text" class="perk-input" placeholder="Perk 1..."></div>
                    <div class="perk-item"><input type="text" class="perk-input" placeholder="Perk 2..."></div>
                    <div class="perk-item"><input type="text" class="perk-input" placeholder="Perk 3..."></div>
                    <div class="perk-item"><input type="text" class="perk-input" placeholder="Perk 4..."></div>
                    <div class="perk-item"><input type="text" class="perk-input" placeholder="Perk 5..."></div>
                    <div class="perk-item"><input type="text" class="perk-input" placeholder="Perk 6..."></div>
                    <div class="perk-item"><input type="text" class="perk-input" placeholder="Perk 7..."></div>
                    <div class="perk-item"><input type="text" class="perk-input" placeholder="Perk 8..."></div>
                    <div class="perk-item"><input type="text" class="perk-input" placeholder="Perk 9..."></div>
                    <div class="perk-item"><input type="text" class="perk-input" placeholder="Perk 10..."></div>
                    <div class="perk-item"><input type="text" class="perk-input" placeholder="Perk 11..."></div>
                    <div class="perk-item"><input type="text" class="perk-input" placeholder="Perk 12..."></div>
                </div>
                <div class="traits-column">
                    <h4>Traits</h4>
                    <div class="trait-item"><input type="text" class="trait-input" placeholder="Trait 1..."></div>
                    <div class="trait-item"><input type="text" class="trait-input" placeholder="Trait 2..."></div>
                    <div class="trait-item"><input type="text" class="trait-input" placeholder="Trait 3..."></div>
                    <div class="trait-item"><input type="text" class="trait-input" placeholder="Trait 4..."></div>
                    <div class="trait-item"><input type="text" class="trait-input" placeholder="Trait 5..."></div>
                    <div class="trait-item"><input type="text" class="trait-input" placeholder="Trait 6..."></div>
                    <div class="trait-item"><input type="text" class="trait-input" placeholder="Trait 7..."></div>
                    <div class="trait-item"><input type="text" class="trait-input" placeholder="Trait 8..."></div>
                    <div class="trait-item"><input type="text" class="trait-input" placeholder="Trait 9..."></div>
                    <div class="trait-item"><input type="text" class="trait-input" placeholder="Trait 10..."></div>
                    <div class="trait-item"><input type="text" class="trait-input" placeholder="Trait 11..."></div>
                    <div class="trait-item"><input type="text" class="trait-input" placeholder="Trait 12..."></div>
                </div>
            </div>
        </div>
        
        <div class="section thaumaturgy-section">
            <div class="section-title">Thaumaturgy</div>
            <div style="text-align: center; font-style: italic; margin-bottom: 15px; color: #cccccc;">
                "I reject your reality and substitute my own."
            </div>
            
            <div class="facets-grid">
                <div class="facet" onclick="toggleFacet(this)" data-facet="correspondence">
                    <div class="facet-name">Correspondence</div>
                    <div class="facet-desc">Connection, distance, position</div>
                </div>
                
                <div class="facet" onclick="toggleFacet(this)" data-facet="probability">
                    <div class="facet-name">Probability</div>
                    <div class="facet-desc">Chance, fate, alignment</div>
                </div>
                
                <div class="facet" onclick="toggleFacet(this)" data-facet="forces">
                    <div class="facet-name">Forces</div>
                    <div class="facet-desc">Physics, energy manipulation</div>
                </div>
                
                <div class="facet" onclick="toggleFacet(this)" data-facet="matter">
                    <div class="facet-name">Matter</div>
                    <div class="facet-desc">Structure, form, transformation</div>
                </div>
                
                <div class="facet" onclick="toggleFacet(this)" data-facet="spirit">
                    <div class="facet-name">Spirit</div>
                    <div class="facet-desc">The other side, prayers, watchers</div>
                </div>
                
                <div class="facet" onclick="toggleFacet(this)" data-facet="sixth">
                    <div class="facet-name">[Sixth Facet]</div>
                    <div class="facet-desc">Eluvian Chisel</div>
                </div>
            </div>
            
            <div style="margin-top: 20px;">
                <label style="color: #ffffff; font-weight: 600;">Known Directives:</label>
                <textarea id="directives" style="width: 100%; height: 80px; background: #000; border: 1px solid #ffffff; color: #fff; font-family: 'Cinzel Decorative', serif; border-radius: 5px; padding: 10px; resize: vertical;" placeholder="List your known directives..."></textarea>
            </div>
        </div>

        <div class="section blessings-section">
            <div class="section-title">Blessings</div>
            <div class="blessings-grid">
                <div class="blessing-item">
                    <div class="blessing-name">
                        <input type="text" class="blessing-name-input" placeholder="Blessing Name...">
                    </div>
                    <div class="blessing-description">
                        <textarea class="blessing-desc-input" placeholder="Describe the blessing's effects and abilities..."></textarea>
                    </div>
                </div>
                <div class="blessing-item">
                    <div class="blessing-name">
                        <input type="text" class="blessing-name-input" placeholder="Blessing Name...">
                    </div>
                    <div class="blessing-description">
                        <textarea class="blessing-desc-input" placeholder="Describe the blessing's effects and abilities..."></textarea>
                    </div>
                </div>
                <div class="blessing-item">
                    <div class="blessing-name">
                        <input type="text" class="blessing-name-input" placeholder="Blessing Name...">
                    </div>
                    <div class="blessing-description">
                        <textarea class="blessing-desc-input" placeholder="Describe the blessing's effects and abilities..."></textarea>
                    </div>
                </div>
                <div class="blessing-item">
                    <div class="blessing-name">
                        <input type="text" class="blessing-name-input" placeholder="Blessing Name...">
                    </div>
                    <div class="blessing-description">
                        <textarea class="blessing-desc-input" placeholder="Describe the blessing's effects and abilities..."></textarea>
                    </div>
                </div>
                <div class="blessing-item">
                    <div class="blessing-name">
                        <input type="text" class="blessing-name-input" placeholder="Blessing Name...">
                    </div>
                    <div class="blessing-description">
                        <textarea class="blessing-desc-input" placeholder="Describe the blessing's effects and abilities..."></textarea>
                    </div>
                </div>
                <div class="blessing-item">
                    <div class="blessing-name">
                        <input type="text" class="blessing-name-input" placeholder="Blessing Name...">
                    </div>
                    <div class="blessing-description">
                        <textarea class="blessing-desc-input" placeholder="Describe the blessing's effects and abilities..."></textarea>
                    </div>
                </div>
            </div>
        </div>
        
        <div class="section equipment-section">
            <div class="section-title">Equipment & Belongings</div>
            <div class="equipment-grid">
                <div class="equipment-category">
                    <h4>Weapons</h4>
                    <div class="equipment-list">
                        <textarea id="weapons" style="width: 100%; height: 120px; background: #000; border: 1px solid #ffffff; color: #fff; font-family: 'Cinzel Decorative', serif; border-radius: 5px; padding: 8px; resize: none;" placeholder="List weapons..."></textarea>
                    </div>
                </div>
                
                <div class="equipment-category">
                    <h4>Armor & Protection</h4>
                    <div class="equipment-list">
                        <textarea id="armor" style="width: 100%; height: 120px; background: #000; border: 1px solid #ffffff; color: #fff; font-family: 'Cinzel Decorative', serif; border-radius: 5px; padding: 8px; resize: none;" placeholder="List armor..."></textarea>
                    </div>
                </div>
                
                <div class="equipment-category">
                    <h4>Tools & Gear</h4>
                    <div class="equipment-list">
                        <textarea id="tools" style="width: 100%; height: 120px; background: #000; border: 1px solid #ffffff; color: #fff; font-family: 'Cinzel Decorative', serif; border-radius: 5px; padding: 8px; resize: none;" placeholder="List gear..."></textarea>
                    </div>
                </div>
            </div>
        </div>
        
        <div class="section notes-section">
            <div class="section-title">Background & Notes</div>
            <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 20px;">
                <div>
                    <label style="color: #ffffff; font-weight: 600; display: block; margin-bottom: 5px;">Personal History:</label>
                    <textarea id="history" class="notes-textarea" style="background: #000; border: 1px solid #ffffff; color: #fff; font-family: 'Cinzel Decorative', serif; border-radius: 5px; padding: 10px;" placeholder="Character background..."></textarea>
                </div>
                
                <div>
                    <label style="color: #ffffff; font-weight: 600; display: block; margin-bottom: 5px;">Goals & Motivations:</label>
                    <textarea id="goals" class="notes-textarea" style="background: #000; border: 1px solid #ffffff; color: #fff; font-family: 'Cinzel Decorative', serif; border-radius: 5px; padding: 10px;" placeholder="What drives this character..."></textarea>
                </div>
            </div>
        </div>

        <div class="section art-library-section">
            <div class="art-library-title">Character Art Library</div>
            
            <div class="art-drop-zone" id="artDropZone" onclick="document.getElementById('fileInput').click()">
                <div class="drop-text">Drop Images Here or Click to Browse</div>
                <div class="drop-subtext">Concept Art, Portraits, References - All Welcome</div>
                <input type="file" id="fileInput" class="file-input" multiple accept="image/*">
            </div>
            
            <div class="art-gallery" id="artGallery">
            </div>
        </div>
        
        <div class="ornamental">⧨ ⟡ ⧨</div>
    </div>

    <div id="notification" class="notification">Character saved!</div>
    
    <script>
        let artImages = [];

        // Advanced image compression with multiple techniques
        function compressImage(file, maxWidth = 600, quality = 0.85) {
            return new Promise((resolve) => {
                const canvas = document.createElement('canvas');
                const ctx = canvas.getContext('2d');
                const img = new Image();
                
                img.onload = () => {
                    // Calculate new dimensions with smart sizing
                    let newWidth = img.width;
                    let newHeight = img.height;
                    
                    // Only resize if image is larger than maxWidth
                    if (img.width > maxWidth || img.height > maxWidth) {
                        const ratio = Math.min(maxWidth / img.width, maxWidth / img.height);
                        newWidth = Math.round(img.width * ratio);
                        newHeight = Math.round(img.height * ratio);
                    }
                    
                    canvas.width = newWidth;
                    canvas.height = newHeight;
                    
                    // Enable image smoothing for better quality at smaller sizes
                    ctx.imageSmoothingEnabled = true;
                    ctx.imageSmoothingQuality = 'high';
                    
                    // Draw image
                    ctx.drawImage(img, 0, 0, newWidth, newHeight);
                    
                    // Try WebP first (much better compression), fallback to JPEG
                    let compressedDataUrl;
                    try {
                        // WebP can be 25-50% smaller than JPEG with same quality
                        compressedDataUrl = canvas.toDataURL('image/webp', quality);
                        // Check if WebP is actually supported and smaller
                        if (!compressedDataUrl.startsWith('data:image/webp') || compressedDataUrl.length >= file.length) {
                            throw new Error('WebP not supported or not smaller');
                        }
                    } catch (e) {
                        // Fallback to optimized JPEG
                        compressedDataUrl = canvas.toDataURL('image/jpeg', quality);
                    }
                    
                    resolve(compressedDataUrl);
                };
                
                img.src = file;
            });
        }

        // Compress text data by removing unnecessary whitespace and formatting
        function compressTextData(data) {
            const compressed = { ...data };
            
            // Remove empty strings and arrays to reduce JSON size
            Object.keys(compressed).forEach(key => {
                if (compressed[key] === '' || 
                    (Array.isArray(compressed[key]) && compressed[key].length === 0)) {
                    delete compressed[key];
                }
            });
            
            // Compress arrays by removing empty entries
            ['perks', 'traits', 'blessings', 'facets'].forEach(arrayKey => {
                if (compressed[arrayKey]) {
                    if (arrayKey === 'blessings') {
                        compressed[arrayKey] = compressed[arrayKey].filter(blessing => 
                            blessing.name?.trim() || blessing.description?.trim()
                        );
                    } else {
                        compressed[arrayKey] = compressed[arrayKey].filter(item => 
                            typeof item === 'string' ? item.trim() : item
                        );
                    }
                    if (compressed[arrayKey].length === 0) {
                        delete compressed[arrayKey];
                    }
                }
            });
            
            return compressed;
        }

        // URL Sharing Functions
        function generateShareLink() {
            const rawData = getAllFormData();
            const compressedData = compressTextData(rawData);
            
            // For URL sharing, we need to be more aggressive with compression
            // Remove art images for URL sharing (they make URLs too long)
            const urlData = { ...compressedData };
            delete urlData.artImages; // Images would make URL too long
            
            try {
                const jsonString = JSON.stringify(urlData);
                const compressed = LZString.compress(jsonString);
                const encoded = btoa(compressed).replace(/[+/=]/g, function(match) {
                    return {'=':'','+':'-','/':'_'}[match];
                });
                
                const shareUrl = window.location.origin + window.location.pathname + '?c=' + encoded;
                
                document.getElementById('shareUrlOutput').value = shareUrl;
                document.getElementById('shareLinkSection').classList.remove('hidden');
                
                // Show compression stats
                const originalSize = jsonString.length;
                const compressedSize = encoded.length;
                const savings = Math.round((1 - compressedSize / originalSize) * 100);
                
                showNotification(`Share link generated! ${savings}% smaller than raw JSON.`);
                
            } catch (error) {
                console.error('Failed to generate share link:', error);
                showNotification('Error generating share link', 'error');
            }
        }

        function copyShareLink() {
            const shareUrl = document.getElementById('shareUrlOutput');
            shareUrl.select();
            shareUrl.setSelectionRange(0, 99999);
            
            try {
                document.execCommand('copy');
                const copyBtn = document.getElementById('copyBtn');
                const originalText = copyBtn.textContent;
                copyBtn.textContent = 'Copied!';
                copyBtn.style.background = 'linear-gradient(135deg, #2a5934 0%, #4a8f5a 100%)';
                
                setTimeout(() => {
                    copyBtn.textContent = originalText;
                    copyBtn.style.background = '';
                }, 2000);
                
                showNotification('Share link copied to clipboard!');
            } catch (err) {
                // Fallback for browsers that don't support execCommand
                navigator.clipboard?.writeText(shareUrl.value).then(() => {
                    showNotification('Share link copied to clipboard!');
                }).catch(() => {
                    showNotification('Please copy the link manually', 'error');
                });
            }
        }

        function loadFromShareLink() {
            const shareInput = document.getElementById('shareUrlInput').value.trim();
            if (!shareInput) {
                showNotification('Please paste a share link first', 'error');
                return;
            }
            
            try {
                // Extract the compressed data from the URL
                let encoded;
                if (shareInput.includes('?c=')) {
                    encoded = shareInput.split('?c=')[1].split('&')[0];
                } else if (shareInput.includes('&c=')) {
                    encoded = shareInput.split('&c=')[1].split('&')[0];
                } else {
                    // Maybe it's just the encoded part
                    encoded = shareInput;
                }
                
                // Decode the data
                const urlSafe = encoded.replace(/-/g, '+').replace(/_/g, '/');
                // Add padding if needed
                const padded = urlSafe + '='.repeat((4 - urlSafe.length % 4) % 4);
                const compressed = atob(padded);
                const jsonString = LZString.decompress(compressed);
                
                if (!jsonString) {
                    throw new Error('Failed to decompress data');
                }
                
                const data = JSON.parse(jsonString);
                loadFormData(data);
                
                showNotification('Character loaded from share link!');
                document.getElementById('shareUrlInput').value = '';
                document.getElementById('shareLinkSection').classList.add('hidden');
                
            } catch (error) {
                console.error('Failed to load from share link:', error);
                showNotification('Invalid share link format', 'error');
            }
        }

        // Check for shared character on page load
        function checkForSharedCharacter() {
            const urlParams = new URLSearchParams(window.location.search);
            const sharedData = urlParams.get('c');
            
            if (sharedData) {
                try {
                    const urlSafe = sharedData.replace(/-/g, '+').replace(/_/g, '/');
                    const padded = urlSafe + '='.repeat((4 - urlSafe.length % 4) % 4);
                    const compressed = atob(padded);
                    const jsonString = LZString.decompress(compressed);
                    
                    if (jsonString) {
                        const data = JSON.parse(jsonString);
                        loadFormData(data);
                        showNotification('Shared character loaded!');
                        
                        // Clean up URL without reloading page
                        const cleanUrl = window.location.origin + window.location.pathname;
                        window.history.replaceState({}, document.title, cleanUrl);
                    }
                } catch (error) {
                    console.error('Failed to load shared character:', error);
                    showNotification('Invalid shared character data', 'error');
                }
            }
        }

        function exportCharacter() {
            const rawData = getAllFormData();
            const compressedData = compressTextData(rawData);
            
            // Compress images with advanced techniques
            Promise.all(artImages.map(async (art) => {
                const compressed = await compressImage(art.src);
                return { 
                    id: art.id, 
                    src: compressed, 
                    title: art.title?.trim() || '' 
                };
            })).then(compressedImages => {
                // Filter out images with empty titles if they're just placeholder data
                const validImages = compressedImages.filter(img => 
                    img.title || img.src !== artImages.find(a => a.id === img.id)?.src
                );
                
                const exportData = {
                    v: 2, // Version for future compatibility
                    d: new Date().toISOString().split('T')[0], // Date only, not full timestamp
                    data: { 
                        ...compressedData, 
                        artImages: validImages.length > 0 ? validImages : undefined 
                    }
                };

                // Create blob with no pretty printing (removes all unnecessary spaces)
                const jsonString = JSON.stringify(exportData);
                const blob = new Blob([jsonString], { type: 'application/json' });
                const url = URL.createObjectURL(blob);
                const a = document.createElement('a');
                a.href = url;
                
                // Shorter filename
                const name = compressedData.characterName?.replace(/[^a-zA-Z0-9]/g, '') || 'character';
                a.download = `${name}_${Date.now()}.json`;
                
                document.body.appendChild(a);
                a.click();
                document.body.removeChild(a);
                URL.revokeObjectURL(url);
                
                // Show compression stats
                const originalSize = JSON.stringify({
                    exportDate: new Date().toISOString(),
                    data: rawData
                }).length;
                const compressedSize = jsonString.length;
                const savings = Math.round((1 - compressedSize / originalSize) * 100);
                
                showNotification(`Exported! ${savings}% smaller than uncompressed.`);
            });
        }

        function importFromFile(input) {
            const file = input.files[0];
            if (!file) return;

            const reader = new FileReader();
            reader.onload = function(e) {
                try {
                    const importData = JSON.parse(e.target.result);
                    
                    // Handle both new compressed format and legacy format
                    let data;
                    if (importData.v === 2) {
                        // New compressed format
                        data = importData.data;
                    } else {
                        // Legacy format compatibility
                        data = importData.data || importData;
                    }
                    
                    loadFormData(data);
                    showNotification('Character imported successfully!');
                    document.getElementById('importSection').classList.add('hidden');
                } catch (error) {
                    showNotification('Error importing file: Invalid format', 'error');
                    console.error('Import error:', error);
                }
            };
            reader.readAsText(file);
        }

        function showImportSection() {
            const section = document.getElementById('importSection');
            section.classList.toggle('hidden');
            // Hide share section when showing import
            document.getElementById('shareLinkSection').classList.add('hidden');
        }

        function toggleFacet(element) {
            element.classList.toggle('active');
        }

        // Art Library Functions
        function initializeArtLibrary() {
            const dropZone = document.getElementById('artDropZone');
            const fileInput = document.getElementById('fileInput');

            dropZone.addEventListener('dragover', (e) => {
                e.preventDefault();
                dropZone.classList.add('dragover');
            });

            dropZone.addEventListener('dragleave', () => {
                dropZone.classList.remove('dragover');
            });

            dropZone.addEventListener('drop', (e) => {
                e.preventDefault();
                dropZone.classList.remove('dragover');
                handleFiles(e.dataTransfer.files);
            });

            fileInput.addEventListener('change', (e) => {
                handleFiles(e.target.files);
            });
        }

        function handleFiles(files) {
            Array.from(files).forEach(file => {
                if (file.type.startsWith('image/')) {
                    const reader = new FileReader();
                    reader.onload = (e) => {
                        addArtImage(e.target.result, file.name);
                    };
                    reader.readAsDataURL(file);
                }
            });
        }

        function addArtImage(src, originalName) {
            const artId = Date.now() + Math.random();
            const artItem = {
                id: artId,
                src: src,
                title: originalName.replace(/\.[^/.]+$/, "")
            };

            artImages.push(artItem);
            renderArtGallery();
        }

        function removeArtImage(artId) {
            artImages = artImages.filter(art => art.id !== artId);
            renderArtGallery();
        }

        function updateArtTitle(artId, newTitle) {
            const artItem = artImages.find(art => art.id === artId);
            if (artItem) {
                artItem.title = newTitle;
            }
        }

        function renderArtGallery() {
            const gallery = document.getElementById('artGallery');
            gallery.innerHTML = '';

            artImages.forEach(art => {
                const artDiv = document.createElement('div');
                artDiv.className = 'art-item';
                artDiv.innerHTML = `
                    <button class="remove-btn" onclick="removeArtImage(${art.id})">×</button>
                    <img src="${art.src}" alt="${art.title}" class="art-image">
                    <input type="text" class="art-title" value="${art.title}" 
                           onchange="updateArtTitle(${art.id}, this.value)"
                           placeholder="Image title...">
                `;
                gallery.appendChild(artDiv);
            });
        }

        function getAllFormData() {
            const data = {
                characterName: document.getElementById('characterName').value,
                titles: document.getElementById('titles').value,
                level: document.getElementById('level').value,
                race: document.getElementById('race').value,
                age: document.getElementById('age').value,
                alignment: document.getElementById('alignment').value,
                indomitability: document.getElementById('indomitability').value,
                fluidity: document.getElementById('fluidity').value,
                lucidity: document.getElementById('lucidity').value,
                authority: document.getElementById('authority').value,
                currentHP: document.getElementById('currentHP').value,
                maxHP: document.getElementById('maxHP').value,
                defense: document.getElementById('defense').value,
                currentAtramenta: document.getElementById('currentAtramenta').value,
                maxAtramenta: document.getElementById('maxAtramenta').value,
                movement: document.getElementById('movement').value,
                directives: document.getElementById('directives').value,
                weapons: document.getElementById('weapons').value,
                armor: document.getElementById('armor').value,
                tools: document.getElementById('tools').value,
                history: document.getElementById('history').value,
                goals: document.getElementById('goals').value,
                perks: [],
                traits: [],
                blessings: [],
                facets: [],
                artImages: artImages
            };

            // Get perks
            document.querySelectorAll('.perk-input').forEach(input => {
                if (input.value.trim()) {
                    data.perks.push(input.value);
                }
            });

            // Get traits
            document.querySelectorAll('.trait-input').forEach(input => {
                if (input.value.trim()) {
                    data.traits.push(input.value);
                }
            });

            // Get blessings
            const blessingNames = document.querySelectorAll('.blessing-name-input');
            const blessingDescs = document.querySelectorAll('.blessing-desc-input');
            for (let i = 0; i < blessingNames.length; i++) {
                if (blessingNames[i].value.trim() || blessingDescs[i].value.trim()) {
                    data.blessings.push({
                        name: blessingNames[i].value,
                        description: blessingDescs[i].value
                    });
                }
            }

            // Get active facets
            document.querySelectorAll('.facet.active').forEach(facet => {
                data.facets.push(facet.dataset.facet);
            });

            return data;
        }

        function loadFormData(data) {
            if (!data) return;

            // Basic info
            document.getElementById('characterName').value = data.characterName || '';
            document.getElementById('titles').value = data.titles || '';
            document.getElementById('level').value = data.level || '';
            document.getElementById('race').value = data.race || '';
            document.getElementById('age').value = data.age || '';
            document.getElementById('alignment').value = data.alignment || '';

            // Attributes
            document.getElementById('indomitability').value = data.indomitability || '';
            document.getElementById('fluidity').value = data.fluidity || '';
            document.getElementById('lucidity').value = data.lucidity || '';
            document.getElementById('authority').value = data.authority || '';

            // Stats
            document.getElementById('currentHP').value = data.currentHP || '';
            document.getElementById('maxHP').value = data.maxHP || '';
            document.getElementById('defense').value = data.defense || '';
            document.getElementById('currentAtramenta').value = data.currentAtramenta || '';
            document.getElementById('maxAtramenta').value = data.maxAtramenta || '';
            document.getElementById('movement').value = data.movement || '';

            // Text areas
            document.getElementById('directives').value = data.directives || '';
            document.getElementById('weapons').value = data.weapons || '';
            document.getElementById('armor').value = data.armor || '';
            document.getElementById('tools').value = data.tools || '';
            document.getElementById('history').value = data.history || '';
            document.getElementById('goals').value = data.goals || '';

            // Clear existing inputs first
            document.querySelectorAll('.perk-input').forEach(input => input.value = '');
            document.querySelectorAll('.trait-input').forEach(input => input.value = '');
            document.querySelectorAll('.blessing-name-input').forEach(input => input.value = '');
            document.querySelectorAll('.blessing-desc-input').forEach(input => input.value = '');

            // Perks
            const perkInputs = document.querySelectorAll('.perk-input');
            if (data.perks) {
                data.perks.forEach((perk, index) => {
                    if (perkInputs[index]) {
                        perkInputs[index].value = perk;
                    }
                });
            }

            // Traits
            const traitInputs = document.querySelectorAll('.trait-input');
            if (data.traits) {
                data.traits.forEach((trait, index) => {
                    if (traitInputs[index]) {
                        traitInputs[index].value = trait;
                    }
                });
            }

            // Blessings
            const blessingNames = document.querySelectorAll('.blessing-name-input');
            const blessingDescs = document.querySelectorAll('.blessing-desc-input');
            if (data.blessings) {
                data.blessings.forEach((blessing, index) => {
                    if (blessingNames[index]) {
                        blessingNames[index].value = blessing.name || '';
                    }
                    if (blessingDescs[index]) {
                        blessingDescs[index].value = blessing.description || '';
                    }
                });
            }

            // Clear existing facets first
            document.querySelectorAll('.facet').forEach(facet => {
                facet.classList.remove('active');
            });

            // Facets
            if (data.facets) {
                data.facets.forEach(facetName => {
                    const facet = document.querySelector(`[data-facet="${facetName}"]`);
                    if (facet) {
                        facet.classList.add('active');
                    }
                });
            }

            // Art Images
            artImages = [];
            if (data.artImages) {
                artImages = data.artImages;
                renderArtGallery();
            }
        }

        function showNotification(message, type = 'success') {
            const notification = document.getElementById('notification');
            notification.textContent = message;
            notification.classList.add('show');
            
            if (type === 'error') {
                notification.style.background = 'linear-gradient(135deg, #8b1e1e 0%, #b91e1e 100%)';
            } else {
                notification.style.background = 'linear-gradient(135deg, #2a5934 0%, #4a8f5a 100%)';
            }
            
            setTimeout(() => {
                notification.classList.remove('show');
            }, 3000);
        }

        // Initialize on page load
        window.addEventListener('load', () => {
            initializeArtLibrary();
            checkForSharedCharacter();
        });

        // Keyboard shortcuts
        document.addEventListener('keydown', (e) => {
            if (e.ctrlKey || e.metaKey) {
                if (e.key === 'e') {
                    e.preventDefault();
                    exportCharacter();
                } else if (e.key === 's') {
                    e.preventDefault();
                    generateShareLink();
                }
            }
        });
    </script>
</body>
</html>
