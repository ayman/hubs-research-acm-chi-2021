# Hubs Systems Research

In this directory we're going to add some experimental features for
research. To add a plugin you really just drop it here and include it
in the root `hubs.js` document as a starting point. There is a [longer writeup 
on the logger](https://ayman.medium.com/vr-research-in-mozilla-hubs-63fd3002eedf)
on Medium.

## about this snapshot 
The code here is a snapshot of the full [bespoke Mozilla Hubs
Client](https://github.com/ayman/hubs/blob/hubs-cloud/src/systems/research/README.md)
for data collection. Each client sends data packages to another server
which simply logs a HTTP POST request to a file, see [line
118](https://github.com/ayman/hubs-research-acm-chi-2021/blob/eb0001fb2f7a8a7fd85506150b86ab0a7a074469/1.HubsLogger/research-logger.js#L118)
of the `research-logger.js`.  The server logger, while not complex, is
not included here and can be written in any number of languages.

## research-logger

This is a client side logger where user location and actions (but not
chat) is sent to a third party server for collection.  This is to
relieve network load on the [janus server](https://bit.ly/3ckvqui
"Discord discussion").  You'll need to set up your own server for
collection and make sure you set the content-security-policy in your
Hubs as well as CORS on your data server.

### schema
We record the POST data as:
```
{
    info: [...],
    data: [[tick1], [tick2]]
}
```
For the `info`:
```
    getUUID(),
    timestamp, // post time
    window.APP.store.credentialsAccountId !== null ? window.APP.store.credentialsAccountId : "",
    window.APP.store.state.profile.avatarId,
    avatarRig.components["player-info"].identityName,
    avatarRig.components["player-info"].displayName,
    avatarRig.components["player-info"].isRecording,
    avatarRig.components["player-info"].isOwner,
    detectOS(navigator.userAgent),
    AFRAME.utils.device.isBrowserEnvironment ? 1 : 0,
    AFRAME.utils.device.checkARSupport() ? 1 : 0,
    AFRAME.utils.device.checkHeadsetConnected() ? 1 : 0,
    AFRAME.utils.device.isIOS() ? 1 : 0,
    AFRAME.utils.device.isLandscape() ? 1 : 0,
    AFRAME.utils.device.isMobile() ? 1 : 0,
    AFRAME.utils.device.isMobileVR() ? 1 : 0,
    AFRAME.utils.device.isOculusBrowser() ? 1 : 0,
    AFRAME.utils.device.isR7() ? 1 : 0,
    AFRAME.utils.device.isTablet() ? 1 : 0,
    AFRAME.utils.device.isWebXRAvailable ? 1 : 0
```

For each data tick we will log an array line of a csv:
```
        timestamp,
        AFRAME.scenes[0].ownerDocument.location.pathname,
        AFRAME.scenes[0].ownerDocument.location.search,
        rigPosition.x,
        rigPosition.y,
        rigPosition.z,
        povPosition.x,
        povPosition.y,
        povPosition.z,
        rigQuant._x,
        rigQuant._y,
        rigQuant._z,
        rigQuant._w,
        povQuant._x,
        povQuant._y,
        povQuant._z,
        povQuant._w,
        rigDirection.x,
        rigDirection.y,
        rigDirection.z,
        povDirection.x,
        povDirection.y,
        povDirection.z,
        AFRAME.scenes[0].systems["hubs-systems"].characterController.fly ? 1 : 0,
        AFRAME.scenes[0].states.includes("spacebubble") ? 1 : 0,
        AFRAME.scenes[0].states.includes("visible") ? 1 : 0,
        AFRAME.scenes[0].states.includes("loaded") ? 1 : 0,
        AFRAME.scenes[0].states.includes("entered") ? 1 : 0,
        AFRAME.scenes[0].states.includes("muted") ? 1 : 0,
        this.lastFPS,
        AFRAME.scenes[0].systems["local-audio-analyser"].volume,
        window.APP.store.state.preferences.audioOutputMode === "audio" ? 1 : 0
```

I think this is the proper orientation:
`document.getElementById('avatar-pov-node').object3D.getWorldQuaternion();`
which is the `rigQuant` above.

## Licenses
This *code* is released under [Mozilla Public License
2.0](https://github.com/ayman/hubs-research-2021/blob/main/LICENSE).
