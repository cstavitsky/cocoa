# Cocoa/iOS Demo

## Setup

In **XCode**:

Select th sentry-cocoa root folder to open the app profile:

1. Set a `SENTRY_AUTH_TOKEN` in 'Run Script' build phase.

2. sentry-cli must be installed at /usr/local/bin

3. Click the Run/play button targeting iPhone 11

4. Click on Stop to disconnect the debugger from the app in the simulator

In **Simulator**, Launch the sentry-cocoa app

## Flow/Demo

The demo app enriches every event with: Custom context, breadcrumbs, tags, user IP, extra data.

1. From the Simulator explicitly send an event to Sentry by clicking
    - **Handled Exception**
    - **Capture Message**

![Send Message](cocoa-send-message.gif)

2. For Native crashes click:

- **Crash Application**
- **UnHandled Exception**

![Native Crash / Runtime Error](cocoa-native-crash.gif)

3. Release:

- Note that the cocoa-sdk automatically creates a Release by using the build version + dist as described in the Android SDK [Release Version Format](https://docs.sentry.io/platforms/android/#release-version-format) 
- The SDK then automatically tags every event with that release version id (i.e. there is no need to explicitly set the release version ID, unless you're explicitly setting a custom release name)

4. Run Scripts:
    
    Upload the Debug Symbols to the target project and associate the commits to the release object.


## Documentation/Resources

https://docs.sentry.io/clients/cocoa/
