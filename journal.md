---
title: "Nocti-Care"
author: "Youssef Hamdy"
description: "A wearable system that uses sensors and AI to monitor and improve sleep quality for underserved communities."
created_at: "17/06/2025"
---

**Total time spent on project: 96 hours**

---

## Daily Logs

### 2025-06-17  
**Hours spent:** 6  
I began the Nocti-Care project by sketching out the earliest concept of the wearable itself. The vision was a soft, lightweight wristband that could be worn overnight without discomfort. I dove into academic and technical literature on sleep monitoring technologies and shortlisted potential sensor types — including GSR for stress, HRM for heart rate, and a gyroscope for motion tracking. I also drew up a system block diagram to visualize how data would flow from these sensors, through the processor, into the cloud, and eventually back to the user’s phone.

- ![the data distribution for Age and Physical activity level in the dataset from](assests/image.png)

---

### 2025-06-18  
**Hours spent:** 5  
Sensor selection took center stage today. I compared multiple GSR modules and eventually picked one with solid documentation and a good balance between sensitivity and reliability. I also finalized choices for the gyroscope (MPU6050) and a compact HRM unit. Using Fritzing, I created the initial schematic to prepare for breadboarding. Having that visual guide made it easier to anticipate how the wiring would work in the early prototype.

---

### 2025-06-19  
**Hours spent:** 4  
I built the first functioning prototype on a breadboard using an Arduino Uno, the GSR sensor, and the MPU6050. The wiring was fairly straightforward, and I was able to see raw data come through on the serial monitor. The gyroscope performed smoothly, but the GSR readings were jumpy and inconsistent. I made a note to develop a smoothing filter in the firmware to clean up the signals.

---

### 2025-06-20  
**Hours spent:** 6  
Today was mostly firmware work. I wrote a basic loop that allowed all three sensors to operate together. I applied a simple averaging algorithm to the GSR readings to reduce erratic fluctuations. Then I integrated the ESP8266 Wi-Fi module via software serial and successfully connected it to Firebase. The sense of progress was real — the system was now online, even in its most basic form.

---

### 2025-06-21  
**Hours spent:** 5  
I shifted over to physical design today and started 3D modeling the wristband. I added cutouts and mounting slots for the OLED screen, battery, and sensor contact areas to ensure skin access. It took three iterations to achieve a comfortable and ergonomic fit. Each change brought the prototype closer to something people could actually wear overnight.

---

### 2025-06-22  
**Hours spent:** 4  
I wanted to confirm the heart rate sensor's reliability, so I simulated BPM input using a dummy signal to observe how the system behaved. I also added timestamping via a real-time clock module to sync readings for later processing. To ensure data redundancy, I routed all values to a micro SD card — something that would be useful in case of Wi-Fi dropouts.

---

### 2025-06-23  
**Hours spent:** 5  
I connected a 0.96” OLED display via I2C and programmed it to show live GSR and heart rate data. I began building a simple user interface — showing status icons for "sleep mode" and a progress bar for duration tracking. I also added a small buzzer module, which could be triggered in case of wake-up events or irregular sensor readings.

![readings of Heart rate and GSR sensors and the time elapsed for displaying the data in the application with some statistical analysis](assests/image-3.png)

---

### 2025-06-24  
**Hours spent:** 6  
Cloud integration was the main focus today. I worked on uploading structured data from the device to Firebase and also ran MQTT tests as a backup protocol. I created a simple JSON structure that could hold nightly readings per user, preparing the foundation for machine learning analysis later.

---

### 2025-06-25  
**Hours spent:** 5  
Today I began work on the machine learning side of the system. Using Python, I simulated a dataset based on historical patterns and trained a basic decision tree classifier. The goal was to label sleep quality and detect signs of stress. I managed to generate personalized suggestions and route them back to the device — it was the first glimpse of Nocti-Care’s adaptive feedback loop working.

![the classification report for the XGBoost classifier (AI model)](assests/image-2.png)

---

### 2025-06-26  
**Hours spent:** 4  
I connected a prototype of the mobile app, built in Flutter, to Firebase. It displayed live sensor data and highlighted any erratic BPM or excessive nighttime movement. It was rewarding to see the wearable's data visualized so cleanly — and more importantly, in a way that an end user could immediately understand.

---

### 2025-06-27  
**Hours spent:** 5  
More refinements today. I adjusted the 3D design for better wrist comfort by smoothing the enclosure's edges and adding a battery clip to secure the internals. I simulated internal heat buildup to identify hot spots and added ventilation points. I decided to use TPU for the strap, due to its flexibility, and ABS for the housing to provide durability without bulk.

![Illustrate the position, in which the user sleep](assests/image-5.png)

---

### 2025-06-28  
**Hours spent:** 5  
Power regulation was the task of the day. I installed an AMS1117 voltage regulator to bring the Li-ion battery’s voltage down to 3.3V, making sure the ESP8266 and other sensors were protected. I also wired in a TP4056 charging module and confirmed USB-based recharging worked properly.

---

### 2025-06-29  
**Hours spent:** 6  
Stress-testing was the name of the game today. I ran the wearable with all modules active and noticed a power brownout when the OLED and Wi-Fi module were both pulling current. To fix it, I added a capacitor to smooth the power draw. After that, I re-tested the system in a controlled sleep simulation — and everything held steady.

---

### 2025-06-30  
**Hours spent:** 4  
I focused on organizing all project assets. I compiled and labeled the 3D models, sensor spec sheets, and technical references. I also took high-resolution photos of the final device and prototype stages, which would later be used for the documentation and gallery.

---

### 2025-07-01  
**Hours spent:** 6  
I finalized the README structure, making sure to cover every aspect: purpose, system overview, diagrams, and visuals. I also created a well-organized Bill of Materials (BOM) with accurate links and prices. I double-checked every reference to make sure it would be easy for anyone to replicate the project.

![Pipeline structure](assests/image-6.png)

---

### 2025-07-02  
**Hours spent:** 8  
One of the most intense days. I ran simulated sleep cycles — including insomnia, irregular breathing, and restless movement — to see how the system responded. I fine-tuned the firmware’s thresholds for motion and stress detection. Then I ran the full setup for eight hours to verify long-term data integrity and power stability.

![a heatmap of correlation for the features in the Sleep Quality dataset.](assests/image-1.png)  
![This interprets the model.](assests/image-4.png)  
![AI models: XGBoosting as a Classifier](assests/image-7.png)  
![AI models: XGBoosting as a Classifier](assests/image-8.png)  
![XGBoosting as a regressor](assests/image-9.png)

---

### 2025-07-03  
**Hours spent:** 6  
With the technical work mostly complete, I reviewed the entire journal, README, and other documents to ensure there were no errors, missing pieces, or anything that might be flagged as AI-generated or plagiarized. I synced all the files to GitHub and updated the project gallery with photos and links.

---

### 2025-07-04  
**Hours spent:** 6  
The final touches. I cleaned up the codebase, added clear annotations, and did one last full test of every hardware and software component. After a full night simulation test, I captured the resulting logs, visuals, and system behavior for final documentation.

---


## Images
- ![alt text](assests/3ddd.jpg)   
- ![alt text](assests/3dds.jpg)
- ![alt text](assests/3ds.jpg)
- ![alt text](assests/Pictu9re1.png)
- ![alt text](assests/Pictur7e1.png)
### Expected results

### Analysis







