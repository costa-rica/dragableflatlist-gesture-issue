# App crashes when GestureHandler is triggered alongside DraggableFlatList

## Description

When trying to use react-native-draggable-flatlist and react-native-gesture-handler in the same application, the app crashes.

I do not know what this issue is between the two I just know that individually they both run fine, but if the packages are introduced to the same application and the GestureHandler is triggered the app crashes.

## Expected vs. Actual behavior

- Expected: tapping gesture should not cause the app to crash.
- Actual: tapping gesture causes the app to crash.

## Steps to reproduce

### Step 1: Create react native project

`sudo npx create-expo-app@latest --template`

- chose blank
- delete /node_modules
- delete package-lock.json
- yarn install

### Step 2: Add dependencies

- yarn add react-native-draggable-flatlist
- yarn add react-native-gesture-handler
- yarn add react-native-reanimated

### Step 3: Downgrade dependencies

Downgrade dependencies was the only way I could get the app to run.

- yarn add react-native-reanimated@~3.17.4
- yarn add react-native-gesture-handler@~2.24.0
- yarn add react-native@0.79.5

### Step 4: Run the app

- yarn start

## Video of crash

<img src="https://1drv.ms/i/c/60df6d5feed7ac60/IQSkR-5tbPN-RLQ5VVSJUPmyAUGAmSOBNZTMNSNQuz44cYI?width=1024" width="1024" height="auto" />

## Crash report

https://1drv.ms/t/c/60df6d5feed7ac60/Eemphyuq-8hGltN_hpNxC4IBBmaJZjpQRTZI-Hl0enRlzw?e=BzDmCW

## Environment

```
  expo-env-info 1.3.4 environment info:
    System:
      OS: macOS 15.6.1
      Shell: 5.9 - /bin/zsh
    Binaries:
      Node: 22.18.0 - ~/.nvm/versions/node/v22.18.0/bin/node
      Yarn: 1.22.22 - ~/.nvm/versions/node/v22.18.0/bin/yarn
      npm: 10.9.3 - ~/.nvm/versions/node/v22.18.0/bin/npm
    Managers:
      CocoaPods: 1.16.2 - /opt/homebrew/bin/pod
    SDKs:
      iOS SDK:
        Platforms: DriverKit 24.5, iOS 18.5, macOS 15.5, tvOS 18.5, visionOS 2.5, watchOS 11.5
    IDEs:
      Xcode: 16.4/16F6 - /usr/bin/xcodebuild
    npmPackages:
      expo: ~53.0.22 => 53.0.22
      react: 19.0.0 => 19.0.0
      react-native: 0.79.5 => 0.79.5
    npmGlobalPackages:
      eas-cli: 16.17.4
    Expo Workflow: managed
```
