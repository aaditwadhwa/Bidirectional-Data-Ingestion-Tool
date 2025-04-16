# 🚀 ClickHouse & Flat File Data Ingestion Tool

A **web-based data ingestion tool** enabling **bidirectional data transfer** between **ClickHouse** databases and **Flat Files (CSV)**. This tool provides an intuitive UI for seamless configuration, secure connection, column selection, and efficient data movement – all with **JWT token-based authentication**, **schema discovery**, **data preview**, and optional **multi-table JOIN** support.

---

## 🌟 Key Features

✅ **Bidirectional Data Flow**  
- **ClickHouse ➜ Flat File**  
- **Flat File ➜ ClickHouse**

✅ **Secure Authentication**  
- JWT token-based access for ClickHouse

✅ **Custom Column Selection**  
- Choose only relevant data columns for transfer

✅ **Schema Discovery**  
- Auto-detects schema from ClickHouse tables or CSV headers

✅ **Optional Enhancements**  
- Data Preview (First 100 records)  
- Multi-Table JOIN Support (ClickHouse)  
- Progress bar during ingestion

✅ **User Feedback**  
- Real-time status updates and final record count

---


## ⚙️ Setup Instructions

### 1. Clone the Repository

```bash
https://github.com/aaditwadhwa/Bidirectional-Data-Ingestion-Tool.git
```

### 2. Build the Project

```bash
mvn clean package
```

### 3. Run the Application

```bash
mvn spring-boot:run
```

### 4. Access the Web UI

Open your browser and go to:

```
http://localhost:8081
```

---

## 🧑‍💻 Usage Guide

### 🔁 ClickHouse ➜ Flat File

1. Select **ClickHouse** as source and **Flat File** as target  
2. Fill in ClickHouse connection details:
   - Host, Port, Database, User, JWT Token  
3. Test connection & load available tables  
4. Select table and load column list  
5. Configure target Flat File (file path, delimiter, etc.)  
6. Select columns to ingest  
7. *(Optional)* Preview first 100 rows  
8. Click **Start Ingestion**

---

### 🔄 Flat File ➜ ClickHouse

1. Select **Flat File** as source and **ClickHouse** as target  
2. Configure Flat File:
   - File path, delimiter, has header?  
3. Load file schema  
4. Enter ClickHouse connection details  
5. Specify destination table name  
6. Select columns to ingest  
7. *(Optional)* Preview first 100 rows  
8. Click **Start Ingestion**

---

## 🧰 Tech Stack

- **Backend**: Java, Spring Boot  
- **Frontend**: Thymeleaf, Bootstrap 5, jQuery  
- **Database**: ClickHouse (via JDBC)  
- **File I/O**: Apache Commons CSV

---

## 🛠️ Prerequisites

- Java 8+
- Maven 3.6+
- ClickHouse (local Docker or cloud-based instance)

---


