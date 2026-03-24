<?php
// login.php - Sistema de autenticación para ST. Fiacre Hospital
session_start();

// Configuración de credenciales (en producción esto iría en base de datos)
$valid_credentials = [
    'dr.martinez' => ['password' => 'medico2024', 'name' => 'Dr. Martínez', 'role' => 'Médico de Emergencias', 'badge' => 'SAMS-001'],
    'dra.lopez' => ['password' => 'lopez2024', 'name' => 'Dra. López', 'role' => 'Jefa de Traumatología', 'badge' => 'SAMS-002'],
    'enfermera.garcia' => ['password' => 'garcia2024', 'name' => 'Enf. García', 'role' => 'Enfermera Jefe', 'badge' => 'SAMS-003'],
    'paramedico.rodriguez' => ['password' => 'rodriguez2024', 'name' => 'Paramédico Rodríguez', 'role' => 'Paramédico Senior', 'badge' => 'SAMS-004'],
    'admin.sams' => ['password' => 'admin2024', 'name' => 'Administrador', 'role' => 'Administrador del Sistema', 'badge' => 'SAMS-ADMIN']
];

$error = '';
$success = '';

// Procesar login
if ($_SERVER['REQUEST_METHOD'] === 'POST') {
    $username = trim($_POST['username'] ?? '');
    $password = trim($_POST['password'] ?? '');
    $remember = isset($_POST['remember']);
    
    if (empty($username) || empty($password)) {
        $error = 'Por favor, complete todos los campos.';
    } elseif (isset($valid_credentials[$username]) && $valid_credentials[$username]['password'] === $password) {
        // Login exitoso
        $_SESSION['sams_user'] = [
            'username' => $username,
            'name' => $valid_credentials[$username]['name'],
            'role' => $valid_credentials[$username]['role'],
            'badge' => $valid_credentials[$username]['badge'],
            'login_time' => time()
        ];
        
        // Guardar cookie si "recordar" está activado
        if ($remember) {
            setcookie('sams_remember', $username, time() + (86400 * 7), '/'); // 7 días
        }
        
        $success = 'Acceso autorizado. Redirigiendo al sistema...';
        header('refresh:2;url=dashboard.php');
    } else {
        $error = 'Credenciales incorrectas. Por favor, verifique sus datos.';
        // Registrar intento fallido (log)
        error_log("Intento de acceso fallido para usuario: $username - " . date('Y-m-d H:i:s'));
    }
}

