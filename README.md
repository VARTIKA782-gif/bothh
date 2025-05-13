
<html>
<head>
    <title>WhatsApp Bot Interface</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 50px;
            background-color: white;
        }

        h1 {
            color: green;
        }

        .chat-box {
            background-color: white;
            padding: 20px;
            border-radius: 10px;
            max-width: 600px;
            margin: 0 auto;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
        }

        .message {
            margin-bottom: 10px;
            padding: 10px;
            border-radius: 5px;
            max-width: 80%;
        }

        .user {
            background-color: green;
            align-self: flex-end;
        }

        .bot {
            background-color: white;
            border:  solid green;
            align-self: flex-start;
        }

        .messages {
            display: flex;
            flex-direction: column;
            gap: 10px;
            margin-bottom: 20px;
            min-height: 200px;
        }

        form {
            display: flex;
        }

        input[type="text"] {
            flex: 1;
            padding: 10px;
        }

        button {
            padding: 10px 20px;
        }
    </style>
</head>
<body>
    <div class="chat-box">
        <h1>Chat with WhatsApp Bot</h1>
        <div class="messages" id="chat">
            <!-- Messages appear here -->
        </div>
        <form id="chatForm">
            <input type="text" id="messageInput" placeholder="Type your message here" required>
            <button type="submit">Send</button>
        </form>
    </div>

    <script>
        const chat = document.getElementById('chat');
        const form = document.getElementById('chatForm');
        const input = document.getElementById('messageInput');

        form.addEventListener('submit', function(e)
		 {
            e.preventDefault();

            const userMessage = input.value.trim();
            if (userMessage === '') return;

            // Add user message
            const userDiv = document.createElement('div');
            userDiv.className = 'message user';
            userDiv.textContent = "You: " + userMessage;
            chat.appendChild(userDiv);

            input.value = '';

            // Simulate bot response
            setTimeout(() => {
                const botDiv = document.createElement('div');
                botDiv.className = 'message bot';
                botDiv.textContent = "Bot: " + Response(userMessage);
                chat.appendChild(botDiv);
                chat.scrollTop = chat.scrollHeight;
            }, 500);
        });

        function Response(message) {
            // Simple response logic (can be improved or connected to a backend)
            if (message.toLowerCase().includes("hello")) 
			{
                return "Hi there! How can I help you today?";
            }
			 else if (message.toLowerCase().includes("bye"))
			 {
                return "Goodbye! Have a great day!";
			  }
			else if (message.toLowerCase().includes("what you are doing"))
			 {
                return "nathing !! just talking to you!!";
			}
				else if (message.toLowerCase().includes("good moring"))
			{
              	  return "good morninng";
            } 
			else 
			{
                return "I'm just a bot, but I'm listening!";
            }
        }
    </script>
</body>
</html>
