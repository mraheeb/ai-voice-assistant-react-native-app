<img src="./.github/assets/icon.png" alt="Voice Assistant App Icon" width="100" height="100">

# React-Native Voice Assistant

This is an app connector for the project [AI Voice Assistant For The Elderly](https://github.com/RashadAR/ai-voice-assistant)

## Getting started

The easiest way to get this app running is with the [Sandbox for LiveKit Cloud](https://cloud.livekit.io/projects/p_/sandbox) and the [LiveKit CLI](https://docs.livekit.io/home/cli/cli-setup/).

We'll use [EAS build](https://docs.expo.dev/build/introduction/) from expo to compile relevant [builds](https://docs.expo.dev/build-reference/apk/)

First, create a new [Sandbox Token Server](https://cloud.livekit.io/projects/) for your LiveKit Cloud project from the sandbox templates and grab the sandbox id.

Then, run the following command to automatically clone this template and connect it to LiveKit Cloud:

```bash
lk app create --template-url https://github.com/mraheeb/ai-voice-assistant-react-native-app --sandbox <token_server_sandbox_id>
```

Afterwards, move to the newly created folder and run the following commands:

```bash
# EAS installation
npm install -g eas-cli

# Configure the project, you'll be prompted for login
eas build:configure

# For development builds
npx expo install expo-dev-client

# Run a build with profiles (no flag might yield AAB)
eas build --platform android --profile development

# Install General Packages
npm install

# Android
npx expo start

```

You'll also need an agent to speak with. [AI Voice Assistant For The Elderly](https://github.com/RashadAR/ai-voice-assistant)

> [!NOTE]
> To setup without the LiveKit CLI, clone the repository and edit the `hooks/useConnectionDetails.ts` file to add either a `sandboxID` (if using a [Sandbox Token Server](https://cloud.livekit.io/projects/p_/sandbox/templates/token-server)), or a [manually generated](#token-generation) URL and token.
> You'll also need to clone and run the agent


## Token generation

In a production environment, you will be responsible for developing a solution to [generate tokens for your users](https://docs.livekit.io/home/server/generating-tokens/) which is integrated with your authentication solution. You should disable your sandbox token server and modify `hooks/useConnectionDetails.ts` to use your own token server.


