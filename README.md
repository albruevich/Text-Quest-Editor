[English](README.md) | [Українська](README.uk.md) | [Русский](README.ru.md)

# Text Quest Editor

![Engine](https://img.shields.io/badge/engine-Unity-000000?logo=unity&logoColor=white)
![Language](https://img.shields.io/badge/language-C%23-blue)
![Format](https://img.shields.io/badge/data-JSON-orange)

**Text Quest Editor** allows you to create and use text quests inspired by the mechanics of games like "Space Rangers".

The editor is distributed as ready-made builds for Windows, macOS, and Linux platforms.

Ready-made quests can be:
- launched directly in **Text Quest Editor** for testing,
- or connected to the project [**Text Quest Reader**](https://github.com/albruevich/Text-Quest-Reader).

**Text Quest Reader** is an open-source solution and allows you to:
- see and understand how the quest works,
- use its code in your own projects,
- customize the UI for your own tasks.

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
4. Add one more location
5. Connect them with a transition
6. Press Play

Done — you have your first working quest.

---

## Creating a New Quest

To create a new quest:
1. Click the button <img src="docs/btn_new.webp" width="30">
2. Enter the quest name and click **Accept**
3. The quest name is used as its ID and, unlike Display Name, cannot be changed
4. The quest name must match the folder name (this happens automatically when creating it — it is important not to change it manually)

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
1. Click the quest loading button <img src="docs/btn_load.webp" width="30">
2. Click the **Open folder** button — the `Quests` folder will open
3. Place the downloaded and unpacked quests into this folder
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

A quest is a folder whose name matches the name of your quest.

Inside it there are:
- the main file `quest.json`
- the `Images` folder
- the `Sounds` folder
- the `Musics` folder

All these folders and the `quest.json` file are created automatically when creating a quest.

After adding the quest to Text Quest Reader, the structure in Unity should look like this:

<img src="docs/quest_structure.webp" width="480">

---

## Core Idea

Creating a quest is built on three key elements: parameters, locations, and transitions.

1. Creating and editing parameters
2. Creating and editing locations
3. Creating and editing transitions between locations
4. The influence of locations and transitions on parameters
5. Conditions for displaying transitions depending on parameters

---

[↑ Back to Contents](#contents)

---

## Parameters

It is recommended to start creating a quest by setting up several key parameters, for example: gold, health, mood.

#### 1. Creating a Parameter

1. Click the button <img src="docs/btn_params.webp" width="30">
2. Click the field to the left of “Add parameter” <img src="docs/box_add_param.webp" width="164">
3. Specify **Working title** (a working name, not displayed in the game)

---

#### 2. Parameter Values

Each parameter has:
- a minimum value,
- a maximum value,
- a starting value.

Set them and click the **Apply** button.

<img src="docs/param_panel_1.webp" width="680">

---

#### 3. Parameter Display

Parameters can be displayed in different ways.

In this example, display ranks are configured (3 levels):
- if Mood = 1 → this will be shown: *You are furious*
- if Mood = 2 → this will be shown: *Normal mood*

<img src="docs/param_panel_2.webp" width="680">

---

If you want to display the numeric value of a parameter, use `<>` — during the game it will be replaced with the current value:

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

Parameters can be of three types: **Normal**, **Successful**, **Failed**

- **Normal** — does not affect quest completion  
- ** Successful** — completes the quest with victory when a critical value is reached  
- ** Failed** — completes the quest with defeat when a critical value is reached  

For example: if the gold parameter reaches 10, the quest ends with victory.

<img src="docs/param_types.webp" width="680">

*(For critical values you can also set images and sounds — this will be explained later.)*

---

#### 5. Disabling a Parameter

You can disable a parameter by unchecking the box to the left of it.

In this case, the parameter will not be used in the quest.

<img src="docs/param_disable.webp" width="159">

---

[↑ Back to Contents](#contents)

---

## Quest Settings

To open the quest settings:
1. Click the button <img src="docs/btn_params.webp" width="30">
2. Go to the **Quest settings** tab

Here you configure the quest parameters that are displayed in **Text Quest Reader** when selecting it:

1. Display Name  
2. Start Music  
3. Start Image  
4. Quest Description

<img src="docs/quest_settings.webp" width="680">

---

## Modes

The editor has three main modes: location mode, transition mode, and movement mode.

<img src="docs/modes.webp" width="177">

1. **Location Mode**  
   When you left-click on the working area (grid), the panel for creating a new location opens.

2. **Transition Mode**  
   Left-click the first location, then the second one. After that, the transition creation panel will open.  
   *Note: you can create a transition that leads to the same location from which it starts.*

3. **Movement Mode**  
   - Left-click on a location allows you to move it to a free cell.  
   - Left-click on a transition allows you to change its position between locations.  
     In this case, it is important where the first click was made — at the beginning (tail) or at the end (head) of the transition.


---

### Right Click

1. Right-click on a location or transition opens their editing panel.
2. In transition mode, if the starting location has already been selected, right-click cancels transition creation.

---

### Undoing Actions

If you made a mistake, use these buttons to undo the last action (Undo) or to perform it again (Redo).

<img src="docs/undo.webp" width="64">

---

## Locations

To open the location editing panel:
- right-click on an existing location,  
- or left-click on an empty cell in location mode.

The editing or creation panel for a location will open.

<img src="docs/edit_location.webp" width="680">

#### 1. Location Descriptions

In the main text field, you can edit the location description.

One location can have several descriptions.  
To add a new description, click the “Add” button.  
To select a description, use the dropdown list:

<img src="docs/loc_descr_1.webp" width="164">

Descriptions can be deleted.

<img src="docs/loc_descr_2.webp" width="444">

If the “Select in order” checkbox is enabled, descriptions will be shown one after another.

If the “Select by formula” checkbox is enabled, the description will be selected based on a formula.

For example:  
`p1 > 5 ? 1 : 2`  
If p1 (gold) is greater than 5 — description №1 will be shown, otherwise — №2.

<img src="docs/loc_descr_3.webp" width="338">

Another example:  
`p2 + 1`

The formula returns the description number.

- If the player has a pistol (p2 = 1), the result will be 2 — description №2 will be shown.  
- If there is no pistol (p2 = 0), the result will be 1 — description №1 will be shown.


**Descriptions can contain parameters and formulas.**

For example:  
`You are so tired today, your health is somewhere around {p3}`  
In the game it will be shown as:  
`You are so tired today, your health is somewhere around 7`

Or:  
`He gave you exactly half of his money: {p1 / 2}`


#### 2. Location Types

Locations can have different types: **Neutral, Start, Victory, Fail, Empty**.

<img src="docs/loc_types.webp" width="173">

**Neutral** — does not affect the course of the game by itself.

**Start** — the quest starts from this location. There can only be one start location in a quest.

**Victory** — when entering this location, the quest ends with victory.

**Fail** — when entering this location, the quest ends with defeat.

**Empty** — if a location has this type, its description is not displayed. Instead, the description of the transition that led to this location is shown.

#### 3. Visit Limit

You can limit the number of visits to a location.

By default, a location has unlimited visits — the player can visit it any number of times.

<img src="docs/loc_pass_1.webp" width="184">

To set a limit:
- uncheck the “Unlimited visits” checkbox,  
- specify the maximum number of visits.

After reaching the limit, the location will no longer be available (the transition to it will not be shown).

For example: the player can visit a friend 3 times, and on the 4th time the location will no longer appear (the friend went on vacation).

<img src="docs/loc_pass_2.webp" width="199">

This mechanism is also convenient for creating one-time locations.

#### 4. Influence of a Location on Parameters

When entering a location, it can change the player's parameters.

To do this, select the required parameter:

<img src="docs/loc_infl_to_param.webp" width="680">

---

**Actions**

A location can:
- **show a parameter** — it will be displayed in the game,
- **hide a parameter**,  
- **do nothing** (default value).

---

**Influence on Parameter Values**

4 modes are available: **Units**, **Value**, **Percent**, **Expression**

**Units**  
Changes the value of a parameter by the specified number (adds or subtracts).  
Example: there were 2 gold, +3 is specified → it will become 5 (taking into account the minimum and maximum value).

**Value**  
Sets the exact value of a parameter.  
Example: there were 2 gold, 0 is set → the player no longer has gold.

**Percent**  
Changes the value of a parameter by the specified percentage.  
Example: there were 10 gold, -50% is specified → it will become 5.

**Expression**  
Sets the value of a parameter using a formula.

Example:

p1 + (p11 == 0 ? -2 : 0)

- `p1` — oxygen  
- `p11` — breach (0 — not fixed)

If the breach is not fixed, oxygen decreases by 2.

Another example:

(p2 + p5) / 2

- `p1` — gold  
- `p2` — working hours  
- `p5` — bonus  

In this case, gold becomes the average value between working hours and the bonus.

---

**Random**

Formulas support random values.

Example:

p9 - rnd(1, 3)

- `p9` — monster health  

When shooting, the health is reduced by a random number from 1 to 3.

---

[↑ Back to Contents](#contents)

---

## Transitions

Transitions are very similar to locations: they can also have visit limits, show or hide parameters, and affect their values.  
These mechanisms work in the same way, so they are not repeated here.

<img src="docs/edit_trans.webp" width="680">

---

**Main Differences**

- A transition always has only one description.
- Transition button text is required.

<img src="docs/trans_btn_text.webp" width="288">

In the game it looks like this:

<img src="docs/trans_btn_view.webp" width="215">

---

**Conditions for Displaying a Transition**

Whether a transition will be shown depends on several conditions:

### 1. Logical condition

<img src="docs/trans_logical_condition.webp" width="277">

Sets a formula under which the transition is shown.  
For example: the transition will be shown only if there is more than 3 gold.

---

### 2. Range

<img src="docs/trans_range.webp" width="239">

The transition is shown if the parameter value is within the specified range.  
For example: from 1 to 4 gold.

---

### 3. Accepts / does not accept values

<img src="docs/trans_accepts.webp" width="241">

The transition is shown if the parameter accepts (or does not accept) the specified values.  
For example: p1 (gold) equals 1, or (apples - 2), or a random number from 3 to 10.

---

### 4. Divisibility

<img src="docs/trans_div.webp" width="239">

The transition is shown if the parameter value is divisible (or not divisible) by the specified values.

---

### 5. Important

The transition will be shown **only if all conditions are met at the same time**:
- Logical condition  
- Range  
- Accepts / does not accept values  
- Divisibility  

It is recommended to start with one condition so as not to complicate the logic and not get confused while testing the quest.

---

### 6. Display Order

If there are several transitions, they can be shown in different order.

<img src="docs/trans_order_1.webp" width="274">

The order is set through the **Display order** parameter:
- the smaller the value, the higher the button is in the list,
- if the values are the same — the order is determined randomly.

<img src="docs/trans_order_2.webp" width="127">

---

### 7. Priority

A quest can contain transitions with the same button text. Such transitions are called **conflicting** and are highlighted in red.

For example: two transitions “Run from the monster to the technical sector”  
— one leads to rescue, the other to defeat.

<img src="docs/trans_prior_1.webp" width="551">

The selection probability is determined by priority (weight):
- the higher the value, the higher the chance of displaying that transition.

<img src="docs/trans_prior_2.webp" width="219">

For example:
- chance of rescue = 3  
- chance of death = 7  
→ 30% and 70%

There are also probabilistic transitions (not conflicting).  
For them, a value from 0 to 1 is used:
- 0.5 = 50% chance of appearing.

---

### 8. Grey (inactive) transitions / Always show

If the transition conditions are not met, it may not be displayed.  
However, you can enable the “Always show” option to display such transitions as inactive.

<img src="docs/trans_always_show_1.webp" width="390">

For example: the path to the Medbay or the emergency section is closed (conditions are not met), but the transition is still shown in grey.

This allows you to:
- give the player hints,
- create a sense of choice,
- encourage them to look for a solution.

<img src="docs/trans_always_show_2.webp" width="137">

---

[↑ Back to Contents](#contents)

---

## Working with Resources

In locations, transitions, and critical parameters, you can use resources (images, music, and sounds) through special tags.

**Resource tags:**

- Images:  
  `<im your_beautiful_picture im>`

- Music:  
  `<mu your_music mu>`

- Sounds:  
  `<so your_sound so>`

---

After adding the tags, you need to place the corresponding files into the quest folder.

To open the quest folder:
- click the quest save button,
- then select **Open folder**.

A folder with the required structure will open:

<img src="docs/res_folders.webp" width="358">

---

**File formats:**

- Images: `.png`, `.jpg`, `.jpeg`  
- Sounds: `.mp3`, `.wav`, `.ogg`

---

**Usage Examples:**

<img src="docs/res_tags_1.webp" width="680">

<img src="docs/res_tags_2.webp" width="680">

---

**Refreshing Resources**

The editor uses resource caching.  
After changing files in the folders, you need to refresh them manually.

To do this, click the corresponding refresh buttons:

<img src="docs/res_cache.webp" width="225">

Or restart the editor — this will also apply all changes.


---

## Game Mode

To launch and debug the quest, click the button:

<img src="docs/btn_play.webp" width="36">

In game mode, you can:
- complete the quest from beginning to end,
- temporarily set parameters for testing,
- rewind the playthrough back.

---

## Misc

You can enable or disable hints — the text at the top of the screen that reminds you of the current mode.

If hints are enabled:
- when hovering over locations and transitions, tooltips with information are displayed.

You can also enable or disable the grid display:

<img src="docs/grid_n_hints.webp" width="60">

You can open a short mouse control reference using the button:

<img src="docs/btn_info.webp" width="32">

Transitions have visual differences:
- tail (from) — blue and wide,
- head (to) — white and narrow.

<img src="docs/trans_view.webp" width="360">

---

## Tips

Do not start with a complex quest right away.

It is recommended to first create a small quest (5–10 locations) in order to:
- learn the editor’s basic capabilities,
- understand the system logic,
- avoid typical mistakes in the future.

After that, it will be much easier to move on to more complex scenarios.


---

[↑ Back to Contents](#contents)
