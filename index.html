<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Gõ Phím Tốc Độ - Vietnamese Typing Test</title>
    <style>
        /* --- CSS STYLES --- */
        :root {
            --primary: #3498db;
            --success: #2ecc71;
            --error: #e74c3c;
            --bg: #f4f7f6;
            --text: #2c3e50;
        }

        body {
            font-family: 'Segoe UI', Arial, sans-serif;
            background-color: var(--bg);
            color: var(--text);
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            margin: 0;
        }

        .container {
            background: white;
            padding: 30px;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            width: 90%;
            max-width: 800px;
        }

        h1 { text-align: center; margin-bottom: 20px; }

        /* Chọn thời gian */
        .settings {
            display: flex;
            justify-content: center;
            gap: 10px;
            margin-bottom: 20px;
        }

        .time-btn {
            border: 2px solid var(--primary);
            background: transparent;
            color: var(--primary);
            padding: 8px 20px;
            border-radius: 20px;
            cursor: pointer;
            font-weight: bold;
            transition: 0.3s;
        }

        .time-btn.active {
            background: var(--primary);
            color: white;
        }

        /* Khung hiển thị chữ */
        .word-box {
            background: #fdfdfd;
            border: 1px solid #ddd;
            padding: 20px;
            border-radius: 10px;
            font-size: 24px;
            line-height: 1.8;
            height: 120px;
            overflow: hidden;
            margin-bottom: 25px;
            display: flex;
            flex-wrap: wrap;
            gap: 12px;
            user-select: none;
            position: relative;
        }

        .word { color: #95a5a6; transition: 0.1s; }
        .current { 
            background: #e1eaf2; 
            border-radius: 4px; 
            color: #2c3e50;
            padding: 0 5px;
        }
        .correct { color: var(--success); }
        .incorrect { color: var(--error); text-decoration: underline; }

        /* Vùng nhập liệu */
        .input-area {
            display: flex;
            gap: 15px;
            align-items: center;
        }

        input {
            flex: 1;
            padding: 15px;
            font-size: 1.2rem;
            border: 2px solid #ddd;
            border-radius: 10px;
            outline: none;
            transition: 0.3s;
        }

        input:focus { border-color: var(--primary); box-shadow: 0 0 8px rgba(52, 152, 219, 0.3); }

        #timer {
            font-size: 1.8rem;
            font-weight: bold;
            color: var(--primary);
            min-width: 60px;
            text-align: center;
        }

        #reset-btn {
            background: #95a5a6;
            color: white;
            border: none;
            padding: 12px 20px;
            border-radius: 10px;
            cursor: pointer;
            font-size: 1.2rem;
        }

        /* Kết quả */
        #result-modal {
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(0,0,0,0.85);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 100;
        }

        .result-content {
            background: white;
            padding: 40px;
            border-radius: 20px;
            text-align: center;
            max-width: 400px;
            width: 80%;
        }

        .stats { display: flex; justify-content: space-around; margin: 20px 0; }
        .stat-item span { display: block; font-size: 2rem; font-weight: bold; color: var(--primary); }
        
        .hidden { display: none !important; }

        button.play-again {
            background: var(--success);
            color: white;
            border: none;
            padding: 10px 30px;
            border-radius: 5px;
            font-size: 1rem;
            cursor: pointer;
        }
    </style>
