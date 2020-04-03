# 2D Graphics in Godot

Godot has tons of functionality, but the core is just rendering sprites. The hard
part of this "easy-to-learn" engine is cutting through all of the advanced
features I don't need to get to the basics.

Let's talk about some good old-fashined pizel pushing in Godot!

## Image files
Godot supports multiple formats. For the kinds of old-school 2D, turn-based games
that I want to write, PNG is the way to go.

When you create a project in the Godot editor, you define a project directory.
Anything that you put into that directory in the filesystem shows up in the
editor automatically, ready to load and use.

## Godot _really_ wants to filter your images!

If you're making pixel graphics, you're likely to be dismayed when you try to
load your carefully-crafted sprites into the editor. They'll show up all fuzzy
and crappy looking.

Godot wants to apply a smoothing filter to everything it gets its virtual hands on.
To make matters worse, when you look at your `Sprite` object in the **Inspector**
panel in the editor, you'll find a couple of different properties for filtering
that appear to be disabled by default. What gives?!

I searched online for the answer, and found several references to image loader
properties in the project settings. This section no longer exists in version 3.2.
Instead, they've moved this to what I can only assume they thought was a more
intuitive spot in an **Import** tab behind the **Scene** tab.

Online sources indicate that the import settings are global, but the current
version seems to have fixed that to make them per image. Of course, this means
that every new image defaults to flitered.

<table>
  <tr>
    <td> <b>Important</b>: You must click the <b>Reimport</b> button at the bottom
         of the <b>Import</b> panel to apply your changes.
    </td>
  </tr>
</table>

<!--
----|----10---|----20---|----30---|----40---|----50---|----60---|----70---|----80
-->
