# HowTo 2D Games

One of the drawbacks of Godot, and many other modern, general use game engines, is
that there are so many features that just aren't relevant to the kinds of simple,
2D games that I want to make. This topic is for notes about how to actually make
the kinds of games I want, cutting through the fog of all the other features and
whatnot.

What kinds of games am I talking about? For the most part, what I need is:

-   Simple sprite handling
-   Collision detection
-   Animation
-   Tile map backgrounds

Which means all the stull to support physics and kinematics and particle effects,
and so on are just needless confusion for me.

## To create sprites

1.  Create an _Area2D_ node to be the character scene.
2.  Create a child node _AnimatedSprite_ to handle the sprite animation.

    -   You can add multiple animations to this node to cover different actions
        and situations.
    -   When you use this arrangement, the parent _Area2D_ node doesn't need to
        have any texture applied.

3.  Create a _CollisionShape2D_ node, also as a child of your _Area2D_ node.

    -   You can use a different collision node if it makes sense for the
        situation.

<!--
----|----10---|----20---|----30---|----40---|----50---|----60---|----70---|----80
-->
