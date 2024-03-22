# CadastroGameTcc
Códigos do sistema de cadastro utilizados no game rooster ninja(meu projeto em grupo no tcc)
**Powered by:** [Firebase](https://firebase.google.com/?hl=pt)

Código para o firebase

 "SuaAPIKey", "seu-projeto.firebaseapp.com", substitua pelos valores reais do seu projeto Firebase. Informações no Console do Firebase.

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cadastro de Clínica com Firebase</title>
</head>
<body>
    <form onsubmit="return CadastrarClinica()">
        <label for="email">Email:</label>
        <input type="email" id="email" required>
        <br>
        <label for="password">Password:</label>
        <input type="password" id="password" required>
        <br>
        <button type="submit">Cadastrar</button>
    </form>

    <!-- Adicione o bloco de código do Firebase aqui -->
    <script src="https://www.gstatic.com/firebasejs/9.4.1/firebase-app.js"></script>
    <script src="https://www.gstatic.com/firebasejs/9.4.1/firebase-auth.js"></script>

    <script>
        // Configuração do Firebase
        const firebaseConfig = {
            apiKey: "SuaAPIKey",
            authDomain: "seu-projeto.firebaseapp.com",
            projectId: "seu-projeto",
            storageBucket: "seu-projeto.appspot.com",
            messagingSenderId: "SeuMessagingSenderId",
            appId: "SuaAppId"
        };

        // Inicialize o Firebase
        firebase.initializeApp(firebaseConfig);

        function CadastrarClinica() {
            var email = document.getElementById("email").value;
            var password = document.getElementById("password").value;

            // Crie um novo usuário no Firebase Authentication
            firebase.auth().createUserWithEmailAndPassword(email, password)
                .then((userCredential) => {
                    // Usuário criado com sucesso
                    var user = userCredential.user;
                    console.log("Cadastro de clínica realizado com sucesso! UID:", user.uid);
                })
                .catch((error) => {
                    // Trate erros aqui
                    var errorCode = error.code;
                    var errorMessage = error.message;
                    console.error("Erro no cadastro:", errorMessage);
                });

            return false; // Impede o envio do formulário
        }
    </script>
</body>
</html>




Código para formulário simples em html

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cadastro de Clínica</title>
</head>
<body>
    <form onsubmit="return CadastrarClinica()">
        <label for="username">Username:</label>
        <input type="text" id="username" required>
        <br>
        <label for="password">Password:</label>
        <input type="password" id="password" required>
        <br>
        <label for="email">Email:</label>
        <input type="email" id="email" required>
        <br>
        <label for="cnpj">CNPJ:</label>
        <input type="text" id="cnpj" required>
        <br>
        <button type="submit">Cadastrar</button>
    </form>

    <script>
        function CadastrarClinica() {
            var username = document.getElementById("username").value;
            var password = document.getElementById("password").value;
            var email = document.getElementById("email").value;
            var cnpj = document.getElementById("cnpj").value;

            // Adicione aqui a lógica de validação e armazenamento

            console.log("Cadastro de clínica realizado com sucesso!");
            return false; // Impede o envio do formulário
        }
    </script>
</body>
</html>





