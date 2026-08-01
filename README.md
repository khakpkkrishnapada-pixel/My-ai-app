
<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My AI Assistant</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #121212;
            color: #ffffff;
            margin: 0;
            display: flex;
            flex-direction: column;
            height: 100vh;
        }
        .header {
            padding: 15px;
            background-color: #1f1f1f;
            text-align: center;
            font-size: 20px;
            font-weight: bold;
            border-bottom: 1px solid #333;
        }
        .chat-box {
            flex: 1;
            padding: 20px;
            overflow-y: auto;
            display: flex;
            flex-direction: column;
            gap: 15px;
        }
        .message {
            max-width: 80%;
            padding: 12px 16px;
            border-radius: 12px;
            line-height: 1.5;
        }
        .user-message {
            background-color: #007bff;
            align-self: flex-end;
            color: white;
        }
        .ai-message {
            background-color: #2a2a2a;
            align-self: flex-start;
            color: white;
        }
        .input-container {
            display: flex;
            padding: 15px;
            background-color: #1f1f1f;
            border-top: 1px solid #333;
        }
        input {
            flex: 1;
            padding: 12px;
            border: 1px solid #444;
            border-radius: 8px;
            background-color: #2b2b2b;
            color: white;
            font-size: 16px;
            outline: none;
        }
        button {
            margin-left: 10px;
            padding: 12px 20px;
            border: none;
            background-color: #28a745;
            color: white;
            border-radius: 8px;
            font-size: 16px;
            cursor: pointer;
        }
        button:hover {
            background-color: #218838;
        }
    </style>
</head>
<body>

    <div class="header">My AI Assistant</div>

    <div class="chat-box" id="chatBox">
        <div class="message ai-message">হ্যালো! আমি আপনার AI অ্যাসিস্ট্যান্ট। কীভাবে সাহায্য করতে পারি?</div>
    </div>

    <div class="input-container">
        <input type="text" id="userInput" placeholder="আপনার প্রশ্ন লিখুন...">
        <button onclick="sendMessage()">Send</button>
    </div>

    <script>
        function sendMessage() {
            const input = document.getElementById('userInput');
            const chatBox = document.getElementById('chatBox');
            const text = input.value.trim();

            if (text !== '') {
                // User message display
                const userDiv = document.createElement('div');
                userDiv.className = 'message user-message';
                userDiv.innerText = text;
                chatBox.appendChild(userDiv);

                input.value = '';
                chatBox.scrollTop = chatBox.scrollHeight;

                // Temporary AI response simulation
                setTimeout(() => {
                    const aiDiv = document.createElement('div');
                    aiDiv.className = 'message ai-message';
                    aiDiv.innerText = 'ধন্যবাদ! খুব শীঘ্রই আমার সাথে আসল AI সংযোগ (API) চালু হতে যাচ্ছে।';
                    chatBox.appendChild(aiDiv);
                    chatBox.scrollTop = chatBox.scrollHeight;
                }, 1000);
            }
        }
    </script>

</body>
</html>
