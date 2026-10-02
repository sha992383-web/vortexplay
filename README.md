```html
<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>پنل مدیریت فیلترشکل | Cloud Proxy</title>
    <link href="https://cdn.jsdelivr.net/gh/rastikerdar/vazirmatn@v33.003/Vazirmatn-font-face.css" rel="stylesheet" type="text/css" />
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        :root {
            --primary-blue: #2563eb;
            --dark-blue: #1e3a8a;
            --light-blue: #dbeafe;
            --bg-color: #f0f4f8;
            --card-bg: #ffffff;
            --text-main: #1e293b;
            --text-muted: #64748b;
            --success: #10b981;
            --danger: #ef4444;
            --border-radius: 12px;
            --shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Vazirmatn', sans-serif;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-main);
            display: flex;
            min-height: 100vh;
        }

        /* Sidebar */
        .sidebar {
            width: 250px;
            background: linear-gradient(180deg, var(--dark-blue) 0%, var(--primary-blue) 100%);
            color: white;
            padding: 20px;
            display: flex;
            flex-direction: column;
            position: fixed;
            height: 100%;
            right: 0;
            top: 0;
            z-index: 100;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: bold;
            margin-bottom: 40px;
            text-align: center;
            border-bottom: 1px solid rgba(255,255,255,0.2);
            padding-bottom: 20px;
        }

        .menu-item {
            padding: 15px;
            cursor: pointer;
            border-radius: 8px;
            transition: 0.3s;
            display: flex;
            align-items: center;
            gap: 10px;
            margin-bottom: 5px;
        }

        .menu-item:hover, .menu-item.active {
            background-color: rgba(255,255,255,0.2);
        }

        /* Main Content */
        .main-content {
            margin-right: 250px;
            padding: 30px;
            width: 100%;
        }

        .header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 30px;
        }

        .user-profile {
            display: flex;
            align-items: center;
            gap: 10px;
            background: var(--card-bg);
            padding: 10px 20px;
            border-radius: 50px;
            box-shadow: var(--shadow);
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
            gap: 20px;
            margin-bottom: 30px;
        }

        .stat-card {
            background: var(--card-bg);
            padding: 20px;
            border-radius: var(--border-radius);
            box-shadow: var(--shadow);
            border-top: 4px solid var(--primary-blue);
        }

        .stat-title {
            color: var(--text-muted);
            font-size: 0.9rem;
            margin-bottom: 10px;
        }

        .stat-value {
            font-size: 1.8rem;
            font-weight: bold;
            color: var(--dark-blue);
        }

        .actions-bar {
            display: flex;
            justify-content: space-between;
            margin-bottom: 20px;
        }

        .search-box {
            padding: 10px 15px;
            border: 1px solid #cbd5e1;
            border-radius: 8px;
            width: 300px;
            outline: none;
        }

        .btn {
            padding: 10px 20px;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            font-weight: bold;
            display: flex;
            align-items: center;
            gap: 8px;
            transition: 0.3s;
        }

        .btn-primary {
            background-color: var(--primary-blue);
            color: white;
        }

        .btn-primary:hover {
            background-color: var(--dark-blue);
        }

        .btn-danger {
            background-color: var(--danger);
            color: white;
            padding: 5px 10px;
            font-size: 0.8rem;
        }

        .btn-copy {
            background-color: var(--light-blue);
            color: var(--dark-blue);
            padding: 5px 10px;
            font-size: 0.8rem;
        }

        table {
            width: 100%;
            border-collapse: collapse;
            background: var(--card-bg);
            border-radius: var(--border-radius);
            overflow: hidden;
            box-shadow: var(--shadow);
        }

        th, td {
            padding: 15px;
            text-align: right;
            border-bottom: 1px solid #e2e8f0;
        }

        th {
            background-color: var(--light-blue);
            color: var(--dark-blue);
        }

        tr:hover {
            background-color: #f8fafc;
        }

        .status-badge {
            padding: 5px 10px;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: bold;
        }

        .status-active {
            background-color: #d1fae5;
            color: #065f46;
        }

        .status-inactive {
            background-color: #fee2e2;
            color: #991b1b;
        }

        /* Modal */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.5);
            justify-content: center;
            align-items: center;
            z-index: 1000;
        }

        .modal-content {
            background: white;
            padding: 30px;
            border-radius: var(--border-radius);
            width: 400px;
            box-shadow: 0 10px 25px rgba(0,0,0,0.2);
        }

        .form-group {
            margin-bottom: 15px;
        }

        .form-group label {
            display: block;
            margin-bottom: 5px;
            color: var(--text-muted);
        }

        .form-group input, .form-group select {
            width: 100%;
            padding: 10px;
            border: 1px solid #cbd5e1;
            border-radius: 6px;
        }

        .modal-actions {
            display: flex;
            justify-content: flex-end;
            gap: 10px;
            margin-top: 20px;
        }

        @media (max-width: 768px) {
            .sidebar {
                width: 70px;
                padding: 10px;
            }
            .sidebar span, .logo span {
                display: none;
            }
            .main-content {
                margin-right: 70px;
            }
            .menu-item {
                justify-content: center;
            }
        }
    </style>
</head>
<body>

    <!-- Sidebar -->
    <div class="sidebar">
        <div class="logo">
            <i class="fas fa-cloud"></i> <span>کلود پروکسی</span>
        </div>
        <div class="menu-item active">
            <i class="fas fa-users"></i> <span>کاربران</span>
        </div>
        <div class="menu-item">
            <i class="fas fa-chart-line"></i> <span>آمار و گزارش</span>
        </div>
        <div class="menu-item">
            <i class="fas fa-cog"></i> <span>تنظیمات</span>
        </div>
    </div>

    <!-- Main Content -->
    <div class="main-content">
        <div class="header">
            <h2>مدیریت کاربران و کانفیگ‌ها</h2>
            <div class="user-profile">
                                <i class="fas fa-user-circle"></i>
                <span>ادمین</span>
            </div>
        </div>

        <!-- Stats -->
        <div class="stats-grid">
            <div class="stat-card">
                <div class="stat-title">کل کاربران</div>
                <div class="stat-value" id="total-users">124</div>
            </div>
            <div class="stat-card">
                <div class="stat-title">فعال امروز</div>
                <div class="stat-value" style="color: var(--success)">89</div>
            </div>
            <div class="stat-card">
                <div class="stat-title">ترافیک مصرفی</div>
                <div class="stat-value">45.2 GB</div>
            </div>
        </div>

        <!-- Actions -->
        <div class="actions-bar">
            <input type="text" class="search-box" placeholder="جستجوی نام یا ایمیل..." onkeyup="filterTable(this.value)">
            <button class="btn btn-primary" onclick="openModal()">
                <i class="fas fa-plus"></i> افزودن کاربر جدید
            </button>
        </div>

        <!-- Table -->
        <table>
            <thead>
                <tr>
                    <th>نام کاربر</th>
                    <th>ایمیل</th>
                    <th>وضعیت</th>
                    <th>سرور</th>
                    <th>تاریخ عضویت</th>
                    <th>عملیات</th>
                </tr>
            </thead>
            <tbody id="users-table-body">
                <!-- Rows will be populated by JS -->
            </tbody>
        </table>
    </div>

    <!-- Add User Modal -->
    <div class="modal" id="userModal">
        <div class="modal-content">
            <h3>افزودن کاربر جدید</h3>
            <form id="addUserForm">
                <div class="form-group">
                    <label>نام کاربری</label>
                    <input type="text" id="username" required>
                </div>
                <div class="form-group">
                    <label>ایمیل</label>
                    <input type="email" id="email" required>
                </div>
                <div class="form-group">
                    <label>سرور مقصد</label>
                    <select id="server">
                        <option value="us">آمریکا 🇺🇸</option>
                        <option value="de">آلمان 🇩🇪</option>
                        <option value="nl">هلند 🇳🇱</option>
                    </select>
                </div>
                <div class="modal-actions">
                    <button type="button" class="btn" style="background:#eee;" onclick="closeModal()">انصراف</button>
                    <button type="submit" class="btn btn-primary">ذخیره</button>
                </div>
            </form>
        </div>
    </div>

    <script>
        // Mock Data
        let users = [
            { id: 1, name: 'علی رضایی', email: 'ali@example.com', status: 'active', server: 'آمریکا', date: '1402/08/10' },
            { id: 2, name: 'سارا محمدی', email: 'sara@example.com', status: 'inactive', server: 'آلمان', date: '1402/08/12' },
            { id: 3, name: 'رضا کریمی', email: 'reza@example.com', status: 'active', server: 'هلند', date: '1402/08/15' },
        ];

        const tbody = document.getElementById('users-table-body');
        const modal = document.getElementById('userModal');
        const form = document.getElementById('addUserForm');
        const totalUsersEl = document.getElementById('total-users');

        // Render Table
        function renderTable(data = users) {
            tbody.innerHTML = '';
            data.forEach(user => {
                const tr = document.createElement('tr');
                const statusClass = user.status === 'active' ? 'status-active' : 'status-inactive';
                const statusText = user.status === 'active' ? 'فعال' : 'غیرفعال';
                
                tr.innerHTML = `
                    <td>${user.name}</td>
                    <td>${user.email}</td>
                    <td><span class="status-badge ${statusClass}">${statusText}</span></td>
                    <td>${user.server}</td>
                    <td>${user.date}</td>
                    <td>
                        <button class="btn btn-copy" onclick="copyConfig('${user.id}')"><i class="fas fa-copy"></i></button>
                        <button class="btn btn-danger" onclick="deleteUser(${user.id})"><i class="fas fa-trash"></i></button>
                    </td>
                `;
                tbody.appendChild(tr);
            });
            updateStats();
        }

        // Update Stats
        function updateStats() {
            totalUsersEl.innerText = users.length;
        }

        // Copy Config Simulation
        function copyConfig(id) {
            const user = users.find(u => u.id == id);
            const configLink = `https://your-domain.workers.dev/?url=https://google.com&user=${user.email}&key=${Math.random().toString(36).substring(7)}`;
            navigator.clipboard.writeText(configLink);
            alert('لینک کانفیگ کپی شد:\n' + configLink);
        }

        // Delete User
        function deleteUser(id) {
            if(confirm('آیا مطمئن هستید؟')) {
                users = users.filter(u => u.id !== id);
                renderTable();
            }
        }

        // Filter Table
        function filterTable(query) {
            const filtered = users.filter(u => 
                u.name.includes(query) || u.email.includes(query)
            );
            renderTable(filtered);
        }

        // Modal Functions
        function openModal() {
            modal.style.display = 'flex';
        }

        function closeModal() {
            modal.style.display = 'none';
        }

        // Add User Logic
        form.addEventListener('submit', (e) => {
            e.preventDefault();
            const name = document.getElementById('username').value;
            const email = document.getElementById('email').value;
            const serverSelect = document.getElementById('server');
            const server = serverSelect.options[serverSelect.selectedIndex].text;
            
            const newUser = {
                id: Date.now(),
                name: name,
                email: email,
                status: 'active',
                server: server.split(' ')[0], // Just keep the country name part roughly
                date: new Date().toLocaleDateString('fa-IR')
            };

            users.unshift(newUser);
            renderTable();
            closeModal();
            form.reset();
        });

        // Close modal when clicking outside
        window.onclick = function(event) {
            if (event.target == modal) {
                closeModal();
            }
        }

        // Initial Render
        renderTable();
    </script>
</body>
</html>
```
