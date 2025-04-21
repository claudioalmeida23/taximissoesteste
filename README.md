<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Login Motorista - Táxi Missões</title>
  <style>
    body { font-family: Arial, sans-serif; text-align: center; padding: 20px; }
    input { padding: 10px; margin: 10px 0; width: 80%; max-width: 300px; }
    button { padding: 10px; width: 80%; max-width: 300px; background-color: #28a745; color: white; border: none; cursor: pointer; }
    button:hover { background-color: #218838; }
  </style>
</head>
<body>
  <h2>Login do Motorista</h2>
  <form id="loginForm">
    <input type="text" id="username" placeholder="Nome de usuário" required><br>
    <input type="password" id="password" placeholder="Senha" required><br>
    <button type="submit">Entrar</button>
  </form>
  <script src="https://www.gstatic.com/firebasejs/9.22.2/firebase-app.js"></script>
  <script src="https://www.gstatic.com/firebasejs/9.22.2/firebase-auth.js"></script>
  <script>
    const firebaseConfig = {
      apiKey: "SUA_API_KEY",
      authDomain: "SEU_DOMINIO.firebaseapp.com",
      databaseURL: "https://SEU_DOMINIO-default-rtdb.firebaseio.com",
      projectId: "SEU_PROJETO",
      storageBucket: "SEU_BUCKET.appspot.com",
      messagingSenderId: "ID_MENSAGEM",
      appId: "SEU_APP_ID"
    };

    firebase.initializeApp(firebaseConfig);
    const auth = firebase.auth();

    const form = document.getElementById("loginForm");
    form.addEventListener("submit", (e) => {
      e.preventDefault();
      const username = document.getElementById("username").value;
      const password = document.getElementById("password").value;

      auth.signInWithEmailAndPassword(username, password).then(user => {
        window.location.href = "admin.html";  // Redireciona para o painel do motorista
      }).catch(err => {
        alert("Erro no login: " + err.message);
      });
    });
  </script>
</body>
</html>
