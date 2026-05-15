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
{% include runners/game.html runner_id="pong-oop-demo" challenge="Show OOP in Pong" code="// Simple Paddle class example\nclass Paddle {\n  constructor(x, y) {\n    this.x = x;\n    this.y = y;\n    this.width = 10;\n    this.height = 60;\n  }\n  draw(ctx) {\n    ctx.fillStyle = '#327FC7';\n    ctx.fillRect(this.x, this.y, this.width, this.height);\n  }\n}\n\n// Create and draw a paddle\nconst canvas = document.getElementById('gameCanvas');\nconst ctx = canvas.getContext('2d');\nconst paddle = new Paddle(30, 50);\npaddle.draw(ctx);" %}

