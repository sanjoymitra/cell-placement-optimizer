# ATLAS

**Cell Placement & Onboarding Cost Assessment Suite**

ATLAS is an interactive, fully self-contained internal planning tool designed for Infrastructure Strategy and Project Management teams. It allows users to optimize AWS infrastructure deployments based on latency SLAs and generate accurate financial quotes and timelines for customer onboarding.

The application runs entirely in the browser (zero backend required), ensuring complete data privacy and high portability.

---

## 🚀 Key Features

### 1. Cell Placement Optimizer
An interactive mapping and infrastructure planner designed to find the most cost-effective regions to deploy new server cells.

- **Interactive Mapping:** Plot existing cells and target customer endpoints.
- **SLA Configuration:** Set custom latency thresholds and compute direct distances.
- **Cost Calculation:** Estimate OpEx using blended global averages or specific regional baseline indices (e.g., Paris = 1.10x).

### 2. Onboarding Cost Calculator (Interactive Gantt)
A dynamic project scoping tool that pairs financial quoting with an interactive timeline.

- **Dynamic Scoping (3 Tiers):** Instantly generate project templates based on infrastructure needs:
  - *Tier 1 (Full Deployment):* New Cell + New Service Provider integration.
  - *Tier 2 (Integration Only):* Existing Cell + New Service Provider integration.
  - *Tier 3 (Standard Onboarding):* Existing Cell & Existing Provider.
- **Financial Quoting:** Input desired margins and blended hourly rates to instantly see total internal costs versus the final customer price.
- **Interactive Timeline:** Drag-and-drop row reordering, inline task editing, intelligent dependency cascading, and customizable effort hours.

### 3. Session Management & Export
- **JSON State Management:** Export your current session as a JSON file and import it later to resume work.
- **Client Proposals (Beta):** Generate a clean, branded PDF summarizing the deployment strategy and timeline, masking internal margins for external client viewing.

---

## 🛠️ Tech Stack

This project is built using a modern, lightweight, frontend-only tech stack to ensure it remains a highly portable, single-file application.

- **Core:** HTML5, CSS3, Vanilla JavaScript (ES6+)
- **Styling & UI:** Tailwind CSS (via CDN)
- **Interactive Timeline:** DHTMLX Gantt (Client-side interactive chart rendering)
- **Icons & Typography:**
  - FontAwesome
  - Phosphor Icons
  - Google Fonts (Inter)
- **Data Storage:** In-memory browser state (Offline JSON Export/Import capabilities)

---

## 🔐 Data Privacy & Security

By design, this tool does not communicate with any external databases. All inputs, infrastructure plans, and financial margins are stored temporarily in your browser's local memory.

To save your work across sessions, use the **Export → Export Session Data (JSON)** feature in the top right corner of the application.
