# amazon-chime-meeting-broadcast

This repository contains a Docker container that, when started, will join an Amazon Chime meeting by PIN and broadcast the meeting's audio and video in high definition (1080p at 30fps) to an RTMP endpoint you specify. The broadcast participant joins the meeting in the muted state. The meeting PIN must be unlocked in order for the broadcast participant to join the meeting.

## Prerequisites

You will need AWSCLI installed and configured in your terminal.

## Copilot - Installation and Configuration

### MacOS

```
$brew install aws/tap/copilot-cli
gpg --verify copilot.asc /usr/local/bin/copilot
```

### Windows - Use <Power-Shell>

```
Invoke-WebRequest -OutFile 'C:\Program Files\copilot.exe' https://github.com/aws/copilot-cli/releases/latest/download/copilot-windows.exe
gpg --verify ecs-cli.asc 'C:\Program Files\copilot.exe'
```

## Initialize Application and Job. Use <Power-Shell>
```
New-Alias -Name "copilot" copilot-windows
copilot init
```
Application name: amazon-chime-meeting-broadcast
Workload type: Backend Service
Job name: amazon-chime-meeting-broadcast
Dockerfile: Use an existing image instead

## Initialize Environment
```
copilot env init
```
Environment name: dev
Credential source: [profile default]
Default environment configuration? Yes, use default.

## Deploy your environment.
```
copilot env deploy --name dev
```

## Redeploying after a configuration change
```
copilot deploy
```

## Create secrets
```
copilot secret init
```
* `MEETING_URL`: Chime Meeting URL (without any spaces in it)
  * Example(If you want to record Chime): `https://app.chime.aws/portal/<your Meeting ID here>`
  * Example(Hosted [Chime SDK Serverless Demo](https://github.com/aws/amazon-chime-sdk-js/tree/master/demos/serverless) URL): `<Hosted Chime URL>/?m=<Meeting ID>&broadcast=true`
* `RTMP_URL`: the URL of the RTMP endpoint,
  * Twitch example: `rtmp://live.twitch.tv/app/<stream key>`
  * YouTube Live example: `rtmp://a.rtmp.youtube.com/live2/<stream key>`
