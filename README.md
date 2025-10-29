# Distressed Property Outreach Automation  
*2025 AI Property Insights Hackathon (BatchData)*  
**Author:** _Alfonso Hernandez_

This project automates the workflow for identifying distressed properties, skip-tracing property owners, and generating personalized outreach messages using AI. It is designed for real estate investors, wholesalers, and solo operators who want fast, repeatable lead processing without manual effort.

The notebook pulls targeted property data from BatchData, performs skip-trace lookups to retrieve owner contact information, filters out phone numbers on Do Not Call lists, and uses OpenAI to generate compliant outreach templates (email, phone script, and letter copy).  
Results can be exported to CSV for outbound dialers, mail merge, CRM ingestion, AWS SES / Connect, print mailers, etc.

---

## ✅ Features

| Feature | Description |
|--------|-------------|
| **BatchData Property Search** | Discover distressed and high-probability seller leads. |
| **Skip Tracing** | Automatically retrieve owner phones, emails, and mailing addresses. |
| **DNC Filtering** | Removes phone numbers marked as Do-Not-Call. |
| **AI Outreach Messaging** | Generates email, call script, and letter for each owner. |
| **Export-Ready Structuring** | Produces clean Python dictionaries and CSV-friendly fields. |

---

## 🧠 Workflow Overview

1. Query BatchData distressed property lists.
2. Skip trace owners to retrieve contact information.
3. Filter out disallowed or low-quality contact points.
4. Use OpenAI to produce personalized outreach messaging.
5. Export results to CSV / CRM / dialer / mail system.

---

## 🧩 Requirements

- Python 3.9+
- Virtual environment recommended (`.venv`)
- API Keys for:
  - BatchData
  - OpenAI

Install dependencies:

```bash
pip install -r requirements.txt
```

---

## 🔐 Environment Setup

Create a `.env` file:

```
BATCHDATA_API_PROD_KEY=your_batchdata_api_key
BATCHDATA_API_BASE_URL=https://api.batchdata.com/api/v1
OPENAI_API_KEY=your_openai_api_key
```

Be sure your `.gitignore` *includes* `.env`.

---

### Example `.env.example`

```
# Copy this to `.env` and fill in real keys

BATCHDATA_API_PROD_KEY=
BATCHDATA_API_BASE_URL=https://api.batchdata.com/api/v1
OPENAI_API_KEY=
```

---

## ▶️ Running the Notebook

1. Launch VS Code / Jupyter.
2. Run all cells sequentially.
3. Review outputs in the variables:
   - `contacts`
   - `outreach_assets`

Export or integrate into your workflow as needed.

---

## 📤 Sample Output Structure

```json
{
  "name": "Cedarbrook LLC",
  "address": "4522 W Ravina Ln, Phoenix, AZ 85086",
  "phones_ok_to_call": ["6464966437"],
  "emails": ["proudmommy0408@gmail.com"],
  "assets": {
    "email_subject": "Just a Quick Note",
    "email_body": "...",
    "call_script": "...",
    "letter_body": "..."
  }
}
```

---

## 🚀 Future Enhancements

| Enhancement | Description |
|-------------|-------------|
| Streamlit UI | One-click CSV generation & zip code input. |
| Multi-Property Owner Ranking | Prioritize high-value targets. |
| Market Heatmapping | Identify “hot zones” of distress activity. |
| CRM Integration | Podio / Resimpli / HubSpot / Salesforce sync. |
| Automated Delivery | AWS Connect auto-dial + SES + print mail queue. |

---

## 📝 License
MIT License

---

## 🤝 Acknowledgments
- **BatchData** — Data platform and hackathon sponsor.
- **2025 AI Property Insights Hackathon** — courtesy of [Tech in Real Estate]([http://example.com](https://www.skool.com/techinrealestate)) and Ariel Herrera.
- **OpenAI** — Outreach generation.
