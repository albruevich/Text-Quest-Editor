[English](README.md) | [Українська](README.uk.md) | [Русский](README.ru.md)

# Text Quest Editor

![Engine](https://img.shields.io/badge/engine-Unity-000000?logo=unity&logoColor=white)
![Language](https://img.shields.io/badge/language-C%23-blue)
![Format](https://img.shields.io/badge/data-JSON-orange)

**Text Quest Editor** allows you to create and use text quests inspired by mechanics of games like "Space Rangers".

The editor is distributed as ready-made builds for Windows, macOS and Linux platforms.

Ready quests can be:
- launched directly in **Text Quest Editor** for testing,
- or connected to the project [**Text Quest Reader**](https://github.com/albruevich/Text-Quest-Reader).

**Text Quest Reader** is an open-source solution and allows you to:
- see and understand how the quest works,
- use its code in your own projects,
- customize the UI for your needs.

Quests are created and stored in JSON format, which makes the combination of **Text Quest Editor** and **Text Quest Reader (open-source)** a universal solution for using text quests in any projects.

---

## Contents

- [Quick Start](#quick-start)
- [Creating a New Quest](#creating-a-new-quest)
- [Loading a Quest](#loading-a-quest)
- [Saving a Quest](#saving-a-quest)
- [Example Quests](#viewing-example-quests)
- [Adding to Text Quest Reader](#adding-a-quest-to-text-quest-reader)
- [Quest Structure](#quest-structure)
- [Core Idea](#core-idea)
- [Parameters](#parameters)
- [Quest Settings](#quest-settings)
- [Modes](#modes)
- [Locations](#locations)
- [Transitions](#transitions)
- [Working with Resources](#working-with-resources)
- [Game Mode](#game-mode)
- [Misc](#misc)
- [Tips](#tips)

---

## Quick Start

1. Create a new quest
2. Add 1–2 parameters (for example: gold)
3. Create a starting location
4. Add another location
5. Connect them with a transition
6. Press Play

Done — you have your first working quest.

---

## Creating a New Quest

To create a new quest:
1. Click the button <img src="docs/btn_new.webp" width="30">
2. Enter the quest name and click **Accept**
3. The quest name is used as its ID and, unlike Display Name, cannot be changed
4. The quest name must match the folder name (it is done automatically on creation — it is important not to change it manually)

---

## Loading a Quest

1. Click the button <img src="docs/btn_load.webp" width="30">
2. Select the required quest
3. Click the **Load** button

---

## Saving a Quest

1. Click the button <img src="docs/btn_save.webp" width="30">
2. Click the **Save** button
3. You can also use hotkeys:
   - **Ctrl + S** (Windows)
   - **Cmd + S** (macOS)

---

## Viewing Example Quests

The repository contains [ready-made quests](https://github.com/albruevich/QuestEditor_Builds/tree/main/Quests)

To add them to the editor:
1. Click the load quests button <img src="docs/btn_load.webp" width="30">
2. Click the **Open folder** button — the `Quests` folder will open
3. Place downloaded and unpacked quests into this folder
4. Close and reopen the quest loading panel to refresh the list

---

## Adding a Quest to [Text Quest Reader](https://github.com/albruevich/Text-Quest-Reader)

To use your quest in **Text Quest Reader**:
1. Click the quest save button <img src="docs/btn_save.webp" width="30">
2. Click the **Open folder** button — the `Quests/YourQuest` folder will open, copy it
3. Open the **Text Quest Reader** project in Unity
4. Paste the quest folder into: `Assets/Resources/Quests/`
5. Add the quest folder name to `Assets/_Settings/Quest Folders List`
6. Click the **Run** button — the quest will appear in the list of available ones

---

## Quest Structure

A quest is a folder that matches the name of your quest.

Inside it there are:
- main file `quest.json`
- `Images` folder
- `Sounds` folder
- `Musics` folder

All these folders and the `quest.json` file are created automatically when creating a quest.

After adding the quest to Text Quest Reader, the structure in Unity will look like this:

<img src="docs/quest_structure.webp" width="480">

---

## Core Idea

Creating a quest is based on three key elements: parameters, locations and transitions.

1. Creating and editing parameters
2. Creating and editing locations
3. Creating and editing transitions between locations
4. Influence of locations and transitions on parameters
5. Conditions for displaying transitions depending on parameters

---

[↑ Back to Contents](#contents)

---

## Parameters

It is recommended to start creating a quest by setting up several key parameters, for example: gold, health, mood.

#### 1. Creating a Parameter

1. Click the button <img src="docs/btn_params.webp" width="30">
2. Click the field to the left of “Add parameter” <img src="docs/box_add_param.webp" width="164">
3. Specify **Working title** (working name, not displayed in the game)

---

#### 2. Parameter Values

Each parameter has:
- minimum value,
- maximum value,
- starting value.

Set them and click the **Apply** button.

<img src="docs/param_panel_1.webp" width="680">

---

#### 3. Parameter Display

Parameters can be displayed in different ways.

In this example, rank display (3 levels) is configured:
- if Mood = 1 → will be shown: *You are furious*
- if Mood = 2 → will be shown: *Normal mood*

<img src="docs/param_panel_2.webp" width="680">

---

If you want to display a numeric value of a parameter, use `<>` — during the game it will be replaced with the current value:

<img src="docs/param_outlook_1.webp" width="301">

In the game it looks like this:

<img src="docs/param_outlook_2.webp" width="180">

---

You can also use values of other parameters.

For example, to display the score between teams:

<img src="docs/param_outlook_3.webp" width="680">

In the game it looks like this:

<img src="docs/param_outlook_4.webp" width="159">

---

If the display field is left empty, the parameter will not be shown in the game:

<img src="docs/param_outlook_5.webp" width="680">

---

#### 4. Parameter Type

Parameters can be of three types: **Normal**, **Success**, **Fail**

- **Normal** — does not affect quest completion  
- **Success** — completes the quest with victory when a critical value is reached  
- **Fail** — completes the quest with defeat when a critical value is reached  

For example: if the gold parameter reaches 10, the quest ends with victory.

<img src="docs/param_types.webp" width="680">

*(For critical values you can also set images and sounds — this will be described later.)*

---

#### 5. Disable Parameter

You can disable a parameter by unchecking the checkbox to the left of it.

In this case, the parameter will not be used in the quest.

<img src="docs/param_disable.webp" width="159">

---

[↑ Back to Contents](#contents)

---

## Quest Settings

To open quest settings:
1. Click the button <img src="docs/btn_params.webp" width="30">
2. Go to the **Quest settings** tab

Here you configure quest parameters that are displayed in **Text Quest Reader** when selecting it:

1. Display Name  
2. Start Music  
3. Start Image  
4. Quest Description  

<img src="docs/quest_settings.webp" width="680">

---

## Modes

The editor has three main modes: location mode, transition mode and movement mode.

<img src="docs/modes.webp" width="177">

1. **Location Mode**  
   Left click on the workspace (grid) opens the panel for creating a new location.

2. **Transition Mode**  
   Left click the first location, then the second. After that, the transition creation panel will open.  
   *Note: you can create a transition that leads to the same location it starts from.*

3. **Movement Mode**  
   - Left click on a location allows you to move it to a free cell.  
   - Left click on a transition allows you to change its position between locations.  
     It is important where the first click was made — at the start (tail) or at the end (head) of the transition.

---

### Right Click

1. Right click on a location or transition opens its editing panel.
2. In transition mode, if the starting location is already selected, right click cancels transition creation.

---

### Undo Actions

If you made a mistake, use these buttons to undo the last action (Undo) or redo it (Redo).

<img src="docs/undo.webp" width="64">

---

## Locations

To open the location editing panel:
- right click on an existing location,
- or left click on an empty cell in location mode.

The location editing or creation panel will open.

<img src="docs/edit_location.webp" width="680">

#### 1. Location Descriptions

In the main text field you can edit the location description.

A location can have multiple descriptions.  
To add a new description, click the “Add” button.  
To select a description, use the dropdown:

<img src="docs/loc_descr_1.webp" width="164">

Descriptions can be deleted.

<img src="docs/loc_descr_2.webp" width="444">

If the “Select in order” checkbox is enabled, descriptions will be shown one by one.

If the “Select by formula” checkbox is enabled, the description will be selected based on a formula.

Example:  
`p1 > 5 ? 1 : 2`

If p1 (gold) is greater than 5 — description №1 will be shown, otherwise — №2.

<img src="docs/loc_descr_3.webp" width="338">

Another example:  
`p2 + 1`

The formula returns the description number.

- If the player has a gun (p2 = 1), the result will be 2 — description №2 is shown.  
- If there is no gun (p2 = 0), the result will be 1 — description №1 is shown.

**Descriptions can contain parameters and formulas.**

Example:  
`You are so tired today, your health is somewhere around {p3}`  

In the game it will be:  
`You are so tired today, your health is somewhere around 7`

Or:  
`He gave you exactly half of his money: {p1 / 2}`

---

#### 2. Location Types

Locations can have different types: **Neutral, Start, Victory, Fail, Empty**

<img src="docs/loc_types.webp" width="173">

**Neutral** — does not affect gameplay by itself  

**Start** — the quest begins from it. There can be only one start location in a quest  

**Victory** — entering this location ends the quest with victory  

**Fail** — entering this location ends the quest with defeat  

**Empty** — if a location has this type, its description is not shown. Instead, the description of the transition that led to this location is shown  

---

#### 3. Visit Limit

You can limit the number of visits to a location.

By default, a location has unlimited visits.

<img src="docs/loc_pass_1.webp" width="184">

To set a limit:
- uncheck “Unlimited visits”  
- set the maximum number of visits  

After reaching the limit, the location becomes unavailable.

---

#### 4. Parameter Influence

When entering a location, it can change player parameters.

Modes:
- Units  
- Value  
- Percent  
- Expression  

Random supported:
`rnd(1, 3)`

---

[↑ Back to Contents](#contents)

---

## Transitions

Transitions are similar to locations.

---

### Key Differences

- Only one description  
- Button text is required  

---

### Conditions

1. Logical condition  
2. Range  
3. Accepts values  
4. Divisibility  

All conditions must be met.

---

### Display Order

Lower value → higher in the list.

---

### Priority

Higher value → higher chance.

---

### Always Show

Transitions can be shown disabled (grey).

---

[↑ Back to Contents](#contents)

---

## Working with Resources

Tags:

- Images: `<im ... im>`  
- Music: `<mu ... mu>`  
- Sounds: `<so ... so>`

---

Place files in quest folder.

Formats:
- Images: `.png`, `.jpg`, `.jpeg`  
- Sounds: `.mp3`, `.wav`, `.ogg`

---

Refresh resources manually or restart the editor.

---

## Game Mode

Click Play.

You can:
- complete the quest  
- set parameters  
- rewind  

---

## Misc

- Hints  
- Grid  
- Mouse help  

---

## Tips

Do not start with a complex quest.

Start with 5–10 locations.

Then scale.

---

[↑ Back to Contents](#contents)