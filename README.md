# Attendify – RFID Smart Employee Tracking & Reporting System

An **RFID-based employee attendance and tracking system** developed using **Embedded C, LPC2148 ARM7, and Linux C programming**.

The system uses an RFID reader to identify employees, records their IN/OUT attendance with date and time, and stores attendance information in a CSV database through a Linux-based application.

---

## ✨ Features

* RFID-based employee identification
* Admin authentication using an RFID card
* Add, edit and delete employee information
* Employee IN/OUT attendance tracking
* RTC-based date and time recording
* SPI EEPROM data storage
* LCD and keypad interface
* UART communication between LPC2148 and Linux PC
* CSV-based employee and attendance records
* Working-hours calculation

---

## 🏗️ System Architecture

```text
                    RFID CARD
                        │
                        ▼
                  RFID READER
                        │
                        ▼
                 ┌─────────────┐
                 │   LPC2148   │
                 │ Embedded C  │
                 └──────┬──────┘
                        │
                     UART0
                        │
                        ▼
                 ┌─────────────┐
                 │ Linux C App │
                 │   main.c    │
                 └──────┬──────┘
                        │
                        ▼
                  CSV Database
```

The project contains **two application programs**:

1. **Embedded application** – runs on the LPC2148 and handles RFID, LCD, keypad, RTC, SPI EEPROM, interrupts and UART.
2. **Linux application** – runs on the PC, communicates with the controller through UART and manages employee/attendance information in the CSV file.

---

## 🔄 How It Works

### 👨‍💼 Admin

When the **Admin RFID card** is scanned:

```text
Admin Card
    ↓
LPC2148
    ↓
UART
    ↓
Linux main.c
    ↓
Admin selects operation
    ↓
Enter employee details
    ↓
Update CSV
```

The Linux application allows the admin to perform operations such as **adding, editing and deleting users**.

### 👤 Employee

When an employee scans their RFID card:

```text
Employee RFID Card
        ↓
    LPC2148
        ↓
    Employee ID
        ↓
     Linux C
        ↓
   Read/Update CSV
        ↓
   IN / OUT + Date + Time
        ↓
 Working Hours Calculation
```

The CSV maintains information such as **User ID, User Name, Date, IN time, OUT time, Working Hours and IN/OUT status**.

---

## 🔌 Hardware

* LPC2148 ARM7 Development Board
* RFID Reader
* RFID Cards
* AT25LC512 SPI EEPROM
* 16×2 LCD
* 4×4 Keypad
* Switches
* MAX232
* USB-to-UART Converter

---

## 💻 Software

* Embedded C
* Linux C
* Keil C Compiler
* Flash Magic
* UART Communication
* CSV File Handling

---

## 📂 Project Structure

```text
Attendify--RFID-Smart-Employee-Tracking-Reporting-System/
│
├── README.md
│
├── Embedded/
│   ├── main.c
│   ├── admin.c
│   ├── admin.h
│   ├── lcd.c
│   ├── lcd.h
│   ├── kpm.c
│   ├── kpm.h
│   ├── rtc.c
│   ├── rtc.h
│   ├── rtc_edit.c
│   ├── uart.c
│   ├── uart1.c
│   ├── uart1.h
│   ├── SPI_Protocol.c
│   ├── SPI_defines.h
│   ├── SPI_functions.h
│   ├── interrupt.c
│   ├── interrupt.h
│   ├── delay.c
│   ├── delay.h
│   ├── pin_connect_block.c
│   ├── pin_connect_block.h
│   └── other header files
│
└── Linux/
    ├── linux_main.c
    └── employee_details.csv
```

---

## 🧩 Main Modules

| Module         | Function                           |
| -------------- | ---------------------------------- |
| RFID           | Employee identification            |
| LPC2148        | Main embedded controller           |
| SPI EEPROM     | Non-volatile data storage          |
| RTC            | Date and time                      |
| LCD            | Display                            |
| Keypad         | User/admin input                   |
| UART           | LPC2148 ↔ Linux communication      |
| Linux `main.c` | Employee and attendance processing |
| CSV            | Employee and attendance database   |

---

## 📊 CSV Record

The attendance information is maintained in a structured CSV format:

```text
S.No | User ID | User Name | Date | Working Hours | IN | OUT | IN/OUT Status
```

The system updates the corresponding employee's IN/OUT information whenever an RFID card is received.

---

## 🎯 Key Embedded Concepts

* Embedded C programming
* LPC2148 ARM7
* RFID interfacing
* SPI communication
* EEPROM interfacing
* UART communication
* RTC interfacing
* LCD interfacing
* Keypad interfacing
* Interrupt handling
* Linux C programming
* CSV file handling
* Working-hours calculation

---

## 👩‍💻 Author

**DeepthiSri Avula**

**Embedded Systems | Embedded C | ARM7 | SPI | UART**

---
