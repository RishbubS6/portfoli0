---
layout: post
title: Object-Oriented Programming (OOP) Showcase
permalink: /cs111-oop
---

# Object-Oriented Programming (OOP)

OOP is about designing code using classes, objects, and inheritance. It helps organize code for games and applications, making it modular and reusable.

## Subrequirements

### Writing Classes

<div style="margin-bottom: 12px;">
<strong>What was learned:</strong> Classes are blueprints for creating objects, letting us organize code for different parts of a game or app. By defining custom classes, we can model things like paddles, balls, or players with their own properties and behaviors. In Pong and Snake, writing classes made it easier to manage game logic and reuse code.
</div>
<div style="margin-bottom: 18px;">
<strong>Evidence:</strong>
<ul>
  <li>Pong Game: Custom classes for Ball, Paddle, Game (<a href="{{site.baseurl}}/custompong">View Pong Game</a>)</li>
  <li>Snake Game: Game logic organized in functions and objects (<a href="{{site.baseurl}}/snake">View Snake Game</a>)</li>
</ul>
</div>

```javascript
// Example from Pong (hacks/pong.md)
class Paddle {
  constructor(x, y, width, height, speed, boundsHeight) {
    this.position = new Vector2(x, y);
    this.width = width;
    this.height = height;
    this.speed = speed;
    this.boundsHeight = boundsHeight;
  }
  // ...
}
```

### Methods & Parameters

<div style="margin-bottom: 12px;">
<strong>What was learned:</strong> Methods are functions inside classes that define what an object can do, and parameters let us pass in information. In Pong, methods like <code>handleCollision(other, direction)</code> let the ball and paddles react to game events. Using methods with parameters made our code flexible and easy to extend for new features.
</div>
<div style="margin-bottom: 18px;">
<strong>Evidence:</strong>
<ul>
  <li>Pong Game: Methods like <code>handleCollision(other, direction)</code> in Ball and Paddle classes.</li>
</ul>
</div>

### Instantiation & Objects

<div style="margin-bottom: 12px;">
<strong>What was learned:</strong> Instantiation means creating an object from a class, giving us a working game element with its own data. In Pong, we instantiate balls and paddles to bring the game to life. This process is key to building games with many interactive parts.
</div>
<div style="margin-bottom: 18px;">
<strong>Evidence:</strong>
<ul>
  <li>Pong Game: <code>new Ball(...)</code>, <code>new Paddle(...)</code> in game setup.</li>
</ul>
</div>

### Inheritance (Basic)

<div style="margin-bottom: 12px;">
<strong>What was learned:</strong> Inheritance lets us create new classes based on existing ones, sharing code and adding new features. For example, a Paddle class could extend a generic GameObject class to add paddle-specific logic. This makes our code more organized and easier to maintain as games grow.
</div>
<div style="margin-bottom: 18px;">
<strong>Evidence:</strong>
<ul>
  <li>Pong Game: Ball and Paddle could extend a base class (see code structure in <a href="{{site.baseurl}}/custompong">hacks/pong.md</a>).</li>
</ul>
</div>

### Method Overriding

<div style="margin-bottom: 12px;">
<strong>What was learned:</strong> Method overriding means redefining a method from a parent class in a child class to change its behavior. In Pong, we override <code>draw()</code> and <code>update()</code> to make each object act differently. This is a powerful way to customize how game elements work while keeping code organized.
</div>
<div style="margin-bottom: 18px;">
<strong>Evidence:</strong>
<ul>
  <li>Pong Game: Overriding <code>draw()</code> and <code>update()</code> methods in game classes.</li>
</ul>
</div>

### Constructor Chaining

<div style="margin-bottom: 12px;">
<strong>What was learned:</strong> Constructor chaining uses <code>super()</code> to call a parent class's constructor from a child class. This ensures all properties are set up correctly when creating new objects. In Pong, using <code>super()</code> helps us build complex objects from simple building blocks.
</div>
<div style="margin-bottom: 18px;">
<strong>Evidence:</strong>
<ul>
  <li>Pong Game: Example of constructor chaining in class definitions.</li>
