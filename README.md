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

## ⚙️ Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/aaditwadhwa/zeotap-assignment.git
cd ClickHouse-Flat-File-Data-Ingestion-Tool
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

### 🔗 Bonus: Multi-Table JOIN (ClickHouse)

1. Select **ClickHouse** as source  
2. Enable the **Multi-Table Join** option  
3. Select additional tables  
4. Enter JOIN condition (e.g., `table1.id = table2.fk_id`)  
5. Proceed with column selection and ingestion steps

---

## 🧪 Testing Scenarios

| Test Case | Description |
|-----------|-------------|
| ✅ TC1 | **ClickHouse ➜ Flat File** (with selected columns) |
| ✅ TC2 | **Flat File ➜ ClickHouse** (create new table) |
| ✅ TC3 | *(Bonus)* ClickHouse multi-table JOIN ➜ Flat File |
| ✅ TC4 | Invalid JWT / connection failure |
| ✅ TC5 | *(Optional)* Test preview before ingestion |

### Sample Datasets:

- `uk_price_paid`  
- `ontime`  
Get them from: https://clickhouse.com/docs/en/getting-started/example-datasets/

---

## ⚙️ Configuration

Edit `src/main/resources/application.properties` to update:

- Server port  
- Default settings  

---

## 📂 File Structure

```
├── src
│   ├── main
│   │   ├── java/... (Spring Boot backend)
│   │   ├── resources/templates/... (HTML)
├── pom.xml
├── README.md
└── prompts.txt (if AI tools were used)
```

---

## 🤖 AI Tooling

**AI tools were used for assistance during development.**  
All prompts used are recorded in `prompts.txt` and checked into the repository.

---


