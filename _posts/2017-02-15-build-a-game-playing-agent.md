---
layout: post
title: "Build a Game-playing Agent"
date: 2017-02-15
categories: ['Artificial Intelligence']
---

In this project, we will develop an adversarial search agent to play the game "Isolation". 

Isolation is a deterministic, two-player game of perfect information in which the players alternate turns moving a single piece from one cell to another on a board. Whenever either player occupies a cell, that cell becomes blocked for the remainder of the game. The first player with no remaining legal moves loses, and the opponent is declared the winner.

This project uses a version of Isolation where each agent is restricted to L-shaped movements (like a knight in chess) on a rectangular grid (like a chess or checkerboard). The agents can move to any open cell on the board that is 2-rows and 1-column or 2-columns and 1-row away from their current position on the board. Movements are blocked at the edges of the board (the board does not wrap around), however, the player can "jump" blocked or occupied spaces (just like a knight in chess).

Additionally, agents will have a fixed time limit each turn to search for the best move and respond. If the time limit expires during a player's turn, that player forfeits the match, and the opponent wins.

These rules are implemented in the isolation.Board class provided in the repository.

[Source Code](https://github.com/srikanthpagadala/udacity/tree/master/Artificial%20Intelligence%20Nanodegree/Build%20a%20Game-playing%20Agent){:target="_blank"}

[Report](https://github.com/srikanthpagadala/udacity/blob/master/Artificial%20Intelligence%20Nanodegree/Build%20a%20Game-playing%20Agent/reports/tournament_results.txt){:target="_blank"}

