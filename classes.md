UNCA OPEN SPEC DOCUMENT

## User
```json
{
  "_id": "{user_id}",
  "username": "String",
  "display": {...},
  "descrption": String,
  // if a user is 'open' they can be DMed without a friend request
  "open": bool
}
```
## Channel
```json
{
  "_id": "{channel_id}",
  "self": bool,
  "members": ["user_id"]
}
```

## Message
```json
{
  "id": "{message_id}",
  "content": "String",
  //nullable
  "reply": "{message_id}"
}
```