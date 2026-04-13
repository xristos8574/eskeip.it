# Eskeip.it! 🚀

**Eskeip.it!** is a cutting-edge, browser-based reconnaissance and kiosk escape toolkit designed for security researchers, penetration testers, and developers. Uncover hidden browser capabilities, probe device hardware, and test the boundaries of restricted web environments across all major platforms.

## Table of Contents

1.  [How Eskeip.it! Was Born](#how-eskeipit-was-born)
2.  [Disclaimer](#disclaimer)
3.  [What is Eskeip.it!?](#what-is-eskeipit)
4.  [General Functionality Note](#general-functionality-note)
5.  [SYSTEM & OS INTERACTION](#system--os-interaction)
    *   [📁 File & Disk](#file--disk)
    *   [🔐 Permissions Audit](#permissions-audit)
    *   [📊 System Info Dump](#system-info-dump)
    *   [🔗 Deep Link App Launcher](#deep-link-app-launcher)
    *   [🔓 Kiosk Escape Toolkit](#kiosk-escape-toolkit)
    *   [🖼 Display & UI Control](#display--ui-control)
    *   [💾 Storage & Data](#storage--data)
6.  [NETWORK & CONNECTIVITY](#network--connectivity)
    *   [🌐 Network Recon](#network-recon)
    *   [🔍 Subnet Discovery Scanner](#subnet-discovery-scanner)
    *   [💻 Web Serial / USB](#web-serial--usb)
    *   [🔌 NFC](#nfc)
    *   [🎮 Gamepad / Controller](#gamepad--controller)
7.  [MEDIA & SENSORS](#media--sensors)
    *   [📷 Camera & Video](#camera--video)
    *   [🎤 Microphone & Audio](#microphone--audio)
    *   [🎮 Motion & Orientation](#motion--orientation)
    *   [💡 Ambient Light & Proximity](#ambient-light--proximity)
8.  [IDENTITY & LOCATION](#identity--location)
    *   [👤 Identity & Biometrics](#identity--biometrics)
    *   [📋 Clipboard Access](#clipboard-access)
    *   [🕵 Browser Fingerprint](#browser-fingerprint)
    *   [📢 Social & Notification Triggers](#social--notification-triggers)

## How Eskeip.it! Was Born

Once upon a time, during a routine pentest on a kiosk machine, I found myself trapped within the browser. The usual escape routes were blocked. I desperately needed a website with file upload, then download, then print functionality – each attempt a dead end, consuming precious time typing URLs on a clunky on-screen keyboard. That's when the lightbulb flashed: "Why not build *one* tool with *all* these capabilities and more?" And so, **Eskeip.it!** was conceived – a single, powerful HTML file to quickly escape kiosks and perform rapid reconnaissance. Sure, `escape.it` was taken, but `eskeip.it`? That's just more original! 😎

## Disclaimer

**Eskeip.it!** is provided strictly for **educational, research, and authorized testing purposes only**. It is designed to assist security professionals, developers, and system administrators in understanding browser capabilities, identifying potential vulnerabilities, and testing security configurations in controlled environments. **Under no circumstances should this tool be used for malicious activities, unauthorized access, or any illegal purposes.** Users are solely responsible for ensuring they have explicit permission and legal authorization before deploying or testing this tool on any system. The creators disclaim any liability for misuse or damages caused by this tool.

## What is Eskeip.it!?

**Eskeip.it!** is a self-contained HTML file that acts as a comprehensive browser-based utility. It allows you to probe a web browser's environment, interact with device hardware, and test various Web APIs to understand what information can be gathered or what actions can be triggered from within a browser context. It's particularly useful for:

*   **Kiosk Testing**: Identifying and exploiting browser features that might allow an escape from a locked-down kiosk mode.
*   **Hardware Reconnaissance**: Checking access to cameras, microphones, sensors, USB, and other peripherals.
*   **Network Discovery**: Mapping local network segments and identifying reachable hosts.
*   **Browser Fingerprinting**: Understanding the unique identifiers a browser exposes.

**Transparency is key**: All the code for **Eskeip.it!** is open-source and contained within this single `index.html` file. Anyone can inspect the code to verify its functionality and ensure no hidden or malicious actions are performed. Furthermore, all functions run directly within your browser's sandbox; **no data is sent to any external server by the tool itself.** For use in closed networks or offline scenarios, simply host the `index.html` file locally.

## General Functionality Note

**Eskeip.it!** is a testing tool. This means that not all functionalities are guaranteed to work on every browser, device, or operating system. Modern browsers and operating systems implement strict security policies that may prevent certain actions (e.g., accessing local files, triggering system dialogs without user interaction). If a feature does not work, it often indicates that the browser or device is successfully preventing that action, which is a valuable test result in itself.

## SYSTEM & OS INTERACTION

This section focuses on capabilities that allow interaction with the underlying operating system and file system, as well as system-level information gathering.

![SYSTEM & OS INTERACTION Screenshot](https://private-us-east-1.manuscdn.com/sessionFile/Sqrp2yIBMVfp3KJt29zeYW/sandbox/RHr73iyBzdSCN1TzmDlD5l-images_1776110990623_na1fn_L2hvbWUvdWJ1bnR1L3JlYWRtZV9hc3NldHMvZnVsbF92aWV3XzE.webp?Policy=eyJTdGF0ZW1lbnQiOlt7IlJlc291cmNlIjoiaHR0cHM6Ly9wcml2YXRlLXVzLWVhc3QtMS5tYW51c2Nkbi5jb20vc2Vzc2lvbkZpbGUvU3FycDJ5SUJNVmZwM0tKdDI5emVZVy9zYW5kYm94L1JIcjczaXlCemRTQ04xVHptRGxENWwtaW1hZ2VzXzE3NzYxMTA5OTA2MjNfbmExZm5fTDJodmJXVXZkV0oxYm5SMUwzSmxZV1J0WlY5aGMzTmxkSE12Wm5Wc2JGOTJhV1YzWHpFLndlYnAiLCJDb25kaXRpb24iOnsiRGF0ZUxlc3NUaGFuIjp7IkFXUzpFcG9jaFRpbWUiOjE3OTg3NjE2MDB9fX1dfQ__&Key-Pair-Id=K2HSFNDJXOU9YS&Signature=sx1IiENlTFchdh5cmFQ0VU6Qnjau2yKIJDYxFv7hVX32Sh6gwZQoQj78fjJHOx0a3iUKeJ04aa7bB7NSZ~VxdNo6XbIBhxRcDS~s1TpeFbvEYg49LZ8HncysbV2suVmkWr~wtqiGsUcKxSg086aMhI6pi83b8vbXlZnmSe8J~m5pzUGnhJGGWc0Piwm1rPAfkt315e9UO-HBodXWtf6MiaFhMEl6wXvQ3ZxNM34rD~i1FaJdtg0g6YDv0ute2LUoShRi0-1ugOYyeuV-BANRJU4xqHjsMryVcq7lpkObyY~7B1yR8PeB7ne3wNksL6inQeCNXxpQzxmWcPmDTvgdlw__)

### 📁 File & Disk

This card provides various methods for interacting with files and the local disk, including uploading, downloading, and accessing system file pickers.

*   **Functionality**: Drag & Drop, Standard File Upload, Multi-File Upload, Modern File Picker (Desktop), Save to Disk (Universal).
*   **Usage**: Test how files can be moved into and out of the browser environment. The "Save to Disk" button attempts to use the modern File System Access API and falls back to a Blob-based download for wider compatibility.
*   **Expectation**: File upload and Blob-based download should work on most platforms. The Modern File Picker and advanced Save to Disk features are typically restricted to desktop browsers (e.g., Chrome, Edge).

### 🔐 Permissions Audit

Check the current state of various browser permissions, indicating whether access is granted, denied, or requires a prompt.

*   **Functionality**: Scans the status of numerous Web API permissions (e.g., camera, microphone, geolocation, notifications, clipboard, window management, display capture, local network, sensors).
*   **Usage**: Identify which sensitive capabilities the browser has access to or will prompt the user for. This is crucial for understanding the browser's security posture.
*   **Expectation**: Permissions will vary widely by browser, OS, and user settings. Some permissions (e.g., `local-network`, `window-management`) might show as `unknown` or `denied` by default due to strict browser policies.

### 📊 System Info Dump

Gather detailed information about the system and browser performance.

*   **Functionality**: Provides a "Full System Recon Dump" (User Agent, screen resolution, language, timezone) and "Performance Timing" (RAM usage).
*   **Usage**: Collect telemetry about the host environment, useful for fingerprinting or understanding resource constraints.
*   **Expectation**: Basic system info is generally available. Performance timing (like RAM usage) might be restricted or less precise on some mobile browsers.

### 🔗 Deep Link App Launcher

Attempt to launch native applications or system settings using deep links/URI schemes.

*   **Functionality**: Tabs for Windows, iOS, and Android, each with buttons to trigger specific deep links (e.g., `ms-settings:`, `facetime://`, `intent://`).
*   **Usage**: Test for potential escapes from kiosk modes by trying to launch external applications or system configuration panels. This can reveal misconfigurations in locked-down environments.
*   **Expectation**: Success depends heavily on the OS, installed apps, and browser security settings. Many deep links will only work if the target application is installed and the OS allows the URI scheme.

### 🔓 Kiosk Escape Toolkit

Tools designed to test and potentially bypass restrictions in kiosk or locked-down browser environments.

*   **Functionality**: Open New Tab, Open `about:blank`, History Length Probe, Print Preview Escape.
*   **Usage**: These functions are intended to test browser behaviors that might allow a user to break out of a restricted web view. For example, `about:blank` can sometimes provide a less restricted context, and print preview can expose system dialogs.
*   **Expectation**: Effectiveness varies greatly. Modern browsers are highly resistant to these escapes, especially when hosted on a web server. Success is more likely in older or misconfigured kiosk setups.

### 🖼 Display & UI Control

Interact with the display and user interface elements.

*   **Functionality**: Screen EyeDropper, Prevent Sleep (WakeLock), Release WakeLock, Multi-Monitor Scan, Enter Fullscreen, Exit Fullscreen.
*   **Usage**: Test display-related APIs. WakeLock can prevent a device from sleeping, useful for maintaining an active screen. Multi-Monitor Scan can reveal connected displays.
*   **Expectation**: EyeDropper and Multi-Monitor Scan are typically desktop-only. WakeLock is widely supported but requires user interaction. Fullscreen APIs are generally robust.

### 💾 Storage & Data

Explore and dump various forms of browser-side storage.

*   **Functionality**: Storage Quota, Dump localStorage, Dump sessionStorage, Dump Cookies, List IndexedDB DBs.
*   **Usage**: Investigate what data a website or browser environment is storing locally. This can reveal sensitive information or provide vectors for data exfiltration.
*   **Expectation**: All these functions should generally work, as they interact with browser-controlled storage. The amount and type of data retrieved depend on what has been stored by visited websites.

## NETWORK & CONNECTIVITY

This section focuses on tools for network reconnaissance, IP address identification, and connectivity testing.

![NETWORK & CONNECTIVITY Screenshot](https://private-us-east-1.manuscdn.com/sessionFile/Sqrp2yIBMVfp3KJt29zeYW/sandbox/RHr73iyBzdSCN1TzmDlD5l-images_1776110990623_na1fn_L2hvbWUvdWJ1bnR1L3JlYWRtZV9hc3NldHMvZnVsbF92aWV3XzI.webp?Policy=eyJTdGF0ZW1lbnQiOlt7IlJlc291cmNlIjoiaHR0cHM6Ly9wcml2YXRlLXVzLWVhc3QtMS5tYW51c2Nkbi5jb20vc2Vzc2lvbkZpbGUvU3FycDJ5SUJNVmZwM0tKdDI5emVZVy9zYW5kYm94L1JIcjczaXlCemRTQ04xVHptRGxENWwtaW1hZ2VzXzE3NzYxMTA5OTA2MjNfbmExZm5fTDJodmJXVXZkV0oxYm5SMUwzSmxZV1J0WlY5aGMzTmxkSE12Wm5Wc2JGOTJhV1YzWHpJLndlYnAiLCJDb25kaXRpb24iOnsiRGF0ZUxlc3NUaGFuIjp7IkFXUzpFcG9jaFRpbWUiOjE3OTg3NjE2MDB9fX1dfQ__&Key-Pair-Id=K2HSFNDJXOU9YS&Signature=evq-WdogP91qbpCTOyRnt2QiV1yOmB3e8jgJKF6Nw6qRE-82CBHlPf5-~8CR5lJ2LF7t3oGA8BSTnf0rQUWVzfQbYpdx0SeG6rxgaaJIqISoCDJ5c6gp9iWBADJR4v06FewoQihibdbfeVKTuRAckmQgsWOrG8QLycbyNejT182siUvXuc7bGdCLw-oYz1yFd37lBxt-O-KMLv~lis7OmK2h8UpY8U3iclEB5SuseuVvJShmPWFzv59Pssk9swcje1jCBeDGD6llxtpHjwgvbmu2jNb-wN6o~C5tQKA9gfSnlFc2L3P8pSawaQei6hkS6FRJtOaF~k8Vpp15ji4ljw__)

### 🌐 Network Recon

Tools for identifying local and public IP addresses, and testing network reachability.

*   **Functionality**: WebRTC IP Leak (Full), Connected to Internet?, What is my IP?, Ping Home Routers, Ping Corporate Routers, Scan Chromecast/TV.
*   **Usage**: Determine the device's public and local IP addresses. Test internet connectivity and ping common router IPs. The WebRTC IP Leak attempts to expose local IP addresses that might otherwise be hidden.
*   **Expectation**: Public IP detection is highly reliable. Local IP detection via WebRTC is effective but can be blocked by some VPNs or browser settings. Pinging local network devices from a browser is heavily restricted; successful pings usually indicate the device is alive and responding to `no-cors` HTTP requests.

### 🔍 Subnet Discovery Scanner

An advanced scanner to discover active hosts and open ports within specified IP ranges or subnets.

*   **Functionality**: Scans single IPs, CIDR /24 subnets, IP ranges, or mixed comma-separated targets. Probes common ports (80, 443, 3000, etc.) and reports `[HIT]` for open ports and `[ACT]` for active (responding) hosts.
*   **Usage**: Perform active reconnaissance on local networks to identify live devices and their services. The Adaptive Noise Threshold dynamically adjusts to filter out false positives on mobile devices.
*   **Expectation**: `[HIT]` (Open) results are definitive. `[ACT]` (Active) results indicate a host is responding but the port might not be fully open to the browser (e.g., connection reset). Due to browser security, direct port scanning is limited, but this tool maximizes discovery within those constraints.

### 💻 Web Serial / USB

Access and interact with serial ports and USB devices connected to the host.

*   **Functionality**: Open Serial Port, Scan USB Devices, Scan Bluetooth, Access MIDI.
*   **Usage**: Test the browser's ability to communicate with external hardware. This is particularly useful for IoT devices, industrial controls, or specialized peripherals.
*   **Expectation**: These APIs are generally restricted to **Desktop Chrome/Edge** and require explicit user permission for each connection. They are typically not available on mobile browsers.

### 🔌 NFC

Interact with Near Field Communication (NFC) tags.

*   **Functionality**: Scan NFC Tag, Write NFC Tag.
*   **Usage**: Test NFC capabilities for reading and writing data to NFC tags. Useful for physical access control testing or data transfer.
*   **Expectation**: Primarily supported on **Android Chrome** (Android 10+). Not available on iOS or most desktop browsers.

### 🎮 Gamepad / Controller

Detect and poll connected gamepads or controllers.

*   **Functionality**: Scan for Gamepads, Start Live Poll, Stop Poll.
*   **Usage**: Determine if game controllers are connected and what input they provide. Can be used for understanding device interaction methods.
*   **Expectation**: Widely supported across platforms, but requires user interaction (e.g., pressing a button on the controller) to activate detection.

## MEDIA & SENSORS

This section explores the browser's access to media devices (camera, microphone) and various device sensors.

![MEDIA & SENSORS Screenshot](https://private-us-east-1.manuscdn.com/sessionFile/Sqrp2yIBMVfp3KJt29zeYW/sandbox/RHr73iyBzdSCN1TzmDlD5l-images_1776110990623_na1fn_L2hvbWUvdWJ1bnR1L3JlYWRtZV9hc3NldHMvZnVsbF92aWV3XzM.webp?Policy=eyJTdGF0ZW1lbnQiOlt7IlJlc291cmNlIjoiaHR0cHM6Ly9wcml2YXRlLXVzLWVhc3QtMS5tYW51c2Nkbi5jb20vc2Vzc2lvbkZpbGUvU3FycDJ5SUJNVmZwM0tKdDI5emVZVy9zYW5kYm94L1JIcjczaXlCemRTQ04xVHptRGxENWwtaW1hZ2VzXzE3NzYxMTA5OTA2MjNfbmExZm5fTDJodmJXVXZkV0oxYm5SMUwzSmxZV1J0WlY5aGMzTmxkSE12Wm5Wc2JGOTJhV1YzWHpNLndlYnAiLCJDb25kaXRpb24iOnsiRGF0ZUxlc3NUaGFuIjp7IkFXUzpFcG9jaFRpbWUiOjE3OTg3NjE2MDB9fX1dfQ__&Key-Pair-Id=K2HSFNDJXOU9YS&Signature=c-XhGqPTVdsmsUExuY7rXtrf8NScXHMfX50leXk-w6LgigXSpmExiGU4P~V3NaFg8clOuPRqm89cN-Xh9c~8O-MfJ15yft7cV5GgjSixoLG4sZPM4CcW0rZnp65hZ~wv1qdQisAPCIuA~nTOvJzKd6ot72gvJ6Mwo-YzxP45Mm5uz8nQTpnYxMhPkCqopGv26M334su7zRAiCO8NhL5NfB-YAPC-Ynxa8lxNQKaOYqg32eJoKF-XSpkjLA1pGYh71cdbhXeWhbsxlGfWWgd04NHLv1kspdI1FwbRPt14ktEE1hVBxGjS~rAscsK2EBf9zsAQ8mu5bBiUMm~XFmVNpw__)

### 📷 Camera & Video

Control and access the device's camera and screen sharing capabilities.

*   **Functionality**: Start Camera Stream (front/back toggle), Capture Photo, Stop Stream, Screen Share (Desktop).
*   **Usage**: Test camera access, switch between front and back cameras, and capture images. Screen sharing tests the ability to record or broadcast the display.
*   **Expectation**: Camera access requires explicit user permission. Front/back camera switching is well-supported on mobile. Screen sharing is typically a desktop-only feature.

### 🎤 Microphone & Audio

Manage audio input (microphone) and output (text-to-speech), and speech recognition.

*   **Functionality**: Start Microphone (with real-time waveform visualizer), Stop Mic, Text-to-Speech, Speech-to-Text.
*   **Usage**: Test microphone access and audio processing. Text-to-Speech and Speech-to-Text demonstrate browser capabilities for voice interaction.
*   **Expectation**: Microphone access requires explicit user permission. All features are generally well-supported across modern browsers.

### 🎮 Motion & Orientation

Access various motion and orientation sensors of the device.

*   **Functionality**: Track Tilt (DeviceOrientation), Accelerometer, Gyroscope, Magnetometer (with start/stop controls), Lock Landscape, Vibrate.
*   **Usage**: Gather data from device sensors to understand its physical orientation, movement, and magnetic field. Vibrate can trigger haptic feedback.
*   **Expectation**: Sensor access is generally available on mobile devices (iOS/Android). Lock Landscape and Vibrate are mobile-specific features. Sensor data streams continuously until stopped.

### 💡 Ambient Light & Proximity

Access environmental sensors like ambient light and proximity.

*   **Functionality**: Ambient Light Sensor, Proximity Sensor, Battery Status, Network Info, RAM Usage.
*   **Usage**: Collect environmental data and device telemetry. Ambient light and proximity sensors are useful for understanding the device's immediate surroundings. Battery, network, and RAM info provide system health metrics.
*   **Expectation**: Ambient Light and Proximity sensors are primarily supported on Android. Battery, Network, and RAM info are widely available but may offer varying levels of detail across platforms.

## IDENTITY & LOCATION

This section focuses on features related to user identity, biometrics, location, and browser fingerprinting.

![IDENTITY & LOCATION Screenshot](https://private-us-east-1.manuscdn.com/sessionFile/Sqrp2yIBMVfp3KJt29zeYW/sandbox/RHr73iyBzdSCN1TzmDlD5l-images_1776110990623_na1fn_L2hvbWUvdWJ1bnR1L3JlYWRtZV9hc3NldHMvZnVsbF92aWV3XzQ.webp?Policy=eyJTdGF0ZW1lbnQiOlt7IlJlc291cmNlIjoiaHR0cHM6Ly9wcml2YXRlLXVzLWVhc3QtMS5tYW51c2Nkbi5jb20vc2Vzc2lvbkZpbGUvU3FycDJ5SUJNVmZwM0tKdDI5emVZVy9zYW5kYm94L1JIcjczaXlCemRTQ04xVHptRGxENWwtaW1hZ2VzXzE3NzYxMTA5OTA2MjNfbmExZm5fTDJodmJXVXZkV0oxYm5SMUwzSmxZV1J0WlY5aGMzTmxkSE12Wm5Wc2JGOTJhV1YzWHpRLndlYnAiLCJDb25kaXRpb24iOnsiRGF0ZUxlc3NUaGFuIjp7IkFXUzpFcG9jaFRpbWUiOjE3OTg3NjE2MDB9fX1dfQ__&Key-Pair-Id=K2HSFNDJXOU9YS&Signature=v2krPBK8WpSZl~npoTBue7riHB1cwASe-VGe8tCqzdJuLqXybGX7Fh5FHQg46BnDQiqvaQ~~3WIX9dMc2gbwXgc49fUC0Id20mdlNS4gzYKiq5WIAAu3akNcDPvhx-7xzW8y8F3~VQt7ufj7HPr2L2pUPzyr6jNDLSirQQ~Hnn-HzeqN0h1Crft1P2zby5l1bBAXx~T4Tzh~-FvRmTA2GKkTNNa~r~6er4dCcmMYuB9YbfDLf82QZNEkt1klSfiQ5GkK8RQBHwnbHi0TvQu0mEkDNSZU63~cCG8uUytpu4H3Pxd9x8k8aWLT7bHZinBmclJHUHsP06x0Jb4XqeWYwQ__)

### 👤 Identity & Biometrics

Test biometric authentication and access location services.

*   **Functionality**: Biometric / WebAuthn Auth, GPS Location (High Accuracy), Watch GPS (Live Track), Stop GPS, Access System Contacts.
*   **Usage**: The Biometric Auth button attempts to trigger the OS-level biometric prompt (e.g., Face ID, Touch ID, Windows Hello). GPS functions retrieve and track the device's geographical location. Access System Contacts tests contact list access.
*   **Expectation**: Biometric authentication requires user interaction and device support. GPS access requires explicit user permission. Contact access is highly restricted and often requires specific OS-level permissions.

### 📋 Clipboard Access

Read from and write to the system clipboard.

*   **Functionality**: Copy Test String, Read Clipboard, Read Clipboard Image.
*   **Usage**: Test the browser's ability to interact with the system clipboard for text and image data. This is a common vector for data exfiltration or injection.
*   **Expectation**: Clipboard access requires explicit user permission, especially for reading. Writing to the clipboard is generally less restricted. Image clipboard access is a newer API and might have limited support.

### 🕵 Browser Fingerprint

Generate unique identifiers based on browser and system characteristics.

*   **Functionality**: Generate Fingerprint (User Agent, resolution, language, timezone), Canvas/GPU Fingerprint, Font Detection.
*   **Usage**: Understand how much unique information a browser exposes, which can be used to track users even without cookies. Canvas and font detection are common fingerprinting techniques.
*   **Expectation**: All these methods should work across platforms, as they rely on standard browser APIs. The uniqueness of the generated fingerprint depends on the combination of browser, OS, and hardware.

### 📢 Social & Notification Triggers

Trigger system-level notifications and social interaction prompts.

*   **Functionality**: Request Notification Permission, Fire Test Notification, Trigger Leave Confirmation, Alert Dialog, Confirm Dialog, Prompt Dialog.
*   **Usage**: Test the browser's ability to send notifications or trigger system-level dialogs. Leave confirmation, alert, confirm, and prompt dialogs are standard browser UI elements that can be used for social engineering or to interrupt user flow.
*   **Expectation**: Notifications require explicit user permission. All dialogs should function as expected across platforms, as they are fundamental browser features.

---

*This tool was made By **Christos Xenofontos**. You can connect with me on [LinkedIn](https://www.linkedin.com/in/chris857/). The project can be found here: [GitHub - eskeip.it](https://github.com/xristos8574/eskeip.it/).*
