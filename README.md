# My First Project

This is my first GitHub repository 🚀

## Features
- Simple project
- Learning GitHub

## Author
Yuvraj Sharma# Chat-box<!DOCTYPE html>
<html>
<head>
  <title>Chat App</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>

<h2>💬 Chat Box</h2>

<div id="chatBox"></div>

<input type="text" id="msg" placeholder="Type message...">
<button onclick="sendMsg()">Send</button>

<br><br>
<a href="ai.html">Go to AI Page</a> |
<a href="profile.html">Profile</a>

<script src="script.js"></script>
</body>
</html><!DOCTYPE html>
<html>
<head>
  <title>AI Chat</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>

<h2>🤖 AI Chat</h2>

<div id="aiBox"></div>

<input type="text" id="aiInput" placeholder="Ask AI...">
<button onclick="askAI()">Ask</button>

<br><br>
<a href="index.html">Back to Chat</a>

<script src="script.js"></script>
</body>
</html><!DOCTYPE html>
<html>
<head>
  <title>Profile</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>

<h2>👤 Profile</h2>

<input type="text" id="name" placeholder="Enter name">
<button onclick="saveProfile()">Save</button>

<p id="showName"></p>

<br><br>
<a href="index.html">Back to Chat</a>

<script src="script.js"></script>
</body>
</html>body {
  font-family: Arial;
  text-align: center;
  background: #111;
  color: white;
}

#chatBox, #aiBox {
  height: 200px;
  border: 1px solid #444;
  margin: 10px;
  padding: 10px;
  overflow-y: scroll;
}

input {
  padding: 8px;
}

button {
  padding: 8px;
  background: blue;
  color: white;
  border: none;
}function sendMsg() {
  let msg = document.getElementById("msg").value;
  let box = document.getElementById("chatBox");

  box.innerHTML += "<p>🧑: " + msg + "</p>";
  document.getElementById("msg").value = "";
}

function askAI() {
  let input = document.getElementById("aiInput").value;
  let box = document.getElementById("aiBox");

  box.innerHTML += "<p>🧑: " + input + "</p>";
  
  // Fake AI reply
  box.innerHTML += "<p>🤖: I am AI, working...!</p>";

  document.getElementById("aiInput").value = "";
}

function saveProfile() {
  let name = document.getElementById("name").value;
  localStorage.setItem("username", name);
  document.getElementById("showName").innerText = "Saved: " + name;
}

// Load saved name
window.onload = function() {
  let name = localStorage.getItem("username");
  if(name) {
    document.getElementById("showName").innerText = "Saved: " + name;
  }
}