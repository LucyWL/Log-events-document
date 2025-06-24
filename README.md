# MHS2.0 Log Events Illustration Document
This repository is to create a structured illustration of MHS2.0's log events.

# Table of Contents
- [General Information](#general-information)
- [Specific Event Information](#specific-event-information)
  - [Game Start Event](#game-start-event)
  - [Game End Event](#game-end-event)
  - [Trigger Event (Object Interaction Event)](#trigger-event-object-interaction-event)
  - [Quest Event](#quest-event)
  - [Dialogue Event](#dialogue-event)
  - [Dialogue Node Event](#dialogue-node-event)
  - [Movement Event](#movement-event)
  - [DANI Menu Event](#dani-menu-event)
  - [DANI Feature Event](#dani-feature-event)
  - [Hotkey Event](#hotkey-event)
  - [Topographic Map Event](#topographic-map-event)
  - [Objectives Event](#objectives-event)
  - [Argumentation Event](#argumentation-event)
  - [Argumentation Node Event](#argumentation-node-event)
  - [Argumentation Tool Event (Backing info)](#argumentation-tool-event)
  - [Argumentation Answer Event](#argumentation-answer-event)
  - [Mini Game Event](#mini-game-event)
  - [Mini Game Interaction Event](#mini-game-interaction-event)
- [Reference Information](#reference-information)
  - [Dialogue Event Reference](#dialogue-event-1)
  - [Dialogue Node Event Reference](#dialogue-node-event-1)
  - [Argumentation Node Events Reference](#argumentation-node-events)
  - [Player General Information](#player-general-information)

## General Information
Each log record should contain the following variables:

- **itemID:** A unique Id given to each collected log record
- **installID:** A unique Id given to each computer (or device), which installs the game.
- **buildType:** What type is the game release version, “Development” for within-team testing, or “Production” for field tests in schools.
- **buildVersion:** Each released game version is assigned a unique ID, which we can use to select which version to analyze.
- **playerName:** The Name of the student (player) can be given by the teacher, who has a name map of the students’ fake and real names.
- **playerId:** This is a unique ID for a student, in case the playerName has duplicate records.
- **Platform:** The platform the student used to play the game (e.g., Windows, Mac, iPad).
- **timestamp:** The time point when this log record is collected with a format of “yyyy-mm-dd hh:mm:ss”.
- **(optional)timezone:** The Time zone (which should be meaningful) still needs more discussion (it restricts the geographic zones where the game will be played) (UTC).
- **playerPosition:** (global)
  - X
  - Y
  - Z
- **cameraRotation:**
  - X
  - Y
  - Z
- **performance:**
  - memory
  - frame/sec
  - other metrics (to be continued)
- **sceneNames:** Which scene the student (player) is in (each unit has several scenes). Example name format: “Unit 1_scene”, “Unit 2_scene.”
- **regionName:** The region name (may need to be defined by the team) within a certain scene name.
- **questTable:** An object representing the student's quest menu. It contains:
  - **activeQuests:** An array of quests that are currently active.
  - **completedQuests:** An array of quests that have been completed.
<!-- - **(may not applicable to this game version)taskTable:** An object representing the student's task menu. It contains:
  - **activeTasks:** An array of tasks that are currently active.
  - **completedTasks:** An array of tasks that have been completed.-->
- **eventType:** Which event type this record belongs to. Example events include: gameStartEvent, gameQuitEvent, triggerEvent, questEvent, dialogueEvent, dialogueNodeEvent, movementEvent, DANIMenuEvent, hotkeyEvent, DANIFeatureEvent, argumentationEvent, argumentationNodeEvent, argumentationAnswerEvent, argumentationToolEvent, miniGameEvent, miniGame InteractionEvent, topographicMapEvent, objectivesEvent.
- **specificEventDetail:** This variable is structured as a nested JSON format and contains multiple variables belonging to a specific event type. Not all event types have value for this variable.

### Example JSON format
Each log record should contain the following variables:
```json
{
  "itemID": "123e4567-e89b-12d3-a456-426614174000",
  "installID": "install-abc-001",
  "buildType": "Production",
  "buildVersion": "v1.2.3",
  "playerName": "John Doe",
  "playerId": "player-456",
  "platform": "Windows",
  "timestamp": "2025-02-20 12:34:56",
  "timezone": "UTC+0",
  "playerPosition": {
    "X": 10.5,
    "Y": 20.0,
    "Z": 5.5
  },
  "cameraRotation": {
    "X": 0.0,
    "Y": 180.0,
    "Z": 0.0
  },
  "performance": {
    "memory": "512MB",
    "frame/sec": 60,
    "cpuUsage": "20%"
  },
  "sceneNames": [
    "Unit 2_scene",
  ],
  "regionName": "Spaceship_crashing_dungeon",
  "questTable": {
    "activeQuests": [
      "quest1",
      "quest2"
    ],
    "completedQuests": [
      "quest0"
    ]
  },
  "eventType": "gameStartEvent",
  "specificEventDetail": {
    "eventDetailKey1": "value1",
    "eventDetailKey2": "value2"
  }
}
```
## Specific Event Information
As we mentioned above, each specific event type contains different information, which is reflected in different particular variables within the variable of "specificEventDetail" in a nested structure.

### Game Start Event
When a player starts to play MHS. No event type-specific detailed information.

#### Example JSON format
```JSON
{
  "itemID": "123e4567-e89b-12d3-a456-426614174000",
  "installID": "install-abc-001",
  "buildType": "Production",
  "buildVersion": "v1.2.3",
  "playerName": "John Doe",
  "playerId": "player-456",
  "platform": "Windows",
  "timestamp": "2025-02-20 12:34:56",
  "timezone": "UTC+0",
  "playerPosition": {
    "X": 10.5,
    "Y": 20.0,
    "Z": 5.5
  },
  "cameraRotation": {
    "X": 0.0,
    "Y": 180.0,
    "Z": 0.0
  },
  "performance": {
    "memory": "512MB",
    "frame/sec": 60,
    "cpuUsage": "20%"
  },
  "replayNumber": 2,
  "sceneNames": [
    "Unit 2_scene",
  ],
  "regionName": "Spaceship_crashing_dungeon",
  "questTable": {
    "activeQuests": [
    ],
    "completedQuests": [
    ]
  },
  "eventType": "gameStartEvent",
  "specificEventDetail": {
  }
}
```
### Game End Event
When a player ends up playing MHS. No event type-specific detailed information.

#### Example JSON format
```JSON
{
  "itemID": "123e4567-e89b-12d3-a456-426614174000",
  "installID": "install-abc-001",
  "buildType": "Production",
  "buildVersion": "v1.2.3",
  "playerName": "John Doe",
  "playerId": "player-456",
  "groupType": "individual",
  "platform": "Windows",
  "timestamp": "2025-02-20 12:34:56",
  "timezone": "UTC+0",
  "playerPosition": {
    "X": 10.5,
    "Y": 20.0,
    "Z": 5.5
  },
  "cameraRotation": {
    "X": 0.0,
    "Y": 180.0,
    "Z": 0.0
  },
  "performance": {
    "memory": "512MB",
    "frame/sec": 60,
    "cpuUsage": "20%"
  },
  "replayNumber": 2,
  "sceneNames": [
    "Unit 1_scene",
  ],
  "regionName": "Spaceship",
  "questTable": {
    "activeQuests": [
    ],
    "completedQuests": [
    "quest1",
    "quest2",
    "quest3"
    ]
  },
  "eventType": "gameEndEvent",
  "specificEventDetail": {
  }
}
```
### Trigger Event (Object Interaction Event)
When a player interacts with an in-game object, specific variables related to this event type and saved within the variable of "specificEventDetail" are the following:

- **objectID:** A unique ID created for each object in a certain scene so that we can identify which object the player (student) interacts with.
- **objectName:** A name of the object, such as “Cube1inU2Dungeon,” “ControlPanel1inU3Dungeon.”
- **actionType:** The name of the action, such as “Lift,” “Drop,” “Enter,” “Select,” “Press.”
- **objectStatement:** After solving some puzzles, some in-game objects will change their statement (e.g., colors, format, or outcome). If no statement changing, we can put a value like “NA” or “Not Applicable.”

#### Example JSON format
```json
{
  "itemID": "abc123-unique",
  "installID": "device-001",
  "buildType": "Production",
  "buildVersion": "v2.0.1",
  "playerName": "Alice",
  "playerId": "player_001",
  "platform": "Windows",
  "timestamp": "2025-02-20 14:30:00",
  "timezone": "UTC+2",
  "playerPosition": {
    "X": 10.5,
    "Y": 20.0,
    "Z": 5.5
  },
  "cameraRotation": {
    "X": 0.0,
    "Y": 90.0,
    "Z": 0.0
  },
  "performance": {
    "memory": "8GB",
    "frame/sec": 60,
    "others": "N/A"
  },
  "sceneNames": [
    "Unit 2_scene",
  ],
  "regionName": "Spaceship_crashing_dungeon",
  "questTable": {
    "activeQuests": [
    "quest3"
    ],
    "completedQuests": [
    "quest1",
    "quest2"
    ]
  },
  "eventType": "triggerEvent",
  "specificEventDetail": {
    "objectID": "obj-789",
    "objectName": "Cube1inU2Dungeon",
    "actionType": "Lift",
    "objectStatement": "Color changed to red"
  }
}
```
### Quest Event
When a player starts or finishes a specific part of a unit, such as the "Beam Me Up, DANI!" in unit 1, this event type can be generated:

- **questID:** A unique ID is assigned to each quest.
- **questName:** The descriptive name given to a quest ID. Example names include:
  - “U1 – Welcome to WAT247”
  - “U1 – An Amazing AI”
  - “U1 – Time to Argue”
- **questEventType:** Specifies the event type for the quest. This variable has three possible values: 1) **questActiveEvent:** Represents the log record when the student accepted a new quest. 2) **questCompleteEvent:** Represents the log record when the student completes a quest. 3) **questProgressEvent:** Represents the log record for in-quest progress, such as when the player achieves a milestone (e.g., collecting evidence).
- **progressContent:** Records the specific progress achieved within the quest, such as the details of the collected evidence.

#### Example JSON format
```json
{
  "itemID": "abc123-unique",
  "installID": "device-001",
  "buildType": "Production",
  "buildVersion": "v2.0.1",
  "playerName": "Alice",
  "playerId": "player_001",
  "platform": "Windows",
  "timestamp": "2025-02-20 14:30:00",
  "timezone": "UTC+2",
  "playerPosition": {
    "X": 10.5,
    "Y": 20.0,
    "Z": 5.5
  },
  "cameraRotation": {
    "X": 0.0,
    "Y": 90.0,
    "Z": 0.0
  },
  "performance": {
    "memory": "8GB",
    "frame/sec": 60,
    "others": "N/A"
  },
  "sceneNames": [
    "Unit 2_scene"
  ],
  "regionName": "Spaceship-dungeon",
  "questTable": {
    "activeQuests": [
      "quest3"
    ],
    "completedQuests": [
      "quest1",
      "quest2"
    ]
  },
  "eventType": "questEvent",
  "specificEventDetail": {
    "questID": "quest2",
    "questName": "topoTalk",
    "questEventType": "questProgressEvent",
    "progressContent": "Collected evidence near the waterfall"
  }
}
```
<! -- ### Task Event
When a player receives or completes a task within a part of a certain unit, such as the "U1 – Welcome to WAT247" in unit 1, this event type can be generated:
-->
<!--
- **questID:** A unique ID assigned to each quest.
- **taskID:** A unique ID given to each task.
- **taskName:** The descriptive name given to a task. Example names include “wakeup”, “arfRoom”, “topoTalk.”
- **taskEventType:** Specifies the event type for the task. This variable has three possible values: 1) **taskActiveEvent:** Represents the log record when the student accepted a new task. 2) **taskCompleteEvent:** Represents the log record when the student completes a task. 3) **taskProgressEvent:** Represents the log record for in-task progress, such as when the player achieves a milestone (e.g., collecting evidence).
- **progressContent:** Records the specific progress achieved within the task, such as the details of the collected evidence.

#### Example JSON format
```json
{
  "itemID": "abc123-unique",
  "installID": "device-001",
  "buildType": "Production",
  "buildVersion": "v2.0.1",
  "playerName": "Alice",
  "playerId": "player_001",
  "groupType": "instructor-led",
  "platform": "Windows",
  "timestamp": "2025-02-20 14:30:00",
  "timezone": "UTC+2",
  "playerPosition": {
    "X": 10.5,
    "Y": 20.0,
    "Z": 5.5
  },
  "cameraRotation": {
    "X": 0.0,
    "Y": 90.0,
    "Z": 0.0
  },
  "performance": {
    "memory": "8GB",
    "frame/sec": 60,
    "others": "N/A"
  },
  "replayNumber": 3,
  "sceneNames": [
    "Unit 1_space ship",
    "Unit 2_alien dungeon"
  ],
  "regionName": "Sector 1",
  "questTable": {
    "activeQuests": [
      "quest3"
    ],
    "completedQuests": [
      "quest1",
      "quest2"
    ]
  },
  "taskTable": {
    "activeTasks": [
      "task3"
    ],
    "completedTasks": [
      "task1",
      "task2"
    ]
  },
  "eventType": "taskEvent",
  "specificEventDetail": {
    "questID": "quest3",
    "taskID": "task3",
    "taskName": "topoTalk",
    "taskEventType": "taskProgressEvent",
    "progressContent": "Collected evidence near the waterfall"
  }
}
```
-->
### Dialogue Event
This log event will be captured when a player triggers a dialogue box during the gameplay. The description regarding specific variables under the variable of "specificEventDetail" can be found:

- **dialogueID:** A unique ID assigned to each dialogue section.
- **dialogueEventType:** Specifies the type of dialogue event. It has two possible values: 1) **DialogueStartEvent:** Generated when players start a dialogue section. 2) **DialogueFinishEvent:** Generated when players end a dialogue section.

#### Example JSON format
```json
{
  "itemID": "abc123-unique",
  "installID": "device-001",
  "buildType": "Production",
  "buildVersion": "v2.0.1",
  "playerName": "Alice",
  "playerId": "player_001",
  "platform": "Windows",
  "timestamp": "2025-02-20 14:30:00",
  "timezone": "UTC+2",
  "playerPosition": {
    "X": 10.5,
    "Y": 20.0,
    "Z": 5.5
  },
  "cameraRotation": {
    "X": 0.0,
    "Y": 90.0,
    "Z": 0.0
  },
  "performance": {
    "memory": "8GB",
    "frame/sec": 60,
    "others": "N/A"
  },
  "sceneNames": [
    "Unit 2_scene"
  ],
  "regionName": "Spaceship dungeon",
  "questTable": {
    "activeQuests": [
      "quest3"
    ],
    "completedQuests": [
      "quest1",
      "quest2"
    ]
  },
  "eventType": "dialogueEvent",
  "specificEventDetail": {
    "dialogueID": "dialogue123",
    "dialogueEventType": "DialogueStartEvent"
  }
}
```
### Dialogue Node Event
This log event will be captured when a player needs to select a conversation within a dialogue session. The description regarding specific variables under the variable of "specificEventDetail" can be found:

- **dialogueID:** A unique ID is assigned to each dialogue section.
- **dialogueNodeID:** A unique ID assigned to the dialogue box, which contains the choice nodes, within the corresponding dialogue section.
- **choiceID:** The ID of the choice selected by the student. (Leave it as `null` when `dialogueNodeEventType` equals to “DialogueNodeStartEvent.”)
- **dialogueNodeEventType:** Specifies the event type for the dialogue node. It has two possible values: 1) **DialogueNodeStartEvent:** Generated when players start a dialogue box that contains choice nodes. 2) **DialogueNodeFinishEvent:** Generated when players make a choice and move on to the next dialogue box.

#### Example JSON format
```json
{
  "itemID": "abc123-unique",
  "installID": "device-001",
  "buildType": "Production",
  "buildVersion": "v2.0.1",
  "playerName": "Alice",
  "playerId": "player_001",
  "platform": "Windows",
  "timestamp": "2025-02-20 14:30:00",
  "timezone": "UTC+2",
  "playerPosition": {
    "X": 10.5,
    "Y": 20.0,
    "Z": 5.5
  },
  "cameraRotation": {
    "X": 0.0,
    "Y": 90.0,
    "Z": 0.0
  },
  "performance": {
    "memory": "8GB",
    "frame/sec": 60,
    "others": "N/A"
  },
  "sceneNames": [
    "Unit 2_scene"
  ],
  "regionName": "Spaceship-dungeon",
  "questTable": {
    "activeQuests": [
      "quest3"
    ],
    "completedQuests": [
      "quest1",
      "quest2"
    ]
  },
  "eventType": "dialogueNodeEvent",
  "specificEventDetail": {
    "dialogueID": "dialogue123",
    "dialogueNodeID": "node456",
    "choiceID": null,
    "dialogueNodeEventType": "DialogueNodeStartEvent"
  }
}
```
### Movement Event
This log event will be captured when a player navigates or moves around during the gameplay. The description regarding specific variables under the variable of "specificEventDetail" can be found:

- **actionName:** Specifies the specific movement action. Potential values include:
  - "forwardMove", "leftMove", "rightMove", "backMove", "jump"
  - or corresponding keyboard keys: "W", "A", "D", "S", and "Space."
- **state:** Indicates whether the movement event marks an action's beginning or end. Typical values: "Start" and "End."
- **isToggleHoverboardUsed:** A binary variable indicating whether the player uses the Toggle hoverboard for navigation. Possible values: "Yes" and "No."

#### Example JSON format
```json
{
  "itemID": "abc123-unique",
  "installID": "device-001",
  "buildType": "Production",
  "buildVersion": "v2.0.1",
  "playerName": "Alice",
  "playerId": "player_001",
  "platform": "Windows",
  "timestamp": "2025-02-20 14:30:00",
  "timezone": "UTC+2",
  "playerPosition": {
    "X": 10.5,
    "Y": 20.0,
    "Z": 5.5
  },
  "cameraRotation": {
    "X": 0.0,
    "Y": 90.0,
    "Z": 0.0
  },
  "performance": {
    "memory": "8GB",
    "frame/sec": 60,
    "others": "N/A"
  },
  "sceneNames": [
    "Unit 2_scene"
  ],
  "regionName": "Dungeon",
  "questTable": {
    "activeQuests": [
      "quest3"
    ],
    "completedQuests": [
      "quest1",
      "quest2"
    ]
  },
  "eventType": "movementEvent",
  "specificEventDetail": {
    "actionName": "forwardMove",
    "state": "start",
    "isToggleHoverboardUsed": "No"
  }
}
```
### DANI Menu Event
This log event will be captured when a player opens the panel containing different tools within the game by using the "Tab" keyboard. The description regarding specific variables under the variable of "specificEventDetail" can be found:

- **actionName:** Specifies the action for this event type. It has two possible values: 1) **DANIMenuOpenEvent:** Occurs when the player presses the "Tab" keyboard button to open the in-game tool panel. 2) **DANIMenuCloseEvent:** Occurs when the player closes the in-game tool panel.

#### Example JSON format
```json
{
  "itemID": "abc123-unique",
  "installID": "device-001",
  "buildType": "Production",
  "buildVersion": "v2.0.1",
  "playerName": "Alice",
  "playerId": "player_001",
  "platform": "Windows",
  "timestamp": "2025-02-20 14:30:00",
  "timezone": "UTC+2",
  "playerPosition": {
    "X": 10.5,
    "Y": 20.0,
    "Z": 5.5
  },
  "cameraRotation": {
    "X": 0.0,
    "Y": 90.0,
    "Z": 0.0
  },
  "performance": {
    "memory": "8GB",
    "frame/sec": 60,
    "others": "N/A"
  },
  "sceneNames": [
    "Unit 2_Scene"
  ],
  "regionName": "Sector 1",
  "questTable": {
    "activeQuests": [
      "quest3"
    ],
    "completedQuests": [
      "quest1",
      "quest2"
    ]
  },
  "eventType": "DANIMenuEvent",
  "specificEventDetail": {
    "actionName": "DANIMenuOpenEvent"
  }
}
```
### DANI Feature Event
This log event will be captured when a player chooses a specific tool within the tool panel. The description regarding specific variables under the variable of "specificEventDetail" can be found:

- **featureName:** The name of the tool. Example names include: 1)"map," 2)"background info," and 3)"chat log."
- **actionName:** Specifies the action for this event type. It has two possible values: 1) **arfFeatureOpenEvent:** Occurs when the player presses the "Tab" keyboard button to open the in-game tool panel. 2) **arfFeatureCloseEvent:** Occurs when the player closes the in-game tool panel.

#### Example JSON format
```json
{
  "itemID": "abc123-unique",
  "installID": "device-001",
  "buildType": "Production",
  "buildVersion": "v2.0.1",
  "playerName": "Alice",
  "playerId": "player_001",
  "platform": "Windows",
  "timestamp": "2025-02-20 14:30:00",
  "timezone": "UTC+2",
  "playerPosition": {
    "X": 10.5,
    "Y": 20.0,
    "Z": 5.5
  },
  "cameraRotation": {
    "X": 0.0,
    "Y": 90.0,
    "Z": 0.0
  },
  "performance": {
    "memory": "8GB",
    "frame/sec": 60,
    "others": "N/A"
  },
  "sceneNames": [
    "Unit 1_scene"
  ],
  "regionName": "Spaceship",
  "questTable": {
    "activeQuests": [
      "quest3"
    ],
    "completedQuests": [
      "quest1",
      "quest2"
    ]
  },
  "eventType": "DANIFeatureEvent",
  "specificEventDetail": {
    "featureName": "map",
    "actionName": "DANIFeatureOpenEvent"
  }
}
```
### Hotkey Event
This log event will be captured when a player presses a key on the keyboard to access a specific feature quickly. The description regarding specific variables under the variable of "specificEventDetail" can be found:

- **keyName:** Specifies which keyboard button the player pressed. Example buttons include: "Tab," "B," "M," and "Q."
- **description:** Provides a descriptive name for the keyboard button. For example: "Tab" corresponds to "DANI tool menu;" "B" corresponds to "backing Information;" "M" corresponds to "map;" "Q" corresponds to "quests."

#### Example JSON format
```json
{
  "itemID": "abc123-unique",
  "installID": "device-001",
  "buildType": "Production",
  "buildVersion": "v2.0.1",
  "playerName": "Alice",
  "playerId": "player_001",
  "platform": "Windows",
  "timestamp": "2025-02-20 14:30:00",
  "timezone": "UTC+2",
  "playerPosition": {
    "X": 10.5,
    "Y": 20.0,
    "Z": 5.5
  },
  "cameraRotation": {
    "X": 0.0,
    "Y": 90.0,
    "Z": 0.0
  },
  "performance": {
    "memory": "8GB",
    "frame/sec": 60,
    "others": "N/A"
  },
  "sceneNames": [
    "Unit 1_scene"
  ],
  "regionName": "Spaceship",
  "questTable": {
    "activeQuests": [
      "quest3"
    ],
    "completedQuests": [
      "quest1",
      "quest2"
    ]
  },
  "eventType": "hotkeyEvent",
  "specificEventDetail": {
    "keyName": "Tab",
    "description": "DANI tool menu."
  }
}
```
### Topographic Map Event
This log event will be captured when a player conducts actions within the topographic map. The description regarding specific variables under the variable of "specificEventDetail" can be found:

- **featureUsed:** Indicates which feature on the map is used, such as the topographic level button or a waypoint.
- **actionType:** Describes the specific action conducted by the player. Example values include: "Drag," "Drop," "Select," and "Unselect." It can also be "dragStart" and "dragEnd".
- **locationInfo:** Provides details about where the player moved the waypoint on the topographic map.

#### Example JSON format
```json
{
  "itemID": "abc123-unique",
  "installID": "device-001",
  "buildType": "Production",
  "buildVersion": "v2.0.1",
  "playerName": "Alice",
  "playerId": "player_001",
  "platform": "Windows",
  "timestamp": "2025-02-20 14:30:00",
  "timezone": "UTC+2",
  "playerPosition": {
    "X": 10.5,
    "Y": 20.0,
    "Z": 5.5
  },
  "cameraRotation": {
    "X": 0.0,
    "Y": 90.0,
    "Z": 0.0
  },
  "performance": {
    "memory": "8GB",
    "frame/sec": 60,
    "others": "N/A"
  },
  "sceneNames": [
    "Unit 1_scene",
  ],
  "regionName": "Spaceship",
  "questTable": {
    "activeQuests": [
      "quest3"
    ],
    "completedQuests": [
      "quest1",
      "quest2"
    ]
  },
  "eventType": "topographicMapEvent",
  "specificEventDetail": {
    "featureUsed": "waypoint",
    "actionType": "dragEnd",
    "locationInfo": "(35.6895, 139.6917)"
  }
}
```
### Objectives Event
This log event will be captured when a player conducts actions within the tool of "Objectives". The description regarding specific variables under the variable of "specificEventDetail" can be found:

- **action:** Describes the action the player is performing within the “objectives” menu. Possible values include: "select" and "unselect"
- **missionSelect:** Specifies which mission the player has chosen to track. For example, “Foraged Forging: Collect 5 piles of scrap metal.”

#### Example JSON format
```json
{
  "itemID": "abc123-unique",
  "installID": "device-001",
  "buildType": "Production",
  "buildVersion": "v2.0.1",
  "playerName": "Alice",
  "playerId": "player_001",
  "platform": "Windows",
  "timestamp": "2025-02-20 14:30:00",
  "timezone": "UTC+2",
  "playerPosition": {
    "X": 10.5,
    "Y": 20.0,
    "Z": 5.5
  },
  "cameraRotation": {
    "X": 0.0,
    "Y": 90.0,
    "Z": 0.0
  },
  "performance": {
    "memory": "8GB",
    "frame/sec": 60,
    "others": "N/A"
  },
  "sceneNames": [
    "Unit 1_scene"
  ],
  "regionName": "Spaceship",
  "questTable": {
    "activeQuests": [
      "quest3"
    ],
    "completedQuests": [
      "quest1",
      "quest2"
    ]
  },
  "eventType": "objectivesEvent",
  "specificEventDetail": {
    "action": "select",
    "missionSelect": "Foraged Forging: Collect 5 piles of scrap metal"
  }
}
```
### Argumentation Event
This log event will be captured when a player opens or exists the argumentation system. The description regarding specific variables under the variable of "specificEventDetail" can be found:

- **argumentationTitle:** The title or topic of the argumentation. Example names include: "U1 – Argumentation tutorial," "U2 – Watershed," and "U3 – Pollution Upstream."
- **argumentationDescription:** A brief description of the corresponding argumentation title. For example: "U1 – Argumentation tutorial - Place the claim, reasoning, and evidence orbs in orbit," "U2 – Watershed - Which watershed is bigger based on collected evidence from eastern and western waterfalls," and "U3 – Pollution Upstream" equals "Where is the pollution site probably located?"
- **arctionType:** Specifies the action type for the argumentation event. It has two possible values: 1) **argumentationSessionOpen:** Indicates that the player has opened the scientific argumentation engine. 2) **argumentationSessionClose:** Indicates that the player has closed the scientific argumentation engine.

#### Example JSON format
```json
{
  "itemID": "abc123-unique",
  "installID": "device-001",
  "buildType": "Production",
  "buildVersion": "v2.0.1",
  "playerName": "Alice",
  "playerId": "player_001",
  "platform": "Windows",
  "timestamp": "2025-02-20 14:30:00",
  "timezone": "UTC+2",
  "playerPosition": {
    "X": 10.5,
    "Y": 20.0,
    "Z": 5.5
  },
  "cameraRotation": {
    "X": 0.0,
    "Y": 90.0,
    "Z": 0.0
  },
  "performance": {
    "memory": "8GB",
    "frame/sec": 60,
    "others": "N/A"
  },
  "sceneNames": [
    "Unit 2_scene"
  ],
  "regionName": "Alien dungeon",
  "questTable": {
    "activeQuests": [
      "quest3"
    ],
    "completedQuests": [
      "quest1",
      "quest2"
    ]
  },
  "eventType": "argumentationEvent",
  "specificEventDetail": {
    "argumentationTitle": "U2 – Watershed",
    "argumentationDescription": "Which watershed is bigger based on collected evidence from eastern and western waterfalls",
    "arctionType": "argumentationSessionOpen"
  }
}
```
### Argumentation Node Event
This log event will be captured when a player interacts with the features or functions within the argumentation system. The description regarding specific variables under the variable of "specificEventDetail" can be found:

- **argumentationTitle:** The title or topic of the argumentation. Example names include: "U1 – Argumentation tutorial", "U2 – Watershed", "U3 – Pollution Upstream"
- **nodeName:** The name of the choice node. Example names include: "A", "1" and "II."
- **arctionType:** Specifies the action type for the argumentation node event. It has four possible values: 1) **argumentationNodeHoverStart:** Generated when the player hovers on a choice node and a dialogue box pops up for them to read. 2)**argumentationNodeHoverEnd:** Generated when the player ends hovering on a specific node. 3) **argumentationNodeAdd:** Generated when the player drags the choice node into the argumentation structure. 4)**argumentationNodeRemove:** Generated when the player removes the node from the argumentation structure.

#### Example JSON format
```json
{
  "itemID": "abc123-unique",
  "installID": "device-001",
  "buildType": "Production",
  "buildVersion": "v2.0.1",
  "playerName": "Alice",
  "playerId": "player_001",
  "platform": "Windows",
  "timestamp": "2025-02-20 14:30:00",
  "timezone": "UTC+2",
  "playerPosition": {
    "X": 10.5,
    "Y": 20.0,
    "Z": 5.5
  },
  "cameraRotation": {
    "X": 0.0,
    "Y": 90.0,
    "Z": 0.0
  },
  "performance": {
    "memory": "8GB",
    "frame/sec": 60,
    "others": "N/A"
  },
  "sceneNames": [
    "Unit 2_scene"
  ],
  "regionName": "Alien dungeon",
  "questTable": {
    "activeQuests": [
      "quest3"
    ],
    "completedQuests": [
      "quest1",
      "quest2"
    ]
  },
  "eventType": "argumentationNodeEvent",
  "specificEventDetail": {
    "argumentationTitle": "U1 – Argumentation tutorial",
    "nodeName": "A",
    "arctionType": "argumentationNodeHoverStart"
  }
}
```
### Argumentation Tool Event (Backing Info)
This log event will be captured when a player interacts with tools like "instruction" and "previous chat" within the argumentation system. The description regarding specific variables under the variable of "specificEventDetail" can be found:

- **argumentationTitle:** The title or topic of the argumentation. Example names include: 1) "U1 – Argumentation tutorial," 2) "U2 – Watershed," and "U3 – Pollution Upstream."
- **toolName:** The name of the tool that the player can refer to within the argumentation engine.
- **arctionType:** Specifies the action type for the argumentation tool event. It has two possible values: 1) **argumentationToolOpen:** Indicates that the player has opened the argumentation tool within a certain argumentation session. 2) **argumentationToolClose:** Indicates that the player has closed the argumentation tool within a certain argumentation session.

