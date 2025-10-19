# 🌸 FNP Excel Sales Analytics (Excel + CSV)

## 📘 Executive Summary

**Scope:**  
- 1 Fact table (`Orders`)  
- 2 Dimension tables (`Products`, `Customers`)  
- 3 CSV files  
- 1 Excel Dashboard  

**KPIs (Filtered View):**  
- **Total Orders:** 126  
- **Total Revenue:** ₹586,176  
- **Average Delivery Days:** 5.72  
- **ARPO (Average Revenue Per Order):** ₹4,652  
> *All KPIs update dynamically with slicers and refresh.*

**Seasonal Drivers:**  
Holi, Diwali, Raksha Bandhan, and Valentine’s Day dominate both **order volume** and **revenue**.

---

## 📂 Files

| File Name | Description |
|------------|-------------|
| `fnp_final_project_excel.xlsx` | Excel model with data model, pivot tables, and dashboard |
| `orders.csv` | ~75k chars; includes OrderID, CustomerID, ProductID, Quantity, Order/Delivery Date & Time, Location, Occasion |
| `products.csv` | ~5.8k chars; includes ProductID, ProductName, Category, Price (INR), Occasion |
| `customers.csv` | ~10.7k chars; includes CustomerID, Name, City, Gender, Address |

---

## 🧩 Data Model

**Joins:**
- `Orders.CustomerID` → `Customers.CustomerID`
- `Orders.ProductID` → `Products.ProductID`

**Derived Fields (in Orders):**
- `PriceINR` → Lookup from Products  
- `Revenue` = `Quantity × PriceINR`  
- `DaysinDelivery` = `DeliveryDate − OrderDate`  
- `Hour`, `MonthName`, `OrderDay`, `DeliveryTime_Hour/Minute/Second`

---

## 📊 Key KPIs (Example)

| Metric | Value |
|--------|--------|
| Total Orders | 126 |
| Total Revenue | ₹586,176 |
| Avg Delivery Days | 5.72 |
| ARPO | ₹4,652 |
| Peak Occasions | Holi, Raksha Bandhan, Diwali, Valentines Day |

---

## 📈 Dashboard Usage

1. Open **`fnp_final_project_excel.xlsx`**
2. Enable content (macros/connections)
3. Click **Refresh All**
4. Navigate to the **Dashboard** sheet
5. Use **Slicers (Occasion, Month, City)** and **Timeline (OrderDate)** to filter and update KPIs/charts instantly

**Quick Checks:**
- Highest-revenue occasion this month  
- Slowest average delivery city  
- Top category for Holi  

---

## 🗂️ Minimal Data Dictionaries

### `orders.csv`
- Fields: IDs, quantities, date/time (HHMMSS), Location, Occasion  
- Basis for revenue and lead-time calculations  

### `products.csv`
- Fields: Price (INR), Category, Occasion  
- Used for pricing and category mix analysis  

### `customers.csv`
- Fields: City, Demographics  
- Supports geography-based pivots  

---

## ⚙️ Assumptions

- Revenue = **List Price (INR) × Quantity**  
- No taxes or discounts modeled  
- `DaysinDelivery` = Difference between Delivery and Order dates  
- Time of day parsed separately  

---

## 🔄 Refresh Steps

1. Keep CSV names and paths consistent (or update connections in Excel)  
2. Enable content → **Refresh All**  
3. Use **Slicers/Timeline** to explore — KPI numbers will auto-update  

---

🟢 *End of Summary*
