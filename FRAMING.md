# Framing

The way I intend on sending data back and forth between the client and server is just by throwing around a bunch of JSON! *laughs nervously* <br>
Example: The server sending data to a client
```json
{
  "messagetype": 1,
  "for": 0
  "from": 0,
  "date": "This is a test"
}
```

## Messagetype
Messagetype is what to client/server is sending. A string message, a message with other data for auth, or maybe even a binary data, for some reason.
```cs
enum MessageType {
  STRING=0,
  DATA,
  BINARY
}
```

## For
This will be used for what the message is for, a broadcast from the server, the client sending a message, auth, or a lot of other things
```cs
enum MessageFor {
  CLIENT_MESSAGE=0,
  SERVER_MESSAGE,
  SERVER_AUTH,
  CLIENT_AUTH
}
```

## From 
Where the message originated, like the server or client. But both can do some checking to make sure its coming from the authenticated source

## Data
This is where the meat of the commucation is, holds the string for a string message, binary, string message along with metadata.

## Conclusion
The reason why this file is so small right now I becuase I dont exactly know what I need. This file will change as I get more comfortable with client/server 
relationships.
