UNCA OPEN SPEC DOCUMENT

### Preamble
If you've read a OPENSPEC document before you can skip this part.
- Communication is documented from the perspective of the client unless specified otherwise
- Data is represented by JSON/BSONs with comments for clarity of specifics (e.g. u16 instead of u32).
- Data {surrounded by brackets} represent variables and UPPERCASE represent constants.
- When documenting interactions the standard follows "Collection; Action". for example Message; Send.
- If an item in the JSON has the nullable* comment it means that at least ONE of the nullable* fields MUST be present.
- Guidelines recommend abiding by CRUD order and wording

CRUD

## Client -> Server
### Message; Create
```json
{
  "action": "MessageSend",
  "channel": "{channel_id}",
  "content": "String",
  // nullable 
  "reply": "{message_id}",
  
}
```
### Message; Get
```json
{
  "action": "MessageGet",
  "channel": "{channel_id}",
  "message": "{message_id}"
}
```
### Message; Get Many
```json
{
  "action": "MessageGetMany",
  "channel": "{channel_id}",
}
```
### Message; Edit
note: if all fields are null the request will be ignored
```json
{
  "action": "MessageEdit",
  "message": "{message_id}",
  // nullable 
  "content": "String",
  // nullable 
  "reply": "{message_id}",
  
}
```
### Message; Delete
```json
{
  "action": "MessageDelete",
  "message": "{message_id}",
}
```
### TypeStatus
note: if typing == true in more than one channels; the oldest will be removed
```json
{
  "action": "TypeStatus",
  "typing": bool,
  "channel": "{channel_id}"
}
```
### Ping
```json
{
  "action": "Ping",
  "ping": bool,
  // nullable 
  "data": 0.0
}
```

### Friend; Add
note: this acts as sending a friend request OR accepting one
```json
{
  "action": "FriendAdd",
  // nullable?
  "user": "{user_id}",
  // nullable?
  "user_name": "{Username}"
}
```
### Friend; Get All
note: this acts as sending a friend request OR accepting one
```json
{
  "action": "FriendGetAll",
}
```

### Friend; Remove
note: this acts as removing a friend OR rejecting a friend request
```json
{
  "action": "FriendRemove",
  // nullable?
  "user": "{user_id}",
  // nullable?
  "user_name": "{Username}"
}
```

### Block; Add
note: this will automatically de-friend this user
```json
{
  "action": "BlockAdd",
  "user": "{user_id}",
}

```
### Block; Get All
```json
{
  "action": "BlockGetAll",
}
```
### Block; Remove
```json
{
  "action": "BlockRemove",
  "user": "{user_id}",
}
```

