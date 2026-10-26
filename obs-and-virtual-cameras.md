# Face swap output: preview, OBS, and virtual cameras

[Back to the guide](README.md)

## These are separate capabilities

| Capability | What it establishes | What remains unproven |
| --- | --- | --- |
| Browser or desktop preview | The application can show a result. | Recording, OBS capture, virtual-camera output, or receiving-app compatibility. |
| Saved recording | A processed clip can be saved and played. | Live delivery to another application. |
| OBS capture | OBS can receive a particular window, display, stream, or supported source. | A built-in integration, isolated video output, or acceptance by a calling app. |
| Virtual camera | Software exposes an output source that a receiving app may select as a webcam. | That app's actual compatibility, timing, or the required audio routing. |

## Verify the full path

Write down the route you intend to use, for example:

`camera → face swap application → supported OBS source → OBS scene → OBS Virtual Camera → receiving app`

This is a conceptual route, not a claim that every face swap application supports it. A desktop window capture and a website in an OBS Browser Source have different access and rendering conditions. Test the actual source type; do not assume one substitutes for the other.

For tools that document a compatible route:

1. Confirm a changing processed result in the original tool.
2. Add the documented source to a new OBS test scene. Verify it captures the intended result rather than the raw input or unrelated desktop content.
3. Check framing, crop, mirror behavior, and any unwanted user interface.
4. Follow [OBS's Virtual Camera Guide](https://obsproject.com/kb/virtual-camera-guide) to choose the intended output and start the virtual camera.
5. In the receiving app, select the virtual camera and inspect a private test preview. Record the receiving app's version and whether changing frames arrive.
6. Verify microphone/audio handling independently; a visible video feed does not establish your required audio route.

Do not stream publicly or join someone else's call simply to verify this route. Use a local/private preview with authorized participants.

## If the virtual camera is missing

Use the current [OBS troubleshooting guide](https://obsproject.com/kb/virtual-camera-troubleshooting) for your operating system and OBS version. Installation and compatibility differ by platform. Avoid treating instructions for a different platform or old virtual-camera component as current for your device.

## Scope for Live Face Swap

This guide does not claim verified OBS, virtual-camera, Zoom, Discord, or other call integration for the maintainer's pre-release browser project. A local preview or recording alone is not evidence of these integrations.
