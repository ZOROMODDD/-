<!DOCTYPE html><html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8">
  <title>إنشاء سيرفر ماينكرافت بيدروك</title>
  <style>
    body { font-family: Arial; background-color: #f0f0f0; text-align: center; padding: 30px; }
    .container { background: white; padding: 20px; border-radius: 10px; display: inline-block; }
    select, button { padding: 10px; margin: 10px; font-size: 16px; }
    #timer { font-size: 20px; color: red; margin-top: 20px; }
    pre { text-align: left; background: #eee; padding: 10px; direction: ltr; overflow-x: auto; }
  </style>
</head>
<body>
  <div class="container">
    <h1>مُنشئ سيرفرات ماينكرافت بيدروك</h1>
    <label for="version">اختر الإصدار:</label>
    <select id="version">
      <option value="1.20.81">1.20.81</option>
      <option value="1.20.50">1.20.50</option>
      <option value="1.20.40">1.20.40</option>
    </select>
    <br>
    <button onclick="startServer()">إنشاء السيرفر</button>
    <div id="output"></div>
    <div id="timer"></div>
  </div>  <script>
    function startServer() {
      const version = document.getElementById('version').value;
      const output = document.getElementById('output');
      const timer = document.getElementById('timer');

      // مثال على أوامر تشغيل السيرفر يدويًا
      output.innerHTML = `<h3>خطوات التشغيل:</h3>
        <pre>
1. قم بتحميل السيرفر من:
https://minecraft.net/en-us/download/server/bedrock

2. فك الضغط في مجلد جديد
3. ضع المودات (إن وجدت) داخل مجلد behavior_packs
4. شغّل الملف: bedrock_server.exe
        </pre>`;// بدء المؤقت
  let timeLeft = 600; // 10 دقائق
  const interval = setInterval(() => {
    if (timeLeft <= 0) {
      clearInterval(interval);
      timer.innerText = 'انتهى وقت السيرفر. يُفضل إغلاقه الآن.';
    } else {
      const minutes = Math.floor(timeLeft / 60);
      const seconds = timeLeft % 60;
      timer.innerText = `الوقت المتبقي: ${minutes}:${seconds < 10 ? '0' : ''}${seconds}`;
      timeLeft--;
    }
  }, 1000);
}

  </script>
</body>
</html>
