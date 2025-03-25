
# 🔐 How to Get Your Confluence API Token

If you're using **Atlassian Cloud** (e.g., `yourcompany.atlassian.net`), follow these steps to generate and use your Confluence API token.

---

## 🪪 Step 1: Create an API Token

1. **Go to the Atlassian API Token Page:**  
   👉 [https://id.atlassian.com/manage-profile/security/api-tokens](https://id.atlassian.com/manage-profile/security/api-tokens)

2. **Log in** with your Atlassian (Confluence/Jira) account.

3. Click **"Create API token"**.

4. Enter a label like: `"Confluence Space Access"`.

5. Click **"Create"**.

6. **Copy the token immediately** – this is the only time it will be shown.  
   Paste it into your secure password manager or use it in your `.env` file right away.

---

## 🧪 Example: Using the API Token in Python

### `.env` File

```
CONFLUENCE_EMAIL=your.email@company.com
CONFLUENCE_API_TOKEN=your_generated_token_here
```

### `example.py`

```python
import requests
from requests.auth import HTTPBasicAuth
import os
from dotenv import load_dotenv

load_dotenv()

EMAIL = os.getenv("CONFLUENCE_EMAIL")
API_TOKEN = os.getenv("CONFLUENCE_API_TOKEN")
BASE_URL = "https://yourcompany.atlassian.net/wiki/rest/api"

response = requests.get(
    f"{BASE_URL}/space",
    auth=HTTPBasicAuth(EMAIL, API_TOKEN),
    headers={"Accept": "application/json"}
)

print(response.json())
```

---

## 🛠️ Need Self-Hosted (On-Prem) Confluence?
If you're using **self-hosted Confluence**, the authentication method might be different (e.g., personal access tokens or Basic Auth). Reach out to your admin or refer to your local Confluence documentation.

---

Happy Integrating! 🚀
