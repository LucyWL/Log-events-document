# Potential New Logs

## DANI Panel Event
This event will happen every time when the player hit the "Tab" keyboard or other possible ways (mouse-clicking) to open the tool panel. Also, it will capture which specific tools they selected witin the panel. The value of the eventType could be "DANIEvent". Specific variables under this event type could be "actionType" and "toolName". The values under the "actionType" could be "open", and "close". The values under the "toolName" could be "Map", "Argumentation" and "ChatLog". If it just opens the Dani's panel, then the action type could be empty. Example JSON record could be:
```
{
    "_id": "69b4824e98a42e37064a7561",
    "data": {
      "toolName": "Map",
      "actionType": "Open"
    },
    "device": {
      "dpi": 96,
      "gMemory": 512,
      "gdApiType": "OpenGLES3",
      "gdName": "ANGLE (Intel, Vulkan 1.3.289 (Intel(R) UHD Graphics (JSL) (0x00004E55)), Intel open-source Mesa driver)",
      "memory": 182,
      "os": "Windows 11",
      "platform": "UnityWebGL",
      "processors": 1,
      "resolution": {
        "height": 1440,
        "refreshRate": {
          "denominator": 1,
          "numerator": 60,
          "value": 60
        },
        "width": 3440
      }
    },
    "eventType": "DaniEvent",
    "game": "mhs",
    "playerId": "wenyi222",
    "sceneName": "Unit 2 Dev",
    "serverTimestamp": "2026-03-13T21:31:58.497Z",
    "version": "20260313-10763"
  }
```
And
```
{
    "_id": "69b4824e98a42e37064a7561",
    "data": {
      "toolName": "",
      "actionType": "Close"
    },
    "device": {
      "dpi": 96,
      "gMemory": 512,
      "gdApiType": "OpenGLES3",
      "gdName": "ANGLE (Intel, Vulkan 1.3.289 (Intel(R) UHD Graphics (JSL) (0x00004E55)), Intel open-source Mesa driver)",
      "memory": 182,
      "os": "Windows 11",
      "platform": "UnityWebGL",
      "processors": 1,
      "resolution": {
        "height": 1440,
        "refreshRate": {
          "denominator": 1,
          "numerator": 60,
          "value": 60
        },
        "width": 3440
      }
    },
    "eventType": "DaniEvent",
    "game": "mhs",
    "playerId": "wenyi222",
    "sceneName": "Unit 2 Dev",
    "serverTimestamp": "2026-03-13T21:31:58.497Z",
    "version": "20260313-10763"
  }
```
## Missions Event (May not applicable)
This event will happen every time when the player open the "Missions" tool within Objectives tool. The value of the eventType could be "missionsEvent". Specific variables under this eventType could be "title", "actionType" and "status". For the values, it depends on the situation: (1) It's related to open or close the Missions session on the Objectives tool interface. Then the values to "actionType" could be "Open" and "Close" and other two variables could be NAs; (2) It's related to clicking on the content within the Missions' interface. Then the value to the "actionType" could be "Select", and the value to the "title" should be the quest name, and the values to the "status" could be "Open" and "Completed". Example JSON record could be:
```
{
    "_id": "69b4824e98a42e37064a7561",
    "data": {
      "title": "NA",
      "actionType": "Open",
      "status": "NA"
    },
    "device": {
      "dpi": 96,
      "gMemory": 512,
      "gdApiType": "OpenGLES3",
      "gdName": "ANGLE (Intel, Vulkan 1.3.289 (Intel(R) UHD Graphics (JSL) (0x00004E55)), Intel open-source Mesa driver)",
      "memory": 182,
      "os": "Windows 11",
      "platform": "UnityWebGL",
      "processors": 1,
      "resolution": {
        "height": 1440,
        "refreshRate": {
          "denominator": 1,
          "numerator": 60,
          "value": 60
        },
        "width": 3440
      }
    },
    "eventType": "missionsEvent",
    "game": "mhs",
    "playerId": "wenyi222",
    "sceneName": "Unit 2 Dev",
    "serverTimestamp": "2026-03-13T21:31:58.497Z",
    "version": "20260313-10763"
  }
```
And
```
{
    "_id": "69b4824e98a42e37064a7561",
    "data": {
      "title": "TheMeasureOfAMutt",
      "actionType": "Select",
      "status": "Completed"
    },
    "device": {
      "dpi": 96,
      "gMemory": 512,
      "gdApiType": "OpenGLES3",
      "gdName": "ANGLE (Intel, Vulkan 1.3.289 (Intel(R) UHD Graphics (JSL) (0x00004E55)), Intel open-source Mesa driver)",
      "memory": 182,
      "os": "Windows 11",
      "platform": "UnityWebGL",
      "processors": 1,
      "resolution": {
        "height": 1440,
        "refreshRate": {
          "denominator": 1,
          "numerator": 60,
          "value": 60
        },
        "width": 3440
      }
    },
    "eventType": "missionsEvent",
    "game": "mhs",
    "playerId": "wenyi222",
    "sceneName": "Unit 2 Dev",
    "serverTimestamp": "2026-03-13T21:31:58.497Z",
    "version": "20260313-10763"
  }
```
##  Chat Event
This event will happen every time when the player open the "Chat" tool within Objectives tool. The value of the eventType could be "chatEvent". Specific variables under this eventType could be "chatID", "actionType" and "title". First of all, it will reflect whether the Chat session opens or closes, so the "actionType" under this situation could be "Open" and "Close"; Secondly, focusing on the content of the "Chat" session's content, based on our discussions today, values of "actionType" should depend on dev team's work load. If it's not hard, then it could be more granular - "ScrollUp", "ScrollDown", "ScrollStop"; If it needs too much time to finish, then it could be less granular - "Scroll" and "Stop". When the "actionType" is "Open", "Stop" or "ScrollStop", then the "chat" will contain a list of conversation plus dialogue ids shown in the snapshot or the raw dialogue texts shown in the snapshot. Example JSON record could be:

