---
layout: post
title: Control Structures Showcase
permalink: /cs111-control-structures
---

# Control Structures

Control structures let you control the flow of your program using loops, conditionals, and nested logic. These are essential for game logic and decision-making.

## Subrequirements

### Iteration

<div style="margin-bottom: 12px;">
<strong>What was learned:</strong> Iteration means repeating actions using loops like <code>for</code>, <code>while</code>, and <code>forEach</code>. In games, loops are used to update positions, check collisions, and animate objects every frame. Practicing iteration in Pong, Snake, and homeworks showed how essential loops are for building interactive programs.
</div>
<div style="margin-bottom: 18px;">
<strong>Evidence:</strong>
<ul>
	<li>Pong Game: Loops for updating and drawing multiple objects (<a href="{{site.baseurl}}/custompong">View Pong Game</a>)</li>
	<li>Snake Game: Loops for moving the snake and handling food (<a href="{{site.baseurl}}/snake">View Snake Game</a>)</li>
	<li>Homeworks: <a href="{{site.baseurl}}/js/arrays">Arrays Homework</a></li>
</ul>
</div>

### Conditionals

<div style="margin-bottom: 12px;">
<strong>What was learned:</strong> Conditionals use <code>if</code>, <code>else</code>, and <code>switch</code> to make decisions in code. They let us respond to player actions, check for win conditions, and control game flow. Applying conditionals in Pong and homeworks made it clear how games react to different situations.
</div>
<div style="margin-bottom: 18px;">
<strong>Evidence:</strong>
<ul>
	<li>Pong Game: Conditionals for collision detection and scoring</li>
	<li>Homeworks: <a href="{{site.baseurl}}/js/nested-conditionals">Nested Conditionals Homework</a></li>
</ul>
</div>

### Nested Conditions

<div style="margin-bottom: 12px;">
<strong>What was learned:</strong> Nested conditions are when we put one conditional inside another, allowing for multi-step decisions. This is useful for handling complex game logic, like checking for power-ups and special events. Practicing nested conditions in Pong and homeworks helped me understand how to manage advanced scenarios in code.
</div>
<div style="margin-bottom: 18px;">
<strong>Evidence:</strong>
<ul>
	<li>Pong Game: Nested checks for power-ups and win conditions</li>
	<li>Homeworks: <a href="{{site.baseurl}}/js/nested-conditionals">Nested Conditionals Homework</a></li>
</ul>
</div>

---


---

<h3>Coderunner/Gamerunner Example</h3>
<div style="margin-bottom: 18px;">
<em>Below is a Gamerunner widget showing how control structures are used in Pong. Try changing the code to see how loops and conditionals affect the game!</em>
</div>


{% include runners/game.html runner_id="pong-control-demo" challenge="Show control structures in Pong" code="// Example: loop and conditional\nlet score = 0;\nfor (let i = 0; i < 5; i++) {\n  score += 2;\n}\nif (score >= 10) {\n  document.getElementById('gameCanvas').style.background = '#1E90FF';\n}" %}

