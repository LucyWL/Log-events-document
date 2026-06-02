# Potential New Logs
## Missions Event
This event will happen every time when the player open the "Missions" tool within Dani's tool panel. The value of the eventType could be "missionsEvent". Specific variables under this eventType could be "title", "actionType" and "status". Example JSON record could be:
```
{
    "_id": "69b4824e98a42e37064a7561",
    "data": {
      "title": "InfoAndIntros",
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
And
```
{
    "_id": "69b4824e98a42e37064a7561",
    "data": {
      "title": "TheMeasureOfAMutt",
      "actionType": "Select",
      "status": "Open"
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
This event will happen every time when the player open the "Chat" tool within Dani's tool panel. The value of the eventType could be "chatEvent". Specific variables under this eventType could be "chatID", "actionType" and "title". Example JSON record could be:

```
{
    "_id": "69b4824e98a42e37064a7561",
    "data": {
      "chatID": "20-1",
      "actionType": "Select",
      "title": "U2/Player"
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
      "chatID": "10-3",
      "actionType": "Select",
      "title": "U2/Jasper"
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
This event will happen every time when the player start or exit the game. The value of the eventType could be "gameStartEvent" and "gameEndEvent". I don't think this envent type needs specific variables. Example JSON record could be:

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