```
{
    "_id": "69b4824e98a42e37064a7561",
    "data": {
      "chat": "Dani says ....." (or "[10-1, 10-2, 10-3]"),
      "actionType": "Open"
    },
    "device": {
      "dpi": 96,
      "gMemory": 512,
      "gdApiType": "OpenGLES3",
      "gdName": "ANGLE (Intel, Vulkan 1.3.289 (Intel(R) UHD Graphics (JSL) (0x00004E55)), Intel open-source Mesa driver)",
      "memory": 182,
      "os": "Windows 11",
      "platform": "UnityWebGL",
      "processors": 1,
      "resolution": {
        "height": 1440,
        "refreshRate": {
          "denominator": 1,
          "numerator": 60,
          "value": 60
        },
        "width": 3440
      }
    },
    "eventType": "chatEvent",
    "game": "mhs",
    "playerId": "wenyi222",
    "sceneName": "Unit 2 Dev",
    "serverTimestamp": "2026-03-13T21:31:58.497Z",
    "version": "20260313-10763"
  }
```
And
```
{
    "_id": "69b4824e98a42e37064a7561",
    "data": {
      "chat": "Dani says" (or "[10-1, 10-2, 10-3]"),
      "actionType": "ScrollStop"
    },
    "device": {
      "dpi": 96,
      "gMemory": 512,
      "gdApiType": "OpenGLES3",
      "gdName": "ANGLE (Intel, Vulkan 1.3.289 (Intel(R) UHD Graphics (JSL) (0x00004E55)), Intel open-source Mesa driver)",
      "memory": 182,
      "os": "Windows 11",
      "platform": "UnityWebGL",
      "processors": 1,
      "resolution": {
        "height": 1440,
        "refreshRate": {
          "denominator": 1,
          "numerator": 60,
          "value": 60
        },
        "width": 3440
      }
    },
    "eventType": "chatEvent",
    "game": "mhs",
    "playerId": "wenyi222",
    "sceneName": "Unit 2 Dev",
    "serverTimestamp": "2026-03-13T21:31:58.497Z",
    "version": "20260313-10763"
  }
```

And

```
{
    "_id": "69b4824e98a42e37064a7561",
    "data": {
      "chat": NA,
      "actionType": "ScrollUp"
    },
    "device": {
      "dpi": 96,
      "gMemory": 512,
      "gdApiType": "OpenGLES3",
      "gdName": "ANGLE (Intel, Vulkan 1.3.289 (Intel(R) UHD Graphics (JSL) (0x00004E55)), Intel open-source Mesa driver)",
      "memory": 182,
      "os": "Windows 11",
      "platform": "UnityWebGL",
      "processors": 1,
      "resolution": {
        "height": 1440,
        "refreshRate": {
          "denominator": 1,
          "numerator": 60,
          "value": 60
        },
        "width": 3440
      }
    },
    "eventType": "chatEvent",
    "game": "mhs",
    "playerId": "wenyi222",
    "sceneName": "Unit 2 Dev",
    "serverTimestamp": "2026-03-13T21:31:58.497Z",
    "version": "20260313-10763"
  }
```

