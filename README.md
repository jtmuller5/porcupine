# Porcupine

[![GitHub release](https://img.shields.io/github/release/Picovoice/Porcupine.svg)](https://github.com/Picovoice/Porcupine/releases)

Made in Vancouver, Canada by [Picovoice](https://picovoice.ai)

Porcupine is a highly-accurate and lightweight wake word engine. It enables building always-listening voice-enabled
applications. It is

- using deep neural networks trained in real-world environments.
- compact and computationally-efficient. It is perfect for IoT.
- cross-platform. Raspberry Pi, BeagleBone, Arm Cortex-M, Android, iOS, Linux (x86_64), macOS (x86_64), Windows (x86_64), and web
  browsers are supported.
- scalable. It can detect multiple always-listening voice commands with no added runtime footprint.
- self-service. Developers can train custom wake word models using [Picovoice Console](https://picovoice.ai/console/).

> Porcupine wake word models for all major voice assistants (`Alexa`, `Hey Google`, `Ok Google`, and `Hey Siri`) are
> available for free (under Apache 2.0) in this repo.

## Table of Contents

- [Porcupine](#porcupine)
  - [Table of Contents](#table-of-contents)
  - [License & Terms](#license--terms)
  - [Use Cases](#use-cases)
  - [Try It Out](#try-it-out)
  - [Language Support](#language-support)
  - [Performance](#performance)
  - [Demos](#demos)
    - [Python](#python-demos)
    - [.NET](#net-demos)
    - [Java](#java-demos)
    - [Unity](#unity-demos)
    - [Flutter](#flutter-demos)
    - [React Native](#react-native-demos)
    - [Android](#android-demos)
    - [iOS](#ios-demos)
    - [Web](#web-demos)
      - [Vanilla JavaScript and HTML](#vanilla-javascript-and-html)
      - [Angular](#angular-demos)
      - [React](#react-demos)
      - [Vue](#vue-demos)
    - [NodeJS](#nodejs-demos)
    - [C](#c-demos)
    - [Microcontroller](#microcontroller-demos)
  - [SDKs](#sdks)
    - [Python](#python)
    - [.NET](#net)
    - [Java](#java)
    - [Unity](#unity)
    - [Flutter](#flutter)
    - [React Native](#react-native)
    - [Android](#android)
    - [iOS](#ios)
    - [Web](#web)
      - [Vanilla JavaScript and HTML (CDN Script Tag)](#vanilla-javascript-and-html-cdn-script-tag)
      - [Vanilla JavaScript and HTML (ES Modules)](#vanilla-javascript-and-html-es-modules)
      - [Angular](#angular)
      - [React](#react)
      - [Vue](#vue)
    - [NodeJS](#nodejs)
    - [C](#c)
    - [Microcontroller](#microcontroller)
  - [Releases](#releases)
  - [FAQ](#faq)

## License & Terms

Porcupine SDK is free and licensed under Apache 2.0 including the [models](/resources/keyword_files) released within the
repository. [Picovoice Console](https://picovoice.ai/console/) offers two types of subscriptions: Personal and Enterprise.
Personal accounts can train custom wake word models that run on x86_64, subject to limitations and strictly for
non-commercial purposes. Personal accounts empower researchers, hobbyists, and tinkerers to experiment. Enterprise
accounts can unlock all capabilities of Picovoice Console, are permitted for use in commercial settings, and have a path
to graduate to commercial distribution[<sup>\*</sup>](https://picovoice.ai/pricing/).

## Use Cases

Porcupine is the right product if you need to detect one or a few static (always-listening) voice commands.

- If you want to create voice experiences similar to Alexa or Google, see the
  [Picovoice platform](https://github.com/Picovoice/picovoice).
- If you need to understand complex and naturally-spoken voice commands within a specific domain, see the
  [Rhino Speech-to-Intent engine](https://github.com/Picovoice/rhino).

## Try It Out

- [Interactive Web Demo](https://picovoice.ai/demos/lamp/)

- [Android Demo Application](https://play.google.com/store/apps/details?id=ai.picovoice.porcupine.demo&hl=en)

- Porcupine on a Raspberry Pi Zero

[![Porcupine in Action](https://img.youtube.com/vi/Fi_IJEcNr3I/0.jpg)](https://www.youtube.com/watch?v=Fi_IJEcNr3I)

## Language Support

- English, German, French, and Spansih.
- Support for additional languages is available for commercial customers on a case-by-case basis.

## Performance

A comparison between accuracy and runtime metrics of Porcupine and two other widely-used libraries, PocketSphinx and
Snowboy, is provided [here](https://github.com/Picovoice/wakeword-benchmark). Compared to the best-performing engine of
these two, Porcupine is **6.0 times more accurate** and **6.5 times faster** (on Raspberry Pi 3).

## Demos

### Python Demos

Install [PyAudio](https://people.csail.mit.edu/hubert/pyaudio/) and then the demo package:

```console
sudo pip3 install pvporcupinedemo
```

With a working microphone connected to your device run the following in the terminal:

```console
porcupine_demo_mic --keywords porcupine
```

The engine starts processing the audio input from the microphone in realtime and outputs to the terminal when it detects
utterances of `Porcupine`.

For more information about Python demos go to [demo/python](/demo/python).

### .NET Demos

Install [OpenAL](https://openal.org/) and then from [demo/dotnet/PorcupineDemo](/demo/dotnet/PorcupineDemo) run the
following in the terminal to build the demo:

```console
dotnet build -c MicDemo.Release
```

Make sure there is a working microphone connected to your device. From [demo/dotnet/PorcupineDemo](/demo/dotnet/PorcupineDemo) run the
following in the terminal:

```console
dotnet run -c MicDemo.Release -- --keywords porcupine
```

The engine starts processing the audio input from the microphone in realtime and outputs to the terminal when it detects
utterances of `Porcupine`.

For more information about .NET demos go to [demo/dotnet](/demo/dotnet).

### Java Demos

Make sure there is a working microphone connected to your device. From the root of the repository, run the following command from the terminal:

```console
java -jar demo/java/bin/porcupine-mic-demo.jar -k porcupine
```

The engine starts processing the audio input from the microphone in realtime and outputs to the terminal when it detects
utterances of `Porcupine`.

For more information about Java demos go to [demo/java](/demo/java).

### Unity Demos

To run the Porcupine Unity demo, import the [Porcupine Unity package](/binding/unity/porcupine.unitypackage) into your project, open the PorcupineDemo scene and hit play. To run on other platforms or in the player, go to _File > Build Settings_, choose your platform and hit the `Build and Run` button.

To browse the demo source go to [demo/unity](/demo/unity).

### Flutter Demos

To run the Porcupine demo on Android or iOS with Flutter, you must have the [Flutter SDK](https://flutter.dev/docs/get-started/install) installed on your system. Once installed, you can run `flutter doctor` to determine any other missing requirements for your relevant platform. Once your environment has been set up, launch a simulator or connect an Android/iOS device.

Run the following command from [demo/flutter](/demo/flutter) to build and deploy the demo to your device:

```console
flutter run
```

### React Native Demos

To run the React Native Porcupine demo app you will first need to setup your React Native environment. For this,
please refer to [React Native's documentation](https://reactnative.dev/docs/environment-setup). Once your environment has
been set up, navigate to [demo/react-native](/demo/react-native) to run the following commands:

For Android:

```console
yarn android-install    # sets up environment
yarn android-run        # builds and deploys to Android
```

For iOS:

```console
yarn ios-install        # sets up environment
yarn ios-run            # builds and deploys to iOS
```

### Android Demos

Using [Android Studio](https://developer.android.com/studio/index.html), open
[demo/android/Activity](/demo/android/Activity) as an Android project and then run the application.

To learn about how to use Porcupine in long running services go to [demo/android/Service](/demo/android/Service).

### iOS Demos

Before building the demo app, run the following from this directory to install the Porcupine-iOS Cocoapod:
```ruby
pod install
```

Then, using [Xcode](https://developer.apple.com/xcode/), open the generated `PorcupineDemo.xcworkspace` and run the application.

### Web Demos

#### Vanilla JavaScript and HTML

From [demo/web](/demo/web) run the following in the terminal:

```console
yarn
yarn start
```

(or)

```console
npm install
npm run start
```

Open http://localhost:5000 in your browser to try the demo.

#### Angular Demos

From [demo/angular](/demo/angular) run the following in the terminal:

```console
yarn
yarn start
```

(or)

```console
npm install
npm run start
```

Open http://localhost:4200 in your browser to try the demo.

#### React Demos

From [demo/react](/demo/react) run the following in the terminal:

```console
yarn
yarn start
```

(or)

```console
npm install
npm run start
```

Open http://localhost:3000 in your browser to try the demo.

#### Vue Demos

From [demo/vue](/demo/vue) run the following in the terminal:

```console
yarn
yarn serve
```

(or)

```console
npm install
npm run serve
```

Open http://localhost:8080 in your browser to try the demo.

### NodeJS Demos

Install [node-record-lpcm16](https://www.npmjs.com/package/node-record-lpcm16) NPM package and follow the instructions
there for setting up your microphone. Then install the demo package:

```console
yarn global add @picovoice/porcupine-node-demo
```

With a working microphone connected to your device run the following in the terminal:

```console
ppn-mic-demo --keywords porcupine
```

The engine starts processing the audio input from the microphone in realtime and outputs to the terminal when it detects
utterances of `Porcupine`.

For more information about NodeJS demos go to [demo/nodejs](/demo/nodejs).

### C Demos

[Microphone demo](/demo/c/porcupine_demo_mic.c) runs on Linux-based systems (e.g. Ubuntu, Raspberry Pi, and BeagleBone).
Build the demo:

```console
gcc -std=c99 -O3 -o demo/c/porcupine_demo_mic \
-I include/ demo/c/porcupine_demo_mic.c -ldl -lasound
```

Find the name of audio input device (microphone) on your computer using `arecord -L` and then from the root of the
repository run the demo:

```console
./demo/c/porcupine_demo_mic ${LIBRARY_PATH} lib/common/porcupine_params.pv \
resources/keyword_files/${SYSTEM}/porcupine_${SYSTEM}.ppn 0.5 ${INPUT_AUDIO_DEVICE}
```

Replace `${LIBRARY_PATH}` with path to appropriate library available under [lib](/lib), `${SYSTEM}` with the
name of the platform you are running on (`linux`, `raspberry-pi`, or `beaglebone`), and `${INPUT_AUDIO_DEVICE}` with
the name of your microphone device. The demo opens an audio stream and detects utterances of `Porcupine`.

For more information about C demos go to [demo/c](/demo/c).

### Microcontroller Demos

There are several projects for various development boards inside the [mcu demo](./demo/mcu) folder.

## SDKs

### Python

Install the Python SDK:

```console
pip3 install pvporcupine
```

The SDK exposes a factory method to create instances of the engine:

```python
import pvporcupine

handle = pvporcupine.create(keywords=['picovoice', 'bumblebee'])
```

`keywords` argument is a shorthand for accessing default keyword files shipped with the library. The default keyword
files available can be retrieved via

```python
import pvporcupine

print(pvporcupine.KEYWORDS)
```

If you wish to use a non-default keyword file you need to identify its path:

```python
import pvporcupine

handle = pvporcupine.create(keyword_paths=['path/to/non/default/keyword/file'])
```

When initialized, valid sample rate can be obtained using `handle.sample_rate`. The required frame length
(number of audio samples in an input array) is `handle.frame_length`. The object can be used to monitor
incoming audio as follows:

```python
import pvporcupine

handle = pvporcupine.create(keywords=['porcupine'])

def get_next_audio_frame():
    pass

while True:
    keyword_index = handle.process(get_next_audio_frame())
    if keyword_index >= 0:
        # Insert detection event callback here
        pass
```

Finally, when done be sure to explicitly release the resources using `handle.delete()`.

### .NET

Install the .NET SDK using NuGet or the dotnet CLI:

```console
dotnet add package Porcupine
```

The SDK exposes a factory method to create instances of the engine:

```csharp
using Pv

Porcupine handle = Porcupine.Create(keywords: new List<string> { "picovoice" });
```

The `keywords` argument is a shorthand for accessing built-in keyword files shipped with the library. The built-in keyword
files available can be retrieved via:

```csharp
using Pv

foreach (string keyword in Porcupine.KEYWORDS)
{
    Console.WriteLine(keyword);
}
```

If you wish to use a custom keyword file (i.e. a keyword file generated by Picovoice Console, with a `.ppn` extension), you need to specify its path:

```csharp
using Pv

Porcupine handle = Porcupine.Create(
    keywordPaths: new List<string>{ "path/to/custom/keyword/file"});
```

When initialized, the required sample rate can be obtained using `handle.SampleRate`. Expected frame length
(number of audio samples in an input array) is `handle.FrameLength`. The object can be used to monitor
incoming audio as below:

```csharp
short[] getNextAudioFrame()
{
    // .. get a frame of audio
    return audioFrame;
}

while(true)
{
    var keywordIndex = handle.Process(getNextAudioFrame())
    if(keywordIndex >= 0)
    {
        // .. Insert detection event callback here
    }
}
```

Porcupine will have its resources freed by the garbage collector, but to have resources freed immediately after use,
wrap it in a `using` statement:

```csharp
using(Porcupine handle = Porcupine.Create(keywords: new List<string> { "picovoice" }))
{
    // .. Porcupine usage here
}
```

### Java

Install the Porcupine Java binding by downloading and referencing the latest Porcupine JAR file available
[here](/binding/java/bin). The SDK exposes a builder to create instances of the engine:

```java
import ai.picovoice.porcupine.*;

try{
    Porcupine handle = new Porcupine.Builder()
                        .setKeyword("picovoice")
                        .build();
} catch (PorcupineException e) { }
```

The `setKeyword()` builder argument is a shorthand for accessing built-in keyword model files shipped with the package.

The built-in keyword files available can be retrieved via:

```java
import ai.picovoice.porcupine.*;

for(String keyword : Porcupine.KEYWORDS){
    System.out.println(keyword);
}
```

If you wish to use a custom keyword file (i.e. a keyword file generated by Picovoice Console, with a `.ppn` extension) you need to the file path as demonstrated below:

```java
import ai.picovoice.porcupine.*;

try{
    Porcupine handle = new Porcupine.Builder()
                        .setKeywordPath("path/to/custom/keyword/file")
                        .build();
} catch (PorcupineException e) { }
```

When initialized, valid sample rate can be obtained using `handle.getSampleRate()`. Expected frame length
(number of audio samples in an input array) is `handle.getFrameLength()`. The object can be used to monitor
incoming audio as below:

```java
short[] getNextAudioFrame(){
    // .. get audioFrame
    return audioFrame;
}

while(true){
    int keywordIndex = handle.Process(getNextAudioFrame());
    if(keywordIndex >= 0){
        // .. detection event logic/callback
    }
}
```

Once you're done with Porcupine, ensure you release its resources explicitly:

```java
handle.delete();
```

### Unity

Import the [Porcupine Unity Package](/binding/unity/porcupine.unitypackage) into your Unity project.

The SDK provides two APIs:

#### High-Level API

[PorcupineManager](/binding/unity/Assets/Porcupine/PorcupineManager.cs) provides a high-level API that takes care of audio recording. This is the quickest way to get started.

The static constructor `PorcupineManager.FromKeywords` will create an instance of the `PorcupineManager` using one or more of the built-in keywords.

```csharp
using Pv.Unity;

try {
    List<string> keywords = new List<string>(){ "picovoice", "porcupine" };
    PorcupineManager _porcupineManager = PorcupineManager.FromKeywords(
                                            keywords,
                                            OnWakeWordDetected);
}
catch (Exception ex)
{
    // handle porcupine init error
}
```

To create an instance of PorcupineManager that detects custom keywords, you can use the `PorcupineManager.FromKeywordPaths`
static constructor and provide the paths to the `.ppn` file(s).

```csharp
List<string> keywordPaths = new List<string>(){ "/path/to/keyword.ppn" };
PorcupineManager _porcupineManager = PorcupineManager.FromKeywordPaths(
                                        keywordPaths,
                                        OnWakeWordDetected);
```

Once you have instantiated a PorcupineManager, you can start/stop audio capture and wake word detection by calling:

```csharp
_porcupineManager.Start();
// .. use porcupine
_porcupineManager.Stop();
```

Once the app is done with using PorcupineManager, you can explicitly release the resources allocated to Porcupine:

```csharp
_porcupineManager.Delete();
```

There is no need to deal with audio capture to enable wake word detection with PorcupineManager.
This is because it uses our
[unity-voice-processor](https://github.com/Picovoice/unity-voice-processor/)
Unity package to capture frames of audio and automatically pass it to the wake word engine.

#### Low-Level API

[Porcupine](/binding/unity/Assets/Porcupine/Porcupine.cs) provides low-level access to the wake word engine for those who want to incorporate wake word detection into a already existing audio processing pipeline. To create an instance of `Porcupine`, use the `.Create` static constructor.

```csharp
using Pv.Unity;

try
{
    List<string> keywords = new List<string>(){ "porcupine", "picovoice" };
    Porcupine _porcupine = Porcupine.Create(keywords: keywords);
}
catch (Exception ex)
{
    // handle porcupine init error
}
```

To search for a keyword in audio, you must pass frames of audio to Porcupine using the `Process` function. The `keywordIndex` returned will either be -1 if no detection was made or an integer specifying which keyword was detected.

```csharp
short[] frame = getAudioFrame();

try
{
    int keywordIndex = _porcupine.Process(frame);
    if (keywordIndex >= 0)
    {
        // detection made!
    }
}
catch (Exception ex)
{
    Debug.LogError(ex.ToString());
}
```

For `Process` to work correctly, the provided audio must be single-channel and 16-bit linearly-encoded.

Finally, once you no longer need the wake word engine, you can explicitly release the resources allocated to Porcupine:

```csharp
_porcupine.Dispose();
```

### Flutter

Add the [Porcupine Flutter plugin](https://pub.dev/packages/porcupine) to your pub.yaml.

```yaml
dependencies:
  porcupine: ^<version>
```

The SDK provides two APIs:

#### High-Level API

[PorcupineManager](/binding/flutter/lib/porcupine_manager.dart) provides a high-level API that takes care of audio recording. This class is the quickest way to get started.

The static constructor `PorcupineManager.fromKeywords` will create an instance of the `PorcupineManager` using one or more of the built-in keywords.

```dart
import 'package:porcupine/porcupine_manager.dart';
import 'package:porcupine/porcupine_error.dart';

void createPorcupineManager() async {
    try{
        _porcupineManager = await PorcupineManager.fromKeywords(
            ["picovoice", "porcupine"],
            _wakeWordCallback);
    } on PvError catch (err) {
        // handle porcupine init error
    }
}
```

To create an instance of PorcupineManager that detects custom keywords, you can use the `PorcupineManager.fromKeywordPaths` static constructor and provide the paths to the `.ppn` file(s).

```dart
_porcupineManager = await PorcupineManager.fromKeywordPaths(
    ["/path/to/keyword.ppn"],
    _wakeWordCallback);
```

Once you have instantiated a PorcupineManager, you can start/stop audio capture and wake word detection by calling:

```dart
try{
    await _porcupineManager.start();
} on PvAudioException catch (ex) {
    // deal with either audio exception
}
// .. use porcupine
await _porcupineManager.stop();
```

Once the app is done with using PorcupineManager, be sure you explicitly release the resources allocated to Porcupine:

```dart
await _porcupineManager.delete();
```

There is no need to deal with audio capture to enable wake word detection with PorcupineManager.
This is because it uses [flutter_voice_processor](https://github.com/Picovoice/flutter-voice-processor/) plugin to capture frames of audio and automatically pass it to the wake word engine.

#### Low-Level API

[Porcupine](/binding/flutter/lib/porcupine.dart) provides low-level access to the wake word engine for those who want to incorporate wake word detection into a already existing audio processing pipeline.`Porcupine` has `fromKeywords` and `fromKeywordPaths` static constructors.

```dart
import 'package:porcupine/porcupine_manager.dart';
import 'package:porcupine/porcupine_error.dart';

void createPorcupine() async {
    try{
        _porcupine = await Porcupine.fromKeywords(["picovoice"]);
    } on PvError catch (err) {
        // handle porcupine init error
    }
}
```

To search for a keyword in audio, you must pass frames of audio to Porcupine using the `process` function. The `keywordIndex` returned will either be -1 if no detection was made or an integer specifying which keyword was detected.

```dart
List<int> buffer = getAudioFrame();

try {
    int keywordIndex = _porcupine.process(buffer);
    if (keywordIndex >= 0) {
        // detection made!
    }
} on PvError catch (error) {
    // handle error
}
```

For `process` to work correctly, the provided audio must be single-channel and 16-bit linearly-encoded.

Finally, once you no longer need the wake word engine, be sure to explicitly release the resources allocated to Porcupine:

```dart
_porcupine.delete();
```

### React Native

Install [@picovoice/react-native-voice-processor](https://www.npmjs.com/package/@picovoice/react-native-voice-processor)
and [@picovoice/porcupine-react-native](https://www.npmjs.com/package/@picovoice/porcupine-react-native). The SDK
provides two APIs:

#### High-Level API

[PorcupineManager](/binding/react-native/src/porcupinemanager.tsx) provides a high-level API that takes care of
audio recording. This class is the quickest way to get started.

Using the constructor `PorcupineManager.fromKeywords` will create an instance of the `PorcupineManager`
using one or more of the built-in keywords.

```javascript
async createPorcupineManager(){
    try{
        this._porcupineManager = await PorcupineManager.fromKeywords(
            ["picovoice", "porcupine"],
            detectionCallback);
    } catch (err) {
        // handle error
    }
}
```

To create an instance of PorcupineManager that detects custom keywords, you can use the `PorcupineManager.fromKeywordPaths`
static constructor and provide the paths to the `.ppn` file(s).

```javascript
this._porcupineManager = await PorcupineManager.fromKeywords(
  ["/path/to/keyword.ppn"],
  detectionCallback
);
```

Once you have instantiated a Porcupine manager, you can start/stop audio capture and wake word detection by calling:

```javascript
let didStart = this._porcupineManager.start();
// .. use Porcupine
let didStop = this._porcupineManager.stop();
```

Once the app is done with using PorcupineManager, be sure you explicitly release the resources allocated to Porcupine:

```javascript
this._porcupineManager.delete();
```

There is no need to deal with audio capture to enable wake word detection with PorcupineManager.
This is because it uses [@picovoice/react-native-voice-processor](https://github.com/Picovoice/react-native-voice-processor/)
module to capture frames of audio and automatically pass it to the wake word engine.

#### Low-Level API

[Porcupine](/binding/react-native/src/porcupine.tsx) provides low-level access to the wake word engine for those
who want to incorporate wake word detection into a already existing audio processing pipeline. `Porcupine` also has
`fromKeywords` and `fromKeywordPaths` static constructors.

```javascript
async createPorcupine(){
    try{
        this._porcupine = await Porcupine.fromKeywords(["picovoice"]);
    } catch (err) {
        // handle error
    }
}
```

To search for a keyword in audio, you must pass frames of audio to Porcupine using the `process` function. The `keywordIndex` returned will either be -1 if no detection was made or an integer specifying which keyword was detected.

```javascript
let buffer = getAudioFrame();

try {
  let keywordIndex = await this._porcupine.process(buffer);
  if (keywordIndex >= 0) {
    // detection made!
  }
} catch (e) {
  // handle error
}
```

For `process` to work correctly, the provided audio must be single-channel and 16-bit linearly-encoded.

Finally, once you no longer need the wake word engine, be sure to explicitly release the resources allocated to Porcupine:

```javascript
this._porcupine.delete();
```

### Android

To include the package in your Android project, ensure you have included `mavenCentral()` in your top-level `build.gradle` file and then add the following to your app's `build.gradle`:

```groovy
dependencies {    
    implementation 'ai.picovoice:porcupine-android:1.9.0'
}
```

There are two possibilities for integrating Porcupine into an Android application.

#### High-Level API

[PorcupineManager](binding/android/Porcupine/porcupine/src/main/java/ai/picovoice/porcupine/PorcupineManager.java)
provides a high-level API for integrating Porcupine into Android applications. It manages all activities related to creating
an input audio stream, feeding it into the Porcupine library, and invoking a user-provided detection callback.

```java
import ai.picovoice.porcupine.*;

final String keywordPath = "/path/to/keyword.ppn"
try {    
    

    PorcupineManager porcupineManager = new PorcupineManager.Builder()
                        .setKeywordPath(keywordPath)
                        .setSensitivity(0.5f)
                        .build(context, 
                        new PorcupineManagerCallback() {
                            @Override
                            public void invoke(int keywordIndex) {
                                // detection event logic/callback
                            }
                        });
} catch (PorcupineException e) { }
```

Sensitivity is the parameter that enables developers to trade miss rate for false alarm. It is a floating point number within
[0, 1]. A higher sensitivity reduces miss rate at cost of increased false alarm rate.

When initialized, input audio can be monitored using `manager.start()`. Stop the manager using by invoking
`manager.stop()`. When done be sure to release the resources using `manager.delete()`.

#### Low-Level API

[Porcupine](/binding/android/Porcupine/porcupine/src/main/java/ai/picovoice/porcupine/Porcupine.java) provides a
binding for Android. It can be initialized using.

```java
import ai.picovoice.porcupine.*;

final String keywordPath = "/path/to/keyword.ppn"
try {    
    Porcupine porcupine = new Porcupine.Builder()
                        .setKeywordPath(keywordPath)
                        .setSensitivity(0.5f)
                        .build(context);
} catch (PorcupineException e) { }
```
Once initialized, `porcupine` can be used to monitor incoming audio.

```java
private short[] getNextAudioFrame();

while (true) {
    final int keywordIndex = porcupine.process(getNextAudioFrame());
    if (keywordIndex != -1) {
        // detection event logic/callback
    }
}
```

Finally, be sure to explicitly release resources acquired by porcupine as the binding class does not rely on the garbage collector for releasing native resources.

```java
porcupine.delete();
```

### iOS

There are two approaches for integrating Porcupine into an iOS application.

#### High-Level API

[PorcupineManager](/binding/ios/PorcupineManager.swift) manages audio recording, passing it into Porcupine, and invoking
the user-provided detection callback.

```swift
let modelPath: String = ... // Available at lib/common/porcupine_params.pv
let keywordPaths: [String] = ["/path/to/keyword/file/a", "/path/to/keyword/file/b"]
let sensitivities: [Float32] = [0.35, 0.64]
let keywordCallback: ((Int32) -> Void) = { keywordIndex in
    // Insert detection event logic
}

let manager = try PorcupineManager(
    modelPath: modelPath,
    keywordPaths: keywordPaths,
    sensitivities: sensitivities
    onDetection: keywordCallback)
```

When initialized, input audio can be monitored using `manager.start()`. When done be sure to stop the manager using
`manager.stop()`.

#### Low-Level API

[Porcupine.swift](/binding/ios/Porcupine.swift) provides low-level access to the wake word engine for those who want to incorporate wake word detection into a already existing audio processing pipeline.

To construct an instance of Porcupine, pass it a keyword. 

```swift
import Porcupine

do {
    Porcupine porcupine = try Porcupine(keyword: Porcupine.BuiltInKeyword.picovoice)
} catch { }
```

To search for a keyword in audio, you must pass frames of audio to Porcupine using the `process` function. The `keywordIndex` returned will either be -1 if no detection was made or an integer specifying which keyword was detected.

```swift
func getNextAudioFrame() -> [Int16] {
    // .. get audioFrame
    return audioFrame;
}

while true {
    do {
        let keywordIndex = try porcupine.process(getNextAudioFrame())
        if keywordIndex >= 0 {
            // .. detection made!
        }
    } catch { }
}
```

Once you're done with Porcupine you can force it to release its native resources rather than waiting for the garbage collector:
```swift
porcupine.delete();
```

### Web

Porcupine is available on modern web browsers (i.e. not Internet Explorer) via [WebAssembly](https://webassembly.org/). Microphone audio is handled via the [Web Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API) and is abstracted by the WebVoiceProcessor, which also handles downsampling to the correct format. Porcupine is provided pre-packaged as a [Web Worker](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API/Using_web_workers).

Each spoken language is available as a dedicated npm package (e.g. @picovoice/porcupine-web-en-worker). These packages can be used with the @picovoice/web-voice-processor. They can also be used with the Angular, React, and Vue bindings, which abstract and hide the web worker communication details.

#### Vanilla JavaScript and HTML (CDN Script Tag)

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <script src="https://unpkg.com/@picovoice/porcupine-web-en-worker/dist/iife/index.js"></script>
    <script src="https://unpkg.com/@picovoice/web-voice-processor/dist/iife/index.js"></script>
    <script type="application/javascript">
      async function startPorcupine() {
        console.log("Porcupine is loading. Please wait...");
        let ppnEn = await PorcupineWebEnWorker.PorcupineWorkerFactory.create([
          {
            builtin: "Picovoice",
            sensitivity: 0.65,
          },
        ]);

        console.log("Porcupine worker ready!");

        const keywordDetectionCallback = (msg) => {
          if (msg.data.command === "ppn-keyword") {
            console.log("Keyword detected: " + msg.data.keywordLabel);
          }
        };

        ppnEn.onmessage = keywordDetectionCallback;

        console.log(
          "WebVoiceProcessor initializing. Microphone permissions requested ..."
        );

        try {
          let webVp = await window.WebVoiceProcessor.WebVoiceProcessor.init({
            engines: [ppnEn],
          });
          console.log("WebVoiceProcessor ready and listening!");
        } catch (e) {
          console.log("WebVoiceProcessor failed to initialize: " + e);
        }
      }

      document.addEventListener("DOMContentLoaded", function () {
        startPorcupine();
      });
    </script>
  </head>
  <body></body>
</html>
```

#### Vanilla JavaScript and HTML (ES Modules)

```console
yarn add @picovoice/porcupine-web-en-worker @picovoice/web-voice-processor
```

(or)

```console
npm install @picovoice/porcupine-web-en-worker @picovoice/web-voice-processor
```

```javascript
import { PorcupineWorkerFactory } from "@picovoice/porcupine-web-en-worker"
import { WebVoiceProcessor } from "@picovoice/web-voice-processor"

async startPorcupine()
  const porcupineWorker = await PorcupineWorkerFactory.create(
    [{builtin: "Picovoice", sensitivity: 0.65}]
  );

  porcupineWorker.onmessage = (msg) => {
    switch (msg.data.command) {
      case 'ppn-keyword':
        // Porcupine keyword detection
        console.log("Porcupine detected " + msg.data.keywordLabel);
        break;
      default:
        break;
    }
  };

  const webVp = await WebVoiceProcessor.init({
    engines: [porcupineWorker],
    start: true,
  });
  }

}
startPorcupine()
```

#### Angular

```console
yarn add @picovoice/porcupine-web-angular
```

(or)

```console
npm install @picovoice/porcupine-web-angular
```

```typescript
async ngOnInit() {
    // Load Porcupine worker chunk with specific language model (large ~1-2MB chunk; dynamically imported)
    const porcupineFactoryEn = (await import('@picovoice/porcupine-web-en-worker')).PorcupineWorkerFactory
    // Initialize Porcupine Service
    try {
      await this.porcupineService.init(porcupineFactoryEn,
      {porcupineFactoryArgs: [{ builtin: "Okay Google", sensitivity: 0.65 }, { builtin: "Picovoice" }]})
      console.log("Porcupine is now loaded and listening")
    }
    catch (error) {
      console.error(error)
    }
  }

  ngOnDestroy() {
    this.porcupineDetection.unsubscribe()
    this.porcupineService.release()
  }
```

#### React

```console
yarn add @picovoice/porcupine-web-react
```

(or)

```console
npm install @picovoice/porcupine-web-react
```

```javascript
import React, { useState } from "react";
import { PorcupineWorkerFactory } from "@picovoice/porcupine-web-en-worker";
import { usePorcupine } from "@picovoice/porcupine-web-react";

const keywords = [{ builtin: "Picovoice", sensitivity: 0.65 }];

function VoiceWidget(props) {
  const keywordEventHandler = (keywordLabel) => {
    console.log(`Porcupine detected ${keywordLabel}`);
  };

  const {
    isLoaded,
    isListening,
    isError,
    errorMessage,
    start,
    resume,
    pause,
  } = usePorcupine(
    PorcupineWorkerFactory,
    { keywords, start: true },
    keywordEventHandler
  );
}
```

#### Vue

```console
yarn add @picovoice/porcupine-web-vue
```

(or)

```console
npm install @picovoice/porcupine-web-vue
```

```html
<template>
  <div class="voice-widget">
    <Porcupine
      v-bind:porcupineFactoryArgs="[
        { builtin: 'Grasshopper', sensitivity: 0.65 },
        { builtin: 'Grapefruit', sensitivity: 0.4 },
      ]"
      v-bind:porcupineFactory="factory"
      v-on:ppn-ready="ppnReadyFn"
      v-on:ppn-keyword="ppnKeywordFn"
      v-on:ppn-error="ppnErrorFn"
    />
    <h3>Keyword Detections:</h3>
    <ul v-if="detections.length > 0">
      <li v-for="(item, index) in detections" :key="index">{{ item }}</li>
    </ul>
  </div>
</template>
<script>
  import Porcupine from "@picovoice/porcupine-web-vue";
  import { PorcupineWorkerFactoryEn } from "@picovoice/porcupine-web-en-worker";

  export default {
    name: "VoiceWidget",
    components: {
      Porcupine,
    },
    data: function () {
      return {
        detections: [],
        isError: null,
        isLoaded: false,
        factory: PorcupineWorkerFactoryEn,
      };
    },
    methods: {
      ppnReadyFn: function () {
        this.isLoaded = true;
      },
      ppnKeywordFn: function (data) {
        this.detections = [...this.detections, data.keywordLabel];
      },
      ppnErrorFn: function (data) {
        this.isError = true;
        this.errorMessage = data.toString();
      },
    },
  };
</script>
```

### NodeJS

Install NodeJS SDK:

```console
yarn add @picovoice/porcupine-node
```

Create instances of the Porcupine class by specifying which keywords you want it to listen for:

```javascript
const Porcupine = require("@picovoice/porcupine-node");

const {
  GRASSHOPPER,
  BUMBLEBEE,
} = require("@picovoice/porcupine-node/builtin_keywords");

let handle = new Porcupine([GRASSHOPPER, BUMBLEBEE], [0.5, 0.65]);
```

`GRASSHOPPER` and `BUMBLEBEE` are built-in keywords. If you wish to use a custom keyword file, you need to identify its path:

```javascript
const Porcupine = require("@picovoice/porcupine-node");

let handle = new Porcupine(["/path/to/custom/keyword/file"], [0.5]);
```

When instantiated, `handle` can process audio via its `.process` method.

```javascript
let getNextAudioFrame = function() {
    ...
};

while (true) {
  let keywordIndex = handle.process(getNextAudioFrame());
  if (keywordIndex !== -1) {
    // detection event callback
  }
}
```

When done be sure to release resources acquired by WebAssembly using `release()`:

```javascript
handle.release();
```

### C

Porcupine is implemented in ANSI C and therefore can be directly linked to C applications.
[include/pv_porcupine.h](/include/pv_porcupine.h) header file contains relevant information. An instance of Porcupine
object can be constructed as follows.

```c
const char *model_path = ... // Available at lib/common/porcupine_params.pv
const char *keyword_path = ...
const float sensitivity = 0.5f;

pv_porcupine_t *handle = NULL;
const pv_status_t status = pv_porcupine_init(
    model_path,
    1,
    &keyword_path,
    &sensitivity,
    &handle);
if (status != PV_STATUS_SUCCESS) {
    // Insert error handling logic
}
```

Sensitivity is the parameter that enables developers to trade miss rate for false alarm. It is a floating point number
within [0, 1]. A higher sensitivity reduces miss rate (false reject rate) at cost of (potentially) increased false alarm
rate.

Now the `handle` can be used to monitor incoming audio stream. Porcupine accepts single channel, 16-bit linearly-encoded
PCM audio. The sample rate can be retrieved using `pv_sample_rate()`. Finally, Porcupine accepts input audio in
consecutive chunks (aka frames) the length of each frame can be retrieved using `pv_porcupine_frame_length()`.

```c
extern const int16_t *get_next_audio_frame(void);

while (true) {
    const int16_t *pcm = get_next_audio_frame();
    int32_t keyword_index = -1;
    const pv_status_t status = pv_porcupine_process(handle, pcm, &keyword_index);
    if (status != PV_STATUS_SUCCESS) {
        // error handling logic
    }
    if (keyword_index != -1) {
        // Insert detection event callback
    }
}
```

Finally, when done be sure to release the acquired resources:

```c
pv_porcupine_delete(handle);
```

### Microcontroller

Porcupine is implemented in ANSI C and therefore can be directly linked to embedded C projects. Its public header file contains relevant information. An instance of the Porcupine object can be constructed as follows.

```c
#define MEMORY_BUFFER_SIZE ...
uint8_t memory_buffer[MEMORY_BUFFER_SIZE] __attribute__((aligned(16)));

const uint8_t keyword_array[] = {...};

const int32_t keyword_model_sizes = sizeof(keyword_array);
const void *keyword_models = keyword_array;
const float sensitivity = 0.5f;

pv_porcupine_t *handle = NULL;

const pv_status_t status = pv_porcupine_init(
        MEMORY_BUFFER_SIZE,
        memory_buffer,
        1,
        &keyword_model_sizes,
        &keyword_models,
        &sensitivity,
        &handle);

if (status != PV_STATUS_SUCCESS) {
    // error handling logic
}
```

Sensitivity is the parameter that enables developers to trade miss rate for false alarm. It is a floating-point number
within [0, 1]. A higher sensitivity reduces miss rate (false reject rate) at cost of increased false alarm rate.

Now the `handle` can be used to monitor incoming audio stream. Porcupine accepts single channel, 16-bit PCM audio. The sample rate can be retrieved using `pv_sample_rate()`. Finally, Picovoice accepts input audio in consecutive chunks (aka frames) the length of each frame can be retrieved using `pv_porcupine_frame_length()`.

```c
extern const int16_t *get_next_audio_frame(void);

while (true) {
    const int16_t *pcm = get_next_audio_frame();
    int32_t keyword_index;
    const pv_status_t status = pv_porcupine_process(handle, pcm, &keyword_index);
    if (status != PV_STATUS_SUCCESS) {
        // error handling logic
    }
    if (keyword_index != -1) {
        // detection event logic/callback
    }
}
```

Finally, when done be sure to release the acquired resources.

```c
pv_porcupine_delete(handle);
```

## Releases

### v1.9.0 - December 2nd, 2020

- Added _Alexa_, _Computer_, _Hey Google_, _Hey Siri_, _Jarvis_, and _Okay Google_ models under Apache 2.0.
- Added React Native SDK.
- Added Java SDK.
- Added .NET SDK.
- Added NodeJS SDK.
- Improved accuracy.
- Runtime optimization.

### v1.8.0 - May 27th, 2020

- Improved accuracy.
- Runtime optimization.

### v1.7.0 - Feb 13th, 2020

- Improved accuracy.
- Runtime optimization.
- Added support for Raspberry Pi 4.
- Added service-based Android demo application.
- Added C demo applications.
- Updated documentation.

### v1.6.0 - April 25th, 2019

- Improved accuracy.
- Runtime optimization.
- Added support for BeagleBone.
- iOS build can run on simulator now.

### v1.5.0 - November 13, 2018

- Improved accuracy.
- Runtime optimization.
- Added support for running within web browsers (WebAssembly).

### v1.4.0 - July 20, 2018

- Improved accuracy.
- Runtime optimizations.
- Updated documentation.

### v1.3.0 - June 19, 2018

- Improved accuracy.
- Runtime optimizations

### v1.2.0 - April 21, 2018

- Runtime optimizations.

### v1.1.0 - April 11, 2018

- Added multiple command detection capability.

### v1.0.0 - March 13, 2018

- Initial release.

## FAQ

You can find the FAQ [here](https://picovoice.ai/docs/faq/porcupine/).
