# 🛡️ Microsoft Sentinel Analytics Rules

A personal collection of custom Microsoft Sentinel analytics rules and KQL queries — built from real-world detection engineering experience. Each rule is ready to use and available in two formats for flexibility.

---

## 📁 Repository Structure

```
/
├── Helpful Queries/
│   └── Determine Mean Time to Detect for Analytics Rules.kql
│
├── IOC Queries/
│   ├── Chrysalis Backdoor Notepad++ Rapid7 IOC Threat Hunt.kql
│   └── readme.md
│
├── KQL/
│   ├── Multiple Email Reports with Matching Entities/
│   │   ├── Multiple Email Reports with Matching Entities.kql
│   │   └── Multiple Email Reports with Matching Entities.json
│   │
│   ├── Sentinel Data Connector Status Anomaly Detection/
│   │   ├── Sentinel Data Connector Status Anomaly Detection.kql
│   │   └── Sentinel Data Connector Status Anomaly Detection.json
│   │
│   └── Suspicious Email Interaction with Downstream Execution IOC/
│       ├── Suspicious Email Interaction with Downstream Execution IOC.kql
│       └── Suspicious Email Interaction with Downstream Execution IOC.json
│
└── README.md
```

**Helpful Queries** — standalone KQL utility queries (not analytics rules), useful for operational insight and reporting.

**IOC Queries** — threat hunting queries built around specific IOCs or threat actor TTPs.

**KQL** — full analytics rules, each with a raw `.kql` file and an importable `.json` ARM template.

---

## 🚀 How to Use

### Option 1 — Import the JSON (Recommended)

1. In the [Azure Portal](https://portal.azure.com), navigate to your **Microsoft Sentinel** workspace.
2. Go to **Analytics** → **Active rules**.
3. Click **Import** and upload the `.json` file from the rule's folder.
4. Review the rule settings and click **Save**.

### Option 2 — Run the Raw KQL

1. Open the `.kql` file in the rule's folder.
2. Paste the query into **Sentinel → Logs** or the **Log Analytics query editor**.
3. Adjust any parameters (time range, thresholds, entity mappings) to suit your environment.
4. Optionally promote it to a new Scheduled Query Rule manually.

---

## 📋 Rules & Queries Index

### 🔵 Analytics Rules (`/KQL`)

| Rule Name | Description |
|-----------|-------------|
| [Multiple Email Reports with Matching Entities](./KQL/Multiple%20Email%20Reports%20with%20Matching%20Entities) | Detects multiple email alert reports that share matching entities, helping surface coordinated or repeated email-based threats. |
| [Sentinel Data Connector Status Anomaly Detection](./KQL/Sentinel%20Data%20Connector%20Status%20Anomaly%20Detection) | Identifies anomalies in data connector health and ingestion status, alerting on connectors that have stopped reporting or behaving unexpectedly. |
| [Suspicious Email Interaction with Downstream Execution IOC](./KQL/Suspicious%20Email%20Interaction%20with%20Downstream%20Execution%20IOC) | Correlates email interaction events with downstream process or execution IOCs to detect phishing-to-execution attack chains. |

### 🟡 IOC Queries (`/IOC Queries`)

| Query Name | Description |
|------------|-------------|
| [Chrysalis Backdoor Notepad++ Rapid7 IOC Threat Hunt](./IOC%20Queries/Chrysalis%20Backdoor%20Notepad%2B%2B%20Rapid7%20IOC%20Threat%20Hunt.kql) | Threat hunting query targeting IOCs associated with the Chrysalis backdoor delivered via a malicious Notepad++ plugin, based on Rapid7 threat intelligence. |

### 🟢 Helpful Queries (`/Helpful Queries`)

| Query Name | Description |
|------------|-------------|
| [Determine Mean Time to Detect for Analytics Rules](./Helpful%20Queries/Determine%20Mean%20Time%20to%20Detect%20for%20Analytics%20Rules.kql) | Calculates the Mean Time to Detect (MTTD) across your Sentinel analytics rules, useful for measuring and reporting on SOC detection performance. |

---

## ⚙️ Requirements

- Microsoft Sentinel workspace (Log Analytics)
- Appropriate data connectors enabled depending on the rule — check each rule's `.kql` file for the tables referenced
- Analytics rules in `/KQL` require a Sentinel workspace with scheduled query rule creation permissions

---

## 📌 Notes

- Rules are provided **as-is** and should be tested in a non-production environment before deployment.
- Thresholds, time windows, and entity mappings may need tuning to reduce false positives in your specific environment.
- KQL queries use the `TimeGenerated` field and target the **Microsoft Sentinel / Log Analytics** table schema.

---

## 🤝 Contributing

This is a personal repository, but suggestions and feedback are welcome. If you spot an issue with a rule or have an improvement idea, feel free to open an Issue.

---

## 📄 License

This project is licensed under the [MIT License](LICENSE). You are free to use, modify, and distribute these rules — attribution is appreciated but not required.

---

*Built with ❤️ and too many late-night threat hunts.*