#### Example JSON format
```json
{
  "itemID": "abc123-unique",
  "installID": "device-001",
  "buildType": "Production",
  "buildVersion": "v2.0.1",
  "playerName": "Alice",
  "playerId": "player_001",
  "platform": "Windows",
  "timestamp": "2025-02-20 14:30:00",
  "timezone": "UTC+2",
  "playerPosition": {
    "X": 10.5,
    "Y": 20.0,
    "Z": 5.5
  },
  "cameraRotation": {
    "X": 0.0,
    "Y": 90.0,
    "Z": 0.0
  },
  "performance": {
    "memory": "8GB",
    "frame/sec": 60,
    "others": "N/A"
  },
  "sceneNames": [
    "Unit 1_scene"
  ],
  "regionName": "Spaceship",
  "questTable": {
    "activeQuests": [
      "quest3"
    ],
    "completedQuests": [
      "quest1",
      "quest2"
    ]
  },
  "eventType": "argumentationToolEvent",
  "specificEventDetail": {
    "argumentationTitle": "U1 – Argumentation tutorial",
    "toolName": "referenceTool",
    "arctionType": "argumentationToolOpen"
  }
}
```
### Argumentation Answer Event
This log event will be captured when a player presses the "submit" button within the argumentation system. The description regarding specific variables under the variable of "specificEventDetail" can be found:

