# JARVIS Android Companion — upgraded project

This is a local-first Android companion prototype built with Kotlin and Jetpack Compose.

## Included now
- Dark JARVIS workspace with Home and Chat screens.
- Procedurally drawn pixel-art floating companion (no remote image or model needed for the overlay).
- Overlay permission flow from the Home screen.
- Drag-to-move interaction, simple edge wandering, blink/breath motion, tap expression, and double-tap text-to-speech.
- Start/Stop Floating Mate controls.
- A manifest XML preflight in GitHub Actions, so malformed XML reports an explicit parser error before Gradle.
- GitHub Actions workflow to build and upload a debug APK.

## Important current limitations
- Chat uses a demo response engine; it is **not yet a real language model**.
- Double-tap speaks a fixed phrase; microphone speech recognition and true conversational voice are not implemented.
- Text-to-speech uses Android's installed TTS engine; offline availability depends on the voice data installed on the device.
- The avatar is procedural pixel art, not a Live2D rig.
- This project has not been verified as a Play Store release.

## Build from a phone with GitHub Actions
1. Upload the contents of this folder to the root of a new GitHub repository. Keep `.github/workflows/android-apk.yml`.
2. Open **Actions**, select **Build JARVIS APK**, and tap **Run workflow**. A push to `main` also starts the workflow.
3. When the run succeeds, open its **Artifacts** section and download `jarvis-debug-apk`.
4. Extract the artifact ZIP and install `app-debug.apk`.

## Floating companion setup
1. Open JARVIS and tap **Start Floating Mate**.
2. Android opens the overlay permission page if permission is missing. Enable **Allow display over other apps** for JARVIS.
3. Return to JARVIS and tap **Start Floating Mate** again.
4. Drag the character to move it. Double-tap it to hear its greeting. Use **Stop Mate** to remove it.

## Roadmap to the larger JARVIS vision
The next major pieces are a genuine on-device model runtime with a user-selected compatible model, persistent local memory, explicit microphone permission plus speech input, an action broker for approved device actions, and richer avatar animation. Those are intentionally not represented as completed in this build. A model runtime and model weights are separate dependencies; this ZIP does not contain a large language model.
