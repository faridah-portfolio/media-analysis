# 📊 Social Media Engagement Analytics Dashboard

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-0078D4?style=for-the-badge&logo=microsoft&logoColor=white)
![Excel](https://img.shields.io/badge/Excel-217346?style=for-the-badge&logo=microsoftexcel&logoColor=white)

## 📌 Project Overview
An interactive Power BI dashboard analyzing **2,000 synthetic social media posts** 
across multiple categories, post types, and user behaviors. 
The goal was to uncover what drives engagement on social media platforms 
and present findings in a clean, interactive visual report.

---

## 🖼️ Dashboard Preview
![Dashboard Preview](https://github.com/faridah-portfolio/media-analysis/blob/1491d40c5c148c9a41c483088c61083786c1122d/Power%20BI%20Desktop%206_26_2026%209_16_59%20PM.png)

---

## 📂 Dataset Description
| Column | Description |
|---|---|
| `user_id` | Unique user identifier |
| `post_type` | Type of post — video, image, text |
| `post_length` | Length of the post in characters |
| `likes` | Number of likes on the post |
| `comments` | Number of comments on the post |
| `shares` | Number of shares on the post |
| `engagement_rate` | Percentage engagement metric |
| `user_followers` | Number of followers the user has |
| `post_category` | Category — fashion, sports, food, technology |
| `post_hour` | Hour of the day the post was published |
| `is_weekend` | 0 = Weekday, 1 = Weekend |
| `user_verified` | 0 = Not Verified, 1 = Verified |
| `spam_flag` | 0 = Legitimate, 1 = Spam |

---

## 🧹 Data Cleaning Steps
- Removed **100 rows** with missing `post_length` and `engagement_rate` values
- Verified no duplicate records existed
- Corrected data types for all columns in **Power Query**
- Applied **spam filter** to exclude flagged posts from all visuals

---

## ⚙️ DAX Calculated Columns
```DAX
-- Total Engagement
Total Engagement = mediarates[likes] + mediarates[comments] + mediarates[shares]

-- Time of Day
Time of Day = 
IF(mediarates[post_hour] >= 5 && mediarates[post_hour] < 12, "Morning",
IF(mediarates[post_hour] >= 12 && mediarates[post_hour] < 18, "Afternoon",
IF(mediarates[post_hour] >= 18 && mediarates[post_hour] < 22, "Evening", "Night")))

-- Day Type
Day Type = IF(mediarates[is_weekend] = 1, "Weekend", "Weekday")

-- Verified Label
Verified Label = IF(mediarates[user_verified] = 1, "Verified", "Not Verified")
```

---

## 📊 Dashboard Features
- ✅ **4 KPI Cards** — Total Likes, Total Posts, Avg Engagement Rate, Spam Count
- ✅ **Donut Chart** — Post Type Distribution
- ✅ **Bar Chart** — Engagement Rate by Category
- ✅ **Clustered Bar Chart** — Likes, Comments & Shares by Post Type
- ✅ **Line Chart** — Engagement Rate by Hour of Day
- ✅ **Stacked Bar Chart** — Weekend vs Weekday by Verified Status
- ✅ **Bar Chart** — Engagement by Time of Day
- ✅ **4 Interactive Slicers** — post_type, post_category, Day Type, Verified Label
- ✅ **Spam Filter** applied across all pages

---

## 💡 Key Insights
- 📌 **Image posts** drive the highest average likes compared to video and text
- 📌 **Night-time posts** outperform all other time slots in engagement
- 📌 All **4 categories** perform at similar engagement rates
- 📌 **Verified vs Non-verified** users show minimal engagement difference
- 📌 **Weekend vs Weekday** posting has little impact on engagement rate

---

## 🛠️ Tools Used
- **Power BI Desktop** — Dashboard design and visualization
- **Power Query** — Data cleaning and transformation
- **DAX** — Calculated columns and measures
- **Microsoft Excel** — Initial data exploration

---

## 📁 Files in This Repository
