Smart Residential Security System
An intelligent, real-time surveillance system that uses computer vision and deep learning to automatically detect malicious activities in residential common areas. The system identifies threats by analyzing human actions, verifies identity using facial recognition to reduce false alarms, and provides a proactive solution to enhance resident safety.
A conceptual image of the final application's user interface.
Key Features
Real-time Action Recognition: Identifies complex, motion-based threats from a live video feed.
Fighting & Physical Altercations
Forced Entry & Vandalism
Unauthorized Package Theft
Tailgating / Unauthorized Entry
Health & Safety Monitoring: Detects potential emergencies.
Fall Detection
Suspicious Loitering
Identity Verification: Integrates facial recognition to differentiate between authorized residents and unknown individuals, drastically reducing false positives.
Automated Alerts: Generates on-screen visual alerts when a credible threat is detected.
Technology Stack
This project is built entirely with free, open-source tools.
Hardware:
Standard PC/Laptop
Webcam (built-in or USB)
Software & Libraries:
Python: Core programming language.
OpenCV: For real-time video capture and image processing.
MediaPipe: For high-fidelity human pose estimation.
TensorFlow / Keras: For building and training the LSTM deep learning model.
face_recognition: For the identity verification module.
Scikit-learn: For data preparation and model evaluation.
NumPy: For numerical operations on landmark data.
System Architecture
The system operates on a smart, trigger-based workflow to ensure efficiency:
Primary Analysis (Always On): The MediaPipe Pose Estimation model runs continuously, extracting skeleton data from every frame of the video feed.
Sequence Classification: This data is fed into a trained LSTM model which analyzes the sequence of movements to classify the ongoing action.
Secondary Verification (On-Demand): If the LSTM model detects a "trigger" event (e.g., package_pickup), the Facial Recognition module is activated.
Final Decision: An alert is generated only if the action is deemed a threat and the identity verification fails (or is not required for the action).
Setup and Installation
Follow these steps to set up the project on your local machine.
1. Clone the Repository
git clone [Your-Repository-URL]
cd [repository-folder-name]


2. Create a Virtual Environment
It is highly recommended to use a virtual environment.
python -m venv venv
source venv/bin/activate  # On Windows use `venv\Scripts\activate`


3. Install Dependencies
Install all the required Python libraries from the requirements.txt file.
pip install -r requirements.txt


(Note: You will need to create a requirements.txt file containing the libraries listed in the Technology Stack section).
4. Create Data Folders
The system requires a specific folder structure to save and read data. Create the following directories in your project root:
Action_Data/
Face_Database/
How to Use
The project is divided into three main scripts. Run them in the following order.
Step 1: Collect Data
Run the collect_data.py script to capture training data using your webcam. The script will guide you through collecting sequences for each predefined action.
python collect_data.py


Step 2: Train the Model
After collecting a sufficient amount of data, run the training script. This will process the collected landmark data, train the LSTM model, and save the result as action_model.h5.
python train_model.py


Step 3: Run the Real-time Application
Execute the main script to start the live surveillance system.
python run_realtime.py


The application will open your webcam, perform real-time analysis, and display alerts on the screen.
Dataset
This project requires a custom dataset. The model's accuracy is directly dependent on the quality and variety of the training data. The dataset should be built by:
Simulating Custom Scenarios: Recording videos of actions specific to a residential lobby (package theft, tailgating, normal entry, etc.) to ensure the data matches the target environment.
Using Public Datasets: Supplementing your custom data with real-world examples of generic threats (fighting, vandalism) from sources like the UCF-Crime dataset to improve model robustness.
Creating a Face Gallery: Taking photos of "authorized" individuals to build the database for the identity verification module.
Future Scope
Multi-Camera Integration: Fuse feeds from multiple cameras to handle occlusion and provide wider coverage.
Advanced Alerting: Integrate with services like Twilio or email APIs to send SMS/email notifications when a threat is detected.
Edge Deployment: Optimize the model to run on a low-power device like a Raspberry Pi for a standalone hardware solution.
Object Detection: Incorporate an object detection model (e.g., YOLO) to identify suspicious items like weapons or tools.
License
This project is licensed under the MIT License - see the LICENSE.md file for details.
