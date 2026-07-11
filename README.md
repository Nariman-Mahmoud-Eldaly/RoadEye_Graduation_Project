# RoadEye: Mobile Real-Time Accident Prediction & Emergency Broadcast System

RoadEye is an intelligent mobile application designed for graduation projects focused on automotive safety, telematics, and edge computing. It uses mobile sensor fusion (IMU) and machine learning to proactively predict/detect traffic accidents and seamlessly dispatch emergency data to public safety authorities and emergency contacts.

## 🚀 Core Features

- **Real-Time Predictive Analytics:** Continuously tracks lane drift, sudden decelerations, and tailgating parameters to warn drivers prior to potential collisions.
- **Robust Accident Detection:** Fuses Accelerometer and Gyroscope dynamic vector data with acoustic signatures to detect catastrophic impact forces ($G \geq 4g$).
- **Fail-Safe Emergency Dispatch:** If a crash is detected, a 15-second cancellation window opens. If uninterrupted, the system auto-dials local emergency services and sends precise GPS locations and medical profiles via SMS/Webhooks.
- **Blackbox Telemetry Recorder:** Stores the last 30 seconds of video data and IMU tracking leading up to an event for insurance and forensic evaluations.

## 🛠️ Architecture & Tech Stack

- **Frontend/Mobile:** Flutter (Cross-platform) / Kotlin (Native Android)
- **Machine Learning Layer:** TensorFlow Lite embedded on-device for real-time video inference and anomaly detection
- **Backend Infrastructure:** FastAPI / PostgreSQL for tracking critical geographical blackspots and managing user authentication
- **Communication Infrastructure:** Twilio API for fallback SMS and automated text-to-speech emergency calls

## 📂 Project Structure

```text
├── src/
│   ├── mobile/         # Mobile application source code (Flutter/Native)
│   ├── backend/        # Server-side telemetry endpoints & notification engines
│   └── models/         # Pre-trained TFLite accident prediction models
├── docs/               # System engineering files & architecture diagrams
└── README.md
```

## ⚙️ Quick Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/your-username/RoadEye_Graduation_Project.git
   cd RoadEye_Graduation_Project
   ```

2. **Setup Mobile Environment:**
   ```bash
   cd src/mobile
   flutter pub get
   flutter run
   ```

3. **Configure Environment Variables:**
   Create a `.env` file within the `src/backend/` directory:
   ```env
   TWILIO_ACCOUNT_SID=your_sid
   TWILIO_AUTH_TOKEN=your_token
   DATABASE_URL=postgresql://user:pass@localhost:5432/roadeye
   ```

## 🛡️ License

This project is licensed under the MIT License - see the LICENSE file for details.
