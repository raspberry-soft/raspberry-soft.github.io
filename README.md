# Scripting Guide

## General Notes

- Each line of text should be limited to approximately 75 characters long. You can do longer lines if there's no other option, but note that readers usually skip long lines of text.
- You can make comments for me in the script by prefacing it with `# TODO`:
```renpy
"Dialogue line" # TODO Please revise this line.
```
- Everything is case-sensitive. `Aiko` and `aiko` are not the same.
- Use honorifics, for example: `Aiko-chan`

## Location / Time

Each time the location or time changes, write: `scene bg <location> <time>`.

In the background folder, you'll find available locations. Names should exactly match.
The time of day available to choose are: `morning`, `afternoon`, `night`.
Example of 3 different scenes:

```renpy
scene bg home bedroom morning
```
```renpy
scene bg home front afternoon
```
```renpy
scene bg office boss night
```

## Character entering the scene

Each time a character appears on a new scene, write: `show <name> <expression> <outfit>`.

The list of characters available as sprites are: `aiko` and `ryou`.
The list of available outfits and expressions are on the respetive character folders.

```renpy
show aiko uniform smiling
```
```renpy
show aiko nude playful
```

## Character speaking WITHOUT changing expressions

Write the codename of the character followed by the text inside `""` quotations.
Aiko codename is `a`.
The antagonist (Ryou) codename is `r`.
The main character codename is `mc`.

```renpy
a "I'm Aiko!"

r "I'm the antagonist!"

mc "I'm the main character!"
```

## Character speaking WHILE changing expressions

Write the expression after the codename, but before the text.
The list of all available expressions with the corresponding image is their respetive character folders. 

```renpy
a smiling "I'm happy!"

a angry "Now I'm angry!"

a "Still angry"  # Note: The character is talking without changing the previous expression.

a smiling "Happy again!"
```

## Main character thinking

Same as above, but instead of the codename `mc`, use the codename `mcn`, which stands for Main Character Narrating.
This will show a side image of the character while thinking, so you are able to specify an expression.

```renpy
mc smiling "I'm talking while smiling."

mcn worried "Now I look worried, but I'm quiet."
```
