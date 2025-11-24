# Chatbot_simple
Simple_chatbot para testes
<!DOCTYPE html>
<html>
<head>
    <title>Chatbot Simples</title>
    <style>
        body { font-family: Arial; background: #f0f0f0; padding: 20px; }
        #chat { width: 100%; max-width: 500px; margin: auto; }
        .msg { background: #fff; padding: 10px; margin: 5px 0; border-radius: 5px; }
        .user { background: #d1e7dd; }
    </style>
</head>
<body>
    <div id="chat"></div>

    <input type="text" id="input" placeholder="Digite sua mensagem..." style="width:80%;">
    <button onclick="send()">Enviar</button>

    <script>
        function send() {
            let input = document.getElementById("input");
            let text = input.value.trim();
            if (!text) return;

            addMessage("Você: " + text, "user");

            let resposta = responder(text);
            addMessage("Bot: " + resposta);

            input.value = "";
        }

        function addMessage(text, cls = "") {
            let chat = document.getElementById("chat");
            let div = document.createElement("div");
            div.className = "msg " + cls;
            div.textContent = text;
            chat.appendChild(div);
        }

        // Regras simples de resposta
        function responder(msg) {
            msg = msg.toLowerCase();

            if (msg.includes("oi") || msg.includes("olá"))
                return "Olá! Como posso ajudar?";

            if (msg.includes("nome"))
                return "Eu sou um bot simples feito no GitHub";

            if (msg.includes("tchau"))
                return "Até mais!";

            return "Não entendi. Sou apenas um bot simples 😅";
        }
    </script>
</body>
</html>
