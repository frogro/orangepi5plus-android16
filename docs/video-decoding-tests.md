# AV1 integration tests

4K 3840x2160, 8-bit, 30 fps source clips, 300 frames each. Explicit Codec2 ByteBuffer decoding, no HDMI presentation or audio synchronization.

| Test | Frames | Approximate decode fps |
| --- | --- | --- |
| AV1 hardware, optimized, no checksum overhead | 300/300 | 33.7 |
| AV1 forced software | 300/300 | 37.0 |
| AV1 injected hardware-start failure -> software | 300/300 | 35.8 |
| H.264 regression | 300/300 | 34.3 |
| HEVC regression | 300/300 | 42.6 |
| VP9 regression | 300/300 | 37.3 |

Visible-plane SHA256 checksums of frames 1, 150 and 300 match their baselines; AV1 hardware matches software output. Throughput is sample-dependent; software was faster for this AV1 sample. Hardware paths were verified from V4L2 logs, not just Android codec flags.

Changes include the AV1 V4L2-request backend, read-only linear NV12 buffer mapping, faster NV12 conversion and bounded input replay for software fallback before the first hardware output. A later hardware failure is reported as an error; seamless midstream recovery is not implemented. 10-bit/HDR, film grain, seeking, long playback and 60 fps remain unvalidated. The AV1 codec XML advertises the tested 3840x2160 size in this candidate.