</ul>
</div>

---


---

<h3>Coderunner/Gamerunner Example</h3>
<div style="margin-bottom: 18px;">
<em>Below is a Gamerunner widget showing how OOP is used in Pong. Try changing the code to see how classes and objects work in practice!</em>
</div>
{% include runners/game.html runner_id="pong-oop-demo" challenge="Show OOP in Pong" code="// Full Pong Game Example\nconst Config = {\n  canvas: { width: 400, height: 250 },\n  paddle: { width: 10, height: 60, speed: 7 },\n  ball: { radius: 8, speed: 5 },\n  rules: { winningScore: 3 },\n  keys: { p1Up: 'w', p1Down: 's', p2Up: 'ArrowUp', p2Down: 'ArrowDown' },\n  visuals: { bg: '#222', fg: '#fff', text: '#fff', win: 'yellow' }\n};\nclass Paddle {\n  constructor(x, y) { this.x = x; this.y = y; this.width = Config.paddle.width; this.height = Config.paddle.height; this.score = 0; }\n  draw(ctx) { ctx.fillStyle = Config.visuals.fg; ctx.fillRect(this.x, this.y, this.width, this.height); }\n  move(dy) { this.y += dy; this.y = Math.max(0, Math.min(this.y, Config.canvas.height - this.height)); }\n}\nclass Ball {\n  constructor() { this.reset(); }\n  reset() { this.x = Config.canvas.width/2; this.y = Config.canvas.height/2; this.vx = (Math.random() > 0.5 ? 1 : -1) * Config.ball.speed; this.vy = (Math.random()-0.5)*Config.ball.speed; }\n  draw(ctx) { ctx.beginPath(); ctx.arc(this.x, this.y, Config.ball.radius, 0, 2*Math.PI); ctx.fillStyle = Config.visuals.fg; ctx.fill(); }\n  update(p1, p2) { this.x += this.vx; this.y += this.vy; if (this.y < Config.ball.radius || this.y > Config.canvas.height-Config.ball.radius) this.vy *= -1; if (this.collides(p1)) { this.vx = Math.abs(this.vx); } if (this.collides(p2)) { this.vx = -Math.abs(this.vx); } if (this.x < 0) { p2.score++; this.reset(); } if (this.x > Config.canvas.width) { p1.score++; this.reset(); } }\n  collides(p) { return this.x - Config.ball.radius < p.x + p.width && this.x + Config.ball.radius > p.x && this.y > p.y && this.y < p.y + p.height; }\n}\nconst canvas = document.getElementById('gameCanvas');\ncanvas.width = Config.canvas.width;\ncanvas.height = Config.canvas.height;\nconst ctx = canvas.getContext('2d');\nconst p1 = new Paddle(10, Config.canvas.height/2-Config.paddle.height/2);\nconst p2 = new Paddle(Config.canvas.width-20, Config.canvas.height/2-Config.paddle.height/2);\nconst ball = new Ball();\nfunction draw() { ctx.fillStyle = Config.visuals.bg; ctx.fillRect(0,0,canvas.width,canvas.height); p1.draw(ctx); p2.draw(ctx); ball.draw(ctx); ctx.fillStyle = Config.visuals.text; ctx.font = '20px Arial'; ctx.fillText(p1.score, 80, 30); ctx.fillText(p2.score, canvas.width-100, 30); }\nfunction update() { ball.update(p1, p2); }\nfunction loop() { update(); draw(); if (p1.score < Config.rules.winningScore && p2.score < Config.rules.winningScore) requestAnimationFrame(loop); else { ctx.fillStyle = Config.visuals.win; ctx.font = '28px Arial'; ctx.fillText('Game Over!', canvas.width/2-70, canvas.height/2); } }\ndocument.addEventListener('keydown', e => { if (e.key === Config.keys.p1Up) p1.move(-Config.paddle.speed); if (e.key === Config.keys.p1Down) p1.move(Config.paddle.speed); if (e.key === Config.keys.p2Up) p2.move(-Config.paddle.speed); if (e.key === Config.keys.p2Down) p2.move(Config.paddle.speed); });\nloop();" %}

