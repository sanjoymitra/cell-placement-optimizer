# AWS Cell Placement Optimizer

A lightweight, browser-based tool for planning AWS global infrastructure deployments. The Cell Placement Optimizer helps you determine exactly where to deploy your infrastructure ("cells") around the world to ensure your customers get fast, reliable connections while minimizing your monthly OPEX.

## 🚀 Features

* **Current Footprint Mapping**: Easily define your existing AWS cell locations using a map or list view.
* **Customer Location Mapping**: Add target customers by selecting AWS Regions or snapping to major World Cities on the map.
* **Infrastructure Cost Estimator**: Estimate monthly OPEX with a built-in AWS Regional Price Index (anchored to US East). Supports blended or specific cell baselines.
* **Advanced Latency Estimation**:
    * **Naive Mode**: Uses a simplified proxy approach (AWS Backbone latency).
    * **Realistic Mode**: Introduces a hybrid distance model using direct Haversine fiber distance (0.012 ms/km) plus a tier-based last-mile infrastructure tax.
* **Coverage Analysis & Dashboard**: 
    * **Cost-Effective Algorithm**: Iteratively calculates the cheapest combination of new AWS regions required to get 100% of your uncovered customers into a "Pass" state for your strict SLA.
    * **Latency Explorer**: Debug and explore the top candidate cells for each uncovered customer, including latency breakdowns (Base + Distance + Infra Tax).

## 🛠️ Tech Stack

This project is built as a **single-file web application** for maximum portability and ease of use. It requires no build steps, bundlers, or server-side backend.

* **HTML5 / Vanilla JavaScript**
* **Tailwind CSS** (via CDN for styling)
* **Leaflet.js** (via CDN for interactive maps)
* **FontAwesome** (via CDN for icons)

## 💻 Usage

Getting started is incredibly simple:

1. Clone or download this repository.
2. Open the `Cell_optmizer.html` (or `index.html` if renamed) file directly in any modern web browser.
3. Follow the 4-step wizard to map your footprint, add customers, define your SLA, and generate your deployment analysis.

## 🧠 How It Works (Under the Hood)

### Latency Models
* **AWS to AWS**: Uses a hardcoded 32x32 ping matrix representing the true latency of the AWS global backbone.
* **AWS to City (Realistic Mode)**: Bypasses the AWS matrix. Calculates the exact Haversine geographic distance between the data center and the city coordinates, multiplies it by 0.012 ms per kilometer, and adds a last-mile infrastructure tier tax (Tier 1: +5ms to Tier 4: +60ms).

### Cost-Effective Coverage Algorithm
The tool treats your defined SLA as a strict pass/fail gate. For each candidate AWS region, it calculates a **Cost Efficiency Score** (`Region_Cost ÷ Customers_Covered`). Lower scores win. The algorithm iteratively picks the cheapest combination of regions to get 100% of your un-covered customers into the "Pass" state.

## 📜 License

[MIT License](LICENSE)
