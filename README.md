

# 🏥 Healthcare Database System

This project is a comprehensive **SQL-based Healthcare Database** designed to manage and analyze data related to patients, doctors, appointments, prescriptions, and billing. It includes queries for data retrieval, analytics, performance tracking, and reporting to support healthcare operations and decision-making.

---

## 📦 Project Overview

The healthcare database supports:

* Patient record management
* Appointment scheduling and tracking
* Prescription logging
* Billing and payment tracking
* Analytical insights (demographics, trends, doctor performance)

---

## 🛠️ Technologies Used

* **SQL (MySQL syntax)**
* Relational Database Concepts
* Data Analysis using Aggregate Functions and Joins

---

## 🗃️ Database Schema Overview

The project uses a relational database named `healthcare` with the following main tables:

| Table           | Description                     |
| --------------- | ------------------------------- |
| `patients`      | Stores patient demographic data |
| `doctors`       | Stores doctor information       |
| `appointments`  | Stores appointment records      |
| `prescriptions` | Stores medications prescribed   |
| `billing`       | Stores billing and payment data |

---

## 📌 Key Features and Queries

### 1. 🧾 Data Retrieval

```sql
SELECT * FROM patients;
SELECT * FROM doctors;
SELECT * FROM appointments;
SELECT * FROM prescriptions;
SELECT * FROM billing;
```

---

### 2. 👥 Patient Management

* Appointments for a specific patient
* Prescriptions from specific appointment
* Detailed view of each patient
* Patients with recent or no appointments
* Patient demographics (e.g., gender)

```sql
SELECT * FROM appointments WHERE patient_id = 1;
SELECT * FROM prescriptions WHERE appointment_id = 1;
```

---

### 3. 📅 Appointments

* Appointment trends by month or year
* Reasons for visits
* Day-wise counts
* Appointments with/without billing
* Appointments by doctor or specialty

```sql
SELECT DATE_FORMAT(appointment_date,'%Y-%m') AS month, COUNT(*) FROM appointments GROUP BY month;
```

---

### 4. 💊 Prescription Tracking

* Frequently prescribed medications
* Prescriptions with pending billing
* Dosage analysis by medication

```sql
SELECT medication, COUNT(*) AS frequency
FROM prescriptions
GROUP BY medication
ORDER BY frequency DESC;
```

---

### 5. 💰 Billing & Payments

* Total billed and paid
* Billing by doctor or appointment
* Payment trends
* Pending or unpaid bills

```sql
SELECT 
  (SELECT SUM(amount) FROM billing) AS total_billed,
  (SELECT SUM(amount) FROM billing WHERE status = 'Paid') AS total_paid;
```

---

### 6. 📈 Analytics & Reports

* Top patients by billing
* Doctor performance (number of appointments)
* Monthly and yearly trends
* Correlation between appointments and billing

```sql
SELECT d.doctor_id, d.first_name, d.last_name, COUNT(a.appointment_id) AS number_of_appointments
FROM doctors d
LEFT JOIN appointments a ON d.doctor_id = a.doctor_id
GROUP BY d.doctor_id;
```

---

## 🧪 Example Use Cases

* **Clinic Managers**: Monitor doctor workload and patient inflow.
* **Finance Teams**: Track revenue trends, unpaid bills, and performance.
* **Data Analysts**: Perform demographic studies or healthcare trend analysis.

---

## ✅ How to Use

1. Clone the repository:

   ```bash
   git clone https://github.com/your-username/healthcare-database.git
   ```

2. Import the database:

   ```sql
   CREATE DATABASE healthcare;
   USE healthcare;
   ```

3. Run the SQL queries in your MySQL Workbench or compatible tool.

---


## 📬 Contact

**Author:** Your Name
📧 [your.email@example.com](mahek456shrivastava@gmail.com)
🔗 [GitHub Profile](https://github.com/Mahek45600)
