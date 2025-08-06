---
title: "Nocti-Care"
author: "Youssef hamdy"
description: "A wearable system that uses sensors and AI to monitor and improve sleep quality for underserved communities."
created_at: "17/06/2025"
---

**Total time spent on project: 96 hours**

---

### 2025-06-17
**Hours spent:** 6
- Started by sketching the first conceptual design of the wristband form factor.  
- Reviewed literature on sleep monitoring sensors (GSR, HRM, gyroscope).  
- Created a block diagram of system flow from sensors to cloud and back to mobile.

---

### 2025-06-18  
**Hours spent:** 5  
- Finalized sensor selection for stress (GSR), motion (MPU6050), and heart rate.  
- Compared 4 different GSR sensor modules. Selected one with decent documentation.  
- Created first schematic in Fritzing for breadboarding.

---

### 2025-06-19  
**Hours spent:** 4  
- Built initial prototype on breadboard with jumper wires, Arduino Uno, GSR, and gyroscope.  
- Verified data readout via serial monitor.  
- Noticed inconsistent GSR signal; marked for smoothing filter implementation.

---

### 2025-06-20  
**Hours spent:** 6  
- Created basic firmware loop for all three sensors.  
- Implemented simple averaging for GSR readings.  
- Connected ESP8266 via software serial; tested Wi-Fi connectivity to Firebase.

---

### 2025-06-21  
**Hours spent:** 5  
- Started 3D design.  
- Designed slots for OLED, battery, and sensor holes for skin contact.  
- Made three iterations of the wrist housing for ergonomic comfort.

---

### 2025-06-22  
**Hours spent:** 4  
- Simulated heart rate data collection using dummy sensor to test reliability.  
- Implemented timestamping using RTC module for data sync.  
- Logged all data to micro SD card for redundancy.

---

### 2025-06-23  
**Hours spent:** 5  
- Integrated OLED screen (0.96” I2C) to show live GSR and BPM data.  
- Started building UI logic: sleep mode indication, progress bar, etc.  
- Added buzzer module as alarm trigger for wake events.

---

### 2025-06-24  
**Hours spent:** 6  
- Worked on cloud integration: Firebase and test MQTT broker.  
- Uploaded basic sensor data for remote ML analysis.  
- Designed JSON data structure to store night-long readings per user.

---

### 2025-06-25  
**Hours spent:** 5  
- Developed Python simulation to feed historical data for training ML model.  
- Model: Decision Tree with sleep/stress label classification.  
- Output: personalized sleep suggestion sent back to device.

---

### 2025-06-26  
**Hours spent:** 4  
- Connected mobile app prototype (Flutter) to Firebase.  
- Displayed live data and insights.  
- UI shows alert if erratic BPM or movement during night is detected.

---

### 2025-06-27  
**Hours spent:** 5  
- Revised 3D design for comfort: smoothed edges, added battery clip.  
- Simulated heat buildup inside case and checked airflow openings.  
- Selected TPU material for strap and ABS for core.

---

### 2025-06-28  
**Hours spent:** 5  
- Installed power regulation circuit (AMS1117 3.3V).  
- Ensured ESP and sensors were powered reliably off Li-ion battery.  
- Added TP4056 charging module and verified USB charging.

---

### 2025-06-29  
**Hours spent:** 6  
- Stress-tested all connections. Detected minor brownouts with OLED+ESP active.  
- Added capacitor to smooth current draw.  
- Re-tested under sleep simulation environment.

---

### 2025-06-30  
**Hours spent:** 4  
- Documented system: 3D files, sensor spec sheets.  
- Took photos.

---

### 2025-07-01  
**Hours spent:** 6  
- Finalized README structure: overview, purpose, diagrams, images.  
- Created detailed table BOM.  
- Ensured links and prices are verifiable.

---

### 2025-07-02  
**Hours spent:** 8  
- Simulated alternate sleep scenarios to test model response (insomnia, restlessness).  
- Tuned thresholds in the Arduino firmware for motion and stress trigger.  
- Verified data stability over 8-hour test.

---

### 2025-07-03  
**Hours spent:** 6  
- Reviewed journal and documentation for compliance.  
- Made sure no AI content, plagiarism, or missing sections.  
- Synced all files to GitHub, checked gallery.

---

### 2025-07-04  
**Hours spent:** 6  
- Final code cleanup and annotations.  
- Readme polish and retested all components.  
- Final test run: full night simulation + result capture.

---
## Images
- ![alt text](assests/3ddd.jpg)   
- ![alt text](assests/3dds.jpg)
- ![alt text](assests/3ds.jpg)
- ![alt text](assests/Pictu9re1.png)
- ![alt text](assests/Pictur7e1.png)
### Expected results
- ![the data distribution for Age and Physical activity level in the dataset from](assests/image.png)
- ![a heatmap of correlation for the features in the Sleep Quality dataset.](assests/image-1.png)
- ![the classification report for the XGBoost classifier (AI model)](assests/image-2.png)
- ![readings of Heart rate and GSR sensors and the time elapsed for displaying the data in the application with some statistical analysis](assests/image-3.png)
- ![This interprets the model.](assests/image-4.png)
- ![Illustrate the position, in which the user sleep](assests/image-5.png)
### Analysis
- ![Pipeline structure](assests/image-6.png)
- ![AI models: XGBoosting as a Classifier](assests/image-7.png)
- ![AI models: XGBoosting as a Classifier](assests/image-8.png)
- ![XGBoosting as a regressor](assests/image-9.png)


