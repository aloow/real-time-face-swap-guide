# Real-Time Face Swap Guide

Choose a webcam face swap workflow, check browser recording support, and understand what it takes to send the result to OBS or a video call.

[简体中文](README.zh-CN.md) · [Browser checklist](browser-checklist.md) · [OBS and virtual cameras](obs-and-virtual-cameras.md) · [Test protocol](testing.md)

**Start here:** Need a desktop webcam workflow? Compare the documented options below. Troubleshooting a browser tool? Open the included [browser capability checker](browser-check.html) locally. Need video-call output? Check the complete output path before choosing a tool.

## What “real-time face swap” means

A live workflow processes incoming camera frames while you perform. Photo swapping, processing a prerecorded video, animating a portrait, and replacing a whole character are related tasks with different inputs and results. A fast video export or a static before/after image does not establish live webcam performance.

There are four separate things to verify:

1. **Input:** Can the tool receive your camera?
2. **Processing:** Does it transform incoming frames with acceptable delay?
3. **Recording:** Can it save the processed result, with the audio you need?
4. **Output:** Can another application receive that result as a supported source?

A preview inside a browser proves neither virtual-camera output nor compatibility with a particular calling app.

## Documented options

Documentation and repository status checked **2026-10-26**. These are source reviews, **not hands-on performance benchmarks**. “Documented” means an upstream source describes the feature; it does not mean we ran it successfully. Ordering is alphabetical within each group, with no paid placement.

| Project | Documented workflow | Setup and output | What still needs testing |
| --- | --- | --- | --- |
| [Deep-Live-Cam](https://github.com/hacksider/Deep-Live-Cam) | Webcam mode, plus image/video processing | Local installation and model files. README describes capturing the live window with OBS. | Device-specific frame rate, delay, audio synchronization, and capture behavior. A screen-capture route is distinct from a built-in virtual camera. |
| [FaceFusion](https://github.com/facefusion/facefusion) | Face manipulation with an installed application, browser UI, and command-line jobs | Upstream README links installation instructions and Windows/macOS installers. A browser UI does not imply installation-free processing. | Live webcam input and output routing are not established by the README reviewed here; check the current detailed documentation for your version. |
| [VisoMaster](https://github.com/visomaster/VisoMaster) | Image/video editing and live webcam swapping | README describes Windows/NVIDIA installation and virtual-camera output. | Host-app compatibility and device performance. Repository was not archived when reviewed, but its last recorded push was in March 2025; check current maintenance before adopting. |

### Legacy reference

| Project | Why it is useful to understand | Maintenance limit |
| --- | --- | --- |
| [DeepFaceLive](https://github.com/iperov/DeepFaceLive) | Documents webcam/video face swapping and separate streaming and video-call setup paths. | Original repository was archived in November 2024. Treat it as a legacy reference rather than an actively maintained recommendation. |

### Maintainer's browser project

[Live Face Swap](https://live-face-swap.net/?utm_source=github&utm_medium=referral&utm_campaign=real_time_face_swap_guide&utm_content=readme) is the maintainer's related browser project. It is **pre-release**; generation access and device compatibility are not publicly verified by this guide. Check the website for its current availability. Do not assume public AI access, OBS output, or virtual-camera support from this link.

**Disclosure:** This guide is maintained by [aloow](https://github.com/aloow), the developer of Live Face Swap. The website is commercial; the guide is freely reusable under the [MIT license](LICENSE). Third-party projects and models retain their own licenses. Corrections and competing tools are welcome under the same [inclusion criteria](CONTRIBUTING.md).

## A practical selection checklist

| Your requirement | Evidence to request |
| --- | --- |
| No installation | A live browser session on the intended device; distinguish browser UI from a locally installed backend. |
| Live performance | A timed recording that shows input and processed output together, with device, model, resolution, and measurement method. |
| OBS streaming | An actual capture or output route visible in an OBS scene. Record whether it uses window capture, a stream, or another mechanism. |
| Video calls | A working virtual camera or another source accepted by the calling app, tested in that app. |
| Local processing | An explicit data-flow description. A local preview or local recording does not establish where AI inference happens. |
| Saved videos | A short processed recording that can be replayed after saving, with the actual container/codec and audio result recorded. |

## Guides and tools

- [Browser checklist and troubleshooting](browser-checklist.md): permissions, camera conflicts, recording formats, and privacy questions.
- [OBS and virtual cameras](obs-and-virtual-cameras.md): distinguish preview, capture, recording, and camera output.
- [Reproducible test protocol](testing.md): report startup, motion delay, recording, and output routing separately.
- [Browser capability checker](browser-check.html): a standalone HTML file that checks API and format support without opening a camera, requesting a microphone, or uploading data. Download it and open it locally; GitHub's source view does not execute it.
- [Sources](SOURCES.md): the primary references behind this edition.

## Frequently asked questions

**Does a browser tool work on every phone or laptop?** No such compatibility claim is made here. Browser API availability is only a prerequisite; model access, processing capacity, memory, and the complete workflow also need testing.

**Does “supports WebM” mean recording will succeed?** No. A support query reports capability; a real recording may still fail because of resources or stream characteristics. Replay a short saved clip before relying on it.

**Does a smooth preview prove low delay?** No. Frame rate and input-to-output delay are different measurements. See the [test protocol](testing.md).

**Can I select a website directly as my camera in a call?** A website preview by itself does not create an operating-system camera device. Verify the tool's supported output path and the receiving app.

**Where are the face photos and camera frames processed?** This depends on the tool and configuration. Check the provider's current processing information. Use your own or explicitly authorized references, and disclose the visual effect to participants.

## Contributing

Submit sourced corrections or a reproducible compatibility report. Include the version and test conditions; do not attach private face photos, session tokens, or identifying recordings. See [CONTRIBUTING.md](CONTRIBUTING.md).
