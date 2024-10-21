---
title: C_INFO
---

<style>

.article h1, .article h2, .article h3, .article h4, .article h5 {
  font-size: inherit;
}

.article h1 {
  color: #9a5050; /* red colour for the main heading */
  background-color: #262422; /* header bg colour */
  text-align: center;
  border-bottom: 1px solid #808080;
  padding: 5px;
  margin: -7px -7px; /* needed to overcome the article padding */
}

.article h2 {
}

/* Author + Date/Version Section */

.doc-info {
  background-color: #262422; /* header bg colour */
  font-weight: bold;
  display: flex;
  justify-content: space-between;
  padding: 0;
  margin: 7px -7px 0;
  border-bottom: 1px solid #808080;
}
.doc-info li {
  padding: 0 7px;
  display: flex;
  flex-wrap: wrap; /* necessary for very narrow screens */
}
/* needed for the seperating border */
.doc-info li:nth-child(1) {
  width: 50%;
  border-right: 1px solid;
}
/* first child */
.doc-info li:nth-child(1)::before {
  content: "Author:";
  padding-right: 3px;
}
/* second child */
.doc-info li:nth-child(2)::before {
  content: "Version:";
  padding-right: 3px;
}


/* ARTICLE SECTION */
	
.article {
  background-color: #0f0f0f;
  padding: 7px;
  border: 1px solid #808080;
  margin-top: 20px;
}

/* Needed for markdown styling in order to have seperate boxes divided into h2 sections */
.article h2::before {
  display: block;
  height: 20px;
  width: calc(100% + 16px);
  background-color: black;
  content: '';
  position: relative;
  left: -8px;
  border: 1px solid #808080;
  border-left: black;
  border-right: black;
  margin-bottom: 10px;
}
</style>


# C_INFO Daedalus class

* Auronen <!-- Author --> 
* 02.08.2022 <!-- Date -->
{: .doc-info }

Heavily inspired by the amazing documentation site https://www.gothic-library.ru
{: .acknowledgment } 
<!-- Todo: Automatically add "Acknowledgement" title to a section like this and style accordingly, see GMC doc -->

The `C_INFO` class is used to define dialogues in the game.


## Class definition

