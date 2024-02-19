UNCA OPEN SPEC DOCUMENT

## Server -> Client


### Establish
Sent ONCE on websocket startup
```json
{
  "users": [
    {
      "_id": "{user_id}",
      "username": "String"
    }
  ],
  "channels": [
    {
      "_id": "{channel_id}",
      "members": ["{user_id}"]
    }
  ]
}
```
### Message; Send
```json
{
  "action": "MessageSend",
  "_id": "{message_id}",
  "author": "{user_id}",
  "content": "String",
  "reply"?: "{message_id}",
  "channel": "{channel_id}",
}
```
### TypeStatus
note: if typing == true in more than one channels; the oldest will be removed
```json
{
  "action": "TypeStatus",
  "typing"?: true,
  "channel": "{channel_id}",
  "user": "{user_id}"
}
```
### Pong
```json
{
  "action": "Ping",
  // nullable 
  "data"?: 0
}
```