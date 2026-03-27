# Potential New Logs
## Argumentation Answer Event
This event will happen every time when the player hit the "Submit" button within the argumentation engine/system. The value of the eventType could be "argumentationAnswer". Specific variables under this eventType could be "argumentationTitle" and "answer". Example JSON record could be:

```
{
    "_id": "69b4824e98a42e37064a7561",
    "data": {
      "argumentationTitle": "Unit 1 - Freshwater",
      "answer": "A,1,I"
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
    "eventType": "argumentationAnswerEvent",
    "game": "mhs",
    "playerId": "wenyi222",
    "sceneName": "Unit 1 Dev",
    "serverTimestamp": "2026-03-13T21:31:58.497Z",
    "version": "20260313-10763"
  }
```
And
```
{
    "_id": "69b4824e98a42e37064a7561",
    "data": {
      "argumentationTitle": "Unit 1 - Freshwater",
      "answer": "B,1,II"
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
    "eventType": "argumentationAnswerEvent",
    "game": "mhs",
    "playerId": "wenyi222",
    "sceneName": "Unit 1 Dev",
    "serverTimestamp": "2026-03-13T21:31:58.497Z",
    "version": "20260313-10763"
  }
```
## Movement Event
Current position event will generate log records every 30 seconds. We need more granularity or density of such records, such as 10 seconds a record. Additionally, to better measure the students' game literacy or skills, we also need to record each time when students press the navigation keyboard, such as keys of "W", "A", "S", "D", "Space", "H" and "Shift". Example JSON log records could be:
```
{
    "_id": "69b4824e98a42e37064a7561",
    "data": {
      "key": "W"
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
    "eventType": "movementEvent",
    "game": "mhs",
    "playerId": "wenyi222",
    "sceneName": "Unit 1 Dev",
    "serverTimestamp": "2026-03-13T21:31:58.497Z",
    "version": "20260313-10763"
  }
```
And
```
{
    "_id": "69b4824e98a42e37064a7561",
    "data": {
      "key": "Space"
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
    "eventType": "movementEvent",
    "game": "mhs",
    "playerId": "wenyi222",
    "sceneName": "Unit 1 Dev",
    "serverTimestamp": "2026-03-13T21:31:58.497Z",
    "version": "20260313-10763"
  }
```
And
```
{
    "_id": "69b4824e98a42e37064a7561",
    "data": {
      "key": "Shift"
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
    "eventType": "movementEvent",
    "game": "mhs",
    "playerId": "wenyi222",
    "sceneName": "Unit 1 Dev",
    "serverTimestamp": "2026-03-13T21:31:58.497Z",
    "version": "20260313-10763"
  }
```
## Object/Item Interaction Event
In Unit 1, actually there are limited objects the students could interact with. I am not sure if the later game version will refine the topographic map simulator there, if the game will, then we could record students' interactions logs regarding that object/item. The "data" variable could contain two sub-variables - "objectName" and "actionType". Example JSON logs could be:
```
{
    "_id": "69b4824e98a42e37064a7561",
    "data": {
      "objectName": "TopomapSimulation",
      "actionType": "TurnOn"
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
    "eventType": "ObjectInterEvent",
    "game": "mhs",
    "playerId": "wenyi222",
    "sceneName": "Unit 1 Dev",
    "serverTimestamp": "2026-03-13T21:31:58.497Z",
    "version": "20260313-10763"
  }
```
And
```
{
    "_id": "69b4824e98a42e37064a7561",
    "data": {
      "objectName": "TopomapSimulation",
      "actionType": "RaiseMap"
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
    "eventType": "ObjectInterEvent",
    "game": "mhs",
    "playerId": "wenyi222",
    "sceneName": "Unit 1 Dev",
    "serverTimestamp": "2026-03-13T21:31:58.497Z",
    "version": "20260313-10763"
  }
```
