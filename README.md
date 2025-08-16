<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Character Codex</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Cinzel:wght@400;600;700&family=Cinzel+Decorative:wght@400;700&display=swap');
        
        body {
            margin: 0;
            padding: 20px;
            background: #000000;
            font-family: 'Cinzel', serif;
            color: #ffffff;
            min-height: 100vh;
            background-image: 
                radial-gradient(circle at 20% 50%, rgba(255, 0, 0, 0.1) 0%, transparent 50%),
                radial-gradient(circle at 80% 20%, rgba(0, 100, 255, 0.1) 0%, transparent 50%),
                radial-gradient(circle at 40% 80%, rgba(255, 255, 255, 0.05) 0%, transparent 50%);
        }
        
        .character-sheet {
            max-width: 1200px;
            margin: 0 auto;
            background: linear-gradient(135deg, #0a0a0a 0%, #1a1a1a 50%, #000000 100%);
            border: 3px solid #ffffff;
            border-radius: 0;
            position: relative;
            padding: 40px;
            box-shadow: 
                0 0 50px rgba(255, 255, 255, 0.2),
                inset 0 0 50px rgba(0, 0, 0, 0.8);
        }
        
        .character-sheet::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(45deg, 
                transparent 30%, 
                rgba(255, 255, 255, 0.03) 50%, 
                transparent 70%);
            pointer-events: none;
        }
        
        .header {
            text-align: center;
            margin-bottom: 40px;
            border-bottom: 3px solid #ffffff;
            padding-bottom: 30px;
            position: relative;
        }
        
        .header::after {
            content: '';
            position: absolute;
            bottom: -3px;
            left: 50%;
            transform: translateX(-50%);
            width: 60px;
            height: 3px;
            background: #ff0000;
        }
        
        .title {
            font-family: 'Cinzel Decorative', serif;
            font-size: 3em;
            font-weight: 700;
            color: #ffffff;
            text-shadow: 
                0 0 10px rgba(255, 255, 255, 0.5),
                0 0 20px rgba(255, 255, 255, 0.3),
                0 0 30px rgba(255, 255, 255, 0.1);
            margin-bottom: 15px;
            letter-spacing: 3px;
        }

        .share-buttons {
            text-align: center;
            margin-bottom: 30px;
        }

        .btn {
            background: linear-gradient(135deg, #000000 0%, #333333 50%, #000000 100%);
            border: 2px solid #ffffff;
            color: #ffffff;
            padding: 12px 25px;
            margin: 0 8px;
            border-radius: 0;
            cursor: pointer;
            font-family: 'Cinzel', serif;
            font-size: 0.9em;
            text-transform: uppercase;
            letter-spacing: 2px;
            transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.5);
        }

        .btn:hover {
            background: linear-gradient(135deg, #ffffff 0%, #cccccc 50%, #ffffff 100%);
            color: #000000;
            transform: translateY(-2px);
            box-shadow: 0 6px 20px rgba(255, 255, 255, 0.3);
        }

        .btn.success {
            background: linear-gradient(135deg, #1a1a1a 0%, #444444 50%, #1a1a1a 100%);
            border-color: #00ff00;
        }

        .btn.success:hover {
            background: linear-gradient(135deg, #00ff00 0%, #00cc00 50%, #00ff00 100%);
            color: #000000;
        }

        .load-section {
            background: linear-gradient(135deg, #0a0a0a 0%, #1a1a1a 100%);
            border: 2px solid #666666;
            border-radius: 0;
            padding: 20px;
            margin: 15px 0;
            text-align: left;
            box-shadow: inset 0 0 20px rgba(0, 0, 0, 0.8);
        }

        .load-section input {
            width: 100%;
            background: #000000;
            border: 1px solid #ffffff;
            color: #ffffff;
            padding: 10px;
            border-radius: 0;
            font-family: 'Cinzel', serif;
            margin: 8px 0;
            box-shadow: inset 0 0 10px rgba(0, 0, 0, 0.8);
        }

        .load-section input:focus {
            outline: none;
            border-color: #ff0000;
            box-shadow: 0 0 15px rgba(255, 0, 0, 0.5);
        }
        
        .name-section {
            text-align: center;
            margin-bottom: 40px;
            background: linear-gradient(135deg, #000000 0%, #1a1a1a 50%, #000000 100%);
            border: 3px solid #ffffff;
            border-radius: 0;
            padding: 35px;
            position: relative;
            box-shadow: 
                0 0 30px rgba(255, 255, 255, 0.2),
                inset 0 0 30px rgba(0, 0, 0, 0.8);
        }
        
        .name-section::before {
            content: '';
            position: absolute;
            top: 10px;
            left: 10px;
            right: 10px;
            bottom: 10px;
            border: 1px solid rgba(255, 255, 255, 0.3);
            pointer-events: none;
        }
        
        .name-input {
            font-family: 'Cinzel Decorative', serif;
            font-size: 2.5em;
            font-weight: 700;
            background: transparent;
            border: none;
            border-bottom: 4px solid #ffffff;
            color: #ffffff;
            text-align: center;
            width: 100%;
            max-width: 600px;
            padding: 15px;
            margin-bottom: 20px;
            text-shadow: 0 0 15px rgba(255, 255, 255, 0.5);
        }
        
        .name-input:focus {
            outline: none;
            border-bottom-color: #ff0000;
            text-shadow: 0 0 20px rgba(255, 255, 255, 0.8);
            box-shadow: 0 5px 25px rgba(255, 0, 0, 0.3);
        }
        
        .name-input::placeholder {
            color: #666666;
            opacity: 0.7;
        }
        
        .titles-input {
            font-family: 'Cinzel', serif;
            font-size: 1.4em;
            background: transparent;
            border: none;
            border-bottom: 2px solid #cccccc;
            color: #cccccc;
            text-align: center;
            width: 100%;
            max-width: 700px;
            padding: 10px;
            font-style: italic;
        }
        
        .titles-input:focus {
            outline: none;
            border-bottom-color: #ffffff;
            color: #ffffff;
        }
        
        .titles-input::placeholder {
            color: #555555;
            opacity: 0.8;
        }
        
        .main-grid {
            display: grid;
            grid-template-columns: 1fr 1fr 1fr;
            gap: 30px;
            margin-bottom: 30px;
        }
        
        .section {
            background: linear-gradient(135deg, #000000 0%, #1a1a1a 50%, #000000 100%);
            border: 2px solid #ffffff;
            border-radius: 0;
            padding: 25px;
            position: relative;
            box-shadow: 
                0 0 25px rgba(255, 255, 255, 0.1),
                inset 0 0 25px rgba(0, 0, 0, 0.8);
        }
        
        .section::before {
            content: '';
            position: absolute;
            top: 8px;
            left: 8px;
            right: 8px;
            bottom: 8px;
            border: 1px solid rgba(255, 255, 255, 0.2);
            pointer-events: none;
        }
        
        .section-title {
            font-family: 'Cinzel Decorative', serif;
            font-size: 1.5em;
            font-weight: 700;
            color: #ffffff;
            text-align: center;
            margin-bottom: 20px;
            text-transform: uppercase;
            letter-spacing: 3px;
            border-bottom: 2px solid #ffffff;
            padding-bottom: 10px;
            text-shadow: 0 0 10px rgba(255, 255, 255, 0.5);
        }
        
        .basic-info {
            grid-column: 1 / -1;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 25px;
        }
        
        .info-field {
            display: flex;
            flex-direction: column;
        }
        
        .info-field label {
            font-family: 'Cinzel', serif;
            font-weight: 600;
            color: #ffffff;
            margin-bottom: 8px;
            text-transform: uppercase;
            font-size: 0.9em;
            letter-spacing: 2px;
        }
        
        .info-field input, .info-field textarea {
            background: #000000;
            border: 2px solid #ffffff;
            border-radius: 0;
            padding: 12px;
            color: #ffffff;
            font-family: 'Cinzel', serif;
            box-shadow: inset 0 0 10px rgba(0, 0, 0, 0.8);
        }
        
        .info-field input:focus, .info-field textarea:focus {
            outline: none;
            border-color: #ff0000;
            box-shadow: 
                inset 0 0 10px rgba(0, 0, 0, 0.8),
                0 0 15px rgba(255, 0, 0, 0.5);
        }
        
        .attributes-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
        }
        
        .attribute {
            display: flex;
            align-items: center;
            background: linear-gradient(135deg, #000000 0%, #0a0a0a 100%);
            border: 2px solid #ffffff;
            border-radius: 0;
            padding: 15px;
            box-shadow: inset 0 0 15px rgba(0, 0, 0, 0.8);
        }
        
        .attribute-letter {
            font-family: 'Cinzel Decorative', serif;
            font-size: 2.2em;
            font-weight: 700;
            color: #ffffff;
            width: 50px;
            text-align: center;
            margin-right: 20px;
            text-shadow: 
                0 0 10px rgba(255, 255, 255, 0.5),
                0 0 20px rgba(255, 255, 255, 0.3);
        }
        
        .attribute-details {
            flex: 1;
        }
        
        .attribute-name {
            font-family: 'Cinzel', serif;
            font-weight: 700;
            color: #ffffff;
            font-size: 1.1em;
            margin-bottom: 5px;
            text-transform: uppercase;
            letter-spacing: 1px;
        }
        
        .attribute-desc {
            font-family: 'Cinzel', serif;
            font-size: 0.8em;
            color: #cccccc;
            line-height: 1.4;
            font-style: italic;
        }
        
        .attribute-score {
            text-align: center;
            margin-left: 20px;
        }
        
        .attribute-score input {
            width: 60px;
            height: 60px;
            text-align: center;
            font-size: 1.6em;
            font-weight: bold;
            background: #000000;
            border: 3px solid #ffffff;
            border-radius: 0;
            color: #ffffff;
            font-family: 'Cinzel Decorative', serif;
            box-shadow: inset 0 0 15px rgba(0, 0, 0, 0.8);
        }
        
        .attribute-score input:focus {
            border-color: #ff0000;
            box-shadow: 
                inset 0 0 15px rgba(0, 0, 0, 0.8),
                0 0 15px rgba(255, 0, 0, 0.5);
        }
        
        .stats-section {
            display: flex;
            flex-direction: column;
        }
        
        .stats-stats {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
        }
        
        .stat-box {
            background: linear-gradient(135deg, #000000 0%, #0a0a0a 100%);
            border: 2px solid #ffffff;
            border-radius: 0;
            padding: 15px;
            text-align: center;
            box-shadow: inset 0 0 15px rgba(0, 0, 0, 0.8);
        }
        
        .stat-label {
            font-family: 'Cinzel', serif;
            font-size: 1em;
            color: #ffffff;
            margin-bottom: 8px;
            text-transform: uppercase;
            font-weight: 600;
            letter-spacing: 2px;
        }
        
        .stat-value {
            font-family: 'Cinzel Decorative', serif;
            font-size: 1.3em;
            font-weight: bold;
            color: #ffffff;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
        }

        .stat-input {
            width: 60px;
            height: 45px;
            background: transparent;
            border: none;
            color: #ffffff;
            text-align: center;
            font-size: 1.3em;
            font-family: 'Cinzel Decorative', serif;
            font-weight: bold;
            border-bottom: 2px solid #ffffff;
        }

        .stat-input:focus {
            outline: none;
            background: rgba(255, 255, 255, 0.05);
            border-bottom-color: #ff0000;
            box-shadow: 0 0 10px rgba(255, 0, 0, 0.3);
        }
        
        .thaumaturgy-section {
            grid-column: 1 / -1;
        }
        
        .facets-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 20px;
            margin-top: 20px;
        }
        
        .facet {
            background: linear-gradient(135deg, #000000 0%, #0a0a0a 100%);
            border: 2px solid #ffffff;
            border-radius: 0;
            padding: 20px;
            text-align: center;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: inset 0 0 15px rgba(0, 0, 0, 0.8);
        }
        
        .facet:hover {
            background: linear-gradient(135deg, #1a1a1a 0%, #2a2a2a 100%);
            border-color: #ff0000;
            transform: translateY(-3px);
            box-shadow: 
                inset 0 0 15px rgba(0, 0, 0, 0.8),
                0 5px 20px rgba(255, 0, 0, 0.3);
        }
        
        .facet.active {
            background: linear-gradient(135deg, #ffffff 0%, #cccccc 100%);
            color: #000000;
            border-color: #000000;
        }
        
        .facet-name {
            font-family: 'Cinzel', serif;
            font-weight: 700;
            margin-bottom: 8px;
            text-transform: uppercase;
            letter-spacing: 1px;
        }
        
        .facet-desc {
            font-family: 'Cinzel', serif;
            font-size: 0.8em;
            opacity: 0.8;
            font-style: italic;
        }
        
        .perks-traits-section {
            grid-column: 1 / -1;
        }
        
        .perks-traits-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 40px;
            margin-top: 20px;
        }
        
        .perks-column, .traits-column {
            background: linear-gradient(135deg, #000000 0%, #0a0a0a 100%);
            border: 2px solid #ffffff;
            border-radius: 0;
            padding: 20px;
            box-shadow: inset 0 0 20px rgba(0, 0, 0, 0.8);
        }
        
        .perks-column h4, .traits-column h4 {
            font-family: 'Cinzel Decorative', serif;
            color: #ffffff;
            border-bottom: 2px solid #ffffff;
            padding-bottom: 8px;
            margin-bottom: 15px;
            text-transform: uppercase;
            letter-spacing: 2px;
            text-shadow: 0 0 10px rgba(255, 255, 255, 0.5);
        }
        
        .perk-item, .trait-item {
            background: #000000;
            border: 1px solid #666666;
            border-radius: 0;
            padding: 10px;
            margin-bottom: 10px;
            font-family: 'Cinzel', serif;
            font-size: 0.9em;
            box-shadow: inset 0 0 10px rgba(0, 0, 0, 0.8);
        }
        
        .perk-item input, .trait-item input {
            width: 100%;
            background: transparent;
            border: none;
            color: #ffffff;
            font-family: 'Cinzel', serif;
        }
        
        .perk-item input:focus, .trait-item input:focus {
            outline: none;
            color: #ff0000;
        }

        .blessings-section {
            grid-column: 1 / -1;
            margin-top: 30px;
        }

        .blessings-grid {
            display: grid;
            grid-template-columns: 1fr;
            gap: 20px;
            margin-top: 20px;
            max-width: 900px;
            margin-left: auto;
            margin-right: auto;
        }

        .blessing-item {
            background: linear-gradient(135deg, #000000 0%, #0a0a0a 100%);
            border: 2px solid #ffffff;
            border-radius: 0;
            padding: 20px;
            box-shadow: inset 0 0 20px rgba(0, 0, 0, 0.8);
        }

        .blessing-name {
            margin-bottom: 15px;
        }

        .blessing-name input {
            width: 100%;
            background: transparent;
            border: none;
            border-bottom: 2px solid #ffffff;
            color: #ffffff;
            font-family: 'Cinzel', serif;
            font-weight: 600;
            font-size: 1.2em;
            padding: 8px 0;
        }

        .blessing-name input:focus {
            outline: none;
            border-bottom-color: #ff0000;
            color: #ff0000;
        }

        .blessing-description textarea {
            width: 100%;
            height: 70px;
            background: #000000;
            border: 1px solid #666666;
            border-radius: 0;
            color: #cccccc;
            font-family: 'Cinzel', serif;
            font-size: 0.9em;
            padding: 10px;
            resize: vertical;
            box-shadow: inset 0 0 10px rgba(0, 0, 0, 0.8);
        }

        .blessing-description textarea:focus {
            outline: none;
            border-color: #ffffff;
            color: #ffffff;
        }
        
        .equipment-section {
            grid-column: 1 / -1;
        }
        
        .equipment-grid {
            display: grid;
            grid-template-columns: 1fr 1fr 1fr;
            gap: 25px;
            margin-top: 20px;
        }
        
        .equipment-category h4 {
            font-family: 'Cinzel Decorative', serif;
            color: #ffffff;
            border-bottom: 2px solid #ffffff;
            padding-bottom: 8px;
            margin-bottom: 15px;
            text-transform: uppercase;
            letter-spacing: 2px;
            text-shadow: 0 0 10px rgba(255, 255, 255, 0.5);
        }
        
        .equipment-list {
            max-height: 160px;
            overflow-y: auto;
        }
        
        .equipment-list::-webkit-scrollbar {
            width: 8px;
        }
        
        .equipment-list::-webkit-scrollbar-track {
            background: #000000;
            border: 1px solid #666666;
        }
        
        .equipment-list::-webkit-scrollbar-thumb {
            background: #ffffff;
            border-radius: 0;
        }

        .equipment-list textarea {
            background: #000000;
            border: 2px solid #ffffff;
            color: #ffffff;
            font-family: 'Cinzel', serif;
            border-radius: 0;
            padding: 10px;
            resize: none;
            box-shadow: inset 0 0 15px rgba(0, 0, 0, 0.8);
        }

        .equipment-list textarea:focus {
            outline: none;
            border-color: #ff0000;
            box-shadow: 
                inset 0 0 15px rgba(0, 0, 0, 0.8),
                0 0 15px rgba(255, 0, 0, 0.5);
        }
        
        .notes-section {
            grid-column: 1 / -1;
            margin-top: 30px;
        }
        
        .notes-textarea {
            width: 100%;
            min-height: 120px;
            resize: vertical;
            background: #000000;
            border: 2px solid #ffffff;
            color: #ffffff;
            font-family: 'Cinzel', serif;
            border-radius: 0;
            padding: 15px;
            box-shadow: inset 0 0 20px rgba(0, 0, 0, 0.8);
        }

        .notes-textarea:focus {
            outline: none;
            border-color: #ff0000;
            box-shadow: 
                inset 0 0 20px rgba(0, 0, 0, 0.8),
                0 0 15px rgba(255, 0, 0, 0.5);
        }
        
        .ornamental {
            text-align: center;
            font-family: 'Cinzel Decorative', serif;
            font-size: 2.5em;
            color: #ffffff;
            margin: 30px 0;
            text-shadow: 0 0 20px rgba(255, 255, 255, 0.5);
        }

        .notification {
            position: fixed;
            top: 30px;
            right: 30px;
            background: linear-gradient(135deg, #000000 0%, #1a1a1a 100%);
            color: #ffffff;
            padding: 20px 25px;
            border-radius: 0;
            border: 2px solid #00ff00;
            font-family: 'Cinzel', serif;
            z-index: 1000;
            transform: translateX(400px);
            transition: transform 0.3s ease;
            box-shadow: 0 0 30px rgba(0, 255, 0, 0.5);
        }

        .notification.show {
            transform: translateX(0);
        }

        .art-library-section {
            grid-column: 1 / -1;
            margin-top: 40px;
            background: linear-gradient(135deg, #000000 0%, #1a1a1a 50%, #000000 100%);
            border: 3px solid #ffffff;
            border-radius: 0;
            padding: 40px;
            position: relative;
            box-shadow: 
                0 0 40px rgba(255, 255, 255, 0.2),
                inset 0 0 40px rgba(0, 0, 0, 0.8);
        }

        .art-library-section::before {
            content: '';
            position: absolute;
            top: 12px;
            left: 12px;
            right: 12px;
            bottom: 12px;
            border: 1px solid rgba(255, 255, 255, 0.3);
            pointer-events: none;
        }

        .art-library-title {
            font-family: 'Cinzel Decorative', serif;
            font-size: 2.5em;
            font-weight: 700;
            color: #ffffff;
            text-align: center;
            margin-bottom: 40px;
            text-transform: uppercase;
            letter-spacing: 4px;
            text-shadow: 
                0 0 15px rgba(255, 255, 255, 0.5),
                0 0 30px rgba(255, 255, 255, 0.3);
        }

        .art-drop-zone {
            border: 3px dashed #666666;
            border-radius: 0;
            padding: 80px 50px;
            text-align: center;
            background: rgba(0, 0, 0, 0.8);
            transition: all 0.3s ease;
            cursor: pointer;
            position: relative;
            min-height: 250px;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            box-shadow: inset 0 0 30px rgba(0, 0, 0, 0.8);
        }

        .art-drop-zone:hover {
            border-color: #ffffff;
            background: rgba(255, 255, 255, 0.05);
            box-shadow: 
                inset 0 0 30px rgba(0, 0, 0, 0.8),
                0 0 20px rgba(255, 255, 255, 0.2);
        }

        .art-drop-zone.dragover {
            border-color: #ff0000;
            background: rgba(255, 0, 0, 0.1);
            transform: scale(1.02);
            box-shadow: 0 0 30px rgba(255, 0, 0, 0.3);
        }

        .drop-text {
            font-family: 'Cinzel Decorative', serif;
            font-size: 1.6em;
            color: #ffffff;
            margin-bottom: 20px;
            text-transform: uppercase;
            letter-spacing: 2px;
            text-shadow: 0 0 10px rgba(255, 255, 255, 0.5);
        }

        .drop-subtext {
            font-family: 'Cinzel', serif;
            font-size: 1em;
            color: #aaaaaa;
            text-transform: uppercase;
            letter-spacing: 3px;
            font-style: italic;
        }

        .file-input {
            display: none;
        }

        .art-gallery {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 25px;
            margin-top: 40px;
        }

        .art-item {
            background: linear-gradient(135deg, #000000 0%, #0a0a0a 100%);
            border: 2px solid #ffffff;
            border-radius: 0;
            padding: 20px;
            text-align: center;
            position: relative;
            transition: all 0.3s ease;
            box-shadow: inset 0 0 20px rgba(0, 0, 0, 0.8);
        }

        .art-item:hover {
            transform: translateY(-5px);
            border-color: #ff0000;
            box-shadow: 
                inset 0 0 20px rgba(0, 0, 0, 0.8),
                0 10px 30px rgba(255, 0, 0, 0.3);
        }

        .art-image {
            width: 100%;
            height: 220px;
            object-fit: cover;
            border-radius: 0;
            border: 1px solid #666666;
            filter: contrast(1.2) brightness(0.9);
        }

        .art-title {
            font-family: 'Cinzel', serif;
            color: #ffffff;
            margin-top: 15px;
            font-size: 1em;
            padding: 8px;
            background: transparent;
            border: none;
            border-bottom: 1px solid #666666;
            text-align: center;
            width: 100%;
        }

        .art-title:focus {
            outline: none;
            border-bottom-color: #ffffff;
            color: #ff0000;
        }

        .remove-btn {
            position: absolute;
            top: 15px;
            right: 15px;
            background: rgba(255, 0, 0, 0.9);
            border: 2px solid #ffffff;
            border-radius: 0;
            width: 30px;
            height: 30px;
            color: white;
            cursor: pointer;
            font-size: 16px;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.3s ease;
            font-family: 'Cinzel', serif;
            font-weight: bold;
        }

        .remove-btn:hover {
            background: rgba(255, 255, 255, 0.9);
            color: #000000;
            transform: scale(1.1);
        }

        .hidden {
            display: none !important;
        }

        .storage-info {
            background: #111111;
            border: 1px solid #666666;
            border-radius: 0;
            padding: 15px;
            margin: 15px 0;
            font-size: 0.8em;
            color: #aaaaaa;
            font-family: 'Cinzel', serif;
            font-style: italic;
        }

        /* Additional noir aesthetic enhancements */
        .quote-section {
            text-align: center;
            font-style: italic;
            margin-bottom: 20px;
            color: #cccccc;
            font-family: 'Cinzel', serif;
            font-size: 1.1em;
            padding: 15px;
            border-left: 3px solid #ffffff;
            border-right: 3px solid #ffffff;
            background: rgba(255, 255, 255, 0.02);
        }

        /* Scrollbar styling for consistency */
        ::-webkit-scrollbar {
            width: 8px;
        }

        ::-webkit-scrollbar-track {
            background: #000000;
            border: 1px solid #333333;
        }

        ::-webkit-scrollbar-thumb {
            background: #ffffff;
            border-radius: 0;
        }

        ::-webkit-scrollbar-thumb:hover {
            background: #cccccc;
        }

        /* Responsive adjustments */
        @media (max-width: 768px) {
            .main-grid {
                grid-template-columns: 1fr;
            }
            
            .attributes-grid {
                grid-template-columns: 1fr;
            }
            
            .stats-stats {
                grid-template-columns: 1fr;
            }
            
            .perks-traits-grid {
                grid-template-columns: 1fr;
            }
            
            .equipment-grid {
                grid-template-columns: 1fr;
            }
            
            .facets-grid {
                grid-template-columns: 1fr 1fr;
            }
            
            .title {
                font-size: 2em;
            }
            
            .name-input {
                font-size: 1.8em;
            }
        }
    </style>
</head>
<body>
    <div class="character-sheet">
        <div class="header">
            <div class="title">CHARACTER CODEX</div>
            <div class="share-buttons">
                <button class="btn" onclick="exportCharacter()">Export Data</button>
                <button class="btn" onclick="showImportSection()">Import Data</button>
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
            
            <div class="section stats-section"
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
            <div class="quote-section">
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
            
            <div style="margin-top: 25px;">
                <label style="color: #ffffff; font-weight: 600; font-family: 'Cinzel', serif; text-transform: uppercase; letter-spacing: 1px;">Known Directives:</label>
                <textarea id="directives" style="width: 100%; height: 90px; background: #000000; border: 2px solid #ffffff; color: #ffffff; font-family: 'Cinzel', serif; border-radius: 0; padding: 15px; resize: vertical; margin-top: 10px; box-shadow: inset 0 0 15px rgba(0, 0, 0, 0.8);" placeholder="List your known directives..."></textarea>
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
                        <textarea id="weapons" style="width: 100%; height: 130px;" placeholder="List weapons..."></textarea>
                    </div>
                </div>
                
                <div class="equipment-category">
                    <h4>Armor & Protection</h4>
                    <div class="equipment-list">
                        <textarea id="armor" style="width: 100%; height: 130px;" placeholder="List armor..."></textarea>
                    </div>
                </div>
                
                <div class="equipment-category">
                    <h4>Tools & Gear</h4>
                    <div class="equipment-list">
                        <textarea id="tools" style="width: 100%; height: 130px;" placeholder="List gear..."></textarea>
                    </div>
                </div>
            </div>
        </div>
        
        <div class="section notes-section">
            <div class="section-title">Background & Notes</div>
            <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 25px;">
                <div>
                    <label style="color: #ffffff; font-weight: 600; display: block; margin-bottom: 8px; font-family: 'Cinzel', serif; text-transform: uppercase; letter-spacing: 1px;">Personal History:</label>
                    <textarea id="history" class="notes-textarea" placeholder="Character background..."></textarea>
                </div>
                
                <div>
                    <label style="color: #ffffff; font-weight: 600; display: block; margin-bottom: 8px; font-family: 'Cinzel', serif; text-transform: uppercase; letter-spacing: 1px;">Goals & Motivations:</label>
                    <textarea id="goals" class="notes-textarea" placeholder="What drives this character..."></textarea>
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
        
        <div class="ornamental">⧨ ⟐ ⧨</div>
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
                notification.style.background = 'linear-gradient(135deg, #000000 0%, #1a1a1a 100%)';
                notification.style.borderColor = '#ff0000';
                notification.style.boxShadow = '0 0 30px rgba(255, 0, 0, 0.5)';
            } else {
                notification.style.background = 'linear-gradient(135deg, #000000 0%, #1a1a1a 100%)';
                notification.style.borderColor = '#00ff00';
                notification.style.boxShadow = '0 0 30px rgba(0, 255, 0, 0.5)';
            }
            
            setTimeout(() => {
                notification.classList.remove('show');
            }, 3000);
        }

        // Initialize on page load
        window.addEventListener('load', () => {
            initializeArtLibrary();
        });

        // Keyboard shortcuts
        document.addEventListener('keydown', (e) => {
            if (e.ctrlKey || e.metaKey) {
                if (e.key === 'e') {
                    e.preventDefault();
                    exportCharacter();
                }
            }
        });

        // Add some atmospheric effects
        document.addEventListener('DOMContentLoaded', () => {
            // Add subtle glow effects to inputs on focus
            const inputs = document.querySelectorAll('input, textarea');
            inputs.forEach(input => {
                input.addEventListener('focus', () => {
                    input.style.transition = 'all 0.3s ease';
                });
            });

            // Add typing effects for character name
            const nameInput = document.getElementById('characterName');
            nameInput.addEventListener('input', () => {
                if (nameInput.value.length > 0) {
                    nameInput.style.textShadow = '0 0 15px rgba(255, 255, 255, 0.8), 0 0 25px rgba(255, 255, 255, 0.4)';
                } else {
                    nameInput.style.textShadow = '0 0 15px rgba(255, 255, 255, 0.5)';
                }
            });
        });
    </script>
</body>
</html>