- **argumentationTitle:** The title or topic of the argumentation. Example names include: "U1 – Argumentation tutorial", "U2 – Watershed", and "U3 – Pollution Upstream".
- **answerSubmitted:** A combination of the three components – Claim, Reasoning, and Evidence. Examples include: "I, A, 2", "II, B, 1", and "I, C, 7". If only one or two components is selected, then: "I,," indicates only Claim is selected. ",A," indicates only Reasoning is selected. ",,1" indicates only Evidence is selected. ",A,1" indicates only evidence and reason are selected.  
- **arctionType:** Specifies the action type for the argumentation answer event. It has two possible values:
  - **argumentationSuccess:** Indicates the player hit the "Submit" button with the correct answer.
  - **argumentationFailed:** Indicates the player submitted an incorrect answer.
- **feedbackText:** Provides the feedback the player received upon submitting the answer. The feedback content depends on the answer provided.

#### Example JSON format
```json
{
  "itemID": "abc123-unique",
  "installID": "device-001",
  "buildType": "Production",
  "buildVersion": "v2.0.1",
  "playerName": "Alice",
  "playerId": "player_001",
  "platform": "Windows",
  "timestamp": "2025-02-20 14:30:00",
  "timezone": "UTC+2",
  "playerPosition": {
    "X": 10.5,
    "Y": 20.0,
    "Z": 5.5
  },
  "cameraRotation": {
    "X": 0.0,
    "Y": 90.0,
    "Z": 0.0
  },
  "performance": {
    "memory": "8GB",
    "frame/sec": 60,
    "others": "N/A"
  },
  "sceneNames": [
    "Unit 2_scene"
  ],
  "regionName": "Alien dungeon",
  "questTable": {
    "activeQuests": [
      "quest3"
    ],
    "completedQuests": [
      "quest1",
      "quest2"
    ]
  },
  "eventType": "argumentationAnswerEvent",
  "specificEventDetail": {
    "argumentationTitle": "U1 – Argumentation tutorial",
    "answerSubmitted": "I, A, 2",
    "arctionType": "argumentationSuccess",
    "feedbackText": "Well done! Your answer is correct."
  }
}
```
### Mini Game Event
This log event will be captured when a player starts or ends to play mini-games. The description regarding specific variables under the variable of "specificEventDetail" can be found:

