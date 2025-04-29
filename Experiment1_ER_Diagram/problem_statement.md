# Experiment 1: Entity-Relationship (ER) Diagram

## 🎯 Objective:
To understand and apply the concepts of ER modeling by creating an ER diagram for a real-world application.

## 📚 Purpose:
The purpose of this workshop is to gain hands-on experience in designing ER diagrams that visually represent the structure of a database including entities, relationships, attributes, and constraints.

---

## 🧪 Choose One Scenario:

### 🔹 Scenario 1: University Database
Design a database to manage students, instructors, programs, courses, and student enrollments. Include prerequisites for courses.

**User Requirements:**
- Academic programs grouped under departments.
- Students have admission number, name, DOB, contact info.
- Instructors with staff number, contact info, etc.
- Courses have number, name, credits.
- Track course enrollments by students and enrollment date.
- Add support for prerequisites (some courses require others).

---

### 🔹 Scenario 2: Hospital Database
Design a database for patient management, appointments, medical records, and billing.

**User Requirements:**
- Patient details including contact and insurance.
- Doctors and their departments, contact info, specialization.
- Appointments with reason, time, patient-doctor link.
- Medical records with treatments, diagnosis, test results.
- Billing and payment details for each appointment.

---

## 📝 Tasks:
1. Identify entities, relationships, and attributes.
2. Draw the ER diagram using any tool (draw.io, dbdiagram.io, hand-drawn and scanned).
3. Include:
   - Cardinality & participation constraints
   - Prerequisites for University OR Billing for Hospital
4. Explain:
   - Why you chose the entities and relationships.
   - How you modeled prerequisites or billing.

# ER Diagram Submission - Student Name

## Scenario Chosen:
Hospital Database

