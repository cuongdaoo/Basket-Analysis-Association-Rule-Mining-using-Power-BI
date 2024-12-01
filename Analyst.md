<div align="center">
  <img src="https://github.com/user-attachments/assets/0a632ee9-d078-4695-bc66-3e1b897a3d70" alt="mô tả" width="1000">
</div>

# 1. Overview
- Number of transactions: 7,835 transactions were analyzed.
- Number of items: 170 unique items were analyzed
  Main goal: Discover relationships between products (customer purchasing patterns) through association rule mining.

**Networking chart**
<div align="center">
  <img src="https://github.com/user-attachments/assets/7ae093cb-8ba1-40fa-a0b5-55fc8a9227aa" alt="mô tả" width="600">
</div>

The basket analysis network displays relationships between products based on:
- Frequency of co-occurrence in baskets.
- Support and Confidence values between products.

**Main/key products**:
- Yogurt (14.44), Root Vegetables (14.11), and Whipped/Sour Cream (13.68) are the three most popular products, as shown by their large size on the chart, meaning they appear with high frequency.
- These products are linked to many other product groups, indicating their importance in forming groups of related items in the shopping basket.

**Less common products**:
Like "Sliced ​​Cheese" and "Sausage" are smaller sized products that appear less frequently.

**Closely related product groups**:

- Yogurt is strongly related to Curd (7.37) and Whipped/Sour Cream.
- Root Vegetables are strongly related to Frozen Vegetables (6.84) and Herbs (6.18).

**Scatter plot**
<div align="center">
  <img src="https://github.com/user-attachments/assets/7ddce2a8-ff59-4c42-8f2f-206350bd98ae" alt="mô tả" width="800">
</div>

**Matrix**
<div align="center">
  <img src="https://github.com/user-attachments/assets/a21cdf2d-7f3d-4e41-910f-e41d9f978867" alt="mô tả" width="600">
</div>

# 2.Detailed analysis of product pairs
By combining **network diagrams**, **scatter plot** and **table data** for deeper analysis:


## **2.1. Product Pairs with Strong Influence**

Product Pairs with High **Lift (Lift > 3):**

- **Root Vegetables – Herbs (3.72):** Very strong relationship, high lift means that if one product is purchased, the probability of the other product being purchased is higher than usual.

- **Whipped/Sour Cream – Berries (3.56):** A popular combination of sour cream and berries, notable for display or cross-selling.

- **Frozen Vegetables – Chicken (3.31):** This combination habit reflects the convenience of customers with frozen products.

---
## **2.2. Product Pairs with High Support (Support > 1.5%)**

Product Pairs with Significant **Sum of Support**:

- **Root Vegetables – Other Vegetables (4.80%):** High proportion in the shopping cart, suggesting how to group vegetable items to optimize revenue.

- **Tropical Fruit – Citrus Fruit (2.00%)** and **Tropical Fruit – Pip Fruit (1.93%):** High popularity in the fruit product group.

Low Support Product Pairs with **High Lift (>3)**:

- **Whipped/Sour Cream – Berries (Support = 1.06%)**, although the support level is lower, it is a good cross-buy option.

---

## **2.3. Product Pairs to Focus on Growth**

Product Pairs with **low support (<1%) but good Lift (>2.5):**

- **Frozen Vegetables – Butter (0.64%; Lift = 2.4):** Show potential for growth with increased promotion.

- **Sliced ​​Cheese – Sausage (Support = 0.62%; Lift = 3.1):** Although low in presence, can be grouped for purchase growth strategies.

---

# **3. Combining Support & Lift Charts**

- **Support Map Chart (Basket Analysis Map):**

- **Root Vegetables – Other Vegetables:** Have the highest support rate (>4%) and average Lift (2.27), should continue to be positioned close together on the shelf.

- **Whipped/Sour Cream – Berries:** Has a high Lift (>3.5) and good support, a very promising product pair.

- **Frozen Vegetables – Chicken:** Stands out with a high Lift (>3.3), should focus on cross-buying in promotions.

# 4. Business Strategy Proposal

## 4.1. Focus on Revenue Growth:

- **Vegetables:**

- Ensure **Root Vegetables**, **Frozen Vegetables**, and other vegetables are displayed close together in the store due to high linkage and support rates.

- Create cross-sell suggestions between **Root Vegetables** and accompanying products such as **Herbs** & **Onions**.

- **Milk and Butter:**

- Create combo promotions or common areas for **Yogurt – Curd – Whipped/Sour Cream** to attract customers.

- Suggest adding **Cream Cheese** when customers choose **Yogurt**.

- **Frozen Products:**

- Save promotion for **Frozen Vegetables** group with proteins such as **Chicken** and **Butter** to increase Lift.

## 4.2. Developing small but potential groups:

- **Bers and Whipped/Sour Cream Group:** They have high Lift, but need to increase purchase rate through marketing suggesting dishes or combined recipes.
