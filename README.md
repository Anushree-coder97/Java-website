/java-coding-website  
│── index.html  (Main page)  
│── style.css   (CSS for styling)  
│── script.js   (JavaScript for interactivity)  
│── firebase.js (For login, leaderboard, etc.)  
│── quiz.js     (For quizzes and challenges)  
│── forum.js    (For the discussion forum)  
│── assets/     (Images, icons, etc.)  
│── exercises/  (Coding challenges)
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Learn Java</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header>
        <h1>Learn Java</h1>
        <nav>
            <a href="#">Home</a>
            <a href="quiz.html">Quizzes</a>
            <a href="forum.html">Forum</a>
            <a id="login-btn">Login</a>
        </nav>
    </header>

    <section class="hero">
        <h2>Master Java with Interactive Exercises</h2>
        <button onclick="startLearning()">Start Learning</button>
    </section>

    <section id="topics">
        <h3>Topics</h3>
        <ul>
            <li><a href="exercises/variables.html">Variables</a></li>
            <li><a href="exercises/loops.html">Loops</a></li>
            <li><a href="exercises/oop.html">Object-Oriented Programming</a></li>
        </ul>
    </section>

    <script src="script.js"></script>
    <script src="firebase.js"></script>
</body>
</html>
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    background: #f5f5f5;
}
header {
    background: #222;
    color: white;
    padding: 10px;
    display: flex;
    justify-content: space-between;
}
nav a {
    color: white;
    text-decoration: none;
    margin: 0 10px;
}
.hero {
    text-align: center;
    padding: 50px;
    background: #ffcc00;
}
#topics ul {
    list-style: none;
}
function startLearning() {
    alert("Welcome! Start exploring the topics.");
}

document.getElementById("login-btn").addEventListener("click", function() {
    alert("Login feature coming soon!");
});
const quizData = [
    { question: "What is Java?", options: ["Language", "Drink", "City"], answer: 0 }
];

document.addEventListener("DOMContentLoaded", function() {
    let quizContainer = document.getElementById("quiz");
    quizData.forEach((q, index) => {
        let div = document.createElement("div");
        div.innerHTML = `<p>${q.question}</p>`;
        q.options.forEach((opt, i) => {
            div.innerHTML += `<button onclick="checkAnswer(${index}, ${i})">${opt}</button>`;
        });
        quizContainer.appendChild(div);
    });
});

function checkAnswer(qIndex, selected) {
    if (selected === quizData[qIndex].answer) {
        alert("Correct!");
    } else {
        alert("Try again.");
    }
}
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Java Quizzes</title>
    <script src="quiz.js"></script>
</head>
<body>
    <h1>Java Quizzes</h1>
    <div id="quiz"></div>
</body>
</html>
document.addEventListener("DOMContentLoaded", function() {
    let forum = document.getElementById("forum");
    document.getElementById("post-btn").addEventListener("click", function() {
        let post = document.getElementById("post-input").value;
        if (post.trim() !== "") {
            let p = document.createElement("p");
            p.textContent = post;
            forum.appendChild(p);
        }
    });
});
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Java Forum</title>
    <script src="forum.js"></script>
</head>
<body>
    <h1>Discussion Forum</h1>
    <textarea id="post-input"></textarea>
    <button id="post-btn">Post</button>
    <div id="forum"></div>
</body>
</html>