## Game Start and End Event
This event will happen every time when the player start or exit the game. The value of the eventType could be "gameStartEvent" and "gameEndEvent". "gameStartEvent" is easy to capture, while the "gameEndEvent" should ask Dale's help. I don't think this envent type needs specific variables. Example JSON record could be:

 ```
{
    "_id": "69b4824e98a42e37064a7561",
    "data": {
    },
    "device": {
      "dpi": 96,
      "gMemory": 512,
      "gdApiType": "OpenGLES3",
      "gdName": "ANGLE (Intel, Vulkan 1.3.289 (Intel(R) UHD Graphics (JSL) (0x00004E55)), Intel open-source Mesa driver)",
      "memory": 182,
      "os": "Windows 11",
      "platform": "UnityWebGL",
      "processors": 1,
      "resolution": {
        "height": 1440,
        "refreshRate": {
          "denominator": 1,
          "numerator": 60,
          "value": 60
        },
        "width": 3440
      }
    },
    "eventType": "gameStartEvent",
    "game": "mhs",
    "playerId": "wenyi222",
    "sceneName": "Unit 2 Dev",
    "serverTimestamp": "2026-03-13T21:31:58.497Z",
    "version": "20260313-10763"
  }
```
And
 ```
{
    "_id": "69b4824e98a42e37064a7561",
    "data": {
    },
    "device": {
      "dpi": 96,
      "gMemory": 512,
      "gdApiType": "OpenGLES3",
      "gdName": "ANGLE (Intel, Vulkan 1.3.289 (Intel(R) UHD Graphics (JSL) (0x00004E55)), Intel open-source Mesa driver)",
      "memory": 182,
      "os": "Windows 11",
      "platform": "UnityWebGL",
      "processors": 1,
      "resolution": {
        "height": 1440,
        "refreshRate": {
          "denominator": 1,
          "numerator": 60,
          "value": 60
        },
        "width": 3440
      }
    },
    "eventType": "gameEndEvent",
    "game": "mhs",
    "playerId": "wenyi222",
    "sceneName": "Unit 2 Dev",
    "serverTimestamp": "2026-03-13T21:31:58.497Z",
    "version": "20260313-10763"
  }
```

## Game Window Focus and Unfocus Event
This event will happen every time when the player leave or re-focus the game window. The value of the eventType could be "gameWindowFocusEvent" and "gameWindowRefocusEvent". I don't think this envent type needs specific variables.

 ```
{
    "_id": "69b4824e98a42e37064a7561",
    "data": {
    },
    "device": {
      "dpi": 96,
      "gMemory": 512,
      "gdApiType": "OpenGLES3",
      "gdName": "ANGLE (Intel, Vulkan 1.3.289 (Intel(R) UHD Graphics (JSL) (0x00004E55)), Intel open-source Mesa driver)",
      "memory": 182,
      "os": "Windows 11",
      "platform": "UnityWebGL",
      "processors": 1,
      "resolution": {
        "height": 1440,
        "refreshRate": {
          "denominator": 1,
          "numerator": 60,
          "value": 60
        },
        "width": 3440
      }
    },
    "eventType": "gameWindowFocusEvent",
    "game": "mhs",
    "playerId": "wenyi222",
    "sceneName": "Unit 2 Dev",
    "serverTimestamp": "2026-03-13T21:31:58.497Z",
    "version": "20260313-10763"
  }
```
And
 ```
{
    "_id": "69b4824e98a42e37064a7561",
    "data": {
    },
    "device": {
      "dpi": 96,
      "gMemory": 512,
      "gdApiType": "OpenGLES3",
      "gdName": "ANGLE (Intel, Vulkan 1.3.289 (Intel(R) UHD Graphics (JSL) (0x00004E55)), Intel open-source Mesa driver)",
      "memory": 182,
      "os": "Windows 11",
      "platform": "UnityWebGL",
      "processors": 1,
      "resolution": {
        "height": 1440,
        "refreshRate": {
          "denominator": 1,
          "numerator": 60,
          "value": 60
        },
        "width": 3440
      }
    },
    "eventType": "gameWindowUnfocusEvent",
    "game": "mhs",
    "playerId": "wenyi222",
    "sceneName": "Unit 2 Dev",
    "serverTimestamp": "2026-03-13T21:31:58.497Z",
    "version": "20260313-10763"
  }
```
## Soil Key Puzzle Event

This event will happen every time when the player interacts with the soil key puzzle. Currently, we have collected logs regarding this puzzle with limited actions, `"Started"` and `"Finished"`. We can extend the action types to `"LeftDrag"` and `"RightDrag"`.

