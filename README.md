# SMART-ATTENDANCE
SMART ATTENDANCE USING FACE RECOGINATION AND GAZE TRACKING  (SMS SENDING)
📘 SMART ATTENDANCE SYSTEM – README
📌 Project Overview

The Smart Attendance System is an AI-based solution that combines:

🎯 Face Recognition

👁️ Gaze / Attention Tracking

📊 Automated Attendance Logging

📩 SMS Alerts to Parents (via Twilio)

This system is designed for college/classroom CCTV integration, which aligns with your department CCTV implementation requirement.

🏗️ System Architecture
4
🔄 Flow:

Capture student images

Train face recognition model

Recognize students via webcam/CCTV

Track gaze for attention score

Mark attendance

Send SMS to absentees

📂 Project Structure
File	Description
main.py	Menu-based controller program 

main


capture_dataset.py	Capture student face images 

capture_dataset


train_model.py	Train face encodings and generate trained_faces.pkl 

train_model


recognize_attendance.py	Face recognition & attendance marking 

recognize_attendance


gaze_tracking.py	Eye gaze detection using dlib landmarks 

gaze_tracking


attendance_gaze.py	Combined face + attention score system 

attendance_gaze


run_session.py	Full pipeline (recognition + gaze + SMS) 

main_model


sms_alert.py	Send SMS to absent students 

sms_alert


send_sms_all.py	Send SMS to all students 

send_sms_all


test_face_gaze.py	Test webcam + gaze detection 

test_face_gaze


test_sms_absentees.py	Test SMS functionality 

test_sms_absentees

⚙️ Requirements
🔹 Software Requirements

Python 3.8 – 3.11

Webcam / CCTV camera

Windows OS (recommended)

🔹 Install Dependencies
pip install opencv-python
pip install face_recognition
pip install mediapipe
pip install dlib
pip install twilio
pip install numpy
🚀 How To Run (Step-by-Step)
1️⃣ Capture Dataset

Run:

python capture_dataset.py

Enter student name

Press SPACE to capture images

Press ESC to exit

Images saved inside:

dataset/<student_name>/
2️⃣ Train Model
python train_model.py

Creates:

trained_faces.pkl
3️⃣ Recognize Attendance Only
python recognize_attendance.py

Press Q to stop

Attendance saved in:

attendance.csv
4️⃣ Run Complete Smart Session (Recommended)
python run_session.py

This will:

✔ Recognize faces
✔ Track attention score
✔ Mark attendance
✔ Send SMS to absentees

5️⃣ Use Main Menu
python main.py

Menu options: 

main

1) Capture dataset
2) Train model
3) Recognize attendance
4) Run full session
5) Send SMS
👁️ Attention Score Logic

The system uses MediaPipe Face Mesh Iris Landmarks to calculate:

Eye center

Distance from screen center

Normalized attention score (0 → 1)

Implemented in: 

attendance_gaze

📩 SMS Alert System

Uses Twilio API

Environment Variables Required:

TWILIO_ACCOUNT_SID
TWILIO_AUTH_TOKEN
TWILIO_FROM

Students list must be in:

students.csv

Format:

Name,Phone
John,+91XXXXXXXXXX

SMS logic in: 

sms_alert

📊 Output Files
File	Purpose
attendance.csv	Present students
attendance_log.csv	Attention score log
trained_faces.pkl	Saved face encodings
🧠 Technologies Used

OpenCV

face_recognition (dlib-based)

MediaPipe Face Mesh

NumPy

Twilio SMS API

CSV / Pickle

🔐 Security Notes

⚠ Do NOT hardcode Twilio credentials in production.
⚠ Use environment variables instead.
⚠ Ensure camera permissions are enabled.

🏫 Use Case for College CCTV Deployment

For department CCTV:

Connect CCTV stream via RTSP

Replace cv2.VideoCapture(0) with RTSP URL

Deploy on local server

Connect to centralized attendance database

📌 Future Improvements

Web Dashboard (Flask/Django)

Cloud deployment

Real-time database (Firebase)

Admin panel

Multi-camera support

Face anti-spoofing

AI-based attention analytics report

👨‍💻 Author

Gowrish N
Bengaluru, Karnataka
AI & Computer Vision Developer
