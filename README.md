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

## The choice of the MQTT library

Most SDKs developped by our team are based on MQTT libs distributed by the [Eclipse Paho project](http://www.eclipse.org/paho/). This project provide an implementation for most mainstream language, like C#, Java, Python, C, C++, ... But you'll easily find MQTT libs for almost any languages, and you are free to choose any implementation of MQTT in accordance with you requirements. For example, although the Paho project provide a embedded C implementation, you might


