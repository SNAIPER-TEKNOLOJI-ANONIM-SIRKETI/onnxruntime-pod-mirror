# onnxruntime-pod-mirror

Unmodified copies of ONNX Runtime's CocoaPods archives, kept so that iOS builds can still fetch them
while the upstream host `download.onnxruntime.ai` serves a certificate for another name (since about
2026-11-20) and `pod install` fails with `curl: (60) SSL: no alternative certificate subject name
matches target host name`.

ONNX Runtime is Copyright (c) Microsoft Corporation and distributed under the MIT License; the licence
file is in this repository and inside every archive. Nothing here is modified or built by us.

## Archives

| Pod | Version | Release asset | sha256 |
|---|---|---|---|
| `onnxruntime-c` | 1.30.0 | `pod-archive-onnxruntime-c-1.30.0.zip` | `c9ba872647b7efa803e597ed69296d18e2e7c8e0dfe81afa379a8857cc09074f` |

The 1.30.0 archive was packed on 2026-11-25 from a CocoaPods download cache filled from
`https://download.onnxruntime.ai/pod-archive-onnxruntime-c-1.30.0.zip` on 2026-11-19, before the outage.
It holds exactly what the published podspec installs: `Headers/`, `LICENSE` and
`onnxruntime.xcframework` (ios-arm64, ios-arm64_x86_64-simulator, macos-arm64_x86_64). The zip itself is
a new container, so its sha256 is this mirror's, not the upstream archive's.

## Use

Point the pod at a local podspec whose `source` is the release asset with its checksum:

```json
"source": {
  "http": "https://github.com/SNAIPER-TEKNOLOJI-ANONIM-SIRKETI/onnxruntime-pod-mirror/releases/download/onnxruntime-c-1.30.0/pod-archive-onnxruntime-c-1.30.0.zip",
  "sha256": "c9ba872647b7efa803e597ed69296d18e2e7c8e0dfe81afa379a8857cc09074f"
}
```

CocoaPods refuses the download when the checksum does not match. Remove the override once the upstream
host is back.
