# Excel Script: Glucose Data Sorting and Highlighting

This project contains an **Excel Office Script** I wrote to automate cleaning and organizing glucose testing data. It was built to streamline reviewing patient point-of-care (POC) results by hiding irrelevant columns, sorting samples, grouping patients visually, and flagging low glucose values (<70 mg/dL) for quick review.

---

## 🔧 What the Script Does

This script runs directly in **Excel on the web (Office Scripts)** and automates the following steps:

1. **Identify Key Columns**  
   Dynamically detects the "Date/Time," "Sample ID," and "Glucose" columns so it works on any file with the same header structure.

2. **Hide Unnecessary Columns**  
   Removes clutter by hiding columns that aren't relevant (only keeps essentials like Date/Time, Sample ID, Glucose, Location, Operator names, Status, Flow Error, and Sample Type).

3. **Sort and Group Data**  
   Sorts results by **Sample ID (ascending)** and then by **Date/Time (descending)**, grouping each patient's results together in reverse chronological order.

4. **Visual Grouping with Colors**  
   Alternates font color (green) for every other patient group to make it easier to see where one patient ends and another begins.

5. **Flag Low Glucose Values**  
   Adds a `<70?` column to quickly mark any result below 70 mg/dL. Rows with low values are highlighted red for visibility.

---

## 🖥️ Example Use Case

This script is designed for **POC glucose result audits**, but it could be adapted for any lab data with similar structure.  
It's especially useful for:
- Reviewing batches of patient data quickly  
- Identifying hypoglycemic values at a glance  
- Organizing messy export files into something readable for compliance or QA checks  

---

## 🚀 How to Use

1. Open Excel for the Web and upload your data file (must contain headers like *Date/Time*, *Sample ID*, and *Glucose*).
2. Go to **Automate** > **New Script**, paste this code, and save it.
3. Run the script — it will:
   - Hide unused columns
   - Sort and group data
   - Flag glucose <70 mg/dL

---

## 📌 Why I Built This

In Point of Care (POC), we often export large data files from glucometers that are messy and hard to read. This script was my way of automating what I used to do manually: sorting patients, scanning for low values, and filtering out noise. It’s a simple but effective tool for anyone in a lab or QA role working with POC glucose data.

---

## ⚠️ Disclaimer

This script does **not** contain or process any patient-identifiable information (PHI).  
It was developed for **educational and workflow improvement purposes** in a healthcare quality context.

---


