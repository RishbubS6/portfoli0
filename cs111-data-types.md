---
layout: post
title: Data Types Showcase
permalink: /cs111-data-types
---

# Data Types

Data types are the building blocks of all programs. You use numbers, strings, booleans, arrays, and objects to store and manipulate information.

## Subrequirements

### Numbers

<div style="margin-bottom: 12px;">
<strong>What was learned:</strong> Numbers are used to represent values like position, speed, and score in games and apps. They are the basis for all calculations, from moving a ball to keeping track of points. Working with numbers in Pong and the Calculator project showed how math drives game mechanics and user feedback.
</div>
<div style="margin-bottom: 18px;">
<strong>Evidence:</strong>
<ul>
	<li>Pong Game: Ball position, velocity, and score (<a href="{{site.baseurl}}/custompong">View Pong Game</a>)</li>
	<li>Calculator: Arithmetic operations (<a href="{{site.baseurl}}/calculator">View Calculator</a>)</li>
</ul>
</div>

### Strings

<div style="margin-bottom: 12px;">
<strong>What was learned:</strong> Strings are sequences of characters used for names, messages, and game states. They let us display information to players and manage text-based data. Practicing string operations in Pong and homeworks made it clear how important clear communication is in software.
</div>
<div style="margin-bottom: 18px;">
<strong>Evidence:</strong>
<ul>
	<li>Pong Game: Displaying scores and messages</li>
	<li>Homeworks: <a href="{{site.baseurl}}/js/strings">Strings Homework</a></li>
</ul>
</div>

### Booleans

<div style="margin-bottom: 12px;">
<strong>What was learned:</strong> Booleans are true/false values that control logic and state in programs. In games, they help track things like whether the game is paused, if a player has won, or if a collision happened. Using booleans in Pong and homeworks helped me understand how to manage game flow and decisions.
</div>
<div style="margin-bottom: 18px;">
<strong>Evidence:</strong>
<ul>
	<li>Pong Game: Flags for pause, win, and collision</li>
	<li>Homeworks: <a href="{{site.baseurl}}/js/booleans">Booleans Homework</a></li>
</ul>
</div>

### Arrays

<div style="margin-bottom: 12px;">
<strong>What was learned:</strong> Arrays are lists that let us store and manage groups of related data, like game objects or scores. They make it easy to loop through and update many items at once. Using arrays in Pong and homeworks showed how to efficiently handle collections in code.
</div>
<div style="margin-bottom: 18px;">
<strong>Evidence:</strong>
<ul>
	<li>Pong Game: Array of power-ups</li>
	<li>Homeworks: <a href="{{site.baseurl}}/js/arrays">Arrays Homework</a></li>
</ul>
</div>

### Objects (JSON)

<div style="margin-bottom: 12px;">
<strong>What was learned:</strong> Objects and JSON let us organize data with named properties, making it easy to store settings, player info, or game state. They are used for configuration and to pass complex data between parts of a program. Working with objects in Pong and homeworks helped me see how to structure and access information efficiently.
</div>
<div style="margin-bottom: 18px;">
<strong>Evidence:</strong>
<ul>
	<li>Pong Game: Config object</li>
	<li>Homeworks: <a href="{{site.baseurl}}/js/json">JSON Homework</a></li>
</ul>
</div>

---


---

<h3>Coderunner/Gamerunner Example</h3>
<div style="margin-bottom: 18px;">
<em>Below is a Gamerunner widget showing how data types are used in Pong. Try changing the code to see how numbers, strings, and arrays work in practice!</em>
</div>
{% include runners/game.html runner_id="pong-datatypes-demo" challenge="Show data types in Pong" code="// Example: numbers, strings, arrays\nlet scores = [3, 5, 7];\nlet total = 0;\nfor (let s of scores) total += s;\nlet msg = 'Total score: ' + total;\ndocument.getElementById('gameCanvas').style.background = '#6A5ACD';\nctx = document.getElementById('gameCanvas').getContext('2d');\nctx.fillStyle = '#fff';\nctx.font = '20px Arial';\nctx.fillText(msg, 30, 50);" %}

