# 🛡️ Microsoft Sentinel Analytics Rules

A personal collection of custom Microsoft Sentinel analytics rules — built from real-world detection engineering experience. Each rule is ready to use and available in two formats for flexibility.

---

## 📁 Repository Structure

```
/
├── Rule-Name/
│   ├── rule.kql          # Raw KQL query — run directly in Log Analytics or Sentinel
│   └── rule.json         # ARM template — import directly into Sentinel
├── Another-Rule/
│   ├── rule.kql
│   └── rule.json
└── README.md
```

Each folder represents a single analytics rule. The folder name reflects the rule's purpose.

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
4. Optionally create a new Scheduled Query Rule from the query manually.

---

## ⚙️ Requirements

- Microsoft Sentinel workspace (Log Analytics)
- Appropriate data connectors enabled for each rule's required tables
- Each rule folder will note any specific table or connector dependencies in future updates

---

## 📌 Notes

- Rules are provided **as-is** and should be tested in a non-production environment before deployment.
- Thresholds, time windows, and entity mappings may need tuning to reduce false positives in your specific environment.
- KQL queries target the **Unified Security Operations Platform** table schema. If you're on a legacy workspace, minor adjustments may be needed.

---

## 🤝 Contributing

This is a personal repository, but suggestions and feedback are welcome. If you spot an issue with a rule or have an improvement idea, feel free to open an Issue.

---

## 📄 License

This project is licensed under the [MIT License](LICENSE). You are free to use, modify, and distribute these rules — attribution is appreciated but not required.

---

*Built with ❤️ and too many late-night threat hunts.*
