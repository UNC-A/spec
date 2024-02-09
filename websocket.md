UNCA OPEN SPEC DOCUMENT

### Preamble
If you've read a OPENSPEC document before you can skip this part.
- Communication is documented from the perspective of the client unless specified otherwise data is represented by JSON/BSONs with comments for clarity of specifics (e.g. u16 instead of u32).
- Data {surronded by brackets} reperesent variables and UPPERCASE represent constants.
- When documenting interactions the standard follows "Collection; Action". for example Message; Send.
- If an item in the JSON has the nullable* comment it means that at least ONE of the nullable* fields MUST be present.


## Client -> Server
### Message; Send
```json
{
  "action": "MessageSend",
  "channel_id": "String",
  "content": "String",
  // nullable 
  "reply": "String",
  
}
```
### Message; Edit
note: if all fields are null the request will be ignored
```json
{
  "action": "MessageEdit",
  "_id": "String",
  // nullable 
  "content": "String",
  // nullable 
  "reply": "String",
  
}
```
### Message; Delete
```json
{
  "action": "MessageDelete",
  "_id": "String",
}
```
### TypeStatus
note: if typing == true in more than one channels; the oldest will be removed
```json
{
  "action": "TypeStatus",
  "typing": bool,
  "channel_id": "String"
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
  "user_id": "String",
  // nullable?
  "user_name": "String"
}
```

### Friend; Remove
note: this acts as removing a friend OR rejecting a friend request
#### Varient-1
```json
{
  "action": "FriendRemove",
  // nullable?
  "user_id": "String",
  // nullable?
  "user_name": "String"
}
```