For the `"LeftDrag"` and `"RightDrag"` actions, the `data` variable can contain the following subvariables:

- `actionType`: The interaction performed by the player. Possible values include `"LeftDrag"` and `"RightDrag"`.
- `currentSoilType`: The current soil type (or soil type spectrum) selected after the interaction.
- `waterRetentionChange`: The expected change in water retention caused by the updated soil selection. Possible values include `"Increase"`, `"Decrease"`, and `"NoChange"`.
- `waterLevelStatus`: The resulting water-level condition after applying the current soil selection. Possible values include `"TooLow"`, `"Proper"`, and `"TooHigh"`.
- `isCorrectSelection`: Indicates whether the current soil-spectrum position satisfies the puzzle requirement.

The spectrum position should use the same scale defined internally by the game. For example, if the puzzle contains ten possible positions, position `1` can represent the far-left selection with the greatest water retention, while position `10` can represent the far-right selection with the greatest water drainage.

Example game logs could be:

```json
{
  "_id": "69b4824e98a42e37064a7561",
  "data": {
    "actionType": "LeftDrag",
    "currentSoilType": "Clay",
    "waterRetentionChange": "Increase",
    "waterLevelStatus": "TooHigh",
    "isCorrectSelection": false
  },
  "device": {
    "dpi": 96,
    "gMemory": 512,
    "gdApiType": "OpenGLES3",
    "gdName": "ANGLE (Intel, Vulkan 1.3.289 (Intel(R) UHD Graphics (JSL) (0x00004E55)), Intel open-source Mesa driver)",
    "memory": 182,
    "os": "Windows 11",
    "platform": "UnityWebGL",
    "processors": 1,
    "resolution": {
      "height": 1440,
      "refreshRate": {
        "denominator": 1,
        "numerator": 60,
        "value": 60
      },
      "width": 3440
    }
  },
  "eventType": "Soil Key Puzzle",
  "game": "mhs",
  "playerId": "wenyi222",
  "sceneName": "Unit 3 Dev",
  "serverTimestamp": "2026-03-13T21:31:58.497Z",
  "version": "20260313-10763"
}
```

And

```json
{
  "_id": "69b4824e98a42e37064a7561",
  "data": {
    "actionType": "RightDrag",
    "currentSoilType": "Sand",
    "waterRetentionChange": "Decrease",
    "waterLevelStatus": "Proper",
    "isCorrectSelection": true
  },
  "device": {
    "dpi": 96,
    "gMemory": 512,
    "gdApiType": "OpenGLES3",
    "gdName": "ANGLE (Intel, Vulkan 1.3.289 (Intel(R) UHD Graphics (JSL) (0x00004E55)), Intel open-source Mesa driver)",
    "memory": 182,
    "os": "Windows 11",
    "platform": "UnityWebGL",
    "processors": 1,
    "resolution": {
      "height": 1440,
      "refreshRate": {
        "denominator": 1,
        "numerator": 60,
        "value": 60
      },
      "width": 3440
    }
  },
  "eventType": "Soil Key Puzzle",
  "game": "mhs",
  "playerId": "wenyi222",
  "sceneName": "Unit 3 Dev",
  "serverTimestamp": "2026-03-13T21:31:58.497Z",
  "version": "20260313-10763"
}
```

This design would support more meaningful analyses than recording `"LeftDrag"` or `"RightDrag"` alone. For example, the logs could show how many adjustments a player made, whether the player moved toward or away from the correct setting, and how often the player passed over the correct spectrum position before solving the puzzle.

## Solar Still Design Event

The `SolarStillDesignEvent` should be captured whenever a player interacts with the **Solar Still Design** puzzle.

In this puzzle, the player designs a structure for generating water by making one selection within each of three design elements:

1. **Roof Style** — contains three possible choices.
2. **Extra Covering** — contains two possible choices.
3. **Glass Roof Temperature** — contains two possible choices.

Only **one choice can be selected at a time within each design element**. If the player selects another choice within the same design element, the new selection replaces the previous selection. After making selections, the player can click the **Submit** button to submit the current Solar Still design.

The event logs should therefore capture:

1. Which design element the player interacted with.
2. Which option the player selected.
3. The complete set of design selections when the player clicks **Submit**.

### Variables within `data`

- **featureUsed:** Identifies which part of the Solar Still Design puzzle the player interacted with.

  Recommended values:

  - `RoofStyle`
  - `ExtraCovering`
  - `GlassRoofTemperature`
  - `Submit`