// Verificar si hay cookie de recordar
if (isset($_COOKIE['sams_remember']) && !isset($_SESSION['sams_user'])) {
    $remembered_user = $_COOKIE['sams_remember'];
    if (isset($valid_credentials[$remembered_user])) {
        $_SESSION['sams_user'] = [
            'username' => $remembered_user,
            'name' => $valid_credentials[$remembered_user]['name'],
            'role' => $valid_credentials[$remembered_user]['role'],
            'badge' => $valid_credentials[$remembered_user]['badge'],
            'login_time' => time()
        ];
        header('Location: dashboard.php');
        exit;
    }
}
?>
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <title>ST. Fiacre Hospital | Acceso al Sistema Médico</title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Sistema de gestión médica del ST. Fiacre Hospital - Acceso exclusivo para personal autorizado.">

    <!-- Fuentes modernas -->
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&family=Montserrat:wght@300;400;500;600&display=swap" rel="stylesheet">
    
    <!-- Iconos -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        /* Variables CSS - Misma paleta que el index */
        :root {
            --primary: #2D9CDB;
            --secondary: #27AE60;
            --accent: #EB5757;
            --light: #F8F9FA;
            --light-blue: #E3F2FD;
            --light-green: #E8F5E9;
            --dark: #2C3E50;
            --gray: #95A5A6;
            --border-radius: 16px;
            --shadow: 0 8px 30px rgba(0, 0, 0, 0.08);
            --shadow-hover: 0 15px 40px rgba(0, 0, 0, 0.12);
            --transition: all 0.3s cubic-bezier(0.25, 0.8, 0.25, 1);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Montserrat', sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            overflow-x: hidden;
        }

        /* Fondo animado con partículas médicas */
        body::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-image: url("data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M30 10 L33 18 L42 18 L35 24 L38 32 L30 26 L22 32 L25 24 L18 18 L27 18 L30 10Z' fill='rgba(255,255,255,0.05)'/%3E%3C/svg%3E");
            background-size: 30px 30px;
            animation: floatBackground 60s linear infinite;
            pointer-events: none;
        }

        @keyframes floatBackground {
            0% { background-position: 0 0; }
            100% { background-position: 100% 100%; }
        }

        /* Contenedor principal del login */
        .login-wrapper {
            width: 100%;
            max-width: 1200px;
            margin: 20px;
            position: relative;
            z-index: 2;
            animation: fadeInUp 0.8s ease-out;
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Contenedor del login con efecto glassmorphism */
        .login-container {
            display: flex;
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            border-radius: var(--border-radius);
            overflow: hidden;
            box-shadow: var(--shadow-hover);
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        /* Lado izquierdo - Información del hospital */
        .login-info {
            flex: 1.2;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            padding: 50px 40px;
            position: relative;
            overflow: hidden;
            color: white;
        }

        .login-info::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,255,255,0.1) 1px, transparent 1px);
            background-size: 30px 30px;
            animation: moveGrid 30s linear infinite;
            pointer-events: none;
        }

        @keyframes moveGrid {
            0% { transform: translate(0, 0); }
            100% { transform: translate(50px, 50px); }
        }

        .hospital-badge {
            position: relative;
            z-index: 1;
            text-align: center;
            margin-bottom: 40px;
        }

        .badge-icon {
            width: 100px;
            height: 100px;
            background: rgba(255, 255, 255, 0.2);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 20px;
            border: 2px solid rgba(255, 255, 255, 0.3);
            animation: pulseGlow 2s infinite;
        }

        @keyframes pulseGlow {
            0%, 100% { box-shadow: 0 0 20px rgba(255, 255, 255, 0.3); }
            50% { box-shadow: 0 0 40px rgba(255, 255, 255, 0.6); }
        }

        .badge-icon i {
            font-size: 50px;
            color: white;
        }

        .hospital-badge h1 {
            font-size: 2rem;
            font-weight: 700;
            margin-bottom: 10px;
        }

        .hospital-badge p {
            font-size: 0.9rem;
            opacity: 0.9;
        }

        .info-stats {
            position: relative;
            z-index: 1;
            margin-top: 40px;
        }

        .stat-row {
            display: flex;
            justify-content: space-between;
            margin-bottom: 20px;
            padding: 15px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: var(--border-radius);
            backdrop-filter: blur(5px);
        }

        .stat-label {
            font-size: 0.85rem;
            font-weight: 500;
        }

        .stat-value {
            font-size: 0.85rem;
            font-weight: 700;
        }

        .emergency-badge {
            margin-top: 40px;
            padding: 20px;
            background: rgba(235, 87, 87, 0.2);
            border-radius: var(--border-radius);
            text-align: center;
            border: 1px solid rgba(235, 87, 87, 0.5);
        }

        .emergency-badge .number {
            font-size: 2rem;
            font-weight: 800;
            letter-spacing: 2px;
        }

        .emergency-badge .label {
            font-size: 0.8rem;
            opacity: 0.9;
            margin-top: 5px;
        }

        /* Lado derecho - Formulario */
        .login-form-container {
            flex: 1;
            padding: 50px 45px;
            background: white;
        }

        .form-header {
            text-align: center;
            margin-bottom: 35px;
        }

        .form-header h2 {
            color: var(--dark);
            font-size: 1.8rem;
            font-weight: 700;
            margin-bottom: 10px;
        }

        .form-header h2 i {
            color: var(--primary);
            margin-right: 10px;
        }

        .form-header p {
            color: var(--gray);
            font-size: 0.9rem;
        }

        /* Alertas */
        .alert-message {
            padding: 12px 15px;
            border-radius: var(--border-radius);
            margin-bottom: 25px;
            display: flex;
            align-items: center;
            gap: 12px;
            font-size: 0.85rem;
            animation: slideIn 0.3s ease;
        }

        .alert-error {
            background: rgba(235, 87, 87, 0.1);
            border-left: 3px solid var(--accent);
            color: #c0392b;
        }

        .alert-success {
            background: rgba(39, 174, 96, 0.1);
            border-left: 3px solid var(--secondary);
            color: #27AE60;
        }

        @keyframes slideIn {
            from {
                opacity: 0;
                transform: translateX(-20px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        /* Input groups */
        .input-group {
            margin-bottom: 25px;
        }

        .input-group label {
            display: block;
            color: var(--dark);
            font-size: 0.85rem;
            font-weight: 500;
            margin-bottom: 8px;
        }

        .input-group label i {
            margin-right: 8px;
            color: var(--primary);
        }

        .input-wrapper {
            position: relative;
            display: flex;
            align-items: center;
        }

        .input-wrapper i.input-icon {
            position: absolute;
            left: 15px;
            color: var(--primary);
            font-size: 1rem;
            z-index: 1;
        }

        .input-wrapper input {
            width: 100%;
            padding: 14px 15px 14px 45px;
            background: var(--light);
            border: 2px solid #e0e0e0;
            border-radius: 12px;
            color: var(--dark);
            font-size: 0.95rem;
            transition: var(--transition);
            font-family: 'Montserrat', sans-serif;
        }

        .input-wrapper input:focus {
            outline: none;
            border-color: var(--primary);
            background: white;
            box-shadow: 0 0 0 3px rgba(45, 156, 219, 0.1);
        }

        .input-wrapper input::placeholder {
            color: var(--gray);
            opacity: 0.6;
        }

        .toggle-password {
            position: absolute;
            right: 15px;
            background: none;
            border: none;
            color: var(--gray);
            cursor: pointer;
            transition: var(--transition);
        }

        .toggle-password:hover {
            color: var(--primary);
        }

        /* Opciones del formulario */
        .form-options {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 30px;
            font-size: 0.85rem;
        }

        .remember-me {
            display: flex;
            align-items: center;
            gap: 8px;
            cursor: pointer;
            color: var(--dark);
        }

        .remember-me input {
            width: 16px;
            height: 16px;
            cursor: pointer;
            accent-color: var(--primary);
        }

        .forgot-link {
            color: var(--primary);
            text-decoration: none;
            transition: var(--transition);
        }

        .forgot-link:hover {
            color: var(--secondary);
            text-decoration: underline;
        }

        /* Botón de login */
        .btn-login {
            width: 100%;
            padding: 14px;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            border: none;
            border-radius: 12px;
            color: white;
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            transition: var(--transition);
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
            font-family: 'Poppins', sans-serif;
        }

        .btn-login:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 25px rgba(45, 156, 219, 0.3);
        }

        .btn-login:active {
            transform: translateY(0);
        }

        .btn-login:disabled {
            opacity: 0.7;
            cursor: not-allowed;
        }

        /* Nota de seguridad */
        .security-note {
            margin-top: 25px;
            text-align: center;
            font-size: 0.7rem;
            color: var(--gray);
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
        }

        .security-note i {
            color: var(--secondary);
        }

        .system-status {
            display: inline-flex;
            align-items: center;
            gap: 6px;
        }

        .status-dot {
            width: 8px;
            height: 8px;
            border-radius: 50%;
            background-color: #27AE60;
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0%, 100% { opacity: 1; transform: scale(1); }
            50% { opacity: 0.5; transform: scale(0.8); }
        }

        /* Loading spinner */
        .loading-spinner {
            display: inline-block;
            width: 18px;
            height: 18px;
            border: 2px solid white;
            border-top-color: transparent;
            border-radius: 50%;
            animation: spin 0.8s linear infinite;
        }

        @keyframes spin {
            to { transform: rotate(360deg); }
        }

        /* Responsive */
        @media (max-width: 900px) {
            .login-container {
                flex-direction: column;
            }
            
            .login-info {
                padding: 35px 30px;
            }
            
            .login-form-container {
                padding: 40px 30px;
            }
            
            .stat-row {
                padding: 12px;
            }
        }

        @media (max-width: 480px) {
            .login-wrapper {
                margin: 10px;
            }
            
            .login-info, .login-form-container {
                padding: 25px 20px;
            }
            
            .form-header h2 {
                font-size: 1.5rem;
            }
            
            .form-options {
                flex-direction: column;
                gap: 15px;
                align-items: flex-start;
            }
        }

        /* Animación de error */
        .error-shake {
            animation: shake 0.5s ease-in-out;
        }

        @keyframes shake {
            0%, 100% { transform: translateX(0); }
            25% { transform: translateX(-5px); }
            75% { transform: translateX(5px); }
        }

        /* Efecto hover en tarjetas de estadísticas */
        .stat-row {
            transition: var(--transition);
        }

        .stat-row:hover {
            background: rgba(255, 255, 255, 0.2);
            transform: translateX(5px);
        }
    </style>
</head>
<body>
    <div class="login-wrapper">
        <div class="login-container">
            <!-- Lado izquierdo - Información del Hospital -->
            <div class="login-info">
                <div class="hospital-badge">
                    <div class="badge-icon">
                        <i class="fas fa-hospital-user"></i>
                    </div>
                    <h1>ST. Fiacre</h1>
                    <p>Hospital de San Andreas</p>
                </div>

                <div class="info-stats">
                    <div class="stat-row">
                        <span class="stat-label"><i class="fas fa-clock"></i> Atención</span>
                        <span class="stat-value">24/7 - 365 días</span>
                    </div>
                    <div class="stat-row">
                        <span class="stat-label"><i class="fas fa-user-md"></i> Personal Activo</span>
                        <span class="stat-value">+50 profesionales</span>
                    </div>
                    <div class="stat-row">
                        <span class="stat-label"><i class="fas fa-ambulance"></i> Unidades Móviles</span>
                        <span class="stat-value">12 ambulancias</span>
                    </div>
                    <div class="stat-row">
                        <span class="stat-label"><i class="fas fa-chart-line"></i> Pacientes Atendidos</span>
                        <span class="stat-value">+2,500 mensuales</span>
                    </div>
                </div>

                <div class="emergency-badge">
                    <div class="number">911</div>
                    <div class="label">EMERGENCIAS • ATENCIÓN INMEDIATA</div>
                </div>
            </div>

            <!-- Lado derecho - Formulario de login -->
            <div class="login-form-container">
                <div class="form-header">
                    <h2>
                        <i class="fas fa-heartbeat"></i>
                        Acceso al Sistema
                    </h2>
                    <p>Ingrese sus credenciales médicas para acceder al sistema interno</p>
                </div>

                <?php if ($error): ?>
                <div class="alert-message alert-error">
                    <i class="fas fa-exclamation-triangle"></i>
                    <span><?php echo htmlspecialchars($error); ?></span>
                </div>
                <?php endif; ?>

                <?php if ($success): ?>
                <div class="alert-message alert-success">
                    <i class="fas fa-check-circle"></i>
                    <span><?php echo htmlspecialchars($success); ?></span>
                </div>
                <?php endif; ?>

                <form id="loginForm" method="POST" action="">
                    <div class="input-group">
                        <label for="username">
                            <i class="fas fa-id-card"></i> Credencial / ID Médico
                        </label>
                        <div class="input-wrapper">
                            <i class="fas fa-user-md input-icon"></i>
                            <input type="text" id="username" name="username" 
                                   placeholder="Ej: dr.martinez | enfermera.garcia" 
                                   required autocomplete="username"
                                   value="<?php echo isset($_COOKIE['sams_remember']) ? htmlspecialchars($_COOKIE['sams_remember']) : ''; ?>">
                        </div>
                    </div>

                    <div class="input-group">
                        <label for="password">
                            <i class="fas fa-lock"></i> Contraseña
                        </label>
                        <div class="input-wrapper">
                            <i class="fas fa-key input-icon"></i>
                            <input type="password" id="password" name="password" 
                                   placeholder="••••••••" required autocomplete="current-password">
                            <button type="button" class="toggle-password" id="togglePassword">
                                <i class="fas fa-eye"></i>
                            </button>
                        </div>
                    </div>

                    <div class="form-options">
                        <label class="remember-me">
                            <input type="checkbox" name="remember" id="remember" 
                                   <?php echo isset($_COOKIE['sams_remember']) ? 'checked' : ''; ?>>
                            <span>Mantener sesión activa</span>
                        </label>
                        <a href="#" class="forgot-link" id="forgotPasswordLink">
                            <i class="fas fa-question-circle"></i> ¿Olvidó sus credenciales?
                        </a>
                    </div>

                    <button type="submit" class="btn-login" id="loginBtn">
                        <i class="fas fa-sign-in-alt"></i>
                        <span>ACCEDER AL SISTEMA</span>
                    </button>

                    <div class="security-note">
                        <i class="fas fa-shield-alt"></i>
                        <span>SISTEMA SEGURO • ACCESO RESTRINGIDO</span>
                        <span class="system-status">
                            <span class="status-dot"></span>
                            ACTIVO
                        </span>
                    </div>
                </form>
                
                <div style="margin-top: 20px; text-align: center; font-size: 0.7rem; color: var(--gray);">
                    <i class="fas fa-laptop-medical"></i> ST. Fiacre Hospital v2.0 • Sistema de Gestión Médica
                </div>
            </div>
        </div>
    </div>

    <script>
        // Elementos del DOM
        const togglePassword = document.getElementById('togglePassword');
        const passwordInput = document.getElementById('password');
        const loginForm = document.getElementById('loginForm');
        const loginBtn = document.getElementById('loginBtn');
        const forgotLink = document.getElementById('forgotPasswordLink');

        // Toggle para mostrar/ocultar contraseña
        togglePassword.addEventListener('click', function() {
            const type = passwordInput.getAttribute('type') === 'password' ? 'text' : 'password';
            passwordInput.setAttribute('type', type);
            this.querySelector('i').classList.toggle('fa-eye');
            this.querySelector('i').classList.toggle('fa-eye-slash');
            
            // Efecto visual
            this.style.transform = 'scale(1.1)';
            setTimeout(() => {
                this.style.transform = 'scale(1)';
            }, 200);
        });

        // Validación y envío del formulario con efecto de carga
        loginForm.addEventListener('submit', function(e) {
            const username = document.getElementById('username').value.trim();
            const password = passwordInput.value.trim();
            
            if (!username || !password) {
                e.preventDefault();
                showTemporaryError('Por favor, complete todos los campos');
                return;
            }
            
            // Mostrar efecto de carga
            loginBtn.disabled = true;
            const originalText = loginBtn.innerHTML;
            loginBtn.innerHTML = '<span class="loading-spinner"></span><span>VERIFICANDO CREDENCIALES...</span>';
            
            // El formulario se enviará normalmente, pero mostramos el efecto de carga
            setTimeout(() => {
                // Si después de 5 segundos no se redirige, restaurar botón
                // (esto es solo por si hay problemas de red)
                if (loginBtn.disabled) {
                    loginBtn.disabled = false;
                    loginBtn.innerHTML = originalText;
                }
            }, 5000);
        });

        // Función para mostrar error temporal sin recargar
        function showTemporaryError(message) {
            // Buscar si ya hay un contenedor de alerta
            let alertContainer = document.querySelector('.alert-message');
            if (alertContainer) {
                alertContainer.remove();
            }
            
            const errorDiv = document.createElement('div');
            errorDiv.className = 'alert-message alert-error';
            errorDiv.innerHTML = `
                <i class="fas fa-exclamation-triangle"></i>
                <span>${message}</span>
            `;
            
            const formHeader = document.querySelector('.form-header');
            formHeader.insertAdjacentElement('afterend', errorDiv);
            
            // Animación de shake
            document.querySelector('.login-form-container').classList.add('error-shake');
            setTimeout(() => {
                document.querySelector('.login-form-container').classList.remove('error-shake');
            }, 500);
            
            // Auto-ocultar después de 4 segundos
            setTimeout(() => {
                if (errorDiv) {
                    errorDiv.style.opacity = '0';
                    setTimeout(() => errorDiv.remove(), 300);
                }
            }, 4000);
        }

        // Enlace de recuperación de credenciales
        forgotLink.addEventListener('click', function(e) {
            e.preventDefault();
            
            // Modal de contacto con el departamento médico
            const modal = document.createElement('div');
            modal.style.cssText = `
                position: fixed;
                top: 0;
                left: 0;
                width: 100%;
                height: 100%;
                background: rgba(0, 0, 0, 0.85);
                display: flex;
                align-items: center;
                justify-content: center;
                z-index: 10000;
                animation: fadeIn 0.3s ease;
            `;
            
            const modalContent = document.createElement('div');
            modalContent.style.cssText = `
                background: white;
                padding: 35px;
                border-radius: 20px;
                max-width: 450px;
                width: 90%;
                text-align: center;
                box-shadow: 0 20px 50px rgba(0,0,0,0.3);
            `;
            
            modalContent.innerHTML = `
                <i class="fas fa-heartbeat" style="font-size: 60px; color: var(--primary); margin-bottom: 20px;"></i>
                <h3 style="color: var(--dark); margin-bottom: 15px; font-size: 1.5rem;">Recuperación de Credenciales</h3>
                <p style="color: var(--gray); margin-bottom: 20px; font-size: 0.9rem;">
                    Para restablecer sus credenciales de acceso al sistema, comuníquese con el departamento de Recursos Humanos o con su supervisor inmediato.
                </p>
                <div style="background: var(--light); padding: 20px; border-radius: 12px; margin-bottom: 25px;">
                    <p style="color: var(--primary); margin-bottom: 8px;">
                        <i class="fas fa-envelope"></i> <strong>rrhh@stfiacre.ls</strong>
                    </p>
                    <p style="color: var(--primary); margin-bottom: 8px;">
                        <i class="fas fa-phone"></i> <strong>Ext. 4300 - Recursos Humanos</strong>
                    </p>
                    <p style="color: var(--secondary); font-size: 0.75rem; margin-top: 10px;">
                        <i class="fas fa-clock"></i> Horario: Lunes a Viernes, 8:00 - 17:00
                    </p>
                </div>
                <button id="closeModalBtn" style="
                    background: linear-gradient(135deg, var(--primary), var(--secondary));
                    border: none;
                    padding: 12px 30px;
                    border-radius: 50px;
                    color: white;
                    cursor: pointer;
                    font-weight: 600;
                    font-size: 0.9rem;
                ">CERRAR</button>
            `;
            
            modal.appendChild(modalContent);
            document.body.appendChild(modal);
            
            const closeBtn = modalContent.querySelector('#closeModalBtn');
            closeBtn.addEventListener('click', () => modal.remove());
            modal.addEventListener('click', (e) => { if (e.target === modal) modal.remove(); });
        });

        // Efectos de entrada para inputs
        const inputs = document.querySelectorAll('.input-wrapper input');
        inputs.forEach(input => {
            input.addEventListener('focus', function() {
                this.parentElement.style.transform = 'scale(1.01)';
            });
            input.addEventListener('blur', function() {
                this.parentElement.style.transform = 'scale(1)';
            });
        });

        // Agregar estilo para animación fadeIn
        const style = document.createElement('style');
        style.textContent = `
            @keyframes fadeIn {
                from { opacity: 0; }
                to { opacity: 1; }
            }
        `;
        document.head.appendChild(style);
        
        // Mensaje de consola para seguridad
        console.log('%c⚠️ ST. FIACRE HOSPITAL - SISTEMA DE GESTIÓN MÉDICA ⚠️', 'color: #2D9CDB; font-size: 14px; font-weight: bold;');
        console.log('%cAcceso restringido a personal autorizado. Todos los accesos son registrados.', 'color: #27AE60; font-size: 12px;');
        
        // Contador de intentos de login fallidos (simulado)
        let failedAttempts = 0;
        const usernameInput = document.getElementById('username');
        usernameInput.addEventListener('keypress', function(e) {
            if (e.key === 'Enter') {
                const password = passwordInput.value;
                if (!password) {
                    e.preventDefault();
                    showTemporaryError('Por favor, ingrese su contraseña');
                }
            }
        });
    </script>
</body>
</html>
