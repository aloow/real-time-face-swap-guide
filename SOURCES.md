# Primary sources

Reviewed on **2026-10-26**. This edition paraphrases upstream feature descriptions and checks repository metadata. It does not reproduce model weights, third-party source code, face imagery, or vendor benchmarks as our own measurements.

| Source | Used for | Evidence boundary |
| --- | --- | --- |
| [Deep-Live-Cam README](https://github.com/hacksider/Deep-Live-Cam/blob/main/README.md) | Webcam mode, local installation, models, OBS window-capture suggestion. | Documentation review; no execution benchmark. |
| [DeepFaceLive repository](https://github.com/iperov/DeepFaceLive) and [README](https://github.com/iperov/DeepFaceLive/blob/master/README.md) | Archived status, webcam/video workflow, links to streaming and call setup. | Legacy project; no current device verification. |
| [FaceFusion README](https://github.com/facefusion/facefusion/blob/master/README.md) | Installation, installers, commands, official documentation entry point. | Does not establish a tested live webcam route in this edition. |
| [VisoMaster README](https://github.com/visomaster/VisoMaster/blob/main/README.md) and [repository metadata](https://api.github.com/repos/visomaster/VisoMaster) | Documented webcam/virtual-camera features, installation, last repository push. | No hands-on compatibility claim; repository push recency is not proof of support quality. |
| [MDN: getUserMedia](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/getUserMedia) | Secure context, permission requirements, media-access error categories. | API behavior; no particular AI product endorsement. |
| [MDN: MediaRecorder.isTypeSupported](https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/isTypeSupported_static) | Recording MIME capability queries and resource limitations. | Capability queries do not establish successful recording. |
| [OBS Virtual Camera Guide](https://obsproject.com/kb/virtual-camera-guide) | Scene output and virtual-camera concept. | Does not establish integration for every face swap tool or receiving app. |
| [OBS Virtual Camera Troubleshooting](https://obsproject.com/kb/virtual-camera-troubleshooting) | Platform/version-specific setup and compatibility checks. | Follow the current instructions for the actual setup. |
| [Live Face Swap](https://live-face-swap.net/) | Maintainer's related product and current availability entry point. | Maintainer disclosure: pre-release. Public end-to-end generation was not independently verified for this edition. |

Repository metadata was read through the GitHub API, including `archived` and `pushed_at`; feature descriptions came from project-owned documentation. Dates describe this review, not a promise that upstream content remains unchanged. Corrections should identify the specific source, version, and affected claim.
