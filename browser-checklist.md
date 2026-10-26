# Browser checklist for live face swap and recording

[Back to the guide](README.md)

## Check the workflow before changing settings

Identify which stage fails: camera preview, AI transformation, recording, saving, or sending the result to another application. Test those stages separately. A camera working in a conferencing app does not establish that a particular website has permission to use it.

## Camera preview

1. Use the intended site's secure origin. `getUserMedia()` is restricted to secure contexts; a local development origin may also qualify.
2. Check both the site's camera permission and the operating system's permission for that browser.
3. Select the intended camera. Disconnect unused virtual cameras if selecting a physical camera is confusing; avoid changing drivers as a first step.
4. Close other applications that may be using the device, then retry.
5. If a requested resolution or frame rate fails, retry with the tool's less restrictive settings. Keep a record of what actually worked.

Common `getUserMedia()` error names provide a starting point:

| Error | What to inspect |
| --- | --- |
| `NotAllowedError` | Site permission, system permission, secure context, or an embedding policy that blocks access. |
| `NotFoundError` | Whether a matching input device exists and is connected. |
| `NotReadableError` | Device, operating-system, or browser access failure after permission; another application may be involved. |
| `OverconstrainedError` | Requested media constraints cannot be satisfied; try less restrictive capture settings. |

Source: [MDN: getUserMedia](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/getUserMedia).

## Recording and saving

Check whether the browser exposes `MediaRecorder`, then query the actual MIME types the application uses. The included [checker](browser-check.html) reports a few common candidates without requesting media access.

`MediaRecorder.isTypeSupported()` is a capability query, not a successful recording. Resource limits can still prevent recording. A supported container does not establish that the resulting codec will play in every editor or messaging app.

For a meaningful trial:

1. Record ten seconds of the **processed** result, not just the input preview.
2. Stop cleanly and wait for the application to finish the file.
3. Replay inside the application, save, and replay the saved file.
4. Check the file's actual type and whether the expected audio track exists.
5. Repeat after a longer session if that is your intended use. Report freezes, memory pressure, truncated output, and audio drift separately.

Source: [MDN: isTypeSupported](https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/isTypeSupported_static).

## Privacy questions worth answering

Describe camera preview, reference upload, AI processing, microphone handling, and recording storage separately. A locally saved recording does not prove that the processing was local. Check the tool/provider's current data-flow and processing information before starting.

Use authorized references and avoid attaching private images or identifiable recordings to a public bug report.
