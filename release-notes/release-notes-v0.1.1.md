## AURA 0.1.1: first public release

AURA is a free personal assistant that works offline. It sets reminders and alarms by voice or typing, learns your
own voice and accent on your device, and answers to its name. Built for East African English.

Website: https://josephwalusimbi-eng.github.io/AURA-app/ · Privacy: https://josephwalusimbi-eng.github.io/AURA-app/privacy.html

### Downloads

| File | For | Size |
|---|---|---|
| `AURA-0.1.1-android-arm64.apk` | Android 6 or later, 64-bit (arm64) phones | 34 MB |
| `AURA-0.1.1-windows-x64.zip` | Windows 10 (1809) or later, 64-bit | 17 MB |

Check a download against `SHA256SUMS.txt`:
`certutil -hashfile <file> SHA256` (Windows) or `sha256sum <file>` (Linux, macOS).

The Microsoft Store version (cleaner install, no security warning) is coming; this release is for people who want it
now.

### Install

**Android.** Download the APK on the phone, open it, and allow "install unknown apps" for your browser or file manager
when asked. The APK is signed by the AURA release key (certificate SHA-256
`12:8A:13:B5:93:3C:65:13:B9:E0:C9:E8:84:AE:6A:1A:80:C1:78:FD:1D:FC:B7:54:CC:53:42:77:52:3A:1D:E1`).
**Windows.** Unzip the folder anywhere you like and run `aura.exe`. Windows SmartScreen may say the publisher is
unrecognised, because this zip is not code-signed: choose "More info", then "Run anyway". The Microsoft Store package
has no such warning.

### First run

1. Enter a name and choose **Get started**. Typing a request works straight away.
2. For speech: **Settings → Speech recognition → Download** "Base (East African English)" (82 MB, once; tiny is 44 MB
   and faster but less accurate). After that AURA works without internet.
3. Optional: **Settings → Your voice → Teach AURA your voice**. Read 64 short sentences (6 to 8 minutes), keep the
   device charging, and AURA trains a personal model on the device (about 1.5 h for tiny and 4.5 h for base on a 2017
   phone; about an hour for base on a laptop). It is switched on only if it makes fewer mistakes than the standard model
   on sentences it never trained on. The result screen shows both error counts and how long learning took.
4. Optional: say "AURA" 8 times, then **Settings → Wake word** for hands-free use (Android and Windows; off by default).

### What's in it

- Reminders, alarms, tasks, events and memory, with honest confirmation ("Done" only after the system accepted it)
- On-device speech recognition (whisper.cpp) with models adapted to East African English
- On-device personal voice training and a wake word
- Private by design: no account, no telemetry, recordings deleted after transcription by default

### Fixed during release testing

- The first words of a spoken request were lost (recording now starts when the mic is pressed)
- Agenda and Memory did not refresh when opened
- "Make (for) me an alarm", "set me an alarm" were not understood
- Android automatic backup could have copied recordings to a Google account; it is now off
- Launcher and Windows tile icons replaced Flutter's default

### Known limits

- Speech recognition is least accurate on short commands before you teach it your voice; learning your voice helps
  (first test on a 2017 phone: 22 word errors fell to 10 of 109 on the check sentences, one user).
- The on-device database is not yet encrypted at rest.
- iOS is not available. Windows on Arm runs the x64 build through emulation.
- The speech models are licensed CC BY-NC-SA 4.0 (non-commercial); source code is available from the author on request.

Models: https://huggingface.co/Walusimbi/whisper-afrispeech-east-africa ·
Wake word: https://huggingface.co/Walusimbi/aura-wakeword
