[English](README.md) | [Українська](README.uk.md) | [Русский](README.ru.md)

# 🛠 **Text Quest Editor**

![Engine](https://img.shields.io/badge/engine-Unity-000000?logo=unity&logoColor=white)
![Language](https://img.shields.io/badge/language-C%23-blue)
![Format](https://img.shields.io/badge/data-JSON-orange)
![Web](https://img.shields.io/badge/web-supported-2ea44f)
![PWA](https://img.shields.io/badge/PWA-ready-5A0FC8)

🛠 **Text Quest Editor** is a tool for creating narrative quests and interactive stories inspired by games like *Space Rangers*.

The editor allows you to:
- create non-linear scenarios,
- use parameters, locations, transitions, and formulas,
- add images, music, and sounds,
- test quests directly inside the editor,
- publish quests remotely through a server.

The editor is distributed as ready-to-use builds for Windows and macOS.

---

## Contents

- [Text Quest Ecosystem](#text-quest-ecosystem)
- [Text Quest Reader](#text-quest-reader)
- [Quest Reader Web](#quest-reader-web)
- [Quick Start](#quick-start)
- [Ready Builds](#ready-builds)
- [Creating a New Quest](#creating-a-new-quest)
- [Loading a Quest](#loading-a-quest)
- [Local and Remote Quests](#local-and-remote-quests)
- [Local Quest Saving](#local-quest-saving)
- [Quest Examples](#quest-examples)
- [Adding a Quest to Text Quest Reader](#adding-a-quest-to-text-quest-reader)
- [Quest Structure](#quest-structure)
- [Core Idea](#core-idea)
- [Parameters](#parameters)
- [Main Quest Settings](#main-quest-settings)
- [Modes](#modes)
- [Locations](#editing-locations)
- [Transitions](#transitions)
- [Working with Resources](#working-with-resources)
- [Game Mode](#game-mode)
- [Miscellaneous](#miscellaneous)
- [Tips](#tips)

---

## Text Quest Ecosystem

The ecosystem includes:

- 🛠 **Text Quest Editor** — the editor for narrative quests and interactive stories.
- [**Text Quest Reader**](https://github.com/albruevich/Text-Quest-Reader) — an open-source Unity application.
- [**Quest Reader Web**](https://questreader.onrender.com) — the browser version of the reader.

All components use a unified JSON quest format, allowing the same quest to be created, published, and launched across different platforms.

---

## [**Text Quest Reader**](https://github.com/albruevich/Text-Quest-Reader)

Allows you to:
- launch quests through a ready-to-use desktop application,
- integrate the system into Unity projects,
- customize the interface and behavior for your own needs.

---

## [**Quest Reader Web**](https://questreader.onrender.com)

Allows you to launch quests directly in the browser and supports:
- quests published on the server,
- desktop and mobile devices,
- installation as a PWA application.

---

## Quick start

1. Create a new quest
2. Add 1–2 parameters (for example: gold)
3. Create a starting location
4. Add one more location
5. Connect them with a transition
6. Press Play

Done — you have your first working quest.

---

## Ready Builds

You can download them here:  
👉 [Text Quest Editor Releases](https://github.com/albruevich/Text-Quest-Editor/releases)

### How to Launch

1. Download the archive for your platform  
2. Extract it  
3. Windows: run the `.exe` file  
4. macOS: open the `.dmg` and move the application to Applications

---

## macOS Security Warning

If macOS blocks the application with a message like:

> “App cannot be opened because it is from an unidentified developer”

Do the following:

1. Open:
   `System Settings → Privacy & Security`

2. Scroll down to the security section

3. Press:
   **Open Anyway**

4. Confirm launching the application

After the first launch, the application will open normally.

---

## Creating a new quest

To create a new quest:
1. Press the button <img src="docs/btn_new.webp" width="30">
2. Enter the quest name and press **Accept**

---

## Loading a quest

1. Press the button <img src="docs/btn_load.webp" width="30">
2. Select the required quest
3. Press the **Load** button

---



## Local and remote quests

Two quest sources are available in the editor:

- **Local** — quests saved on your computer.
- **Remote** — quests loaded from the server.

In the loading panel, you can switch between local and remote quests.

If the server is unavailable, the **Remote** tab will be disabled.

Quests loaded from the server have a unique ID, which is displayed to the right of the name.

For example: `#1`

This ID is used to identify the quest on the server.

<table>
<tr>
<td>

<img src="docs/load_local.webp" width="250">

</td>
<td>

<img src="docs/load_remote.webp" width="250">

</td>
</tr>
</table>

---

Authorization is required to publish quests to the server.

After authorization:
- new quests can be published remotely,
- already published quests can be updated,
- your quests will be marked as belonging to you.

---

## Authorization

To open the authorization panel:
1. Press the **Auth** button
2. Register or log in to your account

<img src="docs/auth_register.webp" width="160">

After logging in, the following become available:
- publishing quests,
- updating remote quests,
- managing your own remote quests.

<img src="docs/auth_logged.webp" width="160">

---

## Local quest saving

Quests can be saved locally to your computer, including quests loaded from the server.

1. Press the button <img src="docs/btn_save.webp" width="30">
2. Press the **Save** button
3. You can also use hotkeys:
   - **Ctrl + S** (Windows)
   - **Cmd + S** (macOS)

---

## Example quests

Example [quests](https://github.com/albruevich/QuestEditor_Builds/tree/main/Quests) for local use are available in the repository.

To add them to the editor:
1. Press the quest loading button <img src="docs/btn_load.webp" width="30">
2. Press the **Open folder** button — the `Quests` folder will open
3. Put the downloaded and unpacked quests into this folder
4. Close and reopen the quest loading panel to refresh the list

---

## Adding a quest to [**Text Quest Reader**](https://github.com/albruevich/Text-Quest-Reader)

Quests can be used:
- in the Unity project [**Text Quest Reader**](https://github.com/albruevich/Text-Quest-Reader),
- or in the ready-to-use [**Text Quest Reader APP**](https://github.com/albruevich/Text-Quest-Reader/releases) for Windows and macOS.

To add a quest locally:

1. Press the quest save button <img src="docs/btn_save.webp" width="30">
2. Press the **Open folder** button — the `Quests/YourQuest` folder will open
3. Copy the quest folder

### Into the Unity project

1. Open the [**Text Quest Reader**](https://github.com/albruevich/Text-Quest-Reader) project in Unity
2. Paste the quest folder into:
   `Assets/StreamingAssets/Quests/`
3. Press the **Run** button — the quest will appear in the list of available quests

### Into the ready-to-use [**Text Quest Reader APP**](https://github.com/albruevich/Text-Quest-Reader/releases)

1. Launch the **Text Quest Reader** application
2. Press the **Add Quests** button
3. Copy the quest folder into the folder that opens
4. Press the **Refresh** button or restart the application — the quest will appear in the list of available quests

---

## Quest structure

A quest is a folder whose name matches the name of your quest.

When used locally, the folder name must not be changed.

Inside it, there are:
- the main `quest.json` file
- the `Images` folder
- the `Sounds` folder
- the `Musics` folder

These folders and quest.json are created automatically when a quest is created.  

After adding the quest to the Unity project [**Text Quest Reader**](https://github.com/albruevich/Text-Quest-Reader), the structure will look like this:

<img src="docs/quest_structure.webp" width="280">

---

## Main idea

Quest creation is built around three key elements: parameters, locations, and transitions.

1. Creating and editing parameters
2. Creating and editing locations
3. Creating and editing transitions between locations
4. The influence of locations and transitions on parameters
5. Conditions for displaying transitions depending on parameters

---

[↑ To contents](#contents)

---

## Parameters

It is recommended to start creating a quest by setting up several key parameters, for example: gold, health, mood.

#### 1. Creating a parameter

1. Press the button <img src="docs/btn_params.webp" width="30">
2. Click the field to the left of “Add parameter” <img src="docs/box_add_param.webp" width="164">
3. Specify the **Working title** (a working name that is not displayed in the game)

---

#### 2. Parameter values

Each parameter has:
- a minimum value,
- a maximum value,
- a starting value.

Set them and press the **Apply** button.

<img src="docs/param_panel_1.webp" width="680">

---

#### 3. Parameter display

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

#### 4. Parameter type

Parameters can be of three types: **Normal**, **Successful**, **Failed**

- **Normal** — does not affect quest completion  
- **Successful** — ends the quest with victory when the critical value is reached  
- **Failed** — ends the quest with defeat when the critical value is reached  

For example: if the gold parameter reaches 10, the quest ends with victory.

<img src="docs/param_types.webp" width="680">

*(Images and sounds can also be set for critical values — this will be described later.)*

---

#### 5. Parameter deactivation

You can disable a parameter by unchecking the box to the left of it.

In this case, the parameter will not be used in the quest.

<img src="docs/param_disable.webp" width="159">

---

[↑ To contents](#contents)

---

## Main quest settings

To open the quest settings:
1. Press the button <img src="docs/btn_params.webp" width="30">
2. Go to the **Quest settings** tab

Here you can configure the quest parameters displayed in [**Text Quest Reader**](https://github.com/albruevich/Text-Quest-Reader) when it is selected:

1. Display Name  
2. Start Music  
3. Start Image  
4. Quest description
5. Order in list — determines the quest position in the quest list. The smaller the value, the higher the quest is displayed.
6. Language

**Language** defines the language of the quest system elements in [**Text Quest Reader**](https://github.com/albruevich/Text-Quest-Reader):

- the text of the **Next** button,
- victory and defeat messages,
- the quest language label in the list, for example `[EN]`.

<img src="docs/quest_settings.webp" width="680">

---

## Modes

The editor has three main modes: location mode, transition mode, and movement mode.

<img src="docs/modes.webp" width="177">

1. **Location mode**  
   When you left-click the workspace (grid), the panel for creating a new location opens.

2. **Transition mode**  
   Left-click the first location, then the second one. After that, the transition creation panel will open.  
   *Note: you can create a transition that leads to the same location it starts from.*

3. **Movement mode**  
   - Left-clicking a location allows you to move it to a free cell.  
   - Left-clicking a transition allows you to change its position between locations.  
     What matters here is where the first click was made — on the start (tail) or the end (head) of the transition.


---

### Right click

1. Right-clicking a location or transition opens their editing panel.
2. In transition mode, if the starting location has already been selected, right-click cancels transition creation. 

---

### Undoing actions

If you made a mistake, use these buttons to undo the last action (Undo) or redo it (Redo).

<img src="docs/undo.webp" width="64">

---

## Locations

To open the location editing panel:
- right-click an existing location,  
- or left-click an empty cell in location mode.

The location editing or creation panel will open.

<img src="docs/edit_location.webp" width="680">

#### 1. Location descriptions

In the main text field, you can edit the location description.

One location can have several descriptions.  
To add a new description, press the “Add” button.  
Use the dropdown list to select a description:

<img src="docs/loc_descr_1.webp" width="164">

Descriptions can be deleted.

<img src="docs/loc_descr_2.webp" width="444">

If the “Select in order” checkbox is enabled, descriptions will be shown one after another.

If the “Select by formula” checkbox is enabled, the description will be selected based on a formula.

For example:  
`p1 > 5 ? 1 : 2`  
If p1 (gold) is greater than 5 — description #1 will be shown, otherwise — #2.

<img src="docs/loc_descr_3.webp" width="338">

Another example:  
`p2 + 1`

The formula returns the description number.

- If the player has a pistol (p2 = 1), the result will be 2 — description #2 is shown.  
- If there is no pistol (p2 = 0), the result will be 1 — description #1 is shown.


**Descriptions can contain parameters and formulas.**

For example:  
`You are so tired today, your health is somewhere around {p3}`  
In the game, this will be shown as:  
`You are so tired today, your health is somewhere around 7`

Or:  
`He gave you exactly half of his money: {p1 / 2}`


#### 2. Location types

Locations can have different types: **Neutral, Start, Victory, Fail, Empty**.

<img src="docs/loc_types.webp" width="173">

**Neutral** — does not affect the course of the game by itself.

**Start** — the quest starts from it. A quest can have only one starting location.

**Victory** — when entering this location, the quest ends with victory.

**Fail** — when entering this location, the quest ends with defeat.

**Empty** — if a location has this type, its description is not displayed. Instead, the description of the transition that led to this location is shown.

#### 3. Passability

You can limit the number of visits to a location.

By default, a location has unlimited passability — the player can visit it any number of times.

<img src="docs/loc_pass_1.webp" width="184">

To set a limit:
- uncheck the “Unlimited passability” checkbox,  
- specify the maximum number of visits.

After the limit is reached, the location will no longer be available (the transition to it will not be displayed).

For example: the player can visit a friend 3 times, and on the 4th time the location will not appear (the friend has gone on vacation).

<img src="docs/loc_pass_2.webp" width="199">

This mechanism is also convenient for creating one-time locations.

#### 4. Location influence on parameters

When entering a location, it can change the player’s parameters.

To do this, select the required parameter:

<img src="docs/loc_infl_to_param.webp" width="680">

---

**Actions**

A location can:
- **show a parameter** — it will be displayed in the game,
- **hide a parameter**,  
- **do nothing** (the default value).

---

**Influence on parameter values**

There are 4 available modes: **Units**, **Value**, **Percent**, **Expression**

**Units**  
Changes the parameter value by the specified number (adds or subtracts).  
Example: there were 2 gold, +3 is specified → it becomes 5 (taking into account the minimum and maximum value).

**Value**  
Sets the exact parameter value.  
Example: there were 2 gold, 0 is set → the player has no gold anymore.

**Percent**  
Changes the parameter value by the specified percentage.  
Example: there were 10 gold, -50% is specified → it becomes 5.

**Expression**  
Sets the parameter value using a formula.

Example:

p1 + (p11 == 0 ? -2 : 0)

- `p1` — oxygen  
- `p11` — breach (0 — not fixed)

If the breach is not fixed, oxygen decreases by 2

Another example:

(p2 + p5) / 2

- `p1` — gold  
- `p2` — work hours  
- `p5` — bonus  

In this case, gold becomes the average value between work hours and bonus.

---

**Random**

Formulas support random values.

Example:

p9 - rnd(1, 3)

- `p9` — monster health  

When shot, health decreases by a random number from 1 to 3.

---

[↑ To contents](#contents)

---

## Transitions

Transitions are very similar to locations: they can also have passability, show or hide parameters, and influence their values.  
These mechanics work in the same way, so they are not repeated here.

<img src="docs/edit_trans.webp" width="680">

---

**Main differences**

- A transition always has only one description.
- The transition button text is required.

<img src="docs/trans_btn_text.webp" width="288">

In the game it looks like this:

<img src="docs/trans_btn_view.webp" width="215">

---

**Transition display conditions**

Whether a transition will be shown depends on several conditions:

### 1. Logical condition

<img src="docs/trans_logical_condition.webp" width="277">

Sets a formula under which the transition is displayed.  
For example: the transition will be shown only if gold is greater than 3.

---

### 2. Range

<img src="docs/trans_range.webp" width="239">

The transition is displayed if the parameter value is within the specified range.  
For example: from 1 to 4 gold.

---

### 3. Accepts / does not accept values

<img src="docs/trans_accepts.webp" width="241">

The transition is displayed if the parameter accepts (or does not accept) the specified values.  
For example: p1 (gold) is equal to 1, or (apples - 2), or a random number from 3 to 10.

---

### 4. Divisibility

<img src="docs/trans_div.webp" width="239">

The transition is displayed if the parameter value is divisible (or not divisible) by the specified values.

---

### 5. Important

The transition will be shown **only if all conditions are met at the same time**:
- Logical condition  
- Range  
- Accepts / does not accept values  
- Divisibility  

It is recommended to start with one condition so you do not overcomplicate the logic and get confused while testing the quest.

---

### 6. Display order

If there are several transitions, they can be displayed in different order.

<img src="docs/trans_order_1.webp" width="274">

The order is set through the **Display order** parameter:
- the smaller the value, the higher the button appears in the list,
- if the values are the same — the order is determined randomly.

<img src="docs/trans_order_2.webp" width="127">

---

### 7. Priority

A quest can have transitions with the same button text. Such transitions are called **conflicting** and are highlighted in red.

For example: two transitions “Run from the monster to the technical sector”  
— one leads to rescue, the other to defeat.

<img src="docs/trans_prior_1.webp" width="551">

The probability of selection is determined by priority (weight):
- the higher the value, the higher the chance that the transition will be shown.

<img src="docs/trans_prior_2.webp" width="219">

For example:
- chance of rescue = 3  
- chance of death = 7  
→ 30% and 70%

There are also probabilistic transitions (not conflicting).  
For them, a value from 0 to 1 is used:
- 0.5 = 50% chance of appearing.

---

### 8. Gray (inactive) transitions / Always show

If the transition conditions are not met, it may not be displayed.  
However, you can enable the “Always show” option to show such transitions as inactive.

<img src="docs/trans_always_show_1.webp" width="390">

For example: the path to the Medbay or emergency compartment is closed (conditions are not met), but the transition is still displayed in gray.

This allows you to:
- give the player hints,
- create a feeling of choice,
- push the player toward finding a solution.

<img src="docs/trans_always_show_2.webp" width="137">

---

[↑ To contents](#contents)

---

## Working with resources

In locations, transitions, and critical parameters, you can use resources (images, music, and sounds) through special tags.

**Resource tags:**

- Images:  
  `<im your_beautiful_picture im>`

- Music:  
  `<mu your_music mu>`

- Sounds:  
  `<so your_sound so>`

---

After adding tags, you need to place the corresponding files into the quest folder.

To open the quest folder:
- press the quest save button,
- then select **Open folder**.

A folder with the required structure will open:

<img src="docs/res_folders.webp" width="358">

---

**File formats:**

- Images: `.png`, `.jpg`, `.jpeg`  
- Sounds: `.mp3`, `.wav`, `.ogg`

---

**Usage examples:**

<img src="docs/res_tags_1.webp" width="680">

<img src="docs/res_tags_2.webp" width="680">

---

**Updating resources**

The editor uses resource caching.  
After changing files in the folders, you need to refresh them manually.

To do this, press the corresponding refresh buttons:

<img src="docs/res_cache.webp" width="225">

Or restart the editor — this will also apply all changes.


---

## Game mode

To launch and debug the quest, press the button:

<img src="docs/btn_play.webp" width="36">

In game mode, you can:
- play through the quest from start to finish,
- temporarily set parameters for testing,
- rewind the playthrough back.

---

## Miscellaneous

You can enable or disable hints — the text at the top of the screen that reminds you of the current mode.

If hints are enabled:
- when hovering over locations and transitions, tooltips with information are displayed.

You can also enable or disable grid display:

<img src="docs/grid_n_hints.webp" width="60">

A short reference for mouse controls can be opened with this button:

<img src="docs/btn_info.webp" width="32">

Transitions have visual differences:
- tail (from) — blue and wide,
- head (to) — white and narrow.

<img src="docs/trans_view.webp" width="360">

---

## Tips

Do not start with a complex quest right away.

It is recommended to first create a small quest (5–10 locations) to:
- learn the main features of the editor,
- understand the system logic,
- avoid common mistakes in the future.

After that, it will be much easier to move on to more complex scenarios.


---

[↑ To contents](#contents)
