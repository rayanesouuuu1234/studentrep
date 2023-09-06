---
comments: True
layout: post
title: Soccer Card Game
description: 
type: hacks
courses: {'csse': {'week': 1}, 'csp': {'week': 3}, 'csa': {'week': 0}}
categories: ['C4.1']
---

<html lang="en">
<head>
    <!-- Set character encoding for the document -->
    <meta charset="UTF-8">
    <!-- Set viewport for responsive design on mobile devices -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Soccer Card Game</title>
</head>
<body>
    <h1>Soccer Card Game</h1>
    
<!-- Button to start a round of the game -->
    <div>
        <button id="play-btn" onclick="playRound()">Play Round</button>
    </div>

 <!-- Section to display player scores -->
    <h2>Score:</h2>
    <p>Player 1: <span id="player1-score">0</span></p>
    <p>Player 2: <span id="player2-score">0</span></p>

<!-- Section to display the results of the round and which card each player drew -->

    <h2>Results:</h2>
    <p>Player 1 drew: <span id="player1-result">---</span></p>
    <p>Player 2 drew: <span id="player2-result">---</span></p>
    <h3><span id="round-result">Press the button to start the game!</span></h3>
    <h4><span id="game-result">Best out of 5 rounds!</span></h4>

    <script>
        // Array of player cards, each with a name and overall rating
        const players = [
            {name: "Ronaldo", overall: 92},
            {name: "Messi", overall: 93},
            {name: "Neymar", overall: 91},
            {name: "Mbappe", overall: 90},
            {name: "Lewandowski", overall: 91},
            {name: "Modric", overall: 89},
            {name: "Ramos", overall: 90},
            {name: "Kante", overall: 88},
            {name: "Bruno Fernandes", overall: 88},
            {name: "Van Dijk", overall: 90}
        ];
        // variables for the game
        let roundsPlayed = 0;
        let player1Wins = 0;
        let player2Wins = 0;

        // Function to update the displayed scores on the webpage
        function updateScore() {
            document.getElementById("player1-score").textContent = player1Wins;
            document.getElementById("player2-score").textContent = player2Wins;
        }

        function playRound() {
            roundsPlayed++;
            const player1Card = players[Math.floor(Math.random() * players.length)];
            const player2Card = players[Math.floor(Math.random() * players.length)];

            document.getElementById("player1-result").textContent = `${player1Card.name} (Overall: ${player1Card.overall})`;
            document.getElementById("player2-result").textContent = `${player2Card.name} (Overall: ${player2Card.overall})`;

            if (player1Card.overall > player2Card.overall) {
                document.getElementById("round-result").textContent = "Player 1 wins this round!";
                player1Wins++;
            } else if (player1Card.overall < player2Card.overall) {
                document.getElementById("round-result").textContent = "Player 2 wins this round!";
                player2Wins++;
            } else {
                document.getElementById("round-result").textContent = "It's a draw!";
            }

            updateScore();

            if (roundsPlayed == 5) {
                document.getElementById("play-btn").disabled = true;

                if (player1Wins > player2Wins) {
                    document.getElementById("game-result").textContent = "Player 1 is the overall winner!";
                } else if (player1Wins < player2Wins) {
                    document.getElementById("game-result").textContent = "Player 2 is the overall winner!";
                } else {
                    document.getElementById("game-result").textContent = "The game ends in a draw!";
                }
            }
        }
    </script>
</body>
</html>
