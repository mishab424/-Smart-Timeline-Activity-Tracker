# 🧭 Smart Timeline & Activity Tracker for Oracle APEX

The **Smart Timeline & Activity Tracker** is a lightweight and elegant **Oracle APEX Region Plugin** that displays an interactive, auto-grouped timeline of activities and events.  
It helps visualize activities in a chronological order — automatically partitioned by month — providing users with a clear, modern, and intuitive overview of actions or milestones.

---

## 🚀 Features

- 📅 **Automatic Monthly Partitioning** — Events are automatically grouped by month and year.  
- 🎨 **Modern UI Design** — Clean and responsive layout powered by custom CSS.  
- ⚡ **Font Awesome Icons Support** — Use any Font Awesome icon to represent an event visually.  
- 🧩 **Easy to Integrate** — No custom JavaScript required. Plug and play in Oracle APEX.  
- 🕒 **Dynamic Data Source** — Supports SQL queries with substitution tokens.  
- 💡 **Fully Customizable** — Easily change colors, icons, and layout with CSS.

---

## 📦 Installation Guide

### **Step 1 — Download Plugin File**
Download the plugin export file (`smart_timeline_activity_tracker.sql`) from this repository.

### **Step 2 — Import Plugin**
1. Go to your Oracle APEX **App Builder**.  
2. Open your desired application.  
3. Navigate to **Shared Components → Plugins → Import**.  
4. Upload the downloaded `.sql` file and install the plugin.

### **Step 3 — Create a Region**
1. Go to **Page Designer**.  
2. Create a new **Region**.  
3. Set **Region Type** to **Smart Timeline & Activity Tracker**.

### **Step 4 — Import CSS File**
1. Go to **Shared Components → Static Application Files**.  
2. Upload `timeline_style.css` (provided in the `/assets` folder).

### **Step 5 — Add SQL Source**
Use the following **sample SQL query** to generate your timeline:

```sql
SELECT 
    TO_CHAR(SYSDATE, 'DD-MON-YYYY') AS event_date,
    '<i class="fa-solid fa-flag"></i>' AS icon_html,
    'Hello' AS title,
    'This is a sample event description.' AS description
FROM dual
UNION ALL
SELECT 
    TO_CHAR(SYSDATE + 30, 'DD-MON-YYYY') AS event_date,
    '<i class="fa-solid fa-star"></i>' AS icon_html,
    'Next Month Event' AS title,
    'This is another timeline event.' AS description
FROM dual
-- ORDER BY event_date DESC
