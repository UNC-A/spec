UNCA OPEN SPEC DOCUMENT


## Client -> Server

### Message; Send
```json
{
  "action": "MessageSend",
  "content": "String",
  "channel": "{channel_id}",
}
```
### TypeStatus
note: if typing == true in more than one channels; the oldest will be removed
```json
{
  "action": "TypeStatus",
  "typing"?: true,
  "channel": "{channel_id}"
}
```
### Ping
```json
{
  "action": "Ping",
  "data"?: 0.0
}
```
