# Rokid Glasses Development Stack

Organized overview of the three main development paths for building on Rokid AI Glasses / AR devices.

**Suitable for**: Idea validation, agent building, custom apps, and spatial computing experiences.

## Overview

| Path | Target | Best For | Compute Priority |
|------|--------|----------|------------------|
| **AIUI Studio** | AI Agents on Glasses | No-code / natural language idea validation | On-device first |
| **CXR-S / CXR-L SDK** | Custom apps on glasses or phone | Deep hardware control, low-latency, compliance | Glasses → Phone → Cloud (prefer on-device) |
| **YodaOS-Master** | Spatial computing on Station | Desktop / spatial apps, Unity / JSAR | Station host |

> In an era of tightening compliance, keep data on-device whenever possible.

---

## 01. AIUI Studio

**One sentence to build an agent. Craft to refine. Interactive Inview to simulate. One-click publish to Agent Store.**

- Browser-based, no local setup required.
- Natural language → full project via AIUI CODING.
- Built-in simulator (Interactive Inview) for glasses interaction testing.
- Suitable for: **No code yet, want to validate an idea first.**

### Key Links
- [AIUI Studio (Global)](https://aiui-global.rokid.com)
- [AIUI Docs](https://js.rokid.com/AIUI)
- [Official Dev Tools & Skills](https://github.com/yodaos-project/AIUI)
- Scaffold locally: `npm create @yodaos-pkg/aiui-agent@latest my-agent`

### Workflow
1. Describe idea in natural language.
2. Refine with Craft / AI assistance.
3. Simulate in Interactive Inview.
4. Package & publish to Agent Store.

---

## 02. CXR-S / CXR-L SDK

Four-level compute ladder: **Glasses → Phone → Cloud → On-device priority**.

### CXR-S (Glasses-side)
- Bare-metal independent app running directly on the glasses (YodaOS-Sprite).
- Direct management of: buttons, IMU, camera, sensors.
- Bidirectional communication with phone.
- Maven: `com.rokid.cxr:cxr-service-bridge`

### CXR-L (Phone-side)
- Your app runs on the phone.
- Via Rokid AI App, accesses glasses IO:
  - Image
  - Audio
  - Display
  - Command channels
- Maven: `com.rokid.cxr:client-l`

### When to use
- Need low latency or deep hardware access.
- Prefer data stays on device (compliance / privacy).
- Building standalone glasses apps or companion phone apps.

### Resources
- [Rokid Open Platform](https://open.rokid.com/)
- Community docs examples exist (e.g. buildwithfenna/rokid-docs).

---

## 03. YodaOS-Master

Rokid’s spatial computing system running on the **Station** host.

- Three app types:
  - Desktop applications
  - Spatial applications
  - Spatial mini-programs
- Development: **Unity** and **JSAR**.
- Based on AOSP, strong Android compatibility.

### Key Capabilities
- Real-time spatial computing (SLAM, plane detection, tracking).
- Gesture / trackpad / ray-casting interaction.
- Spatial audio and large virtual screens.

### Resources
- [YodaOS-Master overview](https://global.rokid.com/blogs/yodaos-master)
- Official Rokid Station / AR Lite product pages.

---

## Project Structure (Suggested)

```
rokid-dev-stack/
├── README.md                 # This guide
├── aiui-studio/               # No-code / AIUI agent samples & notes
├── cxr-sdk/                   # CXR-S / CXR-L examples & integration notes
└── yodaos-master/             # Spatial computing / Station app notes
```

## Next Steps

- Add concrete sample agents under `aiui-studio/`.
- Document CXR connection patterns and Caps protocol usage.
- Collect YodaOS-Master Unity / JSAR starter templates.

---

*Organized from Rokid official announcements (IFA 2026 AIUI Studio launch, Open Day 2026 YodaOS, etc.) and public developer documentation.*
