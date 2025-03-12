# OCD Patient Dataset: Demographics & Clinical Data Analysis

## 📌 Project Overview
This project analyzes the demographics, clinical data, and treatment insights of OCD (Obsessive-Compulsive Disorder) patients. The dataset includes key attributes such as age, gender, symptom severity, obsession and compulsion types, co-occurring mental health conditions, and prescribed medications.

Through statistical analysis and visualization, we uncover trends in OCD symptom duration, severity, and common treatment strategies, providing valuable insights for mental health research and clinical applications.

---

## 🚀 Technologies Used
- **Python**: Data manipulation, analysis, and visualization
- **Pandas & NumPy**: Data processing and calculations
- **Matplotlib & Seaborn**: Data visualization
- **Jupyter Notebook**: Code execution and analysis

---

## 📂 Dataset Overview
The dataset contains various attributes related to OCD patients, including:
- **Demographics**: Age, gender, ethnicity, marital status, education
- **Clinical Insights**: Symptom duration, obsession and compulsion types, severity (Y-BOCS scores)
- **Co-occurring Conditions**: Depression and anxiety prevalence
- **Treatment Data**: Medications prescribed and their effectiveness

---

## 📊 Project Code & Analysis

### 1️⃣ **Average Duration of OCD Symptoms**
```python
# Convert symptom duration from months to years
data1['ocd_duration_years'] = data1['symptom_duration_months'] / 12
avg_duration = data1['ocd_duration_years'].mean()
print(f"Average duration of OCD symptoms: {avg_duration:.2f} years")
```
**Result:** The average duration of OCD symptoms is **10.15 years**, highlighting the chronic nature of the disorder and the need for early intervention.

### 2️⃣ **Most Common Obsession & Compulsion Types**
```python
# Visualization of obsession and compulsion types
fig, axes = plt.subplots(1, 2, figsize=(12, 5))

sns.countplot(x='obsession_type', data=data1, palette="coolwarm", ax=axes[0])
axes[0].set_title("Most Common Obsession Types")
axes[0].set_xticklabels(axes[0].get_xticklabels(), rotation=45)

sns.countplot(x='compulsion_type', data=data1, palette="viridis", ax=axes[1])
axes[1].set_title("Most Common Compulsion Types")
axes[1].set_xticklabels(axes[1].get_xticklabels(), rotation=45)

plt.tight_layout()
plt.show()
```
**Key Findings:**
- The most common obsession types are **contamination** and **symmetry**.
- The most frequent compulsion types are **checking** and **cleaning**.

### 3️⃣ **Severity of OCD Symptoms (Y-BOCS Scores)**
```python
# Calculate the average Y-BOCS score
avg_ybocs = data['ybocs_total_score'].mean()
print(f"Average Y-BOCS score: {avg_ybocs:.2f}")
```
**Result:** The average Y-BOCS score indicates a **moderate to severe level of OCD symptoms**.

### 4️⃣ **Family History of OCD**
```python
# Calculate percentage of patients with a family history of OCD
family_history_counts = data['family_history_ocd'].value_counts(normalize=True) * 100
print(f"Percentage of patients with a family history of OCD: {family_history_counts[1]:.2f}%")
```
**Result:** **49.33%** of patients have a family history of OCD, suggesting a genetic component to the disorder.

### 5️⃣ **Mental Health & Co-occurring Conditions**
```python
# Count patients with depression and/or anxiety
depression_count = data['depression_diagnosis'].sum()
anxiety_count = data['anxiety_diagnosis'].sum()
both_conditions_count = data[(data['depression_diagnosis'] == 1) & (data['anxiety_diagnosis'] == 1)].shape[0]
```
**Key Findings:**
- **2272 patients** have been diagnosed with depression alongside OCD.
- **2251 patients** have anxiety in addition to OCD symptoms.
- **349 patients** suffer from both depression and anxiety, indicating a high degree of comorbidity.

### 6️⃣ **Correlation Between OCD Severity & Co-occurring Conditions**
```python
# Calculate correlation between OCD severity and co-occurring conditions
correlation_depression = data1[['Symptom_Severity', 'depression_diagnosis']].corr().iloc[0,1]
correlation_anxiety = data1[['Symptom_Severity', 'anxiety_diagnosis']].corr().iloc[0,1]
```
**Results:**
- No strong correlation was found between **OCD severity and depression**.
- A weak negative correlation (**-0.01**) was found between **OCD severity and anxiety**, suggesting no significant relationship.

### 7️⃣ **Most Prescribed Medications for OCD**
```python
# Count and visualize the most prescribed medications
medication_counts = data1['medications'].value_counts()
print(medication_counts.head())
```
**Top 5 Medications:**
- **Benzodiazepine** - 386 patients
- **No Medication** - 386 patients
- **SNRI (Serotonin-Norepinephrine Reuptake Inhibitor)** - 376 patients
- **SSRI (Selective Serotonin Reuptake Inhibitor)** - 352 patients

### 8️⃣ **Medication Type vs. Symptom Severity**
```python
# Checking correlation between medications and symptom severity
correlation = data[['medications', 'Symptom_Severity']].corr()
```
**Result:** No strong correlation was found between medication type and symptom severity.

---

## 📌 Key Findings & Conclusion
### ✅ **Demographics & Prevalence**
- Individuals aged **25-34 years** have the highest OCD prevalence.
- **Females** are slightly more affected than males.
- **Caucasians (26.53%)** and **Hispanics (26.13%)** have the highest prevalence.
- Most patients are **married** and have a **college degree or higher**.

### ✅ **OCD Symptoms & Severity**
- The **average duration** of OCD symptoms is **10.15 years**.
- **Contamination & symmetry obsessions** are the most common.
- **Checking & cleaning compulsions** are the most frequent.
- The **average Y-BOCS score** indicates **moderate to severe symptoms**.

### ✅ **Co-occurring Mental Health Conditions**
- High prevalence of **depression (2272 patients)** and **anxiety (2251 patients)**.
- **349 patients** suffer from both depression and anxiety.
- No strong correlation was found between **OCD severity and co-occurring conditions**.

### ✅ **Treatment Insights**
- **Benzodiazepines, SNRIs, and SSRIs** are the most commonly prescribed medications.
- No strong relationship was found between **medication type and symptom severity**.

---

## 📌 Final Thoughts
This project provides a **detailed analysis of OCD patient data**, helping mental health professionals **better understand the disorder, treatment patterns, and co-occurring conditions**.

### 📢 **Future Research**
- Study the **long-term effectiveness of different treatments**.
- Investigate **genetic factors** influencing OCD.
- Explore **personalized therapy approaches** to improve patient outcomes.

📌 **This project is open-source and contributions are welcome!**

---

## 📌 Author
**Aniket Surwade**

