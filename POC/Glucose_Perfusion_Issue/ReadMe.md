# Glucose Monitoring Trend Analysis: Poor Perfusion Case Study

This repository contains an Excel-based case study focused on analyzing glucose values in a patient with known **poor perfusion**, a condition that can significantly affect point-of-care (POC) testing accuracy.

## 🧬 Study Objective

This project compares:
- **POC Glucose Values** — often prone to error in low-perfusion states
- **Main Lab Serum Glucose Values** — considered the **gold standard** in laboratory diagnostics

The study seeks to:
- Detect erroneous low glucose readings from POC devices
- Visualize trends across both testing methods
- Highlight instances of hypoglycemia (<70 mg/dL)
- Quantify measurement variability over time
- Establish a trendline to evaluate glucose behavior longitudinally

## 📁 Files Included

- `Patient Study Glucose.xlsx`: Contains the full dataset, trendline calculations, error bar data, and charting components.
- 'Poor Perfusion POC Glucose Study.jpeg': Depicts a scatterplot of data collected from POC Glucometers and Main Lab Chemistry analyzer

## 📊 Regression Trendline (Main Lab Values)

A linear regression was calculated based on the main lab glucose values (serum), to serve as a baseline.

**Equation of Trendline:**

y = m * x + b

m = -0.321441303
b = 14818.1577


- `x`: Excel serial date (e.g., `2/24/2025` = 45346)
- `y`: Predicted glucose value
- The **negative slope** reflects a gradual decrease in serum glucose levels over time.

## 📷 Visual Output

![Final Glucose Chart](https://github.com/khangsheng1/MT-Work/blob/main/POC/Glucose_Perfusion_Issue/Poor%20Perfusion%20POC%20Glucose%20Study.jpg)

## 🧠 Interpretation

The visualization clearly shows:
- **POC values are frequently inconsistent when compared to main lab readings**, especially in the presence of hypoperfusion.
- Multiple **false hypoglycemic readings** are observed from POC data.
- **Main Lab data offers a more reliable and stable trend**, making it crucial for clinical decision-making in similar patients.

## 🔍 Use Cases

- Quality assurance analysis in hospital POC programs
- Education on limitations of bedside testing
- Case review for patient safety events

---

⚠️ *This case study supports the importance of validating low POC glucose values with serum lab testing in patients with poor perfusion.*


