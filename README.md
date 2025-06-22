# D92W.github.io<!DOCTYPE html><html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>موقع المنصوري لتعليم بايثون</title>
  <style>
    body {
      margin: 0;
      font-family: 'Tahoma', sans-serif;
      background-color: #000;
      color: #0f0;
    }
    .login-page, .main-page {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      height: 100vh;
    }
    input {
      padding: 10px;
      margin: 10px;
      border-radius: 8px;
      border: none;
      font-size: 16px;
      background-color: #111;
      color: #0f0;
    }
    button {
      padding: 10px 20px;
      background-color: #900;
      color: white;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      font-size: 16px;
    }
    .hidden { display: none; }
    .content {
      padding: 30px;
      background: #111;
      border-radius: 16px;
      max-width: 900px;
      margin: auto;
      box-shadow: 0 0 30px red;
    }
    h1, h2 { color: #f00; }
    .footer {
      margin-top: 30px;
      font-size: 14px;
      color: #888;
      text-align: center;
    }
    a { color: #0f0; text-decoration: none; }
    .video-box, .lesson-img {
      margin: 20px 0;
      border: 2px solid #0f0;
      border-radius: 12px;
      padding: 10px;
      background: #000;
    }
    .dashboard {
      background: #111;
      padding: 20px;
      margin-top: 30px;
      border: 2px dashed #0f0;
      border-radius: 12px;
    }
  </style>
</head>
<body>
  <div class="login-page" id="login-page">
    <h1>تسجيل دخول</h1>
    <input type="text" id="username" placeholder="أي اسم مستخدم">
    <input type="password" id="password" placeholder="أي كلمة سر">
    <button onclick="login()">دخول</button>
  </div>  <div class="main-page hidden" id="main-page">
    <div class="content">
      <h1>🌟 كورس بايثون الكامل مع المنصوري</h1>
      <p>تعلم لغة البرمجة بايثون خطوة بخطوة مع فيديوهات وصور ودروس.</p><h2>📹 فيديو تعليمي:</h2>
  <div class="video-box">
    <video controls width="100%">
      <source src="video1.mp4" type="video/mp4">
      متصفحك لا يدعم تشغيل الفيديو.
    </video>
  </div>

  <h2>📘 درس 1: طباعة نص</h2>
  <pre style="background:#000; padding: 10px; color: #0f0; border-radius: 8px;">print("مرحبا بك في عالم بايثون")</pre>

  <h2>📷 صورة توضيحية:</h2>
  <div class="lesson-img">
    <img src="python_intro.png" alt="مقدمة بايثون" style="width:100%; border-radius: 8px;">
  </div>

  <h2>📬 تواصل مع المالك</h2>
  <p>للحصول على التعليمات أو التحدث مع الأدمن، راسل <a href="https://t.me/D9_2W">@D9_2W</a> عبر تيليجرام</p>

  <div class="dashboard">
    <h3>🛠️ لوحة تحكم الأدمن</h3>
    <ul>
      <li>➕ إضافة دروس جديدة</li>
      <li>📤 رفع فيديوهات</li>
      <li>🖼️ رفع صور تعليمية</li>
      <li>📬 مراجعة الرسائل القادمة من الزوار</li>
    </ul>
    <p>⚠️ فقط الأدمن لديه حق الدخول الكامل إلى إدارة المحتوى.</p>
  </div>

  <div class="footer">
    🔒 الموقع بإدارة <strong>الــمـنصوري DF</strong> <br>
    تيليجرام: <a href="https://t.me/D9_2W">@D9_2W</a> | جميع الحقوق محفوظة
  </div>
</div>

  </div>  <script>
    function login() {
      document.getElementById("login-page").classList.add("hidden");
      document.getElementById("main-page").classList.remove("hidden");
    }
  </script></body>
</html>![Screenshot_٢٠٢٥-٠٦-٢١-٢٢-١٥-٥٦-٣٣٥_com termux](https://github.com/user-attachments/assets/3ddc9ff9-5aea-4da9-99d2-ca1efce901f6)
