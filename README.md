# Recommendation System Using PySpark

## Project Overview
A scalable **Recommendation System** for the **Google Merchandise Store**, built using **PySpark MLlib**. It predicts items users are likely to interact with (`add_to_cart`, `begin_checkout`, `purchase`) using collaborative filtering.

---

## Technologies
- **PySpark** (MLlib, DataFrame API)
- **BigQuery Dataset**: Google Merchandise Store (3 months of data)

---

## Dataset
- **items**: Item details (`id`, `name`, `category`, `price_in_usd`)
- **events**: User interactions (`user_id`, `type`, `item_id`, `date`)
- **users**: User metadata (`id`, `ltv`, `date`)

---

## Workflow
1. **Data Preparation**:
   - Encode `user_id` and `item_id` using **StringIndexer**.
   - Map `type` to numerical `event_type` (1: `add_to_cart`, 2: `begin_checkout`, 3: `purchase`).

2. **Model Training**:
   - Train an **ALS model** with `user`, `item`, and `event_type`.
   - Evaluate using **RMSE** ( Best model with a score of 0.2000 ) 

3. **Recommendations**:
   - Generate top-N item recommendations for each user.
   - Decode item IDs to display names.
