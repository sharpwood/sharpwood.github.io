<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>2026年中考倒计时</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', 'Microsoft YaHei', sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #1a2980, #26d0ce);
            color: #fff;
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 20px;
        }
        
        .container {
            max-width: 900px;
            width: 100%;
            text-align: center;
            padding: 40px 30px;
            background-color: rgba(0, 0, 0, 0.4);
            border-radius: 20px;
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.3);
            backdrop-filter: blur(5px);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .header {
            margin-bottom: 40px;
        }
        
        .header h1 {
            font-size: 2.8rem;
            margin-bottom: 15px;
            color: #fff;
            text-shadow: 0 2px 10px rgba(0, 0, 0, 0.2);
        }
        
        .header p {
            font-size: 1.2rem;
            opacity: 0.9;
            max-width: 700px;
            margin: 0 auto;
            line-height: 1.6;
        }
        
        .target-date {
            background-color: rgba(255, 255, 255, 0.1);
            padding: 15px;
            border-radius: 12px;
            display: inline-block;
            margin-top: 15px;
            font-size: 1.3rem;
            border: 1px solid rgba(255, 255, 255, 0.2);
        }
        
        .countdown-container {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 25px;
            margin: 50px 0;
        }
        
        .countdown-box {
            background: linear-gradient(145deg, rgba(255, 255, 255, 0.15), rgba(255, 255, 255, 0.05));
            border-radius: 15px;
            padding: 30px 20px;
            min-width: 150px;
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
            border: 1px solid rgba(255, 255, 255, 0.1);
            transition: transform 0.3s ease;
        }
        
        .countdown-box:hover {
            transform: translateY(-5px);
        }
        
        .countdown-value {
            font-size: 3.5rem;
            font-weight: 700;
            display: block;
            text-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
            color: #4fffd2;
        }
        
        .countdown-label {
            font-size: 1.2rem;
            margin-top: 10px;
            opacity: 0.9;
            text-transform: uppercase;
            letter-spacing: 1px;
        }
        
        .motivation {
            margin-top: 40px;
            font-size: 1rem;
            padding: 15px;
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 10px;
            border-top: 1px solid rgba(255, 255, 255, 0.2);
            font-style: normal;
            opacity: 0.8;
        }
        
        .footer {
            margin-top: 40px;
            font-size: 0.9rem;
            opacity: 0.8;
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
        }
        
        .share-btn {
            background-color: rgba(79, 255, 210, 0.2);
            color: white;
            border: 1px solid rgba(79, 255, 210, 0.5);
            padding: 10px 20px;
            border-radius: 50px;
            cursor: pointer;
            font-size: 1rem;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            gap: 8px;
        }
        
        .share-btn:hover {
            background-color: rgba(79, 255, 210, 0.3);
            transform: scale(1.05);
        }
        
        @media (max-width: 768px) {
            .container {
                padding: 30px 20px;
            }
            
            .header h1 {
                font-size: 2.2rem;
            }
            
            .countdown-box {
                min-width: 120px;
                padding: 20px 15px;
            }
            
            .countdown-value {
                font-size: 2.8rem;
            }
            
            .footer {
                flex-direction: column;
                gap: 20px;
                text-align: center;
            }
        }
        
        @media (max-width: 480px) {
            .countdown-container {
                gap: 15px;
            }
            
            .countdown-box {
                min-width: 90px;
                padding: 15px 10px;
            }
            
            .countdown-value {
                font-size: 2.2rem;
            }
            
            .countdown-label {
                font-size: 1rem;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1><i class="fas fa-hourglass-half"></i> 2026年中考倒计时</h1>
            <p>CI工作室祝你学业有成！</p>
            <div class="target-date">
                <i class="far fa-calendar-alt"></i> 目标日期: 2026年6月24日
            </div>
        </div>
        
        <div class="countdown-container">
            <div class="countdown-box">
                <span class="countdown-value" id="days">0</span>
                <span class="countdown-label">天</span>
            </div>
            <div class="countdown-box">
                <span class="countdown-value" id="hours">0</span>
                <span class="countdown-label">小时</span>
            </div>
            <div class="countdown-box">
                <span class="countdown-value" id="minutes">0</span>
                <span class="countdown-label">分钟</span>
            </div>
            <div class="countdown-box">
                <span class="countdown-value" id="seconds">0</span>
                <span class="countdown-label">秒</span>
            </div>
        </div>
        
        <div class="motivation">
            该网页由chromium intelligence提供技术支持
        </div>
        
        <div class="footer">
            <div>
                倒计时最后更新: <span id="last-update">刚刚</span>
            </div>
            <button class="share-btn" id="share-btn">
                <i class="fas fa-share-alt"></i> 分享倒计时
            </button>
        </div>
    </div>

    <script>
        // 设置中考目标日期：2026年6月24日
        const targetDate = new Date('2026-06-24T00:00:00');
        
        // 获取显示元素
        const daysElement = document.getElementById('days');
        const hoursElement = document.getElementById('hours');
        const minutesElement = document.getElementById('minutes');
        const secondsElement = document.getElementById('seconds');
        const lastUpdateElement = document.getElementById('last-update');
        const shareButton = document.getElementById('share-btn');
        
        // 更新倒计时
        function updateCountdown() {
            const now = new Date();
            const timeDifference = targetDate - now;
            
            // 如果已经过了目标日期
            if (timeDifference < 0) {
                daysElement.textContent = '0';
                hoursElement.textContent = '0';
                minutesElement.textContent = '0';
                secondsElement.textContent = '0';
                lastUpdateElement.textContent = '中考已开始';
                return;
            }
            
            // 计算剩余时间
            const days = Math.floor(timeDifference / (1000 * 60 * 60 * 24));
            const hours = Math.floor((timeDifference % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const minutes = Math.floor((timeDifference % (1000 * 60 * 60)) / (1000 * 60));
            const seconds = Math.floor((timeDifference % (1000 * 60)) / 1000);
            
            // 更新显示
            daysElement.textContent = days.toString().padStart(2, '0');
            hoursElement.textContent = hours.toString().padStart(2, '0');
            minutesElement.textContent = minutes.toString().padStart(2, '0');
            secondsElement.textContent = seconds.toString().padStart(2, '0');
            
            // 更新最后更新时间
            const updateTime = new Date().toLocaleTimeString('zh-CN', { 
                hour: '2-digit', 
                minute: '2-digit',
                second: '2-digit'
            });
            lastUpdateElement.textContent = updateTime;
        }
        
        // 初始化倒计时
        updateCountdown();
        
        // 每秒更新一次
        setInterval(updateCountdown, 1000);
        
        // 分享功能
        shareButton.addEventListener('click', function() {
            const shareData = {
                title: '2026年中考倒计时',
                text: '查看距离2026年6月24日中考的实时倒计时，一起为中考加油！',
                url: window.location.href
            };
            
            if (navigator.share) {
                navigator.share(shareData)
                    .then(() => console.log('分享成功'))
                    .catch((error) => console.log('分享失败:', error));
            } else {
                // 如果浏览器不支持Web Share API，则使用复制链接的方式
                navigator.clipboard.writeText(window.location.href)
                    .then(() => {
                        alert('链接已复制到剪贴板！您可以发送给朋友了。');
                    })
                    .catch(err => {
                        console.error('复制失败:', err);
                        prompt('请手动复制以下链接:', window.location.href);
                    });
            }
        });
    </script>
</body>
</html>
# sharpwood.github.io