- **gameSession:** Specifies which mini-game session the log belongs to. Example sessions include: "Nanomanchine1," "Nanomanchine2," and "Forge Mini Game"
- **action:** Indicates the state of the mini-game session. Possible values include: "start" (when the player starts the session) and "end" (when the player completes the session).

#### Example JSON format
```json
{
  "itemID": "abc123-unique",
  "installID": "device-001",
  "buildType": "Production",
  "buildVersion": "v2.0.1",
  "playerName": "Alice",
  "playerId": "player_001",
  "platform": "Windows",
  "timestamp": "2025-02-20 14:30:00",
  "timezone": "UTC+2",
  "playerPosition": {
    "X": 10.5,
    "Y": 20.0,
    "Z": 5.5
  },
  "cameraRotation": {
    "X": 0.0,
    "Y": 90.0,
    "Z": 0.0
  },
  "performance": {
    "memory": "8GB",
    "frame/sec": 60,
    "others": "N/A"
  },
  "sceneNames": [
    "Unit 1_scene"
  ],
  "regionName": "Spaceship",
  "questTable": {
    "activeQuests": [
      "quest3"
    ],
    "completedQuests": [
      "quest1",
      "quest2"
    ]
  },
  "eventType": "miniGameEvent",
  "specificEventDetail": {
    "gameSession": "Nanomanchine1",
    "action": "start"
  }
}
```
### Mini Game Interaction Event
This log event will be captured when a player starts or ends to play mini-games. The description regarding specific variables under the variable of "specificEventDetail" can be found:

