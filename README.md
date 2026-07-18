<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portal Login - E-Kesiswaan</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Font Awesome -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Google Fonts: Inter -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                    },
                    colors: {
                        primary: '#4f46e5', // Indigo 600
                    }
                }
            }
        }
    </script>
    <style>
        body {
            /* Animated gradient background */
            background: linear-gradient(-45deg, #4f46e5, #3b82f6, #1e293b, #0f172a);
            background-size: 400% 400%;
            animation: gradientBG 15s ease infinite;
        }

        @keyframes gradientBG {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        /* Input field autofill styling fix for Tailwind */
        input:-webkit-autofill,
        input:-webkit-autofill:hover, 
        input:-webkit-autofill:focus, 
        input:-webkit-autofill:active{
            -webkit-box-shadow: 0 0 0 30px white inset !important;
            -webkit-text-fill-color: #1e293b !important;
        }
    </style>
</head>
<body class="min-h-screen flex items-center justify-center p-4 font-sans antialiased">

    <div class="bg-white rounded-3xl shadow-2xl w-full max-w-md overflow-hidden transform transition-all duration-500 hover:shadow-indigo-500/20">
        
        <!-- Header Section -->
        <div class="bg-slate-50 pt-8 pb-6 px-8 text-center border-b border-slate-100">
            <div class="mx-auto flex items-center justify-center w-16 h-16 bg-indigo-600 text-white rounded-2xl shadow-lg mb-4 transform rotate-3">
                <i class="fas fa-graduation-cap text-3xl -rotate-3"></i>
            </div>
            <h1 class="text-2xl font-bold text-slate-800 tracking-tight">Portal E-Kesiswaan</h1>
            <p class="text-slate-500 text-sm mt-2">Selamat datang! Silakan masuk ke akun Anda.</p>
        </div>

        <div class="flex border-b border-slate-200">
            <button id="tab-admin" onclick="switchTab('admin')" class="flex-1 py-4 text-sm font-semibold text-indigo-600 border-b-2 border-indigo-600 transition-colors bg-white hover:bg-slate-50 focus:outline-none">
                <i class="fas fa-user-shield mr-2"></i>Admin / Guru
            </button>
            <button id="tab-siswa" onclick="switchTab('siswa')" class="flex-1 py-4 text-sm font-semibold text-slate-400 border-b-2 border-transparent hover:text-slate-600 transition-colors bg-white hover:bg-slate-50 focus:outline-none">
                <i class="fas fa-user-graduate mr-2"></i>Siswa
            </button>
        </div>

        <div class="p-8">
            <form id="loginForm" onsubmit="handleLogin(event)" class="space-y-5">
                
                <!-- Username Input -->
                <div>
                    <label id="label-username" for="username" class="block text-sm font-medium text-slate-700 mb-1">Username Admin</label>
                    <div class="relative">
                        <div class="absolute inset-y-0 left-0 pl-3 flex items-center pointer-events-none">
                            <i id="icon-username" class="fas fa-user text-slate-400"></i>
                        </div>
                        <input type="text" id="username" name="username" required autocomplete="off"
                            class="block w-full pl-10 pr-3 py-2.5 border border-slate-300 rounded-xl text-slate-900 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm transition-shadow" 
                            placeholder="Masukkan username...">
                    </div>
                </div>

                <!-- Password Input -->
                <div>
                    <label for="password" class="block text-sm font-medium text-slate-700 mb-1">Password</label>
                    <div class="relative">
                        <div class="absolute inset-y-0 left-0 pl-3 flex items-center pointer-events-none">
                            <i class="fas fa-lock text-slate-400"></i>
                        </div>
                        <input type="password" id="password" name="password" required 
                            class="block w-full pl-10 pr-10 py-2.5 border border-slate-300 rounded-xl text-slate-900 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm transition-shadow" 
                            placeholder="Masukkan password...">
                        <!-- Toggle Password Visibility -->
                        <div class="absolute inset-y-0 right-0 pr-3 flex items-center cursor-pointer" onclick="togglePassword()">
                            <i id="eye-icon" class="fas fa-eye text-slate-400 hover:text-indigo-500 transition-colors"></i>
                        </div>
                    </div>
                </div>

                <div class="flex items-center justify-between mt-2">
                    <div class="flex items-center">
                        <input id="remember-me" name="remember-me" type="checkbox" class="h-4 w-4 text-indigo-600 focus:ring-indigo-500 border-slate-300 rounded cursor-pointer">
                        <label for="remember-me" class="ml-2 block text-sm text-slate-600 cursor-pointer">
                            Ingat saya
                        </label>
                    </div>
                    <div class="text-sm">
                        <a href="#" class="font-medium text-indigo-600 hover:text-indigo-500 transition-colors">
                            Lupa password?
                        </a>
                    </div>
                </div>

                <!-- Submit Button -->
                <div class="pt-2">
                    <button type="submit" class="group relative w-full flex justify-center py-2.5 px-4 border border-transparent text-sm font-semibold rounded-xl text-white bg-indigo-600 hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500 transition-all shadow-md hover:shadow-lg">
                        <span class="absolute left-0 inset-y-0 flex items-center pl-3">
                            <i class="fas fa-sign-in-alt text-indigo-500 group-hover:text-indigo-400 transition-colors"></i>
                        </span>
                        Masuk ke Dashboard
                    </button>
                </div>
            </form>

            <!-- Hint for Demo -->
            <div class="mt-6 p-3 bg-blue-50 border border-blue-100 rounded-lg text-xs text-blue-700 text-center">
                <p><strong>Demo Mode Admin:</strong></p>
                <p>Username: <span class="font-mono bg-white px-1 py-0.5 rounded border border-blue-200">admin</span> | Pass: <span class="font-mono bg-white px-1 py-0.5 rounded border border-blue-200">adminsiswa</span></p>
            </div>
        </div>
        
        <!-- Footer -->
        <div class="bg-slate-50 py-4 text-center border-t border-slate-100">
            <p class="text-xs text-slate-500">&copy; 2026 E-Kesiswaan Sekolah. All rights reserved.</p>
        </div>
    </div>

    <div id="custom-modal" class="fixed inset-0 z-50 hidden flex items-center justify-center px-4">
        <div class="fixed inset-0 bg-slate-900/60 backdrop-blur-sm transition-opacity" onclick="closeModal()"></div>
        <div class="bg-white rounded-2xl shadow-2xl p-6 z-10 w-full max-w-sm transform transition-all scale-95 opacity-0" id="modal-box">
            <div class="text-center">
                <div id="modal-icon-container" class="mx-auto flex items-center justify-center h-14 w-14 rounded-full bg-red-100 text-red-600 mb-4">
                    <i id="modal-icon" class="fas fa-times-circle text-2xl"></i>
                </div>
                <h3 class="text-lg font-bold text-slate-900 mb-2" id="modal-title">Judul</h3>
                <p class="text-sm text-slate-500 mb-6" id="modal-message">Pesan disini.</p>
                <button onclick="closeModal()" id="modal-btn" class="w-full inline-flex justify-center rounded-xl border border-transparent shadow-sm px-4 py-2 bg-red-600 text-base font-medium text-white hover:bg-red-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-red-500 sm:text-sm transition-colors">
                    Coba Lagi
                </button>
            </div>
        </div>
    </div>

    <script>
        let currentRole = 'admin'; // Default role

        function switchTab(role) {
            currentRole = role;
            const tabAdmin = document.getElementById('tab-admin');
            const tabSiswa = document.getElementById('tab-siswa');
            const labelUsername = document.getElementById('label-username');
            const inputUsername = document.getElementById('username');
            const iconUsername = document.getElementById('icon-username');

            // Reset Tabs styling
            tabAdmin.className = "flex-1 py-4 text-sm font-semibold text-slate-400 border-b-2 border-transparent hover:text-slate-600 transition-colors bg-white hover:bg-slate-50 focus:outline-none";
            tabSiswa.className = "flex-1 py-4 text-sm font-semibold text-slate-400 border-b-2 border-transparent hover:text-slate-600 transition-colors bg-white hover:bg-slate-50 focus:outline-none";

            // Apply Active styling based on role
            if (role === 'admin') {
                tabAdmin.className = "flex-1 py-4 text-sm font-semibold text-indigo-600 border-b-2 border-indigo-600 transition-colors bg-white hover:bg-slate-50 focus:outline-none";
                labelUsername.innerText = "Username Admin";
                inputUsername.placeholder = "Masukkan username...";
                iconUsername.className = "fas fa-user-shield text-slate-400";
                inputUsername.value = ""; // clear input
                document.getElementById('password').value = "";
            } else {
                tabSiswa.className = "flex-1 py-4 text-sm font-semibold text-indigo-600 border-b-2 border-indigo-600 transition-colors bg-white hover:bg-slate-50 focus:outline-none";
                labelUsername.innerText = "NIS (Nomor Induk Siswa)";
                inputUsername.placeholder = "Masukkan NIS Anda...";
                iconUsername.className = "fas fa-id-card text-slate-400";
                inputUsername.value = ""; // clear input
                document.getElementById('password').value = "";
            }
        }

        function togglePassword() {
            const passInput = document.getElementById('password');
            const eyeIcon = document.getElementById('eye-icon');
            if (passInput.type === 'password') {
                passInput.type = 'text';
                eyeIcon.classList.remove('fa-eye');
                eyeIcon.classList.add('fa-eye-slash');
            } else {
                passInput.type = 'password';
                eyeIcon.classList.remove('fa-eye-slash');
                eyeIcon.classList.add('fa-eye');
            }
        }

        // Custom Modal Logic
        const modal = document.getElementById('custom-modal');
        const modalBox = document.getElementById('modal-box');

        function showModal(title, message, type) {
            document.getElementById('modal-title').innerText = title;
            document.getElementById('modal-message').innerText = message;
            
            const iconContainer = document.getElementById('modal-icon-container');
            const icon = document.getElementById('modal-icon');
            const btn = document.getElementById('modal-btn');

            if (type === 'success') {
                iconContainer.className = "mx-auto flex items-center justify-center h-14 w-14 rounded-full bg-emerald-100 text-emerald-600 mb-4";
                icon.className = "fas fa-check-circle text-2xl";
                btn.className = "w-full inline-flex justify-center rounded-xl border border-transparent shadow-sm px-4 py-2 bg-emerald-600 text-base font-medium text-white hover:bg-emerald-700 focus:outline-none sm:text-sm transition-colors";
                btn.innerText = "Lanjutkan ke Dashboard";
            } else {
                iconContainer.className = "mx-auto flex items-center justify-center h-14 w-14 rounded-full bg-red-100 text-red-600 mb-4";
                icon.className = "fas fa-exclamation-triangle text-2xl";
                btn.className = "w-full inline-flex justify-center rounded-xl border border-transparent shadow-sm px-4 py-2 bg-red-600 text-base font-medium text-white hover:bg-red-700 focus:outline-none sm:text-sm transition-colors";
                btn.innerText = "Coba Lagi";
            }

            modal.classList.remove('hidden');
            setTimeout(() => {
                modalBox.classList.remove('scale-95', 'opacity-0');
                modalBox.classList.add('scale-100', 'opacity-100');
            }, 10);
        }

        function closeModal() {
            modalBox.classList.remove('scale-100', 'opacity-100');
            modalBox.classList.add('scale-95', 'opacity-0');
            setTimeout(() => {
                modal.classList.add('hidden');
            }, 200);
        }

        function handleLogin(e) {
            e.preventDefault(); // Mencegah reload halaman
            const user = document.getElementById('username').value;
            const pass = document.getElementById('password').value;

            if (currentRole === 'admin') {
                // Validasi data yang diminta
                if (user === 'admin' && pass === 'adminsiswa') {
                    showModal('Login Berhasil!', 'Selamat datang Admin. Di aplikasi PHP asli, Anda akan diarahkan ke Dashboard.', 'success');
                    // Simulasi redirect (opsional) jika ada index.html
                    // setTimeout(() => { window.location.href = 'index.html'; }, 2000);
                } else {
                    showModal('Akses Ditolak', 'Username atau password admin yang Anda masukkan salah.', 'error');
                }
            } else {
                // Simulasi login untuk siswa
                if(user.length > 0 && pass.length > 0) {
                     showModal('Login Siswa Berhasil!', `Selamat datang siswa dengan NIS ${user}.`, 'success');
                } else {
                     showModal('Form Tidak Lengkap', 'Harap isi NIS dan Password Anda.', 'error');
                }
            }
        }
    </script>
</body>
</html>
