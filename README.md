# <!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Login </title>
<style>
    body {
        font-family: Arial, sans-serif;
        background-color: #f4f4f4;
        margin: 0;
        padding: 0;
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
    }

    .container {
        width: 300px;
        padding: 20px;
        background-color: #fff;
        border-radius: 5px;
        box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        text-align: center;
    }

    h2 {
        text-align: center;
        margin-bottom: 20px;
    }

    label {
        display: block;
        margin-bottom: 5px;
    }

    input[type="text"], input[type="password"] {
        width: 100%;
        padding: 8px;
        margin-bottom: 15px;
        border: 1px solid #ccc;
        border-radius: 3px;
        box-sizing: border-box;
    }

    button {
        width: 100%;
        padding: 10px;
        background-color: #4CAF50;
        color: #fff;
        border: none;
        border-radius: 3px;
        cursor: pointer;
    }

    button:hover {
        background-color: #45a049;
    }

    .hidden {
        display: none;
    }

    .store-container {
        width: 400px;
        padding: 20px;
        background-color: #fff;
        border-radius: 5px;
        box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        text-align: center;
    }

    .store-container img {
        width: 100%;
        border-radius: 5px;
        margin-bottom: 20px;
    }

    .store-container p {
        margin-bottom: 10px;
    }

    .store-container a {
        display: inline-block;
        padding: 10px 20px;
        background-color: #4CAF50;
        color: #fff;
        text-decoration: none;
        border-radius: 3px;
        margin-top: 20px;
    }

    .store-container a:hover {
        background-color: #45a049;
    }
</style>
</head>
<body>

<div id="loginPage" class="container">
    <h2>Login </h2>
    <form id="loginForm">
        <label for="username">Username:</label>
        <input type="text" id="username" name="username" required>
        <label for="password">Password:</label>
        <input type="password" id="password" name="password" required>
        <button type="submit">Login</button>
    </form>
</div>

<div id="storePage" class="store-container hidden">
    <h2>Bem-vindo à Loja Virtual</h2>
    <img src="https://via.placeholder.com/300" alt="Loja Virtual">
    <p>Seja bem-vindo à nossa loja virtual! Aqui você encontra os melhores produtos com os melhores preços.</p>
    <a href="#" id="logoutBtn">Sair</a>
</div>

<script>
    const loginPage = document.getElementById('loginPage');
    const storePage = document.getElementById('storePage');
    const loginForm = document.getElementById('loginForm');
    const logoutBtn = document.getElementById('logoutBtn');

    loginForm.addEventListener('submit', function(event) {
        event.preventDefault();
        const username = loginForm.elements.username.value;
        const password = loginForm.elements.password.value;
        if (username === 'admin' && password === 'admin') {
            loginPage.classList.add('hidden');
            storePage.classList.remove('hidden');
        } else {
            alert('Credenciais inválidas. Tente novamente.');
        }
    });

    logoutBtn.addEventListener('click', function() {
        loginPage.classList.remove('hidden');
        storePage.classList.add('hidden');
    });
</script>

</body>
</html>
