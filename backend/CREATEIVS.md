# Simplifying live streaming contribution - Create a Amazon IVS Channel

## [Optional] Channel Creation and Application Configuration
We provide a shell script to create your Amazon IVS Channel, you can use [this guide](https://docs.aws.amazon.com/ivs/latest/userguide/getting-started.html) if you prefer to create it using the AWS Console.
Create a Channel on Amazon Interactive Video Service:

```sh
cd simple-streaming-webapp/backend
./create_ivs_channel.sh ivs-webrtc
```
## Copy and save the ingestEndpoint, streamKey value and playbackUrl 

```
  Copy EndPoint: rtmps://{randome_id}.global-contribute.live-video.net:443/app/
  Copy StreamKey: sk_us-east-1_dffsfbff_{randome_id}
  Copy playbackUrl: https://{randome_id}.us-east-1.playback.live-video.net/api/video/v1/us-east-1.{randome_id}.channel.ranodmcode.m3u8
```






