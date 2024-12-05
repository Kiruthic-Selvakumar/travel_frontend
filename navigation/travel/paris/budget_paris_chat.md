---
layout: post
title: Paris Budget Chat
search_exclude: true
permalink: /travel/Paris/budget/chat
menu: nav/paris_hotbar.html
---
<style>
    body {
        margin: 0;
        font-family: Arial, sans-serif;
        background-color: #FDF5E6;
    }
    .chatroom-container {
        max-width: 600px;
        margin: 0 auto;
        padding: 20px;
        border: 2px solid #add8e6;
        border-radius: 8px;
        background-color: #001F3F;
    }
    .chatroom-header {
        text-align: center;
        color: #add8e6;
    }
    .chat-area {
        height: 400px;
        overflow-y: auto;
        background-color: #404040;
        border: 2px solid #add8e6;
        border-radius: 8px;
        padding: 10px;
        margin-bottom: 20px;
        color: white;
        display: flex;
        flex-direction: column;
    }
    .message {
        max-width: 80%;
        margin: 10px 0;
        padding: 10px;
        border-radius: 20px;
        position: relative;
    }
    .message.sent {
        background-color: #add8e6;
        color: black;
        align-self: flex-end;
        position: relative;
        margin-bottom: 0px;
    }
    .message-form {
        display: flex;
    }
    #messageInput {
        flex: 1;
        padding: 10px;
        border: 2px solid #add8e6;
        border-radius: 5px;
    }
    button {
        background-color: #add8e6;
        border: none;
        padding: 10px 15px;
        border-radius: 5px;
        cursor: pointer;
    }
    button:hover {
        background-color: #733f3f;
    }
    .chatroom-link {
            display: block;
            text-align: center;
            margin: 20px 0;
            padding: 10px;
            background-color: #1A2A6C;
            color: black;
            text-decoration: none;
            border-radius: 5px;
        }
    .chatroom-link:hover {
        background-color: #add8e6;
    }
</style>
<div class="chatroom-container">
        <header class="chatroom-header">
            <h1>Paris Budget Chatroom</h1>
            <p>What deals were you able to find?</p>
        </header>
        <div class="chat-area" id="chatArea">
        </div>
        <form class="message-form" id="messageForm">
            <input type="text" id="messageInput" placeholder="Enter your message..." required>
            <button type="submit">Send</button>
        </form>
        <a href="{{site.baseurl}}/travel/Paris/budget.html" class="chatroom-link">Back to Paris Budget</a>
</div>
<script>
    const chatArea = document.getElementById('chatArea');
    const messageForm = document.getElementById('messageForm');
    const messageInput = document.getElementById('messageInput');
    messageForm.addEventListener('submit', function (e) {
        e.preventDefault();
        const messageText = messageInput.value.trim();
        if (messageText !== "") {
            const messageElement = document.createElement('div');
            messageElement.classList.add('message', 'sent');
            messageElement.textContent = messageText;
            chatArea.appendChild(messageElement);
            messageInput.value = "";
            chatArea.scrollTop = chatArea.scrollHeight; // Auto-scroll to the newest message
        }
    });
</script>