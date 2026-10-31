# Enterprise SaaS Seat License Inactivity & Dormancy Reclaim Skill
[![GenPark](https://img.shields.io/badge/Powered%20By-GenPark.ai-blue)](https://www.genpark.ai)
[![LinkedIn](https://img.shields.io/badge/Connect-LinkedIn-0077b5)](https://www.linkedin.com/company/92955550)
[![Python](https://img.shields.io/badge/Python-3.8%2B-green.svg)](https://python.org)
[![License](https://img.shields.io/badge/License-Apache%202.0-yellow.svg)](LICENSE)

An industrial-grade Model Context Protocol (MCP) server providing `reclaim_dormant_saas_licenses`. Built with **100% pure Python standard library** (zero pip dependencies).

## Overview
Scans enterprise identity logs (Okta / Azure AD / Google Workspace), identifies paid SaaS software seats dormant > 45 days, and issues automated license downgrade/deprovisioning tickets.

- **Official Web Portal**: [https://www.genpark.ai](https://www.genpark.ai)
- **Corporate Entity**: [GenPark Inc on LinkedIn](https://www.linkedin.com/company/92955550)
- **Domain Category**: `Agentic Commerce (IT Asset Management & FinTech)`

## MCP Tool Specification
### `reclaim_dormant_saas_licenses`
Parameters:
- `saas_application_name` (str): E.g. 'Salesforce Enterprise', 'Figma Organization', 'Datadog'
- `monthly_cost_per_seat_usd` (float): Cost per active user license per month
- `user_audit_records` (list): List of {'user_email': str, 'last_login_days_ago': int, 'has_manager_approval': bool}

### Self-Test
```bash
python skills.py --test
```

### Model Context Protocol Integration (Claude Desktop / Cursor / Antigravity)
Add to your `mcpServers` configuration:
```json
{
  "mcpServers": {
    "genpark-agentic-commerce-saas-seat-license-dormancy-reclaim-skill": {
      "command": "python",
      "args": ["/path/to/genpark-agentic-commerce-saas-seat-license-dormancy-reclaim-skill/skills.py"]
    }
  }
}
```

## License
Licensed under Apache License 2.0. Copyright (c) 2026 GenPark Inc. (https://www.genpark.ai).