- **gameSession:** Specifies which mini-game session the log belongs to.
- **action:** Indicates the action the player is performing. Example values include: "drag," "drop," and "remove."
- **object:** Identifies which piece is interacted with by the player. Example pieces include: "horizontalLine1," "horizontalLine2," "leftDownCorner," and "rightDownCorner."
- **statement:** Describes how the action on the object changes the object's state or outcome. Example values include: "cold", "warm", and "hot". If the interaction does not affect the object's statement, use "NA".

#### Example JSON format
```json
{
  "itemID": "abc123-unique",
  "installID": "device-001",
  "buildType": "Production",
  "buildVersion": "v2.0.1",
  "playerName": "Alice",
  "playerId": "player_001",
  "platform": "Windows",
  "timestamp": "2025-02-20 14:30:00",
  "timezone": "UTC+2",
  "playerPosition": {
    "X": 10.5,
    "Y": 20.0,
    "Z": 5.5
  },
  "cameraRotation": {
    "X": 0.0,
    "Y": 90.0,
    "Z": 0.0
  },
  "performance": {
    "memory": "8GB",
    "frame/sec": 60,
    "others": "N/A"
  },
  "sceneNames": [
    "Unit 2_scene"
  ],
  "regionName": "Alien dungeon",
  "questTable": {
    "activeQuests": [
      "quest3"
    ],
    "completedQuests": [
      "quest1",
      "quest2"
    ]
  },
  "eventType": "miniGameInteractionEvent",
  "specificEventDetail": {
    "gameSession": "Nanomanchine1",
    "action": "drag",
    "object": "horizontalLine1",
    "statement": "cold"
  }
}
```
## Reference Information
This type of information can be uploaded manually and saved in a local database instead of being collected by the logging system in real time.

