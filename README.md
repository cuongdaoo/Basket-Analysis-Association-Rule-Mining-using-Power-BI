# Basket-Analysis-Association-Rule-Mining-using-Power-BI
# I. Market Basket Analysis is?
Market basket analysis (also called association analysis) is one of the most important methods used to uncover relationships between items. It looks for combinations of items that frequently occur together in transactions.
<div align="center">
  <img src="https://github.com/user-attachments/assets/b1ff599e-d3c7-429c-86e5-424452760b5e" alt="mô tả" width="600">
</div>

# II. Use cases
Store Layout Planning 
Product Recommendations 
Cross-Selling Strategies 
Pricing & Sales Strategies
# III. Key concepts
<div align="center">
  <img src="https://github.com/user-attachments/assets/dcd67ace-8989-4d2c-a4cb-2cfeefce3bf4" alt="mô tả" width="300">
</div>

1. **Support**:  
   - Measures how frequently an itemset appears in the dataset.  
   - Formula:
$$ \text{Support(A)} = \frac{\text{Number of transactions containing A}}{\text{Total number of transactions}} $$

   - Higher values mean the itemset is more frequent.

2. **Confidence**:  
   - Measures the reliability of an association rule. It’s the conditional probability that the consequent (B) occurs given that the antecedent (A) has occurred.  
   - Formula:  
     $$\text{Confidence(A → B)} = \frac{\text{Support(A ∪ B)}}{\text{Support(A)}} $$
   - Higher values indicate stronger rule reliability.

3. **Lift**:  
   - Measures the strength and significance of an association rule compared to when items are independent.  
   - Formula:  
     $$\text{Lift(A → B)} = \frac{\text{Confidence(A → B)}}{\text{Support(B)}}$$
   - **Interpretation**:
     - **Lift > 1**: Positive association (A promotes B).  
     - **Lift = 1**: No association (A and B are independent).  
     - **Lift < 1**: Negative association (A discourages B).

**Alternative formula for Lift**:  
$$\text{Lift(A → B)} = \frac{\text{Support(A ∪ B)}}{\text{Support(A)} \times \text{Support(B)}}$$
This compares joint occurrence to independent occurrence probabilities.
# IV. Building Process and Analyst
<div align="center">
  <img src="https://github.com/user-attachments/assets/3e66de8b-955f-447b-8bed-89cdc709c8e3" alt="mô tả" width="1000">
</div>

**Unpivot**
<div align="center">
  <img src="https://github.com/user-attachments/assets/82fe6b31-c16b-4544-9b35-759b9650bace" alt="mô tả" width="1000">
</div>

**Measure**
-  Total transactions = DISTINCTCOUNT(Groceries[TransactionID])
-  Product Count = DISTINCTCOUNT(Groceries[Products])

**Crossjoin**
![image](https://github.com/user-attachments/assets/a6626ad6-214e-408f-bc25-26d22acc105e)

- Cross table:
```
Basket Analyst = 
FILTER(
CROSSJOIN(
    SELECTCOLUMNS(VALUES(Groceries[Products]), "Product1", Groceries[Products]),
    SELECTCOLUMNS(VALUES(Groceries[Products]), "Product2", Groceries[Products])),
    [Product1]>[Product2])
```
- Support Basket:
```
Support Basket = 
var prod1='Basket Analyst'[Product1]
var prod2='Basket Analyst'[Product2]

var prod1Transaction= SELECTCOLUMNS(FILTER(Groceries,Groceries[Products]=prod1),"TransactionID", Groceries[TransactionID])
var prod2Transaction= SELECTCOLUMNS(FILTER(Groceries,Groceries[Products]=prod2),"TransactionID", Groceries[TransactionID])

var BothProdTransaction=INTERSECT(prod1Transaction,prod2Transaction)

RETURN

COUNTROWS(BothProdTransaction)/[Total transactions]
```
- Confidence:
```
Confidence of Prod1 = 

var prod1= 'Basket Analyst'[Product1]

var Supportprod1= COUNTROWS(FILTER(Groceries,Groceries[Products]=prod1))/[Total transactions]

RETURN
'Basket Analyst'[Support Basket]/Supportprod1
```
- Lift:
```
Lift = 
var prod1= 'Basket Analyst'[Product1]
var prod2= 'Basket Analyst'[Product2]

var SupProd1= COUNTROWS(FILTER(Groceries,Groceries[Products]=prod1))/ [Total transactions]
var SupProd2= COUNTROWS(FILTER(Groceries,Groceries[Products]=prod2))/ [Total transactions]

RETURN
'Basket Analyst'[Support Basket]/(SupProd1*SupProd2)
```




