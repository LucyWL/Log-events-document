# Potential New Logs

## DANI Panel Event
This event will happen every time when the player hit the "Tab" keyboard or other possible ways (mouse-clicking) to open the tool panel. Also, it will capture which specific tools they selected witin the panel. The value of the eventType could be "DANIEvent". Specific variables under this event type could be "actionType" and "toolName". The values under the "actionType" could be "open", and "close". The values under the "toolName" could be "DaniPanel", "Map", "Arguments" and "Objectives". Example JSON record could be:
```
{
    "_id": "69b4824e98a42e37064a7561",
    "data": {
      "toolName": "DaniPanel",
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
      "toolName": "Objectives",
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
    "eventType": "missionsEvent",
    "game": "mhs",
    "playerId": "wenyi222",
    "sceneName": "Unit 2 Dev",
    "serverTimestamp": "2026-03-13T21:31:58.497Z",
    "version": "20260313-10763"
  }
```
## Missions Event
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
This event will happen every time when the player open the "Chat" tool within Objectives tool. The value of the eventType could be "chatEvent". Specific variables under this eventType could be "chatID", "actionType" and "title". First of all, it will reflect whether the Chat session opens or closes, so the "actionType" under this situation could be "Open" and "Close"; Secondly, focusing on the content of the "Chat" session's content, based on our discussions today, values of "actionType" should depend on dev team's work load. If it's not hard, then it could be more granular - "ScrollUp", "ScrollDown", "ScrollStop"; If it needs too much time to finish, then it could be less granular - "Scroll" and "Stop". When the "actionType" is "Stop" or "ScrollStop", then the "ChatID" will contain a list of conversation plus dialogue ids shown in the snapshot, such as "[10-1, 10-2, 10-3]" (conversationId - dialogueNodeId) (if it's not a good data format, let me know). Example JSON record could be:

```
{
    "_id": "69b4824e98a42e37064a7561",
    "data": {
      "chatID": NA,
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
      "chatID": "[10-1, 10-2, 10-3]",
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
      "chatID": NA,
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
