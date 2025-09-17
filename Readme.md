
# 🏠 Smart Residential Security System

**Smart Residential Security System** is an intelligent, real-time surveillance solution that leverages computer vision and deep learning to detect malicious activities in residential areas. It analyzes human actions from live video feeds, verifies identities via facial recognition to reduce false alarms, and provides proactive alerts to enhance resident safety.

---

## 🔑 Key Features

- 🎯 **Real-time Action Recognition** of threats:
  - Fighting & Physical Altercations  
  - Forced Entry & Vandalism  
  - Unauthorized Package Theft  
  - Tailgating / Unauthorized Entry  
- 🚨 **Health & Safety Monitoring**:
  - Fall Detection  
  - Suspicious Loitering  
- 🆔 **Identity Verification** using facial recognition to distinguish residents from intruders.  
- ⚡ **Automated Alerts** displayed in real-time on detection of threats.

---

## 🛠️ Tech Stack

- **Frontend**: OpenCV (Video Display Interface)  
- **Backend**: Python  
- **Machine Learning**:
  - TensorFlow / Keras (LSTM Model)  
  - MediaPipe (Pose Estimation)  
  - face_recognition (Identity Verification)  
  - scikit-learn, NumPy (Data processing)  
- **Hardware**:
  - Webcam (built-in or USB)  
  - Standard PC or Laptop  

---

## 📁 Project Structure

```
smart-security-system/
├── Action_Data/       # Collected action sequences for training
├── Face_Database/     # Stored faces for identity verification
├── collect_data.py    # Script to collect landmark data
├── train_model.py     # Script to train the LSTM action recognition model
├── run_realtime.py    # Main real-time monitoring script
├── requirements.txt   # Python dependencies
├── action_model.h5    # Trained LSTM model
├── README.md          # Project documentation
└── ...
```

---

## ⚙️ Setup Instructions

1. **Clone the repository**  
   ```bash
   git clone [Your-Repository-URL]  
   cd [repository-folder-name]  
   ```

2. **Create and activate a virtual environment**  
   ```bash
   python -m venv venv  
   source venv/bin/activate   # On Windows: venv\Scripts\activate  
   ```

3. **Install dependencies**  
   ```bash
   pip install -r requirements.txt  
   ```

4. **Run the application**  
   - First, collect training data:  
     ```bash
     python collect_data.py  
     ```  
   - Then, train the action recognition model:  
     ```bash
     python train_model.py  
     ```  
   - Finally, run the real-time security system:  
     ```bash
     python run_realtime.py  
     ```  
   - Open your webcam and monitor the interface for real-time alerts.

---

## 🌟 Future Enhancements

- Multi-camera integration for broader coverage  
- Advanced SMS/Email alerting using Twilio or similar services  
- Edge Deployment on Raspberry Pi or Jetson Nano  
- Object detection to identify weapons or suspicious objects  

---

## 📜 License

This project is licensed under the MIT License.
