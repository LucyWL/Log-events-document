# MHS2.0 Log Events Illustration Document
This repository is to create a structured illustration of MHS2.0's log events.

## General Information
Each log record should contain the following variables:

- **itemID:** A unique Id given to each collected log record
- **installID:** A unique Id given to each computer (or device), which installs the game.
- **buildType:** What type is the game release version, “Development” for within-team testing, or “Production” for field tests in schools.
- **buildVersion:** Each released game version is assigned a unique ID, which we can use to select which version to analyze.
- **playerName:** The Name of the student (player) can be given by the teacher, who has a name map of the students’ fake and real names.
- **playerId:** This is a unique ID for a student, in case the playerName has duplicate records.
- **groupType:** Whether an instructor within a class setting leads the player or plays the game individually.
Platform: ** The platform the student used to play the game (e.g., Windows, Mac, iPad).
- **timestamp:** The time point when this log record is collected with a format of “yyyy-mm-dd hh:mm:ss”.
- **timezone:** The Time zone (which should be meaningful) still needs more discussion (it restricts the geographic zones where the game will be played).
- **playerPosition:**
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
  - others (to be continued)
- **replayNumber:** The number of times the student has replayed corresponding game parts.
- **sceneNames:** Which scene the student (player) is in (each unit has several scenes). Example name format: “Unit 1_space ship”, “Unit 2_ailien dungeon”, “Unit 2_topotraphy.”
- **regionName:** The region name within a certain scene name.
- **questTable:** An object representing the student's quest menu. It contains:
  - **activeQuests:** An array of quests that are currently active.
  - **completedQuests:** An array of quests that have been completed.
- **taskTable:** An object representing the student's task menu. It contains:
  - **activeTasks:** An array of tasks that are currently active.
  - **completedTasks:** An array of tasks that have been completed.
- **eventType:** Which event type this record belongs to. Example events include: gameStartEvent, gameQuitEvent, triggerEvent, questEvent, taskEvent, dialogueEvent, dialogueNodeEvent, movementEvent, DANIMenuEvent, hotkeyEvent, DANIFeatureEvent, argumentationEvent, argumentationNodeEvent, argumentationAnswerEvent, argumentationToolEvent, miniGameEvent, miniGame InteractionEvent, topographicMapEvent, objectivesEvent.
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
    "Unit 1_space ship",
  ],
  "regionName": "Sector 7G",
  "questTable": {
    "activeQuests": [
      "quest1",
      "quest2"
    ],
    "completedQuests": [
      "quest0"
    ]
  },
  "taskTable": {
    "activeTasks": [
      "task1",
      "task2"
    ],
    "completedTasks": [
      "task0"
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
When a player starts to play MHS. No event type specific detailed information.

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
    "Unit 1_space ship",
  ],
  "regionName": "Sector 7G",
  "questTable": {
    "activeQuests": [
    ],
    "completedQuests": [
    ]
  },
  "taskTable": {
    "activeTasks": [
    ],
    "completedTasks": [
    ]
  },
  "eventType": "gameStartEvent",
  "specificEventDetail": {
  }
}
```
### Game End Event
When a player ends up playing MHS. No event type specific detailed information.

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
    "Unit 1_space ship",
  ],
  "regionName": "Sector 7G",
  "questTable": {
    "activeQuests": [
    ],
    "completedQuests": [
    ]
  },
  "taskTable": {
    "activeTasks": [
    ],
    "completedTasks": [
    ]
  },
  "eventType": "gameEndEvent",
  "specificEventDetail": {
  }
}
```
### Trigger Event (Object Interaction Event)
When a player interacts with an in-game object, specific variables related to this event type are the following:

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
  "eventType": "triggerEvent",
  "specificEventDetail": {
    "objectID": "obj-789",
    "objectName": "Cube1inU2Dungeon",
    "actionType": "Lift",
    "objectStatement": "Color changed to red"
  }
}
```
