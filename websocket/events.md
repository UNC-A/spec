UNCA OPEN SPEC DOCUMENT

## Server -> Client
### Establish
runs at the start of a WS instance
Establish can be manually triggered if the user believes that their current information is out of date with the server
```json
{
  "action": "Establish",
  "channels": "[...]",
  "users": "[...]",
  "messages": "[...]"
}
```

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
  "channel": "{channel_id}",
  "user": "{user_id}"
}
```
### Pong
```json
{
  "action": "Ping",
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

### Block; Remove
```json
{
  "action": "BlockRemove",
  "user": "{user_id}",
}
```
### Channel; Create
```json
{
  "action": "ChannelCreate",
  "channel": {...}
}
```

### Channel; Remove
```json
{
  "action": "ChannelRemove",
  "user": "{user_id}",
}
```