UNCA OPEN SPEC DOCUMENT

### Preamble
If you've read a OPENSPEC document before you can skip this part.
- Communication is documented from the perspective of the client unless specified otherwise
- Data is represented by JSON/BSONs with comments for clarity of specifics (e.g. u16 instead of u32).
- Data {surrounded by brackets} represent variables and UPPERCASE represent constants.
- When documenting interactions the standard follows "Collection; Action". for example Message; Send.
- If an item in the JSON has the nullable* comment it means that at least ONE of the nullable* fields MUST be present.
- Guidelines recommend abiding by CRUD order and wording

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