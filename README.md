# 🛡️ Microsoft Sentinel Analytics Rules

A personal collection of custom Microsoft Sentinel analytics rules and KQL queries — built from real-world detection engineering experience.

---

## 📁 Repository Structure

```
/
├── Helpful Queries/       # Standalone KQL utility queries for operational insight and reporting
├── IOC Queries/           # Threat hunting queries built around specific IOCs or threat actor TTPs
└── KQL/                   # Full analytics rules — each subfolder contains a .kql and .json file
```

### Folders

**`/Helpful Queries`** — Standalone KQL queries that aren't analytics rules but are useful for day-to-day SOC operations, reporting, and Sentinel health checks.

**`/IOC Queries`** — Threat hunting queries tied to specific IOCs or threat actor campaigns. Run these manually in Log Analytics when investigating a specific threat.

**`/KQL`** — The main analytics rules. Each subfolder contains:
- A raw `.kql` file — paste directly into Log Analytics or Sentinel Logs
- A `.json` ARM template — import directly into Sentinel as a Scheduled Query Rule

---

## 🚀 How to Use

### Import a rule into Sentinel (Recommended)

1. Navigate to your **Microsoft Sentinel** workspace in the [Azure Portal](https://portal.azure.com).
2. Go to **Analytics** → **Active rules**.
3. Click **Import** and upload the `.json` file from the relevant folder.
4. Review and save.

### Run the raw KQL

1. Copy the contents of the `.kql` file.
2. Paste into **Sentinel → Logs** or your Log Analytics workspace.
3. Tune thresholds and time windows to your environment as needed.

---

## 📌 Notes

- All rules are provided **as-is** and should be tested before deploying to production.
- Thresholds and entity mappings may need tuning to suit your environment and reduce false positives.
- Queries use the `TimeGenerated` field and target the standard Microsoft Sentinel / Log Analytics table schema.

---

## 📄 License

Licensed under the [MIT License](LICENSE). Free to use, modify, and distribute — attribution appreciated but not required.

---
