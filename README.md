# 📊 Adidas Interactive Sales Dashboard (Arab Region)

![Adidas Sales Dashboard](Adidas%20Sales%20DashBoard.jpg)
---
Adidas Sales Dashboard Overview
<img width="1650" height="1275" alt="Adidas Sales DashBoard" src="https://github.com/user-attachments/assets/b47a3129-95a2-4a16-86e2-7c7c7d477152" />

---

## 📝 Overview / نظرة عامة
هذا المشروع يقدم لوحة تحكم تفاعلية (Interactive Dashboard) وتحليلاً شاملاً لمبيعات وأرباح شركة **Adidas** في خمس دول عربية (**مصر، السعودية، العراق، لبنان، وعمان**)، وذلك باستخدام **Pivot Tables**, **Pivot Charts**, **Map Charts**, و **Slicers** لتسهيل واستدعاء البيانات بسرعة ودقة.

This repository features an interactive sales performance dashboard for **Adidas** across 5 Arab countries (**Egypt, Saudi Arabia, Iraq, Lebanon, and Oman**), focusing on revenue, profit margins, distribution channels, and regional market share.

---

## 🎯 أهم مكونات وتحليلات لوحة التحكم (Key Features)

1. **مؤشرات الأداء الرئيسية (KPIs Cards):**
   - **إجمالي الوحدات المباعة (Units Sold):** 3,550 قطعة.
   - **إجمالي المبيعات (Total Sales):** $287,378.
   - **إجمالي الأرباح (Profit):** $85,070.
   - **عدد المتاجر / الموزعين (Retailers):** 1,200.

2. **الجداول والرسوم البيانية المحورية (Pivot Tables & Charts):**
   - **Product Per Profit (مخطط عمودي):** يوضح ترتيب منتجات الشركة حسب مساهمتها في الربحية (الأحذية الرجالية/النسائية، الملابس، والإكسسوارات).
   - **Sales Per Store Type (مخطط دائري Donut):** يوضح نسبة مساهمة أنواع المتاجر (*Online: 46%*, *Retail: 36%*, *Outlet: 12%*, *Wholesale: 6%*).
   - **Retailers Sales (مخطط أفقي):** مقارنة حجم المبيعات الإجمالي بين طرق وقنوات البيع المختلفة.
   - **Sales Trend By Year (مخطط خطي):** تتبع مسار وتطور المبيعات عبر الأرباع السنوية للأعوام (2023 - 2025).

3. **الخريطة التفاعلية (Map Chart):**
   - توضيح حجم المبيعات والفروقات التنافسية بين الدول العربية المحددة (**مصر، العراق، عمان، السعودية، لبنان**) ونسبة استحواذ كل دولة على المبيعات.

4. **شرائح التصفية التفاعلية (Slicers):**
   - إضافة Slicer مخصص للـ **Region / Country** لتصفية البيانات فوراً بمجرد الضغط على اسم الدولة.

---

## 💻 كود بايثون لتوليد ملف الإكسيل تلقائياً (Python Automation Code)

يمكنك استخدام كود البايثون التالي لبناء وتجهيز البيانات والجداول بنفس الهيكلية المعتمدة في اللوحة:

```python
import openpyxl
from openpyxl.styles import Font, PatternFill, Alignment, Border, Side
from openpyxl.utils import get_column_letter
import pandas as pd
import numpy as np

# 1. إعداد بيانات محاكاة مطابقة للوحة التحكم
np.random.seed(42)
n_rows = 1200

countries = ['Egypt', 'Saudi Arabia', 'Iraq', 'Lebanon', 'Oman']
country_weights = [0.30, 0.12, 0.28, 0.06, 0.24]

products = [
    "Men's Footwear", "Women's Footwear", "Men's Apparel", "Women's Apparel",
    "Men's Accessories", "Women's Accessories", "Other Footwear", "Other Apparel", "Other Accessories"
]
prod_weights = [0.35, 0.26, 0.14, 0.11, 0.06, 0.05, 0.015, 0.01, 0.005]

channels = ['Online', 'Retail', 'Outlet', 'Wholesale']
channel_weights = [0.46, 0.36, 0.12, 0.06]

years = [2023, 2024, 2025]
quarters = ['Qtr1', 'Qtr2', 'Qtr3', 'Qtr4']

data = []
for i in range(n_rows):
    c = np.random.choice(countries, p=country_weights)
    p = np.random.choice(products, p=prod_weights)
    ch = np.random.choice(channels, p=channel_weights)
    y = np.random.choice(years, p=[0.3, 0.4, 0.3])
    q = np.random.choice(quarters)
    units = np.random.randint(1, 6)
    
    price = np.random.uniform(80, 150) if "Footwear" in p else np.random.uniform(30, 90)
    margin = 0.30
    sales = units * price
    profit = sales * margin
    
    data.append([f"ORD-{10000+i}", y, q, f"{y}-{q}", c, ch, p, units, round(sales, 2), round(profit, 2)])

df = pd.DataFrame(data, columns=['Order ID', 'Year', 'Quarter', 'Period', 'Country', 'Sales Channel', 'Product Category', 'Units Sold', 'Total Sales ($)', 'Profit ($)'])

# 2. التصدير إلى ملف إكسيل
df.to_excel("Adidas_Sales_Analysis.xlsx", index=False, sheet_name="Raw Data")
print("تم إنشاء ملف البيانات بنجاح!")
