# Notes on writing an SDK for Emitter

From the point of view of a client application, Emitter behaves exaclty like any MQTT brokers. Therefore, Emitter SDKs are merely light wrappers around some pre-existing MQTT lib. The role of the SDK is to simplify as much as possible the communication with the Emitter broker, so that - for example - the following code...

```
var emitter = emitter.connect(); 
var key = 'LyOL3fhQDfOKyB6PWNkv6vemLSPjP8hg';

emitter.publish({
  key: key,
  channel: "testChannel,
  message: JSON.stringify({
    id: 1,
    text: "message"
    })
});
```

...is really all it takes for a Javascript app to start a connection with Emitter and send a message.
