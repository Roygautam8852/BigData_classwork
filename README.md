# Hadoop WordCount Project

## 📌 Project Overview

This project demonstrates how to perform word count using Hadoop MapReduce.
A text file is stored in HDFS and processed using the WordCount program to count the frequency of each word.

---

## 🛠️ Technologies Used

* Hadoop (HDFS + YARN)
* MapReduce
* Java (Hadoop Examples JAR)
* Windows + winutils

---

## 📁 Project Structure

```
HDFS Directory:
/user/gauta/My_folder/
    ├── mapreduce.txt   (input file)
    └── output/
         ├── part-r-00000  (result)
         └── _SUCCESS
```

---

## 🚀 Steps Performed

### 1️⃣ Start Hadoop Services

```
start-dfs.cmd
start-yarn.cmd
```

---

### 2️⃣ Create Directory in HDFS

```
hdfs dfs -mkdir -p /user/gauta/My_folder
```

---

### 3️⃣ Upload File to HDFS

```
hdfs dfs -put "C:\Users\gauta\OneDrive\Documents\Desktop\mapreduce.txt" /user/gauta/My_folder/
```

---

### 4️⃣ Verify File

```
hdfs dfs -ls /user/gauta/My_folder/
```

---

### 5️⃣ Run WordCount Program

```
hadoop jar "C:\hadoop\share\hadoop\mapreduce\hadoop-mapreduce-examples-3.3.6.jar" wordcount /user/gauta/My_folder/mapreduce.txt /user/gauta/My_folder/output
```

---

### 6️⃣ View Output

```
hdfs dfs -cat /user/gauta/My_folder/output/part-r-00000
```

---

## 📊 Sample Output

```
hello 3
hadoop 2
mapreduce 1
```

---

## 🧠 How It Works

* **Map Phase**: Splits text into words
* **Shuffle Phase**: Groups similar words
* **Reduce Phase**: Counts occurrences
* **Output**: Stores result in HDFS

---

## ⚠️ Important Notes

* NodeManager must be running for MapReduce jobs
* Output directory must not exist before running the job
* Always use HDFS paths (`/user/...`) instead of Windows paths

---

## 🎯 Conclusion

This project successfully demonstrates the working of Hadoop HDFS and MapReduce by performing word count on a text file.

---

## 👨‍💻 Author

Gautam Kumar