## ER Diagram:
![image](https://github.com/user-attachments/assets/9c53d469-aadc-433d-afb3-e0fa28879a1a)


## Entities and Attributes:

---

### **1. DEPARTMENT**  
**Explanation:**  
Represents different medical or administrative divisions in a hospital (e.g., Cardiology, Pediatrics).  
**Attributes:**  
- **Department ID** – Unique identifier for each department.  
- **Name** – The name of the department.  
- **Department Head** – The doctor or person in charge of the department.  
**Constraints:**  
- Each department has a unique ID.  
- One department is handled by only one head (assumed one-to-one).  

---

### **2. DOCTOR**  
**Explanation:**  
Stores information about doctors working in the hospital.  
**Attributes:**  
- **Doctor ID** – Unique identifier for each doctor.  
- **Full Name** – The doctor’s name.  
- **Phone Number** – Contact details.  
- **Specialization** – Field of medical expertise (e.g., orthopedics, neurology).  
**Constraints:**  
- Each doctor must belong to a department.  
- A doctor can handle multiple appointments and give prescriptions.

---

### **3. PATIENT**  
**Explanation:**  
Represents individuals receiving medical care or consultation.  
**Attributes:**  
- **Patient ID** – Unique ID assigned to each patient.  
- **Full Name** – Patient's name.  
- **Date of Birth** – For age and record-keeping.  
- **Insurance** – Health insurance details.  
- **Phone Number** – Contact information.  
**Constraints:**  
- One patient can have multiple appointments.  
- Patient ID is unique across the system.

---

### **4. APPOINTMENT**  
**Explanation:**  
Details about the scheduling of a visit between a patient and a doctor.  
**Attributes:**  
- **Appointment ID** – Unique identifier.  
- **Date and Time** – When the appointment is scheduled.  
- **Reason for Visit** – The health concern or issue for the appointment.  
**Constraints:**  
- Each appointment is linked to one patient and one doctor.  
- Appointment ID must be unique.

---

### **5. PRESCRIPTION**  
**Explanation:**  
Contains details about the medication and medical advice provided by a doctor.  
**Attributes:**  
- **Medicine** – Drugs or treatments prescribed.  
- **Test Result** – Results of medical tests.  
- **Diagnoses** – Doctor’s diagnosis of the condition.  
**Constraints:**  
- Each prescription is issued to one patient.  
- Prescriptions can vary for each appointment or visit.

---

## Relationships and Constraints:

Relationships (with connecting entities):
TREATED BY → between Appointment and Doctor

BY → between Appointment and Patient

FOR → between Appointment and Department

HANDLES → between Doctor and Department

TREATS → between Doctor and Department

MEDICATION → between Patient and Prescription

---

### **1. FOR** (between APPOINTMENT and DEPARTMENT)  
**Explanation:**  
Represents that an appointment is made **for** a particular department (e.g., cardiology).  
**Constraint:**  
- Many appointments can be made for one department (many-to-one).

---

### **2. TREATED BY** (between APPOINTMENT and DOCTOR)  
**Explanation:**  
Indicates that each appointment is **handled by** a specific doctor.  
**Constraint:**  
- Many appointments can be treated by one doctor (many-to-one).  
- A doctor can handle multiple appointments.

---

### **3. BY** (between APPOINTMENT and PATIENT)  
**Explanation:**  
Shows that an appointment is **booked by** a patient.  
**Constraint:**  
- One patient can have multiple appointments.  
- Each appointment is for one patient (many-to-one).

---

### **4. TREATS** (between DOCTOR and DEPARTMENT)  
**Explanation:**  
Indicates that a doctor **treats patients** in a specific department.  
**Constraint:**  
- A doctor can work in only one department (assuming 1:1 or many-to-one).  
- A department can have many doctors.

---

### **5. HANDLES** (between DOCTOR and DEPARTMENT)  
**Explanation:**  
Shows which department is **handled or managed by** a doctor.  
**Constraint:**  
- A doctor might be head of or responsible for managing a department.  
- Usually one doctor handles one department (one-to-one or one-to-many depending on policy).

---

### **6. MEDICATION** (between PATIENT and PRESCRIPTION)  
**Explanation:**  
Represents that a patient receives a **prescription** with medication, diagnosis, and tests.  
**Constraint:**  
- A patient can receive many prescriptions.  
- Each prescription belongs to one patient (many-to-one).

---


## Extension (Prerequisite / Billing):
In the given ER model, prerequisites and billing are not explicitly represented but can be incorporated logically. Prerequisites such as prior test results, referrals, or approvals can either be added as additional attributes in the APPOINTMENT entity (like "Referred By" or "Prior Test ID") or modeled as a separate entity called PREREQUISITE. This new entity would store information like the type of prerequisite (test, referral, etc.), its description, and link it to the corresponding appointment. This allows an appointment to have multiple prerequisites, ensuring all necessary conditions are met before a patient’s visit.

For billing, a new entity called BILLING can be introduced to capture all financial transactions related to appointments. The BILLING entity would include attributes such as Billing ID, Appointment ID, Patient ID, Amount, Payment Status (paid/unpaid), and Payment Method (cash, card, insurance, etc.). Billing would be linked to both the APPOINTMENT and the PATIENT, enabling one appointment to generate one or multiple bills if needed. This design ensures that the system effectively tracks all medical and financial information separately but keeps them well connected for easy management.

## Design Choices:
The entities like PATIENT, DOCTOR, DEPARTMENT, APPOINTMENT, and PRESCRIPTION were chosen because they represent the core components of any hospital or healthcare management system. Each of these plays a distinct role: patients seek treatment, doctors provide care, appointments organize the interactions, departments classify medical specialties, and prescriptions document the medical advice.

The relationships such as TREATED BY, BY, FOR, HANDLES, TREATS, and MEDICATION were selected to correctly map the real-world interactions between these entities. For instance, an appointment must be linked to a doctor (TREATED BY) and a patient (BY), and prescriptions must be associated with the patients receiving them (MEDICATION). These relationships ensure that the data model mirrors the real-world workflow clearly and efficiently.

Some assumptions were made to simplify the model: for example, each appointment involves only one patient and one doctor (no group consultations), each department has one head (HANDLE relationship is one-to-one), and a patient can have multiple appointments and prescriptions. These assumptions keep the database design straightforward, scalable, and easy to manage while covering the basic operations of a hospital.

## RESULT:
Thus the ER Diagram for the Hospital Database has been drawn successfully.