</head>
<body>

    <div class="container">
        <h1>⌨️ Typing Test VN</h1>
        
        <div class="settings">
            <button class="time-btn active" data-time="30">30s</button>
            <button class="time-btn" data-time="60">1p</button>
            <button class="time-btn" data-time="120">2p</button>
            <button class="time-btn" data-time="300">5p</button>
        </div>

        <div id="word-display" class="word-box"></div>

        <div class="input-area">
            <input type="text" id="word-input" placeholder="Bắt đầu gõ để tính giờ..." autofocus autocomplete="off">
            <div id="timer">30</div>
            <button id="reset-btn" title="Làm lại">🔄</button>
        </div>

        <div id="result-modal" class="hidden">
            <div class="result-content">
                <h2>Kết quả của bạn</h2>
                <div class="stats">
                    <div class="stat-item">
                        <span id="wpm-score">0</span> WPM
                    </div>
                    <div class="stat-item">
                        <span id="accuracy-score">0</span> %
                    </div>
                </div>
                <button class="play-again" onclick="resetGame()">Thử lại lần nữa</button>
            </div>
        </div>
    </div>

    <script>
        /* --- JAVASCRIPT LOGIC --- */
        
        // Danh sách từ vựng random theo yêu cầu (ngăn cách bởi |)
        const rawDictionary = "chào|học|sinh|trường|chuyên|nghiệp|lập|trình|viên|công|nghệ|thông|tin|việt|nam|thành|phố|tốc|độ|nhanh|chính|xác|bàn|phím|máy|tính|thông|minh|tư|duy|sáng|tạo|vui|vẻ|hạnh|phúc|nỗ|lực|thành|công|tương|lai|phát|triển|khám|phá|kiến|thức|mỗi|ngày|rèn|luyện|kỹ|năng|làm|việc|nhóm|đam|mê|vượt|qua|thử|thách";
        const dictionary = rawDictionary.split('|');

        let words = [];
        let currentIndex = 0;
        let timeLeft = 30;
        let timer = null;
        let isRunning = false;
        let correctChars = 0;
        let totalChars = 0;

        const wordDisplay = document.getElementById('word-display');
        const wordInput = document.getElementById('word-input');
        const timerDisplay = document.getElementById('timer');
        const resultModal = document.getElementById('result-modal');
        const timeBtns = document.querySelectorAll('.time-btn');

        // Khởi tạo danh sách từ ngẫu nhiên
        function init() {
            words = [];
            for (let i = 0; i < 250; i++) {
                const randomWord = dictionary[Math.floor(Math.random() * dictionary.length)];
                words.push(randomWord);
            }
            currentIndex = 0;
            renderWords();
        }

        function renderWords() {
            wordDisplay.innerHTML = words.map((w, i) => `<span class="word" id="word-${i}">${w}</span>`).join('');
            setActiveWord();
        }

        function setActiveWord() {
            const currentEl = document.getElementById(`word-${currentIndex}`);
            if (currentEl) {
                currentEl.classList.add('current');
                // Cuộn mượt mà khi gõ xuống dòng mới
                wordDisplay.scrollTop = currentEl.offsetTop - 40;
            }
        }

        // Bắt đầu đếm ngược
        function startTimer() {
            if (isRunning) return;
            isRunning = true;
            timer = setInterval(() => {
                timeLeft--;
                timerDisplay.innerText = timeLeft;
                if (timeLeft <= 0) endGame();
            }, 1000);
        }

        // Kết thúc và tính điểm
        function endGame() {
            clearInterval(timer);
            isRunning = false;
            wordInput.disabled = true;
            
            // Công thức chuẩn WPM = (Tổng số ký tự đúng / 5) / (số phút)
            const timeInMinutes = parseInt(document.querySelector('.time-btn.active').dataset.time) / 60;
            const wpm = Math.round((correctChars / 5) / timeInMinutes);
            const accuracy = totalChars > 0 ? Math.round((correctChars / totalChars) * 100) : 0;

            document.getElementById('wpm-score').innerText = wpm;
            document.getElementById('accuracy-score').innerText = accuracy;
            resultModal.classList.remove('hidden');
        }

        // Reset game
        function resetGame() {
            clearInterval(timer);
            isRunning = false;
            currentIndex = 0;
            correctChars = 0;
            totalChars = 0;
            timeLeft = parseInt(document.querySelector('.time-btn.active').dataset.time);
            timerDisplay.innerText = timeLeft;
            wordInput.value = "";
            wordInput.disabled = false;
            resultModal.classList.add('hidden');
            init();
            wordInput.focus();
        }

        // Xử lý sự kiện gõ phím
        wordInput.addEventListener('input', (e) => {
            if (!isRunning && wordInput.value.length > 0) {
                startTimer();
            }

            const typedValue = wordInput.value;
            const currentWord = words[currentIndex];

            // Kiểm tra khi nhấn Space
            if (typedValue.endsWith(' ')) {
                const trimmedValue = typedValue.trim();
                const wordEl = document.getElementById(`word-${currentIndex}`);
                
                totalChars += currentWord.length + 1; // +1 cho dấu cách

                if (trimmedValue === currentWord) {
                    wordEl.classList.add('correct');
                    correctChars += currentWord.length + 1;
                } else {
                    wordEl.classList.add('incorrect');
                }

                wordEl.classList.remove('current');
                currentIndex++;
                wordInput.value = "";
                setActiveWord();
            }
        });

        // Chọn mốc thời gian
        timeBtns.forEach(btn => {
            btn.addEventListener('click', () => {
                timeBtns.forEach(b => b.classList.remove('active'));
                btn.classList.add('active');
                resetGame();
            });
        });

        // Bắt đầu khi quay lại tab (theo yêu cầu)
        window.addEventListener('focus', () => {
            wordInput.focus();
        });

        document.getElementById('reset-btn').addEventListener('click', resetGame);

        // Chạy khởi tạo lần đầu
        init();
    </script>
</body>
</html>
