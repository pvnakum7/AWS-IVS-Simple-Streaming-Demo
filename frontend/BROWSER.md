# Simplifying live streaming contribution - Customize the APP

## Use the video MediaDevices.getUserMedia() instead of the Canvas element

Due to browser compatibility, the video track has been wrapped into a canvas element, but it can impact on the video quality, if Chrome is the preferable browser, you can capture the stream using the video html component instead.

You should change the file frontend/src/components/HomePage.js 
The affected function is handleCameraReady()

Currently its using the element canvasVideo, change to use the video.

You also need to change the function function startStream, to avoid audio duplication.
Remove the audioStreaming from the Array in the forEach function.



## Change local app to stream to remote container

The app is currently configure to take in consideration the protocol used, and if it's http, then set the local host as the endpoint. You can replace the testServer by the server, to stream to the remote server from your local machine.



## Additional information:

* [HTMLCanvasElement](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement)
* [HTMLMediaElement](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement)

