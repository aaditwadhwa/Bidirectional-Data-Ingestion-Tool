# 🏗️ ClickHouse Setup Guide for ZeoTap Integration

This guide walks you through installing ClickHouse on windows and setting up a database for use with the ZeoTap Integration tool.

---

## 🔧 Step 1: Install ClickHouse

### ✅ Option A: Using Docker (Recommended)

1. **Install Docker** if not already installed  
   → [Download Docker](https://www.docker.com/products/docker-desktop)

2. **Open Terminal**

3. **Pull the ClickHouse image**

   ```bash
   docker pull clickhouse/clickhouse-server
   ```

4. **Run ClickHouse container**

   ```bash
   docker run -d --name clickhouse-server \
   -p 9000:9000 -p 8123:8123 \
   -e CLICKHOUSE_USER=default \
   -e CLICKHOUSE_PASSWORD=default \
   clickhouse/clickhouse-server
   ```

5. **Access ClickHouse Client**

   ```bash
   docker exec -it clickhouse-server \
   clickhouse-client --user default --password default
   ```

   If successful, you’ll see something like:

   ```
   ClickHouse client version 23.x.x.x
   Connecting to localhost:9000 as user default.
   Connected to ClickHouse server version 23.x.x.

   localhost :) 
   ```

   Type `exit` to leave the client.

---

### 🛠️ Option B: Manual Installation (Without Docker)

1. Visit the official site: [ClickHouse Installation Guide](https://clickhouse.com/docs/en/install)  
2. Follow the Windows installation instructions

---

## 🗃️ Step 2: Create a Database

1. **Login to ClickHouse (via Docker or installed client)**

2. **Create a new database** (example: `zeotap`)

   ```sql
   CREATE DATABASE zeotap;
   ```

3. **Verify the database**

   ```sql
   SHOW DATABASES;
   ```

4. **Switch to your new database**

   ```sql
   USE zeotap;
   ```

---

## ⚙️ Step 3: Configure ZeoTap Integration Tool

1. Start the integration tool and open in your browser:  
   [http://localhost:5000](http://localhost:5000)

2. Use the following settings when configuring ClickHouse:

   - **Host**: `localhost`  
   - **Port**: `8123` (HTTP interface)  
   - **Database**: `zeotap`  
   - **User**: `default`  
   - **JWT Token**: *(leave empty unless required)*  
   - **Secure**: `No` (unless HTTPS is configured)

3. Click **"Test Connection"** to validate your settings.

---

## 🧱 Step 4: (Optional) Create a Table

If you're not letting the tool auto-create tables during ingestion, you can create one manually:

1. **Access the ClickHouse client**

2. **Run the following SQL**

   ```sql
   CREATE TABLE example_table (
     id UInt32,
     name String,
     value Float64,
     created_date Date
   ) ENGINE = MergeTree()
   ORDER BY id;
   ```

3. **Verify your table exists**

   ```sql
   SHOW TABLES;
   ```

---

## 🔄 Step 5: Using the ZeoTap Integration Tool

### 📥 Import Data (Flat File ➜ ClickHouse)

1. Select **"Flat File"** as Source and **"ClickHouse"** as Target  
2. Configure CSV settings: file path, delimiter, header  
3. Enter ClickHouse connection info (from Step 3)  
4. Enter a target table name (existing or new)  
5. Select desired columns  
6. Click **"Start Ingestion"**

---

### 📤 Export Data (ClickHouse ➜ Flat File)

1. Select **"ClickHouse"** as Source and **"Flat File"** as Target  
2. Configure ClickHouse connection (from Step 3)  
3. Select source table and columns  
4. Configure output CSV file (file path, delimiter)  
5. Click **"Start Ingestion"**

---

## 📚 Additional Resources

- 📘 [ClickHouse Documentation](https://clickhouse.com/docs/)
- 📘 [ClickHouse SQL Reference](https://clickhouse.com/docs/en/sql-reference/)
- 📂 [Example Datasets](https://clickhouse.com/docs/getting-started/example-datasets)
