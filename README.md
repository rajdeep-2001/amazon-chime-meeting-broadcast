# amazon-chime-meeting-broadcast

# Installation and Configuration

## MacOS

```
$brew install aws/tap/copilot-cli
gpg --verify copilot.asc /usr/local/bin/copilot
```

## Windows

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

## Adding secrets
```
copilot secret init
```