### Dialogue Event

#### Example JSON format
```json
{
      "dialogueID": "dlg-101",
      "dialogueNames": "Introduction to AI",
      "rawTextContent": "Welcome to the AI unit. Today, we will discuss what AI is and its applications."
}
```
### Dialogue Node Event 

#### Example JSON format
```json
 {
      "dialogueID": "dlg-101",
      "dialogueNodeID": "node-1",
      "choiceID": ["A", "B", "C"],
      "dialogueNodeName": "AI Definition",
      "dialogueNodeText": "AI stands for Artificial Intelligence. What do you think it does?",
      "choiceText": {
        "A": "Mimics human intelligence",
        "B": "Controls robots",
        "C": "Is just a sci-fi concept"
      }
}
```
### Argumentation Node Events 

#### Example JSON format
```json
 {
      "argumentationTitle": "U2 – Watershed",
      "nodeName": "A",
      "nodeDescription": "Water that evaporates from the ocean will leave the salt behind. Thus the rain that falls on land will be drinkable."
}
```
### Player General Information

<!-- - **groupType:** Whether an instructor within a class setting leads the player or plays the game individually (move that to the reference database).
-->
#### Example JSON format
```json
 {
      "playerId": "player-001",
      "teacherId": "teacher-123",
      "classId": "class-789",
}
```
