---
title: "API"
weight: 45
---

# All Players Playtime

### Path
`http://{SERVERIP}:{PORT}/Prefech_playTime/info` |
--|
`http://localhost:30120/Prefech_playTime/info`|

### Response Structure
Field | Type | Description |
--|--|--|
code | integer | Response code will be `0` on fail and `200` on success |
message | string | Info about the response might include some info. |
players | array | arry with all player objects |

### Example Response Object
```json
{
    "message": "200: Success",
    "code": 200,
    "players": {
        "steam:123456789123456": {
            "username": "JokeDevil",
            "steam_hex": "steam:123456789123456",
            "playtime": "465",
            "last_leave": "1658273391",
            "last_join": "1658272972"
        }
    }
}
```

### Authentication
Header | Value |
--|--|
`Authentication` | `token SECRET_TOKEN_HERE`

# Single Player Playtime
 Path
`http://{SERVERIP}:{PORT}/Prefech_playTime/info/{STEAM_HEX}` |
--|
`http://localhost:30120/Prefech_playTime/info/steam:123456789123456` |

### Response Structure
Field | Type | Description |
--|--|--|
code | integer | Response code will be `0` on fail and `200` on success |
message | string | Info about the response might include some info. |
player | array | arry with the player object |

### Example Response Object
```json
{
    "message": "200: Success",
    "code": 200,
    "player": {
        "username": "JokeDevil",
        "steam_hex": "steam:123456789123456",
        "playtime": "465",
        "last_leave": "1658273391",
        "last_join": "1658272972"
    }
}
```
### Authentication
Header | Value |
--|--|
`Authentication` | `token SECRET_TOKEN_HERE`