# Godot Nodes

Nodes are Godot classes. They're called nodes because the whole system is
conceptually designed as a tree structure, where the game is the parent node and
all the game objects are nodes arranged in nested trees within it.

When you create a script for a node, you are creating a inherited class. Here's
an example:

```
extends Area2D

# Player speed in pixels per second
export var speed = 400

# Size of the game window
var screen_size

# _ready is an initialization function that gets called when an instance of the
#  node is added to the tree.
func _ready():
    screen_size = get_viewport_rect().size
    
# _process is called for every active instance every frame of the game.
#  delta is the time elapsed since the last call to _process
func _process(delta):
    var velocity = Vector2()
    # Check for direction keys pressed
    if Input.is_action_pressed("ui_right"):
        velocity.x += 1
    if Input.is_action_pressed("ui_left"):
        velocity.x -= 1
    if Input.is_action_pressed("ui_down"):
        velocity.y += 1
    if Input.is_action_pressed("ui_up"):
        velocity.y -= 1
        
    if velocity.length() > 0:
        velocity = velocity.normalized() * speed
        $AnimatedSprite.play()
    else:
        $AnimatedSprite.stop()
```

The `export` keyword makes the property externally accessible. The immediate
benefit is that the Godot UI can access it, enabling you to change its value
from the inspector.

<!--
----|----10---|----20---|----30---|----40---|----50---|----60---|----70---|----80
-->
