<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>وب‌سایت من</title>
  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }
    body {
      font-family: Tahoma, sans-serif;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      background-size: cover;
      background-position: center;
      transition: background-image 0.5s ease-in-out;
      color: #fff;
    }
    .container {
      background: rgba(0, 0, 0, 0.7);
      padding: 30px;
      border-radius: 15px;
      text-align: center;
      box-shadow: 0 8px 32px rgba(0,0,0,0.5);
      max-width: 400px;
      width: 90%;
    }
    h1 {
      margin-bottom: 15px;
      font-size: 24px;
    }
    p {
      margin-bottom: 20px;
      color: #ddd;
    }
    .admin-btn {
      background: #007bff;
      color: white;
      border: none;
      padding: 10px 15px;
      border-radius: 5px;
      cursor: pointer;
      font-size: 14px;
    }
    .modal {
      display: none;
      position: fixed;
      top: 0; left: 0; width: 100%; height: 100%;
      background: rgba(0,0,0,0.8);
      justify-content: center;
      align-items: center;
    }
    .modal-content {
      background: #222;
      padding: 25px;
      border-radius: 10px;
      width: 90%;
      max-width: 350px;
      text-align: right;
    }
    input {
      width: 100%;
      padding: 10px;
      margin: 10px 0;
      border-radius: 5px;
      border: 1px solid #444;
      background: #333;
      color: white;
    }
    .save-btn {
      width: 100%;
      background: #28a745;
      color: white;
      border: none;
      padding: 10px;
      border-radius: 5px;
      cursor: pointer;
    }
    .close-btn {
      background: #dc3545;
      margin-top: 5px;
    }
  </style>
</head>
<body>

  <div class="container">
    <h1>به وب‌سایت من خوش آمدید</h1>
    <p>این یک سایت میزبانی شده روی GitHub Pages است.</p>
    <button class="admin-btn" onclick="openAdmin()">ورود به پنل مدیریت</button>
  </div>

  <!-- لوحة التحكم -->
  <div class="modal" id="adminModal">
    <div class="modal-content">
      <h3>پنل تغییر پس‌زمینه</h3>
      <input type="password" id="tokenInput" placeholder="رمز عبور را وارد کنید">
      <input type="text" id="bgUrlInput" placeholder="لینک مستقیم عکس (https://...)">
      <button class="save-btn" onclick="saveBackground()">ذخیره پس‌زمینه</button>
      <button class="save-btn close-btn" onclick="closeAdmin()">بستن</button>
    </div>
  </div>

  <script>
    // كلمة المرور الجديدة
    const SECRET_TOKEN = "1234";

    window.onload = function() {
      const savedBg = localStorage.getItem('custom_bg');
      if (savedBg) {
        document.body.style.backgroundImage = `url('${savedBg}')`;
      } else {
        document.body.style.backgroundImage = "url('https://picsum.photos/1920/1080')";
      }
    };

    function openAdmin() {
      document.getElementById('adminModal').style.display = 'flex';
    }

    function closeAdmin() {
      document.getElementById('adminModal').style.display = 'none';
    }

    function saveBackground() {
      const token = document.getElementById('tokenInput').value;
      const bgUrl = document.getElementById('bgUrlInput').value;

      if (token !== SECRET_TOKEN) {
        alert("رمز عبور اشتباه است!");
        return;
      }

      if (!bgUrl) {
        alert("لطفاً لینک عکس را وارد کنید.");
        return;
      }

      localStorage.setItem('custom_bg', bgUrl);
      document.body.style.backgroundImage = `url('${bgUrl}')`;
      alert("پس‌زمینه با موفقیت تغییر کرد!");
      closeAdmin();
    }
  </script>

</body>
</html>
