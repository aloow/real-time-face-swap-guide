# Reproducible compatibility and performance reports

[Back to the guide](README.md)

## Evidence labels

- **Documented:** a dated primary source describes the feature.
- **Observed:** a named test setup reproduced it; include conditions and evidence.
- **Not tested:** no execution evidence is available for that setup.
- **Failed:** a specific test was attempted and did not meet its stated criterion; include the symptom and reproduction steps.

The first edition contains documentation reviews. It does not publish AI frame-rate rankings, latency measurements, or a device compatibility leaderboard. Browser capability checks are a different class of evidence and must not be presented as AI tests.

## Record conditions first

Copy this template into a compatibility issue. Keep it free of account identifiers, device serial numbers, private face media, and session credentials.

```text
Test date:
Tool name and version/commit:
Operating system and version:
Browser and version, if applicable:
CPU / GPU / RAM, if relevant:
Model and execution provider, if known:
Input resolution and requested frame rate:
Actual output resolution and frame rate, if measured:
Reference: self / explicitly authorized / synthetic:
Processing location: local / remote / unknown:
Output path and receiving app/version:
Startup result and measurement method:
Motion-delay result and measurement method:
Continuous session duration and observed failures:
Recording MIME type, length, replay, and saved-file result:
Audio source and synchronization result:
Limitations and reproduction steps:
```

## Run the tests in order

1. **Browser prerequisites:** check secure context, media API availability, and recording MIME support. These checks do not open a camera or establish model compatibility.
2. **Camera:** confirm a changing raw preview using the chosen device and resolution.
3. **Transformation:** obtain a changing processed result using an authorized reference. A prerecorded example is not sufficient.
4. **Startup:** measure from the explicit start action to the first usable processed frame. Repeat and report the individual observations plus a median; include cold-start/model-download conditions.
5. **Motion delay:** show input and output in the same independently recorded frame when feasible. Use a visible movement, count the observed offset, and state the recording frame rate and measurement uncertainty. If the reference timeline is unreliable, leave the numeric delay unreported. Displayed FPS alone does not measure this delay.
6. **Stability:** try the duration your use case needs. Note stalls, reconnects, changes in quality, temperature-related slowdown, and whether processing stops cleanly.
7. **Recording:** save a short processed clip, replay the saved file, and check audio independently. Report container, codec if inspected, duration, and any truncation or drift.
8. **Output:** verify the full route in the actual receiving app. Record preview, window capture, OBS scene, and virtual-camera stages separately.

For a comparison, hold device, resolution, reference, lighting, motion, output path, and test duration as consistent as practical. Report mismatches instead of folding incomparable measurements into a ranking. Mark unknown values as unknown, never zero.

## Publishing results

Provide steps another reader can follow. Prefer descriptions or anonymized technical evidence over face recordings. Obtain explicit permission from everyone shown before sharing any identifiable media. Disclose affiliation with a tested product and any sponsored access. Failures and corrections are as useful as successful tests.
