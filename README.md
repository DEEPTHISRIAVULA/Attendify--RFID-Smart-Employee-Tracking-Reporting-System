# 🚀 Attendify-RFID

### 📡 Smart Employee Tracking & Reporting System

An **RFID-based employee attendance system** developed using **LPC2148, Embedded C, SPI EEPROM, UART and Linux C**.

---

## 🎯 Overview

Attendify automates employee attendance using **RFID cards**.

The system:

* 🪪 Identifies employees using RFID
* 🕒 Records IN/OUT attendance with date & time
* 💾 Stores admin information in **SPI EEPROM**
* 🖥️ Communicates with a Linux application through UART
* 📊 Maintains employee records in a CSV file

---

## 🔧 Hardware

* **LPC2148 ARM7 Microcontroller**
* **RFID Reader & Cards**
* **16×2 LCD**
* **4×4 Keypad**
* **SPI EEPROM – AT25LC512**
* **MAX232**
* **USB-to-UART Converter**

---

## 💻 Software

* Embedded C
* Keil C Compiler
* Flash Magic
* Linux C
* CSV File Handling

---

## 🧩 Main Modules

| Module            | Purpose                                    |
| ----------------- | ------------------------------------------ |
| 📟 LCD            | Display messages and menus                 |
| ⌨️ Keypad         | Admin input and RTC editing                |
| 📡 RFID           | Employee identification                    |
| 🔌 UART           | Communication between LPC2148 and Linux    |
| 🔄 **SPI**        | Communication with SPI EEPROM              |
| 💾 **SPI EEPROM** | Stores admin card information              |
| 🕒 RTC            | Date and time for attendance               |
| 🐧 Linux C        | Employee management and attendance records |

---

## 🔄 System Flow

```text
        RFID Card
            │
            ▼
       ┌──────────┐
       │  LPC2148 │
       └────┬─────┘
            │
      ┌─────┴─────┐
      │           │
      ▼           ▼
   SPI EEPROM    UART
      │           │
      │           ▼
      │      Linux Application
      │           │
      │           ▼
      │        users.csv
      │
      ▼
  Admin Card
  Information
```

---

## 🔐 Admin Operations

Admin card provides:

1. **Admin Card Change**
2. **RTC Information Change**

The admin card number is stored in the **AT25LC512 SPI EEPROM**.

---

## 👤 Employee Attendance

When an employee scans the RFID card:

* Employee ID is identified
* IN/OUT status is updated
* Date and time are recorded
* Working hours are calculated
* Attendance information is stored in `users.csv`

---

## 📊 CSV Records

The Linux application maintains employee information such as:

```text
S.No | User ID | User Name | Date | Working Hours | IN/OUT Status | IN Time | OUT Time
```

---

## 🔌 Communication

The LPC2148 communicates with the Linux application through **UART**.

Example messages:

```text
Admin Card → ACARDNUMBER$
User Card  → UCARDNUMBERRTCINFO$
```

---

## 🛠️ Technologies

**ARM7 • Embedded C • LPC2148 • RFID • SPI • EEPROM • UART • RTC • Linux C • CSV**

---

## 👨‍💻 Project

**Attendify-RFID — Smart Employee Tracking & Reporting System**

Built as an embedded systems project integrating **RFID, SPI EEPROM, UART communication and Linux-based attendance management**.
