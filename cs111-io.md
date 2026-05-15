---
layout: post
title: Input/Output (I/O) Showcase
permalink: /cs111-io
---

# Input/Output (I/O)

I/O covers how your program interacts with users and other systems, including keyboard input, canvas rendering, and API calls.

## Subrequirements

### Keyboard Input

<div style="margin-bottom: 12px;">
<strong>What was learned:</strong> Keyboard input lets users control games and apps by pressing keys. We use event listeners to detect when keys are pressed and trigger actions like moving paddles or starting a game. Practicing keyboard input in Pong and Snake made it clear how important responsive controls are for a good user experience.
</div>
<div style="margin-bottom: 18px;">
<strong>Evidence:</strong>
<ul>
	<li>Pong Game: WASD and Arrow key controls (<a href="{{site.baseurl}}/custompong">View Pong Game</a>)</li>
	<li>Snake Game: Spacebar and arrow key controls (<a href="{{site.baseurl}}/snake">View Snake Game</a>)</li>
</ul>
</div>

### Canvas Rendering

<div style="margin-bottom: 12px;">
<strong>What was learned:</strong> Canvas rendering is how we draw graphics, shapes, and text in games using code. By updating the canvas every frame, we can animate objects and create interactive visuals. Working with the canvas in Pong and Snake helped me understand how games display action and feedback to players.
</div>
<div style="margin-bottom: 18px;">
<strong>Evidence:</strong>
<ul>
	<li>Pong Game: Drawing paddles, ball, and background</li>
	<li>Snake Game: Drawing snake and food</li>
</ul>
</div>

### GameEnv Configuration

<div style="margin-bottom: 12px;">
<strong>What was learned:</strong> Game environment configuration means setting up things like canvas size, difficulty, and other options before the game starts. This helps make games flexible and customizable for different players. Using config objects in Pong and homeworks showed how to organize and manage game settings.
</div>
<div style="margin-bottom: 18px;">
<strong>Evidence:</strong>
<ul>
	<li>Pong Game: Config object for game settings</li>
	<li>Homeworks: <a href="{{site.baseurl}}/localStorage">Local Storage Demo</a></li>
</ul>
</div>

### API Integration & Async I/O

<div style="margin-bottom: 12px;">
<strong>What was learned:</strong> APIs let our programs talk to other systems, like leaderboards or AI, using network requests. Async I/O with <code>fetch</code>, <code>async/await</code>, and promises helps us handle data that arrives later. Practicing API calls in homeworks showed how to connect games to the web and handle real-time data.
</div>
<div style="margin-bottom: 18px;">
<strong>Evidence:</strong>
<ul>
	<li>Homeworks: <a href="{{site.baseurl}}/js/json">JSON Homework</a></li>
</ul>
</div>

---


---

<h3>Coderunner/Gamerunner Example</h3>
<div style="margin-bottom: 18px;">
<em>Below is a Gamerunner widget showing how input/output is used in Pong. Try changing the code to see how keyboard and canvas interactions work!</em>
</div>
{% include runners/game.html runner_id="pong-io-demo" challenge="Show I/O in Pong" code="// Example: keyboard and canvas\nconst canvas = document.getElementById('gameCanvas');\nconst ctx = canvas.getContext('2d');\nlet y = 50;\ndocument.addEventListener('keydown', e => {\n  if (e.key === 'ArrowDown') y += 10;\n  if (e.key === 'ArrowUp') y -= 10;\n  ctx.clearRect(0,0,canvas.width,canvas.height);\n  ctx.fillStyle = '#FF8C00';\n  ctx.fillRect(30, y, 40, 40);\n});\nctx.fillStyle = '#FF8C00';\nctx.fillRect(30, y, 40, 40);" %}

