# **Log Analyzer and Visualizer**

This project helps you **read**, **analyze**, and **visualize logs** from various formats like JSON, Base64, and text-based logs. It's designed to handle real-world messy logs and generate beautiful charts that make it easy to understand what’s happening in your logs.

---

## **What Does This Project Do?**

1. **Reads Logs**: Automatically extracts useful information like user actions, timestamps, and events.
2. **Handles Messy Logs**: Skips broken or invalid lines and logs them for review.
3. **Creates Visuals**: Turns your log data into:
   - Stacked bar charts (for errors, actions, etc.).
   - Line graphs (for numbers like quantities or prices).

---

## **Why Should You Use This?**

- You’re working with logs that are hard to understand just by looking at them.
- You want to create **simple charts** to see patterns over time.
- You don’t know how to deal with logs that are **messy or inconsistent**.

---


## **Technologies Used**

This project leverages the following technologies:

1. **Programming Language**:  
   - **Python**: The primary language for parsing, processing, and visualizing logs.

2. **Python Libraries**:  
   - **Pandas**: For data cleaning, manipulation, and tabular data handling.  
   - **Matplotlib**: For creating visualizations like bar charts and line graphs.

3. **Version Control**:  
   - **Git**: To manage the source code and track changes.  
   - **GitHub**: To host and share the project repository.

4. **Development Environment**:  
   - Works in **Jupyter Notebook**, **VS Code**, or any Python IDE.  
   - **Terminal/Command Prompt**: For running Git commands and executing scripts.

5. **Data Handling**:  
   - Handles structured (e.g., JSON) and semi-structured (e.g., Base64-encoded) data.  
   - Processes log files stored locally.

6. **Visualization Framework**:  
   - Uses **Matplotlib** to generate stacked bar charts and time-series plots.  

---

## **How to Get Started**

### **Step 1: Install Python**

First, make sure you have **Python 3.8 or higher** installed. You can download it from [python.org](https://www.python.org/downloads/).

### **Step 2: Install the Required Libraries**

Run this command in your terminal or command prompt to install the required tools:

```bash
pip install pandas matplotlib
```

### **Step 3: Clone the Project**

Download the project to your computer:

```bash
git clone https://github.com/<your-username>/log-analyzer.git
cd log-analyzer
```

### **Step 4: Add Your Log File**

Place your log file (e.g., `my-log.log`) into the `data/` folder in the project directory.

---

## **How to Use**

### **1. Parse Your Logs**

Run the code to process your logs and turn them into a clean table:

```python
from log_analyzer import parse_logs

log_file_path = 'data/my-log.log'
parsed_data = parse_logs(log_file_path)
print(parsed_data.head())
```

You’ll see a table that looks something like this:

| Final_Timestamp         | user     | event    | quantity | price  |  
|--------------------------|----------|----------|----------|--------|  
| 2024-11-18 10:37:33.994 | user_123 | purchase | 3        | 517.19 |  

---

### **2. Visualize Your Data**

Run the visualization function to generate charts:

```python
from log_analyzer import create_visualizations

create_visualizations(parsed_data)
```

You’ll get:
- **Bar Charts**: How many times each user performed an action or error occurred over time.
- **Line Charts**: Trends in numbers like quantities or prices over time.

---

## **Log Formats Supported**

This tool works with several types of logs:

1. **JSON Logs**:
   ```json
   {"user": "user_123", "timestamp": "2024-11-18T10:37:33.994", "event": "purchase", "details": {"quantity": 3, "price": 517.19}}
   ```

2. **Base64 Logs**:
   ```plaintext
   BASE64:eyJ1c2VyIjogInVzZXJfMTIzIiwgInRpbWVzdGFtcCI6ICIyMDI0LTExLTE4VDEwOjM3OjMzLjk5NDU0NyIsICJldmVudCI6ICJwdXJjaGFzZSIsICJkZXRhaWxzIjogeyJxdWFudGl0eSI6IDMsICJwcmljZSI6IDUxNy4xOX19
   ```

3. **Action-Based Logs**:
   ```plaintext
   user_123 performed purchase at 2024-11-18T10:37:33.994
   ```

4. **Error Logs**:
   ```plaintext
   TimeoutError: Connection to DB failed 2024-11-18T20:38:31.994
   ```

---

## **What If Something Goes Wrong?**

1. **Skipped Lines**:  
   If the logs are too messy to parse, the program will skip them and tell you how many were skipped.
   Example:
   ```plaintext
   Skipped lines due to parsing issues: 15 skipped lines.
   ```

2. **No Charts?**  
   Check if your logs contain valid timestamps or numeric data for charts. Otherwise, you might only see empty graphs.

3. **Need Help?**  
   Open an issue on the GitHub repository!

---

## **File Structure**

```
log-analyzer/
├── data/
│   └── sample.log      # Place your log files here
├── log_analyzer.py     # Main script for parsing and visualizations
├── README.md           # Documentation
```

---

## **Beginner Tips**

1. **New to Python?**  
   Follow a quick [Python tutorial](https://www.learnpython.org/) to understand basic programming concepts.

2. **Need to Learn Pandas?**  
   Pandas is the library used to handle tables. Check out the [Pandas Getting Started Guide](https://pandas.pydata.org/docs/getting_started/index.html).

3. **Learn Visualization**:  
   The charts are powered by Matplotlib. Explore [Matplotlib documentation](https://matplotlib.org/stable/contents.html) for more details.

---

## **Next Steps**

1. Customize the `parse_logs` function to handle your specific log format.
2. Add more visualizations if needed.
3. Share the project with your team or friends!

---

## **Contributing**

We love contributions! Here’s how you can help:
1. Fork the repository.
2. Add your improvements.
3. Submit a pull request.

---

## **License**

This project is licensed under the MIT License. See `LICENSE` for more details.

---

Enjoy analyzing your logs!