Class definition as it is defined in the [Scripts/Content/_intern/Classes.d](https://github.com/PhoenixTales/gothic-devkit/blob/HEAD/gothic/_work/data/Scripts/content/_Intern/CLASSES.D#L164) script file.


### C_Info Daedalus class

<!-- TODO: We somehow have to include some form of automatic syntax highlighting -->
```
CLASS C_Info
{
    var int    npc;         // npc instance has the dialogue
    var int    nr;          // number of the dialogue (for sorting)
    var int    important;   // should the npc start the dialogue automatically
    var func   condition;   // condition function
    var func   information; // function called on selecting the dialogue
    var string description; // text in the dialogue box
    var int    trade;       // should the dialogue show the trade window
    var int    permanent;   // should the dialogue be permanent or only one time deal
};
```

## Class members 

| Variable                    | Type   | Description                                                                         |
|-----------------------------|--------|-------------------------------------------------------------------------------------|
| [npc](#npc)                 | int    | npc instance to have the dialogue                                                   |
| [nr](#nr)                   | int    | dialogue order number                                                               |
| [important](#important)     | int    | npc addresses player automatically                                                  |
| [condition](#condition)     | func   | condition function whether the dialogue is shown or not                             |
| [information](#information) | func   | function called on dialogue selection - contains the dialogue lines and other logic |
| [description](#description) | string | text shown in the dialogue box                                                      |
| [trade](#trade)             | int    | is it a trade dialogue                                                              |
| [permanent](#permanent)     | int    | does the dialogue stay after being played once                                      |

### Class member overview

Description of the class member variables.

### npc

Sets what NPC will have this dialogue instance. Set a NPC instance.

```
INSTANCE Info_Diego_Gamestart (C_INFO)
{
	npc	= PC_Thief; // NPC instance for Diego
    // ...
};
```

### nr

The `nr` member variables determines the order of shown dialogues. Dialogues are ordered in the ascending order - instances with higher `nr` are below instances with lower `nr`.

```c++
INSTANCE Info_Diego_Gamestart (C_INFO)
{
    // ...
    nr = 1;
    // ...
};
```

This is why the end dialogues usually have `nr = 999;` this is the highest number out of any dialogues therefore will always show up at the bottom. (999 is not the highest number the `nr` can store, it is just considered the highest number, as there will hardly be 998 dialogue instances for a single character).
{: .note }
<!-- Todo: Add this kind of extra "note" styling in a table, see original documents; add "Note" title automatically, if needed -->


### important

The `important` member variable determines, whether the NPC will automatically address the player or not.

* `important = TRUE` - the NPC will address the player
* `important = FALSE` - the player has to talk to the NPC

When `important` is set to `TRUE` the description is not needed, since the dialogue is never shown in the dialogue box.

If there are multiple important dialogues that satisfy their condition function, they will be played in the order specified by [`nr`](#nr).
{: .info }
<!-- ToDO: Add styling and if needed automatically insert "info" title, see original docs -->
	
`important` variable is of the type integer, and it is initialized by the engine to the value of `0`. If you do not want your dialogue to be important, you can omit the `important` member variable since it will be initialized to `0` by the engine.
{: .tip }
<!-- Todo: Add styling and if needed automatically add "tip" title" -->


### condition

Condition function with signature `func int f()`. If the function returns `TRUE` the dialogue is displayed, if it return `FALSE` it is not displayed. The function name does not have to follow a particular naming convention, but a naming convention is used throughout all of the Gothic scripts: `{DialogueName}_Condition`.

Conditioned dialogue:
```
INSTANCE Info_Diego_Gamestart (C_INFO)
{
// ...
condition   = Info_Diego_Gamestart_Condition;
// ...
};

FUNC INT Info_Diego_Gamestart_Condition()
{
if (Kapitel < 2) // Show only when chapter is less than 2
{
    return TRUE;
};
return FALSE; // Not needed, but added for readability
};
```
		
Unconditioned dialogue:
```
INSTANCE Info_Diego_EXIT_Gamestart(C_INFO)
{
// ...
condition = Info_Diego_EXIT_Gamestart_Condition;
// ...
};

FUNC INT Info_Diego_EXIT_Gamestart_Condition()
{
return TRUE; // or return 1;
};
```

It is not necessary to return `FALSE` from dialogue conditions, but in other cases it can very rarely cause subtle bugs. It is thus good practice to always return some value, even if that is `FALSE`.
{: .tip }
<!-- Todo: Add styling and if needed automatically add "tip" title" -->


### information

The `information` function contains the function name (without double quotes `""` as `func` is a type in Daedalus) that is called when the dialogue option is selected. It contains the lines NPC's will say, items that will be transferred, quests related logic and much more. The function name does not have to follow a particular naming convention, but a naming convention is used throughout all of the Gothic scripts: `{DialogueName}_Info`.

```
INSTANCE Info_Diego_Gamestart (C_INFO)
{
    npc         = PC_Thief;
    nr          = 1;
    condition   = Info_Diego_Gamestart_Condition;
    information = Info_Diego_Gamestart_Info;
    permanent   = FALSE;
    important   = TRUE;
};

FUNC INT Info_Diego_Gamestart_Condition()
{
    if (Kapitel < 2)
    {
        return TRUE;
    };
    return FALSE;
};

FUNC VOID Info_Diego_Gamestart_Info()
{
    AI_Output(self,hero,"Info_Diego_Gamestart_11_00"); //I'm Diego.
    AI_Output(hero,self,"Info_Diego_Gamestart_15_01"); //I'm...
    AI_Output(self,hero,"Info_Diego_Gamestart_11_02"); //I'm not interested in who you are. You've just arrived. I look after the new arrivals. That's all for now.
    AI_Output(self,hero,"Info_Diego_Gamestart_11_03"); //If you plan to stay alive for a while, you should talk to me. But of course I won't keep you from choosing your own destruction. Well, what do you think?

    B_Kapitelwechsel(1); // Show the chapter 1 screen
};
```


### description

Specify a string that will be shown in the dialogue window.

```
instance DIA_XARDAS_GMC(C_INFO)
{
    // ...
	description = "Hello, is this the GMC site?";
};
```

![Description](../../../img/c_info_description.png)


### trade

If `trade` is set to `TRUE` the trading interface will be launched after the content `information` function is finished.

Fisk's trade dialogue:
```
instance  Stt_311_Fisk_Trade (C_INFO)
{
    npc         = Stt_311_Fisk;
    nr          = 800;
    condition   = Stt_311_Fisk_Trade_Condition;
    information = Stt_311_Fisk_Trade_Info;
    permanent   = TRUE;
    description = "Show me your goods.";
    trade       = TRUE;
};

FUNC int  Stt_311_Fisk_Trade_Condition()
{
    return TRUE;
};

FUNC VOID  Stt_311_Fisk_Trade_Info()
{
    AI_Output (other, self, "Stt_311_Fisk_Trade_15_00"); //Show me your goods.
};
```

Trade manager has been added to ZenGin not that long before the release of Gothic 1 (as discussed and discovered on [Phoenix the Game Discord server](https://discord.gg/CK4VAR7fpH) with the acquisition of Gothic version `0.94k`). In version 0.94 the trade manager worked quite differently and used a special (nowadays unused) Daedalus class `C_ItemReact`.
{: .trivia }
<!-- Add styling, and additional Trivia title automatically if needed -->

### permanent

Dialogues with `permanent = TRUE` do not disappear after the dialogue is played. This is used for dialogues where you ask for directions or flavor dialogues for unnamed NPCs.

Frequently used external function `Npc_KnowsInfo` which returns true if the dialogue instance has been played has had a bug in the implementation for a long time. This bug made it impossible to use this function with dialogue instances with `permanent = TRUE` as it would always return `FALSE`. This has been fixed in `Union 1.0m`.
{: .bug }
<!-- add additional styling if and extra "bug" title inserted automatically if needed -->

	    
## zParserExtender

zParserExtender implements some Quality of Life features for dialogues. More information can be found in [Dialogue constants article](../../../scripts/extenders/zPArserExtender/dialogues/)

	    
## AF Script Packet

Enhaced Info Manager (implemented using Ikarus and LeGo) adds tun of customisation and additional features to dialogues. More information can be found in the [AFSP Enhanced Information Manager article](../../scripts/extenders/afsp/index.md)
