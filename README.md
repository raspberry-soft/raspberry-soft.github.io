# Scripting Guide

## General Notes

- Lines of dialogue are placed inside `""` quotations. If you want to use quotations inside the dialogue use `''`.

```renpy
"Dialogue line."

"Dialogue line with a 'quotation'"
```

- Each line of text should be limited to approximately 75 characters long. You can do longer lines if there's no other option, but note that readers usually skip long lines of text.
- You can make comments for me in the script by prefacing it with `# TODO`:

```renpy
"Dialogue line" # TODO Please revise this line.
```

- You can use the following symbols: `{heart}`, `{music}`.

```renpy
"Bye, dear. {heart}"  # Note: An image of a heart (❤️) appears.

"What a good day, la la la. {music}." # Note: An image of a music note (🎵) appears.
```

- Everything is case-sensitive. `Aiko` and `aiko` are not the same.
- Use honorifics, for example: `Aiko-chan`

## Scene Title / Organization

For easy script navigation for us and the readers, each scene must begin with a title and a short description of what is about.
That should be placed at the very top of the scene as a comment (using `#`), like this:

```renpy
# Title (Use Title Case)

# Description
```

Example:

```renpy
# Couple Conversation

# Aiko and Hitoshi have a pleasant conversation.
```

## Location / Time

Each time the location or time changes, write: `scene bg <location> <time>`.

In the background folder, you'll find available locations. Names should exactly match.
The time of day available to choose are: `morning`, `afternoon`, `night`.
Example of 3 different scenes:

```renpy
scene bg home bedroom morning  # Note: "bedroom" is the location and "morning" is the time.
```
```renpy
scene bg home front afternoon  # Note: "home front" is the location and "afternoon" is the time.
```
```renpy
scene bg office boss night  # Note: "office boss" is the location and "night" is the time.
```

## Character entering the scene

Each time a character appears on a new scene, write: `show <character> <outfit> <expression>`.

The list of characters available as sprites are: `aiko` and `ryou`.
The list of available outfits and expressions are on the respetive character folders.
> Note: The main character has no full-body sprite image. It has a side image that don't need to be scripted to be shown. To make it appear, he have to talk or think using an expression.

```renpy
show aiko indoor smiling  # Note: Makes Aiko appear wearing the "indoor" outfit and making the "smiling" expression.
```
```renpy
show ryou uniform angry  # Note: Makes Ryou appear wearing the "uniform" outfit and making the "angry" expression.
```
```renpy
mc smiling "Hi guys! I'm just a side image!"  # Note: Makes the main character side image appear.

mct smiling "Thinking makes me appear too!"  # Note: Also makes the main character side image appear.
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

Same as above, but instead of the codename `mc`, use the codename `mct`, which stands for Main Character Thinking.
This will show a side image of the character while thinking, so you are able to specify an expression.

```renpy
mc smiling "I'm talking while smiling."

mct worried "Now I look worried but only talking to myself."
```

## Main character narrating

The novel is first-person. If you want the main character to narrate events without showing his face (side image), write the text inside `""` quotations, without any codename."

```renpy
"I'll always remember her..."
```

## Event CG illustration

A CG illustration event is a special case. The differences are:
- Sprite images don't appear. All characters and expressions comes from the illustration and thus vary.
- The CG events are planned and agreed ahead of time. If available, you'll have the actual image files. If not, I'll describe it to you.
- When writing an event, the main character should describe the image presented to him.
- Use `scene cg <event name> <variation>` to begin the scene:
- Use `show cg <variation>` to switch between expressions or any other variation. Note that the `event name` is no longer needed.

```renpy
scene cg s3xwithaiko screaming

a "Ahhh!"

show cg smiling

a "I'm smiling."

```

# Script Examples

## Normal Scene

```renpy

# Couple Conversation

# Aiko and Hitoshi have a pleasant conversation.

scene bg livingroom afternoon

"Another typical murky day passing by..."  # MC narrating (No side image is shown)

mct worried "I wonder when things started to get this stale..." # MC thinking while showing an expression.

show aiko underwear smiling

mc surprised "A-Aiko-chan..."

a smiling "Hmmm? Yes?"

mc worried "I-I was just thinking, I know nowadays I have been held up with unexpected overtime from work, never really having the time to pay attention to you... and today being one of the only few days where I get an off..."  # This sentence is way too long. Divide it in two lines."

mc nervous "I was thinking! P-perhaps there's something you'd like to do today...?"

a worried "Oh my, Hmmmm... I don't really have anything I specifically want to do today Tatsuya-kun."

mc "E-eh?! Nothing at all?"

a "Mhmmm."

mc sad "A-ah... I see... Alright... (sigh)"

a lusting "Ehehe. Honey..."
```

## Event Scene

```renpy

# Married s3x

# Aiko and Hitoshi have s3x but something feels off.

scene cg s3xwithaiko screaming

a "Ahhh!"

show cg smiling

a "I'm smiling."
```
