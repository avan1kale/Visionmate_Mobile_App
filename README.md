# 👁️ VisionMate — Mobile Assistive Vision System

**Location**: `E:\DEEP LEARNING\VisionMate_Mobile_App`  
**Trained Models Included**: `models/best.tflite` and `models/best.onnx` (8 target classes: Person, Car, Bicycle, Motorcycle, Chair, Table, Door, Books)

---

## 🌟 Overview: Designed for Instant Access on ALL Phones

To ensure this app is **easily downloaded, installed, and accessible on any phone** (both Android and iOS), VisionMate Mobile is provided in two complementary forms:

| Solution | Target Device | How to Access / Install |
|---|---|---|
| **Universal Mobile App (PWA)** *(Recommended)* | **ALL Phones** (Android, Samsung, Pixel, iPhone, etc.) | **Instant**: Open the local Wi-Fi link in Chrome/Safari, tap **"Add to Home Screen"** or **"Install App"**. It downloads and creates a standalone App icon on your phone! |
| **Native Android Project** | **Android Devices** (APK) | Open `android_native/` in Android Studio, connect your phone, and build the APK. |

Both solutions:
1. ✅ Access your phone's **back camera** in real-time.
2. ✅ Prioritize obstacles in your **centre of vision** (Left / Centre / Right).
3. ✅ Relay spoken instructions **through your Bluetooth earphones/headphones if connected**, or **through the phone speaker**.
4. ✅ Enforce a **2-second rate limit** to prevent voice spamming.
5. ✅ Provide an on-demand **Book OCR title reader**.
6. ✅ Provide **emergency obstacle proximity alerts** (*"Caution! Stop! Obstacle directly ahead!"*).

---

## 🚀 Quick Start: Running on Any Phone in 60 Seconds

### Step 1: Start the VisionMate Server on your Laptop
Open PowerShell or double-click `run_server.bat` in `E:\DEEP LEARNING\VisionMate_Mobile_App`:

```powershell
cd "E:\DEEP LEARNING\VisionMate_Mobile_App"
& "E:\DEEP LEARNING\CORNERSTONE\.venv\Scripts\python.exe" run_server.py
```

The terminal will show your local Wi-Fi connection URL, for example:
```
======================================================================
   👁️  VISIONMATE — UNIVERSAL MOBILE ASSISTIVE VISION SYSTEM
======================================================================
📱 MOBILE ACCESS URL:  http://192.168.1.45:8080
💻 LAPTOP BROWSER URL: http://localhost:8080
======================================================================
```

### Step 2: Open on your Phone
1. Connect your phone to the **same Wi-Fi network** as your laptop.
2. Open **Google Chrome** (on Android) or **Safari** (on iPhone).
3. Enter the **Mobile Access URL** shown in your terminal (e.g., `http://192.168.1.45:8080`).

### Step 3: Install as an App on your Phone's Home Screen
- **On Android**: Tap the Chrome menu (`⋮` three dots at the top right) $\to$ select **"Install App"** or **"Add to Home screen"**.
- **On iPhone**: Tap the Safari Share button (the box with an upward arrow $\uparrow$) $\to$ select **"Add to Home Screen"**.

> 🎉 **Done!** VisionMate is now installed on your phone with its own App icon. Launching it opens full-screen without any browser address bar!

### Step 4: Use the Assistive System
1. Tap **"Open Back Camera & Start"**.
2. **Audio / Bluetooth**:
   - Pair any Bluetooth earphones (AirPods, Galaxy Buds, boAt, etc.) with your phone.
   - The top status pill will automatically display `🎧 Bluetooth Earphones`.
   - Voice guidance will speak directly into your ears! If you turn off Bluetooth, it immediately falls back to the phone speaker.
3. **Directions**:
   - The screen shows **LEFT**, **CENTRE (FOV)**, and **RIGHT** navigational zones.
   - Center obstacles trigger spoken cues (*"Person directly ahead"*, *"Chair on your left"*).
4. **Eyes-Free Book OCR via Hardware Button**:
   - **Press your phone's physical VOLUME DOWN (🔉) button** anytime!
   - Your phone will give a brief tactile haptic vibration, snap a full-resolution photo of the book, and read the visible title aloud through your Bluetooth earphones or speaker.
   - You can also tap the on-screen button if preferred.
5. **Obstacle Proximity Alerts**:
   - Tap the **📡 Dist** button to test distance alerts. When under 45 cm, an urgent red alert fires (*"DANGER! OBSTACLE AHEAD! STOP!"*).

---

## 🛠️ Method B: Compiling the Native Android APK (Android Studio)

If you want to build a native Android `.apk` file:
1. Open **Android Studio**.
2. Click **Open Project** and select `E:\DEEP LEARNING\VisionMate_Mobile_App\android_native`.
3. The project includes:
   - `best.tflite` pre-copied inside `app/src/main/assets/`.
   - `CameraX` setup with `DEFAULT_BACK_CAMERA`.
   - `TFLiteDetector.kt` for 8-class inference and Non-Maximum Suppression.
   - `SpeechManager.kt` with automatic Bluetooth SCO / A2DP audio routing.
4. Click **Build $\to$ Build Bundle(s) / APK(s) $\to$ Build APK(s)** to generate `app-debug.apk`.
5. Transfer and install `app-debug.apk` onto any Android phone.
"# Visionmate_Mobile_App" 
