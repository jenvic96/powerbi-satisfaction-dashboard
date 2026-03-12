# 📊 Análisis de Satisfacción y Comportamiento de Compra

![Dashboard Preview](powerbidashboard.png)

---

## 📋 Project Overview

This Power BI dashboard analyzes customer satisfaction and purchasing behavior data from a **local electronics store** in Costa Rica. The store conducted a customer survey to better understand their clientele and improve their marketing strategy and customer service.

---

## 🎯 Business Questions Answered

- What is the overall satisfaction level of customers?
- What is the gender distribution of the customer base?
- How does purchase frequency vary by age?
- Which product categories are most popular among customers?

---

## 📈 Key Insights

- 🟠 **Most customers are satisfied** : the majority rated their experience 4 or 5 out of 5
- 👥 **50/50 gender split** : equal distribution between male and female customers
- 🛍️ **Electrónica is the top category** : 37.50% of customers prefer electronics, followed by Entretenimiento and Hogar at 31.25% each
- 📊 **Purchase frequency varies by age** : customers in their mid-to-late 30s show the highest purchase frequency

---

## 🔍 Deep Dive Analysis

### Overall Satisfaction
- Average satisfaction score: **3.38 / 5** : room for improvement!
- The store may believe customers are happy, but the data suggests otherwise

### Satisfaction by Product Category
| Category | Avg Satisfaction |
|----------|-----------------|
| 🎮 Entretenimiento | 3.60 ⭐ highest |
| 🏠 Hogar | 3.40 |
| 💻 Electrónica | 3.17 ⚠️ lowest |

> Despite being the most popular category, Electronics has the **lowest satisfaction** : high-income customers may expect more from the store's electronics offering.

### Income vs Satisfaction
| Category | Avg Monthly Income |
|----------|-------------------|
| 🏠 Hogar | $4,300 |
| 💻 Electrónica | $4,250 |
| 🎮 Entretenimiento | $3,620 |

> Electronics and Home customers have **higher incomes** but lower satisfaction : a key opportunity for the store to improve quality and service in these categories.

### Satisfaction by Gender
| Gender | Avg Satisfaction |
|--------|-----------------|
| 👩 Femenino | 3.50 |
| 👨 Masculino | 3.25 |

> Female customers are slightly more satisfied : the store could investigate what's driving lower satisfaction among male customers.

### Payment Method Preferences
| Method | Count |
|--------|-------|
| 💳 Tarjeta | 6 (37.5%) |
| 💵 Efectivo | 5 (31.25%) |
| 🌐 Online | 5 (31.25%) |

> Card payment is most popular : the store should ensure a smooth card payment experience and could offer card-based loyalty rewards.

### 💼 Business Recommendations
1. **Improve electronics service** : highest revenue category but lowest satisfaction
2. **Offer card payment incentives** : most popular payment method
3. **Target high-income customers** : electronics and home buyers earn more and expect premium service
4. **Investigate male satisfaction** : slightly lower than female, worth exploring why

---

## 🗂️ Dataset

**File:** `BD_Encuesta_Satisfacción.csv`

| Column | Description |
|--------|-------------|
| Cliente | Anonymous customer ID |
| Edad | Customer age |
| Género | Customer gender (M/F) |
| Satisfacción (1-5) | Satisfaction score 1-5 |
| Frecuencia de Compra (mensual) | Monthly purchase frequency |
| Ingreso Mensual (USD) | Monthly income in USD |
| Tipo de Producto Favorito | Favorite product category |
| Método de Pago Preferido | Preferred payment method |

- **Rows:** 16 customers
- **Source:** Customer satisfaction survey : local electronics store

---

## 📊 Dashboard Features

| Visual | Description |
|--------|-------------|
| 📊 Bar Chart | Customer satisfaction levels (1-5) |
| 🥧 Pie Chart | Customer proportion by gender |
| 📈 Line Chart | Purchase frequency evolution by age |
| 📊 Stacked Bar | Favorite product category distribution |
| 🎛️ Slicers | Filter by Satisfacción, Género, Edad, Producto Favorito |

---

## 🔄 ETL Process

Data was cleaned and transformed in **Power Query** before loading into the dashboard.

**1. Changed column data types to Whole Number:**
```powerquery
= Table.TransformColumnTypes(Source, {
    {"Edad", Int64.Type},
    {"Satisfacción (1-5)", Int64.Type},
    {"Frecuencia de Compra (mensual)", Int64.Type}
})
```

**2. Conditional Column added to expand gender codes:**
```powerquery
= Table.AddColumn(#"Changed Type", "Genero Completo", each if [Género] = "F" then "Femenino" else "Masculino")
```

This transformed the raw `M/F` values into full Spanish labels (`Masculino/Femenino`) for cleaner dashboard visuals.

---



![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Excel](https://img.shields.io/badge/Excel-217346?style=for-the-badge&logo=microsoftexcel&logoColor=white)
![Power Query](https://img.shields.io/badge/Power%20Query-217346?style=for-the-badge&logo=microsoft&logoColor=white)

- **Power BI Desktop** : dashboard development
- **Power Query** : data cleaning and transformation
- **Conditional Column** : created full gender names (Masculino/Femenino)

---

## 📁 Files

| File | Description |
|------|-------------|
| `Lab_3_Jennifer_Arriola.pbix` | Power BI dashboard file |
| `BD_Encuesta_Satisfacción.csv` | Raw dataset |
| `powerbidashboard.png` | Dashboard preview |

---

## 👩‍💻 Author

**Jennifer Victoria Arriola Salazar**
- 🎓 Technical Certificate in Data Analytics : Universidad Cenfotec
- 💼 [LinkedIn](https://www.linkedin.com/in/jennifervictoriaarriolasalazar/)
- 🐙 [GitHub](https://github.com/jenvic96)