- **actionType:** Describes the specific action performed by the player.

  Recommended values:

  - `OptionSelected`: The player selected an option within one of the design elements.
  - `DesignSubmitted`: The player clicked the Submit button to submit the current Solar Still design.

- **selectedOption:** Records the option selected by the player.

  This field should be included when:

  - `actionType` is `OptionSelected`.

  The exact values should use the canonical option names defined within the game.

  For example:

  ```text
  RoofStyleOption1
  RoofStyleOption2
  RoofStyleOption3
  ```

  ```text
  ExtraCoveringOption1
  ExtraCoveringOption2
  ```

  ```text
  GlassRoofTemperatureOption1
  GlassRoofTemperatureOption2
  ```

  These names are placeholders and should be replaced with the actual option names used internally by the game if such names already exist.

- **designSelections:** Records the player's complete Solar Still design at the time the player clicks the Submit button.

  This field should be included when:

  - `actionType` is `DesignSubmitted`.

  It should contain the currently selected value for:

  * `roofStyle`
  * `extraCovering`
  * `glassRoofTemperature`

---

### Example 1: Selecting a Roof Style

This event should be captured when the player selects one of the three choices under **Roof Style**.

```json
{
  "eventType": "SolarStillDesignEvent",
  "data": {
    "featureUsed": "RoofStyle",
    "actionType": "OptionSelected",
    "selectedOption": "RoofStyleOption1"
  }
}
```
### Example 2: Changing the Roof Style

If the player previously selected one roof style and then selects a different roof style, another event should be generated.

Because only one roof style can be active at a time, the new selection replaces the previous selection.

```json
{
  "eventType": "SolarStillDesignEvent",
  "data": {
    "featureUsed": "RoofStyle",
    "actionType": "OptionSelected",
    "selectedOption": "RoofStyleOption3"
  }
}
```

This allows the gameplay log to preserve not only the player's final choice, but also changes made while reasoning through the puzzle.

### Example 3: Selecting Extra Covering

This event should be captured when the player selects one of the two choices under **Extra Covering**.

```json
{
  "eventType": "SolarStillDesignEvent",
  "data": {
    "featureUsed": "ExtraCovering",
    "actionType": "OptionSelected",
    "selectedOption": "ExtraCoveringOption1"
  }
}
```

If the player later changes the selection:

```json
{
  "eventType": "SolarStillDesignEvent",
  "data": {
    "featureUsed": "ExtraCovering",
    "actionType": "OptionSelected",
    "selectedOption": "ExtraCoveringOption2"
  }
}
```

### Example 4: Selecting the Glass Roof Temperature

This event should be captured when the player selects one of the two choices under **Glass Roof Temperature**.

```json
{
  "eventType": "SolarStillDesignEvent",
  "data": {
    "featureUsed": "GlassRoofTemperature",
    "actionType": "OptionSelected",
    "selectedOption": "GlassRoofTemperatureOption1"
  }
}
```

If the player changes the selected temperature:

```json
{
  "eventType": "SolarStillDesignEvent",
  "data": {
    "featureUsed": "GlassRoofTemperature",
    "actionType": "OptionSelected",
    "selectedOption": "GlassRoofTemperatureOption2"
  }
}
```

### Example 5: Submitting the Solar Still Design

This event should be captured every time the player clicks the **Submit** button.

The event should record the complete design configuration that the player submitted so that the submitted solution can be reconstructed directly from the gameplay log.

```json
{
  "eventType": "SolarStillDesignEvent",
  "data": {
    "featureUsed": "Submit",
    "actionType": "DesignSubmitted",
    "designSelections": {
      "roofStyle": "RoofStyleOption3",
      "extraCovering": "ExtraCoveringOption1",
      "glassRoofTemperature": "GlassRoofTemperatureOption1"
    }
  }
}
```

### Recommended Event Structure Summary

#### Design-option interaction

```json
{
  "eventType": "SolarStillDesignEvent",
  "data": {
    "featureUsed": "RoofStyle | ExtraCovering | GlassRoofTemperature",
    "actionType": "OptionSelected",
    "selectedOption": "...",
    "previousSelection": "..."
  }
}
```

`previousSelection` should only be included when the player changes an existing selection.

#### Design submission

```json
{
  "eventType": "SolarStillDesignEvent",
  "data": {
    "featureUsed": "Submit",
    "actionType": "DesignSubmitted",
    "designSelections": {
      "roofStyle": "...",
      "extraCovering": "...",
      "glassRoofTemperature": "..."
    }
  }
}
```

